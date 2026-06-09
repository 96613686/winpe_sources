# EapQueryBuffer

- ea: `0x18000a528`
- end: `0x18000a5f1`
- name: `EapQueryBuffer`
- size: `201`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009370`
- `0x18000a2cc`
- `0x18000a9f8`
- `0x18000aa78`

## callees

- `0x180009a88`
- `0x18000a528`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000a553`
- `ntdll!RtlInitUnicodeString` at `0x18000a553`
- `ntdll!ZwQueryValueKey` at `0x18000a57b`
- `ntdll!ZwQueryValueKey` at `0x18000a5c5`
- `ntdll!ZwQueryValueKey` at `0x18000a57b`
- `ntdll!ZwQueryValueKey` at `0x18000a5c5`

## pseudocode

```c
__int64 __fastcall EapQueryBuffer(HANDLE KeyHandle, const WCHAR *a2, int a3, __int64 a4)
{
  NTSTATUS v7; // eax
  NTSTATUS Buffer; // ecx
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+68h] [rbp+20h] BYREF

  ResultLength = 0;
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, a2);
  v7 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, *(PVOID *)a4, *(_DWORD *)(a4 + 8), &ResultLength);
  Buffer = v7;
  if ( v7 == -1073741789 || v7 == -2147483643 )
  {
    Buffer = EapExpandValueQueryBuffer(a4, ResultLength);
    if ( Buffer < 0 )
      return (unsigned int)Buffer;
    Buffer = ZwQueryValueKey(
               KeyHandle,
               &ValueName,
               KeyValueFullInformation,
               *(PVOID *)a4,
               *(_DWORD *)(a4 + 8),
               &ResultLength);
  }
  if ( Buffer >= 0 && a3 != *(_DWORD *)(*(_QWORD *)a4 + 4LL) )
    return (unsigned int)-1073741811;
  return (unsigned int)Buffer;
}

```

## disassembly

```asm
0x18000a528  mov     rax, rsp
0x18000a52b  mov     [rax+8], rbx
0x18000a52f  mov     [rax+10h], rsi
0x18000a533  push    rdi
0x18000a534  sub     rsp, 40h
0x18000a538  mov     rsi, rcx
0x18000a53b  mov     dword ptr [rax+20h], 0
0x18000a542  xorps   xmm0, xmm0
0x18000a545  lea     rcx, [rax-18h]; DestinationString
0x18000a549  movups  xmmword ptr [rax-18h], xmm0
0x18000a54d  mov     rbx, r9
0x18000a550  mov     edi, r8d
0x18000a553  call    cs:__imp_RtlInitUnicodeString
0x18000a559  mov     r9, [rbx]; KeyValueInformation
0x18000a55c  lea     rax, [rsp+48h+arg_18]
0x18000a561  mov     [rsp+48h+ResultLength], rax; ResultLength
0x18000a566  lea     rdx, [rsp+48h+ValueName]; ValueName
0x18000a56b  mov     eax, [rbx+8]
0x18000a56e  mov     r8d, 1; KeyValueInformationClass
0x18000a574  mov     rcx, rsi; KeyHandle
0x18000a577  mov     [rsp+48h+Length], eax; Length
0x18000a57b  call    cs:__imp_ZwQueryValueKey
0x18000a581  mov     ecx, eax
0x18000a583  cmp     eax, 0C0000023h
0x18000a588  jz      short loc_18000A591
0x18000a58a  cmp     eax, 80000005h
0x18000a58f  jnz     short loc_18000A5CD
0x18000a591  mov     edx, [rsp+48h+arg_18]
0x18000a595  mov     rcx, rbx
0x18000a598  call    EapExpandValueQueryBuffer
0x18000a59d  mov     ecx, eax
0x18000a59f  test    eax, eax
0x18000a5a1  js      short loc_18000A5DF
0x18000a5a3  mov     r9, [rbx]; KeyValueInformation
0x18000a5a6  lea     rax, [rsp+48h+arg_18]
0x18000a5ab  mov     [rsp+48h+ResultLength], rax; ResultLength
0x18000a5b0  lea     rdx, [rsp+48h+ValueName]; ValueName
0x18000a5b5  mov     eax, [rbx+8]
0x18000a5b8  mov     r8d, 1; KeyValueInformationClass
0x18000a5be  mov     rcx, rsi; KeyHandle
0x18000a5c1  mov     [rsp+48h+Length], eax; Length
0x18000a5c5  call    cs:__imp_ZwQueryValueKey
0x18000a5cb  mov     ecx, eax
0x18000a5cd  test    ecx, ecx
0x18000a5cf  js      short loc_18000A5DF
0x18000a5d1  mov     rax, [rbx]
0x18000a5d4  mov     edx, 0C000000Dh
0x18000a5d9  cmp     edi, [rax+4]
0x18000a5dc  cmovnz  ecx, edx
0x18000a5df  mov     rbx, [rsp+48h+arg_0]
0x18000a5e4  mov     eax, ecx
0x18000a5e6  mov     rsi, [rsp+48h+arg_8]
0x18000a5eb  add     rsp, 40h
0x18000a5ef  pop     rdi
0x18000a5f0  retn
```
