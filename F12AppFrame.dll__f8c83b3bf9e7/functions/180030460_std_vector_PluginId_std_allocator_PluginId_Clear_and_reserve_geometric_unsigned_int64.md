# std::vector<PluginId,std::allocator<PluginId>>::_Clear_and_reserve_geometric(unsigned __int64)

- ea: `0x180030460`
- end: `0x180030588`
- name: `?_Clear_and_reserve_geometric@?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@AEAAX_K@Z`
- size: `296`
- prototype: `char *__fastcall(void **, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002f8e4`

## callees

- `0x180001900`
- `0x18000193c`
- `0x1800056c4`
- `0x1800056ec`
- `0x180030460`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char *__fastcall std::vector<enum PluginId>::_Clear_and_reserve_geometric(void **a1, unsigned __int64 a2, __int64 a3)
{
  _BYTE *v5; // r8
  _BYTE *v6; // rcx
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // r10
  unsigned __int64 v9; // rbx
  _BYTE *v10; // rax
  size_t v11; // rbx
  _QWORD *v12; // rax
  void *v13; // rax
  void *v14; // rcx
  char *result; // rax

  if ( a2 > 0x3FFFFFFFFFFFFFFFLL )
    std::vector<ATL::CComVariant>::_Xlength(a1, a2, a3, a2);
  v5 = a1[2];
  v6 = *a1;
  v7 = (v5 - v6) >> 2;
  v8 = v7 >> 1;
  if ( v7 <= 0x3FFFFFFFFFFFFFFFLL - (v7 >> 1) )
  {
    v9 = v7 + v8;
    if ( v7 + v8 < a2 )
      v9 = a2;
  }
  else
  {
    v9 = 0x3FFFFFFFFFFFFFFFLL;
  }
  if ( v6 )
  {
    if ( (unsigned __int64)(4 * ((v5 - v6) >> 2)) < 0x1000 )
    {
      v10 = v6;
    }
    else
    {
      v10 = (_BYTE *)*((_QWORD *)v6 - 1);
      if ( (unsigned __int64)(v6 - v10 - 8) > 0x1F )
        goto LABEL_18;
    }
    operator delete(v10);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
  if ( v9 > 0x3FFFFFFFFFFFFFFFLL )
LABEL_23:
    __scrt_throw_std_bad_array_new_length();
  v11 = 4 * v9;
  if ( v11 )
  {
    if ( v11 < 0x1000 )
    {
      v12 = operator new(v11);
      goto LABEL_21;
    }
    if ( v11 + 39 >= v11 )
    {
      v13 = operator new(v11 + 39);
      v14 = v13;
      if ( v13 )
      {
        v12 = (_QWORD *)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v12 - 1) = v14;
        goto LABEL_21;
      }
LABEL_18:
      __fastfail(5u);
    }
    goto LABEL_23;
  }
  v12 = 0;
LABEL_21:
  *a1 = v12;
  a1[1] = v12;
  result = (char *)v12 + v11;
  a1[2] = result;
  return result;
}

```

## disassembly

```asm
0x180030460  mov     [rsp+arg_0], rbx
0x180030465  mov     [rsp+arg_8], rbp
0x18003046a  push    rdi
0x18003046b  sub     rsp, 20h
0x18003046f  mov     rbp, 3FFFFFFFFFFFFFFFh
0x180030479  mov     r9, rdx
0x18003047c  mov     rdi, rcx
0x18003047f  cmp     rdx, rbp
0x180030482  ja      loc_18003057C
0x180030488  mov     r8, [rcx+10h]
0x18003048c  mov     rax, rbp
0x18003048f  mov     rcx, [rcx]
0x180030492  mov     rdx, r8
0x180030495  sub     rdx, rcx
0x180030498  sar     rdx, 2
0x18003049c  mov     r10, rdx
0x18003049f  shr     r10, 1
0x1800304a2  sub     rax, r10
0x1800304a5  cmp     rdx, rax
0x1800304a8  jbe     short loc_1800304AF
0x1800304aa  mov     rbx, rbp
0x1800304ad  jmp     short loc_1800304BA
0x1800304af  lea     rbx, [rdx+r10]
0x1800304b3  cmp     rbx, r9
0x1800304b6  cmovb   rbx, r9
0x1800304ba  test    rcx, rcx
0x1800304bd  jz      short loc_180030510
0x1800304bf  sub     r8, rcx
0x1800304c2  sar     r8, 2
0x1800304c6  lea     rdx, ds:0[r8*4]
0x1800304ce  cmp     rdx, 1000h
0x1800304d5  jb      short loc_1800304EE
0x1800304d7  mov     rax, [rcx-8]
0x1800304db  sub     rcx, rax
0x1800304de  sub     rcx, 8
0x1800304e2  cmp     rcx, 1Fh
0x1800304e6  ja      short loc_180030541
0x1800304e8  add     rdx, 27h ; '''
0x1800304ec  jmp     short loc_1800304F1
0x1800304ee  mov     rax, rcx
0x1800304f1  mov     rcx, rax; Block
0x1800304f4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800304f9  mov     qword ptr [rdi], 0
0x180030500  mov     qword ptr [rdi+8], 0
0x180030508  mov     qword ptr [rdi+10h], 0
0x180030510  cmp     rbx, rbp
0x180030513  ja      short loc_180030582
0x180030515  shl     rbx, 2
0x180030519  test    rbx, rbx
0x18003051c  jnz     short loc_180030522
0x18003051e  xor     eax, eax
0x180030520  jmp     short loc_18003055E
0x180030522  cmp     rbx, 1000h
0x180030529  jb      short loc_180030556
0x18003052b  lea     rcx, [rbx+27h]; Size
0x18003052f  cmp     rcx, rbx
0x180030532  jbe     short loc_180030582
0x180030534  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030539  mov     rcx, rax
0x18003053c  test    rax, rax
0x18003053f  jnz     short loc_180030548
0x180030541  mov     ecx, 5
0x180030546  int     29h; Win8: RtlFailFast(ecx)
0x180030548  add     rax, 27h ; '''
0x18003054c  and     rax, 0FFFFFFFFFFFFFFE0h
0x180030550  mov     [rax-8], rcx
0x180030554  jmp     short loc_18003055E
0x180030556  mov     rcx, rbx; Size
0x180030559  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003055e  mov     rbp, [rsp+28h+arg_8]
0x180030563  mov     [rdi], rax
0x180030566  mov     [rdi+8], rax
0x18003056a  add     rax, rbx
0x18003056d  mov     rbx, [rsp+28h+arg_0]
0x180030572  mov     [rdi+10h], rax
0x180030576  add     rsp, 20h
0x18003057a  pop     rdi
0x18003057b  retn
0x18003057c  call    ?_Xlength@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@CAXXZ; std::vector<ATL::CComVariant>::_Xlength(void)
0x180030582  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
