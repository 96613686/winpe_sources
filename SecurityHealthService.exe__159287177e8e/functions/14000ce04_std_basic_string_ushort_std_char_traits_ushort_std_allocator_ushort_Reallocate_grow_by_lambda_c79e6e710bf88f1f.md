# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)

- ea: `0x14000ce04`
- end: `0x14000cf91`
- name: `??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z`
- size: `397`
- prototype: `void **__fastcall(void **Src, unsigned __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x14000da08`

## callees

- `0x1400015f4`
- `0x140001b9c`
- `0x14000ce04`
- `0x14000d9c8`
- `0x14000d9f0`
- `0x1400121e0`

## string_xrefs

- `0x14000cf00`: `\MsMpLics.dll`
- `0x14000cf5a`: `\MsMpLics.dll`

## pseudocode

```c
void **__fastcall std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
        void **Src,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  void *v5; // r14
  __int64 v6; // rbx
  unsigned __int64 v8; // r15
  char *v9; // rbp
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  size_t v12; // rcx
  void *v13; // rax
  _QWORD *v14; // rdi
  size_t v15; // r8
  __int64 v16; // r14
  char *v17; // r12
  size_t v18; // rbp
  _BYTE *v19; // rbx
  unsigned __int64 v20; // rdx
  _BYTE *v21; // rcx
  void **result; // rax

  v5 = Src[2];
  v6 = 0x7FFFFFFFFFFFFFFELL;
  if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v5 < a2 )
    std::_Xlen_string();
  v8 = (unsigned __int64)Src[3];
  v9 = (char *)v5 + a2;
  v10 = ((unsigned __int64)v5 + a2) | 7;
  if ( v10 <= 0x7FFFFFFFFFFFFFFELL && (v11 = v8 >> 1, v8 <= 0x7FFFFFFFFFFFFFFELL - (v8 >> 1)) )
  {
    v6 = v10;
    if ( v10 < v8 + v11 )
      v6 = v8 + v11;
    if ( (unsigned __int64)(v6 + 1) > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_25;
    v12 = 2 * (v6 + 1);
    if ( !v12 )
    {
      v14 = 0;
      goto LABEL_15;
    }
  }
  else
  {
    v12 = -2;
  }
  if ( v12 < 0x1000 )
  {
    v14 = operator new(v12);
    goto LABEL_15;
  }
  if ( v12 + 39 < v12 )
LABEL_25:
    __scrt_throw_std_bad_array_new_length();
  v13 = operator new(v12 + 39);
  if ( !v13 )
    goto LABEL_19;
  v14 = (_QWORD *)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v14 - 1) = v13;
LABEL_15:
  v15 = 2LL * (_QWORD)v5;
  v16 = (__int64)v5 + a5;
  Src[2] = v9;
  Src[3] = (void *)v6;
  v17 = (char *)v14 + v15;
  v18 = 2 * a5;
  if ( v8 <= 7 )
  {
    memcpy_0(v14, Src, v15);
    memcpy_0(v17, L"\\MsMpLics.dll", v18);
    *((_WORD *)v14 + v16) = 0;
    goto LABEL_23;
  }
  v19 = *Src;
  memcpy_0(v14, *Src, v15);
  memcpy_0(v17, L"\\MsMpLics.dll", v18);
  v20 = 2 * v8 + 2;
  *((_WORD *)v14 + v16) = 0;
  if ( v20 < 0x1000 )
  {
    v21 = v19;
    goto LABEL_21;
  }
  v21 = (_BYTE *)*((_QWORD *)v19 - 1);
  if ( (unsigned __int64)(v19 - v21 - 8) > 0x1F )
LABEL_19:
    __fastfail(5u);
  v20 = 2 * v8 + 41;
LABEL_21:
  operator delete(v21, v20);
LABEL_23:
  result = Src;
  *Src = v14;
  return result;
}

```

## disassembly

