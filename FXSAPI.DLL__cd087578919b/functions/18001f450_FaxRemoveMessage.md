# FaxRemoveMessage

- ea: `0x18001f450`
- end: `0x18001f634`
- name: `FaxRemoveMessage`
- size: `484`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18001f450`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001f573`
- `RPCRT4!NdrClientCall3` at `0x18001f573`
- `KERNEL32!SetLastError` at `0x18001f4d0`
- `KERNEL32!SetLastError` at `0x18001f53b`
- `KERNEL32!SetLastError` at `0x18001f5e5`
- `KERNEL32!SetLastError` at `0x18001f4d0`
- `KERNEL32!SetLastError` at `0x18001f53b`
- `KERNEL32!SetLastError` at `0x18001f5e5`

## pseudocode

```c
__int64 __fastcall FaxRemoveMessage(__int64 a1, __int64 a2, unsigned int a3)
{
  _QWORD *v6; // rcx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  DWORD v9; // ecx
  unsigned int Pointer; // eax

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 264, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a1 || !*(_DWORD *)a1 || *(_DWORD *)(a1 + 16) )
  {
    SetLastError(6u);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v8 = 265;
LABEL_27:
    WPP_SF_(v7[2], v8, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
    return 0;
  }
  if ( !a2 )
  {
    SetLastError(0x57u);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v8 = 266;
    goto LABEL_27;
  }
  if ( a3 <= 1 )
  {
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x43u,
                              0,
                              **(_QWORD **)(a1 + 32),
                              a2,
                              a3).Pointer;
    if ( !Pointer )
      return 1;
    v9 = Pointer;
  }
  else
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x1000) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      WPP_SF_d(v6[2], 267, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, a3);
    v9 = 87;
  }
  SetLastError(v9);
  return 0;
}

```

## disassembly

