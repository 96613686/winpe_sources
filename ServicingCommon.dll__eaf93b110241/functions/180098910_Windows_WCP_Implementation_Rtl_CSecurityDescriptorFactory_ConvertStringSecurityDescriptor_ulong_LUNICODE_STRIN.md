# Windows::WCP::Implementation::Rtl::CSecurityDescriptorFactory::ConvertStringSecurityDescriptor(ulong,_LUNICODE_STRING const &,Windows::Auto<_SECURITY_DESCRIPTOR> *,ulong *)

- ea: `0x180098910`
- end: `0x180098aff`
- name: `?ConvertStringSecurityDescriptor@CSecurityDescriptorFactory@Rtl@Implementation@WCP@Windows@@QEBAJKAEBU_LUNICODE_STRING@@PEAV?$Auto@U_SECURITY_DESCRIPTOR@@@5@PEAK@Z`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180098708`

## callees

- `0x180002564`
- `0x18001f6c0`
- `0x18001fd10`
- `0x1800293a0`
- `0x18006b844`
- `0x18006c994`
- `0x18007e720`
- `0x1800987ec`
- `0x1800988a0`
- `0x180098910`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800989be`
- `KERNEL32!GetLastError` at `0x180098a1c`
- `KERNEL32!GetLastError` at `0x1800989be`
- `KERNEL32!GetLastError` at `0x180098a1c`
- `KERNEL32!LocalFree` at `0x180098a67`
- `KERNEL32!LocalFree` at `0x180098ab8`
- `KERNEL32!LocalFree` at `0x180098a67`
- `KERNEL32!LocalFree` at `0x180098ab8`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800989a5`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800989a5`

## string_xrefs

