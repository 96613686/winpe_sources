# DeoRpcServerOpenContextHandle

- ea: `0x18006a750`
- end: `0x18006a8f3`
- name: `DeoRpcServerOpenContextHandle`
- size: `419`
- prototype: `__int64 __fastcall(__int64, DWORD *, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000deac`
- `0x18000decc`
- `0x18000f778`
- `0x18001912c`
- `0x18002e4bc`
- `0x180068a20`
- `0x180069898`
- `0x1800698e0`
- `0x18006a750`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18006a7a6`
- `RPCRT4!RpcImpersonateClient` at `0x18006a7a6`
- `RPCRT4!RpcRevertToSelf` at `0x18006a7dc`
- `RPCRT4!RpcRevertToSelf` at `0x18006a7dc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006a7ce`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006a7ce`

## string_xrefs

- `0x18006a77a`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserver.cpp`
- `0x18006a7fa`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserver.cpp`
- `0x18006a81d`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserver.cpp`
- `0x18006a854`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DeoRpcServerOpenContextHandle(__int64 a1, DWORD *a2, __int64 a3, __int64 a4)
{
  int HasSystemManagementCapability; // ebx
  __int64 v8; // rdx
  __int64 result; // rax
  RPC_STATUS v10; // eax
  HANDLE v11; // rbx
  int v12; // eax
  const char *v13; // r9
  const char *v14; // r9
  int v15[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v16; // [rsp+28h] [rbp-40h] BYREF
  std::_Ref_count_base *v17; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HANDLE v19; // [rsp+88h] [rbp+20h] BYREF

  if ( !a4 )
  {
    HasSystemManagementCapability = -2147024809;
    v8 = 277;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\lib\\"
                    "deorpcserver.cpp",
      (const char *)(unsigned int)HasSystemManagementCapability,
      v15[0]);
    return (unsigned int)HasSystemManagementCapability;
  }
  if ( !a3 )
  {
    HasSystemManagementCapability = Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerImpl::VerifyRpcCallerHasSystemManagementCapability();
    if ( HasSystemManagementCapability < 0 )
    {
      v8 = 284;
      goto LABEL_3;
    }
  }
  v10 = RpcImpersonateClient(0);
  HasSystemManagementCapability = v10;
  if ( v10 > 0 )
    HasSystemManagementCapability = (unsigned __int16)v10 | 0x80010000;
  if ( HasSystemManagementCapability < 0 )
  {
    v8 = 291;
    goto LABEL_3;
  }
  v11 = OpenProcess(0x40u, 0, *a2);
  *(_QWORD *)v15 = v11;
  v12 = RpcRevertToSelf();
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80010000;
  if ( v12 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x12A,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\lib\\"
                    "deorpcserver.cpp",
      (const char *)(unsigned int)v12,
      v15[0]);
  if ( (((unsigned __int64)v11 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    HasSystemManagementCapability = wil::details::in1diag3::Return_GetLastError(
                                      retaddr,
                                      (void *)0x12C,
                                      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displaye"
                                                    "nhancementoverride\\server\\lib\\deorpcserver.cpp",
                                      v13);
LABEL_21:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v15);
    return (unsigned int)HasSystemManagementCapability;
  }
  Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerImpl,Microsoft::Bluetooth::Foundation::SingletonInitializeFactory<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerImpl>>::TryGetInstance(&v16);
  if ( !v16 )
  {
    HasSystemManagementCapability = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12F,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\lib\\"
                    "deorpcserver.cpp",
      (const char *)0x80004003LL,
      v15[0]);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    goto LABEL_21;
  }
  try
  {
    v19 = v11;
    Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerImpl::AddClient(v16, a3, a4, &v19, 0);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v15);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v19) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x137,
                     (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverrid"
                                   "e\\server\\lib\\deorpcserver.cpp",
                     v14);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v15);
    return (unsigned int)v19;
  }
  return result;
}

```

## disassembly

