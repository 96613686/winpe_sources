# Windows::WCP::Implementation::Rtl::CSecurityDescriptorFactory::ConvertStringSecurityDescriptor(ulong,_LUNICODE_STRING const &,Windows::Auto<_SECURITY_DESCRIPTOR> *,ulong *)

- ea: `0x180096a60`
- end: `0x180096c54`
- name: `?ConvertStringSecurityDescriptor@CSecurityDescriptorFactory@Rtl@Implementation@WCP@Windows@@QEBAJKAEBU_LUNICODE_STRING@@PEAV?$Auto@U_SECURITY_DESCRIPTOR@@@5@PEAK@Z`
- size: `500`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180096860`

## callees

- `0x180004a8c`
- `0x180021878`
- `0x18002d2b0`
- `0x18006ba4c`
- `0x18006c87c`
- `0x18007d794`
- `0x18009693c`
- `0x1800969f0`
- `0x180096a60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180096b12`
- `KERNEL32!GetLastError` at `0x180096b70`
- `KERNEL32!GetLastError` at `0x180096b12`
- `KERNEL32!GetLastError` at `0x180096b70`
- `KERNEL32!LocalFree` at `0x180096bc7`
- `KERNEL32!LocalFree` at `0x180096c18`
- `KERNEL32!LocalFree` at `0x180096bc7`
- `KERNEL32!LocalFree` at `0x180096c18`
- `ntdll!RtlRaiseStatus` at `0x180096b85`
- `ntdll!RtlRaiseStatus` at `0x180096b85`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180096af5`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180096af5`

## string_xrefs

- `0x180096b3a`: `Windows::WCP::Implementation::Rtl::CSecurityDescriptorFactory::ConvertStringSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::CSecurityDescriptorFactory::ConvertStringSecurityDescriptor(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char **a4)
{
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  signed int LastError; // eax
  const char *v12; // rax
  const char *v13; // rax
  const char *v14; // [rsp+20h] [rbp-50h] BYREF
  const char *v15; // [rsp+28h] [rbp-48h]
  __int64 v16; // [rsp+30h] [rbp-40h]
  const char *v17; // [rsp+38h] [rbp-38h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-30h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+48h] [rbp-28h] BYREF
  int v20; // [rsp+4Ch] [rbp-24h] BYREF
  __int128 v21; // [rsp+50h] [rbp-20h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+60h] [rbp-10h]

  v20 = 0;
  if ( !(unsigned __int8)Windows::StringUtil::AreStringsEqualByOrdinal<_LUNICODE_STRING,_LUNICODE_STRING>(
                           g_LUNICODE_STRING__lparen_inherit_rparen_,
                           a3) )
  {
    StringSecurityDescriptor = 0;
    v14 = (const char *)&v21;
    v21 = 0;
    v6 = Windows::StringUtil::Rtl::DuplicateToNullTerminatedString<_LUNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(
           a3,
           &v14);
    if ( v6 >= 0 )
    {
      SecurityDescriptor = 0;
      SecurityDescriptorSize = 0;
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
             StringSecurityDescriptor,
             1u,
             &SecurityDescriptor,
             &SecurityDescriptorSize) )
      {
        v14 = 0;
        v15 = 0;
        v6 = Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(&v14, SecurityDescriptor);
        if ( v6 >= 0 )
        {
          v12 = *a4;
          *a4 = v14;
          v14 = v12;
          v13 = a4[1];
          a4[1] = v15;
          v15 = v13;
          Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v14);
          if ( SecurityDescriptor )
          {
            LocalFree(SecurityDescriptor);
            SecurityDescriptor = 0;
          }
          Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v21);
          return 0;
        }
        Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v14);
      }
      else
      {
        Windows::WCP::Rtl::RtlAutoTrace<_LUNICODE_STRING>(v8, v7, v9, a3);
        if ( GetLastError() )
        {
          LastError = GetLastError();
          if ( !LastError )
            RtlRaiseStatus(-1073741595);
        }
        else
        {
          LastError = 14077;
        }
        v16 = 124;
        v14 = "onecore\\base\\wcp\\library\\sddlparse.cpp";
        v15 = "Windows::WCP::Implementation::Rtl::CSecurityDescriptorFactory::ConvertStringSecurityDescriptor";
        v17 = "GetLastError";
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v6 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
               &v20,
               &v14,
               (unsigned int)LastError);
      }
      if ( SecurityDescriptor )
      {
        LocalFree(SecurityDescriptor);
        SecurityDescriptor = 0;
      }
    }
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v21);
    return (unsigned int)v6;
  }
  Windows::Auto<_SECURITY_DESCRIPTOR>::Close(a4);
  return 0;
}

