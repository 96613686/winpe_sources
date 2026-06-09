# dllmain_raw(HINSTANCE__ * const,ulong,void * const)

- ea: `0x10010a26`
- end: `0x10010a51`
- name: `?dllmain_raw@@YGHQAUHINSTANCE__@@KQAX@Z`
- size: `43`
- prototype: `int __stdcall(HINSTANCE, unsigned int, void *const)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10010920`

## callees

- `0x1000b035`
- `0x10010a26`

## pseudocode

```c
int __stdcall dllmain_raw(HINSTANCE a1, unsigned int a2, void *const a3)
{
  return 1;
}

```

## disassembly

```asm
0x10010a26  push    ebp
0x10010a27  mov     ebp, esp
0x10010a29  push    esi
0x10010a2a  mov     esi, ds:dword_1002B52C
0x10010a30  test    esi, esi
0x10010a32  jnz     short loc_10010A39
0x10010a34  xor     eax, eax
0x10010a36  inc     eax
0x10010a37  jmp     short loc_10010A4C
0x10010a39  push    [ebp+arg_8]
0x10010a3c  mov     ecx, esi
0x10010a3e  push    [ebp+arg_4]
0x10010a41  push    [ebp+arg_0]
0x10010a44  call    ds:___guard_check_icall_fptr
0x10010a4a  call    esi ; dword_1002B52C
0x10010a4c  pop     esi
0x10010a4d  pop     ebp
0x10010a4e  retn    0Ch
```
