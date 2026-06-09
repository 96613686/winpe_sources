# WindowsStorage::Utilities::Identity::Identity(void)

- ea: `0x180012b7c`
- end: `0x180012d58`
- name: `??0Identity@Utilities@WindowsStorage@@QEAA@XZ`
- size: `476`
- prototype: `WindowsStorage::Utilities::Identity *__fastcall(WindowsStorage::Utilities::Identity *this)`
- caller_count: `12`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180017670`
- `0x1800176f0`
- `0x180017850`
- `0x180017940`
- `0x180017b70`
- `0x180017c60`
- `0x180017f70`
- `0x1800180b0`
- `0x180018440`
- `0x1800188a0`
- `0x180018990`
- `0x180018bb0`

## callees

- `0x18000d4e0`
- `0x180010654`
- `0x180010670`
- `0x180012b7c`
- `0x180012d88`
- `0x180012e74`
- `0x18001410c`
- `0x1800142cc`
- `0x180014400`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012ce0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012ce0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012ccb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012ccb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012c96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012c96`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180012cff`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180012cff`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180012bd5`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180012bd5`

## pseudocode

```c
WindowsStorage::Utilities::Identity *__fastcall WindowsStorage::Utilities::Identity::Identity(
        WindowsStorage::Utilities::Identity *this)
{
  void **v2; // r14
  HRESULT v3; // eax
  unsigned int v4; // r8d
  unsigned int v5; // r8d
  __int64 v6; // rbx
  __int64 (__fastcall *v7)(__int64, __int64, WindowsStorage::Utilities::Identity *); // rdi
  unsigned int v8; // eax
  char v9; // cl
  HANDLE CurrentProcess; // rax
  __int64 v11; // rcx
  HANDLE CurrentThread; // rax
  const char *v13; // r9
  __int64 ImpersonationTokenFromProcess; // rax
  int v16; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v19; // [rsp+58h] [rbp+10h] BYREF
  void *ppInterface; // [rsp+60h] [rbp+18h] BYREF

  *(_QWORD *)this = 0;
  v2 = (void **)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_BYTE *)this + 24) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_BYTE *)this + 40) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_BYTE *)this + 56) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  ppInterface = 0;
  v3 = CoGetCallContext(&GUID_0000013e_0000_0000_c000_000000000046, &ppInterface);
  try
  {
    if ( v3 < 0 )
    {
      if ( v3 != -2147417833 )
        wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x4F, v4, (const char *)(unsigned int)v3, v16);
      CurrentProcess = GetCurrentProcess();
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        this,
        CurrentProcess);
    }
    else
    {
      v19 = 0;
      (**(void (__fastcall ***)(void *, GUID *, __int64 *))ppInterface)(
        ppInterface,
        &GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541,
        &v19);
      v6 = v19;
      if ( !v19 )
        wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x36, v5, (const char *)0x80004002LL, v16);
      v7 = *(__int64 (__fastcall **)(__int64, __int64, WindowsStorage::Utilities::Identity *))(*(_QWORD *)v19 + 24LL);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        this,
        0);
      v8 = v7(v6, 4096, this);
      if ( (int)(v8 + 0x80000000) < 0 || (v9 = 1, v8 == -2147024891) )
        v9 = 0;
      if ( v9 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x3B,
          (unsigned int)"onecore\\base\\windows.storage\\src\\identity.cpp",
          (const char *)v8,
          v16);
      wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(&v19);
    }
    if ( (*(int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface) < 0 )
    {
      ImpersonationTokenFromProcess = WindowsStorage::Utilities::Identity::_GetImpersonationTokenFromProcess(
                                        v11,
                                        &v19,
                                        *(_QWORD *)this);
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        v2,
        ImpersonationTokenFromProcess);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
    }
    else
    {
      LOBYTE(v19) = 1;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        v2,
        0);
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 0xEu, 1, v2) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x59,
          (unsigned int)"onecore\\base\\windows.storage\\src\\identity.cpp",
          v13);
      CoRevertToSelf();
    }
  }
  catch ( ... )
  {
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
    throw;
  }
  wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(&ppInterface);
  return this;
}

```

## disassembly

