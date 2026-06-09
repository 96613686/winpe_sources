# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(void)

- ea: `0x180022a0c`
- end: `0x180022b9d`
- name: `?GetUsoSession@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA?AU?$com_ptr@UIUsoSessionCommon@@@6@XZ`
- size: `401`
- prototype: `_QWORD *__fastcall(winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *this, _QWORD *)`
- caller_count: `12`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180020160`
- `0x180020a74`
- `0x180022404`
- `0x180023134`
- `0x1800231f4`
- `0x18002344c`
- `0x1800235c8`
- `0x18002366c`
- `0x180023b1c`
- `0x180024bac`
- `0x180024c54`
- `0x180024cd8`

## callees

- `0x180002dc0`
- `0x1800039d8`
- `0x180003bc0`
- `0x180008c0c`
- `0x180008e28`
- `0x18001f214`
- `0x18001f318`
- `0x180022a0c`
- `0x180022cd0`
- `0x1800233a4`
- `0x1800257a8`
- `0x1800271ac`
- `0x18002b010`

## string_xrefs

- `0x180022b4b`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *this,
        _QWORD *a2)
{
  unsigned int v4; // eax
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, __int64, GUID *, _QWORD *); // rsi
  int v7; // eax
  const struct winrt::impl::slim_source_location *v9; // rax
  int ppv; // [rsp+20h] [rbp-29h]
  LPVOID v11; // [rsp+38h] [rbp-11h] BYREF
  int pExceptionObject; // [rsp+40h] [rbp-9h] BYREF
  __int128 v13; // [rsp+48h] [rbp-1h]
  _BYTE v14[8]; // [rsp+58h] [rbp+Fh] BYREF
  _QWORD *v15; // [rsp+60h] [rbp+17h]
  IID rclsid; // [rsp+68h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v15 = a2;
  *a2 = 0;
  *((_DWORD *)this + 14) = 0;
  if ( !winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsIotCoreEdition(this) )
  {
    winrt::Windows::System::Update::factory_implementation::hresult_not_supported::hresult_not_supported((winrt::Windows::System::Update::factory_implementation::hresult_not_supported *)&pExceptionObject);
    throw (winrt::Windows::System::Update::factory_implementation::hresult_not_supported *)&pExceptionObject;
  }
  if ( !winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::HasSystemManagementCapability(this) )
  {
    v9 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(&rclsid);
    winrt::hresult_access_denied::hresult_access_denied((winrt::hresult_access_denied *)&pExceptionObject, v9);
    throw (winrt::hresult_access_denied *)&pExceptionObject;
  }
  rclsid.Data1 = -1189259215;
  *(_DWORD *)&rclsid.Data2 = 1174974909;
  *(_DWORD *)rclsid.Data4 = 785881217;
  *(_DWORD *)&rclsid.Data4[4] = -148877291;
  v11 = 0;
  pExceptionObject = 0;
  v13 = 0;
  v4 = CoCreateInstance_0(&rclsid, 0, 4u, &winrt::impl::guid_v<IUpdateSessionOrchestrator>, &v11);
  winrt::check_hresult(v14, v4, &pExceptionObject);
  v5 = v11;
  v6 = *(__int64 (__fastcall **)(LPVOID, __int64, GUID *, _QWORD *))(*(_QWORD *)v11 + 24LL);
  if ( *a2 )
    winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(a2);
  v7 = v6(v5, 1, &GUID_fccc288d_b47e_41fa_970c_935ec952f4a4, a2);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3E5,
      (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
      (const char *)(unsigned int)v7,
      ppv);
  if ( v5 )
    winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v11);
  return a2;
}

```

## disassembly

