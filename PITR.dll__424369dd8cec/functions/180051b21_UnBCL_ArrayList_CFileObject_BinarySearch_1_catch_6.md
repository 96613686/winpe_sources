# _UnBCL::ArrayList_CFileObject___::BinarySearch_::_1_::catch$6

- ea: `0x180051b21`
- end: `0x180051b88`
- name: `_UnBCL::ArrayList_CFileObject___::BinarySearch_::_1_::catch$6`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180051b21`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051b34`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051b34`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180051b50`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180051b50`

## string_xrefs

- `0x180051b46`: `sort failed -- bad comparison routines?`
- `0x180051b64`: `int __cdecl UnBCL::ArrayList<class CFileObject *>::BinarySearch(int,int,class CFileObject *,struct UnBCL::IComparer<class CFileObject *> *)`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_CFileObject___::BinarySearch_::_1_::catch_6(__int64 a1, __int64 a2)
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
                           "int __cdecl UnBCL::ArrayList<class CFileObject *>::BinarySearch(int,int,class CFileObject *,s"
                           "truct UnBCL::IComparer<class CFileObject *> *)");
  throw (UnBCL::InvalidOperationException **)(a2 + 48);
}

```

## disassembly

```asm
0x180051b21  mov     [rsp+arg_8], rdx
0x180051b26  push    rbx
0x180051b27  push    rbp
0x180051b28  sub     rsp, 28h
0x180051b2c  mov     rbp, rdx
0x180051b2f  mov     ecx, 38h ; '8'
0x180051b34  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180051b3a  mov     rbx, rax
0x180051b3d  mov     [rbp+48h], rax
0x180051b41  test    rax, rax
0x180051b44  jz      short loc_180051B62
0x180051b46  lea     rdx, aSortFailedBadC; "sort failed -- bad comparison routines?"
0x180051b4d  mov     rcx, rax
0x180051b50  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x180051b56  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180051b5d  mov     [rbx], rax
0x180051b60  jmp     short loc_180051B64
0x180051b62  xor     ebx, ebx
0x180051b64  lea     rdx, aIntCdeclUnbclA_4; "int __cdecl UnBCL::ArrayList<class CFil"...
0x180051b6b  mov     rcx, rbx
0x180051b6e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180051b73  mov     [rbp+30h], rax
0x180051b77  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180051b7e  lea     rcx, [rbp+30h]; pExceptionObject
0x180051b82  call    _CxxThrowException_0
```
