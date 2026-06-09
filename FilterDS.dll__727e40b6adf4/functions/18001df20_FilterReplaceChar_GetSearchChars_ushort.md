# FilterReplaceChar::GetSearchChars(ushort * *)

- ea: `0x18001df20`
- end: `0x18001dfb6`
- name: `?GetSearchChars@FilterReplaceChar@@UEAAJPEAPEAG@Z`
- size: `150`
- prototype: `__int64 __fastcall(FilterReplaceChar *this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005ca4`
- `0x18001df20`
- `0x18001dfbc`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001dfa0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001dfa0`

## string_xrefs

- `0x18001df7f`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplacechar.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FilterReplaceChar::GetSearchChars(FilterReplaceChar *this, unsigned __int16 **a2)
{
  int Strs; // eax
  unsigned int v5; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int64 ui; // [rsp+38h] [rbp+10h] BYREF
  OLECHAR *strIn; // [rsp+40h] [rbp+18h] BYREF
  unsigned __int16 *v10; // [rsp+48h] [rbp+20h] BYREF

  if ( !a2 )
    return 2147500035LL;
  if ( *((_QWORD *)this + 2) - *((_QWORD *)this + 1) < 4u )
    return 2147500037LL;
  strIn = 0;
  ui = 0;
  Strs = FilterReplaceChar::GetStrs(this, (const unsigned __int16 **)&strIn, (const unsigned __int16 **)&v10, &ui);
  v5 = Strs;
  if ( Strs >= 0 )
  {
    *a2 = SysAllocStringLen(strIn, ui);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\filterreplacechar.cpp",
      (const char *)(unsigned int)Strs,
      v6);
    return v5;
  }
}

```

## disassembly

```asm
0x18001df20  mov     [rsp+arg_0], rbx
0x18001df25  push    rdi; int
0x18001df26  sub     rsp, 20h
0x18001df2a  mov     rdi, rdx
0x18001df2d  test    rdx, rdx
0x18001df30  jnz     short loc_18001DF39
0x18001df32  mov     eax, 80004003h
0x18001df37  jmp     short loc_18001DFAB
0x18001df39  mov     rax, [rcx+10h]
0x18001df3d  sub     rax, [rcx+8]
0x18001df41  cmp     rax, 4
0x18001df45  jnb     short loc_18001DF4E
0x18001df47  mov     eax, 80004005h
0x18001df4c  jmp     short loc_18001DFAB
0x18001df4e  lea     r9, [rsp+28h+ui]; unsigned __int64 *
0x18001df53  mov     [rsp+28h+strIn], 0
0x18001df5c  lea     r8, [rsp+28h+arg_18]; unsigned __int16 **
0x18001df61  mov     [rsp+28h+ui], 0
0x18001df6a  lea     rdx, [rsp+28h+strIn]; unsigned __int16 **
0x18001df6f  call    ?GetStrs@FilterReplaceChar@@AEAAJPEAPEBG0PEA_K@Z; FilterReplaceChar::GetStrs(ushort const * *,ushort const * *,unsigned __int64 *)
0x18001df74  mov     ebx, eax
0x18001df76  test    eax, eax
0x18001df78  jns     short loc_18001DF97
0x18001df7a  mov     rcx, [rsp+28h]; this
0x18001df7f  lea     r8, aMincoreTextinp_23; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18001df86  mov     r9d, eax; char *
0x18001df89  mov     edx, 0C5h; void *
0x18001df8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df93  mov     eax, ebx
0x18001df95  jmp     short loc_18001DFAB
0x18001df97  mov     edx, dword ptr [rsp+28h+ui]; ui
0x18001df9b  mov     rcx, [rsp+28h+strIn]; strIn
0x18001dfa0  call    cs:__imp_SysAllocStringLen
0x18001dfa6  mov     [rdi], rax
0x18001dfa9  xor     eax, eax
0x18001dfab  mov     rbx, [rsp+28h+arg_0]
0x18001dfb0  add     rsp, 20h
0x18001dfb4  pop     rdi
0x18001dfb5  retn
```
