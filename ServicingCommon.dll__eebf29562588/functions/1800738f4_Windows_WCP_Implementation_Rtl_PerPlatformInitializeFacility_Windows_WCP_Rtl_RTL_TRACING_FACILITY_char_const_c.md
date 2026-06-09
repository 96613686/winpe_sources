# Windows::WCP::Implementation::Rtl::PerPlatformInitializeFacility(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const)

- ea: `0x1800738f4`
- end: `0x180073a91`
- name: `?PerPlatformInitializeFacility@Rtl@Implementation@WCP@Windows@@YAXPEAU_RTL_TRACING_FACILITY@134@QEBD@Z`
- size: `413`
- prototype: `void(Windows::WCP::Implementation::Rtl *__hidden this, struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *, const char *const)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006ed1c`

## callees

- `0x180002564`
- `0x1800239c0`
- `0x1800293a0`
- `0x180068edc`
- `0x18007333c`
- `0x180073464`
- `0x1800735ac`
- `0x1800738f4`

## import_xrefs

- `ntdll!NtOpenKey` at `0x1800739ff`
- `ntdll!NtOpenKey` at `0x1800739ff`
- `ntdll!NtQueryValueKey` at `0x180073a35`
- `ntdll!NtQueryValueKey` at `0x180073a35`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180073981`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180073981`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::PerPlatformInitializeFacility(
        Windows::WCP::Implementation::Rtl *this,
        struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *a2,
        const char *const a3)
{
  int v3; // eax
  __int64 v6; // rcx
  unsigned int v7; // ebx
  wchar_t *v8[2]; // [rsp+30h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-29h] BYREF
  ULONG ResultLength; // [rsp+70h] [rbp+7h] BYREF
  void *KeyHandle; // [rsp+78h] [rbp+Fh] BYREF
  struct _UNICODE_STRING Destination; // [rsp+80h] [rbp+17h] BYREF
  __int128 KeyValueInformation; // [rsp+90h] [rbp+27h] BYREF
  wchar_t *String; // [rsp+A0h] [rbp+37h]

  v3 = dword_1800D4D20;
  if ( !dword_1800D4D20 )
  {
    KeyValueInformation = 0;
    String = 0;
    RtlSystemUtil::QueryNullTerminatedEnvironmentValue<_UNICODE_STRING,Windows::Auto<_LUNICODE_STRING> *>(
      this,
      a2,
      &KeyValueInformation);
    if ( (_QWORD)KeyValueInformation )
      dword_1800D4D20 = wcstoul(String, 0, 16) & 0xFFFE | 1;
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&KeyValueInformation);
    v3 = dword_1800D4D20;
  }
  *((_DWORD *)this + 3) |= v3;
  Destination = 0;
  if ( RtlCreateUnicodeStringFromAsciiz(&Destination, (PCSZ)a2) )
  {
    *(_OWORD *)v8 = 0;
    RtlSystemUtil::QueryNullTerminatedEnvironmentValue<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING> *>(
      v6,
      &Destination,
      v8);
    if ( LOWORD(v8[0]) )
    {
      v7 = wcstoul(v8[1], 0, 16);
    }
    else
    {
      KeyHandle = 0;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&g_UNICODE_STRING__bslash_Registry_bslash_Machine_bslash_SOFTWARE_bslash_Microsoft_bslash_Windows_bslash_CurrentVersion_bslash_SideBySide_bslash_Tracing;
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      ObjectAttributes.RootDirectory = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v7 = 0;
      if ( !NtOpenKey(&KeyHandle, 0x101u, &ObjectAttributes) )
      {
        ResultLength = 0;
        if ( NtQueryValueKey(
               KeyHandle,
               &Destination,
               KeyValuePartialInformation,
               &KeyValueInformation,
               0x14u,
               &ResultLength) >= 0
          && *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
        {
          v7 = HIDWORD(KeyValueInformation);
        }
      }
      Windows::Auto<void *>::~Auto<void *>(&KeyHandle);
    }
    *((_DWORD *)this + 3) |= v7;
    Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(v8);
  }
  Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&Destination);
}

