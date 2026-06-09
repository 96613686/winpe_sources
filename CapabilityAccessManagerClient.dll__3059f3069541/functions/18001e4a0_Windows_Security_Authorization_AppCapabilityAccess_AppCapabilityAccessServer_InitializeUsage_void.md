# Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::InitializeUsage(void)

- ea: `0x18001e4a0`
- end: `0x18001e62d`
- name: `?InitializeUsage@AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@AEAAXXZ`
- size: `397`
- prototype: `void __fastcall(Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001ff20`
- `0x180020140`

## callees

- `0x180003c80`
- `0x18000aa04`
- `0x18000c6c8`
- `0x18000f9e4`
- `0x18001b218`
- `0x18001b444`
- `0x18001b5ac`
- `0x18001c3c4`
- `0x18001c724`
- `0x18001e4a0`
- `0x180022d2c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18001e4d4`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18001e4d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e56a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e597`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e56a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e597`

## string_xrefs

- `0x18001e603`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001e61b`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::InitializeUsage(
        RTL_SRWLOCK *this)
{
  __int64 *v2; // rax
  int v3; // eax
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, PVOID, RTL_SRWLOCK *); // rbx
  PVOID Ptr; // r14
  void (__fastcall *v7)(PVOID, _QWORD, __int64, RTL_SRWLOCK *); // rsi
  DWORD CurrentProcessId; // eax
  __int64 UserSidStringFromProcessId; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  const unsigned __int16 *v13; // rax
  __int64 v14; // rbx
  DWORD v15; // eax
  int v16; // [rsp+20h] [rbp-88h]
  __int64 v17; // [rsp+30h] [rbp-78h] BYREF
  unsigned __int64 v18; // [rsp+38h] [rbp-70h] BYREF
  HSTRING string[4]; // [rsp+40h] [rbp-68h] BYREF
  _QWORD v20[4]; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v18 = (unsigned __int64)&this[17] & -(__int64)(TryAcquireSRWLockExclusive(this + 17) != 0);
  if ( v18 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
      (const char *)0x8000FFFFLL,
      v16);
  v17 = 0;
  v2 = (__int64 *)Windows::Internal::StringReference::StringReference(string, 0);
  v3 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics>>(
         *v2,
         (__int64)&v17);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x170,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
      (const char *)(unsigned int)v3,
      v16);
  v4 = v17;
  v5 = *(void (__fastcall **)(__int64, PVOID, RTL_SRWLOCK *))(*(_QWORD *)v17 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&this[14]);
  v5(v4, this[16].Ptr, this + 14);
  Ptr = this[14].Ptr;
  if ( Ptr )
  {
    v7 = *(void (__fastcall **)(PVOID, _QWORD, __int64, RTL_SRWLOCK *))(*(_QWORD *)Ptr + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&this[15]);
    CurrentProcessId = GetCurrentProcessId();
    UserSidStringFromProcessId = Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromProcessId(
                                   string,
                                   CurrentProcessId);
    v13 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                                      UserSidStringFromProcessId,
                                      v10,
                                      v11,
                                      v12);
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v20, v13);
    v14 = v20[0];
    v15 = GetCurrentProcessId();
    v7(Ptr, v15, v14, this + 15);
    std::wstring::_Tidy_deallocate(string);
  }
  LOBYTE(this[29].Ptr) = 1;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v18);
}

```

## disassembly

