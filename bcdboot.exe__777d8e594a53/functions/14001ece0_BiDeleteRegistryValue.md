# BiDeleteRegistryValue

- ea: `0x14001ece0`
- end: `0x14001ed6a`
- name: `BiDeleteRegistryValue`
- size: `138`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, void *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14001b4bc`
- `0x14001b92c`
- `0x14001bb00`
- `0x14001bd44`
- `0x14001c03c`

## callees

- `0x14001ece0`
- `0x14001f980`

## import_xrefs

- `ntdll!ZwClose` at `0x14001ed57`
- `ntdll!ZwClose` at `0x14001ed57`
- `ntdll!ZwDeleteValueKey` at `0x14001ed3b`
- `ntdll!ZwDeleteValueKey` at `0x14001ed3b`
- `ntdll!RtlInitUnicodeString` at `0x14001ecfe`
- `ntdll!RtlInitUnicodeString` at `0x14001ecfe`

## pseudocode

```c
__int64 __fastcall BiDeleteRegistryValue(__int64 a1, const WCHAR *a2, void *a3)
{
  HANDLE v4; // rsi
  NTSTATUS v5; // edi
  struct _UNICODE_STRING ValueName; // [rsp+20h] [rbp-18h] BYREF
  HANDLE KeyHandle; // [rsp+50h] [rbp+18h] BYREF

  KeyHandle = a3;
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, a2);
  v4 = (HANDLE)(a1 & 0xFFFFFFFFFFFFFFFDuLL);
  KeyHandle = 0;
  v5 = BiOpenKey(v4, L"Description", 131103, &KeyHandle);
  if ( v5 >= 0 )
    v5 = ZwDeleteValueKey(KeyHandle, &ValueName);
  if ( KeyHandle != v4 && KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001ece0  mov     rax, rsp
0x14001ece3  mov     [rax+8], rsi
0x14001ece7  mov     [rax+18h], r8
0x14001eceb  push    rdi
0x14001ecec  sub     rsp, 30h
0x14001ecf0  mov     rsi, rcx
0x14001ecf3  xorps   xmm0, xmm0
0x14001ecf6  lea     rcx, [rax-18h]; DestinationString
0x14001ecfa  movups  xmmword ptr [rax-18h], xmm0
0x14001ecfe  call    cs:__imp_RtlInitUnicodeString
0x14001ed04  and     rsi, 0FFFFFFFFFFFFFFFDh
0x14001ed08  mov     [rsp+38h+KeyHandle], 0
0x14001ed11  mov     rcx, rsi
0x14001ed14  lea     r9, [rsp+38h+KeyHandle]
0x14001ed19  mov     r8d, 2001Fh
0x14001ed1f  lea     rdx, aDescription; "Description"
0x14001ed26  call    BiOpenKey
0x14001ed2b  mov     edi, eax
0x14001ed2d  test    eax, eax
0x14001ed2f  js      short loc_14001ED43
0x14001ed31  mov     rcx, [rsp+38h+KeyHandle]; KeyHandle
0x14001ed36  lea     rdx, [rsp+38h+ValueName]; ValueName
0x14001ed3b  call    cs:__imp_ZwDeleteValueKey
0x14001ed41  mov     edi, eax
0x14001ed43  cmp     [rsp+38h+KeyHandle], rsi
0x14001ed48  jz      short loc_14001ED5D
0x14001ed4a  cmp     [rsp+38h+KeyHandle], 0
0x14001ed50  jz      short loc_14001ED5D
0x14001ed52  mov     rcx, [rsp+38h+KeyHandle]; Handle
0x14001ed57  call    cs:__imp_ZwClose
0x14001ed5d  mov     rsi, [rsp+38h+arg_0]
0x14001ed62  mov     eax, edi
0x14001ed64  add     rsp, 30h
0x14001ed68  pop     rdi
0x14001ed69  retn
```
