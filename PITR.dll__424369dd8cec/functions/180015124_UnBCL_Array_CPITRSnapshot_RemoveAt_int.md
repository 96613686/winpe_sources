# UnBCL::Array<CPITRSnapshot *>::RemoveAt(int)

- ea: `0x180015124`
- end: `0x180015186`
- name: `?RemoveAt@?$Array@PEAVCPITRSnapshot@@@UnBCL@@UEAAXH@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180015110`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180015124`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18001512f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18001512f`
- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x18001514c`
- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x18001514c`

## string_xrefs

- `0x180015160`: `void __cdecl UnBCL::Array<class CPITRSnapshot *>::RemoveAt(int)`
- `0x180015142`: `Array doesn't support RemoveAt()`

## pseudocode

```c
void __noreturn UnBCL::Array<CPITRSnapshot *>::RemoveAt()
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
                       "void __cdecl UnBCL::Array<class CPITRSnapshot *>::RemoveAt(int)");
  throw (UnBCL::NotSupportedException **)&pExceptionObject;
}

```

## disassembly

```asm
0x180015124  push    rbx
0x180015126  sub     rsp, 20h
0x18001512a  mov     ecx, 38h ; '8'
0x18001512f  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180015135  mov     rbx, rax
0x180015138  mov     [rsp+28h+arg_18], rax
0x18001513d  test    rax, rax
0x180015140  jz      short loc_18001515E
0x180015142  lea     rdx, aArrayDoesnTSup; "Array doesn't support RemoveAt()"
0x180015149  mov     rcx, rax
0x18001514c  call    cs:__imp_??0NotSupportedException@UnBCL@@QEAA@PEBG@Z; UnBCL::NotSupportedException::NotSupportedException(ushort const *)
0x180015152  lea     rax, ??_SNotSupportedException@UnBCL@@6B@; const UnBCL::NotSupportedException::`local vftable'
0x180015159  mov     [rbx], rax
0x18001515c  jmp     short loc_180015160
0x18001515e  xor     ebx, ebx
0x180015160  lea     rdx, aVoidCdeclUnbcl_53; "void __cdecl UnBCL::Array<class CPITRSn"...
0x180015167  mov     rcx, rbx
0x18001516a  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18001516f  mov     [rsp+28h+pExceptionObject], rax
0x180015174  lea     rdx, _TI5PEAVNotSupportedException@UnBCL@@; pThrowInfo
0x18001517b  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180015180  call    _CxxThrowException_0
```
