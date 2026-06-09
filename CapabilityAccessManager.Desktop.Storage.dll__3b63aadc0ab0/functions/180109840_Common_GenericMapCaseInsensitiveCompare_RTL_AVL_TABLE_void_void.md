# Common::GenericMapCaseInsensitiveCompare(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x180109840`
- end: `0x1801098a5`
- name: `?GenericMapCaseInsensitiveCompare@Common@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `101`
- prototype: `__int64 __fastcall(struct _RTL_AVL_TABLE *Table, const WCHAR **FirstStruct, const WCHAR **SecondStruct)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180109840`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180109861`
- `ntdll!RtlInitUnicodeString` at `0x18010986f`
- `ntdll!RtlInitUnicodeString` at `0x180109861`
- `ntdll!RtlInitUnicodeString` at `0x18010986f`
- `ntdll!RtlCompareUnicodeString` at `0x180109887`
- `ntdll!RtlCompareUnicodeString` at `0x180109887`

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
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

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
0x180109840  push    rbx
0x180109842  sub     rsp, 40h
0x180109846  mov     rdx, [rdx]; SourceString
0x180109849  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18010984e  mov     rbx, [r8]
0x180109851  xorps   xmm0, xmm0
0x180109854  xorps   xmm1, xmm1
0x180109857  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18010985c  movups  xmmword ptr [rsp+48h+String2.Length], xmm1
0x180109861  call    cs:__imp_RtlInitUnicodeString
0x180109867  mov     rdx, rbx; SourceString
0x18010986a  lea     rcx, [rsp+48h+String2]; DestinationString
0x18010986f  call    cs:__imp_RtlInitUnicodeString
0x180109875  mov     ebx, 1
0x18010987a  lea     rdx, [rsp+48h+String2]; String2
0x18010987f  mov     r8b, bl; CaseInsensitive
0x180109882  lea     rcx, [rsp+48h+DestinationString]; String1
0x180109887  call    cs:__imp_RtlCompareUnicodeString
0x18010988d  test    eax, eax
0x18010988f  jg      short loc_18010989D
0x180109891  xor     ecx, ecx
0x180109893  mov     ebx, 2
0x180109898  test    eax, eax
0x18010989a  cmovs   ebx, ecx
0x18010989d  mov     eax, ebx
0x18010989f  add     rsp, 40h
0x1801098a3  pop     rbx
0x1801098a4  retn
```
