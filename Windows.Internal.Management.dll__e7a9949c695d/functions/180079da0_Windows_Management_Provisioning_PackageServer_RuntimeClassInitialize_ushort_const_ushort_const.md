# Windows::Management::Provisioning::PackageServer::RuntimeClassInitialize(ushort const *,ushort const *)

- ea: `0x180079da0`
- end: `0x18007a07e`
- name: `?RuntimeClassInitialize@PackageServer@Provisioning@Management@Windows@@QEAAJPEBG0@Z`
- size: `734`
- prototype: `__int64 __fastcall(Windows::Management::Provisioning::PackageServer *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18006fb68`

## callees

- `0x1800011d4`
- `0x180004d50`
- `0x18000523c`
- `0x18000a2a4`
- `0x18000a8a4`
- `0x18000cfdc`
- `0x18000d724`
- `0x180015f70`
- `0x1800168d0`
- `0x1800169b8`
- `0x1800706b0`
- `0x180078f4c`
- `0x180078f9c`
- `0x180079d34`
- `0x180079da0`
- `0x18007a084`
- `0x1800ae954`
- `0x1800aed10`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079ff1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079ff1`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180079f83`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180079f83`

## string_xrefs

- `0x180079fdd`: `PackageInstallStart`

## pseudocode

```c
__int64 __fastcall Windows::Management::Provisioning::PackageServer::RuntimeClassInitialize(
        Windows::Management::Provisioning::PackageServer *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 PackageAuthor; // rax
  __int64 v15; // rax
  bool IsStateSeparationEnabled; // al
  const WCHAR *v17; // rdx
  const unsigned __int16 *v18; // rax
  __int64 v19; // rax
  int pdwType; // [rsp+20h] [rbp-2E8h]
  DWORD pcbData[2]; // [rsp+40h] [rbp-2C8h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-2C0h] BYREF
  _QWORD v23[2]; // [rsp+50h] [rbp-2B8h] BYREF
  _BYTE v24[32]; // [rsp+60h] [rbp-2A8h] BYREF
  _BYTE v25[32]; // [rsp+80h] [rbp-288h] BYREF
  _BYTE pvData[48]; // [rsp+A0h] [rbp-268h] BYREF
  WCHAR SubKey[264]; // [rsp+D0h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+0h]

  v23[0] = operator new(0xA8u);
  *(_QWORD *)pcbData = v24;
  v6 = std::wstring::wstring(v24, a3);
  v7 = std::wstring::wstring(pvData, a2);
  v8 = ProvPackage::ProvPackage(v23[0], v7, v6);
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v23, v8);
  v9 = v23[0];
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v23[0] + 72LL))(v23[0]) )
  {
    v11 = (**(__int64 (__fastcall ***)(__int64, _BYTE *))v9)(v9, v25);
    std::wstring::operator=((char *)this + 40, v11);
    std::wstring::~wstring(v25);
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 56LL))(v9);
    std::wstring::operator=((char *)this + 72, v12);
    v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v9 + 16LL))(v9, v25);
    std::wstring::operator=((char *)this + 104, v13);
    std::wstring::~wstring(v25);
    PackageAuthor = ProvPackage::GetPackageAuthor(v9, v25);
    std::wstring::operator=((char *)this + 136, PackageAuthor);
    std::wstring::~wstring(v25);
    v15 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v9 + 24LL))(v9, v25);
    std::wstring::operator=((char *)this + 168, v15);
    std::wstring::~wstring(v25);
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
    v17 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Results";
    if ( !IsStateSeparationEnabled )
      v17 = L"SOFTWARE\\Microsoft\\Provisioning\\Results";
    if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, v17, &phkResult) )
    {
      v18 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 104);
      StringCchCopyW(SubKey, 0x104u, v18);
      pcbData[0] = 40;
      if ( RegGetValueW(phkResult, SubKey, L"PackageInstallStart", 2u, 0, pvData, pcbData) )
      {
        std::wstring::_Eos((char *)this + 200);
      }
      else
      {
        v19 = std::wstring::wstring(v25, pvData);
        std::wstring::operator=((char *)this + 200, v19);
        std::wstring::~wstring(v25);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    std::unique_ptr<ProvPackage>::~unique_ptr<ProvPackage>(v23);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packageserver.cpp",
      (const char *)0x8000FFFFLL,
      pdwType);
    std::unique_ptr<ProvPackage>::~unique_ptr<ProvPackage>(v23);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x180079da0  mov     [rsp+arg_18], rbx
