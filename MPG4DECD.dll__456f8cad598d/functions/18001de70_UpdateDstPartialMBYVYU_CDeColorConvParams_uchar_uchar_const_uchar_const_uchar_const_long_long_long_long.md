# UpdateDstPartialMBYVYU(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18001de70`
- end: `0x18001df46`
- name: `?UpdateDstPartialMBYVYU@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `214`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800018b0`
- `0x18001d4b0`
- `0x18001de70`
- `0x180021005`

## pseudocode

```c
void __fastcall UpdateDstPartialMBYVYU(
        struct CDeColorConvParams *a1,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        unsigned __int8 *a5,
        int a6,
        int a7,
        int a8,
        int a9)
{
  int v11; // esi
  unsigned __int8 *i; // rdi
  unsigned __int8 Src[512]; // [rsp+40h] [rbp-238h] BYREF

  UpdateDstMBYVYU(Src, a3, a4, a5, a6, a7, 32);
  v11 = 0;
  for ( i = Src; v11 < a9; ++v11 )
  {
    memcpy_0(a2, i, (int)(2 * (a8 & 0xFFFFFFFE)));
    i += 32;
    a2 += *((int *)a1 + 16);
  }
}

```

## disassembly

```asm
0x18001de70  mov     [rsp+arg_0], rbx
0x18001de75  push    rbp
0x18001de76  push    rsi
0x18001de77  push    rdi
0x18001de78  push    r12
0x18001de7a  push    r14
0x18001de7c  sub     rsp, 250h
0x18001de83  mov     rax, cs:__security_cookie
0x18001de8a  xor     rax, rsp
0x18001de8d  mov     [rsp+278h+var_38], rax
0x18001de95  mov     eax, [rsp+278h+arg_30]
0x18001de9c  mov     r11, r9
0x18001de9f  mov     r14d, [rsp+278h+arg_38]
0x18001dea7  mov     r10, r8
0x18001deaa  mov     r9, [rsp+278h+arg_20]; unsigned __int8 *
0x18001deb2  mov     rbx, rdx
0x18001deb5  mov     [rsp+278h+var_248], 20h ; ' '; int
0x18001debd  mov     r12, rcx
0x18001dec0  mov     [rsp+278h+var_250], eax; int
0x18001dec4  lea     rcx, [rsp+278h+Src]; unsigned __int8 *
0x18001dec9  mov     eax, [rsp+278h+arg_28]
0x18001ded0  mov     r8, r11; unsigned __int8 *
0x18001ded3  mov     rdx, r10; unsigned __int8 *
0x18001ded6  mov     [rsp+278h+var_258], eax; int
0x18001deda  and     r14d, 0FFFFFFFEh
0x18001dede  call    ?UpdateDstMBYVYU@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBYVYU(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001dee3  xor     esi, esi
0x18001dee5  lea     rdi, [rsp+278h+Src]
0x18001deea  cmp     [rsp+278h+arg_40], esi
0x18001def1  jle     short loc_18001DF1F
0x18001def3  lea     eax, [r14+r14]
0x18001def7  movsxd  rbp, eax
0x18001defa  mov     r8, rbp; Size
0x18001defd  mov     rdx, rdi; Src
0x18001df00  mov     rcx, rbx; void *
0x18001df03  call    memcpy_0
0x18001df08  movsxd  rax, dword ptr [r12+40h]
0x18001df0d  add     rdi, 20h ; ' '
0x18001df11  add     rbx, rax
0x18001df14  inc     esi
0x18001df16  cmp     esi, [rsp+278h+arg_40]
0x18001df1d  jl      short loc_18001DEFA
0x18001df1f  mov     rcx, [rsp+278h+var_38]
0x18001df27  xor     rcx, rsp; StackCookie
0x18001df2a  call    __security_check_cookie
0x18001df2f  mov     rbx, [rsp+278h+arg_0]
0x18001df37  add     rsp, 250h
0x18001df3e  pop     r14
0x18001df40  pop     r12
0x18001df42  pop     rdi
0x18001df43  pop     rsi
0x18001df44  pop     rbp
0x18001df45  retn
```
