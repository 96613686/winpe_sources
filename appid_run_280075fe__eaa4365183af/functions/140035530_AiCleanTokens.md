# AiCleanTokens

- ea: `0x140035530`
- end: `0x140035576`
- name: `AiCleanTokens`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001f3c0`
- `0x14002cd1c`

## callees

- `0x140035530`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140035545`
- `ntoskrnl!ZwClose` at `0x14003555e`
- `ntoskrnl!ZwClose` at `0x140035545`
- `ntoskrnl!ZwClose` at `0x14003555e`

## pseudocode

```c
NTSTATUS __fastcall AiCleanTokens(void *a1, void *a2)
{
  NTSTATUS result; // eax

  if ( a1 )
    result = ZwClose(a1);
  if ( a2 )
  {
    if ( a2 != a1 )
      return ZwClose(a2);
  }
  return result;
}

```

## disassembly

```asm
0x140035530  mov     [rsp+arg_0], rbx
0x140035535  push    rdi
0x140035536  sub     rsp, 20h
0x14003553a  mov     rbx, rdx
0x14003553d  mov     rdi, rcx
0x140035540  test    rcx, rcx
0x140035543  jz      short loc_140035551
0x140035545  call    cs:__imp_ZwClose
0x14003554c  nop     dword ptr [rax+rax+00h]
0x140035551  test    rbx, rbx
0x140035554  jz      short loc_14003556A
0x140035556  cmp     rbx, rdi
0x140035559  jz      short loc_14003556A
0x14003555b  mov     rcx, rbx; Handle
0x14003555e  call    cs:__imp_ZwClose
0x140035565  nop     dword ptr [rax+rax+00h]
0x14003556a  mov     rbx, [rsp+28h+arg_0]
0x14003556f  add     rsp, 20h
0x140035573  pop     rdi
0x140035574  retn
```
