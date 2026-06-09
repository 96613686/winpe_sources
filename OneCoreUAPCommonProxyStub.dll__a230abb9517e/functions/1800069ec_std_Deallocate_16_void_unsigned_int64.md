# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x1800069ec`
- end: `0x180006a19`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `45`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000359c`
- `0x1800035ec`
- `0x180006a90`
- `0x180006be8`
- `0x180006d28`
- `0x180007590`
- `0x1800075b8`
- `0x1800075f4`
- `0x180009c50`
- `0x18000a500`

## callees

- `0x18000460c`
- `0x1800069ec`

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
0x1800069ec  cmp     rdx, 1000h
0x1800069f3  jb      short loc_180006A0D
0x1800069f5  mov     rax, [rcx-8]
0x1800069f9  sub     rcx, rax
0x1800069fc  sub     rcx, 8
0x180006a00  cmp     rcx, 1Fh
0x180006a04  ja      short loc_180006A12
0x180006a06  add     rdx, 27h ; '''; unsigned __int64
0x180006a0a  mov     rcx, rax; void *
0x180006a0d  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006a12  mov     ecx, 5
0x180006a17  int     29h; Win8: RtlFailFast(ecx)
```
