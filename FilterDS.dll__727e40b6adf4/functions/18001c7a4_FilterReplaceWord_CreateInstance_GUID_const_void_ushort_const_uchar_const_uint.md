# FilterReplaceWord::CreateInstance(_GUID const &,void * *,ushort const *,uchar const *,uint)

- ea: `0x18001c7a4`
- end: `0x18001c91d`
- name: `?CreateInstance@FilterReplaceWord@@SAJAEBU_GUID@@PEAPEAXPEBGPEBEI@Z`
- size: `377`
- prototype: `__int64 __fastcall(const struct _GUID *, void **, const unsigned __int16 *, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180017840`

## callees

- `0x180001a30`
- `0x180005ca4`
- `0x18001c7a4`
- `0x18001cd28`
- `0x180021816`
- `0x180024010`

## string_xrefs

- `0x18001c881`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplaceword.cpp`
- `0x18001c8d2`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplaceword.cpp`

## pseudocode

```c
__int64 __fastcall FilterReplaceWord::CreateInstance(
        const struct _GUID *a1,
        void **a2,
        const unsigned __int16 *a3,
        const unsigned __int8 *a4,
        unsigned int a5)
{
  int v8; // eax
  const char *v9; // r9
  unsigned int v10; // edi
  FilterReplaceWord *v11; // rax
  FilterReplaceWord *v12; // rbx
  int v13; // eax
  unsigned int v14; // edi
  __int64 result; // rax
  int v16; // eax
  unsigned int v17; // edi
  int v18; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a2 = 0;
  v8 = memcmp_0(&GUID_5b67a2c6_4097_4004_9db9_0c604f924636, &GUID_5b67a2c6_4097_4004_9db9_0c604f924636, 0x10u);
  try
  {
    if ( v8 && memcmp_0(&GUID_5b67a2c6_4097_4004_9db9_0c604f924636, &GUID_0601bcc2_9e20_471d_b612_47900f6c43b2, 0x10u) )
      return (unsigned int)-2147467262;
    v11 = (FilterReplaceWord *)operator new(0x48u);
    v12 = v11;
    if ( v11 )
    {
      *(_QWORD *)v11 = &FilterReplaceWord::`vftable';
      *((_QWORD *)v11 + 4) = 7;
      *((_QWORD *)v11 + 3) = 0;
      *((_WORD *)v11 + 4) = 0;
      *((_QWORD *)v11 + 5) = 0;
      *((_QWORD *)v11 + 6) = 0;
      *((_QWORD *)v11 + 7) = 0;
      *((_DWORD *)v11 + 16) = 0;
      (*(void (__fastcall **)(FilterReplaceWord *))(*(_QWORD *)v11 + 8LL))(v11);
    }
    v13 = FilterReplaceWord::init(v12, a3, a4, a5);
    v14 = v13;
    if ( v13 >= 0 )
    {
      v16 = (**(__int64 (__fastcall ***)(FilterReplaceWord *, GUID *, void **))v12)(
              v12,
              &GUID_5b67a2c6_4097_4004_9db9_0c604f924636,
              a2);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3B,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\filterreplaceword.cpp",
          (const char *)(unsigned int)v16,
          v18);
        (*(void (__fastcall **)(FilterReplaceWord *))(*(_QWORD *)v12 + 16LL))(v12);
        return v17;
      }
      v10 = 0;
      (*(void (__fastcall **)(FilterReplaceWord *))(*(_QWORD *)v12 + 16LL))(v12);
      return v10;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\filterreplaceword.cpp",
      (const char *)(unsigned int)v13,
      v18);
    if ( v12 )
      (*(void (__fastcall **)(FilterReplaceWord *))(*(_QWORD *)v12 + 16LL))(v12);
    result = v14;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x43,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\fil"
                                         "terreplaceword.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x18001c7a4  mov     [rsp+arg_0], rcx
