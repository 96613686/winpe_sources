# KdcUpdateCryptoPolicy

- ea: `0x180037de4`
- end: `0x180037fe4`
- name: `KdcUpdateCryptoPolicy`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800394b4`

## callees

- `0x180002e80`
- `0x180003080`
- `0x1800030e8`
- `0x1800101ec`
- `0x1800351d0`
- `0x18003669c`
- `0x180037de4`
- `0x18003f91c`
- `0x18003ff0c`
- `0x18006ac20`
- `0x18006ad68`
- `0x180083fc4`
- `0x180084084`
- `0x18009c010`

## import_xrefs

- `Kerb3961!__imp_GetDomainCipherPolicy` at `0x180037f1c`
- `Kerb3961!__imp_GetDomainCipherPolicy` at `0x180037f1c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037e24`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037e24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037f9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037f9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037e95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037ec8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037e95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037ec8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037e5a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037e5a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char KdcUpdateCryptoPolicy()
{
  HKEY *phkResult; // rax
  LSTATUS v1; // eax
  HKEY v2; // rcx
  HKEY v3; // rdx
  char v4; // bl
  struct IKdcBackend *v5; // rax
  int v6; // ebx
  __int64 DomainCipherPolicy; // rax
  __int64 v8; // rdx
  KdcAuditEngine *v9; // rax
  int v10; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  RTL_SRWLOCK *v13; // [rsp+48h] [rbp+10h]

  if ( dword_1800B65C0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800B65C0);
    if ( dword_1800B65C0 == -1 )
    {
      atexit(KdcUpdateCryptoPolicy_::_2_::_dynamic_atexit_destructor_for__synchronize__);
      Init_thread_footer(&dword_1800B65C0);
    }
  }
  v13 = &stru_1800B4200;
  AcquireSRWLockExclusive(&stru_1800B4200);
  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System\\Kerberos\\Parameters",
         0,
         0x20019u,
         phkResult);
  v2 = hKey;
  if ( v1 != 2 )
  {
    if ( !hKey )
      goto LABEL_9;
    goto LABEL_6;
  }
  if ( hKey )
  {
LABEL_6:
    if ( RegQueryValueExW(hKey, L"SupportedEncryptionTypes", 0, 0, 0, 0) != 2 )
    {
      v3 = hKey;
      goto LABEL_10;
    }
  }
  RegQueryValueExW(0, L"SupportedEncryptionTypes", 0, 0, 0, 0);
LABEL_9:
  v3 = 0;
LABEL_10:
  if ( byte_1800B42F8 )
  {
    v4 = KerberosCryptoPolicy::ReloadCipherPolicy(v2, v3);
  }
  else
  {
    byte_1800B42F8 = KerberosCryptoPolicy::InitializeCiphers(v2, v3);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AesSha2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AesSha2>::GetImpl'::`2'::impl) )
    {
      v5 = GlobalKdcService::Get();
      v6 = (*(__int64 (__fastcall **)(struct IKdcBackend *))(*(_QWORD *)v5 + 136LL))(v5);
      DomainCipherPolicy = GetDomainCipherPolicy();
      LOBYTE(v8) = v6 < 10 ? 0 : 0xA;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)DomainCipherPolicy + 24LL))(DomainCipherPolicy, v8);
    }
    if ( byte_1800B42F8 )
    {
      v9 = KdcAuditEngine::Get();
      v10 = KdcAuditEngine::Initialize(v9);
      if ( v10 < 0
        && WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          66,
          WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids,
          (unsigned int)v10);
      }
    }
    v4 = byte_1800B42F8;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  ReleaseSRWLockExclusive(&stru_1800B4200);
  return v4;
}

