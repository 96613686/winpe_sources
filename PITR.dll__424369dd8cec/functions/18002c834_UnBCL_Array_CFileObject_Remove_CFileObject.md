# UnBCL::Array<CFileObject *>::Remove(CFileObject *)

- ea: `0x18002c834`
- end: `0x18002c896`
- name: `?Remove@?$Array@PEAVCFileObject@@@UnBCL@@UEAAXPEAVCFileObject@@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002c820`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x18002c834`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002c83f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002c83f`
- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x18002c85c`
- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x18002c85c`

## string_xrefs

- `0x18002c852`: `Array doesn't support Remove()`
- `0x18002c870`: `void __cdecl UnBCL::Array<class CFileObject *>::Remove(class CFileObject *)`

## pseudocode

```c
void __noreturn UnBCL::Array<CFileObject *>::Remove()
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
    UnBCL::NotSupportedException::NotSupportedException(v0, L"Array doesn't support Remove()");
    *(_QWORD *)v1 = &UnBCL::NotSupportedException::`local vftable';
  }
  else
  {
    v1 = 0;
  }
  pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                       v1,
                       "void __cdecl UnBCL::Array<class CFileObject *>::Remove(class CFileObject *)");
  throw (UnBCL::NotSupportedException **)&pExceptionObject;
}

```

## disassembly

```asm
0x18002c834  push    rbx
0x18002c836  sub     rsp, 20h
0x18002c83a  mov     ecx, 38h ; '8'
0x18002c83f  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002c845  mov     rbx, rax
0x18002c848  mov     [rsp+28h+arg_18], rax
0x18002c84d  test    rax, rax
0x18002c850  jz      short loc_18002C86E
0x18002c852  lea     rdx, aArrayDoesnTSup_2; "Array doesn't support Remove()"
0x18002c859  mov     rcx, rax
0x18002c85c  call    cs:__imp_??0NotSupportedException@UnBCL@@QEAA@PEBG@Z; UnBCL::NotSupportedException::NotSupportedException(ushort const *)
0x18002c862  lea     rax, ??_SNotSupportedException@UnBCL@@6B@; const UnBCL::NotSupportedException::`local vftable'
0x18002c869  mov     [rbx], rax
0x18002c86c  jmp     short loc_18002C870
0x18002c86e  xor     ebx, ebx
0x18002c870  lea     rdx, aVoidCdeclUnbcl_7; "void __cdecl UnBCL::Array<class CFileOb"...
0x18002c877  mov     rcx, rbx
0x18002c87a  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002c87f  mov     [rsp+28h+pExceptionObject], rax
0x18002c884  lea     rdx, _TI5PEAVNotSupportedException@UnBCL@@; pThrowInfo
0x18002c88b  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002c890  call    _CxxThrowException_0
```
