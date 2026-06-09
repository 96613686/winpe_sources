# DumpKeySecurityInfo(HKEY__ *)

- ea: `0x140011ee8`
- end: `0x14001205e`
- name: `?DumpKeySecurityInfo@@YAXPEAUHKEY__@@@Z`
- size: `374`
- prototype: `void __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140010fe0`

## callees

- `0x140002310`
- `0x140008d38`
- `0x140008ef4`
- `0x14000d910`
- `0x14000e034`
- `0x140010e08`
- `0x140011d0c`
- `0x140011ee8`
- `0x140012064`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140011f18`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140011f56`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140011f18`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140011f56`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x140011ff3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x140011ff3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140012038`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140012038`

## string_xrefs

- `0x140011f80`: `Failed getting key security dacl information`
- `0x140011ffd`: `Failed converting security descriptor to string`
- `0x140012021`: `  Key Security: {}`

## pseudocode

```c
void __fastcall DumpKeySecurityInfo(HKEY hKey)
{
  const struct std::nothrow_t *v2; // rdx
  LSTATUS KeySecurity; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  signed int v6; // ebx
  __int64 v7; // rdx
  int StringSecurityDescriptorLen; // [rsp+20h] [rbp-40h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+30h] [rbp-30h] BYREF
  int v10[2]; // [rsp+38h] [rbp-28h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+40h] [rbp-20h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+48h] [rbp-18h] BYREF
  signed int v13; // [rsp+4Ch] [rbp-14h] BYREF
  ULONG v14; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  cbSecurityDescriptor = 0;
  if ( RegGetKeySecurity(hKey, 5u, 0, &cbSecurityDescriptor) == 122 )
  {
    pSecurityDescriptor = 0;
    Windows::AutoNewArrayPtr<unsigned char>::AllocateArray(&pSecurityDescriptor, cbSecurityDescriptor);
    if ( pSecurityDescriptor )
    {
      KeySecurity = RegGetKeySecurity(hKey, 5u, pSecurityDescriptor, &cbSecurityDescriptor);
      v6 = KeySecurity;
      if ( KeySecurity > 0 )
        v6 = (unsigned __int16)KeySecurity | 0x80070000;
      if ( v6 >= 0 )
      {
        StringSecurityDescriptor = 0;
        v14 = 0;
        if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
               pSecurityDescriptor,
               1u,
               5u,
               &StringSecurityDescriptor,
               &v14) )
        {
          if ( LogAdapter::g_Logger )
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              1,
              1,
              (__int64)"  Key Security: {}",
              (__int64)&StringSecurityDescriptor);
          LocalFree(StringSecurityDescriptor);
        }
        else
        {
          LogAdapter::TraceAtLevel<>(
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed converting security descriptor to string");
        }
      }
      else
      {
        v13 = v6;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting key security dacl information");
          *(_QWORD *)v10 = &v13;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v7,
            3,
            (__int64)": {}",
            (__int64)v10);
        }
        wil::details::in1diag3::Log_Hr(retaddr, v4, v5, (const char *)(unsigned int)v6, StringSecurityDescriptorLen);
      }
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&pSecurityDescriptor, v2);
  }
}

```

## disassembly

