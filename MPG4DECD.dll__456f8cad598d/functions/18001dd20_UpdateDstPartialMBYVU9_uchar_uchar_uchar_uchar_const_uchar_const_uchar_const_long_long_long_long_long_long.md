# UpdateDstPartialMBYVU9(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long,long,long)

- ea: `0x18001dd20`
- end: `0x18001de69`
- name: `?UpdateDstPartialMBYVU9@@YAXPEAE00PEBE11JJJJJJ@Z`
- size: `329`
- prototype: `void __usercall(unsigned __int8 *@<rcx>, unsigned __int8 *@<rdx>, unsigned __int8 *@<r8>, const unsigned __int8 *@<r9>, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800018b0`
- `0x18001d410`
- `0x18001dd20`
- `0x180021005`

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
0x18001dd20  push    rbx
0x18001dd22  push    rbp
0x18001dd23  push    rsi
0x18001dd24  push    rdi
0x18001dd25  push    r12
0x18001dd27  push    r13
0x18001dd29  push    r14
0x18001dd2b  push    r15
0x18001dd2d  sub     rsp, 198h
0x18001dd34  mov     rax, cs:__security_cookie
0x18001dd3b  xor     rax, rsp
0x18001dd3e  mov     [rsp+1D8h+var_58], rax
0x18001dd46  mov     r10, [rsp+1D8h+arg_28]
0x18001dd4e  mov     r12, r8
0x18001dd51  mov     r11, [rsp+1D8h+arg_20]
0x18001dd59  lea     r8, [rsp+1D8h+var_170]; unsigned __int8 *
0x18001dd5e  mov     ebp, [rsp+1D8h+arg_50]
0x18001dd65  mov     r15, rdx
0x18001dd68  mov     r13d, [rsp+1D8h+arg_58]
0x18001dd70  lea     rdx, [rsp+1D8h+var_180]; unsigned __int8 *
0x18001dd75  mov     [rsp+1D8h+var_190], 4; int
0x18001dd7d  mov     rbx, rcx
0x18001dd80  mov     [rsp+1D8h+var_198], 8; int
0x18001dd88  lea     rcx, [rsp+1D8h+Src]; unsigned __int8 *
0x18001dd90  and     ebp, 0FFFFFFFCh
0x18001dd93  and     r13d, 0FFFFFFFCh
0x18001dd97  mov     eax, ebp
0x18001dd99  sar     eax, 2
0x18001dd9c  mov     [rsp+1D8h+var_188], eax
0x18001dda0  mov     eax, [rsp+1D8h+arg_38]
0x18001dda7  mov     [rsp+1D8h+var_1A0], eax; int
0x18001ddab  mov     eax, [rsp+1D8h+arg_30]
0x18001ddb2  mov     [rsp+1D8h+var_1A8], eax; int
0x18001ddb6  mov     [rsp+1D8h+var_1B0], r10; unsigned __int8 *
0x18001ddbb  mov     [rsp+1D8h+var_1B8], r11; unsigned __int8 *
0x18001ddc0  call    ?UpdateDstMBYVU9@@YAXPEAE00PEBE11JJJJ@Z; UpdateDstMBYVU9(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001ddc5  xor     esi, esi
0x18001ddc7  lea     rdi, [rsp+1D8h+Src]
0x18001ddcf  test    r13d, r13d
0x18001ddd2  jle     short loc_18001DE45
0x18001ddd4  movsxd  r14, [rsp+1D8h+arg_40]
0x18001dddc  movsxd  rbp, ebp
0x18001dddf  mov     r8, rbp; Size
0x18001dde2  mov     rdx, rdi; Src
0x18001dde5  mov     rcx, rbx; void *
0x18001dde8  call    memcpy_0
0x18001dded  add     rdi, 10h
0x18001ddf1  add     rbx, r14
0x18001ddf4  inc     esi
0x18001ddf6  cmp     esi, r13d
0x18001ddf9  jl      short loc_18001DDDF
0x18001ddfb  movsxd  rbp, [rsp+1D8h+var_188]
0x18001de00  lea     rbx, [rsp+1D8h+var_180]
0x18001de05  movsxd  r14, [rsp+1D8h+arg_48]
0x18001de0d  lea     rdi, [rsp+1D8h+var_170]
0x18001de12  xor     esi, esi
0x18001de14  mov     r8, rbp; Size
0x18001de17  mov     rdx, rbx; Src
0x18001de1a  mov     rcx, r15; void *
0x18001de1d  call    memcpy_0
0x18001de22  mov     r8, rbp; Size
0x18001de25  mov     rdx, rdi; Src
0x18001de28  mov     rcx, r12; void *
0x18001de2b  call    memcpy_0
0x18001de30  add     rbx, 4
0x18001de34  add     rdi, 4
0x18001de38  add     r15, r14
0x18001de3b  add     r12, r14
0x18001de3e  inc     esi
0x18001de40  cmp     esi, r13d
0x18001de43  jl      short loc_18001DE14
0x18001de45  mov     rcx, [rsp+1D8h+var_58]
0x18001de4d  xor     rcx, rsp; StackCookie
0x18001de50  call    __security_check_cookie
0x18001de55  add     rsp, 198h
0x18001de5c  pop     r15
0x18001de5e  pop     r14
0x18001de60  pop     r13
0x18001de62  pop     r12
0x18001de64  pop     rdi
0x18001de65  pop     rsi
0x18001de66  pop     rbp
0x18001de67  pop     rbx
0x18001de68  retn
```
