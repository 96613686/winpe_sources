# FilterReplaceWord::CreateInstance(FilterReplaceWord * *,ushort const *,uchar const *,uint)

- ea: `0x18001c924`
- end: `0x18001ca39`
- name: `?CreateInstance@FilterReplaceWord@@SAJPEAPEAV1@PEBGPEBEI@Z`
- size: `277`
- prototype: `__int64 __fastcall(struct FilterReplaceWord **, const unsigned __int16 *, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180018030`

## callees

- `0x180001a30`
- `0x180005ca4`
- `0x18001c924`
- `0x18001cd28`
- `0x180024010`

## string_xrefs

- `0x18001c9c4`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplaceword.cpp`

## pseudocode

```c
__int64 __fastcall FilterReplaceWord::CreateInstance(
        struct FilterReplaceWord **a1,
        const unsigned __int16 *a2,
        const unsigned __int8 *a3,
        unsigned int a4)
{
  FilterReplaceWord *v8; // rax
  FilterReplaceWord *v9; // rbx
  int v10; // eax
  const char *v11; // r9
  unsigned int v12; // edi
  __int64 result; // rax
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 0;
  try
  {
    v8 = (FilterReplaceWord *)operator new(0x48u);
    v9 = v8;
    if ( v8 )
    {
      *(_QWORD *)v8 = &FilterReplaceWord::`vftable';
      *((_QWORD *)v8 + 4) = 7;
      *((_QWORD *)v8 + 3) = 0;
      *((_WORD *)v8 + 4) = 0;
      *((_QWORD *)v8 + 5) = 0;
      *((_QWORD *)v8 + 6) = 0;
      *((_QWORD *)v8 + 7) = 0;
      *((_DWORD *)v8 + 16) = 0;
      (*(void (__fastcall **)(FilterReplaceWord *))(*(_QWORD *)v8 + 8LL))(v8);
    }
    v10 = FilterReplaceWord::init(v9, a2, a3, a4);
    v12 = v10;
    if ( v10 >= 0 )
    {
      if ( v9 )
        (*(void (__fastcall **)(FilterReplaceWord *))(*(_QWORD *)v9 + 8LL))(v9);
      *a1 = v9;
      if ( v9 )
        (*(void (__fastcall **)(FilterReplaceWord *))(*(_QWORD *)v9 + 16LL))(v9);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\filterreplaceword.cpp",
        (const char *)(unsigned int)v10,
        v14);
      if ( v9 )
        (*(void (__fastcall **)(FilterReplaceWord *))(*(_QWORD *)v9 + 16LL))(v9);
      result = v12;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4B,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\fil"
                                         "terreplaceword.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x18001c924  mov     [rsp+arg_8], rbx
0x18001c929  mov     [rsp+arg_10], rsi
0x18001c92e  push    rdi
0x18001c92f  push    r14
0x18001c931  push    r15; int
0x18001c933  sub     rsp, 20h
0x18001c937  mov     edi, r9d
0x18001c93a  mov     r14, r8
0x18001c93d  mov     r15, rdx
0x18001c940  mov     rsi, rcx
0x18001c943  mov     qword ptr [rcx], 0
0x18001c94a  mov     ecx, 48h ; 'H'; Size
0x18001c94f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c954  mov     rbx, rax
0x18001c957  test    rbx, rbx
0x18001c95a  jz      short loc_18001C98B
0x18001c95c  lea     rax, ??_7FilterReplaceWord@@6B@; const FilterReplaceWord::`vftable'
0x18001c963  mov     [rbx], rax
0x18001c966  mov     qword ptr [rbx+20h], 7
0x18001c96e  mov     qword ptr [rbx+18h], 0
0x18001c976  xor     eax, eax
0x18001c978  mov     [rbx+8], ax
0x18001c97c  mov     [rbx+28h], rax
0x18001c980  mov     [rbx+30h], rax
0x18001c984  mov     [rbx+38h], rax
0x18001c988  mov     [rbx+40h], eax
0x18001c98b  mov     [rsp+38h+arg_0], rbx
0x18001c990  test    rbx, rbx
0x18001c993  jz      short loc_18001C9A5
0x18001c995  mov     rax, [rbx]
0x18001c998  mov     rcx, rbx
0x18001c99b  mov     rax, [rax+8]
0x18001c99f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9a4  nop
0x18001c9a5  mov     r9d, edi; unsigned int
0x18001c9a8  mov     r8, r14; unsigned __int8 *
0x18001c9ab  mov     rdx, r15; unsigned __int16 *
0x18001c9ae  mov     rcx, rbx; this
0x18001c9b1  call    ?init@FilterReplaceWord@@IEAAJPEBGPEBEI@Z; FilterReplaceWord::init(ushort const *,uchar const *,uint)
0x18001c9b6  mov     edi, eax
0x18001c9b8  test    eax, eax
0x18001c9ba  jns     short loc_18001C9EF
0x18001c9bc  mov     rcx, [rsp+38h]; this
0x18001c9c1  mov     r9d, eax; char *
0x18001c9c4  lea     r8, aMincoreTextinp_12; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18001c9cb  mov     edx, 49h ; 'I'; void *
0x18001c9d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c9d5  nop
0x18001c9d6  test    rbx, rbx
0x18001c9d9  jz      short loc_18001C9EB
0x18001c9db  mov     rax, [rbx]
0x18001c9de  mov     rcx, rbx
0x18001c9e1  mov     rax, [rax+10h]
0x18001c9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9ea  nop
0x18001c9eb  mov     eax, edi
0x18001c9ed  jmp     short loc_18001CA24
0x18001c9ef  test    rbx, rbx
0x18001c9f2  jz      short loc_18001CA04
0x18001c9f4  mov     rax, [rbx]
0x18001c9f7  mov     rcx, rbx
0x18001c9fa  mov     rax, [rax+8]
0x18001c9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca03  nop
0x18001ca04  mov     [rsi], rbx
0x18001ca07  test    rbx, rbx
0x18001ca0a  jz      short loc_18001CA1C
0x18001ca0c  mov     rax, [rbx]
0x18001ca0f  mov     rcx, rbx
0x18001ca12  mov     rax, [rax+10h]
0x18001ca16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca1b  nop
0x18001ca1c  xor     eax, eax
0x18001ca1e  jmp     short loc_18001CA24
0x18001ca20  mov     eax, dword ptr [rsp+38h+arg_0]
0x18001ca24  mov     rbx, [rsp+38h+arg_8]
0x18001ca29  mov     rsi, [rsp+38h+arg_10]
0x18001ca2e  add     rsp, 20h
0x18001ca32  pop     r15
0x18001ca34  pop     r14
0x18001ca36  pop     rdi
0x18001ca37  retn
```
