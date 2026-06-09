# BingFilterDS::TryGetPreviousCandidateWithSameReading(ushort const *,uint)

- ea: `0x18000a05c`
- end: `0x18000a153`
- name: `?TryGetPreviousCandidateWithSameReading@BingFilterDS@@IEAA?AV?$com_ptr_t@UIMtfSuggestionListElement@@Uerr_exception_policy@wil@@@wil@@PEBGI@Z`
- size: `247`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, const WCHAR *, UINT)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009250`

## callees

- `0x180009a78`
- `0x18000a05c`
- `0x18000ac8c`
- `0x18000c4f2`
- `0x18000e010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18000a0c1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a0c1`

## string_xrefs

- `0x18000a13e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall BingFilterDS::TryGetPreviousCandidateWithSameReading(
        __int64 a1,
        _QWORD *a2,
        const WCHAR *a3,
        UINT a4)
{
  _QWORD *v4; // rbx
  _QWORD *v6; // rdi
  __int64 (__fastcall ***v9)(_QWORD, GUID *, _QWORD *); // rcx
  int v10; // eax
  __int64 (__fastcall ***v11)(_QWORD, GUID *, _QWORD *); // rcx
  int v12; // eax
  int v14; // [rsp+20h] [rbp-88h]
  int v15; // [rsp+30h] [rbp-78h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-70h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v4 = *(_QWORD **)(a1 + 24);
  v6 = *(_QWORD **)(a1 + 32);
  while ( 1 )
  {
    if ( v4 == v6 )
    {
      *a2 = 0;
      return a2;
    }
    memset_0(&v15, 0, 0x48u);
    v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))*v4;
    v15 = 1;
    v10 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *), int *))(*v9)[5])(v9, &v15);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1E2,
        (int)"mincore\\textinput\\dev\\mtf\\datasources\\bingfilterds\\lib\\bingfilterds.cpp",
        (const char *)(unsigned int)v10,
        v14);
    if ( SysStringLen(pbstr) >= a4 && (unsigned __int8)IsPrefixed(a3, a4, pbstr) )
      break;
    ++v4;
  }
  v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))*v4;
  *a2 = 0;
  v12 = (**v11)(v11, &GUID_5f445657_746b_468a_9ebb_ae80a72c4f7a, a2);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v12,
      v14);
  return a2;
}

```

## disassembly

```asm
0x18000a05c  push    rbx
0x18000a05e  push    rbp
0x18000a05f  push    rsi
0x18000a060  push    rdi
0x18000a061  push    r14
0x18000a063  sub     rsp, 80h
0x18000a06a  mov     rbx, [rcx+18h]
0x18000a06e  mov     ebp, r9d
0x18000a071  mov     rdi, [rcx+20h]
0x18000a075  mov     r14, r8
0x18000a078  mov     rsi, rdx
0x18000a07b  cmp     rbx, rdi
0x18000a07e  jz      loc_18000A109
0x18000a084  xor     edx, edx; Val
0x18000a086  lea     rcx, [rsp+0A8h+var_78]; void *
0x18000a08b  lea     r8d, [rdx+48h]; Size
0x18000a08f  call    memset_0
0x18000a094  mov     rcx, [rbx]
0x18000a097  lea     rdx, [rsp+0A8h+var_78]
0x18000a09c  mov     [rsp+0A8h+var_78], 1
0x18000a0a4  mov     rax, [rcx]
0x18000a0a7  mov     rax, [rax+28h]
0x18000a0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0b0  mov     rcx, [rsp+0A8h]; this
0x18000a0b8  test    eax, eax
0x18000a0ba  js      short loc_18000A121
0x18000a0bc  mov     rcx, [rsp+0A8h+pbstr]; pbstr
0x18000a0c1  call    cs:__imp_SysStringLen
0x18000a0c7  cmp     eax, ebp
0x18000a0c9  jb      short loc_18000A0DE
0x18000a0cb  mov     r8, [rsp+0A8h+pbstr]; LPCWSTR
0x18000a0d0  mov     edx, ebp; cchSrc
0x18000a0d2  mov     rcx, r14; lpSrcStr
0x18000a0d5  call    IsPrefixed
0x18000a0da  test    al, al
0x18000a0dc  jnz     short loc_18000A0E4
0x18000a0de  add     rbx, 8
0x18000a0e2  jmp     short loc_18000A07B
0x18000a0e4  mov     rcx, [rbx]
0x18000a0e7  lea     rdx, _GUID_5f445657_746b_468a_9ebb_ae80a72c4f7a
0x18000a0ee  mov     qword ptr [rsi], 0
0x18000a0f5  mov     r8, rsi
0x18000a0f8  mov     rax, [rcx]
0x18000a0fb  mov     rax, [rax]
0x18000a0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a103  test    eax, eax
0x18000a105  js      short loc_18000A136
0x18000a107  jmp     short loc_18000A110
0x18000a109  mov     qword ptr [rsi], 0
0x18000a110  mov     rax, rsi
0x18000a113  add     rsp, 80h
0x18000a11a  pop     r14
0x18000a11c  pop     rdi
0x18000a11d  pop     rsi
0x18000a11e  pop     rbp
0x18000a11f  pop     rbx
0x18000a120  retn
0x18000a121  mov     r9d, eax; char *
0x18000a124  lea     r8, aMincoreTextinp; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18000a12b  mov     edx, 1E2h; void *
0x18000a130  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a136  mov     rcx, [rsp+0A8h]; this
0x18000a13e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a145  mov     r9d, eax; char *
0x18000a148  mov     edx, 1CBEh; void *
0x18000a14d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
