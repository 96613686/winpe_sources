# BaseRegConstructUserClassPrefix

- ea: `0x1800272e0`
- end: `0x1800273b2`
- name: `BaseRegConstructUserClassPrefix`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18002724c`

## callees

- `0x1800272e0`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x180027335`
- `ntdll!RtlCopyUnicodeString` at `0x180027378`
- `ntdll!RtlCopyUnicodeString` at `0x180027335`
- `ntdll!RtlCopyUnicodeString` at `0x180027378`
- `ntdll!RtlAppendUnicodeToString` at `0x18002739f`
- `ntdll!RtlAppendUnicodeToString` at `0x18002739f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180027349`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180027349`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180027360`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180027360`
- `ntdll!RtlInitUnicodeStringEx` at `0x180027321`
- `ntdll!RtlInitUnicodeStringEx` at `0x180027321`
- `ntdll!RtlFreeUnicodeString` at `0x180027389`
- `ntdll!RtlFreeUnicodeString` at `0x180027389`

## string_xrefs

- `0x1800272ff`: `\Registry\User`

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
0x1800272e0  push    rbx
0x1800272e2  sub     rsp, 40h
0x1800272e6  test    byte ptr [rcx], 1
0x1800272e9  xorps   xmm0, xmm0
0x1800272ec  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x1800272f1  mov     rbx, rdx
0x1800272f4  movups  xmmword ptr [rsp+48h+Source.Length], xmm0
0x1800272f9  jz      short loc_18002735B
0x1800272fb  mov     rax, [rcx+10h]
0x1800272ff  lea     rdx, aRegistryUser; "\\Registry\\User"
0x180027306  add     rax, 20h ; ' '
0x18002730a  mov     [rsp+48h+Source.Buffer], rax
0x18002730f  movzx   eax, word ptr [rcx+6]
0x180027313  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180027318  sub     ax, 2Ch ; ','
0x18002731c  mov     [rsp+48h+Source.Length], ax
0x180027321  call    cs:__imp_RtlInitUnicodeStringEx
0x180027328  nop     dword ptr [rax+rax+00h]
0x18002732d  lea     rdx, [rsp+48h+DestinationString]; SourceString
0x180027332  mov     rcx, rbx; DestinationString
0x180027335  call    cs:__imp_RtlCopyUnicodeString
0x18002733c  nop     dword ptr [rax+rax+00h]
0x180027341  lea     rdx, [rsp+48h+Source]; Source
0x180027346  mov     rcx, rbx; Destination
0x180027349  call    cs:__imp_RtlAppendUnicodeStringToString
0x180027350  nop     dword ptr [rax+rax+00h]
0x180027355  test    eax, eax
0x180027357  js      short loc_1800273AB
0x180027359  jmp     short loc_180027395
0x18002735b  lea     rcx, [rsp+48h+Source]; KeyPath
0x180027360  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x180027367  nop     dword ptr [rax+rax+00h]
0x18002736c  test    eax, eax
0x18002736e  js      short loc_1800273AB
0x180027370  lea     rdx, [rsp+48h+Source]; SourceString
0x180027375  mov     rcx, rbx; DestinationString
0x180027378  call    cs:__imp_RtlCopyUnicodeString
0x18002737f  nop     dword ptr [rax+rax+00h]
0x180027384  lea     rcx, [rsp+48h+Source]; UnicodeString
0x180027389  call    cs:__imp_RtlFreeUnicodeString
0x180027390  nop     dword ptr [rax+rax+00h]
0x180027395  lea     rdx, aClasses_0; "_Classes"
0x18002739c  mov     rcx, rbx; Destination
0x18002739f  call    cs:__imp_RtlAppendUnicodeToString
0x1800273a6  nop     dword ptr [rax+rax+00h]
0x1800273ab  add     rsp, 40h
0x1800273af  pop     rbx
0x1800273b0  retn
```
