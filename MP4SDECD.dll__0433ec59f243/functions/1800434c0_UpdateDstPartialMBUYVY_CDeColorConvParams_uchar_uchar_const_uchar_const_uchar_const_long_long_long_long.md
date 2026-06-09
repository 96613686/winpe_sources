# UpdateDstPartialMBUYVY(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x1800434c0`
- end: `0x18004358e`
- name: `?UpdateDstPartialMBUYVY@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `206`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18002aac0`
- `0x1800427d0`
- `0x1800434c0`
- `0x180045805`

## pseudocode

```c
void __fastcall UpdateDstPartialMBUYVY(
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

  UpdateDstMBUYVY(a1, Src, a3, a4, a5, a6, a7, 32);
  v11 = 0;
  for ( i = Src; v11 < a9; ++v11 )
  {
    memcpy_0(a2, i, (int)(2 * (a8 & 0xFFFFFFFE)));
    i += 32;
    a2 += *((int *)a1 + 19);
  }
}

```

## disassembly

```asm
0x1800434c0  mov     [rsp+arg_0], rbx
0x1800434c5  push    rbp
0x1800434c6  push    rsi
0x1800434c7  push    rdi
0x1800434c8  push    r14
0x1800434ca  push    r15
0x1800434cc  sub     rsp, 250h
0x1800434d3  mov     rax, cs:__security_cookie
0x1800434da  xor     rax, rsp
0x1800434dd  mov     [rsp+278h+var_38], rax
0x1800434e5  mov     eax, [rsp+278h+arg_30]
0x1800434ec  mov     rbx, rdx
0x1800434ef  mov     r10, [rsp+278h+arg_20]
0x1800434f7  lea     rdx, [rsp+278h+Src]; unsigned __int8 *
0x1800434fc  mov     r14d, [rsp+278h+arg_38]
0x180043504  mov     r15, rcx
0x180043507  mov     [rsp+278h+var_240], 20h ; ' '; int
0x18004350f  and     r14d, 0FFFFFFFEh
0x180043513  mov     [rsp+278h+var_248], eax; int
0x180043517  mov     eax, [rsp+278h+arg_28]
0x18004351e  mov     [rsp+278h+var_250], eax; int
0x180043522  mov     [rsp+278h+var_258], r10; unsigned __int8 *
0x180043527  call    ?UpdateDstMBUYVY@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstMBUYVY(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18004352c  xor     esi, esi
0x18004352e  lea     rdi, [rsp+278h+Src]
0x180043533  cmp     [rsp+278h+arg_40], esi
0x18004353a  jle     short loc_180043567
0x18004353c  lea     eax, [r14+r14]
0x180043540  movsxd  rbp, eax
0x180043543  mov     r8, rbp; Size
0x180043546  mov     rdx, rdi; Src
0x180043549  mov     rcx, rbx; void *
0x18004354c  call    memcpy_0
0x180043551  movsxd  rax, dword ptr [r15+4Ch]
0x180043555  add     rdi, 20h ; ' '
0x180043559  add     rbx, rax
0x18004355c  inc     esi
0x18004355e  cmp     esi, [rsp+278h+arg_40]
0x180043565  jl      short loc_180043543
0x180043567  mov     rcx, [rsp+278h+var_38]
0x18004356f  xor     rcx, rsp; StackCookie
0x180043572  call    __security_check_cookie
0x180043577  mov     rbx, [rsp+278h+arg_0]
0x18004357f  add     rsp, 250h
0x180043586  pop     r15
0x180043588  pop     r14
0x18004358a  pop     rdi
0x18004358b  pop     rsi
0x18004358c  pop     rbp
0x18004358d  retn
```