```asm
0x18006a750  push    rbx
0x18006a752  push    rsi
0x18006a753  push    rdi
0x18006a754  push    r14
0x18006a756  sub     rsp, 48h
0x18006a75a  mov     rsi, r9
0x18006a75d  mov     rdi, r8
0x18006a760  mov     r14, rdx
0x18006a763  test    r9, r9
0x18006a766  jnz     short loc_18006A78D
0x18006a768  mov     ebx, 80070057h
0x18006a76d  mov     edx, 115h; void *
0x18006a772  mov     rcx, [rsp+68h]; this
0x18006a777  mov     r9d, ebx; char *
0x18006a77a  lea     r8, aOnecoreuapDriv_16; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18006a781  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a786  mov     eax, ebx
0x18006a788  jmp     loc_18006A8E9
0x18006a78d  test    rdi, rdi
0x18006a790  jnz     short loc_18006A7A4
0x18006a792  call    ?VerifyRpcCallerHasSystemManagementCapability@DeoRpcServerImpl@DeoRpcServer@DisplayEnhancement@Windows@Microsoft@@SAJXZ; Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerImpl::VerifyRpcCallerHasSystemManagementCapability(void)
0x18006a797  mov     ebx, eax
0x18006a799  test    eax, eax
0x18006a79b  jns     short loc_18006A7A4
0x18006a79d  mov     edx, 11Ch
0x18006a7a2  jmp     short loc_18006A772
0x18006a7a4  xor     ecx, ecx; BindingHandle
0x18006a7a6  call    cs:__imp_RpcImpersonateClient
0x18006a7ac  mov     ebx, eax
0x18006a7ae  test    eax, eax
0x18006a7b0  jle     short loc_18006A7BB
0x18006a7b2  movzx   ebx, ax
0x18006a7b5  or      ebx, 80010000h
0x18006a7bb  test    ebx, ebx
0x18006a7bd  jns     short loc_18006A7C6
0x18006a7bf  mov     edx, 123h
0x18006a7c4  jmp     short loc_18006A772
0x18006a7c6  mov     r8d, [r14]; dwProcessId
0x18006a7c9  xor     edx, edx; bInheritHandle
0x18006a7cb  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18006a7ce  call    cs:__imp_OpenProcess
0x18006a7d4  mov     rbx, rax
0x18006a7d7  mov     qword ptr [rsp+68h+var_48], rax; int
0x18006a7dc  call    cs:__imp_RpcRevertToSelf
0x18006a7e2  test    eax, eax
0x18006a7e4  jle     short loc_18006A7EE
0x18006a7e6  movzx   eax, ax
0x18006a7e9  or      eax, 80010000h
0x18006a7ee  mov     rcx, [rsp+68h]; this
0x18006a7f3  test    eax, eax
0x18006a7f5  jns     short loc_18006A80C
0x18006a7f7  mov     r9d, eax; char *
0x18006a7fa  lea     r8, aOnecoreuapDriv_16; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18006a801  mov     edx, 12Ah; void *
0x18006a806  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18006a80c  lea     rax, [rbx+1]
0x18006a810  test    rax, 0FFFFFFFFFFFFFFFEh
0x18006a816  jnz     short loc_18006A832
0x18006a818  mov     rcx, [rsp+68h]; this
0x18006a81d  lea     r8, aOnecoreuapDriv_16; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18006a824  mov     edx, 12Ch; void *
0x18006a829  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006a82e  mov     ebx, eax
0x18006a830  jmp     short loc_18006A876
0x18006a832  lea     rcx, [rsp+68h+var_40]
0x18006a837  call    ?TryGetInstance@?$SingletonWithFactory@VDeoRpcServerImpl@DeoRpcServer@DisplayEnhancement@Windows@Microsoft@@U?$SingletonInitializeFactory@VDeoRpcServerImpl@DeoRpcServer@DisplayEnhancement@Windows@Microsoft@@@Foundation@Bluetooth@5@@Foundation@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VDeoRpcServerImpl@DeoRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerImpl,Microsoft::Bluetooth::Foundation::SingletonInitializeFactory<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerImpl>>::TryGetInstance(void)
0x18006a83c  nop
0x18006a83d  mov     rcx, [rsp+68h+var_40]
0x18006a842  test    rcx, rcx
0x18006a845  jnz     short loc_18006A885
0x18006a847  mov     rcx, [rsp+68h]; this
0x18006a84c  mov     ebx, 80004003h
0x18006a851  mov     r9d, ebx; char *
0x18006a854  lea     r8, aOnecoreuapDriv_16; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18006a85b  mov     edx, 12Fh; void *
0x18006a860  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a865  nop
0x18006a866  mov     rcx, [rsp+68h+var_38]; this
0x18006a86b  test    rcx, rcx
0x18006a86e  jz      short loc_18006A876
0x18006a870  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006a875  nop
0x18006a876  lea     rcx, [rsp+68h+var_48]
0x18006a87b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006a880  jmp     loc_18006A786
0x18006a885  mov     [rsp+68h+arg_18], rbx
0x18006a88d  mov     qword ptr [rsp+68h+var_48], 0
0x18006a896  lea     r9, [rsp+68h+arg_18]
0x18006a89e  mov     r8, rsi
0x18006a8a1  mov     rdx, rdi
0x18006a8a4  call    ?AddClient@DeoRpcServerImpl@DeoRpcServer@DisplayEnhancement@Windows@Microsoft@@UEAAXQEAUHWND__@@QEAPEAXV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerImpl::AddClient(HWND__ * const,void * * const,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>)
0x18006a8a9  nop
0x18006a8aa  mov     rcx, [rsp+68h+var_38]; this
0x18006a8af  test    rcx, rcx
0x18006a8b2  jz      short loc_18006A8BA
0x18006a8b4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006a8b9  nop
0x18006a8ba  lea     rcx, [rsp+68h+var_48]
0x18006a8bf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006a8c4  xor     eax, eax
0x18006a8c6  jmp     short loc_18006A8E9
0x18006a8c8  mov     rcx, [rsp+68h+var_38]; this
0x18006a8cd  test    rcx, rcx
0x18006a8d0  jz      short loc_18006A8D8
0x18006a8d2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006a8d7  nop
0x18006a8d8  lea     rcx, [rsp+68h+var_48]
0x18006a8dd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006a8e2  mov     eax, dword ptr [rsp+68h+arg_18]
0x18006a8e9  add     rsp, 48h
0x18006a8ed  pop     r14
0x18006a8ef  pop     rdi
0x18006a8f0  pop     rsi
0x18006a8f1  pop     rbx
0x18006a8f2  retn
```
