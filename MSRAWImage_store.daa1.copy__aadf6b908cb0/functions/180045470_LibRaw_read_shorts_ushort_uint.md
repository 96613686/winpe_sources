# LibRaw::read_shorts(ushort *,uint)

- ea: `0x180045470`
- end: `0x180045515`
- name: `?read_shorts@LibRaw@@IEAAXPEAGI@Z`
- size: `165`
- prototype: `void __fastcall(LibRaw *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `23`
- callee_count: `4`
- tags: ``

## callers

- `0x180009d90`
- `0x180029650`
- `0x180029f90`
- `0x18002a4a0`
- `0x18002a9b0`
- `0x18002c950`
- `0x180048e20`
- `0x1800491d0`
- `0x18004e2a0`
- `0x180050310`
- `0x1800504e0`
- `0x180050ad0`
- `0x180050bd0`
- `0x180052970`
- `0x180052e20`
- `0x180053070`
- `0x180053630`
- `0x180053860`
- `0x1800570e0`
- `0x18005bf50`
- `0x18005d8b0`
- `0x18005e500`
- `0x180065900`

## callees

- `0x1800090f0`
- `0x180009460`
- `0x180045470`
- `0x1800b4010`

## import_xrefs

- `WS2_32!__imp_ntohs` at `0x1800454cb`
- `WS2_32!__imp_ntohs` at `0x1800454cb`

## pseudocode

```c
void __fastcall LibRaw::read_shorts(LibRaw *this, unsigned __int16 *a2, unsigned int a3)
{
  __int16 v6; // bx

  if ( (*(unsigned int (__fastcall **)(_QWORD, unsigned __int16 *, __int64, _QWORD))(**((_QWORD **)this + 47659) + 16LL))(
         *((_QWORD *)this + 47659),
         a2,
         2,
         a3) < a3 )
    LibRaw::derror(this);
  v6 = *((_WORD *)this + 190704);
  if ( (v6 == 18761) == (ntohs(0x1234u) == 4660) )
    LibRaw::libraw_swab(this, a2, 2 * a3);
}

```

## disassembly

```asm
0x180045470  mov     [rsp+arg_0], rbx
0x180045475  mov     [rsp+arg_8], rbp
0x18004547a  mov     [rsp+arg_10], rsi
0x18004547f  mov     [rsp+arg_18], rdi
0x180045484  push    r14
0x180045486  sub     rsp, 30h
0x18004548a  mov     rdi, rcx
0x18004548d  mov     esi, r8d
0x180045490  mov     rcx, [rcx+5D158h]
0x180045497  mov     rbp, rdx
0x18004549a  mov     r9d, r8d
0x18004549d  mov     r8d, 2
0x1800454a3  mov     rax, [rcx]
0x1800454a6  mov     rax, [rax+10h]
0x1800454aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454af  cmp     eax, esi
0x1800454b1  jnb     short loc_1800454BB
0x1800454b3  mov     rcx, rdi; this
0x1800454b6  call    ?derror@LibRaw@@IEAAXXZ; LibRaw::derror(void)
0x1800454bb  movzx   ebx, word ptr [rdi+5D1E0h]
0x1800454c2  mov     r14d, 1234h
0x1800454c8  mov     ecx, r14d; netshort
0x1800454cb  call    cs:__imp_ntohs
0x1800454d1  xor     edx, edx
0x1800454d3  cmp     ax, r14w
0x1800454d7  mov     ecx, edx
0x1800454d9  mov     eax, 4949h
0x1800454de  setz    cl
0x1800454e1  cmp     bx, ax
0x1800454e4  setz    dl
0x1800454e7  cmp     edx, ecx
0x1800454e9  jnz     short loc_1800454FA
0x1800454eb  lea     r8d, [rsi+rsi]; unsigned __int64
0x1800454ef  mov     rdx, rbp; void *
0x1800454f2  mov     rcx, rdi; this
0x1800454f5  call    ?libraw_swab@LibRaw@@IEAAXPEAX_K@Z; LibRaw::libraw_swab(void *,unsigned __int64)
0x1800454fa  mov     rbx, [rsp+38h+arg_0]
0x1800454ff  mov     rbp, [rsp+38h+arg_8]
0x180045504  mov     rsi, [rsp+38h+arg_10]
0x180045509  mov     rdi, [rsp+38h+arg_18]
0x18004550e  add     rsp, 30h
0x180045512  pop     r14
0x180045514  retn
```
