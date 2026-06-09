# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)

- ea: `0x14000c4a0`
- end: `0x14000c5e9`
- name: `??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z`
- size: `329`
- prototype: `void **(void **Src, unsigned __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x14000cdbc`

## callees

- `0x140001614`
- `0x140002390`
- `0x140002ea8`
- `0x14000c4a0`
- `0x14000fa80`

## string_xrefs

- `0x14000c556`: `\MsMpLics.dll`
- `0x14000c5b0`: `\MsMpLics.dll`

## pseudocode

```c
void **std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
        void **Src,
        unsigned __int64 a2,
        __int64 a3,
        ...)
{
  void *v3; // rbx
  __int64 v4; // r8
  unsigned __int64 v6; // r14
  char *v7; // rbp
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  _QWORD *v10; // rax
  __int64 v11; // rdx
  size_t v12; // r8
  void *v13; // rcx
  _QWORD *v14; // rsi
  char *v15; // r15
  size_t v16; // rbp
  __int64 v17; // r12
  _BYTE *v18; // rbx
  unsigned __int64 v19; // rdx
  _BYTE *v20; // rcx
  void **result; // rax
  __int64 v22; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  __int64 v24; // [rsp+70h] [rbp+28h]
  va_list va1; // [rsp+78h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v22 = va_arg(va1, _QWORD);
  v24 = va_arg(va1, _QWORD);
  v3 = Src[2];
  v4 = 0x7FFFFFFFFFFFFFFELL;
  if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v3 < a2 )
    std::_Xlen_string();
  v6 = (unsigned __int64)Src[3];
  v7 = (char *)v3 + a2;
  v8 = ((unsigned __int64)v3 + a2) | 7;
  if ( v8 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v9 = v6 >> 1;
    if ( v6 <= 0x7FFFFFFFFFFFFFFELL - (v6 >> 1) )
    {
      v4 = v6 + v9;
      if ( v8 >= v6 + v9 )
        v4 = v8;
    }
  }
  v22 = v4;
  v10 = std::wstring::_Allocate_for_capacity<0>(v8, (__int64 *)va);
  v11 = v24;
  v12 = 2LL * (_QWORD)v3;
  v13 = (void *)v22;
  v14 = v10;
  Src[2] = v7;
  Src[3] = v13;
  v15 = (char *)v10 + 2 * (_QWORD)v3;
  v16 = 2 * v11;
  v17 = (__int64)v3 + v11;
  if ( v6 <= 7 )
  {
    memcpy_0(v10, Src, v12);
    memcpy_0(v15, L"\\MsMpLics.dll", v16);
    *((_WORD *)v14 + v17) = 0;
  }
  else
  {
    v18 = *Src;
    memcpy_0(v10, *Src, v12);
    memcpy_0(v15, L"\\MsMpLics.dll", v16);
    v19 = 2 * v6 + 2;
    *((_WORD *)v14 + v17) = 0;
    if ( v19 < 0x1000 )
    {
      v20 = v18;
    }
    else
    {
      v20 = (_BYTE *)*((_QWORD *)v18 - 1);
      if ( (unsigned __int64)(v18 - v20 - 8) > 0x1F )
        __fastfail(5u);
      v19 = 2 * v6 + 41;
    }
    operator delete(v20, v19);
  }
  result = Src;
  *Src = v14;
  return result;
}

```

## disassembly

