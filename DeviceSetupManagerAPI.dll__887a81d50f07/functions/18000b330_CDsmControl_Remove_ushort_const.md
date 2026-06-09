# CDsmControl::Remove(ushort const *)

- ea: `0x18000b330`
- end: `0x18000b409`
- name: `?Remove@CDsmControl@@UEAAJPEBG@Z`
- size: `217`
- prototype: `__int64 __fastcall(CDsmControl *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800017c0`
- `0x180009d20`
- `0x18000b330`
- `0x18000d524`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000b393`
- `RPCRT4!NdrClientCall3` at `0x18000b393`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000b359`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000b359`

## pseudocode

```c
__int64 __fastcall CDsmControl::Remove(CDsmControl *this, const unsigned __int16 *a2)
{
  HRESULT Pointer; // ebx
  GUID pclsid; // [rsp+40h] [rbp-28h] BYREF

  pclsid = 0;
  Pointer = CLSIDFromString(a2, &pclsid);
  if ( Pointer >= 0 )
  {
    StartDsmService();
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&stru_1800116C0,
                              4u,
                              0,
                              DsmRpcAdmin_v1_0_c_ifspec,
                              &pclsid).Pointer;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_6c51682e99e93bfa9299cbf564496992_Traceguids,
      (unsigned int)Pointer);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18000b330  mov     [rsp+arg_0], rbx
0x18000b335  push    rdi
0x18000b336  sub     rsp, 60h
0x18000b33a  mov     rax, cs:__security_cookie
0x18000b341  xor     rax, rsp
0x18000b344  mov     [rsp+68h+var_18], rax
0x18000b349  mov     rcx, rdx; lpsz
0x18000b34c  xorps   xmm0, xmm0
0x18000b34f  movups  xmmword ptr [rsp+68h+pclsid.Data1], xmm0
0x18000b354  lea     rdx, [rsp+68h+pclsid]; pclsid
0x18000b359  call    cs:__imp_CLSIDFromString
0x18000b35f  mov     ebx, eax
0x18000b361  mov     [rsp+68h+var_38], eax
0x18000b365  test    eax, eax
0x18000b367  js      short loc_18000B3BE
0x18000b369  call    ?StartDsmService@@YAJXZ; StartDsmService(void)
0x18000b36e  xor     edi, edi
0x18000b370  mov     [rsp+68h+var_30], rdi
0x18000b375  lea     rax, [rsp+68h+pclsid]
0x18000b37a  mov     [rsp+68h+var_48], rax
0x18000b37f  mov     r9, cs:DsmRpcAdmin_v1_0_c_ifspec
0x18000b386  xor     r8d, r8d; pReturnValue
0x18000b389  lea     edx, [rdi+4]; nProcNum
0x18000b38c  lea     rcx, stru_1800116C0; pProxyInfo
0x18000b393  call    cs:__imp_NdrClientCall3
0x18000b399  mov     rbx, rax
0x18000b39c  mov     [rsp+68h+var_30], rax
0x18000b3a1  mov     [rsp+68h+var_38], eax
0x18000b3a5  jmp     short loc_18000B3AD
0x18000b3a7  mov     edi, eax
0x18000b3a9  mov     ebx, [rsp+68h+var_38]
0x18000b3ad  test    edi, edi
0x18000b3af  jz      short loc_18000B3BE
0x18000b3b1  jle     short loc_18000B3BC
0x18000b3b3  movzx   edi, di
0x18000b3b6  or      edi, 80070000h
0x18000b3bc  mov     ebx, edi
0x18000b3be  lea     rax, WPP_GLOBAL_Control
0x18000b3c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3cc  cmp     rcx, rax
0x18000b3cf  jz      short loc_18000B3EF
0x18000b3d1  test    byte ptr [rcx+1Ch], 1
0x18000b3d5  jz      short loc_18000B3EF
0x18000b3d7  mov     edx, 0Eh
0x18000b3dc  mov     r9d, ebx
0x18000b3df  lea     r8, WPP_6c51682e99e93bfa9299cbf564496992_Traceguids
0x18000b3e6  mov     rcx, [rcx+10h]
0x18000b3ea  call    WPP_SF_D
0x18000b3ef  mov     eax, ebx
0x18000b3f1  mov     rcx, [rsp+68h+var_18]
0x18000b3f6  xor     rcx, rsp; StackCookie
0x18000b3f9  call    __security_check_cookie
0x18000b3fe  mov     rbx, [rsp+68h+arg_0]
0x18000b403  add     rsp, 60h
0x18000b407  pop     rdi
0x18000b408  retn
0x18000e6cb  push    rbp
0x18000e6cd  sub     rsp, 30h
0x18000e6d1  mov     rbp, rdx
0x18000e6d4  mov     rcx, [rcx]
0x18000e6d7  mov     ecx, [rcx]; ExceptionCode
0x18000e6d9  call    cs:__imp_RpcExceptionFilter
0x18000e6df  mov     ecx, eax; ExceptionCode
0x18000e6e1  call    cs:__imp_RpcExceptionFilter
0x18000e6e7  nop
0x18000e6e8  add     rsp, 30h
0x18000e6ec  pop     rbp
0x18000e6ed  retn
```