```asm
0x18001f450  mov     [rsp+arg_8], rbx
0x18001f455  mov     [rsp+arg_10], rsi
0x18001f45a  push    rdi
0x18001f45b  push    r14
0x18001f45d  push    r15
0x18001f45f  sub     rsp, 40h
0x18001f463  mov     esi, r8d
0x18001f466  mov     r14, rdx
0x18001f469  mov     rdi, rcx
0x18001f46c  lea     r15, WPP_GLOBAL_Control
0x18001f473  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f47a  mov     ebx, 1000h
0x18001f47f  cmp     rcx, r15
0x18001f482  jz      short loc_18001F4AB
0x18001f484  test    [rcx+1Ch], ebx
0x18001f487  jz      short loc_18001F4AB
0x18001f489  cmp     byte ptr [rcx+19h], 5
0x18001f48d  jb      short loc_18001F4AB
0x18001f48f  mov     edx, 108h
0x18001f494  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001f49b  mov     rcx, [rcx+10h]
0x18001f49f  call    WPP_SF_
0x18001f4a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4ab  test    rdi, rdi
0x18001f4ae  jz      loc_18001F5E0
0x18001f4b4  cmp     dword ptr [rdi], 0
0x18001f4b7  jz      loc_18001F5E0
0x18001f4bd  cmp     dword ptr [rdi+10h], 0
0x18001f4c1  jnz     loc_18001F5E0
0x18001f4c7  test    r14, r14
0x18001f4ca  jnz     short loc_18001F509
0x18001f4cc  lea     ecx, [r14+57h]; dwErrCode
0x18001f4d0  call    cs:__imp_SetLastError
0x18001f4d7  nop     dword ptr [rax+rax+00h]
0x18001f4dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4e3  cmp     rcx, r15
0x18001f4e6  jz      loc_18001F61D
0x18001f4ec  test    [rcx+1Ch], ebx
0x18001f4ef  jz      loc_18001F61D
0x18001f4f5  cmp     byte ptr [rcx+19h], 2
0x18001f4f9  jb      loc_18001F61D
0x18001f4ff  mov     edx, 10Ah
0x18001f504  jmp     loc_18001F60D
0x18001f509  cmp     esi, 1
0x18001f50c  jbe     short loc_18001F54C
0x18001f50e  cmp     rcx, r15
0x18001f511  jz      short loc_18001F536
0x18001f513  test    [rcx+1Ch], ebx
0x18001f516  jz      short loc_18001F536
0x18001f518  cmp     byte ptr [rcx+19h], 2
0x18001f51c  jb      short loc_18001F536
0x18001f51e  mov     edx, 10Bh
0x18001f523  mov     r9d, esi
0x18001f526  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001f52d  mov     rcx, [rcx+10h]
0x18001f531  call    WPP_SF_d
0x18001f536  mov     ecx, 57h ; 'W'; dwErrCode
0x18001f53b  call    cs:__imp_SetLastError
0x18001f542  nop     dword ptr [rax+rax+00h]
0x18001f547  jmp     loc_18001F61D
0x18001f54c  mov     rax, [rdi+20h]
0x18001f550  mov     [rsp+58h+arg_0], 0
0x18001f559  mov     [rsp+58h+var_30], esi
0x18001f55d  mov     [rsp+58h+var_38], r14
0x18001f562  mov     r9, [rax]
0x18001f565  xor     r8d, r8d; pReturnValue
0x18001f568  lea     edx, [r8+43h]; nProcNum
0x18001f56c  lea     rcx, pProxyInfo; pProxyInfo
0x18001f573  call    cs:__imp_NdrClientCall3
0x18001f57a  nop     dword ptr [rax+rax+00h]
0x18001f57f  mov     rbx, rax
0x18001f582  mov     [rsp+58h+arg_0], rax
0x18001f587  mov     [rsp+58h+var_28], eax
0x18001f58b  jmp     short loc_18001F5CE
0x18001f58d  mov     ebx, eax
0x18001f58f  mov     [rsp+58h+var_28], eax
0x18001f593  lea     rdx, WPP_GLOBAL_Control
0x18001f59a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f5a1  cmp     rcx, rdx
0x18001f5a4  jz      short loc_18001F5CE
0x18001f5a6  test    dword ptr [rcx+1Ch], 1000h
0x18001f5ad  jz      short loc_18001F5CE
0x18001f5af  cmp     byte ptr [rcx+19h], 2
0x18001f5b3  jb      short loc_18001F5CE
0x18001f5b5  mov     edx, 10Ch
0x18001f5ba  mov     r9d, eax
0x18001f5bd  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001f5c4  mov     rcx, [rcx+10h]
0x18001f5c8  call    WPP_SF_d
0x18001f5cd  nop
0x18001f5ce  test    ebx, ebx
0x18001f5d0  jz      short loc_18001F5D9
0x18001f5d2  mov     ecx, ebx
0x18001f5d4  jmp     loc_18001F53B
0x18001f5d9  mov     eax, 1
0x18001f5de  jmp     short loc_18001F61F
0x18001f5e0  mov     ecx, 6; dwErrCode
0x18001f5e5  call    cs:__imp_SetLastError
0x18001f5ec  nop     dword ptr [rax+rax+00h]
0x18001f5f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f5f8  cmp     rcx, r15
0x18001f5fb  jz      short loc_18001F61D
0x18001f5fd  test    [rcx+1Ch], ebx
0x18001f600  jz      short loc_18001F61D
0x18001f602  cmp     byte ptr [rcx+19h], 2
0x18001f606  jb      short loc_18001F61D
0x18001f608  mov     edx, 109h
0x18001f60d  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001f614  mov     rcx, [rcx+10h]
0x18001f618  call    WPP_SF_
0x18001f61d  xor     eax, eax
0x18001f61f  mov     rbx, [rsp+58h+arg_8]
0x18001f624  mov     rsi, [rsp+58h+arg_10]
0x18001f629  add     rsp, 40h
0x18001f62d  pop     r15
0x18001f62f  pop     r14
0x18001f631  pop     rdi
0x18001f632  retn
```