```asm
0x14000ce04  push    rbx
0x14000ce06  push    rbp
0x14000ce07  push    rsi
0x14000ce08  push    rdi
0x14000ce09  push    r12
0x14000ce0b  push    r14
0x14000ce0d  push    r15
0x14000ce0f  sub     rsp, 20h
0x14000ce13  mov     r14, [rcx+10h]
0x14000ce17  mov     rbx, 7FFFFFFFFFFFFFFEh
0x14000ce21  mov     rax, rbx
0x14000ce24  mov     rsi, rcx
0x14000ce27  sub     rax, r14
0x14000ce2a  cmp     rax, rdx
0x14000ce2d  jb      loc_14000CF85
0x14000ce33  mov     r15, [rcx+18h]
0x14000ce37  lea     rbp, [r14+rdx]
0x14000ce3b  mov     rcx, rbp
0x14000ce3e  or      rcx, 7
0x14000ce42  cmp     rcx, rbx
0x14000ce45  ja      short loc_14000CE58
0x14000ce47  mov     rdx, r15
0x14000ce4a  mov     rax, rbx
0x14000ce4d  shr     rdx, 1
0x14000ce50  sub     rax, rdx
0x14000ce53  cmp     r15, rax
0x14000ce56  jbe     short loc_14000CE94
0x14000ce58  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x14000ce5f  cmp     rcx, 1000h
0x14000ce66  jb      short loc_14000CEC2
0x14000ce68  lea     rax, [rcx+27h]
0x14000ce6c  cmp     rax, rcx
0x14000ce6f  jbe     loc_14000CF8B
0x14000ce75  mov     rcx, rax; Size
0x14000ce78  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ce7d  test    rax, rax
0x14000ce80  jz      loc_14000CF3E
0x14000ce86  lea     rdi, [rax+27h]
0x14000ce8a  and     rdi, 0FFFFFFFFFFFFFFE0h
0x14000ce8e  mov     [rdi-8], rax
0x14000ce92  jmp     short loc_14000CECA
0x14000ce94  lea     rax, [r15+rdx]
0x14000ce98  mov     rbx, rcx
0x14000ce9b  cmp     rcx, rax
0x14000ce9e  cmovb   rbx, rax
0x14000cea2  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000ceac  lea     rcx, [rbx+1]
0x14000ceb0  cmp     rcx, rax
0x14000ceb3  ja      loc_14000CF8B
0x14000ceb9  add     rcx, rcx
0x14000cebc  jnz     short loc_14000CE5F
0x14000cebe  xor     edi, edi
0x14000cec0  jmp     short loc_14000CECA
0x14000cec2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000cec7  mov     rdi, rax
0x14000ceca  mov     rdx, [rsp+58h+arg_20]
0x14000ced2  lea     r8, [r14+r14]; Size
0x14000ced6  add     r14, rdx
0x14000ced9  mov     [rsi+10h], rbp
0x14000cedd  mov     [rsi+18h], rbx
0x14000cee1  lea     r12, [r8+rdi]
0x14000cee5  mov     rcx, rdi; void *
0x14000cee8  lea     rbp, [rdx+rdx]
0x14000ceec  cmp     r15, 7
0x14000cef0  jbe     short loc_14000CF4F
0x14000cef2  mov     rbx, [rsi]
0x14000cef5  mov     rdx, rbx; Src
0x14000cef8  call    memcpy_0
0x14000cefd  mov     r8, rbp; Size
0x14000cf00  lea     rdx, aMsmplicsDll_0; "\\MsMpLics.dll"
0x14000cf07  mov     rcx, r12; void *
0x14000cf0a  call    memcpy_0
0x14000cf0f  xor     eax, eax
0x14000cf11  lea     rdx, ds:2[r15*2]; unsigned __int64
0x14000cf19  mov     [rdi+r14*2], ax
0x14000cf1e  cmp     rdx, 1000h
0x14000cf25  jb      short loc_14000CF45
0x14000cf27  mov     rcx, [rbx-8]
0x14000cf2b  sub     rbx, rcx
0x14000cf2e  sub     rbx, 8
0x14000cf32  cmp     rbx, 1Fh
0x14000cf36  ja      short loc_14000CF3E
0x14000cf38  add     rdx, 27h ; '''
0x14000cf3c  jmp     short loc_14000CF48
0x14000cf3e  mov     ecx, 5
0x14000cf43  int     29h; Win8: RtlFailFast(ecx)
0x14000cf45  mov     rcx, rbx; void *
0x14000cf48  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000cf4d  jmp     short loc_14000CF70
0x14000cf4f  mov     rdx, rsi; Src
0x14000cf52  call    memcpy_0
0x14000cf57  mov     r8, rbp; Size
0x14000cf5a  lea     rdx, aMsmplicsDll_0; "\\MsMpLics.dll"
0x14000cf61  mov     rcx, r12; void *
0x14000cf64  call    memcpy_0
0x14000cf69  xor     eax, eax
0x14000cf6b  mov     [rdi+r14*2], ax
0x14000cf70  mov     rax, rsi
0x14000cf73  mov     [rax], rdi
0x14000cf76  add     rsp, 20h
0x14000cf7a  pop     r15
0x14000cf7c  pop     r14
0x14000cf7e  pop     r12
0x14000cf80  pop     rdi
0x14000cf81  pop     rsi
0x14000cf82  pop     rbp
0x14000cf83  pop     rbx
0x14000cf84  retn
0x14000cf85  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x14000cf8b  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
