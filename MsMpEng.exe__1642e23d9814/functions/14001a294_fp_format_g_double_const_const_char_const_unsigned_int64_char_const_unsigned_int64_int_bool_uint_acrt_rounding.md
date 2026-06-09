# fp_format_g(double const * const,char * const,unsigned __int64,char * const,unsigned __int64,int,bool,uint,__acrt_rounding_mode,__crt_cached_ptd_host &)

- ea: `0x14001a294`
- end: `0x14001a3e6`
- name: `?fp_format_g@@YAHQEBNQEAD_K12H_NIW4__acrt_rounding_mode@@AEAV__crt_cached_ptd_host@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(__int64 *, char *, unsigned __int64, __int64, __int64, int, char, unsigned int, int, __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001a500`

## callees

- `0x140019e88`
- `0x14001a144`
- `0x14001a294`
- `0x14001f1c4`
- `0x14001f2d4`

## pseudocode

```c
__int64 __fastcall fp_format_g(
        __int64 *a1,
        char *a2,
        unsigned __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        char a7,
        unsigned int a8,
        int a9,
        __crt_cached_ptd_host *a10)
{
  __int64 v11; // rcx
  int v13; // eax
  _BOOL8 v14; // r8
  int v15; // edx
  int v16; // r15d
  char *v17; // rbx
  __int64 result; // rax
  int v19; // eax
  int v21[6]; // [rsp+40h] [rbp-18h] BYREF

  v11 = *a1;
  *(_OWORD *)v21 = 0;
  v13 = sub_14001F2D4(v11, a6, 0, (unsigned int)v21, a4, a5);
  v14 = v21[0] == 45;
  v15 = a3 - v14;
  v16 = v21[1] - 1;
  v17 = &a2[v14];
  if ( a3 == -1 )
    v15 = -1;
  result = _acrt_fp_strflt_to_string((int)v17, v15, a6, (int)v21, v13, a9, a10);
  if ( (_DWORD)result )
  {
    *a2 = 0;
  }
  else
  {
    v19 = v21[1] - 1;
    if ( v21[1] - 1 < -4 || v19 >= a6 )
    {
      return fp_format_e_internal(a2, a3, a6, a7, a8, (struct _strflt *const)v21, 1, a10);
    }
    else
    {
      if ( v16 < v19 )
      {
        while ( *v17++ )
          ;
        *(v17 - 2) = 0;
      }
      return sub_14001A144((int)a2, a3, a6, (int)v21, 1, a10);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001a294  mov     r11, rsp
0x14001a297  mov     [r11+8], rbx
0x14001a29b  mov     [r11+10h], rbp
0x14001a29f  mov     [r11+18h], rdi
0x14001a2a3  mov     [r11+20h], r14
0x14001a2a7  push    r15
0x14001a2a9  sub     rsp, 50h
0x14001a2ad  mov     rax, [rsp+58h+arg_20]
0x14001a2b5  mov     rbp, r8
0x14001a2b8  mov     rcx, [rcx]
0x14001a2bb  mov     rdi, rdx
0x14001a2be  mov     edx, [rsp+58h+arg_28]
0x14001a2c5  xorps   xmm0, xmm0
0x14001a2c8  mov     [r11-30h], rax
0x14001a2cc  xor     r8d, r8d
0x14001a2cf  mov     [r11-38h], r9
0x14001a2d3  lea     r9, [r11-18h]
0x14001a2d7  movups  xmmword ptr [rsp+58h+var_18], xmm0
0x14001a2dc  call    sub_14001F2D4
0x14001a2e1  mov     r15d, [rsp+58h+var_18+4]
0x14001a2e6  xor     r8d, r8d
0x14001a2e9  cmp     [rsp+58h+var_18], 2Dh ; '-'
0x14001a2ee  mov     r9d, eax
0x14001a2f1  mov     eax, [rsp+58h+arg_40]
0x14001a2f8  mov     rdx, rbp
0x14001a2fb  mov     r14, [rsp+58h+arg_48]
0x14001a303  setz    r8b
0x14001a307  sub     rdx, r8
0x14001a30a  mov     [rsp+58h+var_28], r14; __crt_cached_ptd_host *
0x14001a30f  mov     dword ptr [rsp+58h+var_30], eax; int
0x14001a313  dec     r15d
0x14001a316  mov     dword ptr [rsp+58h+var_38], r9d; int
0x14001a31b  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14001a31f  lea     rbx, [r8+rdi]
0x14001a323  mov     r8d, [rsp+58h+arg_28]; int
0x14001a32b  cmovz   rdx, rbp; int
0x14001a32f  lea     r9, [rsp+58h+var_18]; int
0x14001a334  mov     rcx, rbx; int
0x14001a337  call    __acrt_fp_strflt_to_string
0x14001a33c  test    eax, eax
0x14001a33e  jz      short loc_14001A348
0x14001a340  mov     byte ptr [rdi], 0
0x14001a343  jmp     loc_14001A3CB
0x14001a348  mov     eax, [rsp+58h+var_18+4]
0x14001a34c  dec     eax
0x14001a34e  cmp     eax, 0FFFFFFFCh
0x14001a351  jl      short loc_14001A391
0x14001a353  cmp     eax, [rsp+58h+arg_28]
0x14001a35a  jge     short loc_14001A391
0x14001a35c  cmp     r15d, eax
0x14001a35f  jge     short loc_14001A36D
0x14001a361  mov     al, [rbx]
0x14001a363  inc     rbx
0x14001a366  test    al, al
0x14001a368  jnz     short loc_14001A361
0x14001a36a  mov     [rbx-2], al
0x14001a36d  mov     r8d, [rsp+58h+arg_28]; int
0x14001a375  lea     r9, [rsp+58h+var_18]; int
0x14001a37a  mov     [rsp+58h+var_30], r14; __crt_cached_ptd_host *
0x14001a37f  mov     rdx, rbp; int
0x14001a382  mov     rcx, rdi; int
0x14001a385  mov     [rsp+58h+var_38], 1; char
0x14001a38a  call    sub_14001A144
0x14001a38f  jmp     short loc_14001A3CB
0x14001a391  mov     r9b, [rsp+58h+arg_30]; bool
0x14001a399  lea     rax, [rsp+58h+var_18]
0x14001a39e  mov     r8d, [rsp+58h+arg_28]; int
0x14001a3a6  mov     rdx, rbp; unsigned __int64
0x14001a3a9  mov     [rsp+58h+var_20], r14; struct __crt_cached_ptd_host *
0x14001a3ae  mov     rcx, rdi; char *
0x14001a3b1  mov     byte ptr [rsp+58h+var_28], 1; bool
0x14001a3b6  mov     [rsp+58h+var_30], rax; struct _strflt *
0x14001a3bb  mov     eax, [rsp+58h+arg_38]
0x14001a3c2  mov     dword ptr [rsp+58h+var_38], eax; unsigned int
0x14001a3c6  call    ?fp_format_e_internal@@YAHQEAD_KH_NIQEAU_strflt@@2AEAV__crt_cached_ptd_host@@@Z
0x14001a3cb  mov     rbx, [rsp+58h+arg_0]
0x14001a3d0  mov     rbp, [rsp+58h+arg_8]
0x14001a3d5  mov     rdi, [rsp+58h+arg_10]
0x14001a3da  mov     r14, [rsp+58h+arg_18]
0x14001a3df  add     rsp, 50h
0x14001a3e3  pop     r15
0x14001a3e5  retn
```
