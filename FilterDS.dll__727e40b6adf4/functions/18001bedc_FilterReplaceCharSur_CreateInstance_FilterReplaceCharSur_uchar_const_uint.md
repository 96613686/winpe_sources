# FilterReplaceCharSur::CreateInstance(FilterReplaceCharSur * *,uchar const *,uint)

- ea: `0x18001bedc`
- end: `0x18001bfd2`
- name: `?CreateInstance@FilterReplaceCharSur@@SAJPEAPEAV1@PEBEI@Z`
- size: `246`
- prototype: `__int64 __fastcall(struct FilterReplaceCharSur **, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180018510`

## callees

- `0x180001a30`
- `0x180005ca4`
- `0x18001b410`
- `0x18001bedc`
- `0x180024010`

## string_xrefs

- `0x18001bf67`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplacecharsur.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FilterReplaceCharSur::CreateInstance(
        struct FilterReplaceCharSur **a1,
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
      *(_QWORD *)v6 = &FilterReplaceCharSur::`vftable';
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
        (void *)0x4B,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\filterreplacecharsur.cpp",
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
                           (void *)0x4D,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\fil"
                                         "terreplacecharsur.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x18001bedc  push    rbx
0x18001bede  push    rsi
0x18001bedf  push    rdi
0x18001bee0  push    r14
0x18001bee2  sub     rsp, 28h
0x18001bee6  mov     edi, r8d
0x18001bee9  mov     r14, rdx
0x18001beec  mov     rsi, rcx
0x18001beef  mov     qword ptr [rcx], 0
0x18001bef6  mov     ecx, 28h ; '('; Size
0x18001befb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bf00  mov     rbx, rax
0x18001bf03  test    rbx, rbx
0x18001bf06  jz      short loc_18001BF31
0x18001bf08  lea     rax, ??_7FilterReplaceCharSur@@6B@; const FilterReplaceCharSur::`vftable'
0x18001bf0f  mov     [rbx], rax
0x18001bf12  mov     qword ptr [rbx+8], 0
0x18001bf1a  mov     qword ptr [rbx+10h], 0
0x18001bf22  mov     qword ptr [rbx+18h], 0
0x18001bf2a  mov     dword ptr [rbx+20h], 0
0x18001bf31  mov     [rsp+48h+arg_0], rbx
0x18001bf36  test    rbx, rbx
0x18001bf39  jz      short loc_18001BF4B
0x18001bf3b  mov     rax, [rbx]
0x18001bf3e  mov     rcx, rbx
0x18001bf41  mov     rax, [rax+8]
0x18001bf45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf4a  nop
0x18001bf4b  mov     r8d, edi; unsigned int
0x18001bf4e  mov     rdx, r14; unsigned __int8 *
0x18001bf51  mov     rcx, rbx; this
0x18001bf54  call    ?init@FilterChar@@IEAAJPEBEI@Z; FilterChar::init(uchar const *,uint)
0x18001bf59  mov     edi, eax
0x18001bf5b  test    eax, eax
0x18001bf5d  jns     short loc_18001BF92
0x18001bf5f  mov     rcx, [rsp+48h]; this
0x18001bf64  mov     r9d, eax; char *
0x18001bf67  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18001bf6e  mov     edx, 4Bh ; 'K'; void *
0x18001bf73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bf78  nop
0x18001bf79  test    rbx, rbx
0x18001bf7c  jz      short loc_18001BF8E
0x18001bf7e  mov     rax, [rbx]
0x18001bf81  mov     rcx, rbx
0x18001bf84  mov     rax, [rax+10h]
0x18001bf88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf8d  nop
0x18001bf8e  mov     eax, edi
0x18001bf90  jmp     short loc_18001BFC7
0x18001bf92  test    rbx, rbx
0x18001bf95  jz      short loc_18001BFA7
0x18001bf97  mov     rax, [rbx]
0x18001bf9a  mov     rcx, rbx
0x18001bf9d  mov     rax, [rax+8]
0x18001bfa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfa6  nop
0x18001bfa7  mov     [rsi], rbx
0x18001bfaa  test    rbx, rbx
0x18001bfad  jz      short loc_18001BFBF
0x18001bfaf  mov     rax, [rbx]
0x18001bfb2  mov     rcx, rbx
0x18001bfb5  mov     rax, [rax+10h]
0x18001bfb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfbe  nop
0x18001bfbf  xor     eax, eax
0x18001bfc1  jmp     short loc_18001BFC7
0x18001bfc3  mov     eax, dword ptr [rsp+48h+arg_0]
0x18001bfc7  add     rsp, 28h
0x18001bfcb  pop     r14
0x18001bfcd  pop     rdi
0x18001bfce  pop     rsi
0x18001bfcf  pop     rbx
0x18001bfd0  retn
```