```asm
0x140011ee8  mov     [rsp-8+arg_8], rbx
0x140011eed  push    rbp
0x140011eee  mov     rbp, rsp
0x140011ef1  sub     rsp, 60h
0x140011ef5  mov     rax, cs:__security_cookie
0x140011efc  xor     rax, rsp
0x140011eff  mov     [rbp+var_8], rax
0x140011f03  xor     r8d, r8d; pSecurityDescriptor
0x140011f06  mov     [rbp+cbSecurityDescriptor], 0
0x140011f0d  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x140011f11  mov     rbx, rcx
0x140011f14  lea     edx, [r8+5]; SecurityInformation
0x140011f18  call    cs:__imp_RegGetKeySecurity
0x140011f1e  cmp     eax, 7Ah ; 'z'
0x140011f21  jnz     loc_140012047
0x140011f27  mov     edx, [rbp+cbSecurityDescriptor]
0x140011f2a  lea     rcx, [rbp+pSecurityDescriptor]
0x140011f2e  mov     [rbp+pSecurityDescriptor], 0
0x140011f36  call    ?AllocateArray@?$AutoNewArrayPtr@E@Windows@@QEAAPEAE_K@Z; Windows::AutoNewArrayPtr<uchar>::AllocateArray(unsigned __int64)
0x140011f3b  cmp     [rbp+pSecurityDescriptor], 0
0x140011f40  jz      loc_14001203E
0x140011f46  mov     r8, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x140011f4a  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x140011f4e  mov     edx, 5; SecurityInformation
0x140011f53  mov     rcx, rbx; hKey
0x140011f56  call    cs:__imp_RegGetKeySecurity
0x140011f5c  mov     ebx, eax
0x140011f5e  test    eax, eax
0x140011f60  jle     short loc_140011F6B
0x140011f62  movzx   ebx, ax
0x140011f65  or      ebx, 80070000h
0x140011f6b  test    ebx, ebx
0x140011f6d  jns     short loc_140011FC8
0x140011f6f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011f76  mov     [rbp+var_14], ebx
0x140011f79  test    rcx, rcx
0x140011f7c  jz      short loc_140011FBA
0x140011f7e  xor     edx, edx
0x140011f80  lea     r9, aFailedGettingK; "Failed getting key security dacl inform"...
0x140011f87  lea     r8d, [rdx+3]
0x140011f8b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140011f90  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011f97  lea     rax, [rbp+var_14]
0x140011f9b  mov     qword ptr [rbp+var_28], rax
0x140011f9f  lea     r9, asc_140030534; ": {}"
0x140011fa6  lea     rax, [rbp+var_28]
0x140011faa  mov     r8d, 3
0x140011fb0  mov     qword ptr [rsp+60h+StringSecurityDescriptorLen], rax; int
0x140011fb5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140011fba  mov     rcx, [rbp+8]; this
0x140011fbe  mov     r9d, ebx; char *
0x140011fc1  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x140011fc6  jmp     short loc_14001203E
0x140011fc8  mov     rcx, [rbp+pSecurityDescriptor]; SecurityDescriptor
0x140011fcc  lea     rax, [rbp+var_10]
0x140011fd0  mov     ebx, 1
0x140011fd5  mov     [rbp+StringSecurityDescriptor], 0
0x140011fdd  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x140011fe1  mov     [rbp+var_10], 0
0x140011fe8  mov     edx, ebx; RequestedStringSDRevision
0x140011fea  mov     qword ptr [rsp+60h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x140011fef  lea     r8d, [rbx+4]; SecurityInformation
0x140011ff3  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x140011ff9  test    eax, eax
0x140011ffb  jnz     short loc_14001200E
0x140011ffd  lea     rdx, aFailedConverti; "Failed converting security descriptor t"...
0x140012004  lea     ecx, [rbx+2]
0x140012007  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x14001200c  jmp     short loc_14001203E
0x14001200e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012015  test    rcx, rcx
0x140012018  jz      short loc_140012034
0x14001201a  lea     rax, [rbp+StringSecurityDescriptor]
0x14001201e  mov     r8d, ebx
0x140012021  lea     r9, aKeySecurity; "  Key Security: {}"
0x140012028  mov     qword ptr [rsp+60h+StringSecurityDescriptorLen], rax
0x14001202d  mov     dl, bl
0x14001202f  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140012034  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x140012038  call    cs:__imp_LocalFree
0x14001203e  lea     rcx, [rbp+pSecurityDescriptor]
0x140012042  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x140012047  mov     rcx, [rbp+var_8]
0x14001204b  xor     rcx, rsp; StackCookie
0x14001204e  call    __security_check_cookie
0x140012053  mov     rbx, [rsp+60h+arg_8]
0x140012058  add     rsp, 60h
0x14001205c  pop     rbp
0x14001205d  retn
```
