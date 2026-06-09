# FilterReplaceCharSur::GetReplaceChars(ushort * *)

- ea: `0x18001c000`
- end: `0x18001c0aa`
- name: `?GetReplaceChars@FilterReplaceCharSur@@UEAAJPEAPEAG@Z`
- size: `170`
- prototype: `__int64 __fastcall(FilterReplaceCharSur *this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005ca4`
- `0x18001c000`
- `0x18001c14c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001c094`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001c094`

## string_xrefs

- `0x18001c062`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplacecharsur.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FilterReplaceCharSur::GetReplaceChars(FilterReplaceCharSur *this, unsigned __int16 **a2)
{
  int Strs; // eax
  unsigned int v5; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int64 v8; // [rsp+38h] [rbp+10h] BYREF
  OLECHAR *strIn; // [rsp+40h] [rbp+18h] BYREF
  unsigned __int16 *v10; // [rsp+48h] [rbp+20h] BYREF

  if ( !a2 )
    return 2147500035LL;
  if ( *((_QWORD *)this + 2) - *((_QWORD *)this + 1) < 4u )
    return 2147500037LL;
  strIn = 0;
  v8 = 0;
  Strs = FilterReplaceCharSur::GetStrs(this, (const unsigned __int16 **)&v10, (const unsigned __int16 **)&strIn, &v8);
  v5 = Strs;
  if ( Strs >= 0 )
  {
    if ( 2 * v8 >= v8 )
    {
      *a2 = SysAllocStringLen(strIn, 2 * (int)v8);
      return 0;
    }
    else
    {
      return 2147942414LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\filterreplacecharsur.cpp",
      (const char *)(unsigned int)Strs,
      v6);
    return v5;
  }
}

```

## disassembly

```asm
0x18001c000  mov     [rsp+arg_0], rbx
0x18001c005  push    rdi; int
0x18001c006  sub     rsp, 20h
0x18001c00a  mov     rdi, rdx
0x18001c00d  test    rdx, rdx
0x18001c010  jnz     short loc_18001C01C
0x18001c012  mov     eax, 80004003h
0x18001c017  jmp     loc_18001C09F
0x18001c01c  mov     rax, [rcx+10h]
0x18001c020  sub     rax, [rcx+8]
0x18001c024  cmp     rax, 4
0x18001c028  jnb     short loc_18001C031
0x18001c02a  mov     eax, 80004005h
0x18001c02f  jmp     short loc_18001C09F
0x18001c031  lea     r9, [rsp+28h+arg_8]; unsigned __int64 *
0x18001c036  mov     [rsp+28h+strIn], 0
0x18001c03f  lea     r8, [rsp+28h+strIn]; unsigned __int16 **
0x18001c044  mov     [rsp+28h+arg_8], 0
0x18001c04d  lea     rdx, [rsp+28h+arg_18]; unsigned __int16 **
0x18001c052  call    ?GetStrs@FilterReplaceCharSur@@AEAAJPEAPEBG0PEA_K@Z; FilterReplaceCharSur::GetStrs(ushort const * *,ushort const * *,unsigned __int64 *)
0x18001c057  mov     ebx, eax
0x18001c059  test    eax, eax
0x18001c05b  jns     short loc_18001C07A
0x18001c05d  mov     rcx, [rsp+28h]; this
0x18001c062  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18001c069  mov     r9d, eax; char *
0x18001c06c  mov     edx, 0DDh; void *
0x18001c071  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c076  mov     eax, ebx
0x18001c078  jmp     short loc_18001C09F
0x18001c07a  mov     rax, [rsp+28h+arg_8]
0x18001c07f  lea     rdx, [rax+rax]; ui
0x18001c083  cmp     rdx, rax
0x18001c086  jnb     short loc_18001C08F
0x18001c088  mov     eax, 8007000Eh
0x18001c08d  jmp     short loc_18001C09F
0x18001c08f  mov     rcx, [rsp+28h+strIn]; strIn
0x18001c094  call    cs:__imp_SysAllocStringLen
0x18001c09a  mov     [rdi], rax
0x18001c09d  xor     eax, eax
0x18001c09f  mov     rbx, [rsp+28h+arg_0]
0x18001c0a4  add     rsp, 20h
0x18001c0a8  pop     rdi
0x18001c0a9  retn
```
