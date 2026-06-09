# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)

- ea: `0x140007ad8`
- end: `0x140007c0f`
- name: `??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z`
- size: `311`
- prototype: `void **__fastcall(void **Src, unsigned __int64, __int64, const void *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140008c48`
- `0x14000a678`

## callees

- `0x1400023b4`
- `0x140007020`
- `0x140007ad8`
- `0x14000a2ac`
- `0x14000ad14`

## pseudocode

```c
void **__fastcall std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
        void **Src,
        unsigned __int64 a2,
        __int64 a3,
        const void *a4,
        __int64 a5)
{
  void *v5; // rbx
  __int64 v6; // r8
  unsigned __int64 v9; // r14
  char *v10; // rbp
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  _QWORD *v13; // rax
  __int64 v14; // rdx
  size_t v15; // r8
  void *v16; // rcx
  _QWORD *v17; // rsi
  char *v18; // r15
  size_t v19; // rbp
  __int64 v20; // r12
  _BYTE *v21; // rbx
  unsigned __int64 v22; // rdx
  _BYTE *v23; // rcx
  void **result; // rax
  __int64 v25; // [rsp+70h] [rbp+8h] BYREF

  v5 = Src[2];
  v6 = 0x7FFFFFFFFFFFFFFELL;
  if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v5 < a2 )
    std::_Xlen_string();
  v9 = (unsigned __int64)Src[3];
  v10 = (char *)v5 + a2;
  v11 = ((unsigned __int64)v5 + a2) | 7;
  if ( v11 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v12 = v9 >> 1;
    if ( v9 <= 0x7FFFFFFFFFFFFFFELL - (v9 >> 1) )
    {
      v6 = v9 + v12;
      if ( v11 >= v9 + v12 )
        v6 = v11;
    }
  }
  v25 = v6;
  v13 = std::wstring::_Allocate_for_capacity<0>(v11, &v25);
  v14 = a5;
  v15 = 2LL * (_QWORD)v5;
  v16 = (void *)v25;
  v17 = v13;
  Src[2] = v10;
  Src[3] = v16;
  v18 = (char *)v13 + 2 * (_QWORD)v5;
  v19 = 2 * v14;
  v20 = (__int64)v5 + v14;
  if ( v9 <= 7 )
  {
    memcpy_0(v13, Src, v15);
    memcpy_0(v18, a4, v19);
    *((_WORD *)v17 + v20) = 0;
  }
  else
  {
    v21 = *Src;
    memcpy_0(v13, *Src, v15);
    memcpy_0(v18, a4, v19);
    v22 = 2 * v9 + 2;
    *((_WORD *)v17 + v20) = 0;
    if ( v22 < 0x1000 )
    {
      v23 = v21;
    }
    else
    {
      v23 = (_BYTE *)*((_QWORD *)v21 - 1);
      if ( (unsigned __int64)(v21 - v23 - 8) > 0x1F )
        __fastfail(5u);
      v22 = 2 * v9 + 41;
    }
    operator delete(v23, v22);
  }
  result = Src;
  *Src = v17;
  return result;
}

```

## disassembly

```asm
0x140007ad8  push    rbx
0x140007ada  push    rbp
0x140007adb  push    rsi
0x140007adc  push    rdi
0x140007add  push    r12
0x140007adf  push    r13
0x140007ae1  push    r14
0x140007ae3  push    r15
0x140007ae5  sub     rsp, 28h
0x140007ae9  mov     rbx, [rcx+10h]
0x140007aed  mov     r8, 7FFFFFFFFFFFFFFEh
0x140007af7  mov     rax, r8
0x140007afa  mov     r13, r9
0x140007afd  sub     rax, rbx
0x140007b00  mov     rdi, rcx
0x140007b03  cmp     rax, rdx
0x140007b06  jb      loc_140007C09
0x140007b0c  mov     r14, [rcx+18h]
0x140007b10  lea     rbp, [rbx+rdx]
0x140007b14  mov     rcx, rbp
0x140007b17  or      rcx, 7
0x140007b1b  cmp     rcx, r8
0x140007b1e  ja      short loc_140007B3C
0x140007b20  mov     rdx, r14
0x140007b23  mov     rax, r8
0x140007b26  shr     rdx, 1
0x140007b29  sub     rax, rdx
0x140007b2c  cmp     r14, rax
0x140007b2f  ja      short loc_140007B3C
0x140007b31  lea     r8, [r14+rdx]
0x140007b35  cmp     rcx, r8
0x140007b38  cmovnb  r8, rcx
0x140007b3c  lea     rdx, [rsp+68h+arg_0]
0x140007b41  mov     [rsp+68h+arg_0], r8
0x140007b46  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x140007b4b  mov     rdx, [rsp+68h+arg_20]
0x140007b53  lea     r8, [rbx+rbx]; Size
0x140007b57  mov     rcx, [rsp+68h+arg_0]
0x140007b5c  mov     rsi, rax
0x140007b5f  mov     [rdi+10h], rbp
0x140007b63  mov     [rdi+18h], rcx
0x140007b67  lea     r15, [r8+rax]
0x140007b6b  lea     rbp, [rdx+rdx]
0x140007b6f  mov     rcx, rax; void *
0x140007b72  lea     r12, [rbx+rdx]
0x140007b76  cmp     r14, 7
0x140007b7a  jbe     short loc_140007BD5
0x140007b7c  mov     rbx, [rdi]
0x140007b7f  mov     rdx, rbx; Src
0x140007b82  call    memcpy_0
0x140007b87  mov     r8, rbp; Size
0x140007b8a  mov     rdx, r13; Src
0x140007b8d  mov     rcx, r15; void *
0x140007b90  call    memcpy_0
0x140007b95  xor     eax, eax
0x140007b97  lea     rdx, ds:2[r14*2]; unsigned __int64
0x140007b9f  mov     [rsi+r12*2], ax
0x140007ba4  cmp     rdx, 1000h
0x140007bab  jb      short loc_140007BCB
0x140007bad  mov     rcx, [rbx-8]
0x140007bb1  sub     rbx, rcx
0x140007bb4  sub     rbx, 8
0x140007bb8  cmp     rbx, 1Fh
0x140007bbc  ja      short loc_140007BC4
0x140007bbe  add     rdx, 27h ; '''
0x140007bc2  jmp     short loc_140007BCE
0x140007bc4  mov     ecx, 5
0x140007bc9  int     29h; Win8: RtlFailFast(ecx)
0x140007bcb  mov     rcx, rbx; void *
0x140007bce  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007bd3  jmp     short loc_140007BF2
0x140007bd5  mov     rdx, rdi; Src
0x140007bd8  call    memcpy_0
0x140007bdd  mov     r8, rbp; Size
0x140007be0  mov     rdx, r13; Src
0x140007be3  mov     rcx, r15; void *
0x140007be6  call    memcpy_0
0x140007beb  xor     eax, eax
0x140007bed  mov     [rsi+r12*2], ax
0x140007bf2  mov     rax, rdi
0x140007bf5  mov     [rax], rsi
0x140007bf8  add     rsp, 28h
0x140007bfc  pop     r15
0x140007bfe  pop     r14
0x140007c00  pop     r13
0x140007c02  pop     r12
0x140007c04  pop     rdi
0x140007c05  pop     rsi
0x140007c06  pop     rbp
0x140007c07  pop     rbx
0x140007c08  retn
0x140007c09  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
