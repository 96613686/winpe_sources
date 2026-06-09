# Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::SerializeGroupInfo(Windows::Internal::AssignedAccess::RegistryKeyBroker &,ulong,Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *)

- ea: `0x180066928`
- end: `0x180066a54`
- name: `?SerializeGroupInfo@RegistryDataStoreV1Impl@AssignedAccess@Internal@Windows@@AEAAXAEAVRegistryKeyBroker@234@KPEAUIAssignedAccessUserInfo@234@@Z`
- size: `300`
- prototype: `void(Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl *__hidden this, struct Windows::Internal::AssignedAccess::RegistryKeyBroker *, unsigned int, struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800655ec`

## callees

- `0x180006640`
- `0x180010c98`
- `0x180014a5c`
- `0x18002001c`
- `0x180020050`
- `0x18002b190`
- `0x18003bfac`
- `0x1800575cc`
- `0x18005e4bc`
- `0x180063124`
- `0x180064314`
- `0x180066928`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800669fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800669fd`

## string_xrefs

- `0x180066a0e`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x1800669b3`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x180066961`: `GroupConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::SerializeGroupInfo(
        Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl *this,
        struct Windows::Internal::AssignedAccess::RegistryKeyBroker *a2,
        unsigned int a3,
        struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *a4)
{
  struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *v6; // r8
  int v7; // eax
  const WCHAR *v8; // rax
  unsigned int v9; // eax
  int lpData; // [rsp+20h] [rbp-59h]
  unsigned int lpDataa; // [rsp+20h] [rbp-59h]
  BYTE Data[16]; // [rsp+30h] [rbp-49h] BYREF
  HKEY v13[3]; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v14[2]; // [rsp+58h] [rbp-21h] BYREF
  char v15; // [rsp+68h] [rbp-11h]
  _BYTE v16[32]; // [rsp+78h] [rbp-1h] BYREF
  _BYTE v17[32]; // [rsp+98h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *(_DWORD *)Data = a3;
  std::_Integral_to_string<unsigned short,unsigned int>(v14, a3);
  std::operator+<unsigned short>(v16, L"GroupConfig", v14);
  std::wstring::_Tidy_deallocate(v14);
  Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(a2, v13, v16);
  v14[0] = a2;
  v14[1] = v16;
  v15 = 1;
  v7 = Windows::Internal::AssignedAccess::Details::Serialize(v13, a4, v6);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x126,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
      (const char *)(unsigned int)v7,
      lpData);
  std::wstring::wstring(v17, L"Index");
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
  v9 = RegSetValueExW(v13[2], v8, 0, 4u, Data, 4u);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
      (const char *)v9,
      lpDataa);
  std::wstring::_Tidy_deallocate(v17);
  Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v13);
  std::wstring::_Tidy_deallocate(v16);
}

```

## disassembly

```asm
0x180066928  push    rbp
0x18006692a  push    rbx
0x18006692b  push    rdi
0x18006692c  lea     rbp, [rsp-47h]
0x180066931  sub     rsp, 0C0h
0x180066938  mov     rax, cs:__security_cookie
0x18006693f  xor     rax, rsp
0x180066942  mov     [rbp+57h+var_18], rax
0x180066946  mov     rdi, r9
0x180066949  mov     rbx, rdx
0x18006694c  mov     dword ptr [rbp+57h+Data], r8d
0x180066950  mov     edx, r8d
0x180066953  lea     rcx, [rbp+57h+var_78]
0x180066957  call    ??$_Integral_to_string@GI@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@I@Z; std::_Integral_to_string<ushort,uint>(uint)
0x18006695c  nop
0x18006695d  lea     r8, [rbp+57h+var_78]
0x180066961  lea     rdx, aGroupconfig; "GroupConfig"
0x180066968  lea     rcx, [rbp+57h+var_58]
0x18006696c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x180066971  nop
0x180066972  lea     rcx, [rbp+57h+var_78]
0x180066976  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006697b  lea     r8, [rbp+57h+var_58]
0x18006697f  lea     rdx, [rbp+57h+var_90]
0x180066983  mov     rcx, rbx
0x180066986  call    ?Create@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(std::wstring const &,ulong,ulong)
0x18006698b  nop
0x18006698c  mov     [rbp+57h+var_78], rbx
0x180066990  lea     rax, [rbp+57h+var_58]
0x180066994  mov     [rbp+57h+var_70], rax
0x180066998  mov     [rbp+57h+var_68], 1
0x18006699c  mov     rdx, rdi; struct Windows::Internal::AssignedAccess::RegistryKeyBroker *
0x18006699f  lea     rcx, [rbp+57h+var_90]; this
0x1800669a3  call    ?Serialize@Details@AssignedAccess@Internal@Windows@@YAJAEAVRegistryKeyBroker@234@PEAUIAssignedAccessUserInfo@234@@Z; Windows::Internal::AssignedAccess::Details::Serialize(Windows::Internal::AssignedAccess::RegistryKeyBroker &,Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *)
0x1800669a8  mov     rcx, [rbp+5Fh]; this
0x1800669ac  test    eax, eax
0x1800669ae  jns     short loc_1800669C5
0x1800669b0  mov     r9d, eax; char *
0x1800669b3  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800669ba  mov     edx, 126h; void *
0x1800669bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800669c5  lea     rdx, aIndex; "Index"
0x1800669cc  lea     rcx, [rbp+57h+var_38]
0x1800669d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800669d5  nop
0x1800669d6  lea     rcx, [rbp+57h+var_38]
0x1800669da  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800669df  mov     rdx, rax; lpValueName
0x1800669e2  mov     r9d, 4; dwType
0x1800669e8  mov     [rsp+0D0h+cbData], r9d; cbData
0x1800669ed  lea     rax, [rbp+57h+Data]
0x1800669f1  mov     [rsp+0D0h+lpData], rax; unsigned int
0x1800669f6  xor     r8d, r8d; Reserved
0x1800669f9  mov     rcx, [rbp+57h+hKey]; hKey
0x1800669fd  call    cs:__imp_RegSetValueExW
0x180066a03  mov     rcx, [rbp+5Fh]; this
0x180066a07  test    eax, eax
0x180066a09  jz      short loc_180066A20
0x180066a0b  mov     r9d, eax; char *
0x180066a0e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x180066a15  mov     edx, 0CDh; void *
0x180066a1a  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180066a20  lea     rcx, [rbp+57h+var_38]
0x180066a24  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066a29  nop
0x180066a2a  lea     rcx, [rbp+57h+var_90]; this
0x180066a2e  call    ??1RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker(void)
0x180066a33  nop
0x180066a34  lea     rcx, [rbp+57h+var_58]
0x180066a38  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066a3d  mov     rcx, [rbp+57h+var_18]
0x180066a41  xor     rcx, rsp; StackCookie
0x180066a44  call    __security_check_cookie
0x180066a49  add     rsp, 0C0h
0x180066a50  pop     rdi
0x180066a51  pop     rbx
0x180066a52  pop     rbp
0x180066a53  retn
```
