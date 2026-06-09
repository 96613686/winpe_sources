# CRPCTimeoutAndWaitOnAppLaunchGrace::_InitialTimerExpired(void)

- ea: `0x180089b60`
- end: `0x180089c6a`
- name: `?_InitialTimerExpired@CRPCTimeoutAndWaitOnAppLaunchGrace@@AEAAXXZ`
- size: `266`
- prototype: `void __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180089cd0`

## callees

- `0x18000cbc0`
- `0x18003c3a4`
- `0x180050c50`
- `0x1800899d8`
- `0x180089a9c`
- `0x180089b60`
- `0x180089c70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180089bef`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180089bef`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180089bbd`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180089bbd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180089c21`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180089c21`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180089c09`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180089c09`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRPCTimeoutAndWaitOnAppLaunchGrace::_InitialTimerExpired(HANDLE *Parameter)
{
  char v2; // di
  struct _TP_WAIT *ThreadpoolWait; // rax
  LPCWSTR lpName[4]; // [rsp+20h] [rbp-20h] BYREF
  char v5; // [rsp+60h] [rbp+20h] BYREF
  HANDLE v6; // [rsp+68h] [rbp+28h] BYREF

  v2 = 0;
  v5 = 0;
  memset(lpName, 0, 24);
  if ( Parameter[7] )
  {
    if ( (int)Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::InitializeFormat(
                lpName,
                L"AppLaunchGrace-%s") >= 0 )
    {
      v6 = OpenEventW(0x100000u, 0, lpName[0]);
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        Parameter + 10,
        &v6);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v6);
      if ( (char *)Parameter[10] - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && WaitForSingleObject(Parameter[10], 0) == 258 )
      {
        ThreadpoolWait = CreateThreadpoolWait(
                           lambda_a0e0c1b8c193a5c2fbe0107373b1ae68_::_lambda_invoker_cdecl_,
                           Parameter,
                           0);
        Parameter[5] = ThreadpoolWait;
        if ( ThreadpoolWait )
        {
          SetThreadpoolWait(ThreadpoolWait, Parameter[10], 0);
          v2 = 1;
          v5 = 1;
        }
      }
    }
  }
  v6 = Parameter[7];
  AAMTraceProvider::RPCTimerExpired<unsigned __int64 &,unsigned short const *,bool &>(Parameter, &v6, &v5);
  if ( !v2 )
    CRPCTimeoutAndWaitOnAppLaunchGrace::_RepeatedlyCancelRPCsUntilDisarmed(Parameter);
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(lpName);
}

```

## disassembly

```asm
0x180089b60  mov     [rsp-18h+arg_10], rbx
0x180089b65  push    rbp
0x180089b66  push    rsi
0x180089b67  push    rdi
0x180089b68  mov     rbp, rsp
0x180089b6b  sub     rsp, 40h
0x180089b6f  mov     rbx, rcx
0x180089b72  xor     dil, dil
0x180089b75  mov     [rbp+arg_0], dil
0x180089b79  mov     [rbp+lpName], 0
0x180089b81  mov     [rbp+var_18], 0
0x180089b89  mov     [rbp+var_10], 0
0x180089b91  mov     r8, [rcx+38h]
0x180089b95  test    r8, r8
0x180089b98  jz      loc_180089C2E
0x180089b9e  lea     rdx, aApplaunchgrace; "AppLaunchGrace-%s"
0x180089ba5  lea     rcx, [rbp+lpName]
0x180089ba9  call    ?InitializeFormat@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180089bae  test    eax, eax
0x180089bb0  js      short loc_180089C2E
0x180089bb2  mov     r8, [rbp+lpName]; lpName
0x180089bb6  xor     edx, edx; bInheritHandle
0x180089bb8  mov     ecx, 100000h; dwDesiredAccess
0x180089bbd  call    cs:__imp_OpenEventW
0x180089bc3  mov     [rbp+arg_8], rax
0x180089bc7  lea     rsi, [rbx+50h]
0x180089bcb  lea     rdx, [rbp+arg_8]
0x180089bcf  mov     rcx, rsi
0x180089bd2  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180089bd7  lea     rcx, [rbp+arg_8]
0x180089bdb  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180089be0  mov     rcx, [rsi]; hHandle
0x180089be3  lea     rax, [rcx-1]
0x180089be7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180089beb  ja      short loc_180089C2E
0x180089bed  xor     edx, edx; dwMilliseconds
0x180089bef  call    cs:__imp_WaitForSingleObject
0x180089bf5  cmp     eax, 102h
0x180089bfa  jnz     short loc_180089C2E
0x180089bfc  xor     r8d, r8d; pcbe
0x180089bff  mov     rdx, rbx; pv
0x180089c02  lea     rcx, _lambda_a0e0c1b8c193a5c2fbe0107373b1ae68____lambda_invoker_cdecl_; pfnwa
0x180089c09  call    cs:__imp_CreateThreadpoolWait
0x180089c0f  mov     [rbx+28h], rax
0x180089c13  test    rax, rax
0x180089c16  jz      short loc_180089C2E
0x180089c18  xor     r8d, r8d; pftTimeout
0x180089c1b  mov     rdx, [rsi]; h
0x180089c1e  mov     rcx, rax; pwa
0x180089c21  call    cs:__imp_SetThreadpoolWait
0x180089c27  mov     dil, 1
0x180089c2a  mov     [rbp+arg_0], dil
0x180089c2e  mov     rax, [rbx+38h]
0x180089c32  mov     [rbp+arg_8], rax
0x180089c36  lea     r8, [rbp+arg_0]
0x180089c3a  lea     rdx, [rbp+arg_8]
0x180089c3e  mov     rcx, rbx
0x180089c41  call    ??$RPCTimerExpired@AEA_KPEBGAEA_N@AAMTraceProvider@@SAXAEA_K$$QEAPEBGAEA_N@Z; AAMTraceProvider::RPCTimerExpired<unsigned __int64 &,ushort const *,bool &>(unsigned __int64 &,ushort const * &&,bool &)
0x180089c46  test    dil, dil
0x180089c49  jnz     short loc_180089C54
0x180089c4b  mov     rcx, rbx; Parameter
0x180089c4e  call    ?_RepeatedlyCancelRPCsUntilDisarmed@CRPCTimeoutAndWaitOnAppLaunchGrace@@AEAAXXZ; CRPCTimeoutAndWaitOnAppLaunchGrace::_RepeatedlyCancelRPCsUntilDisarmed(void)
0x180089c53  nop
0x180089c54  lea     rcx, [rbp+lpName]
0x180089c58  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180089c5d  mov     rbx, [rsp+40h+arg_10]
0x180089c62  add     rsp, 40h
0x180089c66  pop     rdi
0x180089c67  pop     rsi
0x180089c68  pop     rbp
0x180089c69  retn
```
