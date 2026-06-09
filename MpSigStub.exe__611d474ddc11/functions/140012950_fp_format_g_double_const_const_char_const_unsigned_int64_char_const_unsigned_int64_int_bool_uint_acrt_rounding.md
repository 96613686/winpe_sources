# fp_format_g(double const * const,char * const,unsigned __int64,char * const,unsigned __int64,int,bool,uint,__acrt_rounding_mode,__crt_cached_ptd_host &)

- ea: `0x140012950`
- end: `0x140012aa2`
- name: `?fp_format_g@@YAHQEBNQEAD_K12H_NIW4__acrt_rounding_mode@@AEAV__crt_cached_ptd_host@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(__int64 *, char *, unsigned __int64, char *, size_t, int, char, unsigned int, int, __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140012bbc`

## callees

- `0x14001253c`
- `0x1400127f8`
- `0x140012950`
- `0x1400165a0`
- `0x1400166b0`

## pseudocode

```c
__int64 __fastcall fp_format_g(
        __int64 *a1,
        char *a2,
        unsigned __int64 a3,
        char *a4,
        size_t a5,
        int a6,
        char a7,
        unsigned int a8,
        int a9,
        __crt_cached_ptd_host *a10)
{
  __int64 v11; // rcx
  int v13; // eax
  int v14; // r15d
  char *v15; // rbx
  __int64 result; // rax
  int v17; // eax
  __int128 v19; // [rsp+40h] [rbp-18h] BYREF

  v11 = *a1;
  v19 = 0;
  v13 = sub_1400166B0(v11, a6, 0, (int)&v19, a4, a5);
  v14 = DWORD1(v19) - 1;
  v15 = &a2[(_DWORD)v19 == 45];
  result = _acrt_fp_strflt_to_string(v15, v13, a9, a10);
  if ( (_DWORD)result )
  {
    *a2 = 0;
  }
  else
  {
    v17 = DWORD1(v19) - 1;
    if ( DWORD1(v19) - 1 < -4 || v17 >= a6 )
    {
      return fp_format_e_internal(a2, a3, a6, a7, a8, (struct _strflt *const)&v19, 1, a10);
    }
    else
    {
      if ( v14 < v17 )
      {
        while ( *v15++ )
          ;
        *(v15 - 2) = 0;
      }
      return fp_format_f_internal(a2, a3, a6, (struct _strflt *const)&v19, 1, a10);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140012950  mov     r11, rsp
0x140012953  mov     [r11+8], rbx
0x140012957  mov     [r11+10h], rbp
0x14001295b  mov     [r11+18h], rdi
0x14001295f  mov     [r11+20h], r14
0x140012963  push    r15
0x140012965  sub     rsp, 50h
0x140012969  mov     rax, [rsp+58h+arg_20]
0x140012971  mov     rbp, r8
0x140012974  mov     rcx, [rcx]; int
0x140012977  mov     rdi, rdx
0x14001297a  mov     edx, [rsp+58h+arg_28]; int
0x140012981  xorps   xmm0, xmm0
0x140012984  mov     [r11-30h], rax
0x140012988  xor     r8d, r8d; int
0x14001298b  mov     [r11-38h], r9
0x14001298f  lea     r9, [r11-18h]; int
0x140012993  movups  [rsp+58h+var_18], xmm0
0x140012998  call    sub_1400166B0
0x14001299d  mov     r15d, dword ptr [rsp+58h+var_18+4]
0x1400129a2  xor     r8d, r8d
0x1400129a5  cmp     dword ptr [rsp+58h+var_18], 2Dh ; '-'
0x1400129aa  mov     r9d, eax
0x1400129ad  mov     eax, [rsp+58h+arg_40]
0x1400129b4  mov     rdx, rbp
0x1400129b7  mov     r14, [rsp+58h+arg_48]
0x1400129bf  setz    r8b
0x1400129c3  sub     rdx, r8
0x1400129c6  mov     [rsp+58h+var_28], r14; __crt_cached_ptd_host *
0x1400129cb  mov     dword ptr [rsp+58h+var_30], eax; int
0x1400129cf  dec     r15d
0x1400129d2  mov     dword ptr [rsp+58h+var_38], r9d; int
0x1400129d7  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x1400129db  lea     rbx, [r8+rdi]
0x1400129df  mov     r8d, [rsp+58h+arg_28]
0x1400129e7  cmovz   rdx, rbp
0x1400129eb  lea     r9, [rsp+58h+var_18]
0x1400129f0  mov     rcx, rbx; Dst
0x1400129f3  call    __acrt_fp_strflt_to_string
0x1400129f8  test    eax, eax
0x1400129fa  jz      short loc_140012A04
0x1400129fc  mov     byte ptr [rdi], 0
0x1400129ff  jmp     loc_140012A87
0x140012a04  mov     eax, dword ptr [rsp+58h+var_18+4]
0x140012a08  dec     eax
0x140012a0a  cmp     eax, 0FFFFFFFCh
0x140012a0d  jl      short loc_140012A4D
0x140012a0f  cmp     eax, [rsp+58h+arg_28]
0x140012a16  jge     short loc_140012A4D
0x140012a18  cmp     r15d, eax
0x140012a1b  jge     short loc_140012A29
0x140012a1d  mov     al, [rbx]
0x140012a1f  inc     rbx
0x140012a22  test    al, al
0x140012a24  jnz     short loc_140012A1D
0x140012a26  mov     [rbx-2], al
0x140012a29  mov     r8d, [rsp+58h+arg_28]; int
0x140012a31  lea     r9, [rsp+58h+var_18]; struct _strflt *
0x140012a36  mov     [rsp+58h+var_30], r14; struct __crt_cached_ptd_host *
0x140012a3b  mov     rdx, rbp; unsigned __int64
0x140012a3e  mov     rcx, rdi; Src
0x140012a41  mov     [rsp+58h+var_38], 1; bool
0x140012a46  call    ?fp_format_f_internal@@YAHQEAD_KHQEAU_strflt@@_NAEAV__crt_cached_ptd_host@@@Z
0x140012a4b  jmp     short loc_140012A87
0x140012a4d  mov     r9b, [rsp+58h+arg_30]; bool
0x140012a55  lea     rax, [rsp+58h+var_18]
0x140012a5a  mov     r8d, [rsp+58h+arg_28]; int
0x140012a62  mov     rdx, rbp; unsigned __int64
0x140012a65  mov     [rsp+58h+var_20], r14; struct __crt_cached_ptd_host *
0x140012a6a  mov     rcx, rdi; char *
0x140012a6d  mov     byte ptr [rsp+58h+var_28], 1; bool
0x140012a72  mov     [rsp+58h+var_30], rax; struct _strflt *
0x140012a77  mov     eax, [rsp+58h+arg_38]
0x140012a7e  mov     dword ptr [rsp+58h+var_38], eax; unsigned int
0x140012a82  call    ?fp_format_e_internal@@YAHQEAD_KH_NIQEAU_strflt@@2AEAV__crt_cached_ptd_host@@@Z
0x140012a87  mov     rbx, [rsp+58h+arg_0]
0x140012a8c  mov     rbp, [rsp+58h+arg_8]
0x140012a91  mov     rdi, [rsp+58h+arg_10]
0x140012a96  mov     r14, [rsp+58h+arg_18]
0x140012a9b  add     rsp, 50h
0x140012a9f  pop     r15
0x140012aa1  retn
```
