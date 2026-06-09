# ___acrt_uninitialize_stdio

- ea: `0x411e60`
- end: `0x411eac`
- name: `___acrt_uninitialize_stdio`
- size: `76`
- prototype: `void()`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x40ed53`
- `0x411d7b`
- `0x411e60`
- `0x41484c`
- `0x4148f7`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x411e89`
- `KERNEL32!DeleteCriticalSection` at `0x411e89`

## pseudocode

```c
void __acrt_uninitialize_stdio()
{
  int i; // esi

  sub_411D7B();
  _fcloseall();
  for ( i = 0; i != 12; i += 4 )
  {
    __acrt_stdio_free_buffer_nolock(*(_DWORD *)((char *)dword_42731C + i));
    DeleteCriticalSection((LPCRITICAL_SECTION)(*(_DWORD *)((char *)dword_42731C + i) + 32));
  }
  _free_base(dword_42731C);
  dword_42731C = 0;
}

```

## disassembly

```asm
0x411e60  mov     edi, edi
0x411e62  push    esi
0x411e63  call    sub_411D7B
0x411e68  call    __fcloseall
0x411e6d  xor     esi, esi
0x411e6f  mov     eax, dword_42731C
0x411e74  push    dword ptr [esi+eax]
0x411e77  call    ___acrt_stdio_free_buffer_nolock
0x411e7c  mov     eax, dword_42731C
0x411e81  pop     ecx
0x411e82  mov     eax, [esi+eax]
0x411e85  add     eax, 20h ; ' '
0x411e88  push    eax; lpCriticalSection
0x411e89  call    ds:DeleteCriticalSection
0x411e8f  add     esi, 4
0x411e92  cmp     esi, 0Ch
0x411e95  jnz     short loc_411E6F
0x411e97  push    dword_42731C; Block
0x411e9d  call    __free_base
0x411ea2  and     dword_42731C, 0
0x411ea9  pop     ecx
0x411eaa  pop     esi
0x411eab  retn
```
