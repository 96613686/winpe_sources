# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)

- ea: `0x180002ec4`
- end: `0x180002fc7`
- name: `??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z`
- size: `259`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180003174`

## callees

- `0x180002d84`
- `0x180002de4`
- `0x180002ec4`
- `0x180003284`
- `0x1800032dc`
- `0x180003304`
- `0x18001cf7c`

## string_xrefs

- `0x180002f5c`: `\MDMConfig.dat`
- `0x180002f8f`: `\MDMConfig.dat`

## pseudocode

```c
const void **__fastcall std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
        const void **Src,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  const void *v5; // rbx
  char *v7; // rbp
  __int64 v8; // r14
  unsigned __int64 v9; // r12
  char *v10; // rax
  size_t v11; // r8
  char *v12; // rsi
  char *v13; // r14
  size_t v14; // rbp
  __int64 v15; // r15
  const void *v16; // rbx

  v5 = Src[2];
  if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v5 < a2 )
    std::_Xlen_string();
  v7 = (char *)v5 + a2;
  v8 = std::wstring::_Calculate_growth(Src, (char *)v5 + a2);
  if ( (unsigned __int64)(v8 + 1) > 0x7FFFFFFFFFFFFFFFLL )
    __scrt_throw_std_bad_array_new_length();
  v9 = (unsigned __int64)Src[3];
  v10 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(2 * (v8 + 1));
  v11 = 2LL * (_QWORD)v5;
  Src[2] = v7;
  v12 = v10;
  Src[3] = (const void *)v8;
  v13 = &v10[2 * (_QWORD)v5];
  v14 = 2 * a5;
  v15 = (__int64)v5 + a5;
  if ( v9 <= 7 )
  {
    memcpy_0(v10, Src, v11);
    memcpy_0(v13, L"\\MDMConfig.dat", v14);
    *(_WORD *)&v12[2 * v15] = 0;
  }
  else
  {
    v16 = *Src;
    memcpy_0(v10, *Src, v11);
    memcpy_0(v13, L"\\MDMConfig.dat", v14);
    *(_WORD *)&v12[2 * v15] = 0;
    std::_Deallocate<16>(v16, 2 * v9 + 2);
  }
  *Src = v12;
  return Src;
}

```

## disassembly

```asm
0x180002ec4  push    rbx
0x180002ec6  push    rbp
0x180002ec7  push    rsi
0x180002ec8  push    rdi
0x180002ec9  push    r12
0x180002ecb  push    r14
0x180002ecd  push    r15
0x180002ecf  sub     rsp, 20h
0x180002ed3  mov     rbx, [rcx+10h]
0x180002ed7  mov     rax, 7FFFFFFFFFFFFFFEh
0x180002ee1  sub     rax, rbx
0x180002ee4  mov     rdi, rcx
0x180002ee7  cmp     rax, rdx
0x180002eea  jb      loc_180002FC1
0x180002ef0  lea     rbp, [rbx+rdx]
0x180002ef4  mov     rdx, rbp
0x180002ef7  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBA_K_K@Z; std::wstring::_Calculate_growth(unsigned __int64)
0x180002efc  mov     r14, rax
0x180002eff  lea     rcx, [rax+1]
0x180002f03  mov     rax, 7FFFFFFFFFFFFFFFh
0x180002f0d  cmp     rcx, rax
0x180002f10  ja      loc_180002FBB
0x180002f16  mov     r12, [rdi+18h]
0x180002f1a  add     rcx, rcx
0x180002f1d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180002f22  mov     rdx, [rsp+58h+arg_20]
0x180002f2a  lea     r8, [rbx+rbx]; Size
0x180002f2e  mov     [rdi+10h], rbp
0x180002f32  mov     rsi, rax
0x180002f35  mov     [rdi+18h], r14
0x180002f39  mov     rcx, rax; void *
0x180002f3c  lea     r14, [r8+rax]
0x180002f40  lea     rbp, [rdx+rdx]
0x180002f44  lea     r15, [rbx+rdx]
0x180002f48  cmp     r12, 7
0x180002f4c  jbe     short loc_180002F84
0x180002f4e  mov     rbx, [rdi]
0x180002f51  mov     rdx, rbx; Src
0x180002f54  call    memcpy_0
0x180002f59  mov     r8, rbp; Size
0x180002f5c  lea     rdx, aMdmconfigDat; "\\MDMConfig.dat"
0x180002f63  mov     rcx, r14; void *
0x180002f66  call    memcpy_0
0x180002f6b  xor     eax, eax
0x180002f6d  lea     rdx, ds:2[r12*2]
0x180002f75  mov     rcx, rbx
0x180002f78  mov     [rsi+r15*2], ax
0x180002f7d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180002f82  jmp     short loc_180002FA5
0x180002f84  mov     rdx, rdi; Src
0x180002f87  call    memcpy_0
0x180002f8c  mov     r8, rbp; Size
0x180002f8f  lea     rdx, aMdmconfigDat; "\\MDMConfig.dat"
0x180002f96  mov     rcx, r14; void *
0x180002f99  call    memcpy_0
0x180002f9e  xor     eax, eax
0x180002fa0  mov     [rsi+r15*2], ax
0x180002fa5  mov     [rdi], rsi
0x180002fa8  mov     rax, rdi
0x180002fab  add     rsp, 20h
0x180002faf  pop     r15
0x180002fb1  pop     r14
0x180002fb3  pop     r12
0x180002fb5  pop     rdi
0x180002fb6  pop     rsi
0x180002fb7  pop     rbp
0x180002fb8  pop     rbx
0x180002fb9  retn
0x180002fbb  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x180002fc1  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
