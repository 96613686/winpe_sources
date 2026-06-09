# utl::make_unique<Kerb3961::SimplifiedSpecificKey,,0>(void)

- ea: `0x18001023c`
- end: `0x180010295`
- name: `??$make_unique@USimplifiedSpecificKey@Kerb3961@@$$V$0A@@utl@@YA?AV?$unique_ptr@USimplifiedSpecificKey@Kerb3961@@U?$default_delete@USimplifiedSpecificKey@Kerb3961@@@utl@@@0@XZ`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012c40`
- `0x18001a760`

## callees

- `0x1800029bc`
- `0x18001023c`

## pseudocode

```c
_QWORD *__fastcall utl::make_unique<Kerb3961::SimplifiedSpecificKey,,0>(_QWORD *a1, const struct std::nothrow_t *a2)
{
  _DWORD *v3; // rax

  v3 = operator new(0x48u, a2);
  if ( v3 )
  {
    v3[5] = 0;
    v3[11] = 0;
    v3[17] = 0;
    *(_QWORD *)v3 = 0;
    *((_QWORD *)v3 + 1) = 0;
    v3[4] = -1073741823;
    *((_QWORD *)v3 + 3) = 0;
    *((_QWORD *)v3 + 4) = 0;
    v3[10] = -1073741823;
    *((_QWORD *)v3 + 6) = 0;
    *((_QWORD *)v3 + 7) = 0;
    v3[16] = -1073741823;
  }
  else
  {
    v3 = 0;
  }
  *a1 = v3;
  return a1;
}

```

## disassembly

```asm
0x18001023c  push    rbx
0x18001023e  sub     rsp, 20h
0x180010242  mov     rbx, rcx
0x180010245  mov     ecx, 48h ; 'H'; unsigned __int64
0x18001024a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001024f  xor     edx, edx
0x180010251  test    rax, rax
0x180010254  jz      short loc_180010286
0x180010256  mov     [rax+14h], edx
0x180010259  mov     ecx, 0C0000001h
0x18001025e  mov     [rax+2Ch], edx
0x180010261  mov     [rax+44h], edx
0x180010264  mov     [rax], rdx
0x180010267  mov     [rax+8], rdx
0x18001026b  mov     [rax+10h], ecx
0x18001026e  mov     [rax+18h], rdx
0x180010272  mov     [rax+20h], rdx
0x180010276  mov     [rax+28h], ecx
0x180010279  mov     [rax+30h], rdx
0x18001027d  mov     [rax+38h], rdx
0x180010281  mov     [rax+40h], ecx
0x180010284  jmp     short loc_180010289
0x180010286  mov     rax, rdx
0x180010289  mov     [rbx], rax
0x18001028c  mov     rax, rbx
0x18001028f  add     rsp, 20h
0x180010293  pop     rbx
0x180010294  retn
```
