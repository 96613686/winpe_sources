# AiRegWriteDwordValue

- ea: `0x1400090d0`
- end: `0x140009143`
- name: `AiRegWriteDwordValue`
- size: `115`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1400064f8`

## callees

- `0x140009088`
- `0x1400090d0`

## import_xrefs

- `ntdll!NtSetValueKey` at `0x14000911e`
- `ntdll!NtSetValueKey` at `0x14000911e`
- `ntdll!NtClose` at `0x140009130`
- `ntdll!NtClose` at `0x140009130`

## pseudocode

```c
__int64 __fastcall AiRegWriteDwordValue(__int64 a1, struct _UNICODE_STRING *a2, struct _UNICODE_STRING *a3, int a4)
{
  NTSTATUS v5; // ebx
  HANDLE KeyHandle; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+58h] [rbp+20h] BYREF

  Data = a4;
  KeyHandle = 0;
  v5 = AiRegOpenKey(a1, a2, (__int64)a3, &KeyHandle);
  if ( v5 >= 0 )
    v5 = NtSetValueKey(KeyHandle, a3, 0, 4u, &Data, 4u);
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400090d0  mov     rax, rsp
0x1400090d3  mov     [rax+10h], rbx
0x1400090d7  mov     [rax+20h], r9d
0x1400090db  mov     [rax+8], rcx
0x1400090df  push    rdi
0x1400090e0  sub     rsp, 30h
0x1400090e4  lea     r9, [rax+8]
0x1400090e8  mov     qword ptr [rax+8], 0
0x1400090f0  mov     rdi, r8
0x1400090f3  call    AiRegOpenKey
0x1400090f8  mov     ebx, eax
0x1400090fa  test    eax, eax
0x1400090fc  js      short loc_140009126
0x1400090fe  mov     rcx, [rsp+38h+KeyHandle]; KeyHandle
0x140009103  lea     rax, [rsp+38h+arg_18]
0x140009108  mov     r9d, 4; Type
0x14000910e  xor     r8d, r8d; TitleIndex
0x140009111  mov     [rsp+38h+DataSize], r9d; DataSize
0x140009116  mov     rdx, rdi; ValueName
0x140009119  mov     [rsp+38h+Data], rax; Data
0x14000911e  call    cs:__imp_NtSetValueKey
0x140009124  mov     ebx, eax
0x140009126  mov     rcx, [rsp+38h+KeyHandle]; Handle
0x14000912b  test    rcx, rcx
0x14000912e  jz      short loc_140009136
0x140009130  call    cs:__imp_NtClose
0x140009136  mov     eax, ebx
0x140009138  mov     rbx, [rsp+38h+arg_8]
0x14000913d  add     rsp, 30h
0x140009141  pop     rdi
0x140009142  retn
```
