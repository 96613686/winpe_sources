# _UnBCL::ArrayList_CPITRSnapshot___::BinarySearch_::_1_::catch$6

- ea: `0x180050c58`
- end: `0x180050cbf`
- name: `_UnBCL::ArrayList_CPITRSnapshot___::BinarySearch_::_1_::catch$6`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180050c58`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180050c6b`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180050c6b`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180050c87`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180050c87`

## string_xrefs

- `0x180050c9b`: `int __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::BinarySearch(int,int,class CPITRSnapshot *,struct UnBCL::IComparer<class CPITRSnapshot *> *)`
- `0x180050c7d`: `sort failed -- bad comparison routines?`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_CPITRSnapshot___::BinarySearch_::_1_::catch_6(__int64 a1, __int64 a2)
{
  UnBCL::InvalidOperationException *v3; // rax
  UnBCL::Exception *v4; // rbx

  v3 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
  v4 = v3;
  *(_QWORD *)(a2 + 72) = v3;
  if ( v3 )
  {
    UnBCL::InvalidOperationException::InvalidOperationException(v3, L"sort failed -- bad comparison routines?");
    *(_QWORD *)v4 = &UnBCL::InvalidOperationException::`local vftable';
  }
  else
  {
    v4 = 0;
  }
  *(_QWORD *)(a2 + 48) = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v4,
                           "int __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::BinarySearch(int,int,class CPITRSnapshot"
                           " *,struct UnBCL::IComparer<class CPITRSnapshot *> *)");
  throw (UnBCL::InvalidOperationException **)(a2 + 48);
}

```

## disassembly

```asm
0x180050c58  mov     [rsp+arg_8], rdx
0x180050c5d  push    rbx
0x180050c5e  push    rbp
0x180050c5f  sub     rsp, 28h
0x180050c63  mov     rbp, rdx
0x180050c66  mov     ecx, 38h ; '8'
0x180050c6b  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180050c71  mov     rbx, rax
0x180050c74  mov     [rbp+48h], rax
0x180050c78  test    rax, rax
0x180050c7b  jz      short loc_180050C99
0x180050c7d  lea     rdx, aSortFailedBadC; "sort failed -- bad comparison routines?"
0x180050c84  mov     rcx, rax
0x180050c87  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x180050c8d  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180050c94  mov     [rbx], rax
0x180050c97  jmp     short loc_180050C9B
0x180050c99  xor     ebx, ebx
0x180050c9b  lea     rdx, aIntCdeclUnbclA_2; "int __cdecl UnBCL::ArrayList<class CPIT"...
0x180050ca2  mov     rcx, rbx
0x180050ca5  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180050caa  mov     [rbp+30h], rax
0x180050cae  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180050cb5  lea     rcx, [rbp+30h]; pExceptionObject
0x180050cb9  call    _CxxThrowException_0
```
