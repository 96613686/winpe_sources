# ___acrt_uninitialize_stdio

- ea: `0x415be0`
- end: `0x415c2c`
- name: `___acrt_uninitialize_stdio`
- size: `76`
- prototype: `void()`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x4136b2`
- `0x415afd`
- `0x415be0`
- `0x419211`
- `0x4192bc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x415c09`
- `KERNEL32!DeleteCriticalSection` at `0x415c09`

## pseudocode

```c
void __acrt_uninitialize_stdio()
{
  int i; // esi

  sub_415AFD();
  _fcloseall();
  for ( i = 0; i != 12; i += 4 )
  {
    __acrt_stdio_free_buffer_nolock(*(_DWORD *)((char *)dword_43E7A8 + i));
    DeleteCriticalSection((LPCRITICAL_SECTION)(*(_DWORD *)((char *)dword_43E7A8 + i) + 32));
  }
  _free_base(dword_43E7A8);
  dword_43E7A8 = 0;
}

```

## disassembly

```asm
0x415be0  mov     edi, edi
0x415be2  push    esi
0x415be3  call    sub_415AFD
0x415be8  call    __fcloseall
0x415bed  xor     esi, esi
0x415bef  mov     eax, dword_43E7A8
0x415bf4  push    dword ptr [esi+eax]
0x415bf7  call    ___acrt_stdio_free_buffer_nolock
0x415bfc  mov     eax, dword_43E7A8
0x415c01  pop     ecx
0x415c02  mov     eax, [esi+eax]
0x415c05  add     eax, 20h ; ' '
0x415c08  push    eax; lpCriticalSection
0x415c09  call    ds:DeleteCriticalSection
0x415c0f  add     esi, 4
0x415c12  cmp     esi, 0Ch
0x415c15  jnz     short loc_415BEF
0x415c17  push    dword_43E7A8; Block
0x415c1d  call    __free_base
0x415c22  and     dword_43E7A8, 0
0x415c29  pop     ecx
0x415c2a  pop     esi
0x415c2b  retn
```
