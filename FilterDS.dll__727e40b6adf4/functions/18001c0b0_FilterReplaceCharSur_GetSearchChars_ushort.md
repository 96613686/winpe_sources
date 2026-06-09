# FilterReplaceCharSur::GetSearchChars(ushort * *)

- ea: `0x18001c0b0`
- end: `0x18001c146`
- name: `?GetSearchChars@FilterReplaceCharSur@@UEAAJPEAPEAG@Z`
- size: `150`
- prototype: `__int64 __fastcall(FilterReplaceCharSur *this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005ca4`
- `0x18001c0b0`
- `0x18001c14c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001c130`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001c130`

## string_xrefs

- `0x18001c10f`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplacecharsur.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FilterReplaceCharSur::GetSearchChars(FilterReplaceCharSur *this, unsigned __int16 **a2)
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
  Strs = FilterReplaceCharSur::GetStrs(this, (const unsigned __int16 **)&strIn, (const unsigned __int16 **)&v10, &ui);
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
      (void *)0xC7,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\filterreplacecharsur.cpp",
      (const char *)(unsigned int)Strs,
      v6);
    return v5;
  }
}

```

## disassembly

```asm
0x18001c0b0  mov     [rsp+arg_0], rbx
0x18001c0b5  push    rdi; int
0x18001c0b6  sub     rsp, 20h
0x18001c0ba  mov     rdi, rdx
0x18001c0bd  test    rdx, rdx
0x18001c0c0  jnz     short loc_18001C0C9
0x18001c0c2  mov     eax, 80004003h
0x18001c0c7  jmp     short loc_18001C13B
0x18001c0c9  mov     rax, [rcx+10h]
0x18001c0cd  sub     rax, [rcx+8]
0x18001c0d1  cmp     rax, 4
0x18001c0d5  jnb     short loc_18001C0DE
0x18001c0d7  mov     eax, 80004005h
0x18001c0dc  jmp     short loc_18001C13B
0x18001c0de  lea     r9, [rsp+28h+ui]; unsigned __int64 *
0x18001c0e3  mov     [rsp+28h+strIn], 0
0x18001c0ec  lea     r8, [rsp+28h+arg_18]; unsigned __int16 **
0x18001c0f1  mov     [rsp+28h+ui], 0
0x18001c0fa  lea     rdx, [rsp+28h+strIn]; unsigned __int16 **
0x18001c0ff  call    ?GetStrs@FilterReplaceCharSur@@AEAAJPEAPEBG0PEA_K@Z; FilterReplaceCharSur::GetStrs(ushort const * *,ushort const * *,unsigned __int64 *)
0x18001c104  mov     ebx, eax
0x18001c106  test    eax, eax
0x18001c108  jns     short loc_18001C127
0x18001c10a  mov     rcx, [rsp+28h]; this
0x18001c10f  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18001c116  mov     r9d, eax; char *
0x18001c119  mov     edx, 0C7h; void *
0x18001c11e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c123  mov     eax, ebx
0x18001c125  jmp     short loc_18001C13B
0x18001c127  mov     edx, dword ptr [rsp+28h+ui]; ui
0x18001c12b  mov     rcx, [rsp+28h+strIn]; strIn
0x18001c130  call    cs:__imp_SysAllocStringLen
0x18001c136  mov     [rdi], rax
0x18001c139  xor     eax, eax
0x18001c13b  mov     rbx, [rsp+28h+arg_0]
0x18001c140  add     rsp, 20h
0x18001c144  pop     rdi
0x18001c145  retn
```
