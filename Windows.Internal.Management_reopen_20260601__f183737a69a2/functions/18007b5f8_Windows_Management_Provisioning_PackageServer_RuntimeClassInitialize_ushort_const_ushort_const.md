# Windows::Management::Provisioning::PackageServer::RuntimeClassInitialize(ushort const *,ushort const *)

- ea: `0x18007b5f8`
- end: `0x18007b8e2`
- name: `?RuntimeClassInitialize@PackageServer@Provisioning@Management@Windows@@QEAAJPEBG0@Z`
- size: `746`
- prototype: `__int64 __fastcall(Windows::Management::Provisioning::PackageServer *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18007110c`

## callees

- `0x1800011d4`
- `0x180004eb0`
- `0x18000539c`
- `0x18000a5c4`
- `0x18000abec`
- `0x18000d50c`
- `0x18000dc18`
- `0x180016698`
- `0x180017024`
- `0x180017118`
- `0x180071d28`
- `0x18007a750`
- `0x18007a7a0`
- `0x18007b580`
- `0x18007b5f8`
- `0x18007b8e8`
- `0x1800b1c5c`
- `0x1800b2024`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007b84f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007b84f`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18007b7db`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18007b7db`

## string_xrefs

- `0x18007b83b`: `PackageInstallStart`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
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
  __int64 PackageAuthor; // rax
  __int64 v14; // rax
  bool IsStateSeparationEnabled; // al
  const WCHAR *v16; // rdx
  const unsigned __int16 *v17; // rax
  __int64 v18; // rax
  int pdwType; // [rsp+20h] [rbp-2E8h]
  DWORD pcbData[2]; // [rsp+40h] [rbp-2C8h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-2C0h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-2B8h] BYREF
  _BYTE v23[32]; // [rsp+60h] [rbp-2A8h] BYREF
  _BYTE v24[32]; // [rsp+80h] [rbp-288h] BYREF
  _BYTE pvData[48]; // [rsp+A0h] [rbp-268h] BYREF
  WCHAR SubKey[264]; // [rsp+D0h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+0h]

  v22[0] = operator new(0xA8u);
  *(_QWORD *)pcbData = v23;
  v6 = std::wstring::wstring(v23, a3);
  v7 = std::wstring::wstring(pvData, a2);
  v8 = ProvPackage::ProvPackage(v22[0], v7, v6);
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v22, v8);
  v9 = v22[0];
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v22[0] + 72LL))(v22[0]) )
  {
    v11 = (**(__int64 (__fastcall ***)(__int64, _BYTE *))v9)(v9, v24);
    std::wstring::operator=((char *)this + 40, v11);
    std::wstring::~wstring(v24);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 56LL))(v9);
    std::wstring::operator=((char *)this + 72);
    v12 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v9 + 16LL))(v9, v24);
    std::wstring::operator=((char *)this + 104, v12);
    std::wstring::~wstring(v24);
    PackageAuthor = ProvPackage::GetPackageAuthor(v9, v24);
    std::wstring::operator=((char *)this + 136, PackageAuthor);
    std::wstring::~wstring(v24);
    v14 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v9 + 24LL))(v9, v24);
    std::wstring::operator=((char *)this + 168, v14);
    std::wstring::~wstring(v24);
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
    v16 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Results";
    if ( !IsStateSeparationEnabled )
      v16 = L"SOFTWARE\\Microsoft\\Provisioning\\Results";
    if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, v16, &phkResult) )
    {
      v17 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 104);
      StringCchCopyW(SubKey, 0x104u, v17);
      pcbData[0] = 40;
      if ( RegGetValueW(phkResult, SubKey, L"PackageInstallStart", 2u, 0, pvData, pcbData) )
      {
        std::wstring::_Eos((char *)this + 200);
      }
      else
      {
        v18 = std::wstring::wstring(v24, pvData);
        std::wstring::operator=((char *)this + 200, v18);
        std::wstring::~wstring(v24);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    std::unique_ptr<ProvPackage>::~unique_ptr<ProvPackage>(v22);
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
    std::unique_ptr<ProvPackage>::~unique_ptr<ProvPackage>(v22);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18007b5f8  mov     [rsp+arg_18], rbx
0x18007b5fd  push    rsi
0x18007b5fe  push    rdi
0x18007b5ff  push    r14
0x18007b601  sub     rsp, 2F0h
0x18007b608  mov     rax, cs:__security_cookie
0x18007b60f  xor     rax, rsp
0x18007b612  mov     [rsp+308h+var_28], rax
0x18007b61a  mov     rsi, r8
0x18007b61d  mov     r14, rdx
0x18007b620  mov     rdi, rcx
0x18007b623  mov     ecx, 0A8h; Size
0x18007b628  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007b62d  mov     rbx, rax
0x18007b630  mov     [rsp+308h+var_2B8], rax
0x18007b635  lea     rax, [rsp+308h+var_2A8]
0x18007b63a  mov     qword ptr [rsp+308h+var_2C8], rax
0x18007b63f  mov     rdx, rsi
0x18007b642  lea     rcx, [rsp+308h+var_2A8]
0x18007b647  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007b64c  mov     rsi, rax
0x18007b64f  mov     rdx, r14
0x18007b652  lea     rcx, [rsp+308h+var_268]
0x18007b65a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007b65f  nop
0x18007b660  mov     r8, rsi
0x18007b663  mov     rdx, rax
0x18007b666  mov     rcx, rbx
0x18007b669  call    ??0ProvPackage@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ProvPackage::ProvPackage(std::wstring,std::wstring)
0x18007b66e  nop
0x18007b66f  mov     rdx, rax
0x18007b672  lea     rcx, [rsp+308h+var_2B8]
0x18007b677  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18007b67c  nop
0x18007b67d  mov     rbx, [rsp+308h+var_2B8]
0x18007b682  mov     rax, [rbx]
0x18007b685  mov     rcx, rbx
0x18007b688  mov     rax, [rax+48h]
0x18007b68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b691  test    al, al
0x18007b693  jnz     short loc_18007B6C8
0x18007b695  mov     rcx, [rsp+308h]; this
0x18007b69d  mov     ebx, 8000FFFFh
0x18007b6a2  mov     r9d, ebx; char *
0x18007b6a5  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007b6ac  mov     edx, 29h ; ')'; void *
0x18007b6b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b6b6  nop
0x18007b6b7  lea     rcx, [rsp+308h+var_2B8]
0x18007b6bc  call    ??1?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@QEAA@XZ; std::unique_ptr<ProvPackage>::~unique_ptr<ProvPackage>(void)
0x18007b6c1  mov     eax, ebx
0x18007b6c3  jmp     loc_18007B8BD
0x18007b6c8  mov     rax, [rbx]
0x18007b6cb  lea     rdx, [rsp+308h+var_288]
0x18007b6d3  mov     rcx, rbx
0x18007b6d6  mov     rax, [rax]
0x18007b6d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b6de  lea     rcx, [rdi+28h]
0x18007b6e2  mov     rdx, rax
0x18007b6e5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007b6ea  lea     rcx, [rsp+308h+var_288]
0x18007b6f2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007b6f7  mov     rax, [rbx]
0x18007b6fa  mov     rcx, rbx
0x18007b6fd  mov     rax, [rax+38h]
0x18007b701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b706  lea     rcx, [rdi+48h]
0x18007b70a  mov     rdx, rax
0x18007b70d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18007b712  mov     rax, [rbx]
0x18007b715  lea     rdx, [rsp+308h+var_288]
0x18007b71d  mov     rcx, rbx
0x18007b720  mov     rax, [rax+10h]
0x18007b724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b729  mov     rdx, rax
0x18007b72c  lea     rcx, [rdi+68h]
0x18007b730  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007b735  lea     rcx, [rsp+308h+var_288]
0x18007b73d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007b742  lea     rdx, [rsp+308h+var_288]
0x18007b74a  mov     rcx, rbx
0x18007b74d  call    ?GetPackageAuthor@ProvPackage@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvPackage::GetPackageAuthor(void)
0x18007b752  lea     rcx, [rdi+88h]
0x18007b759  mov     rdx, rax
0x18007b75c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007b761  lea     rcx, [rsp+308h+var_288]
0x18007b769  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007b76e  mov     rax, [rbx]
0x18007b771  lea     rdx, [rsp+308h+var_288]
0x18007b779  mov     rcx, rbx
0x18007b77c  mov     rax, [rax+18h]
0x18007b780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b785  lea     rcx, [rdi+0A8h]
0x18007b78c  mov     rdx, rax
0x18007b78f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007b794  lea     rcx, [rsp+308h+var_288]
0x18007b79c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007b7a1  mov     [rsp+308h+phkResult], 0
0x18007b7aa  xor     edx, edx
0x18007b7ac  lea     rcx, [rsp+308h+phkResult]
0x18007b7b1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18007b7b6  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x18007b7bb  lea     rcx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Provisioning\\Resu"...
0x18007b7c2  lea     rdx, aOsdataSoftware_4; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x18007b7c9  test    al, al
0x18007b7cb  cmovz   rdx, rcx; lpSubKey
0x18007b7cf  lea     r8, [rsp+308h+phkResult]; phkResult
0x18007b7d4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007b7db  call    cs:__imp_RegOpenKeyW
0x18007b7e2  nop     dword ptr [rax+rax+00h]
0x18007b7e7  test    eax, eax
0x18007b7e9  jnz     loc_18007B89F
0x18007b7ef  lea     rcx, [rdi+68h]
0x18007b7f3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b7f8  mov     r8, rax; unsigned __int16 *
0x18007b7fb  mov     edx, 104h; unsigned __int64
0x18007b800  lea     rcx, [rsp+308h+SubKey]; unsigned __int16 *
0x18007b808  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007b80d  mov     [rsp+308h+var_2C8], 28h ; '('
0x18007b815  lea     rax, [rsp+308h+var_2C8]
0x18007b81a  mov     [rsp+308h+pcbData], rax; pcbData
0x18007b81f  lea     rax, [rsp+308h+var_268]
0x18007b827  mov     [rsp+308h+pvData], rax; pvData
0x18007b82c  mov     [rsp+308h+pdwType], 0; pdwType
0x18007b835  mov     r9d, 2; dwFlags
0x18007b83b  lea     r8, aPackageinstall; "PackageInstallStart"
0x18007b842  lea     rdx, [rsp+308h+SubKey]; lpSubKey
0x18007b84a  mov     rcx, [rsp+308h+phkResult]; hkey
0x18007b84f  call    cs:__imp_RegGetValueW
0x18007b856  nop     dword ptr [rax+rax+00h]
0x18007b85b  test    eax, eax
0x18007b85d  jnz     short loc_18007B892
0x18007b85f  lea     rdx, [rsp+308h+var_268]
0x18007b867  lea     rcx, [rsp+308h+var_288]
0x18007b86f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007b874  lea     rcx, [rdi+0C8h]
0x18007b87b  mov     rdx, rax
0x18007b87e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007b883  lea     rcx, [rsp+308h+var_288]
0x18007b88b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007b890  jmp     short loc_18007B89F
0x18007b892  lea     rcx, [rdi+0C8h]
0x18007b899  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x18007b89e  nop
0x18007b89f  lea     rcx, [rsp+308h+phkResult]
0x18007b8a4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007b8a9  nop
0x18007b8aa  lea     rcx, [rsp+308h+var_2B8]
0x18007b8af  call    ??1?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@QEAA@XZ; std::unique_ptr<ProvPackage>::~unique_ptr<ProvPackage>(void)
0x18007b8b4  nop
0x18007b8b5  xor     eax, eax
0x18007b8b7  jmp     short loc_18007B8BD
0x18007b8b9  mov     eax, [rsp+308h+var_2C8]
0x18007b8bd  mov     rcx, [rsp+308h+var_28]
0x18007b8c5  xor     rcx, rsp; StackCookie
0x18007b8c8  call    __security_check_cookie
0x18007b8cd  mov     rbx, [rsp+308h+arg_18]
0x18007b8d5  add     rsp, 2F0h
0x18007b8dc  pop     r14
0x18007b8de  pop     rdi
0x18007b8df  pop     rsi
0x18007b8e0  retn
```
