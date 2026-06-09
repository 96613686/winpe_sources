# FilterReplaceChar::CreateInstance(FilterReplaceChar * *,uchar const *,uint)

- ea: `0x18001dd58`
- end: `0x18001de4e`
- name: `?CreateInstance@FilterReplaceChar@@SAJPEAPEAV1@PEBEI@Z`
- size: `246`
- prototype: `__int64 __fastcall(struct FilterReplaceChar **, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180018510`

## callees

- `0x180001a30`
- `0x180005ca4`
- `0x18001b410`
- `0x18001dd58`
- `0x180024010`

## string_xrefs

- `0x18001dde3`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplacechar.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FilterReplaceChar::CreateInstance(
        struct FilterReplaceChar **a1,
        const unsigned __int8 *a2,
        unsigned int a3)
{
  FilterChar *v6; // rbx
  int v7; // eax
  const char *v8; // r9
  unsigned int v9; // edi
  __int64 result; // rax
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  try
  {
    v6 = (FilterChar *)operator new(0x28u);
    if ( v6 )
    {
      *(_QWORD *)v6 = &FilterReplaceChar::`vftable';
      *((_QWORD *)v6 + 1) = 0;
      *((_QWORD *)v6 + 2) = 0;
      *((_QWORD *)v6 + 3) = 0;
      *((_DWORD *)v6 + 8) = 0;
      (*(void (__fastcall **)(FilterChar *))(*(_QWORD *)v6 + 8LL))(v6);
    }
    v7 = FilterChar::init(v6, a2, a3);
    v9 = v7;
    if ( v7 >= 0 )
    {
      if ( v6 )
        (*(void (__fastcall **)(FilterChar *))(*(_QWORD *)v6 + 8LL))(v6);
      *a1 = v6;
      if ( v6 )
        (*(void (__fastcall **)(FilterChar *))(*(_QWORD *)v6 + 16LL))(v6);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\filterreplacechar.cpp",
        (const char *)(unsigned int)v7,
        v11);
      if ( v6 )
        (*(void (__fastcall **)(FilterChar *))(*(_QWORD *)v6 + 16LL))(v6);
      result = v9;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4E,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\fil"
                                         "terreplacechar.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x18001dd58  push    rbx
0x18001dd5a  push    rsi
0x18001dd5b  push    rdi
0x18001dd5c  push    r14
0x18001dd5e  sub     rsp, 28h
0x18001dd62  mov     edi, r8d
0x18001dd65  mov     r14, rdx
0x18001dd68  mov     rsi, rcx
0x18001dd6b  mov     qword ptr [rcx], 0
0x18001dd72  mov     ecx, 28h ; '('; Size
0x18001dd77  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dd7c  mov     rbx, rax
0x18001dd7f  test    rbx, rbx
0x18001dd82  jz      short loc_18001DDAD
0x18001dd84  lea     rax, ??_7FilterReplaceChar@@6B@; const FilterReplaceChar::`vftable'
0x18001dd8b  mov     [rbx], rax
0x18001dd8e  mov     qword ptr [rbx+8], 0
0x18001dd96  mov     qword ptr [rbx+10h], 0
0x18001dd9e  mov     qword ptr [rbx+18h], 0
0x18001dda6  mov     dword ptr [rbx+20h], 0
0x18001ddad  mov     [rsp+48h+arg_0], rbx
0x18001ddb2  test    rbx, rbx
0x18001ddb5  jz      short loc_18001DDC7
0x18001ddb7  mov     rax, [rbx]
0x18001ddba  mov     rcx, rbx
0x18001ddbd  mov     rax, [rax+8]
0x18001ddc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddc6  nop
0x18001ddc7  mov     r8d, edi; unsigned int
0x18001ddca  mov     rdx, r14; unsigned __int8 *
0x18001ddcd  mov     rcx, rbx; this
0x18001ddd0  call    ?init@FilterChar@@IEAAJPEBEI@Z; FilterChar::init(uchar const *,uint)
0x18001ddd5  mov     edi, eax
0x18001ddd7  test    eax, eax
0x18001ddd9  jns     short loc_18001DE0E
0x18001dddb  mov     rcx, [rsp+48h]; this
0x18001dde0  mov     r9d, eax; char *
0x18001dde3  lea     r8, aMincoreTextinp_23; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18001ddea  mov     edx, 4Ch ; 'L'; void *
0x18001ddef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ddf4  nop
0x18001ddf5  test    rbx, rbx
0x18001ddf8  jz      short loc_18001DE0A
0x18001ddfa  mov     rax, [rbx]
0x18001ddfd  mov     rcx, rbx
0x18001de00  mov     rax, [rax+10h]
0x18001de04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de09  nop
0x18001de0a  mov     eax, edi
0x18001de0c  jmp     short loc_18001DE43
0x18001de0e  test    rbx, rbx
0x18001de11  jz      short loc_18001DE23
0x18001de13  mov     rax, [rbx]
0x18001de16  mov     rcx, rbx
0x18001de19  mov     rax, [rax+8]
0x18001de1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de22  nop
0x18001de23  mov     [rsi], rbx
0x18001de26  test    rbx, rbx
0x18001de29  jz      short loc_18001DE3B
0x18001de2b  mov     rax, [rbx]
0x18001de2e  mov     rcx, rbx
0x18001de31  mov     rax, [rax+10h]
0x18001de35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de3a  nop
0x18001de3b  xor     eax, eax
0x18001de3d  jmp     short loc_18001DE43
0x18001de3f  mov     eax, dword ptr [rsp+48h+arg_0]
0x18001de43  add     rsp, 28h
0x18001de47  pop     r14
0x18001de49  pop     rdi
0x18001de4a  pop     rsi
0x18001de4b  pop     rbx
0x18001de4c  retn
```
