# EapSetValue

- ea: `0x18000ab18`
- end: `0x18000ab73`
- name: `EapSetValue`
- size: `91`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, ULONG)`
- caller_count: `5`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800095e0`
- `0x18000ab7c`
- `0x18000ad20`
- `0x18000aec4`
- `0x18000afd0`

## import_xrefs

- `ntdll!ZwSetValueKey` at `0x18000ab5d`
- `ntdll!ZwSetValueKey` at `0x18000ab5d`
- `ntdll!RtlInitUnicodeString` at `0x18000ab3c`
- `ntdll!RtlInitUnicodeString` at `0x18000ab3c`

## pseudocode

```c
NTSTATUS __fastcall EapSetValue(HANDLE KeyHandle, const WCHAR *a2, ULONG a3, void *a4, ULONG DataSize)
{
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-18h] BYREF

  ValueName = 0;
  RtlInitUnicodeString(&ValueName, a2);
  return ZwSetValueKey(KeyHandle, &ValueName, 0, a3, a4, DataSize);
}

```

## disassembly

```asm
0x18000ab18  mov     rax, rsp
0x18000ab1b  mov     [rax+8], rbx
0x18000ab1f  mov     [rax+10h], rsi
0x18000ab23  push    rdi
0x18000ab24  sub     rsp, 40h
0x18000ab28  mov     rsi, rcx
0x18000ab2b  xorps   xmm0, xmm0
0x18000ab2e  lea     rcx, [rax-18h]; DestinationString
0x18000ab32  mov     rbx, r9
0x18000ab35  movups  xmmword ptr [rax-18h], xmm0
0x18000ab39  mov     edi, r8d
0x18000ab3c  call    cs:__imp_RtlInitUnicodeString
0x18000ab42  mov     eax, [rsp+48h+arg_20]
0x18000ab46  lea     rdx, [rsp+48h+ValueName]; ValueName
0x18000ab4b  mov     [rsp+48h+DataSize], eax; DataSize
0x18000ab4f  mov     r9d, edi; Type
0x18000ab52  xor     r8d, r8d; TitleIndex
0x18000ab55  mov     [rsp+48h+Data], rbx; Data
0x18000ab5a  mov     rcx, rsi; KeyHandle
0x18000ab5d  call    cs:__imp_ZwSetValueKey
0x18000ab63  mov     rbx, [rsp+48h+arg_0]
0x18000ab68  mov     rsi, [rsp+48h+arg_8]
0x18000ab6d  add     rsp, 40h
0x18000ab71  pop     rdi
0x18000ab72  retn
```
