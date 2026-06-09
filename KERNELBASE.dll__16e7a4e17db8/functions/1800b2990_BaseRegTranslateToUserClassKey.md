# BaseRegTranslateToUserClassKey

- ea: `0x1800b2990`
- end: `0x1800b2aaa`
- name: `BaseRegTranslateToUserClassKey`
- size: `282`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18005a0c0`
- `0x1800b2490`
- `0x1800b2840`
- `0x18010ab30`

## callees

- `0x1800b2990`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800b2a1a`
- `ntdll!RtlFreeUnicodeString` at `0x1800b2a1a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800b2a42`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800b2a91`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800b2a42`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800b2a91`
- `ntdll!RtlAppendUnicodeToString` at `0x1800b2a2a`
- `ntdll!RtlAppendUnicodeToString` at `0x1800b2a2a`
- `ntdll!RtlCopyUnicodeString` at `0x1800b2a0f`
- `ntdll!RtlCopyUnicodeString` at `0x1800b2a83`
- `ntdll!RtlCopyUnicodeString` at `0x1800b2a0f`
- `ntdll!RtlCopyUnicodeString` at `0x1800b2a83`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800b2a75`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800b2a75`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800b29fd`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800b29fd`

## string_xrefs

- `0x1800b2a5c`: `\Registry\User`

## pseudocode

```c
int __fastcall BaseRegTranslateToUserClassKey(__int64 a1, struct _UNICODE_STRING *a2, USHORT *a3)
{
  __int64 v3; // r10
  _WORD *v4; // r9
  __int16 v7; // dx
  __int64 v8; // r8
  bool v9; // zf
  int result; // eax
  struct _UNICODE_STRING KeyPath; // [rsp+20h] [rbp-38h] BYREF
  UNICODE_STRING Source; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF

  v3 = *(unsigned __int16 *)(a1 + 4);
  v4 = *(_WORD **)(a1 + 16);
  Source = 0;
  if ( v4[v3 + 2] )
  {
    v7 = 1;
    v8 = 1;
  }
  else
  {
    v7 = 0;
    v8 = 0;
  }
  DestinationString = 0;
  KeyPath = 0;
  Source.Buffer = &v4[v3 - v8 + 2];
  v9 = (*(_BYTE *)a1 & 1) == 0;
  Source.Length = *v4 + 2 * (v7 - v3);
  if ( v9 )
  {
    result = RtlFormatCurrentUserKeyPath(&KeyPath);
    if ( result < 0 )
      return result;
    RtlCopyUnicodeString(a2, &KeyPath);
    RtlFreeUnicodeString(&KeyPath);
  }
  else
  {
    KeyPath.Buffer = v4 + 16;
    KeyPath.Length = *(_WORD *)(a1 + 6) - 44;
    RtlInitUnicodeStringEx(&DestinationString, L"\\Registry\\User");
    RtlCopyUnicodeString(a2, &DestinationString);
    result = RtlAppendUnicodeStringToString(a2, &KeyPath);
    if ( result < 0 )
      return result;
  }
  result = RtlAppendUnicodeToString(a2, L"_Classes");
  if ( result >= 0 )
  {
    *a3 = a2->Length;
    return RtlAppendUnicodeStringToString(a2, &Source);
  }
  return result;
}

```

## disassembly

```asm
0x1800b2990  mov     [rsp+arg_0], rbx
0x1800b2995  push    rdi
0x1800b2996  sub     rsp, 50h
0x1800b299a  movzx   r10d, word ptr [rcx+4]
0x1800b299f  xorps   xmm0, xmm0
0x1800b29a2  mov     r9, [rcx+10h]
0x1800b29a6  mov     rdi, r8
0x1800b29a9  movups  xmmword ptr [rsp+58h+Source.Length], xmm0
0x1800b29ae  mov     rbx, rdx
0x1800b29b1  cmp     word ptr [r9+r10*2+4], 0
0x1800b29b8  jz      loc_1800B2A9D
0x1800b29be  mov     edx, 1
0x1800b29c3  mov     r8d, edx
0x1800b29c6  sub     dx, r10w
0x1800b29ca  mov     rax, r10
0x1800b29cd  sub     rax, r8
0x1800b29d0  add     dx, dx
0x1800b29d3  add     rax, 2
0x1800b29d7  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x1800b29dc  movups  xmmword ptr [rsp+58h+KeyPath.Length], xmm0
0x1800b29e1  lea     rax, [r9+rax*2]
0x1800b29e5  mov     [rsp+58h+Source.Buffer], rax
0x1800b29ea  add     dx, [r9]
0x1800b29ee  test    byte ptr [rcx], 1
0x1800b29f1  mov     [rsp+58h+Source.Length], dx
0x1800b29f6  jnz     short loc_1800B2A53
0x1800b29f8  lea     rcx, [rsp+58h+KeyPath]; KeyPath
0x1800b29fd  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x1800b2a03  test    eax, eax
0x1800b2a05  js      short loc_1800B2A48
0x1800b2a07  lea     rdx, [rsp+58h+KeyPath]; SourceString
0x1800b2a0c  mov     rcx, rbx; DestinationString
0x1800b2a0f  call    cs:__imp_RtlCopyUnicodeString
0x1800b2a15  lea     rcx, [rsp+58h+KeyPath]; UnicodeString
0x1800b2a1a  call    cs:__imp_RtlFreeUnicodeString
0x1800b2a20  lea     rdx, aClasses_0; "_Classes"
0x1800b2a27  mov     rcx, rbx; Destination
0x1800b2a2a  call    cs:__imp_RtlAppendUnicodeToString
0x1800b2a30  test    eax, eax
0x1800b2a32  js      short loc_1800B2A48
0x1800b2a34  movzx   eax, word ptr [rbx]
0x1800b2a37  lea     rdx, [rsp+58h+Source]; Source
0x1800b2a3c  mov     rcx, rbx; Destination
0x1800b2a3f  mov     [rdi], ax
0x1800b2a42  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800b2a48  mov     rbx, [rsp+58h+arg_0]
0x1800b2a4d  add     rsp, 50h
0x1800b2a51  pop     rdi
0x1800b2a52  retn
0x1800b2a53  lea     rax, [r9+20h]
0x1800b2a57  mov     [rsp+58h+KeyPath.Buffer], rax
0x1800b2a5c  lea     rdx, aRegistryUser; "\\Registry\\User"
0x1800b2a63  movzx   eax, word ptr [rcx+6]
0x1800b2a67  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x1800b2a6c  sub     ax, 2Ch ; ','
0x1800b2a70  mov     [rsp+58h+KeyPath.Length], ax
0x1800b2a75  call    cs:__imp_RtlInitUnicodeStringEx
0x1800b2a7b  lea     rdx, [rsp+58h+DestinationString]; SourceString
0x1800b2a80  mov     rcx, rbx; DestinationString
0x1800b2a83  call    cs:__imp_RtlCopyUnicodeString
0x1800b2a89  lea     rdx, [rsp+58h+KeyPath]; Source
0x1800b2a8e  mov     rcx, rbx; Destination
0x1800b2a91  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800b2a97  test    eax, eax
0x1800b2a99  jns     short loc_1800B2A20
0x1800b2a9b  jmp     short loc_1800B2A48
0x1800b2a9d  xor     eax, eax
0x1800b2a9f  movzx   edx, ax
0x1800b2aa2  xor     r8d, r8d
0x1800b2aa5  jmp     loc_1800B29C6
```
