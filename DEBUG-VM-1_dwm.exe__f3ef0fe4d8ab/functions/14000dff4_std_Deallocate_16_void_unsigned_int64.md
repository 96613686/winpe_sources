# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x14000dff4`
- end: `0x14000e021`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `45`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000e028`
- `0x14000e994`
- `0x14000f12c`
- `0x14000f16c`
- `0x14000f1b0`
- `0x14000f20c`

## callees

- `0x1400057c4`
- `0x14000dff4`

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
0x14000dff4  cmp     rdx, 1000h
0x14000dffb  jb      short loc_14000E015
0x14000dffd  mov     rax, [rcx-8]
0x14000e001  sub     rcx, rax
0x14000e004  sub     rcx, 8
0x14000e008  cmp     rcx, 1Fh
0x14000e00c  ja      short loc_14000E01A
0x14000e00e  add     rdx, 27h ; '''; unsigned __int64
0x14000e012  mov     rcx, rax; void *
0x14000e015  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e01a  mov     ecx, 5
0x14000e01f  int     29h; Win8: RtlFailFast(ecx)
```
