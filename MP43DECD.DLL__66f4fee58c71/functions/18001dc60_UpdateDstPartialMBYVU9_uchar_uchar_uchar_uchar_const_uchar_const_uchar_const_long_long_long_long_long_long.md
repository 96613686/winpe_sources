# UpdateDstPartialMBYVU9(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long,long,long)

- ea: `0x18001dc60`
- end: `0x18001dda9`
- name: `?UpdateDstPartialMBYVU9@@YAXPEAE00PEBE11JJJJJJ@Z`
- size: `329`
- prototype: `void __usercall(unsigned __int8 *@<rcx>, unsigned __int8 *@<rdx>, unsigned __int8 *@<r8>, const unsigned __int8 *@<r9>, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180001880`
- `0x18001d350`
- `0x18001dc60`
- `0x180020f45`

## pseudocode

```c
void __fastcall UpdateDstPartialMBYVU9(
        unsigned __int8 *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        const unsigned __int8 *a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12)
{
  signed int v15; // r13d
  signed int v16; // esi
  unsigned __int8 *v17; // rdi
  unsigned __int8 *v18; // rbx
  unsigned __int8 *v19; // rdi
  signed int v20; // esi
  int v21; // [rsp+50h] [rbp-188h]
  unsigned __int8 v22[16]; // [rsp+58h] [rbp-180h] BYREF
  unsigned __int8 v23[24]; // [rsp+68h] [rbp-170h] BYREF
  unsigned __int8 Src[256]; // [rsp+80h] [rbp-158h] BYREF

  v15 = a12 & 0xFFFFFFFC;
  UpdateDstMBYVU9(Src, v22, v23, a4, a5, a6, a7, a8, 8, 4);
  v16 = 0;
  v17 = Src;
  if ( (int)(a12 & 0xFFFFFFFC) > 0 )
  {
    do
    {
      memcpy_0(a1, v17, (int)(a11 & 0xFFFFFFFC));
      v17 += 16;
      a1 += a9;
      ++v16;
    }
    while ( v16 < v15 );
    v21 = (int)(a11 & 0xFFFFFFFC) >> 2;
    v18 = v22;
    v19 = v23;
    v20 = 0;
    do
    {
      memcpy_0(a2, v18, v21);
      memcpy_0(a3, v19, v21);
      v18 += 4;
      v19 += 4;
      a2 += a10;
      a3 += a10;
      ++v20;
    }
    while ( v20 < v15 );
  }
}

```

## disassembly

```asm
0x18001dc60  push    rbx
0x18001dc62  push    rbp
0x18001dc63  push    rsi
0x18001dc64  push    rdi
0x18001dc65  push    r12
0x18001dc67  push    r13
0x18001dc69  push    r14
0x18001dc6b  push    r15
0x18001dc6d  sub     rsp, 198h
0x18001dc74  mov     rax, cs:__security_cookie
0x18001dc7b  xor     rax, rsp
0x18001dc7e  mov     [rsp+1D8h+var_58], rax
0x18001dc86  mov     r10, [rsp+1D8h+arg_28]
0x18001dc8e  mov     r12, r8
0x18001dc91  mov     r11, [rsp+1D8h+arg_20]
0x18001dc99  lea     r8, [rsp+1D8h+var_170]; unsigned __int8 *
0x18001dc9e  mov     ebp, [rsp+1D8h+arg_50]
0x18001dca5  mov     r15, rdx
0x18001dca8  mov     r13d, [rsp+1D8h+arg_58]
0x18001dcb0  lea     rdx, [rsp+1D8h+var_180]; unsigned __int8 *
0x18001dcb5  mov     [rsp+1D8h+var_190], 4; int
0x18001dcbd  mov     rbx, rcx
0x18001dcc0  mov     [rsp+1D8h+var_198], 8; int
0x18001dcc8  lea     rcx, [rsp+1D8h+Src]; unsigned __int8 *
0x18001dcd0  and     ebp, 0FFFFFFFCh
0x18001dcd3  and     r13d, 0FFFFFFFCh
0x18001dcd7  mov     eax, ebp
0x18001dcd9  sar     eax, 2
0x18001dcdc  mov     [rsp+1D8h+var_188], eax
0x18001dce0  mov     eax, [rsp+1D8h+arg_38]
0x18001dce7  mov     [rsp+1D8h+var_1A0], eax; int
0x18001dceb  mov     eax, [rsp+1D8h+arg_30]
0x18001dcf2  mov     [rsp+1D8h+var_1A8], eax; int
0x18001dcf6  mov     [rsp+1D8h+var_1B0], r10; unsigned __int8 *
0x18001dcfb  mov     [rsp+1D8h+var_1B8], r11; unsigned __int8 *
0x18001dd00  call    ?UpdateDstMBYVU9@@YAXPEAE00PEBE11JJJJ@Z; UpdateDstMBYVU9(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001dd05  xor     esi, esi
0x18001dd07  lea     rdi, [rsp+1D8h+Src]
0x18001dd0f  test    r13d, r13d
0x18001dd12  jle     short loc_18001DD85
0x18001dd14  movsxd  r14, [rsp+1D8h+arg_40]
0x18001dd1c  movsxd  rbp, ebp
0x18001dd1f  mov     r8, rbp; Size
0x18001dd22  mov     rdx, rdi; Src
0x18001dd25  mov     rcx, rbx; void *
0x18001dd28  call    memcpy_0
0x18001dd2d  add     rdi, 10h
0x18001dd31  add     rbx, r14
0x18001dd34  inc     esi
0x18001dd36  cmp     esi, r13d
0x18001dd39  jl      short loc_18001DD1F
0x18001dd3b  movsxd  rbp, [rsp+1D8h+var_188]
0x18001dd40  lea     rbx, [rsp+1D8h+var_180]
0x18001dd45  movsxd  r14, [rsp+1D8h+arg_48]
0x18001dd4d  lea     rdi, [rsp+1D8h+var_170]
0x18001dd52  xor     esi, esi
0x18001dd54  mov     r8, rbp; Size
0x18001dd57  mov     rdx, rbx; Src
0x18001dd5a  mov     rcx, r15; void *
0x18001dd5d  call    memcpy_0
0x18001dd62  mov     r8, rbp; Size
0x18001dd65  mov     rdx, rdi; Src
0x18001dd68  mov     rcx, r12; void *
0x18001dd6b  call    memcpy_0
0x18001dd70  add     rbx, 4
0x18001dd74  add     rdi, 4
0x18001dd78  add     r15, r14
0x18001dd7b  add     r12, r14
0x18001dd7e  inc     esi
0x18001dd80  cmp     esi, r13d
0x18001dd83  jl      short loc_18001DD54
0x18001dd85  mov     rcx, [rsp+1D8h+var_58]
0x18001dd8d  xor     rcx, rsp; StackCookie
0x18001dd90  call    __security_check_cookie
0x18001dd95  add     rsp, 198h
0x18001dd9c  pop     r15
0x18001dd9e  pop     r14
0x18001dda0  pop     r13
0x18001dda2  pop     r12
0x18001dda4  pop     rdi
0x18001dda5  pop     rsi
0x18001dda6  pop     rbp
0x18001dda7  pop     rbx
0x18001dda8  retn
```
