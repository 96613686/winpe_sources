# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x140003cd8`
- end: `0x140003d05`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `45`
- prototype: `void __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `16`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140003ddc`
- `0x14000406c`
- `0x140007674`
- `0x140007724`
- `0x1400092ec`
- `0x1400094ac`
- `0x14000a1bc`
- `0x14000a204`
- `0x14000a474`
- `0x14000ed9c`
- `0x14000f3b8`
- `0x14000f794`
- `0x14000f840`
- `0x14000fc40`
- `0x14000fcd4`
- `0x1400100d0`

## callees

- `0x140002504`
- `0x140003cd8`

## pseudocode

```c
void __fastcall std::_Deallocate<16>(_QWORD *a1, unsigned __int64 a2)
{
  if ( a2 >= 0x1000 )
  {
    if ( (unsigned __int64)a1 - *(a1 - 1) - 8 > 0x1F )
      __fastfail(5u);
    a2 += 39LL;
    a1 = (_QWORD *)*(a1 - 1);
  }
  operator delete(a1, a2);
}

```

## disassembly

```asm
0x140003cd8  cmp     rdx, 1000h
0x140003cdf  jb      short loc_140003CF9
0x140003ce1  mov     rax, [rcx-8]
0x140003ce5  sub     rcx, rax
0x140003ce8  sub     rcx, 8
0x140003cec  cmp     rcx, 1Fh
0x140003cf0  ja      short loc_140003CFE
0x140003cf2  add     rdx, 27h ; '''; unsigned __int64
0x140003cf6  mov     rcx, rax; void *
0x140003cf9  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003cfe  mov     ecx, 5
0x140003d03  int     29h; Win8: RtlFailFast(ecx)
```
