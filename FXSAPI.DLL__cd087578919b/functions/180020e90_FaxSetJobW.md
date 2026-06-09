# FaxSetJobW

- ea: `0x180020e90`
- end: `0x180021069`
- name: `FaxSetJobW`
- size: `473`
- prototype: `BOOL __stdcall(HANDLE FaxHandle, DWORD JobId, DWORD Command, const FAX_JOB_ENTRYW *JobEntry)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020dd0`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180020e90`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180020f2c`
- `RPCRT4!NdrClientCall3` at `0x180020f2c`
- `KERNEL32!SetLastError` at `0x180020f93`
- `KERNEL32!SetLastError` at `0x180020fec`
- `KERNEL32!SetLastError` at `0x18002101f`
- `KERNEL32!SetLastError` at `0x180020f93`
- `KERNEL32!SetLastError` at `0x180020fec`
- `KERNEL32!SetLastError` at `0x18002101f`

## pseudocode

```c
BOOL __stdcall FaxSetJobW(HANDLE FaxHandle, DWORD JobId, DWORD Command, const FAX_JOB_ENTRYW *JobEntry)
{
  DWORD Pointer; // eax
  DWORD v8; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
  }
  if ( !FaxHandle || !*(_DWORD *)FaxHandle || *((_DWORD *)FaxHandle + 4) )
  {
    SetLastError(6u);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v11 = 92;
LABEL_23:
    WPP_SF_(v10[2], v11, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
    return 0;
  }
  if ( Command - 1 > 2 )
  {
    SetLastError(0x57u);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v11 = 93;
    goto LABEL_23;
  }
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            6u,
                            0,
                            **((_QWORD **)FaxHandle + 4),
                            JobId,
                            Command).Pointer;
  v8 = Pointer;
  if ( !Pointer )
    return 1;
  SetLastError(Pointer);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180020e90  push    rbx
0x180020e92  push    rsi
0x180020e93  push    r14
0x180020e95  push    r15
0x180020e97  sub     rsp, 48h
0x180020e9b  mov     r14d, r8d
0x180020e9e  mov     r15d, edx
0x180020ea1  mov     rbx, rcx
0x180020ea4  lea     rsi, WPP_GLOBAL_Control
0x180020eab  mov     rcx, cs:WPP_GLOBAL_Control
0x180020eb2  cmp     rcx, rsi
0x180020eb5  jz      short loc_180020EDB
0x180020eb7  test    dword ptr [rcx+1Ch], 1000h
0x180020ebe  jz      short loc_180020EDB
0x180020ec0  cmp     byte ptr [rcx+19h], 5
0x180020ec4  jb      short loc_180020EDB
0x180020ec6  mov     edx, 5Bh ; '['
0x180020ecb  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180020ed2  mov     rcx, [rcx+10h]
0x180020ed6  call    WPP_SF_
0x180020edb  test    rbx, rbx
0x180020ede  jz      loc_18002101A
0x180020ee4  cmp     dword ptr [rbx], 0
0x180020ee7  jz      loc_18002101A
0x180020eed  cmp     dword ptr [rbx+10h], 0
0x180020ef1  jnz     loc_18002101A
0x180020ef7  lea     eax, [r14-1]
0x180020efb  cmp     eax, 2
0x180020efe  ja      loc_180020FE7
0x180020f04  mov     rax, [rbx+20h]
0x180020f08  mov     [rsp+68h+arg_0], 0
0x180020f11  mov     [rsp+68h+var_40], r14d
0x180020f16  mov     [rsp+68h+var_48], r15d
0x180020f1b  mov     r9, [rax]
0x180020f1e  xor     r8d, r8d; pReturnValue
0x180020f21  lea     edx, [r8+6]; nProcNum
0x180020f25  lea     rcx, pProxyInfo; pProxyInfo
0x180020f2c  call    cs:__imp_NdrClientCall3
0x180020f33  nop     dword ptr [rax+rax+00h]
0x180020f38  mov     rbx, rax
0x180020f3b  mov     [rsp+68h+arg_0], rax
0x180020f40  mov     [rsp+68h+var_38], eax
0x180020f44  jmp     short loc_180020F8D
0x180020f46  mov     ebx, eax
0x180020f48  mov     [rsp+68h+var_38], eax
0x180020f4c  lea     rdx, WPP_GLOBAL_Control
0x180020f53  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f5a  cmp     rcx, rdx
0x180020f5d  jz      short loc_180020F86
0x180020f5f  test    dword ptr [rcx+1Ch], 1000h
0x180020f66  jz      short loc_180020F86
0x180020f68  cmp     byte ptr [rcx+19h], 2
0x180020f6c  jb      short loc_180020F86
0x180020f6e  mov     edx, 5Eh ; '^'
0x180020f73  mov     r9d, eax
0x180020f76  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180020f7d  mov     rcx, [rcx+10h]
0x180020f81  call    WPP_SF_d
0x180020f86  lea     rsi, WPP_GLOBAL_Control
0x180020f8d  test    ebx, ebx
0x180020f8f  jz      short loc_180020FE0
0x180020f91  mov     ecx, ebx; dwErrCode
0x180020f93  call    cs:__imp_SetLastError
0x180020f9a  nop     dword ptr [rax+rax+00h]
0x180020f9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020fa6  cmp     rcx, rsi
0x180020fa9  jz      loc_18002105B
0x180020faf  test    dword ptr [rcx+1Ch], 1000h
0x180020fb6  jz      loc_18002105B
0x180020fbc  cmp     byte ptr [rcx+19h], 2
0x180020fc0  jb      loc_18002105B
0x180020fc6  mov     edx, 5Fh ; '_'
0x180020fcb  mov     r9d, ebx
0x180020fce  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180020fd5  mov     rcx, [rcx+10h]
0x180020fd9  call    WPP_SF_d
0x180020fde  jmp     short loc_18002105B
0x180020fe0  mov     eax, 1
0x180020fe5  jmp     short loc_18002105D
0x180020fe7  mov     ecx, 57h ; 'W'; dwErrCode
0x180020fec  call    cs:__imp_SetLastError
0x180020ff3  nop     dword ptr [rax+rax+00h]
0x180020ff8  mov     rcx, cs:WPP_GLOBAL_Control
0x180020fff  cmp     rcx, rsi
0x180021002  jz      short loc_18002105B
0x180021004  test    dword ptr [rcx+1Ch], 1000h
0x18002100b  jz      short loc_18002105B
0x18002100d  cmp     byte ptr [rcx+19h], 2
0x180021011  jb      short loc_18002105B
0x180021013  mov     edx, 5Dh ; ']'
0x180021018  jmp     short loc_18002104B
0x18002101a  mov     ecx, 6; dwErrCode
0x18002101f  call    cs:__imp_SetLastError
0x180021026  nop     dword ptr [rax+rax+00h]
0x18002102b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021032  cmp     rcx, rsi
0x180021035  jz      short loc_18002105B
0x180021037  test    dword ptr [rcx+1Ch], 1000h
0x18002103e  jz      short loc_18002105B
0x180021040  cmp     byte ptr [rcx+19h], 2
0x180021044  jb      short loc_18002105B
0x180021046  mov     edx, 5Ch ; '\'
0x18002104b  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180021052  mov     rcx, [rcx+10h]
0x180021056  call    WPP_SF_
0x18002105b  xor     eax, eax
0x18002105d  add     rsp, 48h
0x180021061  pop     r15
0x180021063  pop     r14
0x180021065  pop     rsi
0x180021066  pop     rbx
0x180021067  retn
```