0x180079da5  push    rsi
0x180079da6  push    rdi
0x180079da7  push    r14
0x180079da9  sub     rsp, 2F0h
0x180079db0  mov     rax, cs:__security_cookie
0x180079db7  xor     rax, rsp
0x180079dba  mov     [rsp+308h+var_28], rax
0x180079dc2  mov     rsi, r8
0x180079dc5  mov     r14, rdx
0x180079dc8  mov     rdi, rcx
0x180079dcb  mov     ecx, 0A8h; Size
0x180079dd0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180079dd5  mov     rbx, rax
0x180079dd8  mov     [rsp+308h+var_2B8], rax
0x180079ddd  lea     rax, [rsp+308h+var_2A8]
0x180079de2  mov     qword ptr [rsp+308h+var_2C8], rax
0x180079de7  mov     rdx, rsi
0x180079dea  lea     rcx, [rsp+308h+var_2A8]
0x180079def  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180079df4  mov     rsi, rax
0x180079df7  mov     rdx, r14
0x180079dfa  lea     rcx, [rsp+308h+var_268]
0x180079e02  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180079e07  nop
0x180079e08  mov     r8, rsi
0x180079e0b  mov     rdx, rax
0x180079e0e  mov     rcx, rbx
0x180079e11  call    ??0ProvPackage@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ProvPackage::ProvPackage(std::wstring,std::wstring)
0x180079e16  nop
0x180079e17  mov     rdx, rax
0x180079e1a  lea     rcx, [rsp+308h+var_2B8]
0x180079e1f  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180079e24  nop
0x180079e25  mov     rbx, [rsp+308h+var_2B8]
0x180079e2a  mov     rax, [rbx]
0x180079e2d  mov     rcx, rbx
0x180079e30  mov     rax, [rax+48h]
0x180079e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079e39  test    al, al
0x180079e3b  jnz     short loc_180079E70
0x180079e3d  mov     rcx, [rsp+308h]; this
0x180079e45  mov     ebx, 8000FFFFh
0x180079e4a  mov     r9d, ebx; char *
0x180079e4d  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180079e54  mov     edx, 29h ; ')'; void *
0x180079e59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079e5e  nop
0x180079e5f  lea     rcx, [rsp+308h+var_2B8]
0x180079e64  call    ??1?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@QEAA@XZ; std::unique_ptr<ProvPackage>::~unique_ptr<ProvPackage>(void)
0x180079e69  mov     eax, ebx
0x180079e6b  jmp     loc_18007A059
0x180079e70  mov     rax, [rbx]
0x180079e73  lea     rdx, [rsp+308h+var_288]
0x180079e7b  mov     rcx, rbx
0x180079e7e  mov     rax, [rax]
0x180079e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079e86  lea     rcx, [rdi+28h]
0x180079e8a  mov     rdx, rax
0x180079e8d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180079e92  lea     rcx, [rsp+308h+var_288]
0x180079e9a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180079e9f  mov     rax, [rbx]
0x180079ea2  mov     rcx, rbx
0x180079ea5  mov     rax, [rax+38h]
0x180079ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079eae  lea     rcx, [rdi+48h]
0x180079eb2  mov     rdx, rax
0x180079eb5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180079eba  mov     rax, [rbx]
0x180079ebd  lea     rdx, [rsp+308h+var_288]
0x180079ec5  mov     rcx, rbx
0x180079ec8  mov     rax, [rax+10h]
0x180079ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079ed1  mov     rdx, rax
0x180079ed4  lea     rcx, [rdi+68h]
0x180079ed8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180079edd  lea     rcx, [rsp+308h+var_288]
0x180079ee5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180079eea  lea     rdx, [rsp+308h+var_288]
0x180079ef2  mov     rcx, rbx
0x180079ef5  call    ?GetPackageAuthor@ProvPackage@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvPackage::GetPackageAuthor(void)
0x180079efa  lea     rcx, [rdi+88h]
0x180079f01  mov     rdx, rax
0x180079f04  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180079f09  lea     rcx, [rsp+308h+var_288]
0x180079f11  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180079f16  mov     rax, [rbx]
0x180079f19  lea     rdx, [rsp+308h+var_288]
0x180079f21  mov     rcx, rbx
0x180079f24  mov     rax, [rax+18h]
0x180079f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079f2d  lea     rcx, [rdi+0A8h]
0x180079f34  mov     rdx, rax
0x180079f37  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180079f3c  lea     rcx, [rsp+308h+var_288]
0x180079f44  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180079f49  mov     [rsp+308h+phkResult], 0
0x180079f52  xor     edx, edx
0x180079f54  lea     rcx, [rsp+308h+phkResult]
0x180079f59  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180079f5e  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x180079f63  lea     rcx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Provisioning\\Resu"...
0x180079f6a  lea     rdx, aOsdataSoftware_4; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x180079f71  test    al, al
0x180079f73  cmovz   rdx, rcx; lpSubKey
0x180079f77  lea     r8, [rsp+308h+phkResult]; phkResult
0x180079f7c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180079f83  call    cs:__imp_RegOpenKeyW
0x180079f89  test    eax, eax
0x180079f8b  jnz     loc_18007A03B
0x180079f91  lea     rcx, [rdi+68h]
0x180079f95  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180079f9a  mov     r8, rax; unsigned __int16 *
0x180079f9d  mov     edx, 104h; unsigned __int64
0x180079fa2  lea     rcx, [rsp+308h+SubKey]; unsigned __int16 *
0x180079faa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180079faf  mov     [rsp+308h+var_2C8], 28h ; '('
0x180079fb7  lea     rax, [rsp+308h+var_2C8]
0x180079fbc  mov     [rsp+308h+pcbData], rax; pcbData
0x180079fc1  lea     rax, [rsp+308h+var_268]
0x180079fc9  mov     [rsp+308h+pvData], rax; pvData
0x180079fce  mov     [rsp+308h+pdwType], 0; pdwType
0x180079fd7  mov     r9d, 2; dwFlags
0x180079fdd  lea     r8, aPackageinstall; "PackageInstallStart"
0x180079fe4  lea     rdx, [rsp+308h+SubKey]; lpSubKey
0x180079fec  mov     rcx, [rsp+308h+phkResult]; hkey
0x180079ff1  call    cs:__imp_RegGetValueW
0x180079ff7  test    eax, eax
0x180079ff9  jnz     short loc_18007A02E
0x180079ffb  lea     rdx, [rsp+308h+var_268]
0x18007a003  lea     rcx, [rsp+308h+var_288]
0x18007a00b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007a010  lea     rcx, [rdi+0C8h]
0x18007a017  mov     rdx, rax
0x18007a01a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007a01f  lea     rcx, [rsp+308h+var_288]
0x18007a027  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007a02c  jmp     short loc_18007A03B
0x18007a02e  lea     rcx, [rdi+0C8h]
0x18007a035  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x18007a03a  nop
0x18007a03b  lea     rcx, [rsp+308h+phkResult]
0x18007a040  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007a045  nop
0x18007a046  lea     rcx, [rsp+308h+var_2B8]
0x18007a04b  call    ??1?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@QEAA@XZ; std::unique_ptr<ProvPackage>::~unique_ptr<ProvPackage>(void)
0x18007a050  nop
0x18007a051  xor     eax, eax
0x18007a053  jmp     short loc_18007A059
0x18007a055  mov     eax, [rsp+308h+var_2C8]
0x18007a059  mov     rcx, [rsp+308h+var_28]
0x18007a061  xor     rcx, rsp; StackCookie
0x18007a064  call    __security_check_cookie
0x18007a069  mov     rbx, [rsp+308h+arg_18]
0x18007a071  add     rsp, 2F0h
0x18007a078  pop     r14
0x18007a07a  pop     rdi
0x18007a07b  pop     rsi
0x18007a07c  retn
```
