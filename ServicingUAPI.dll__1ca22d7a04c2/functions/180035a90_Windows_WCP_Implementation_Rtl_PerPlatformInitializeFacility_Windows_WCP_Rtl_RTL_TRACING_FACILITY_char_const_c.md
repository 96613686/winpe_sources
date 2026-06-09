# Windows::WCP::Implementation::Rtl::PerPlatformInitializeFacility(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const)

- ea: `0x180035a90`
- end: `0x180035c5d`
- name: `?PerPlatformInitializeFacility@Rtl@Implementation@WCP@Windows@@YAXPEAU_RTL_TRACING_FACILITY@134@QEBD@Z`
- size: `461`
- prototype: `void(Windows::WCP::Implementation::Rtl *__hidden this, struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *, const char *const)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003086c`

## callees

- `0x1800031d0`
- `0x180003c28`
- `0x18000e098`
- `0x18003547c`
- `0x180035594`
- `0x180035a90`
- `0x18004d970`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180035be0`
- `ntdll!NtQueryValueKey` at `0x180035be0`
- `ntdll!NtOpenKey` at `0x180035ba9`
- `ntdll!NtOpenKey` at `0x180035ba9`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180035b29`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180035b29`
- `ntdll!NtClose` at `0x180035c10`
- `ntdll!NtClose` at `0x180035c10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::WCP::Implementation::Rtl::PerPlatformInitializeFacility(
        Windows::WCP::Implementation::Rtl *this,
        struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *a2,
        const char *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  void *v7; // rcx
  wchar_t *v8[2]; // [rsp+38h] [rbp-49h] BYREF
  __int64 v9; // [rsp+48h] [rbp-39h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-31h] BYREF
  void *KeyHandle; // [rsp+80h] [rbp-1h] BYREF
  ULONG ResultLength; // [rsp+88h] [rbp+7h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+90h] [rbp+Fh] BYREF
  __int128 KeyValueInformation; // [rsp+A0h] [rbp+1Fh] BYREF
  wchar_t *String; // [rsp+B0h] [rbp+2Fh]

  v9 = -2;
  v5 = dword_180243860;
  if ( !dword_180243860 )
  {
    KeyValueInformation = 0;
    String = 0;
    Windows::WCP::Implementation::Rtl::QueryEnvironmentValue<_LUNICODE_STRING>(this, &KeyValueInformation, a3);
    if ( (_QWORD)KeyValueInformation )
      dword_180243860 = o_wcstoul_0(String, 0, 16) & 0xFFFE | 1;
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&KeyValueInformation);
    v5 = dword_180243860;
  }
  *((_DWORD *)this + 3) |= v5;
  Destination = 0;
  if ( RtlCreateUnicodeStringFromAsciiz(&Destination, (PCSZ)a2) )
  {
    *(_OWORD *)v8 = 0;
    Windows::WCP::Implementation::Rtl::QueryEnvironmentValue<_UNICODE_STRING>(&Destination, v8);
    if ( LOWORD(v8[0]) )
    {
      v6 = o_wcstoul_0(v8[1], 0, 16);
    }
    else
    {
      v6 = 0;
      KeyHandle = 0;
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&g_UNICODE_STRING__bslash_Registry_bslash_Machine_bslash_SOFTWARE_bslash_Microsoft_bslash_Windows_bslash_CurrentVersion_bslash_SideBySide_bslash_Tracing;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
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
          v6 = HIDWORD(KeyValueInformation);
        }
      }
      v7 = KeyHandle;
      if ( (char *)KeyHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        KeyHandle = 0;
        NtClose(v7);
      }
    }
    *((_DWORD *)this + 3) |= v6;
    if ( v8[1] )
      anonymous_namespace_::OurRtlFreeStringRoutine(v8[1]);
  }
  if ( Destination.Buffer )
    anonymous_namespace_::OurRtlFreeStringRoutine(Destination.Buffer);
}

