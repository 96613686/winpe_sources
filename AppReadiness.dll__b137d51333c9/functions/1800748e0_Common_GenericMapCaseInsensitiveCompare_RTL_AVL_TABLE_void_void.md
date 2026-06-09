# Common::GenericMapCaseInsensitiveCompare(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x1800748e0`
- end: `0x180074945`
- name: `?GenericMapCaseInsensitiveCompare@Common@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `101`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800748e0`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180074927`
- `ntdll!RtlCompareUnicodeString` at `0x180074927`
- `ntdll!RtlInitUnicodeString` at `0x180074901`
- `ntdll!RtlInitUnicodeString` at `0x18007490f`
- `ntdll!RtlInitUnicodeString` at `0x180074901`
- `ntdll!RtlInitUnicodeString` at `0x18007490f`

## pseudocode

```c
__int64 __fastcall Common::GenericMapCaseInsensitiveCompare(
        struct _RTL_AVL_TABLE *Table,
        const WCHAR **FirstStruct,
        const WCHAR **SecondStruct)
{
  const WCHAR *v3; // rdx
  const WCHAR *v4; // rbx
  unsigned int v5; // ebx
  LONG v6; // eax
  UNICODE_STRING String2; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  v3 = *FirstStruct;
  v4 = *SecondStruct;
  DestinationString = 0;
  String2 = 0;
  RtlInitUnicodeString(&DestinationString, v3);
  RtlInitUnicodeString(&String2, v4);
  v5 = 1;
  v6 = RtlCompareUnicodeString(&DestinationString, &String2, 1u);
  if ( v6 <= 0 )
  {
    v5 = 2;
    if ( v6 < 0 )
      return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x1800748e0  push    rbx
0x1800748e2  sub     rsp, 40h
0x1800748e6  mov     rdx, [rdx]; SourceString
0x1800748e9  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1800748ee  mov     rbx, [r8]
0x1800748f1  xorps   xmm0, xmm0
0x1800748f4  xorps   xmm1, xmm1
0x1800748f7  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x1800748fc  movups  xmmword ptr [rsp+48h+String2.Length], xmm1
0x180074901  call    cs:__imp_RtlInitUnicodeString
0x180074907  mov     rdx, rbx; SourceString
0x18007490a  lea     rcx, [rsp+48h+String2]; DestinationString
0x18007490f  call    cs:__imp_RtlInitUnicodeString
0x180074915  mov     ebx, 1
0x18007491a  lea     rdx, [rsp+48h+String2]; String2
0x18007491f  mov     r8b, bl; CaseInsensitive
0x180074922  lea     rcx, [rsp+48h+DestinationString]; String1
0x180074927  call    cs:__imp_RtlCompareUnicodeString
0x18007492d  test    eax, eax
0x18007492f  jg      short loc_18007493D
0x180074931  xor     ecx, ecx
0x180074933  mov     ebx, 2
0x180074938  test    eax, eax
0x18007493a  cmovs   ebx, ecx
0x18007493d  mov     eax, ebx
0x18007493f  add     rsp, 40h
0x180074943  pop     rbx
0x180074944  retn
```