```

## disassembly

```asm
0x180037de4  mov     [rsp+arg_10], rbx
0x180037de9  push    rsi
0x180037dea  sub     rsp, 30h
0x180037dee  mov     ecx, cs:_tls_index
0x180037df4  mov     rax, gs:58h
0x180037dfd  mov     edx, 4
0x180037e02  mov     rax, [rax+rcx*8]
0x180037e06  mov     eax, [rdx+rax]
0x180037e09  cmp     cs:dword_1800B65C0, eax
0x180037e0f  jg      loc_180037FAE
0x180037e15  lea     rsi, stru_1800B4200
0x180037e1c  mov     [rsp+38h+arg_8], rsi
0x180037e21  mov     rcx, rsi; SRWLock
0x180037e24  call    cs:__imp_AcquireSRWLockExclusive
0x180037e2a  nop
0x180037e2b  mov     [rsp+38h+hKey], 0
0x180037e34  lea     rcx, [rsp+38h+hKey]
0x180037e39  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180037e3e  mov     [rsp+38h+phkResult], rax; phkResult
0x180037e43  mov     r9d, 20019h; samDesired
0x180037e49  xor     r8d, r8d; ulOptions
0x180037e4c  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180037e53  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037e5a  call    cs:__imp_RegOpenKeyExW
0x180037e60  mov     rcx, [rsp+38h+hKey]; hKey
0x180037e65  cmp     eax, 2
0x180037e68  jz      short loc_180037E71
0x180037e6a  test    rcx, rcx
0x180037e6d  jnz     short loc_180037E76
0x180037e6f  jmp     short loc_180037ECE
0x180037e71  test    rcx, rcx
0x180037e74  jz      short loc_180037EA7
0x180037e76  mov     [rsp+38h+lpcbData], 0; lpcbData
0x180037e7f  mov     [rsp+38h+phkResult], 0; lpData
0x180037e88  xor     r9d, r9d; lpType
0x180037e8b  xor     r8d, r8d; lpReserved
0x180037e8e  lea     rdx, aSupportedencry; "SupportedEncryptionTypes"
0x180037e95  call    cs:__imp_RegQueryValueExW
0x180037e9b  cmp     eax, 2
0x180037e9e  jz      short loc_180037EA7
0x180037ea0  mov     rdx, [rsp+38h+hKey]
0x180037ea5  jmp     short loc_180037ED0
0x180037ea7  mov     [rsp+38h+lpcbData], 0; lpcbData
0x180037eb0  mov     [rsp+38h+phkResult], 0; lpData
0x180037eb9  xor     r9d, r9d; lpType
0x180037ebc  xor     r8d, r8d; lpReserved
0x180037ebf  lea     rdx, aSupportedencry; "SupportedEncryptionTypes"
0x180037ec6  xor     ecx, ecx; hKey
0x180037ec8  call    cs:__imp_RegQueryValueExW
0x180037ece  xor     edx, edx
0x180037ed0  cmp     cs:byte_1800B42F8, 0
0x180037ed7  jz      short loc_180037EE5
0x180037ed9  call    ?ReloadCipherPolicy@KerberosCryptoPolicy@@SA_NW4Kerb3961PolicyType@@PEAUHKEY__@@@Z; KerberosCryptoPolicy::ReloadCipherPolicy(Kerb3961PolicyType,HKEY__ *)
0x180037ede  mov     bl, al
0x180037ee0  jmp     loc_180037F8D
0x180037ee5  call    ?InitializeCiphers@KerberosCryptoPolicy@@SA_NW4Kerb3961PolicyType@@PEAUHKEY__@@@Z; KerberosCryptoPolicy::InitializeCiphers(Kerb3961PolicyType,HKEY__ *)
0x180037eea  mov     cs:byte_1800B42F8, al
0x180037ef0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AesSha2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AesSha2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AesSha2> `wil::Feature<__WilFeatureTraits_Feature_AesSha2>::GetImpl(void)'::`2'::impl
0x180037ef7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AesSha2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AesSha2>::__private_IsEnabled(void)
0x180037efc  test    al, al
0x180037efe  jz      short loc_180037F3C
0x180037f00  call    ?Get@GlobalKdcService@@SAAEAUIKdcBackend@@XZ; GlobalKdcService::Get(void)
0x180037f05  mov     rdx, rax
0x180037f08  mov     rcx, [rax]
0x180037f0b  mov     rax, [rcx+88h]
0x180037f12  mov     rcx, rdx
0x180037f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f1a  mov     ebx, eax
0x180037f1c  call    cs:__imp_GetDomainCipherPolicy
0x180037f22  mov     rcx, rax
0x180037f25  mov     rax, [rax]
0x180037f28  cmp     ebx, 0Ah
0x180037f2b  setl    dl
0x180037f2e  dec     dl
0x180037f30  and     dl, 0Ah
0x180037f33  mov     rax, [rax+18h]
0x180037f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f3c  cmp     cs:byte_1800B42F8, 0
0x180037f43  jz      short loc_180037F87
0x180037f45  call    ?Get@KdcAuditEngine@@SAAEAV1@XZ; KdcAuditEngine::Get(void)
0x180037f4a  mov     rcx, rax; this
0x180037f4d  call    ?Initialize@KdcAuditEngine@@QEAAJXZ; KdcAuditEngine::Initialize(void)
0x180037f52  test    eax, eax
0x180037f54  jns     short loc_180037F87
0x180037f56  lea     rdx, WPP_GLOBAL_Control
0x180037f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f64  cmp     rcx, rdx
0x180037f67  jz      short loc_180037F87
0x180037f69  test    byte ptr [rcx+1Ch], 1
0x180037f6d  jz      short loc_180037F87
0x180037f6f  mov     edx, 42h ; 'B'
0x180037f74  mov     r9d, eax
0x180037f77  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x180037f7e  mov     rcx, [rcx+10h]
0x180037f82  call    WPP_SF_d
0x180037f87  mov     bl, cs:byte_1800B42F8
0x180037f8d  lea     rcx, [rsp+38h+hKey]
0x180037f92  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180037f97  nop
0x180037f98  mov     rcx, rsi; SRWLock
0x180037f9b  call    cs:__imp_ReleaseSRWLockExclusive
0x180037fa1  mov     al, bl
0x180037fa3  mov     rbx, [rsp+38h+arg_10]
0x180037fa8  add     rsp, 30h
0x180037fac  pop     rsi
0x180037fad  retn
0x180037fae  lea     rcx, dword_1800B65C0
0x180037fb5  call    _Init_thread_header
0x180037fba  cmp     cs:dword_1800B65C0, 0FFFFFFFFh
0x180037fc1  jnz     loc_180037E15
0x180037fc7  lea     rcx, _KdcUpdateCryptoPolicy____2____dynamic_atexit_destructor_for__synchronize__; void (__cdecl *)()
0x180037fce  call    atexit
0x180037fd3  lea     rcx, dword_1800B65C0
0x180037fda  call    _Init_thread_footer
0x180037fdf  jmp     loc_180037E15
```
