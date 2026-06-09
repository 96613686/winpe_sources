# ___acrt_uninitialize_stdio

- ea: `0x412750`
- end: `0x41279c`
- name: `___acrt_uninitialize_stdio`
- size: `76`
- prototype: `void()`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x41001a`
- `0x412673`
- `0x412750`
- `0x4141ec`
- `0x414297`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x412779`
- `KERNEL32!DeleteCriticalSection` at `0x412779`

## pseudocode

```c
void __acrt_uninitialize_stdio()
{
  int i; // esi

  sub_412673();
  _fcloseall();
  for ( i = 0; i != 12; i += 4 )
  {
    __acrt_stdio_free_buffer_nolock(*(_DWORD *)((char *)dword_4184B0 + i));
    DeleteCriticalSection((LPCRITICAL_SECTION)(*(_DWORD *)((char *)dword_4184B0 + i) + 32));
  }
  _free_base(dword_4184B0);
  dword_4184B0 = 0;
}

```

## disassembly

```asm
0x412750  mov     edi, edi
0x412752  push    esi
0x412753  call    sub_412673
0x412758  call    __fcloseall
0x41275d  xor     esi, esi
0x41275f  mov     eax, dword_4184B0
0x412764  push    dword ptr [esi+eax]
0x412767  call    ___acrt_stdio_free_buffer_nolock
0x41276c  mov     eax, dword_4184B0
0x412771  pop     ecx
0x412772  mov     eax, [esi+eax]
0x412775  add     eax, 20h ; ' '
0x412778  push    eax; lpCriticalSection
0x412779  call    ds:DeleteCriticalSection
0x41277f  add     esi, 4
0x412782  cmp     esi, 0Ch
0x412785  jnz     short loc_41275F
0x412787  push    dword_4184B0; Block
0x41278d  call    __free_base
0x412792  and     dword_4184B0, 0
0x412799  pop     ecx
0x41279a  pop     esi
0x41279b  retn
```
