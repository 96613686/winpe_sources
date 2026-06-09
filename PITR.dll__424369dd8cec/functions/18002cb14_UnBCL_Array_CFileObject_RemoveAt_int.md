# UnBCL::Array<CFileObject *>::RemoveAt(int)

- ea: `0x18002cb14`
- end: `0x18002cb76`
- name: `?RemoveAt@?$Array@PEAVCFileObject@@@UnBCL@@UEAAXH@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002cb00`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x18002cb14`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002cb1f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002cb1f`
- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x18002cb3c`
- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x18002cb3c`

## string_xrefs

- `0x18002cb32`: `Array doesn't support RemoveAt()`
- `0x18002cb50`: `void __cdecl UnBCL::Array<class CFileObject *>::RemoveAt(int)`

## pseudocode

```c
void __noreturn UnBCL::Array<CFileObject *>::RemoveAt()
{
  UnBCL::NotSupportedException *v0; // rax
  UnBCL::Exception *v1; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+40h] [rbp+18h] BYREF
  UnBCL::NotSupportedException *v3; // [rsp+48h] [rbp+20h]

  v0 = (UnBCL::NotSupportedException *)UnBCL::Object::operator new(0x38u);
  v1 = v0;
  v3 = v0;
  if ( v0 )
  {
    UnBCL::NotSupportedException::NotSupportedException(v0, L"Array doesn't support RemoveAt()");
    *(_QWORD *)v1 = &UnBCL::NotSupportedException::`local vftable';
  }
  else
  {
    v1 = 0;
  }
  pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                       v1,
                       "void __cdecl UnBCL::Array<class CFileObject *>::RemoveAt(int)");
  throw (UnBCL::NotSupportedException **)&pExceptionObject;
}

```

## disassembly

```asm
0x18002cb14  push    rbx
0x18002cb16  sub     rsp, 20h
0x18002cb1a  mov     ecx, 38h ; '8'
0x18002cb1f  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002cb25  mov     rbx, rax
0x18002cb28  mov     [rsp+28h+arg_18], rax
0x18002cb2d  test    rax, rax
0x18002cb30  jz      short loc_18002CB4E
0x18002cb32  lea     rdx, aArrayDoesnTSup; "Array doesn't support RemoveAt()"
0x18002cb39  mov     rcx, rax
0x18002cb3c  call    cs:__imp_??0NotSupportedException@UnBCL@@QEAA@PEBG@Z; UnBCL::NotSupportedException::NotSupportedException(ushort const *)
0x18002cb42  lea     rax, ??_SNotSupportedException@UnBCL@@6B@; const UnBCL::NotSupportedException::`local vftable'
0x18002cb49  mov     [rbx], rax
0x18002cb4c  jmp     short loc_18002CB50
0x18002cb4e  xor     ebx, ebx
0x18002cb50  lea     rdx, aVoidCdeclUnbcl_51; "void __cdecl UnBCL::Array<class CFileOb"...
0x18002cb57  mov     rcx, rbx
0x18002cb5a  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002cb5f  mov     [rsp+28h+pExceptionObject], rax
0x18002cb64  lea     rdx, _TI5PEAVNotSupportedException@UnBCL@@; pThrowInfo
0x18002cb6b  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002cb70  call    _CxxThrowException_0
```
