# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x180004bf0`
- end: `0x180004c1d`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `45`
- prototype: `void __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000de78`
- `0x18000df58`
- `0x18000dfd4`
- `0x18000f144`
- `0x18000f1a8`
- `0x18000f1c0`
- `0x18000f200`
- `0x18000f430`

## callees

- `0x180002f84`
- `0x180004bf0`

## pseudocode

```c
void __fastcall std::_Deallocate<16>(_QWORD *a1, unsigned __int64 a2)
{
  if ( a2 >= 0x1000 )
  {
    if ( (unsigned __int64)a1 - *(a1 - 1) - 8 > 0x1F )
      __fastfail(5u);
    a1 = (_QWORD *)*(a1 - 1);
  }
  operator delete(a1);
}

```

## disassembly

```asm
0x180004bf0  cmp     rdx, 1000h
0x180004bf7  jb      short loc_180004C11
0x180004bf9  mov     rax, [rcx-8]
0x180004bfd  sub     rcx, rax
0x180004c00  sub     rcx, 8
0x180004c04  cmp     rcx, 1Fh
0x180004c08  ja      short loc_180004C16
0x180004c0a  add     rdx, 27h ; '''
0x180004c0e  mov     rcx, rax; Block
0x180004c11  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004c16  mov     ecx, 5
0x180004c1b  int     29h; Win8: RtlFailFast(ecx)
```