```asm
0x180012b7c  mov     [rsp+arg_0], rcx
0x180012b81  push    rbx
0x180012b82  push    rsi
0x180012b83  push    rdi
0x180012b84  push    r14
0x180012b86  push    r15; int
0x180012b88  sub     rsp, 20h
0x180012b8c  mov     rsi, rcx
0x180012b8f  xor     r15d, r15d
0x180012b92  mov     [rcx], r15
0x180012b95  lea     r14, [rcx+8]
0x180012b99  mov     [r14], r15
0x180012b9c  mov     [rcx+10h], r15
0x180012ba0  mov     [rcx+18h], r15b
0x180012ba4  mov     [rcx+20h], r15
0x180012ba8  mov     [rcx+28h], r15b
0x180012bac  mov     [rcx+30h], r15
0x180012bb0  mov     [rcx+38h], r15b
0x180012bb4  mov     [rcx+40h], r15
0x180012bb8  mov     [rcx+48h], r15
0x180012bbc  mov     [rcx+50h], r15
0x180012bc0  mov     [rcx+58h], r15
0x180012bc4  mov     [rsp+48h+ppInterface], r15
0x180012bc9  lea     rdx, [rsp+48h+ppInterface]; ppInterface
0x180012bce  lea     rcx, _GUID_0000013e_0000_0000_c000_000000000046; riid
0x180012bd5  call    cs:__imp_CoGetCallContext
0x180012bdb  test    eax, eax
0x180012bdd  js      loc_180012C8B
0x180012be3  mov     rcx, [rsp+48h+ppInterface]
0x180012be8  mov     [rsp+48h+arg_8], r15
0x180012bed  mov     rax, [rcx]
0x180012bf0  lea     r8, [rsp+48h+arg_8]
0x180012bf5  lea     rdx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541
0x180012bfc  mov     rax, [rax]
0x180012bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c04  nop
0x180012c05  mov     rbx, [rsp+48h+arg_8]
0x180012c0a  test    rbx, rbx
0x180012c0d  jnz     short loc_180012C22
0x180012c0f  mov     rcx, [rsp+48h]; this
0x180012c14  lea     edx, [rbx+36h]; void *
0x180012c17  mov     r9d, 80004002h; char *
0x180012c1d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012c22  mov     rax, [rbx]
0x180012c25  mov     rdi, [rax+18h]
0x180012c29  xor     edx, edx
0x180012c2b  mov     rcx, rsi
0x180012c2e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180012c33  mov     r8, rsi
0x180012c36  mov     edx, 1000h
0x180012c3b  mov     rcx, rbx
0x180012c3e  mov     rax, rdi
0x180012c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c46  mov     edx, 80000000h
0x180012c4b  lea     ecx, [rax+rdx]
0x180012c4e  test    edx, ecx
0x180012c50  jnz     short loc_180012C5B
0x180012c52  cmp     eax, 80070005h
0x180012c57  mov     cl, 1
0x180012c59  jnz     short loc_180012C5E
0x180012c5b  mov     cl, r15b
0x180012c5e  mov     r10, [rsp+48h]
0x180012c63  test    cl, cl
0x180012c65  jz      short loc_180012C7F
0x180012c67  mov     r9d, eax; char *
0x180012c6a  lea     r8, aOnecoreBaseWin_2; "onecore\\base\\windows.storage\\src\\id"...
0x180012c71  mov     edx, 3Bh ; ';'; void *
0x180012c76  mov     rcx, r10; this
0x180012c79  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180012c7f  lea     rcx, [rsp+48h+arg_8]
0x180012c84  call    ??1?$com_ptr_t@UIInspectable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(void)
0x180012c89  jmp     short loc_180012CA7
0x180012c8b  cmp     eax, 80010117h
0x180012c90  jnz     loc_180012D44
0x180012c96  call    cs:__imp_GetCurrentProcess
0x180012c9c  mov     rdx, rax
0x180012c9f  mov     rcx, rsi
0x180012ca2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180012ca7  mov     rcx, [rsp+48h+ppInterface]
0x180012cac  mov     rax, [rcx]
0x180012caf  mov     rax, [rax+20h]
0x180012cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cb8  test    eax, eax
0x180012cba  js      short loc_180012D07
0x180012cbc  mov     byte ptr [rsp+48h+arg_8], 1
0x180012cc1  xor     edx, edx
0x180012cc3  mov     rcx, r14
0x180012cc6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180012ccb  call    cs:__imp_GetCurrentThread
0x180012cd1  mov     r9, r14; TokenHandle
0x180012cd4  mov     edx, 0Eh; DesiredAccess
0x180012cd9  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x180012cdd  mov     rcx, rax; ThreadHandle
0x180012ce0  call    cs:__imp_OpenThreadToken
0x180012ce6  mov     rcx, [rsp+48h]; this
0x180012ceb  test    eax, eax
0x180012ced  jnz     short loc_180012CFF
0x180012cef  lea     r8, aOnecoreBaseWin_2; "onecore\\base\\windows.storage\\src\\id"...
0x180012cf6  lea     edx, [rax+59h]; void *
0x180012cf9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180012cff  call    cs:__imp_CoRevertToSelf
0x180012d05  jmp     short loc_180012D2A
0x180012d07  mov     r8, [rsi]
0x180012d0a  lea     rdx, [rsp+48h+arg_8]
0x180012d0f  call    ?_GetImpersonationTokenFromProcess@Identity@Utilities@WindowsStorage@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX@Z; WindowsStorage::Utilities::Identity::_GetImpersonationTokenFromProcess(void *)
0x180012d14  mov     rdx, rax
0x180012d17  mov     rcx, r14
0x180012d1a  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180012d1f  lea     rcx, [rsp+48h+arg_8]
0x180012d24  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180012d29  nop
0x180012d2a  lea     rcx, [rsp+48h+ppInterface]
0x180012d2f  call    ??1?$com_ptr_t@UIInspectable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(void)
0x180012d34  nop
0x180012d35  mov     rax, rsi
0x180012d38  add     rsp, 20h
0x180012d3c  pop     r15
0x180012d3e  pop     r14
0x180012d40  pop     rdi
0x180012d41  pop     rsi
0x180012d42  pop     rbx
0x180012d43  retn
0x180012d44  mov     rcx, [rsp+48h]; this
0x180012d49  mov     r9d, eax; char *
0x180012d4c  mov     edx, 4Fh ; 'O'; void *
0x180012d51  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
