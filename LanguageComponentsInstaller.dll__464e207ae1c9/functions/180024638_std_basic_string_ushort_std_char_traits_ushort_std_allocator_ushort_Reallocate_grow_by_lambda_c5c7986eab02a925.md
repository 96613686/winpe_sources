# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Reallocate_grow_by<_lambda_c5c7986eab02a925bb28d3483355880c_,unsigned __int64,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c5c7986eab02a925bb28d3483355880c_,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180024638`
- end: `0x18002475e`
- name: `??$_Reallocate_grow_by@V_lambda_c5c7986eab02a925bb28d3483355880c_@@_KPEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c5c7986eab02a925bb28d3483355880c_@@_KPEBG2@Z`
- size: `294`
- prototype: `const void **__fastcall(const void **Src, unsigned __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002502c`

## callees

- `0x180003a34`
- `0x180004100`
- `0x1800058dc`
- `0x18000a844`
- `0x180024638`

## string_xrefs

- `0x1800246bf`: `SOFTWARE\Microsoft\Windows\CurrentVersion\LanguageComponentsInstaller\InstallResults\`

## pseudocode

```c
const void **__fastcall std::wstring::_Reallocate_grow_by<_lambda_c5c7986eab02a925bb28d3483355880c_,unsigned __int64,unsigned short const *,unsigned __int64>(
        const void **Src,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  const void *v6; // rbx
  __int64 v8; // rcx
  unsigned __int64 v9; // r14
  char *v10; // rbp
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // r8
  _QWORD *v13; // rax
  _QWORD *v14; // rsi
  size_t v15; // rbp
  size_t v16; // r8
  char *v17; // r15
  const void *v18; // rbx
  _BYTE *v19; // rcx
  const void **result; // rax
  __int64 v21[7]; // [rsp+20h] [rbp-38h] BYREF

  v6 = Src[2];
  v8 = 0x7FFFFFFFFFFFFFFELL;
  if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v6 < a2 )
    std::_Xlen_string();
  v9 = (unsigned __int64)Src[3];
  v10 = (char *)v6 + a2;
  v11 = ((unsigned __int64)v6 + a2) | 7;
  if ( v11 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v12 = v9 >> 1;
    if ( v9 <= 0x7FFFFFFFFFFFFFFELL - (v9 >> 1) )
    {
      v8 = v9 + v12;
      if ( v11 >= v9 + v12 )
        v8 = v11;
    }
  }
  v21[0] = v8;
  v13 = std::wstring::_Allocate_for_capacity<0>(v8, v21);
  Src[2] = v10;
  v14 = v13;
  v15 = 2LL * (_QWORD)v6 + 2;
  Src[3] = (const void *)v21[0];
  v16 = 2 * a6;
  v17 = (char *)v13 + 2 * a6;
  if ( v9 <= 7 )
  {
    memcpy_0(v13, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\LanguageComponentsInstaller\\InstallResults\\", v16);
    memcpy_0(v17, Src, 2LL * (_QWORD)v6 + 2);
  }
  else
  {
    v18 = *Src;
    memcpy_0(v13, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\LanguageComponentsInstaller\\InstallResults\\", v16);
    memcpy_0(v17, v18, v15);
    if ( 2 * v9 + 2 < 0x1000 )
    {
      v19 = v18;
    }
    else
    {
      v19 = (_BYTE *)*((_QWORD *)v18 - 1);
      if ( (unsigned __int64)((_BYTE *)v18 - v19 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v19);
  }
  result = Src;
  *Src = v14;
  return result;
}

```

## disassembly

```asm
0x180024638  mov     [rsp+arg_10], rbx
0x18002463d  push    rbp
0x18002463e  push    rsi
0x18002463f  push    rdi
0x180024640  push    r14
0x180024642  push    r15
0x180024644  sub     rsp, 30h
0x180024648  mov     rbx, [rcx+10h]
0x18002464c  mov     rdi, rcx
0x18002464f  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180024659  mov     rax, rcx
0x18002465c  sub     rax, rbx
0x18002465f  cmp     rax, rdx
0x180024662  jb      loc_180024758
0x180024668  mov     r14, [rdi+18h]
0x18002466c  lea     rbp, [rbx+rdx]
0x180024670  mov     rdx, rbp
0x180024673  or      rdx, 7
0x180024677  cmp     rdx, rcx
0x18002467a  ja      short loc_180024698
0x18002467c  mov     r8, r14
0x18002467f  mov     rax, rcx
0x180024682  shr     r8, 1
0x180024685  sub     rax, r8
0x180024688  cmp     r14, rax
0x18002468b  ja      short loc_180024698
0x18002468d  lea     rcx, [r14+r8]
0x180024691  cmp     rdx, rcx
0x180024694  cmovnb  rcx, rdx
0x180024698  lea     rdx, [rsp+58h+var_38]
0x18002469d  mov     [rsp+58h+var_38], rcx
0x1800246a2  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x1800246a7  mov     [rdi+10h], rbp
0x1800246ab  mov     rsi, rax
0x1800246ae  mov     rax, [rsp+58h+var_38]
0x1800246b3  lea     rbp, ds:2[rbx*2]
0x1800246bb  mov     [rdi+18h], rax
0x1800246bf  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800246c6  mov     rax, [rsp+58h+arg_28]
0x1800246ce  mov     rcx, rsi; void *
0x1800246d1  lea     r8, [rax+rax]; Size
0x1800246d5  lea     r15, [r8+rsi]
0x1800246d9  cmp     r14, 7
0x1800246dd  jbe     short loc_18002472E
0x1800246df  mov     rbx, [rdi]
0x1800246e2  call    memcpy_0
0x1800246e7  mov     r8, rbp; Size
0x1800246ea  mov     rdx, rbx; Src
0x1800246ed  mov     rcx, r15; void *
0x1800246f0  call    memcpy_0
0x1800246f5  lea     rdx, ds:2[r14*2]
0x1800246fd  cmp     rdx, 1000h
0x180024704  jb      short loc_180024724
0x180024706  mov     rcx, [rbx-8]
0x18002470a  sub     rbx, rcx
0x18002470d  sub     rbx, 8
0x180024711  cmp     rbx, 1Fh
0x180024715  ja      short loc_18002471D
0x180024717  add     rdx, 27h ; '''
0x18002471b  jmp     short loc_180024727
0x18002471d  mov     ecx, 5
0x180024722  int     29h; Win8: RtlFailFast(ecx)
0x180024724  mov     rcx, rbx; Block
0x180024727  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002472c  jmp     short loc_180024741
0x18002472e  call    memcpy_0
0x180024733  mov     r8, rbp; Size
0x180024736  mov     rdx, rdi; Src
0x180024739  mov     rcx, r15; void *
0x18002473c  call    memcpy_0
0x180024741  mov     rax, rdi
0x180024744  mov     [rax], rsi
0x180024747  mov     rbx, [rsp+58h+arg_10]
0x18002474c  add     rsp, 30h
0x180024750  pop     r15
0x180024752  pop     r14
0x180024754  pop     rdi
0x180024755  pop     rsi
0x180024756  pop     rbp
0x180024757  retn
0x180024758  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
