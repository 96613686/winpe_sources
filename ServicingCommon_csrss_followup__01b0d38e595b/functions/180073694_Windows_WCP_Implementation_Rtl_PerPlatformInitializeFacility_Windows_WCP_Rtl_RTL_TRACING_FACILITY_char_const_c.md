# Windows::WCP::Implementation::Rtl::PerPlatformInitializeFacility(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const)

- ea: `0x180073694`
- end: `0x180073831`
- name: `?PerPlatformInitializeFacility@Rtl@Implementation@WCP@Windows@@YAXPEAU_RTL_TRACING_FACILITY@134@QEBD@Z`
- size: `413`
- prototype: `void(Windows::WCP::Implementation::Rtl *__hidden this, struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *, const char *const)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006eaec`

## callees

- `0x180004a8c`
- `0x1800278d0`
- `0x18002d2b0`
- `0x18006930c`
- `0x1800730dc`
- `0x180073204`
- `0x18007334c`
- `0x180073694`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18007379f`
- `ntdll!NtOpenKey` at `0x18007379f`
- `ntdll!NtQueryValueKey` at `0x1800737d5`
- `ntdll!NtQueryValueKey` at `0x1800737d5`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180073721`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180073721`

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

  v3 = dword_1800D2D30;
  if ( !dword_1800D2D30 )
  {
    KeyValueInformation = 0;
    String = 0;
    RtlSystemUtil::QueryNullTerminatedEnvironmentValue<_UNICODE_STRING,Windows::Auto<_LUNICODE_STRING> *>(
      this,
      a2,
      &KeyValueInformation);
    if ( (_QWORD)KeyValueInformation )
      dword_1800D2D30 = wcstoul(String, 0, 16) & 0xFFFE | 1;
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&KeyValueInformation);
    v3 = dword_1800D2D30;
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
0x180073694  mov     [rsp-8+arg_10], rbx
0x180073699  push    rbp
0x18007369a  push    rsi
0x18007369b  push    rdi
0x18007369c  lea     rbp, [rsp-47h]
0x1800736a1  sub     rsp, 0B0h
0x1800736a8  mov     rax, cs:__security_cookie
0x1800736af  xor     rax, rsp
0x1800736b2  mov     [rbp+57h+var_18], rax
0x1800736b6  mov     eax, cs:dword_1800D2D30
0x1800736bc  xor     esi, esi
0x1800736be  mov     rbx, rdx
0x1800736c1  mov     rdi, rcx
0x1800736c4  test    eax, eax
0x1800736c6  jnz     short loc_180073710
0x1800736c8  xorps   xmm0, xmm0
0x1800736cb  lea     r8, [rbp+57h+KeyValueInformation]
0x1800736cf  xor     eax, eax
0x1800736d1  movups  [rbp+57h+KeyValueInformation], xmm0
0x1800736d5  mov     [rbp+57h+String], rax
0x1800736d9  call    ??$QueryNullTerminatedEnvironmentValue@U_UNICODE_STRING@@PEAV?$Auto@U_LUNICODE_STRING@@@Windows@@@RtlSystemUtil@@YAJPEAXAEBU_UNICODE_STRING@@PEAV?$Auto@U_LUNICODE_STRING@@@Windows@@@Z; RtlSystemUtil::QueryNullTerminatedEnvironmentValue<_UNICODE_STRING,Windows::Auto<_LUNICODE_STRING> *>(void *,_UNICODE_STRING const &,Windows::Auto<_LUNICODE_STRING> *)
0x1800736de  cmp     qword ptr [rbp+57h+KeyValueInformation], rsi
0x1800736e2  jz      short loc_180073701
0x1800736e4  mov     rcx, [rbp+57h+String]; String
0x1800736e8  lea     r8d, [rsi+10h]; Radix
0x1800736ec  xor     edx, edx; EndPtr
0x1800736ee  call    wcstoul
0x1800736f3  and     eax, 0FFFEh
0x1800736f8  or      eax, 1
0x1800736fb  mov     cs:dword_1800D2D30, eax
0x180073701  lea     rcx, [rbp+57h+KeyValueInformation]
0x180073705  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18007370a  mov     eax, cs:dword_1800D2D30
0x180073710  or      [rdi+0Ch], eax
0x180073713  lea     rcx, [rbp+57h+Destination]; Destination
0x180073717  xorps   xmm0, xmm0
0x18007371a  mov     rdx, rbx; Source
0x18007371d  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x180073721  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x180073728  nop     dword ptr [rax+rax+00h]
0x18007372d  test    al, al
0x18007372f  jz      loc_180073808
0x180073735  xorps   xmm0, xmm0
0x180073738  lea     r8, [rbp+57h+var_90]
0x18007373c  lea     rdx, [rbp+57h+Destination]
0x180073740  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x180073744  call    ??$QueryNullTerminatedEnvironmentValue@U_UNICODE_STRING@@PEAV?$Auto@U_UNICODE_STRING@@@Windows@@@RtlSystemUtil@@YAJPEAXAEBU_UNICODE_STRING@@PEAV?$Auto@U_UNICODE_STRING@@@Windows@@@Z; RtlSystemUtil::QueryNullTerminatedEnvironmentValue<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING> *>(void *,_UNICODE_STRING const &,Windows::Auto<_UNICODE_STRING> *)
0x180073749  cmp     word ptr [rbp+57h+var_90], si
0x18007374d  jz      short loc_180073765
0x18007374f  mov     rcx, [rbp+57h+var_90+8]; String
0x180073753  xor     edx, edx; EndPtr
0x180073755  lea     r8d, [rdx+10h]; Radix
0x180073759  call    wcstoul
0x18007375e  mov     ebx, eax
0x180073760  jmp     loc_1800737FC
0x180073765  lea     rax, g_UNICODE_STRING__bslash_Registry_bslash_Machine_bslash_SOFTWARE_bslash_Microsoft_bslash_Windows_bslash_CurrentVersion_bslash_SideBySide_bslash_Tracing
0x18007376c  mov     [rbp+57h+KeyHandle], rsi
0x180073770  xorps   xmm0, xmm0
0x180073773  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180073777  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18007377b  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180073783  mov     edx, 101h; DesiredAccess
0x180073788  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180073790  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180073794  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x180073798  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007379d  mov     ebx, esi
0x18007379f  call    cs:__imp_NtOpenKey
0x1800737a6  nop     dword ptr [rax+rax+00h]
0x1800737ab  test    eax, eax
0x1800737ad  jnz     short loc_1800737F3
0x1800737af  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800737b3  lea     rax, [rbp+57h+var_50]
0x1800737b7  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x1800737bc  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800737c0  mov     r8d, 2; KeyValueInformationClass
0x1800737c6  mov     [rsp+0C0h+Length], 14h; Length
0x1800737ce  lea     rdx, [rbp+57h+Destination]; ValueName
0x1800737d2  mov     [rbp+57h+var_50], esi
0x1800737d5  call    cs:__imp_NtQueryValueKey
0x1800737dc  nop     dword ptr [rax+rax+00h]
0x1800737e1  test    eax, eax
0x1800737e3  js      short loc_1800737F3
0x1800737e5  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x1800737e9  jnz     short loc_1800737F3
0x1800737eb  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x1800737ef  cmovz   ebx, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x1800737f3  lea     rcx, [rbp+57h+KeyHandle]
0x1800737f7  call    ??1?$Auto@PEAX@Windows@@QEAA@XZ; Windows::Auto<void *>::~Auto<void *>(void)
0x1800737fc  or      [rdi+0Ch], ebx
0x1800737ff  lea     rcx, [rbp+57h+var_90]
0x180073803  call    ?Close@?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(void)
0x180073808  lea     rcx, [rbp+57h+Destination]
0x18007380c  call    ?Close@?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(void)
0x180073811  mov     rcx, [rbp+57h+var_18]
0x180073815  xor     rcx, rsp; StackCookie
0x180073818  call    __security_check_cookie
0x18007381d  mov     rbx, [rsp+0C0h+arg_10]
0x180073825  add     rsp, 0B0h
0x18007382c  pop     rdi
0x18007382d  pop     rsi
0x18007382e  pop     rbp
0x18007382f  retn
```
