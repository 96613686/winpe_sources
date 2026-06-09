# FaxGetSecurity

- ea: `0x180015d40`
- end: `0x180015eea`
- name: `FaxGetSecurity`
- size: `426`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180015d40`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180015e25`
- `RPCRT4!NdrClientCall3` at `0x180015e25`
- `KERNEL32!SetLastError` at `0x180015db9`
- `KERNEL32!SetLastError` at `0x180015e86`
- `KERNEL32!SetLastError` at `0x180015ea0`
- `KERNEL32!SetLastError` at `0x180015db9`
- `KERNEL32!SetLastError` at `0x180015e86`
- `KERNEL32!SetLastError` at `0x180015ea0`

## pseudocode

```c
__int64 __fastcall FaxGetSecurity(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  _QWORD *v6; // rax
  CLIENT_CALL_RETURN v7; // rax
  int v9; // [rsp+60h] [rbp+8h] BYREF
  CLIENT_CALL_RETURN v10; // [rsp+70h] [rbp+18h]

  v9 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids);
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
    v5 = 48;
LABEL_20:
    WPP_SF_(v4[2], v5, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids);
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
    v5 = 49;
    goto LABEL_20;
  }
  *a2 = 0;
  v6 = *(_QWORD **)(a1 + 32);
  v10.Simple = 0;
  v7.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x17u, 0, *v6, a2, &v9).Pointer;
  v10.Pointer = v7.Pointer;
  if ( !LODWORD(v7.Pointer) )
    return 1;
  SetLastError((DWORD)v7.Pointer);
  return 0;
}

```

## disassembly

```asm
0x180015d40  mov     [rsp+arg_8], rbx
0x180015d45  push    rsi
0x180015d46  push    r14
0x180015d48  push    r15
0x180015d4a  sub     rsp, 40h
0x180015d4e  mov     r14, rdx
0x180015d51  mov     rsi, rcx
0x180015d54  mov     [rsp+58h+arg_0], 0
0x180015d5c  lea     r15, WPP_GLOBAL_Control
0x180015d63  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d6a  mov     ebx, 1000h
0x180015d6f  cmp     rcx, r15
0x180015d72  jz      short loc_180015D94
0x180015d74  test    [rcx+1Ch], ebx
0x180015d77  jz      short loc_180015D94
0x180015d79  cmp     byte ptr [rcx+19h], 5
0x180015d7d  jb      short loc_180015D94
0x180015d7f  mov     edx, 2Fh ; '/'
0x180015d84  lea     r8, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids
0x180015d8b  mov     rcx, [rcx+10h]
0x180015d8f  call    WPP_SF_
0x180015d94  test    rsi, rsi
0x180015d97  jz      loc_180015E9B
0x180015d9d  cmp     dword ptr [rsi], 0
0x180015da0  jz      loc_180015E9B
0x180015da6  cmp     dword ptr [rsi+10h], 0
0x180015daa  jnz     loc_180015E9B
0x180015db0  test    r14, r14
0x180015db3  jnz     short loc_180015DF1
0x180015db5  lea     ecx, [r14+57h]; dwErrCode
0x180015db9  call    cs:__imp_SetLastError
0x180015dc0  nop     dword ptr [rax+rax+00h]
0x180015dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180015dcc  cmp     rcx, r15
0x180015dcf  jz      loc_180015ED8
0x180015dd5  test    [rcx+1Ch], ebx
0x180015dd8  jz      loc_180015ED8
0x180015dde  cmp     byte ptr [rcx+19h], 2
0x180015de2  jb      loc_180015ED8
0x180015de8  lea     edx, [r14+31h]
0x180015dec  jmp     loc_180015EC8
0x180015df1  mov     qword ptr [r14], 0
0x180015df8  mov     rax, [rsi+20h]
0x180015dfc  mov     [rsp+58h+arg_10], 0
0x180015e05  lea     rcx, [rsp+58h+arg_0]
0x180015e0a  mov     [rsp+58h+var_30], rcx
0x180015e0f  mov     [rsp+58h+var_38], r14
0x180015e14  mov     r9, [rax]
0x180015e17  xor     r8d, r8d; pReturnValue
0x180015e1a  lea     edx, [r8+17h]; nProcNum
0x180015e1e  lea     rcx, pProxyInfo; pProxyInfo
0x180015e25  call    cs:__imp_NdrClientCall3
0x180015e2c  nop     dword ptr [rax+rax+00h]
0x180015e31  mov     rbx, rax
0x180015e34  mov     [rsp+58h+arg_10], rax
0x180015e39  mov     [rsp+58h+var_28], eax
0x180015e3d  jmp     short loc_180015E80
0x180015e3f  mov     ebx, eax
0x180015e41  mov     [rsp+58h+var_28], eax
0x180015e45  lea     rdx, WPP_GLOBAL_Control
0x180015e4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e53  cmp     rcx, rdx
0x180015e56  jz      short loc_180015E80
0x180015e58  test    dword ptr [rcx+1Ch], 1000h
0x180015e5f  jz      short loc_180015E80
0x180015e61  cmp     byte ptr [rcx+19h], 2
0x180015e65  jb      short loc_180015E80
0x180015e67  mov     edx, 32h ; '2'
0x180015e6c  mov     r9d, eax
0x180015e6f  lea     r8, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids
0x180015e76  mov     rcx, [rcx+10h]
0x180015e7a  call    WPP_SF_d
0x180015e7f  nop
0x180015e80  test    ebx, ebx
0x180015e82  jz      short loc_180015E94
0x180015e84  mov     ecx, ebx; dwErrCode
0x180015e86  call    cs:__imp_SetLastError
0x180015e8d  nop     dword ptr [rax+rax+00h]
0x180015e92  jmp     short loc_180015ED8
0x180015e94  mov     eax, 1
0x180015e99  jmp     short loc_180015EDA
0x180015e9b  mov     ecx, 6; dwErrCode
0x180015ea0  call    cs:__imp_SetLastError
0x180015ea7  nop     dword ptr [rax+rax+00h]
0x180015eac  mov     rcx, cs:WPP_GLOBAL_Control
0x180015eb3  cmp     rcx, r15
0x180015eb6  jz      short loc_180015ED8
0x180015eb8  test    [rcx+1Ch], ebx
0x180015ebb  jz      short loc_180015ED8
0x180015ebd  cmp     byte ptr [rcx+19h], 2
0x180015ec1  jb      short loc_180015ED8
0x180015ec3  mov     edx, 30h ; '0'
0x180015ec8  lea     r8, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids
0x180015ecf  mov     rcx, [rcx+10h]
0x180015ed3  call    WPP_SF_
0x180015ed8  xor     eax, eax
0x180015eda  mov     rbx, [rsp+58h+arg_8]
0x180015edf  add     rsp, 40h
0x180015ee3  pop     r15
0x180015ee5  pop     r14
0x180015ee7  pop     rsi
0x180015ee8  retn
```
