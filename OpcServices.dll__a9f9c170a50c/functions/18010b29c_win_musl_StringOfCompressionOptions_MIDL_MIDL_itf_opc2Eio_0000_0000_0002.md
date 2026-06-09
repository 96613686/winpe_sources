# win_musl::StringOfCompressionOptions(__MIDL___MIDL_itf_opc2Eio_0000_0000_0002)

- ea: `0x18010b29c`
- end: `0x18010b2e5`
- name: `?StringOfCompressionOptions@win_musl@@YAPEB_WW4__MIDL___MIDL_itf_opc2Eio_0000_0000_0002@@@Z`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f008`
- `0x180017e6c`

## callees

- `0x18010b29c`

## string_xrefs

- `0x18010b2cd`: `CompressionOptions_Maximum`
- `0x18010b2c5`: `CompressionOptions_Fast`
- `0x18010b2dd`: `CompressionOptions_NotCompressed`
- `0x18010b2d5`: `CompressionOptions_Normal`
- `0x18010b2b9`: `CompressionOptions_SuperFast`
- `0x18010b2b2`: `invalid CompressionOption!`

## pseudocode

```c
const wchar_t *__fastcall win_musl::StringOfCompressionOptions(int a1)
{
  const wchar_t *result; // rax

  switch ( a1 )
  {
    case -1:
      return L"CompressionOptions_NotCompressed";
    case 0:
      return L"CompressionOptions_Normal";
    case 1:
      return L"CompressionOptions_Maximum";
    case 2:
      return L"CompressionOptions_Fast";
  }
  result = L"CompressionOptions_SuperFast";
  if ( a1 != 3 )
    return L"invalid CompressionOption!";
  return result;
}

```

## disassembly

```asm
0x18010b29c  cmp     ecx, 0FFFFFFFFh
0x18010b29f  jz      short loc_18010B2DD
0x18010b2a1  test    ecx, ecx
0x18010b2a3  jz      short loc_18010B2D5
0x18010b2a5  cmp     ecx, 1
0x18010b2a8  jz      short loc_18010B2CD
0x18010b2aa  cmp     ecx, 2
0x18010b2ad  jz      short loc_18010B2C5
0x18010b2af  cmp     ecx, 3
0x18010b2b2  lea     rdx, aInvalidCompres; "invalid CompressionOption!"
0x18010b2b9  lea     rax, aCompressionopt_4; "CompressionOptions_SuperFast"
0x18010b2c0  cmovnz  rax, rdx
0x18010b2c4  retn
0x18010b2c5  lea     rax, aCompressionopt_0; "CompressionOptions_Fast"
0x18010b2cc  retn
0x18010b2cd  lea     rax, aCompressionopt_5; "CompressionOptions_Maximum"
0x18010b2d4  retn
0x18010b2d5  lea     rax, aCompressionopt; "CompressionOptions_Normal"
0x18010b2dc  retn
0x18010b2dd  lea     rax, aCompressionopt_1; "CompressionOptions_NotCompressed"
0x18010b2e4  retn
```