0x18001c7a9  push    rbx
0x18001c7aa  push    rsi
0x18001c7ab  push    rdi
0x18001c7ac  push    r14
0x18001c7ae  sub     rsp, 28h
0x18001c7b2  mov     rdi, r9
0x18001c7b5  mov     r14, r8
0x18001c7b8  mov     rsi, rdx
0x18001c7bb  mov     qword ptr [rdx], 0
0x18001c7c2  mov     ebx, 10h
0x18001c7c7  mov     r8d, ebx; Size
0x18001c7ca  lea     rdx, _GUID_5b67a2c6_4097_4004_9db9_0c604f924636; Buf2
0x18001c7d1  lea     rcx, _GUID_5b67a2c6_4097_4004_9db9_0c604f924636; Buf1
0x18001c7d8  call    memcmp_0
0x18001c7dd  test    eax, eax
0x18001c7df  jz      short loc_18001C805
0x18001c7e1  mov     r8d, ebx; Size
0x18001c7e4  lea     rdx, _GUID_0601bcc2_9e20_471d_b612_47900f6c43b2; Buf2
0x18001c7eb  lea     rcx, _GUID_5b67a2c6_4097_4004_9db9_0c604f924636; Buf1
0x18001c7f2  call    memcmp_0
0x18001c7f7  test    eax, eax
0x18001c7f9  jz      short loc_18001C805
0x18001c7fb  mov     edi, 80004002h
0x18001c800  jmp     loc_18001C90A
0x18001c805  mov     ecx, 48h ; 'H'; Size
0x18001c80a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c80f  mov     rbx, rax
0x18001c812  test    rbx, rbx
0x18001c815  jz      short loc_18001C846
0x18001c817  lea     rax, ??_7FilterReplaceWord@@6B@; const FilterReplaceWord::`vftable'
0x18001c81e  mov     [rbx], rax
0x18001c821  mov     qword ptr [rbx+20h], 7
0x18001c829  mov     qword ptr [rbx+18h], 0
0x18001c831  xor     eax, eax
0x18001c833  mov     [rbx+8], ax
0x18001c837  mov     [rbx+28h], rax
0x18001c83b  mov     [rbx+30h], rax
0x18001c83f  mov     [rbx+38h], rax
0x18001c843  mov     [rbx+40h], eax
0x18001c846  mov     [rsp+48h+arg_0], rbx
0x18001c84b  test    rbx, rbx
0x18001c84e  jz      short loc_18001C860
0x18001c850  mov     rax, [rbx]
0x18001c853  mov     rcx, rbx
0x18001c856  mov     rax, [rax+8]
0x18001c85a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c85f  nop
0x18001c860  mov     r9d, [rsp+48h+arg_20]; unsigned int
0x18001c865  mov     r8, rdi; unsigned __int8 *
0x18001c868  mov     rdx, r14; unsigned __int16 *
0x18001c86b  mov     rcx, rbx; this
0x18001c86e  call    ?init@FilterReplaceWord@@IEAAJPEBGPEBEI@Z; FilterReplaceWord::init(ushort const *,uchar const *,uint)
0x18001c873  mov     edi, eax
0x18001c875  test    eax, eax
0x18001c877  jns     short loc_18001C8AC
0x18001c879  mov     rcx, [rsp+48h]; this
0x18001c87e  mov     r9d, eax; char *
0x18001c881  lea     r8, aMincoreTextinp_12; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18001c888  mov     edx, 3Ah ; ':'; void *
0x18001c88d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c892  nop
0x18001c893  test    rbx, rbx
0x18001c896  jz      short loc_18001C8A8
0x18001c898  mov     rax, [rbx]
0x18001c89b  mov     rcx, rbx
0x18001c89e  mov     rax, [rax+10h]
0x18001c8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8a7  nop
0x18001c8a8  mov     eax, edi
0x18001c8aa  jmp     short loc_18001C912
0x18001c8ac  mov     rax, [rbx]
0x18001c8af  mov     r8, rsi
0x18001c8b2  lea     rdx, _GUID_5b67a2c6_4097_4004_9db9_0c604f924636
0x18001c8b9  mov     rcx, rbx
0x18001c8bc  mov     rax, [rax]
0x18001c8bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8c4  mov     edi, eax
0x18001c8c6  test    eax, eax
0x18001c8c8  jns     short loc_18001C8F8
0x18001c8ca  mov     rcx, [rsp+48h]; this
0x18001c8cf  mov     r9d, eax; char *
0x18001c8d2  lea     r8, aMincoreTextinp_12; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18001c8d9  mov     edx, 3Bh ; ';'; void *
0x18001c8de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c8e3  nop
0x18001c8e4  mov     rcx, [rbx]
0x18001c8e7  mov     rax, [rcx+10h]
0x18001c8eb  mov     rcx, rbx
0x18001c8ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8f3  nop
0x18001c8f4  mov     eax, edi
0x18001c8f6  jmp     short loc_18001C912
0x18001c8f8  xor     edi, edi
0x18001c8fa  mov     rcx, [rbx]
0x18001c8fd  mov     rax, [rcx+10h]
0x18001c901  mov     rcx, rbx
0x18001c904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c909  nop
0x18001c90a  mov     eax, edi
0x18001c90c  jmp     short loc_18001C912
0x18001c90e  mov     eax, dword ptr [rsp+48h+arg_0]
0x18001c912  add     rsp, 28h
0x18001c916  pop     r14
0x18001c918  pop     rdi
0x18001c919  pop     rsi
0x18001c91a  pop     rbx
0x18001c91b  retn
```