```

## disassembly

```asm
0x180035a90  mov     rax, rsp
0x180035a93  push    rbp
0x180035a94  push    rsi
0x180035a95  push    r14
0x180035a97  lea     rbp, [rax-5Fh]
0x180035a9b  sub     rsp, 0C0h
0x180035aa2  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x180035aaa  mov     [rax+18h], rbx
0x180035aae  mov     rax, cs:__security_cookie
0x180035ab5  xor     rax, rsp
0x180035ab8  mov     [rbp+57h+var_20], rax
0x180035abc  mov     rbx, rdx
0x180035abf  mov     rsi, rcx
0x180035ac2  mov     eax, cs:dword_180243860
0x180035ac8  xor     r14d, r14d
0x180035acb  test    eax, eax
0x180035acd  jnz     short loc_180035B18
0x180035acf  xorps   xmm0, xmm0
0x180035ad2  xor     eax, eax
0x180035ad4  movups  [rbp+57h+KeyValueInformation], xmm0
0x180035ad8  mov     [rbp+57h+String], rax
0x180035adc  lea     rdx, [rbp+57h+KeyValueInformation]
0x180035ae0  call    ??$QueryEnvironmentValue@U_LUNICODE_STRING@@@Rtl@Implementation@WCP@Windows@@YAJAEBU_UNICODE_STRING@@PEAV?$Auto@U_LUNICODE_STRING@@@3@@Z; Windows::WCP::Implementation::Rtl::QueryEnvironmentValue<_LUNICODE_STRING>(_UNICODE_STRING const &,Windows::Auto<_LUNICODE_STRING> *)
0x180035ae5  cmp     qword ptr [rbp+57h+KeyValueInformation], r14
0x180035ae9  jz      short loc_180035B08
0x180035aeb  xor     edx, edx; EndPtr
0x180035aed  lea     r8d, [r14+10h]; Radix
0x180035af1  mov     rcx, [rbp+57h+String]; String
0x180035af5  call    _o_wcstoul_0
0x180035afa  and     eax, 0FFFEh
0x180035aff  or      eax, 1
0x180035b02  mov     cs:dword_180243860, eax
0x180035b08  lea     rcx, [rbp+57h+KeyValueInformation]
0x180035b0c  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180035b11  nop
0x180035b12  mov     eax, cs:dword_180243860
0x180035b18  or      [rsi+0Ch], eax
0x180035b1b  xorps   xmm0, xmm0
0x180035b1e  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x180035b22  mov     rdx, rbx; Source
0x180035b25  lea     rcx, [rbp+57h+Destination]; Destination
0x180035b29  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x180035b30  nop     dword ptr [rax+rax+00h]
0x180035b35  test    al, al
0x180035b37  jz      loc_180035C2E
0x180035b3d  xorps   xmm0, xmm0
0x180035b40  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x180035b44  lea     rdx, [rbp+57h+var_A0]
0x180035b48  lea     rcx, [rbp+57h+Destination]
0x180035b4c  call    ??$QueryEnvironmentValue@U_UNICODE_STRING@@@Rtl@Implementation@WCP@Windows@@YAJAEBU_UNICODE_STRING@@PEAV?$Auto@U_UNICODE_STRING@@@3@@Z; Windows::WCP::Implementation::Rtl::QueryEnvironmentValue<_UNICODE_STRING>(_UNICODE_STRING const &,Windows::Auto<_UNICODE_STRING> *)
0x180035b51  cmp     word ptr [rbp+57h+var_A0], r14w
0x180035b56  jz      short loc_180035B6E
0x180035b58  xor     edx, edx; EndPtr
0x180035b5a  lea     r8d, [rdx+10h]; Radix
0x180035b5e  mov     rcx, [rbp+57h+var_A0+8]; String
0x180035b62  call    _o_wcstoul_0
0x180035b67  mov     ebx, eax
0x180035b69  jmp     loc_180035C1C
0x180035b6e  mov     ebx, r14d
0x180035b71  mov     [rbp+57h+KeyHandle], r14
0x180035b75  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180035b7d  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180035b85  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x180035b89  lea     rax, g_UNICODE_STRING__bslash_Registry_bslash_Machine_bslash_SOFTWARE_bslash_Microsoft_bslash_Windows_bslash_CurrentVersion_bslash_SideBySide_bslash_Tracing
0x180035b90  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180035b94  xorps   xmm0, xmm0
0x180035b97  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180035b9c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180035ba0  mov     edx, 101h; DesiredAccess
0x180035ba5  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180035ba9  call    cs:__imp_NtOpenKey
0x180035bb0  nop     dword ptr [rax+rax+00h]
0x180035bb5  test    eax, eax
0x180035bb7  jnz     short loc_180035BFE
0x180035bb9  mov     [rbp+57h+ResultLength], r14d
0x180035bbd  lea     rax, [rbp+57h+ResultLength]
0x180035bc1  mov     [rsp+28h], rax; ResultLength
0x180035bc6  mov     [rsp+0D0h+Length], 14h; Length
0x180035bce  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180035bd2  mov     r8d, 2; KeyValueInformationClass
0x180035bd8  lea     rdx, [rbp+57h+Destination]; ValueName
0x180035bdc  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180035be0  call    cs:__imp_NtQueryValueKey
0x180035be7  nop     dword ptr [rax+rax+00h]
0x180035bec  test    eax, eax
0x180035bee  js      short loc_180035BFE
0x180035bf0  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x180035bf4  jnz     short loc_180035BFE
0x180035bf6  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x180035bfa  cmovz   ebx, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x180035bfe  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180035c02  lea     rax, [rcx-1]
0x180035c06  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180035c0a  ja      short loc_180035C1C
0x180035c0c  mov     [rbp+57h+KeyHandle], r14
0x180035c10  call    cs:__imp_NtClose
0x180035c17  nop     dword ptr [rax+rax+00h]
0x180035c1c  or      [rsi+0Ch], ebx
0x180035c1f  cmp     [rbp+57h+var_A0+8], r14
0x180035c23  jz      short loc_180035C2E
0x180035c25  mov     rcx, [rbp+57h+var_A0+8]
0x180035c29  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180035c2e  mov     rcx, [rbp+57h+Destination.Buffer]
0x180035c32  test    rcx, rcx
0x180035c35  jz      short loc_180035C3C
0x180035c37  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180035c3c  mov     rcx, [rbp+57h+var_20]
0x180035c40  xor     rcx, rsp; StackCookie
0x180035c43  call    __security_check_cookie
0x180035c48  mov     rbx, [rsp+0D0h+arg_10]
0x180035c50  add     rsp, 0C0h
0x180035c57  pop     r14
0x180035c59  pop     rsi
0x180035c5a  pop     rbp
0x180035c5b  retn
```
