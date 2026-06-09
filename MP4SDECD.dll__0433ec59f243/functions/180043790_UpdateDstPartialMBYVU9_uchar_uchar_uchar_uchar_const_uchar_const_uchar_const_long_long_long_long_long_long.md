# UpdateDstPartialMBYVU9(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long,long,long)

- ea: `0x180043790`
- end: `0x1800438d9`
- name: `?UpdateDstPartialMBYVU9@@YAXPEAE00PEBE11JJJJJJ@Z`
- size: `329`
- prototype: `void __usercall(unsigned __int8 *@<rcx>, unsigned __int8 *@<rdx>, unsigned __int8 *@<r8>, const unsigned __int8 *@<r9>, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18002aac0`
- `0x180042cf0`
- `0x180043790`
- `0x180045805`

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
0x180043790  push    rbx
0x180043792  push    rbp
0x180043793  push    rsi
0x180043794  push    rdi
0x180043795  push    r12
0x180043797  push    r13
0x180043799  push    r14
0x18004379b  push    r15
0x18004379d  sub     rsp, 198h
0x1800437a4  mov     rax, cs:__security_cookie
0x1800437ab  xor     rax, rsp
0x1800437ae  mov     [rsp+1D8h+var_58], rax
0x1800437b6  mov     r10, [rsp+1D8h+arg_28]
0x1800437be  mov     r12, r8
0x1800437c1  mov     r11, [rsp+1D8h+arg_20]
0x1800437c9  lea     r8, [rsp+1D8h+var_170]; unsigned __int8 *
0x1800437ce  mov     ebp, [rsp+1D8h+arg_50]
0x1800437d5  mov     r15, rdx
0x1800437d8  mov     r13d, [rsp+1D8h+arg_58]
0x1800437e0  lea     rdx, [rsp+1D8h+var_180]; unsigned __int8 *
0x1800437e5  mov     [rsp+1D8h+var_190], 4; int
0x1800437ed  mov     rbx, rcx
0x1800437f0  mov     [rsp+1D8h+var_198], 8; int
0x1800437f8  lea     rcx, [rsp+1D8h+Src]; unsigned __int8 *
0x180043800  and     ebp, 0FFFFFFFCh
0x180043803  and     r13d, 0FFFFFFFCh
0x180043807  mov     eax, ebp
0x180043809  sar     eax, 2
0x18004380c  mov     [rsp+1D8h+var_188], eax
0x180043810  mov     eax, [rsp+1D8h+arg_38]
0x180043817  mov     [rsp+1D8h+var_1A0], eax; int
0x18004381b  mov     eax, [rsp+1D8h+arg_30]
0x180043822  mov     [rsp+1D8h+var_1A8], eax; int
0x180043826  mov     [rsp+1D8h+var_1B0], r10; unsigned __int8 *
0x18004382b  mov     [rsp+1D8h+var_1B8], r11; unsigned __int8 *
0x180043830  call    ?UpdateDstMBYVU9@@YAXPEAE00PEBE11JJJJ@Z; UpdateDstMBYVU9(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x180043835  xor     esi, esi
0x180043837  lea     rdi, [rsp+1D8h+Src]
0x18004383f  test    r13d, r13d
0x180043842  jle     short loc_1800438B5
0x180043844  movsxd  r14, [rsp+1D8h+arg_40]
0x18004384c  movsxd  rbp, ebp
0x18004384f  mov     r8, rbp; Size
0x180043852  mov     rdx, rdi; Src
0x180043855  mov     rcx, rbx; void *
0x180043858  call    memcpy_0
0x18004385d  add     rdi, 10h
0x180043861  add     rbx, r14
0x180043864  inc     esi
0x180043866  cmp     esi, r13d
0x180043869  jl      short loc_18004384F
0x18004386b  movsxd  rbp, [rsp+1D8h+var_188]
0x180043870  lea     rbx, [rsp+1D8h+var_180]
0x180043875  movsxd  r14, [rsp+1D8h+arg_48]
0x18004387d  lea     rdi, [rsp+1D8h+var_170]
0x180043882  xor     esi, esi
0x180043884  mov     r8, rbp; Size
0x180043887  mov     rdx, rbx; Src
0x18004388a  mov     rcx, r15; void *
0x18004388d  call    memcpy_0
0x180043892  mov     r8, rbp; Size
0x180043895  mov     rdx, rdi; Src
0x180043898  mov     rcx, r12; void *
0x18004389b  call    memcpy_0
0x1800438a0  add     rbx, 4
0x1800438a4  add     rdi, 4
0x1800438a8  add     r15, r14
0x1800438ab  add     r12, r14
0x1800438ae  inc     esi
0x1800438b0  cmp     esi, r13d
0x1800438b3  jl      short loc_180043884
0x1800438b5  mov     rcx, [rsp+1D8h+var_58]
0x1800438bd  xor     rcx, rsp; StackCookie
0x1800438c0  call    __security_check_cookie
0x1800438c5  add     rsp, 198h
0x1800438cc  pop     r15
0x1800438ce  pop     r14
0x1800438d0  pop     r13
0x1800438d2  pop     r12
0x1800438d4  pop     rdi
0x1800438d5  pop     rsi
0x1800438d6  pop     rbp
0x1800438d7  pop     rbx
0x1800438d8  retn
```
