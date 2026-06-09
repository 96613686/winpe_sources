# ipx::mtf::CMtfSuggestionClient::SetComplexRanker(IPathEvaluator *)

- ea: `0x18001aa30`
- end: `0x18001aa67`
- name: `?SetComplexRanker@CMtfSuggestionClient@mtf@ipx@@UEAAJPEAUIPathEvaluator@@@Z`
- size: `55`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfSuggestionClient *__hidden this, struct IPathEvaluator *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006074`
- `0x18001aa30`

## pseudocode

```c
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::SetComplexRanker(
        ipx::mtf::CMtfSuggestionClient *this,
        struct IPathEvaluator *a2)
{
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_BYTE *)this + 145) == 2 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7AC,
    (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
    (const char *)0x8000FFFFLL,
    v3);
  return 2147549183LL;
}

```

## disassembly

```asm
0x18001aa30  sub     rsp, 28h
0x18001aa34  cmp     byte ptr [rcx+91h], 2
0x18001aa3b  jz      short loc_18001AA60
0x18001aa3d  mov     rcx, [rsp+28h]; this
0x18001aa42  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001aa49  mov     r9d, 8000FFFFh; char *
0x18001aa4f  mov     edx, 7ACh; void *
0x18001aa54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aa59  mov     eax, 8000FFFFh
0x18001aa5e  jmp     short loc_18001AA62
0x18001aa60  xor     eax, eax
0x18001aa62  add     rsp, 28h
0x18001aa66  retn
```
