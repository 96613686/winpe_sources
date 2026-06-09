# FilterReplaceChar::GetReplaceChars(ushort * *)

- ea: `0x18001de80`
- end: `0x18001df16`
- name: `?GetReplaceChars@FilterReplaceChar@@UEAAJPEAPEAG@Z`
- size: `150`
- prototype: `__int64 __fastcall(FilterReplaceChar *this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005ca4`
- `0x18001de80`
- `0x18001dfbc`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001df00`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001df00`

## string_xrefs

- `0x18001dedf`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplacechar.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FilterReplaceChar::GetReplaceChars(FilterReplaceChar *this, unsigned __int16 **a2)
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
  Strs = FilterReplaceChar::GetStrs(this, (const unsigned __int16 **)&v10, (const unsigned __int16 **)&strIn, &ui);
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
      (void *)0xDA,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\filterreplacechar.cpp",
      (const char *)(unsigned int)Strs,
      v6);
    return v5;
  }
}

```

## disassembly

```asm
0x18001de80  mov     [rsp+arg_0], rbx
0x18001de85  push    rdi; int
0x18001de86  sub     rsp, 20h
0x18001de8a  mov     rdi, rdx
0x18001de8d  test    rdx, rdx
0x18001de90  jnz     short loc_18001DE99
0x18001de92  mov     eax, 80004003h
0x18001de97  jmp     short loc_18001DF0B
0x18001de99  mov     rax, [rcx+10h]
0x18001de9d  sub     rax, [rcx+8]
0x18001dea1  cmp     rax, 4
0x18001dea5  jnb     short loc_18001DEAE
0x18001dea7  mov     eax, 80004005h
0x18001deac  jmp     short loc_18001DF0B
0x18001deae  lea     r9, [rsp+28h+ui]; unsigned __int64 *
0x18001deb3  mov     [rsp+28h+strIn], 0
0x18001debc  lea     r8, [rsp+28h+strIn]; unsigned __int16 **
0x18001dec1  mov     [rsp+28h+ui], 0
0x18001deca  lea     rdx, [rsp+28h+arg_18]; unsigned __int16 **
0x18001decf  call    ?GetStrs@FilterReplaceChar@@AEAAJPEAPEBG0PEA_K@Z; FilterReplaceChar::GetStrs(ushort const * *,ushort const * *,unsigned __int64 *)
0x18001ded4  mov     ebx, eax
0x18001ded6  test    eax, eax
0x18001ded8  jns     short loc_18001DEF7
0x18001deda  mov     rcx, [rsp+28h]; this
0x18001dedf  lea     r8, aMincoreTextinp_23; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18001dee6  mov     r9d, eax; char *
0x18001dee9  mov     edx, 0DAh; void *
0x18001deee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001def3  mov     eax, ebx
0x18001def5  jmp     short loc_18001DF0B
0x18001def7  mov     edx, dword ptr [rsp+28h+ui]; ui
0x18001defb  mov     rcx, [rsp+28h+strIn]; strIn
0x18001df00  call    cs:__imp_SysAllocStringLen
0x18001df06  mov     [rdi], rax
0x18001df09  xor     eax, eax
0x18001df0b  mov     rbx, [rsp+28h+arg_0]
0x18001df10  add     rsp, 20h
0x18001df14  pop     rdi
0x18001df15  retn
```
