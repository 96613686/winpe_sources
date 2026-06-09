# FaxUnregisterServiceProviderExW

- ea: `0x18002a3a0`
- end: `0x18002a526`
- name: `FaxUnregisterServiceProviderExW`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18002a2d0`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002a3a0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18002a466`
- `RPCRT4!NdrClientCall3` at `0x18002a466`
- `KERNEL32!SetLastError` at `0x18002a40c`
- `KERNEL32!SetLastError` at `0x18002a4c7`
- `KERNEL32!SetLastError` at `0x18002a4e1`
- `KERNEL32!SetLastError` at `0x18002a40c`
- `KERNEL32!SetLastError` at `0x18002a4c7`
- `KERNEL32!SetLastError` at `0x18002a4e1`

## pseudocode

```c
__int64 __fastcall FaxUnregisterServiceProviderExW(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  DWORD Pointer; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids);
  }
  if ( !a1 || !*(_DWORD *)a1 || *(_DWORD *)(a1 + 16) )
  {
    SetLastError(6u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 64;
LABEL_20:
    WPP_SF_(v4[2], v5, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids);
    return 0;
  }
  if ( !a2 )
  {
    SetLastError(0x57u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 65;
    goto LABEL_20;
  }
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x3Du, 0, **(_QWORD **)(a1 + 32), a2).Pointer;
  if ( !Pointer )
    return 1;
  SetLastError(Pointer);
  return 0;
}

```

## disassembly

```asm
0x18002a3a0  push    rbx
0x18002a3a2  push    rsi
0x18002a3a3  push    rdi
0x18002a3a4  push    r14
0x18002a3a6  sub     rsp, 48h
0x18002a3aa  mov     rsi, rdx
0x18002a3ad  mov     rdi, rcx
0x18002a3b0  lea     r14, WPP_GLOBAL_Control
0x18002a3b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a3be  mov     ebx, 1000h
0x18002a3c3  cmp     rcx, r14
0x18002a3c6  jz      short loc_18002A3E8
0x18002a3c8  test    [rcx+1Ch], ebx
0x18002a3cb  jz      short loc_18002A3E8
0x18002a3cd  cmp     byte ptr [rcx+19h], 5
0x18002a3d1  jb      short loc_18002A3E8
0x18002a3d3  mov     edx, 3Fh ; '?'
0x18002a3d8  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x18002a3df  mov     rcx, [rcx+10h]
0x18002a3e3  call    WPP_SF_
0x18002a3e8  test    rdi, rdi
0x18002a3eb  jz      loc_18002A4DC
0x18002a3f1  cmp     dword ptr [rdi], 0
0x18002a3f4  jz      loc_18002A4DC
0x18002a3fa  cmp     dword ptr [rdi+10h], 0
0x18002a3fe  jnz     loc_18002A4DC
0x18002a404  test    rsi, rsi
0x18002a407  jnz     short loc_18002A443
0x18002a409  lea     ecx, [rsi+57h]; dwErrCode
0x18002a40c  call    cs:__imp_SetLastError
0x18002a413  nop     dword ptr [rax+rax+00h]
0x18002a418  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a41f  cmp     rcx, r14
0x18002a422  jz      loc_18002A519
0x18002a428  test    [rcx+1Ch], ebx
0x18002a42b  jz      loc_18002A519
0x18002a431  cmp     byte ptr [rcx+19h], 2
0x18002a435  jb      loc_18002A519
0x18002a43b  lea     edx, [rsi+41h]
0x18002a43e  jmp     loc_18002A509
0x18002a443  mov     rax, [rdi+20h]
0x18002a447  mov     [rsp+68h+arg_0], 0
0x18002a450  mov     [rsp+68h+var_48], rsi
0x18002a455  mov     r9, [rax]
0x18002a458  xor     r8d, r8d; pReturnValue
0x18002a45b  lea     edx, [r8+3Dh]; nProcNum
0x18002a45f  lea     rcx, pProxyInfo; pProxyInfo
0x18002a466  call    cs:__imp_NdrClientCall3
0x18002a46d  nop     dword ptr [rax+rax+00h]
0x18002a472  mov     rbx, rax
0x18002a475  mov     [rsp+68h+arg_0], rax
0x18002a47a  mov     [rsp+68h+var_38], eax
0x18002a47e  jmp     short loc_18002A4C1
0x18002a480  mov     ebx, eax
0x18002a482  mov     [rsp+68h+var_38], eax
0x18002a486  lea     rdx, WPP_GLOBAL_Control
0x18002a48d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a494  cmp     rcx, rdx
0x18002a497  jz      short loc_18002A4C1
0x18002a499  test    dword ptr [rcx+1Ch], 1000h
0x18002a4a0  jz      short loc_18002A4C1
0x18002a4a2  cmp     byte ptr [rcx+19h], 2
0x18002a4a6  jb      short loc_18002A4C1
0x18002a4a8  mov     edx, 42h ; 'B'
0x18002a4ad  mov     r9d, eax
0x18002a4b0  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x18002a4b7  mov     rcx, [rcx+10h]
0x18002a4bb  call    WPP_SF_d
0x18002a4c0  nop
0x18002a4c1  test    ebx, ebx
0x18002a4c3  jz      short loc_18002A4D5
0x18002a4c5  mov     ecx, ebx; dwErrCode
0x18002a4c7  call    cs:__imp_SetLastError
0x18002a4ce  nop     dword ptr [rax+rax+00h]
0x18002a4d3  jmp     short loc_18002A519
0x18002a4d5  mov     eax, 1
0x18002a4da  jmp     short loc_18002A51B
0x18002a4dc  mov     ecx, 6; dwErrCode
0x18002a4e1  call    cs:__imp_SetLastError
0x18002a4e8  nop     dword ptr [rax+rax+00h]
0x18002a4ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a4f4  cmp     rcx, r14
0x18002a4f7  jz      short loc_18002A519
0x18002a4f9  test    [rcx+1Ch], ebx
0x18002a4fc  jz      short loc_18002A519
0x18002a4fe  cmp     byte ptr [rcx+19h], 2
0x18002a502  jb      short loc_18002A519
0x18002a504  mov     edx, 40h ; '@'
0x18002a509  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x18002a510  mov     rcx, [rcx+10h]
0x18002a514  call    WPP_SF_
0x18002a519  xor     eax, eax
0x18002a51b  add     rsp, 48h
0x18002a51f  pop     r14
0x18002a521  pop     rdi
0x18002a522  pop     rsi
0x18002a523  pop     rbx
0x18002a524  retn
```
