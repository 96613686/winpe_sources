# AiRegWriteDwordValue

- ea: `0x1400295e8`
- end: `0x140029670`
- name: `AiRegWriteDwordValue`
- size: `136`
- prototype: `__int64 __fastcall(__int64, struct _UNICODE_STRING *, struct _UNICODE_STRING *, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140023e00`
- `0x140024978`
- `0x140024c50`

## callees

- `0x1400295e8`
- `0x1400331a0`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x14002963e`
- `ntoskrnl!ZwSetValueKey` at `0x14002963e`
- `ntoskrnl!ZwClose` at `0x140029656`
- `ntoskrnl!ZwClose` at `0x140029656`

## pseudocode

```c
__int64 __fastcall AiRegWriteDwordValue(__int64 a1, struct _UNICODE_STRING *a2, struct _UNICODE_STRING *a3, int a4)
{
  NTSTATUS v5; // ebx
  HANDLE KeyHandle; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+58h] [rbp+20h] BYREF

  Data = a4;
  KeyHandle = 0;
  v5 = AiRegOpenKey(0, a2, 0x20006u, &KeyHandle);
  if ( v5 >= 0 )
    v5 = ZwSetValueKey(KeyHandle, a3, 0, 4u, &Data, 4u);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400295e8  mov     rax, rsp
0x1400295eb  mov     [rax+10h], rbx
0x1400295ef  mov     [rax+20h], r9d
0x1400295f3  mov     [rax+8], rcx
0x1400295f7  push    rdi
0x1400295f8  sub     rsp, 30h
0x1400295fc  mov     rdi, r8
0x1400295ff  mov     qword ptr [rax+8], 0
0x140029607  mov     r8d, 20006h
0x14002960d  lea     r9, [rax+8]
0x140029611  xor     ecx, ecx
0x140029613  call    AiRegOpenKey
0x140029618  mov     ebx, eax
0x14002961a  test    eax, eax
0x14002961c  js      short loc_14002964C
0x14002961e  mov     rcx, [rsp+38h+KeyHandle]; KeyHandle
0x140029623  lea     rax, [rsp+38h+arg_18]
0x140029628  mov     r9d, 4; Type
0x14002962e  xor     r8d, r8d; TitleIndex
0x140029631  mov     [rsp+38h+DataSize], r9d; DataSize
0x140029636  mov     rdx, rdi; ValueName
0x140029639  mov     [rsp+38h+Data], rax; Data
0x14002963e  call    cs:__imp_ZwSetValueKey
0x140029645  nop     dword ptr [rax+rax+00h]
0x14002964a  mov     ebx, eax
0x14002964c  mov     rcx, [rsp+38h+KeyHandle]; Handle
0x140029651  test    rcx, rcx
0x140029654  jz      short loc_140029662
0x140029656  call    cs:__imp_ZwClose
0x14002965d  nop     dword ptr [rax+rax+00h]
0x140029662  mov     eax, ebx
0x140029664  mov     rbx, [rsp+38h+arg_8]
0x140029669  add     rsp, 30h
0x14002966d  pop     rdi
0x14002966e  retn
```