- `0x1800989e6`: `Windows::WCP::Implementation::Rtl::CSecurityDescriptorFactory::ConvertStringSecurityDescriptor`

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
                           &g_LUNICODE_STRING__lparen_inherit_rparen_,
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
          {
            INTERNAL_ERROR_ACTION(-1073741595);
            JUMPOUT(0x180098AFELL);
          }
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
0x180098910  mov     [rsp-18h+arg_0], rbx
0x180098915  push    rbp
0x180098916  push    rsi
0x180098917  push    rdi
0x180098918  mov     rbp, rsp
0x18009891b  sub     rsp, 70h
0x18009891f  mov     rax, cs:__security_cookie
0x180098926  xor     rax, rsp
0x180098929  mov     [rbp+var_8], rax
0x18009892d  mov     rdx, r8
0x180098930  mov     [rbp+var_24], 0
0x180098937  lea     rcx, g_LUNICODE_STRING__lparen_inherit_rparen_
0x18009893e  mov     rdi, r9
0x180098941  mov     rsi, r8
0x180098944  call    ??$AreStringsEqualByOrdinal@U_LUNICODE_STRING@@U1@@StringUtil@Windows@@YA_NAEBU_LUNICODE_STRING@@0@Z; Windows::StringUtil::AreStringsEqualByOrdinal<_LUNICODE_STRING,_LUNICODE_STRING>(_LUNICODE_STRING const &,_LUNICODE_STRING const &)
0x180098949  test    al, al
0x18009894b  jz      short loc_18009895A
0x18009894d  mov     rcx, rdi
0x180098950  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x180098955  jmp     loc_180098AD5
0x18009895a  xor     eax, eax
0x18009895c  lea     rdx, [rbp+var_50]
0x180098960  mov     [rbp+StringSecurityDescriptor], rax
0x180098964  xorps   xmm0, xmm0
0x180098967  lea     rax, [rbp+var_20]
0x18009896b  mov     rcx, rsi
0x18009896e  mov     [rbp+var_50], rax
0x180098972  movups  [rbp+var_20], xmm0
0x180098976  call    ??$DuplicateToNullTerminatedString@U_LUNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Windows@@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::DuplicateToNullTerminatedString<_LUNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(_LUNICODE_STRING const &,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>)
0x18009897b  mov     ebx, eax
0x18009897d  test    eax, eax
0x18009897f  js      loc_180098A7B
0x180098985  mov     rcx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x180098989  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x18009898d  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180098991  mov     [rbp+SecurityDescriptor], 0
0x180098999  mov     edx, 1; StringSDRevision
0x18009899e  mov     [rbp+SecurityDescriptorSize], 0
0x1800989a5  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800989ac  nop     dword ptr [rax+rax+00h]
0x1800989b1  cmp     eax, 1
0x1800989b4  jz      short loc_180098A32
0x1800989b6  mov     r9, rsi
0x1800989b9  call    ??$RtlAutoTrace@U_LUNICODE_STRING@@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@012@QEBDAEBU_LUNICODE_STRING@@@Z; Windows::WCP::Rtl::RtlAutoTrace<_LUNICODE_STRING>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,_LUNICODE_STRING const &)
0x1800989be  call    cs:__imp_GetLastError
0x1800989c5  nop     dword ptr [rax+rax+00h]
0x1800989ca  test    eax, eax
0x1800989cc  jnz     short loc_180098A1C
0x1800989ce  mov     eax, 36FDh
0x1800989d3  mov     [rbp+var_40], 7Ch ; '|'
0x1800989db  lea     rcx, aOnecoreBaseWcp_22; "onecore\\base\\wcp\\library\\sddlparse."...
0x1800989e2  mov     [rbp+var_50], rcx
0x1800989e6  lea     rcx, aWindowsWcpImpl_5; "Windows::WCP::Implementation::Rtl::CSec"...
0x1800989ed  mov     [rbp+var_48], rcx
0x1800989f1  lea     rcx, aGetlasterror; "GetLastError"
0x1800989f8  mov     [rbp+var_38], rcx
0x1800989fc  test    eax, eax
0x1800989fe  jle     short loc_180098A08
0x180098a00  movzx   eax, ax
0x180098a03  or      eax, 80070000h
0x180098a08  mov     r8d, eax
0x180098a0b  lea     rdx, [rbp+var_50]
0x180098a0f  lea     rcx, [rbp+var_24]
0x180098a13  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180098a18  mov     ebx, eax
0x180098a1a  jmp     short loc_180098A5E
0x180098a1c  call    cs:__imp_GetLastError
0x180098a23  nop     dword ptr [rax+rax+00h]
0x180098a28  test    eax, eax
0x180098a2a  jz      loc_180098AF4
0x180098a30  jmp     short loc_1800989D3
0x180098a32  mov     rdx, [rbp+SecurityDescriptor]
0x180098a36  lea     rcx, [rbp+var_50]
0x180098a3a  mov     [rbp+var_50], 0
0x180098a42  mov     [rbp+var_48], 0
0x180098a4a  call    ?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z; Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)
0x180098a4f  mov     ebx, eax
0x180098a51  test    eax, eax
0x180098a53  jns     short loc_180098A88
0x180098a55  lea     rcx, [rbp+var_50]
0x180098a59  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x180098a5e  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180098a62  test    rcx, rcx
0x180098a65  jz      short loc_180098A7B
0x180098a67  call    cs:__imp_LocalFree
0x180098a6e  nop     dword ptr [rax+rax+00h]
0x180098a73  mov     [rbp+SecurityDescriptor], 0
0x180098a7b  lea     rcx, [rbp+var_20]
0x180098a7f  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180098a84  mov     eax, ebx
0x180098a86  jmp     short loc_180098AD7
0x180098a88  mov     rcx, [rbp+var_50]
0x180098a8c  mov     rax, [rdi]
0x180098a8f  mov     [rdi], rcx
0x180098a92  mov     rcx, [rbp+var_48]
0x180098a96  mov     [rbp+var_50], rax
0x180098a9a  mov     rax, [rdi+8]
0x180098a9e  mov     [rdi+8], rcx
0x180098aa2  lea     rcx, [rbp+var_50]
0x180098aa6  mov     [rbp+var_48], rax
0x180098aaa  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x180098aaf  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180098ab3  test    rcx, rcx
0x180098ab6  jz      short loc_180098ACC
0x180098ab8  call    cs:__imp_LocalFree
0x180098abf  nop     dword ptr [rax+rax+00h]
0x180098ac4  mov     [rbp+SecurityDescriptor], 0
0x180098acc  lea     rcx, [rbp+var_20]
0x180098ad0  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180098ad5  xor     eax, eax
0x180098ad7  mov     rcx, [rbp+var_8]
0x180098adb  xor     rcx, rsp; StackCookie
0x180098ade  call    __security_check_cookie
0x180098ae3  mov     rbx, [rsp+70h+arg_0]
0x180098aeb  add     rsp, 70h
0x180098aef  pop     rdi
0x180098af0  pop     rsi
0x180098af1  pop     rbp
0x180098af2  retn
0x180098af4  mov     ecx, 0C00000E5h; int
0x180098af9  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