```

## disassembly

```asm
0x1800738f4  mov     [rsp-8+arg_10], rbx
0x1800738f9  push    rbp
0x1800738fa  push    rsi
0x1800738fb  push    rdi
0x1800738fc  lea     rbp, [rsp-47h]
0x180073901  sub     rsp, 0B0h
0x180073908  mov     rax, cs:__security_cookie
0x18007390f  xor     rax, rsp
0x180073912  mov     [rbp+57h+var_18], rax
0x180073916  mov     eax, cs:dword_1800D4D20
0x18007391c  xor     esi, esi
0x18007391e  mov     rbx, rdx
0x180073921  mov     rdi, rcx
0x180073924  test    eax, eax
0x180073926  jnz     short loc_180073970
0x180073928  xorps   xmm0, xmm0
0x18007392b  lea     r8, [rbp+57h+KeyValueInformation]
0x18007392f  xor     eax, eax
0x180073931  movups  [rbp+57h+KeyValueInformation], xmm0
0x180073935  mov     [rbp+57h+String], rax
0x180073939  call    ??$QueryNullTerminatedEnvironmentValue@U_UNICODE_STRING@@PEAV?$Auto@U_LUNICODE_STRING@@@Windows@@@RtlSystemUtil@@YAJPEAXAEBU_UNICODE_STRING@@PEAV?$Auto@U_LUNICODE_STRING@@@Windows@@@Z; RtlSystemUtil::QueryNullTerminatedEnvironmentValue<_UNICODE_STRING,Windows::Auto<_LUNICODE_STRING> *>(void *,_UNICODE_STRING const &,Windows::Auto<_LUNICODE_STRING> *)
0x18007393e  cmp     qword ptr [rbp+57h+KeyValueInformation], rsi
0x180073942  jz      short loc_180073961
0x180073944  mov     rcx, [rbp+57h+String]; String
0x180073948  lea     r8d, [rsi+10h]; Radix
0x18007394c  xor     edx, edx; EndPtr
0x18007394e  call    wcstoul
0x180073953  and     eax, 0FFFEh
0x180073958  or      eax, 1
0x18007395b  mov     cs:dword_1800D4D20, eax
0x180073961  lea     rcx, [rbp+57h+KeyValueInformation]
0x180073965  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18007396a  mov     eax, cs:dword_1800D4D20
0x180073970  or      [rdi+0Ch], eax
0x180073973  lea     rcx, [rbp+57h+Destination]; Destination
0x180073977  xorps   xmm0, xmm0
0x18007397a  mov     rdx, rbx; Source
0x18007397d  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x180073981  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x180073988  nop     dword ptr [rax+rax+00h]
0x18007398d  test    al, al
0x18007398f  jz      loc_180073A68
0x180073995  xorps   xmm0, xmm0
0x180073998  lea     r8, [rbp+57h+var_90]
0x18007399c  lea     rdx, [rbp+57h+Destination]
0x1800739a0  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x1800739a4  call    ??$QueryNullTerminatedEnvironmentValue@U_UNICODE_STRING@@PEAV?$Auto@U_UNICODE_STRING@@@Windows@@@RtlSystemUtil@@YAJPEAXAEBU_UNICODE_STRING@@PEAV?$Auto@U_UNICODE_STRING@@@Windows@@@Z; RtlSystemUtil::QueryNullTerminatedEnvironmentValue<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING> *>(void *,_UNICODE_STRING const &,Windows::Auto<_UNICODE_STRING> *)
0x1800739a9  cmp     word ptr [rbp+57h+var_90], si
0x1800739ad  jz      short loc_1800739C5
0x1800739af  mov     rcx, [rbp+57h+var_90+8]; String
0x1800739b3  xor     edx, edx; EndPtr
0x1800739b5  lea     r8d, [rdx+10h]; Radix
0x1800739b9  call    wcstoul
0x1800739be  mov     ebx, eax
0x1800739c0  jmp     loc_180073A5C
0x1800739c5  lea     rax, g_UNICODE_STRING__bslash_Registry_bslash_Machine_bslash_SOFTWARE_bslash_Microsoft_bslash_Windows_bslash_CurrentVersion_bslash_SideBySide_bslash_Tracing
0x1800739cc  mov     [rbp+57h+KeyHandle], rsi
0x1800739d0  xorps   xmm0, xmm0
0x1800739d3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800739d7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800739db  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800739e3  mov     edx, 101h; DesiredAccess
0x1800739e8  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800739f0  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800739f4  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x1800739f8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800739fd  mov     ebx, esi
0x1800739ff  call    cs:__imp_NtOpenKey
0x180073a06  nop     dword ptr [rax+rax+00h]
0x180073a0b  test    eax, eax
0x180073a0d  jnz     short loc_180073A53
0x180073a0f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180073a13  lea     rax, [rbp+57h+var_50]
0x180073a17  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x180073a1c  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180073a20  mov     r8d, 2; KeyValueInformationClass
0x180073a26  mov     [rsp+0C0h+Length], 14h; Length
0x180073a2e  lea     rdx, [rbp+57h+Destination]; ValueName
0x180073a32  mov     [rbp+57h+var_50], esi
0x180073a35  call    cs:__imp_NtQueryValueKey
0x180073a3c  nop     dword ptr [rax+rax+00h]
0x180073a41  test    eax, eax
0x180073a43  js      short loc_180073A53
0x180073a45  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x180073a49  jnz     short loc_180073A53
0x180073a4b  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x180073a4f  cmovz   ebx, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x180073a53  lea     rcx, [rbp+57h+KeyHandle]
0x180073a57  call    ??1?$Auto@PEAX@Windows@@QEAA@XZ; Windows::Auto<void *>::~Auto<void *>(void)
0x180073a5c  or      [rdi+0Ch], ebx
0x180073a5f  lea     rcx, [rbp+57h+var_90]
0x180073a63  call    ?Close@?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(void)
0x180073a68  lea     rcx, [rbp+57h+Destination]
0x180073a6c  call    ?Close@?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(void)
0x180073a71  mov     rcx, [rbp+57h+var_18]
0x180073a75  xor     rcx, rsp; StackCookie
0x180073a78  call    __security_check_cookie
0x180073a7d  mov     rbx, [rsp+0C0h+arg_10]
0x180073a85  add     rsp, 0B0h
0x180073a8c  pop     rdi
0x180073a8d  pop     rsi
0x180073a8e  pop     rbp
0x180073a8f  retn
```
