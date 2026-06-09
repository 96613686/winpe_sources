# ___acrt_uninitialize_stdio

- ea: `0x10018823`
- end: `0x1001886f`
- name: `___acrt_uninitialize_stdio`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1001770e`
- `0x10018823`
- `0x1001ac67`
- `0x1001d134`
- `0x1001d1d5`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1001884c`
- `KERNEL32!DeleteCriticalSection` at `0x1001884c`

## pseudocode

```c
void __acrt_uninitialize_stdio()
{
  int i; // esi

  sub_1001AC67();
  sub_1001D134();
  for ( i = 0; i != 12; i += 4 )
  {
    __acrt_stdio_free_buffer_nolock(*(_DWORD *)((char *)dword_10034F1C + i));
    DeleteCriticalSection((LPCRITICAL_SECTION)(*(_DWORD *)((char *)dword_10034F1C + i) + 32));
  }
  _free_base(dword_10034F1C);
  dword_10034F1C = 0;
}

```

## disassembly

```asm
0x10018823  mov     edi, edi
0x10018825  push    esi
0x10018826  call    sub_1001AC67
0x1001882b  call    sub_1001D134
0x10018830  xor     esi, esi
0x10018832  mov     eax, dword_10034F1C
0x10018837  push    dword ptr [esi+eax]
0x1001883a  call    ___acrt_stdio_free_buffer_nolock
0x1001883f  mov     eax, dword_10034F1C
0x10018844  pop     ecx
0x10018845  mov     eax, [esi+eax]
0x10018848  add     eax, 20h ; ' '
0x1001884b  push    eax; lpCriticalSection
0x1001884c  call    ds:DeleteCriticalSection
0x10018852  add     esi, 4
0x10018855  cmp     esi, 0Ch
0x10018858  jnz     short loc_10018832
0x1001885a  push    dword_10034F1C; Block
0x10018860  call    __free_base
0x10018865  and     dword_10034F1C, 0
0x1001886c  pop     ecx
0x1001886d  pop     esi
0x1001886e  retn
```
