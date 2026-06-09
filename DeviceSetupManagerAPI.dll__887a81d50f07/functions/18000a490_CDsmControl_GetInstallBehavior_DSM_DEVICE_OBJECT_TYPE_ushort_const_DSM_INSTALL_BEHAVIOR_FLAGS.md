# CDsmControl::GetInstallBehavior(DSM_DEVICE_OBJECT_TYPE,ushort const *,DSM_INSTALL_BEHAVIOR_FLAGS *)

- ea: `0x18000a490`
- end: `0x18000a57d`
- name: `?GetInstallBehavior@CDsmControl@@UEAAJW4DSM_DEVICE_OBJECT_TYPE@@PEBGPEAW4DSM_INSTALL_BEHAVIOR_FLAGS@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(__int64, __int64, const OLECHAR *, _DWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800017c0`
- `0x180009d20`
- `0x18000a490`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000a502`
- `RPCRT4!NdrClientCall3` at `0x18000a502`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000a4c8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000a4c8`

## pseudocode

```c
__int64 __fastcall CDsmControl::GetInstallBehavior(__int64 a1, __int64 a2, const OLECHAR *a3, _DWORD *a4)
{
  HRESULT Pointer; // ebx
  GUID pclsid; // [rsp+40h] [rbp-28h] BYREF

  *a4 = 0;
  pclsid = 0;
  Pointer = CLSIDFromString(a3, &pclsid);
  if ( Pointer >= 0 )
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&stru_1800116C0,
                              3u,
                              0,
                              DsmRpcControl_v1_0_c_ifspec,
                              &pclsid,
                              a4,
                              Pointer,
                              0).Pointer;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      &WPP_6c51682e99e93bfa9299cbf564496992_Traceguids,
      (unsigned int)Pointer);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18000a490  mov     [rsp+arg_0], rbx
0x18000a495  mov     [rsp+arg_8], rsi
0x18000a49a  push    rdi
0x18000a49b  sub     rsp, 60h
0x18000a49f  mov     rax, cs:__security_cookie
0x18000a4a6  xor     rax, rsp
0x18000a4a9  mov     [rsp+68h+var_18], rax
0x18000a4ae  mov     rsi, r9
0x18000a4b1  mov     dword ptr [r9], 0
0x18000a4b8  xorps   xmm0, xmm0
0x18000a4bb  movups  xmmword ptr [rsp+68h+pclsid.Data1], xmm0
0x18000a4c0  lea     rdx, [rsp+68h+pclsid]; pclsid
0x18000a4c5  mov     rcx, r8; lpsz
0x18000a4c8  call    cs:__imp_CLSIDFromString
0x18000a4ce  mov     ebx, eax
0x18000a4d0  mov     [rsp+68h+var_38], eax
0x18000a4d4  test    eax, eax
0x18000a4d6  js      short loc_18000A52D
0x18000a4d8  xor     edi, edi
0x18000a4da  mov     [rsp+68h+var_30], rdi
0x18000a4df  mov     [rsp+68h+var_40], rsi
0x18000a4e4  lea     rax, [rsp+68h+pclsid]
0x18000a4e9  mov     [rsp+68h+var_48], rax
0x18000a4ee  mov     r9, cs:DsmRpcControl_v1_0_c_ifspec
0x18000a4f5  xor     r8d, r8d; pReturnValue
0x18000a4f8  lea     edx, [rdi+3]; nProcNum
0x18000a4fb  lea     rcx, stru_1800116C0; pProxyInfo
0x18000a502  call    cs:__imp_NdrClientCall3
0x18000a508  mov     rbx, rax
0x18000a50b  mov     [rsp+68h+var_30], rax
0x18000a510  mov     [rsp+68h+var_38], eax
0x18000a514  jmp     short loc_18000A51C
0x18000a516  mov     edi, eax
0x18000a518  mov     ebx, [rsp+68h+var_38]
0x18000a51c  test    edi, edi
0x18000a51e  jz      short loc_18000A52D
0x18000a520  jle     short loc_18000A52B
0x18000a522  movzx   edi, di
0x18000a525  or      edi, 80070000h
0x18000a52b  mov     ebx, edi
0x18000a52d  lea     rax, WPP_GLOBAL_Control
0x18000a534  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a53b  cmp     rcx, rax
0x18000a53e  jz      short loc_18000A55E
0x18000a540  test    byte ptr [rcx+1Ch], 1
0x18000a544  jz      short loc_18000A55E
0x18000a546  mov     edx, 0Ch
0x18000a54b  mov     r9d, ebx
0x18000a54e  lea     r8, WPP_6c51682e99e93bfa9299cbf564496992_Traceguids
0x18000a555  mov     rcx, [rcx+10h]
0x18000a559  call    WPP_SF_D
0x18000a55e  mov     eax, ebx
0x18000a560  mov     rcx, [rsp+68h+var_18]
0x18000a565  xor     rcx, rsp; StackCookie
0x18000a568  call    __security_check_cookie
0x18000a56d  mov     rbx, [rsp+68h+arg_0]
0x18000a572  mov     rsi, [rsp+68h+arg_8]
0x18000a577  add     rsp, 60h
0x18000a57b  pop     rdi
0x18000a57c  retn
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
