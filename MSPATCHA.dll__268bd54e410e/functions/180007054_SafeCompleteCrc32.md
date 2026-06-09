# SafeCompleteCrc32

- ea: `0x180007054`
- end: `0x180007088`
- name: `SafeCompleteCrc32`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002720`
- `0x180004180`

## callees

- `0x180006d9c`
- `0x180007054`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007076`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007076`

## pseudocode

```c
__int64 __fastcall SafeCompleteCrc32(__int64 a1, unsigned int a2, unsigned int *a3)
{
  unsigned int v3; // r11d

  *a3 = ~(unsigned int)Crc32(a1, a1, a2);
  return v3;
}

```

## disassembly

```asm
0x180007054  push    rbx
0x180007056  sub     rsp, 20h
0x18000705a  mov     rbx, r8
0x18000705d  mov     r11d, 1
0x180007063  mov     r8d, edx
0x180007066  mov     rdx, rcx
0x180007069  call    Crc32
0x18000706e  not     eax
0x180007070  mov     [rbx], eax
0x180007072  jmp     short loc_18000707F
0x180007074  mov     ecx, eax; dwErrCode
0x180007076  call    cs:__imp_SetLastError
0x18000707c  xor     r11d, r11d
0x18000707f  mov     eax, r11d
0x180007082  add     rsp, 20h
0x180007086  pop     rbx
0x180007087  retn
```