```asm
0x180022a0c  mov     [rsp-8+arg_10], rbx
0x180022a11  push    rbp
0x180022a12  push    rsi
0x180022a13  push    rdi
0x180022a14  lea     rbp, [rsp-47h]
0x180022a19  sub     rsp, 90h
0x180022a20  mov     rax, cs:__security_cookie
0x180022a27  xor     rax, rsp
0x180022a2a  mov     [rbp+57h+var_20], rax
0x180022a2e  mov     rbx, rdx
0x180022a31  mov     rdi, rcx
0x180022a34  mov     [rbp+57h+var_40], rdx
0x180022a38  mov     [rbp+57h+var_70], 0
0x180022a3f  mov     qword ptr [rdx], 0
0x180022a46  mov     [rbp+57h+var_70], 1
0x180022a4d  mov     dword ptr [rcx+38h], 0
0x180022a54  call    ?IsIotCoreEdition@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA_NXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsIotCoreEdition(void)
0x180022a59  test    al, al
0x180022a5b  jz      loc_180022B5D
0x180022a61  mov     rcx, rdi; this
0x180022a64  call    ?HasSystemManagementCapability@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA_NXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::HasSystemManagementCapability(void)
0x180022a69  test    al, al
0x180022a6b  jz      loc_180022B77
0x180022a71  mov     [rbp+57h+rclsid.Data1], 0B91D5831h
0x180022a78  mov     dword ptr [rbp+57h+rclsid.Data2], 4608B1BDh
0x180022a7f  mov     dword ptr [rbp+57h+rclsid.Data4], 2ED79881h
0x180022a86  mov     dword ptr [rbp+57h+rclsid.Data4+4], 0F7205015h
0x180022a8d  mov     [rbp+57h+var_68], 0
0x180022a95  mov     [rbp+57h+pExceptionObject], 0
0x180022a9c  xorps   xmm0, xmm0
0x180022a9f  movdqu  [rbp+57h+var_58], xmm0
0x180022aa4  lea     rax, [rbp+57h+var_68]
0x180022aa8  mov     qword ptr [rsp+0A0h+ppv], rax; int
0x180022aad  lea     r9, ??$guid_v@UIUpdateSessionOrchestrator@@@impl@winrt@@3Uguid@2@B; riid
0x180022ab4  xor     edx, edx; pUnkOuter
0x180022ab6  lea     r8d, [rdx+4]; dwClsContext
0x180022aba  lea     rcx, [rbp+57h+rclsid]; rclsid
0x180022abe  call    CoCreateInstance_0
0x180022ac3  lea     r8, [rbp+57h+pExceptionObject]
0x180022ac7  mov     edx, eax
0x180022ac9  lea     rcx, [rbp+57h+var_48]
0x180022acd  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180022ad2  mov     rdi, [rbp+57h+var_68]
0x180022ad6  mov     [rbp+57h+var_68], rdi
0x180022ada  mov     [rbp+57h+var_70], 7
0x180022ae1  mov     rax, [rdi]
0x180022ae4  mov     rsi, [rax+18h]
0x180022ae8  cmp     qword ptr [rbx], 0
0x180022aec  jz      short loc_180022AF6
0x180022aee  mov     rcx, rbx
0x180022af1  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x180022af6  mov     r9, rbx
0x180022af9  lea     r8, _GUID_fccc288d_b47e_41fa_970c_935ec952f4a4
0x180022b00  mov     edx, 1
0x180022b05  mov     rcx, rdi
0x180022b08  mov     rax, rsi
0x180022b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b10  mov     rcx, [rbp+5Fh]; this
0x180022b14  test    eax, eax
0x180022b16  js      short loc_180022B48
0x180022b18  test    rdi, rdi
0x180022b1b  jz      short loc_180022B26
0x180022b1d  lea     rcx, [rbp+57h+var_68]
0x180022b21  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x180022b26  mov     rax, rbx
0x180022b29  mov     rcx, [rbp+57h+var_20]
0x180022b2d  xor     rcx, rsp; StackCookie
0x180022b30  call    __security_check_cookie
0x180022b35  mov     rbx, [rsp+0A0h+arg_10]
0x180022b3d  add     rsp, 90h
0x180022b44  pop     rdi
0x180022b45  pop     rsi
0x180022b46  pop     rbp
0x180022b47  retn
0x180022b48  mov     r9d, eax; char *
0x180022b4b  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180022b52  mov     edx, 3E5h; void *
0x180022b57  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180022b5d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180022b61  call    ??0hresult_not_supported@factory_implementation@Update@System@Windows@winrt@@QEAA@XZ; winrt::Windows::System::Update::factory_implementation::hresult_not_supported::hresult_not_supported(void)
0x180022b66  lea     rdx, _TI2?AUhresult_not_supported@factory_implementation@Update@System@Windows@winrt@@; pThrowInfo
0x180022b6d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180022b71  call    _CxxThrowException_0
0x180022b77  lea     rcx, [rbp+57h+rclsid]
0x180022b7b  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180022b80  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180022b83  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180022b87  call    ??0hresult_access_denied@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::impl::slim_source_location const &)
0x180022b8c  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x180022b93  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180022b97  call    _CxxThrowException_0
```