```asm
0x18001e4a0  mov     [rsp+arg_8], rbx
0x18001e4a5  mov     [rsp+arg_10], rbp
0x18001e4aa  push    rsi
0x18001e4ab  push    rdi
0x18001e4ac  push    r14
0x18001e4ae  sub     rsp, 90h
0x18001e4b5  mov     rax, cs:__security_cookie
0x18001e4bc  xor     rax, rsp
0x18001e4bf  mov     [rsp+0A8h+var_28], rax
0x18001e4c7  mov     rbp, rcx
0x18001e4ca  lea     rbx, [rcx+88h]
0x18001e4d1  mov     rcx, rbx; SRWLock
0x18001e4d4  call    cs:__imp_TryAcquireSRWLockExclusive
0x18001e4da  neg     al
0x18001e4dc  sbb     rdx, rdx
0x18001e4df  and     rdx, rbx; unsigned __int16 (*)[61]
0x18001e4e2  mov     [rsp+0A8h+var_70], rdx
0x18001e4e7  mov     rcx, [rsp+0A8h]; this
0x18001e4ef  jnz     loc_18001E615
0x18001e4f5  mov     [rsp+0A8h+var_78], 0
0x18001e4fe  lea     rcx, [rsp+0A8h+string]; string
0x18001e503  call    ??$?0$0DN@@StringReference@Internal@Windows@@QEAA@AEAY0DN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[61])
0x18001e508  lea     rdx, [rsp+0A8h+var_78]
0x18001e50d  mov     rcx, [rax]
0x18001e510  call    ??$GetActivationFactory@V?$ComPtr@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics>>)
0x18001e515  mov     rcx, [rsp+0A8h]; this
0x18001e51d  test    eax, eax
0x18001e51f  js      loc_18001E600
0x18001e525  mov     rdi, [rsp+0A8h+var_78]
0x18001e52a  mov     rax, [rdi]
0x18001e52d  mov     rbx, [rax+30h]
0x18001e531  lea     rsi, [rbp+70h]
0x18001e535  mov     rcx, rsi
0x18001e538  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001e53d  mov     r8, rsi
0x18001e540  mov     rdx, [rbp+80h]
0x18001e547  mov     rcx, rdi
0x18001e54a  mov     rax, rbx
0x18001e54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e552  mov     r14, [rsi]
0x18001e555  test    r14, r14
0x18001e558  jz      short loc_18001E5BC
0x18001e55a  mov     rax, [r14]
0x18001e55d  mov     rsi, [rax+30h]
0x18001e561  lea     rcx, [rbp+78h]
0x18001e565  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001e56a  call    cs:__imp_GetCurrentProcessId
0x18001e570  mov     edx, eax
0x18001e572  lea     rcx, [rsp+0A8h+string]
0x18001e577  call    ?GetUserSidStringFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromProcessId(ulong)
0x18001e57c  nop
0x18001e57d  mov     rcx, rax
0x18001e580  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e585  mov     rdx, rax; unsigned __int16 *
0x18001e588  lea     rcx, [rsp+0A8h+var_48]; this
0x18001e58d  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001e592  mov     rbx, [rsp+0A8h+var_48]
0x18001e597  call    cs:__imp_GetCurrentProcessId
0x18001e59d  lea     r9, [rbp+78h]
0x18001e5a1  mov     r8, rbx
0x18001e5a4  mov     edx, eax
0x18001e5a6  mov     rcx, r14
0x18001e5a9  mov     rax, rsi
0x18001e5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5b1  nop
0x18001e5b2  lea     rcx, [rsp+0A8h+string]
0x18001e5b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e5bc  mov     byte ptr [rbp+0E8h], 1
0x18001e5c3  lea     rcx, [rsp+0A8h+var_78]
0x18001e5c8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001e5cd  nop
0x18001e5ce  lea     rcx, [rsp+0A8h+var_70]
0x18001e5d3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001e5d8  mov     rcx, [rsp+0A8h+var_28]
0x18001e5e0  xor     rcx, rsp; StackCookie
0x18001e5e3  call    __security_check_cookie
0x18001e5e8  lea     r11, [rsp+0A8h+var_18]
0x18001e5f0  mov     rbx, [r11+28h]
0x18001e5f4  mov     rbp, [r11+30h]
0x18001e5f8  mov     rsp, r11
0x18001e5fb  pop     r14
0x18001e5fd  pop     rdi
0x18001e5fe  pop     rsi
0x18001e5ff  retn
0x18001e600  mov     r9d, eax; char *
0x18001e603  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001e60a  mov     edx, 170h; void *
0x18001e60f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e615  mov     r9d, 8000FFFFh; char *
0x18001e61b  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001e622  mov     edx, 16Dh; void *
0x18001e627  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
