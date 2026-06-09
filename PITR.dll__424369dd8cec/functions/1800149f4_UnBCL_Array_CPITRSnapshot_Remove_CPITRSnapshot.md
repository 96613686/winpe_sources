# UnBCL::Array<CPITRSnapshot *>::Remove(CPITRSnapshot *)

- ea: `0x1800149f4`
- end: `0x180014a56`
- name: `?Remove@?$Array@PEAVCPITRSnapshot@@@UnBCL@@UEAAXPEAVCPITRSnapshot@@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800149e0`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x1800149f4`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800149ff`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800149ff`
- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x180014a1c`
- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x180014a1c`

## string_xrefs

- `0x180014a30`: `void __cdecl UnBCL::Array<class CPITRSnapshot *>::Remove(class CPITRSnapshot *)`
- `0x180014a12`: `Array doesn't support Remove()`

## pseudocode

```c
void __noreturn UnBCL::Array<CPITRSnapshot *>::Remove()
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
                       "void __cdecl UnBCL::Array<class CPITRSnapshot *>::Remove(class CPITRSnapshot *)");
  throw (UnBCL::NotSupportedException **)&pExceptionObject;
}

```

## disassembly

```asm
0x1800149f4  push    rbx
0x1800149f6  sub     rsp, 20h
0x1800149fa  mov     ecx, 38h ; '8'
0x1800149ff  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180014a05  mov     rbx, rax
0x180014a08  mov     [rsp+28h+arg_18], rax
0x180014a0d  test    rax, rax
0x180014a10  jz      short loc_180014A2E
0x180014a12  lea     rdx, aArrayDoesnTSup_2; "Array doesn't support Remove()"
0x180014a19  mov     rcx, rax
0x180014a1c  call    cs:__imp_??0NotSupportedException@UnBCL@@QEAA@PEBG@Z; UnBCL::NotSupportedException::NotSupportedException(ushort const *)
0x180014a22  lea     rax, ??_SNotSupportedException@UnBCL@@6B@; const UnBCL::NotSupportedException::`local vftable'
0x180014a29  mov     [rbx], rax
0x180014a2c  jmp     short loc_180014A30
0x180014a2e  xor     ebx, ebx
0x180014a30  lea     rdx, aVoidCdeclUnbcl_4; "void __cdecl UnBCL::Array<class CPITRSn"...
0x180014a37  mov     rcx, rbx
0x180014a3a  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180014a3f  mov     [rsp+28h+pExceptionObject], rax
0x180014a44  lea     rdx, _TI5PEAVNotSupportedException@UnBCL@@; pThrowInfo
0x180014a4b  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180014a50  call    _CxxThrowException_0
```