```asm
0x14000c4a0  mov     [rsp+arg_0], rbx
0x14000c4a5  mov     [rsp+arg_8], rbp
0x14000c4aa  mov     [rsp+arg_18], r9
0x14000c4af  push    rsi
0x14000c4b0  push    rdi
0x14000c4b1  push    r12
0x14000c4b3  push    r14
0x14000c4b5  push    r15
0x14000c4b7  sub     rsp, 20h
0x14000c4bb  mov     rbx, [rcx+10h]
0x14000c4bf  mov     r8, 7FFFFFFFFFFFFFFEh
0x14000c4c9  mov     rax, r8
0x14000c4cc  mov     rdi, rcx
0x14000c4cf  sub     rax, rbx
0x14000c4d2  cmp     rax, rdx
0x14000c4d5  jb      loc_14000C5E3
0x14000c4db  mov     r14, [rcx+18h]
0x14000c4df  lea     rbp, [rbx+rdx]
0x14000c4e3  mov     rcx, rbp
0x14000c4e6  or      rcx, 7
0x14000c4ea  cmp     rcx, r8
0x14000c4ed  ja      short loc_14000C50B
0x14000c4ef  mov     rdx, r14
0x14000c4f2  mov     rax, r8
0x14000c4f5  shr     rdx, 1
0x14000c4f8  sub     rax, rdx
0x14000c4fb  cmp     r14, rax
0x14000c4fe  ja      short loc_14000C50B
0x14000c500  lea     r8, [r14+rdx]
0x14000c504  cmp     rcx, r8
0x14000c507  cmovnb  r8, rcx
0x14000c50b  lea     rdx, [rsp+48h+arg_18]
0x14000c510  mov     [rsp+48h+arg_18], r8
0x14000c515  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x14000c51a  mov     rdx, [rsp+48h+arg_20]
0x14000c51f  lea     r8, [rbx+rbx]; Size
0x14000c523  mov     rcx, [rsp+48h+arg_18]
0x14000c528  mov     rsi, rax
0x14000c52b  mov     [rdi+10h], rbp
0x14000c52f  mov     [rdi+18h], rcx
0x14000c533  lea     r15, [r8+rax]
0x14000c537  lea     rbp, [rdx+rdx]
0x14000c53b  mov     rcx, rax; void *
0x14000c53e  lea     r12, [rbx+rdx]
0x14000c542  cmp     r14, 7
0x14000c546  jbe     short loc_14000C5A5
0x14000c548  mov     rbx, [rdi]
0x14000c54b  mov     rdx, rbx; Src
0x14000c54e  call    memcpy_0
0x14000c553  mov     r8, rbp; Size
0x14000c556  lea     rdx, aMsmplicsDll_0; "\\MsMpLics.dll"
0x14000c55d  mov     rcx, r15; void *
0x14000c560  call    memcpy_0
0x14000c565  xor     eax, eax
0x14000c567  lea     rdx, ds:2[r14*2]; unsigned __int64
0x14000c56f  mov     [rsi+r12*2], ax
0x14000c574  cmp     rdx, 1000h
0x14000c57b  jb      short loc_14000C59B
0x14000c57d  mov     rcx, [rbx-8]
0x14000c581  sub     rbx, rcx
0x14000c584  sub     rbx, 8
0x14000c588  cmp     rbx, 1Fh
0x14000c58c  ja      short loc_14000C594
0x14000c58e  add     rdx, 27h ; '''
0x14000c592  jmp     short loc_14000C59E
0x14000c594  mov     ecx, 5
0x14000c599  int     29h; Win8: RtlFailFast(ecx)
0x14000c59b  mov     rcx, rbx; void *
0x14000c59e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000c5a3  jmp     short loc_14000C5C6
0x14000c5a5  mov     rdx, rdi; Src
0x14000c5a8  call    memcpy_0
0x14000c5ad  mov     r8, rbp; Size
0x14000c5b0  lea     rdx, aMsmplicsDll_0; "\\MsMpLics.dll"
0x14000c5b7  mov     rcx, r15; void *
0x14000c5ba  call    memcpy_0
0x14000c5bf  xor     eax, eax
0x14000c5c1  mov     [rsi+r12*2], ax
0x14000c5c6  mov     rax, rdi
0x14000c5c9  mov     [rax], rsi
0x14000c5cc  mov     rbx, [rsp+48h+arg_0]
0x14000c5d1  mov     rbp, [rsp+48h+arg_8]
0x14000c5d6  add     rsp, 20h
0x14000c5da  pop     r15
0x14000c5dc  pop     r14
0x14000c5de  pop     r12
0x14000c5e0  pop     rdi
0x14000c5e1  pop     rsi
0x14000c5e2  retn
0x14000c5e3  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
