# fp_format_f(double const * const,char * const,unsigned __int64,char * const,unsigned __int64,int,__acrt_rounding_mode,__crt_cached_ptd_host &)

- ea: `0x14001a06c`
- end: `0x14001a141`
- name: `?fp_format_f@@YAHQEBNQEAD_K12HW4__acrt_rounding_mode@@AEAV__crt_cached_ptd_host@@@Z`
- size: `213`
- prototype: `__int64 __fastcall(__int64 *, _BYTE *, __int64, __int64, __int64, int, int, __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001a500`

## callees

- `0x14001a06c`
- `0x14001a144`
- `0x14001f1c4`
- `0x14001f2d4`

## pseudocode

```c
__int64 __fastcall fp_format_f(
        __int64 *a1,
        _BYTE *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7,
        __crt_cached_ptd_host *a8)
{
  __int64 v10; // rcx
  int v11; // eax
  BOOL v12; // r9d
  int v13; // edx
  __int64 result; // rax
  int v15[6]; // [rsp+40h] [rbp-18h] BYREF

  v10 = *a1;
  *(_OWORD *)v15 = 0;
  v11 = sub_14001F2D4(v10, a6, 0, (unsigned int)v15, a4, a5);
  v12 = v15[0] == 45;
  v13 = a3 - v12;
  if ( a3 == -1 )
    v13 = -1;
  result = _acrt_fp_strflt_to_string(v12 + (int)a2, v13, a6 + v15[1], (int)v15, v11, a7, a8);
  if ( !(_DWORD)result )
    return sub_14001A144((int)a2, a3, a6, (int)v15, 0, a8);
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x14001a06c  mov     r11, rsp
0x14001a06f  mov     [r11+8], rbx
0x14001a073  mov     [r11+10h], rbp
0x14001a077  mov     [r11+18h], rsi
0x14001a07b  push    rdi
0x14001a07c  sub     rsp, 50h
0x14001a080  mov     rax, [rsp+58h+arg_20]
0x14001a088  mov     rdi, r8
0x14001a08b  mov     esi, [rsp+58h+arg_28]
0x14001a092  mov     rbx, rdx
0x14001a095  mov     rcx, [rcx]
0x14001a098  xorps   xmm0, xmm0
0x14001a09b  mov     [r11-30h], rax
0x14001a09f  xor     r8d, r8d
0x14001a0a2  mov     [r11-38h], r9
0x14001a0a6  mov     edx, esi
0x14001a0a8  lea     r9, [r11-18h]
0x14001a0ac  movups  xmmword ptr [rsp+58h+var_18], xmm0
0x14001a0b1  call    sub_14001F2D4
0x14001a0b6  mov     r8d, [rsp+58h+var_18+4]
0x14001a0bb  xor     r9d, r9d
0x14001a0be  cmp     [rsp+58h+var_18], 2Dh ; '-'
0x14001a0c3  mov     r10d, eax
0x14001a0c6  mov     eax, [rsp+58h+arg_30]
0x14001a0cd  mov     rdx, rdi
0x14001a0d0  mov     rbp, [rsp+58h+arg_38]
0x14001a0d8  setz    r9b
0x14001a0dc  sub     rdx, r9
0x14001a0df  mov     [rsp+58h+var_28], rbp; __crt_cached_ptd_host *
0x14001a0e4  add     r8d, esi; int
0x14001a0e7  mov     dword ptr [rsp+58h+var_30], eax; int
0x14001a0eb  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14001a0ef  mov     dword ptr [rsp+58h+var_38], r10d; int
0x14001a0f4  lea     rcx, [r9+rbx]; int
0x14001a0f8  cmovz   rdx, rdi; int
0x14001a0fc  lea     r9, [rsp+58h+var_18]; int
0x14001a101  call    __acrt_fp_strflt_to_string
0x14001a106  test    eax, eax
0x14001a108  jz      short loc_14001A10F
0x14001a10a  mov     byte ptr [rbx], 0
0x14001a10d  jmp     short loc_14001A12C
0x14001a10f  mov     [rsp+58h+var_30], rbp; __crt_cached_ptd_host *
0x14001a114  lea     r9, [rsp+58h+var_18]; int
0x14001a119  mov     r8d, esi; int
0x14001a11c  mov     [rsp+58h+var_38], 0; char
0x14001a121  mov     rdx, rdi; int
0x14001a124  mov     rcx, rbx; int
0x14001a127  call    sub_14001A144
0x14001a12c  mov     rbx, [rsp+58h+arg_0]
0x14001a131  mov     rbp, [rsp+58h+arg_8]
0x14001a136  mov     rsi, [rsp+58h+arg_10]
0x14001a13b  add     rsp, 50h
0x14001a13f  pop     rdi
0x14001a140  retn
```
