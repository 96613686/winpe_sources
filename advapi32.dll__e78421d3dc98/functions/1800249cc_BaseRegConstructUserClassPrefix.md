# BaseRegConstructUserClassPrefix

- ea: `0x1800249cc`
- end: `0x180024a73`
- name: `BaseRegConstructUserClassPrefix`
- size: `167`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180024248`

## callees

- `0x1800249cc`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x180024a1b`
- `ntdll!RtlCopyUnicodeString` at `0x180024a4c`
- `ntdll!RtlCopyUnicodeString` at `0x180024a1b`
- `ntdll!RtlCopyUnicodeString` at `0x180024a4c`
- `ntdll!RtlAppendUnicodeToString` at `0x180024a67`
- `ntdll!RtlAppendUnicodeToString` at `0x180024a67`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180024a29`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180024a29`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180024a3a`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180024a3a`
- `ntdll!RtlInitUnicodeStringEx` at `0x180024a0d`
- `ntdll!RtlInitUnicodeStringEx` at `0x180024a0d`
- `ntdll!RtlFreeUnicodeString` at `0x180024a57`
- `ntdll!RtlFreeUnicodeString` at `0x180024a57`

## string_xrefs

- `0x1800249eb`: `\Registry\User`

## pseudocode

```c
int __fastcall BaseRegConstructUserClassPrefix(__int64 a1, struct _UNICODE_STRING *a2)
{
  bool v2; // zf
  int result; // eax
  UNICODE_STRING Source; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  v2 = (*(_BYTE *)a1 & 1) == 0;
  DestinationString = 0;
  Source = 0;
  if ( v2 )
  {
    result = RtlFormatCurrentUserKeyPath(&Source);
    if ( result < 0 )
      return result;
    RtlCopyUnicodeString(a2, &Source);
    RtlFreeUnicodeString(&Source);
  }
  else
  {
    Source.Buffer = (PWSTR)(*(_QWORD *)(a1 + 16) + 32LL);
    Source.Length = *(_WORD *)(a1 + 6) - 44;
    RtlInitUnicodeStringEx(&DestinationString, L"\\Registry\\User");
    RtlCopyUnicodeString(a2, &DestinationString);
    result = RtlAppendUnicodeStringToString(a2, &Source);
    if ( result < 0 )
      return result;
  }
  return RtlAppendUnicodeToString(a2, L"_Classes");
}

```

## disassembly

```asm
0x1800249cc  push    rbx
0x1800249ce  sub     rsp, 40h
0x1800249d2  test    byte ptr [rcx], 1
0x1800249d5  xorps   xmm0, xmm0
0x1800249d8  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x1800249dd  mov     rbx, rdx
0x1800249e0  movups  xmmword ptr [rsp+48h+Source.Length], xmm0
0x1800249e5  jz      short loc_180024A35
0x1800249e7  mov     rax, [rcx+10h]
0x1800249eb  lea     rdx, aRegistryUser; "\\Registry\\User"
0x1800249f2  add     rax, 20h ; ' '
0x1800249f6  mov     [rsp+48h+Source.Buffer], rax
0x1800249fb  movzx   eax, word ptr [rcx+6]
0x1800249ff  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180024a04  sub     ax, 2Ch ; ','
0x180024a08  mov     [rsp+48h+Source.Length], ax
0x180024a0d  call    cs:__imp_RtlInitUnicodeStringEx
0x180024a13  lea     rdx, [rsp+48h+DestinationString]; SourceString
0x180024a18  mov     rcx, rbx; DestinationString
0x180024a1b  call    cs:__imp_RtlCopyUnicodeString
0x180024a21  lea     rdx, [rsp+48h+Source]; Source
0x180024a26  mov     rcx, rbx; Destination
0x180024a29  call    cs:__imp_RtlAppendUnicodeStringToString
0x180024a2f  test    eax, eax
0x180024a31  js      short loc_180024A6D
0x180024a33  jmp     short loc_180024A5D
0x180024a35  lea     rcx, [rsp+48h+Source]; KeyPath
0x180024a3a  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x180024a40  test    eax, eax
0x180024a42  js      short loc_180024A6D
0x180024a44  lea     rdx, [rsp+48h+Source]; SourceString
0x180024a49  mov     rcx, rbx; DestinationString
0x180024a4c  call    cs:__imp_RtlCopyUnicodeString
0x180024a52  lea     rcx, [rsp+48h+Source]; UnicodeString
0x180024a57  call    cs:__imp_RtlFreeUnicodeString
0x180024a5d  lea     rdx, aClasses_0; "_Classes"
0x180024a64  mov     rcx, rbx; Destination
0x180024a67  call    cs:__imp_RtlAppendUnicodeToString
0x180024a6d  add     rsp, 40h
0x180024a71  pop     rbx
0x180024a72  retn
```
