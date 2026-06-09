# UpdateDstPartialMBYVYU(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18001ddb0`
- end: `0x18001de86`
- name: `?UpdateDstPartialMBYVYU@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `214`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180001880`
- `0x18001d3f0`
- `0x18001ddb0`
- `0x180020f45`

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
0x18001ddb0  mov     [rsp+arg_0], rbx
0x18001ddb5  push    rbp
0x18001ddb6  push    rsi
0x18001ddb7  push    rdi
0x18001ddb8  push    r12
0x18001ddba  push    r14
0x18001ddbc  sub     rsp, 250h
0x18001ddc3  mov     rax, cs:__security_cookie
0x18001ddca  xor     rax, rsp
0x18001ddcd  mov     [rsp+278h+var_38], rax
0x18001ddd5  mov     eax, [rsp+278h+arg_30]
0x18001dddc  mov     r11, r9
0x18001dddf  mov     r14d, [rsp+278h+arg_38]
0x18001dde7  mov     r10, r8
0x18001ddea  mov     r9, [rsp+278h+arg_20]; unsigned __int8 *
0x18001ddf2  mov     rbx, rdx
0x18001ddf5  mov     [rsp+278h+var_248], 20h ; ' '; int
0x18001ddfd  mov     r12, rcx
0x18001de00  mov     [rsp+278h+var_250], eax; int
0x18001de04  lea     rcx, [rsp+278h+Src]; unsigned __int8 *
0x18001de09  mov     eax, [rsp+278h+arg_28]
0x18001de10  mov     r8, r11; unsigned __int8 *
0x18001de13  mov     rdx, r10; unsigned __int8 *
0x18001de16  mov     [rsp+278h+var_258], eax; int
0x18001de1a  and     r14d, 0FFFFFFFEh
0x18001de1e  call    ?UpdateDstMBYVYU@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBYVYU(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001de23  xor     esi, esi
0x18001de25  lea     rdi, [rsp+278h+Src]
0x18001de2a  cmp     [rsp+278h+arg_40], esi
0x18001de31  jle     short loc_18001DE5F
0x18001de33  lea     eax, [r14+r14]
0x18001de37  movsxd  rbp, eax
0x18001de3a  mov     r8, rbp; Size
0x18001de3d  mov     rdx, rdi; Src
0x18001de40  mov     rcx, rbx; void *
0x18001de43  call    memcpy_0
0x18001de48  movsxd  rax, dword ptr [r12+40h]
0x18001de4d  add     rdi, 20h ; ' '
0x18001de51  add     rbx, rax
0x18001de54  inc     esi
0x18001de56  cmp     esi, [rsp+278h+arg_40]
0x18001de5d  jl      short loc_18001DE3A
0x18001de5f  mov     rcx, [rsp+278h+var_38]
0x18001de67  xor     rcx, rsp; StackCookie
0x18001de6a  call    __security_check_cookie
0x18001de6f  mov     rbx, [rsp+278h+arg_0]
0x18001de77  add     rsp, 250h
0x18001de7e  pop     r14
0x18001de80  pop     r12
0x18001de82  pop     rdi
0x18001de83  pop     rsi
0x18001de84  pop     rbp
0x18001de85  retn
```