```

## disassembly

```asm
0x180096a60  mov     [rsp-18h+arg_0], rbx
0x180096a65  push    rbp
0x180096a66  push    rsi
0x180096a67  push    rdi
0x180096a68  mov     rbp, rsp
0x180096a6b  sub     rsp, 70h
0x180096a6f  mov     rax, cs:__security_cookie
0x180096a76  xor     rax, rsp
0x180096a79  mov     [rbp+var_8], rax
0x180096a7d  mov     rdx, r8
0x180096a80  mov     [rbp+var_24], 0
0x180096a87  lea     rcx, g_LUNICODE_STRING__lparen_inherit_rparen_
0x180096a8e  mov     rdi, r9
0x180096a91  mov     rsi, r8
0x180096a94  call    ??$AreStringsEqualByOrdinal@U_LUNICODE_STRING@@U1@@StringUtil@Windows@@YA_NAEBU_LUNICODE_STRING@@0@Z; Windows::StringUtil::AreStringsEqualByOrdinal<_LUNICODE_STRING,_LUNICODE_STRING>(_LUNICODE_STRING const &,_LUNICODE_STRING const &)
0x180096a99  test    al, al
0x180096a9b  jz      short loc_180096AAA
0x180096a9d  mov     rcx, rdi
0x180096aa0  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x180096aa5  jmp     loc_180096C35
0x180096aaa  xor     eax, eax
0x180096aac  lea     rdx, [rbp+var_50]
0x180096ab0  mov     [rbp+StringSecurityDescriptor], rax
0x180096ab4  xorps   xmm0, xmm0
0x180096ab7  lea     rax, [rbp+var_20]
0x180096abb  mov     rcx, rsi
0x180096abe  mov     [rbp+var_50], rax
0x180096ac2  movups  [rbp+var_20], xmm0
0x180096ac6  call    ??$DuplicateToNullTerminatedString@U_LUNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Windows@@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::DuplicateToNullTerminatedString<_LUNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(_LUNICODE_STRING const &,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>)
0x180096acb  mov     ebx, eax
0x180096acd  test    eax, eax
0x180096acf  js      loc_180096BDB
0x180096ad5  mov     rcx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x180096ad9  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x180096add  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180096ae1  mov     [rbp+SecurityDescriptor], 0
0x180096ae9  mov     edx, 1; StringSDRevision
0x180096aee  mov     [rbp+SecurityDescriptorSize], 0
0x180096af5  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180096afc  nop     dword ptr [rax+rax+00h]
0x180096b01  cmp     eax, 1
0x180096b04  jz      loc_180096B92
0x180096b0a  mov     r9, rsi
0x180096b0d  call    ??$RtlAutoTrace@U_LUNICODE_STRING@@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@012@QEBDAEBU_LUNICODE_STRING@@@Z; Windows::WCP::Rtl::RtlAutoTrace<_LUNICODE_STRING>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,_LUNICODE_STRING const &)
0x180096b12  call    cs:__imp_GetLastError
0x180096b19  nop     dword ptr [rax+rax+00h]
0x180096b1e  test    eax, eax
0x180096b20  jnz     short loc_180096B70
0x180096b22  mov     eax, 36FDh
0x180096b27  mov     [rbp+var_40], 7Ch ; '|'
0x180096b2f  lea     rcx, aOnecoreBaseWcp_22; "onecore\\base\\wcp\\library\\sddlparse."...
0x180096b36  mov     [rbp+var_50], rcx
0x180096b3a  lea     rcx, aWindowsWcpImpl_5; "Windows::WCP::Implementation::Rtl::CSec"...
0x180096b41  mov     [rbp+var_48], rcx
0x180096b45  lea     rcx, aGetlasterror; "GetLastError"
0x180096b4c  mov     [rbp+var_38], rcx
0x180096b50  test    eax, eax
0x180096b52  jle     short loc_180096B5C
0x180096b54  movzx   eax, ax
0x180096b57  or      eax, 80070000h
0x180096b5c  mov     r8d, eax
0x180096b5f  lea     rdx, [rbp+var_50]
0x180096b63  lea     rcx, [rbp+var_24]
0x180096b67  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180096b6c  mov     ebx, eax
0x180096b6e  jmp     short loc_180096BBE
0x180096b70  call    cs:__imp_GetLastError
0x180096b77  nop     dword ptr [rax+rax+00h]
0x180096b7c  test    eax, eax
0x180096b7e  jnz     short loc_180096B27
0x180096b80  mov     ecx, 0C00000E5h; Status
0x180096b85  call    cs:__imp_RtlRaiseStatus
0x180096b8c  nop     dword ptr [rax+rax+00h]
0x180096b91  int     3; Trap to Debugger
0x180096b92  mov     rdx, [rbp+SecurityDescriptor]
0x180096b96  lea     rcx, [rbp+var_50]
0x180096b9a  mov     [rbp+var_50], 0
0x180096ba2  mov     [rbp+var_48], 0
0x180096baa  call    ?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z; Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)
0x180096baf  mov     ebx, eax
0x180096bb1  test    eax, eax
0x180096bb3  jns     short loc_180096BE8
0x180096bb5  lea     rcx, [rbp+var_50]
0x180096bb9  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x180096bbe  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180096bc2  test    rcx, rcx
0x180096bc5  jz      short loc_180096BDB
0x180096bc7  call    cs:__imp_LocalFree
0x180096bce  nop     dword ptr [rax+rax+00h]
0x180096bd3  mov     [rbp+SecurityDescriptor], 0
0x180096bdb  lea     rcx, [rbp+var_20]
0x180096bdf  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180096be4  mov     eax, ebx
0x180096be6  jmp     short loc_180096C37
0x180096be8  mov     rcx, [rbp+var_50]
0x180096bec  mov     rax, [rdi]
0x180096bef  mov     [rdi], rcx
0x180096bf2  mov     rcx, [rbp+var_48]
0x180096bf6  mov     [rbp+var_50], rax
0x180096bfa  mov     rax, [rdi+8]
0x180096bfe  mov     [rdi+8], rcx
0x180096c02  lea     rcx, [rbp+var_50]
0x180096c06  mov     [rbp+var_48], rax
0x180096c0a  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x180096c0f  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180096c13  test    rcx, rcx
0x180096c16  jz      short loc_180096C2C
0x180096c18  call    cs:__imp_LocalFree
0x180096c1f  nop     dword ptr [rax+rax+00h]
0x180096c24  mov     [rbp+SecurityDescriptor], 0
0x180096c2c  lea     rcx, [rbp+var_20]
0x180096c30  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180096c35  xor     eax, eax
0x180096c37  mov     rcx, [rbp+var_8]
0x180096c3b  xor     rcx, rsp; StackCookie
0x180096c3e  call    __security_check_cookie
0x180096c43  mov     rbx, [rsp+70h+arg_0]
0x180096c4b  add     rsp, 70h
0x180096c4f  pop     rdi
0x180096c50  pop     rsi
0x180096c51  pop     rbp
0x180096c52  retn
```
