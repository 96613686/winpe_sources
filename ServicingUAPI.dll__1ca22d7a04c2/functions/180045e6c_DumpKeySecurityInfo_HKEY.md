# DumpKeySecurityInfo(HKEY__ *)

- ea: `0x180045e6c`
- end: `0x180045fd7`
- name: `?DumpKeySecurityInfo@@YAXPEAUHKEY__@@@Z`
- size: `363`
- prototype: `void __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180070418`

## callees

- `0x1800031d0`
- `0x1800062b8`
- `0x18000636c`
- `0x18000f614`
- `0x18000f874`
- `0x18001ba4c`
- `0x180043b00`
- `0x180045e6c`
- `0x180045fe0`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180045f72`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180045f72`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180045fa4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180045fa4`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180045ea1`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180045ed0`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180045ea1`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180045ed0`

## string_xrefs

- `0x180045f00`: `Failed getting key security dacl information`
- `0x180045f82`: `Failed converting security descriptor to string`
- `0x180045f94`: `  Key Security: {}`

## pseudocode

```c
void __fastcall DumpKeySecurityInfo(HKEY hKey)
{
  void *v2; // rdi
  LSTATUS KeySecurity; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  signed int v6; // ebx
  __int64 v7; // rdx
  int *StringSecurityDescriptorLen; // [rsp+20h] [rbp-40h]
  int v9[2]; // [rsp+30h] [rbp-30h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+38h] [rbp-28h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+40h] [rbp-20h] BYREF
  signed int v12; // [rsp+44h] [rbp-1Ch] BYREF
  ULONG v13; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  cbSecurityDescriptor = 0;
  if ( RegGetKeySecurity(hKey, 5u, 0, &cbSecurityDescriptor) == 122 )
  {
    v2 = operator new[](cbSecurityDescriptor);
    KeySecurity = RegGetKeySecurity(hKey, 5u, v2, &cbSecurityDescriptor);
    v6 = KeySecurity;
    if ( KeySecurity > 0 )
      v6 = (unsigned __int16)KeySecurity | 0x80070000;
    if ( v6 >= 0 )
    {
      StringSecurityDescriptor = 0;
      v13 = 0;
      if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v2, 1u, 5u, &StringSecurityDescriptor, &v13) )
      {
        LogAdapter::TraceInfo<wchar_t const *>("  Key Security: {}", &StringSecurityDescriptor);
        LocalFree(StringSecurityDescriptor);
      }
      else
      {
        LogAdapter::TraceError<>("Failed converting security descriptor to string");
      }
    }
    else
    {
      v12 = v6;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed getting key security dacl information");
        *(_QWORD *)v9 = &v12;
        LOBYTE(v7) = 1;
        StringSecurityDescriptorLen = v9;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v7,
          3,
          ": {}");
      }
      wil::details::in1diag3::Log_Hr(retaddr, v4, v5, (const char *)(unsigned int)v6, (int)StringSecurityDescriptorLen);
    }
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x180045e6c  mov     [rsp-8+arg_8], rbx
0x180045e71  mov     [rsp-8+arg_10], rdi
0x180045e76  push    rbp
0x180045e77  mov     rbp, rsp
0x180045e7a  sub     rsp, 60h
0x180045e7e  mov     rax, cs:__security_cookie
0x180045e85  xor     rax, rsp
0x180045e88  mov     [rbp+var_10], rax
0x180045e8c  xor     r8d, r8d; pSecurityDescriptor
0x180045e8f  mov     [rbp+cbSecurityDescriptor], 0
0x180045e96  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180045e9a  mov     rbx, rcx
0x180045e9d  lea     edx, [r8+5]; SecurityInformation
0x180045ea1  call    cs:__imp_RegGetKeySecurity
0x180045ea8  nop     dword ptr [rax+rax+00h]
0x180045ead  cmp     eax, 7Ah ; 'z'
0x180045eb0  jnz     loc_180045FB8
0x180045eb6  mov     ecx, [rbp+cbSecurityDescriptor]; unsigned __int64
0x180045eb9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180045ebe  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180045ec2  mov     r8, rax; pSecurityDescriptor
0x180045ec5  mov     edx, 5; SecurityInformation
0x180045eca  mov     rcx, rbx; hKey
0x180045ecd  mov     rdi, rax
0x180045ed0  call    cs:__imp_RegGetKeySecurity
0x180045ed7  nop     dword ptr [rax+rax+00h]
0x180045edc  mov     ebx, eax
0x180045ede  test    eax, eax
0x180045ee0  jle     short loc_180045EEB
0x180045ee2  movzx   ebx, ax
0x180045ee5  or      ebx, 80070000h
0x180045eeb  test    ebx, ebx
0x180045eed  jns     short loc_180045F4A
0x180045eef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180045ef6  mov     [rbp+var_1C], ebx
0x180045ef9  test    rcx, rcx
0x180045efc  jz      short loc_180045F3C
0x180045efe  xor     edx, edx
0x180045f00  lea     r9, aFailedGettingK_1; "Failed getting key security dacl inform"...
0x180045f07  lea     r8d, [rdx+3]
0x180045f0b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180045f10  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180045f17  lea     rax, [rbp+var_1C]
0x180045f1b  mov     qword ptr [rbp+var_30], rax
0x180045f1f  lea     r9, asc_1801CAFB4; ": {}"
0x180045f26  lea     rax, [rbp+var_30]
0x180045f2a  mov     r8d, 3
0x180045f30  mov     dl, 1
0x180045f32  mov     [rsp+60h+StringSecurityDescriptorLen], rax; int
0x180045f37  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180045f3c  mov     rcx, [rbp+8]; this
0x180045f40  mov     r9d, ebx; char *
0x180045f43  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180045f48  jmp     short loc_180045FB0
0x180045f4a  mov     edx, 1; RequestedStringSDRevision
0x180045f4f  mov     [rbp+StringSecurityDescriptor], 0
0x180045f57  lea     rax, [rbp+var_18]
0x180045f5b  mov     [rbp+var_18], 0
0x180045f62  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x180045f66  mov     [rsp+60h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x180045f6b  mov     rcx, rdi; SecurityDescriptor
0x180045f6e  lea     r8d, [rdx+4]; SecurityInformation
0x180045f72  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180045f79  nop     dword ptr [rax+rax+00h]
0x180045f7e  test    eax, eax
0x180045f80  jnz     short loc_180045F90
0x180045f82  lea     rcx, aFailedConverti_1; "Failed converting security descriptor t"...
0x180045f89  call    ??$TraceError@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceError<>(char const * const)
0x180045f8e  jmp     short loc_180045FB0
0x180045f90  lea     rdx, [rbp+StringSecurityDescriptor]
0x180045f94  lea     rcx, aKeySecurity; "  Key Security: {}"
0x180045f9b  call    ??$TraceInfo@PEB_W@LogAdapter@@YAXQEBDAEBQEB_W@Z; LogAdapter::TraceInfo<wchar_t const *>(char const * const,wchar_t const * const &)
0x180045fa0  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x180045fa4  call    cs:__imp_LocalFree
0x180045fab  nop     dword ptr [rax+rax+00h]
0x180045fb0  mov     rcx, rdi; Block
0x180045fb3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180045fb8  mov     rcx, [rbp+var_10]
0x180045fbc  xor     rcx, rsp; StackCookie
0x180045fbf  call    __security_check_cookie
0x180045fc4  lea     r11, [rsp+60h+var_s0]
0x180045fc9  mov     rbx, [r11+18h]
0x180045fcd  mov     rdi, [r11+20h]
0x180045fd1  mov     rsp, r11
0x180045fd4  pop     rbp
0x180045fd5  retn
```
