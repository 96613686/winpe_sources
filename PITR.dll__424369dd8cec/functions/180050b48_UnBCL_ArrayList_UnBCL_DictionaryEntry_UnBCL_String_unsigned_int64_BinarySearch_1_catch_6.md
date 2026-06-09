# _UnBCL::ArrayList_UnBCL::DictionaryEntry_UnBCL::String___unsigned___int64____::BinarySearch_::_1_::catch$6

- ea: `0x180050b48`
- end: `0x180050baf`
- name: `_UnBCL::ArrayList_UnBCL::DictionaryEntry_UnBCL::String___unsigned___int64____::BinarySearch_::_1_::catch$6`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180050b48`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180050b5b`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180050b5b`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180050b77`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180050b77`

## string_xrefs

- `0x180050b6d`: `sort failed -- bad comparison routines?`
- `0x180050b8b`: `int __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *>::BinarySearch(int,int,class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *,struct UnBCL::IComparer<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *> *)`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_UnBCL::DictionaryEntry_UnBCL::String___unsigned___int64____::BinarySearch_::_1_::catch_6(
        __int64 a1,
        __int64 a2)
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
                           "int __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __in"
                           "t64> *>::BinarySearch(int,int,class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __i"
                           "nt64> *,struct UnBCL::IComparer<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *> *)");
  throw (UnBCL::InvalidOperationException **)(a2 + 48);
}

```

## disassembly

```asm
0x180050b48  mov     [rsp+arg_8], rdx
0x180050b4d  push    rbx
0x180050b4e  push    rbp
0x180050b4f  sub     rsp, 28h
0x180050b53  mov     rbp, rdx
0x180050b56  mov     ecx, 38h ; '8'
0x180050b5b  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180050b61  mov     rbx, rax
0x180050b64  mov     [rbp+48h], rax
0x180050b68  test    rax, rax
0x180050b6b  jz      short loc_180050B89
0x180050b6d  lea     rdx, aSortFailedBadC; "sort failed -- bad comparison routines?"
0x180050b74  mov     rcx, rax
0x180050b77  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x180050b7d  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180050b84  mov     [rbx], rax
0x180050b87  jmp     short loc_180050B8B
0x180050b89  xor     ebx, ebx
0x180050b8b  lea     rdx, aIntCdeclUnbclA_17; "int __cdecl UnBCL::ArrayList<class UnBC"...
0x180050b92  mov     rcx, rbx
0x180050b95  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180050b9a  mov     [rbp+30h], rax
0x180050b9e  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180050ba5  lea     rcx, [rbp+30h]; pExceptionObject
0x180050ba9  call    _CxxThrowException_0
```
