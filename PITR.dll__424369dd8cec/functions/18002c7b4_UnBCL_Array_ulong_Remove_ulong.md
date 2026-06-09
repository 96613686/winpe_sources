# UnBCL::Array<ulong>::Remove(ulong)

- ea: `0x18002c7b4`
- end: `0x18002c816`
- name: `?Remove@?$Array@K@UnBCL@@UEAAXK@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002c7a0`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x18002c7b4`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002c7bf`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002c7bf`
- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x18002c7dc`
- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x18002c7dc`

## string_xrefs

- `0x18002c7d2`: `Array doesn't support Remove()`
- `0x18002c7f0`: `void __cdecl UnBCL::Array<unsigned long>::Remove(unsigned long)`

## pseudocode

```c
void __noreturn UnBCL::Array<unsigned long>::Remove()
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
                       "void __cdecl UnBCL::Array<unsigned long>::Remove(unsigned long)");
  throw (UnBCL::NotSupportedException **)&pExceptionObject;
}

```

## disassembly

```asm
0x18002c7b4  push    rbx
0x18002c7b6  sub     rsp, 20h
0x18002c7ba  mov     ecx, 38h ; '8'
0x18002c7bf  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002c7c5  mov     rbx, rax
0x18002c7c8  mov     [rsp+28h+arg_18], rax
0x18002c7cd  test    rax, rax
0x18002c7d0  jz      short loc_18002C7EE
0x18002c7d2  lea     rdx, aArrayDoesnTSup_2; "Array doesn't support Remove()"
0x18002c7d9  mov     rcx, rax
0x18002c7dc  call    cs:__imp_??0NotSupportedException@UnBCL@@QEAA@PEBG@Z; UnBCL::NotSupportedException::NotSupportedException(ushort const *)
0x18002c7e2  lea     rax, ??_SNotSupportedException@UnBCL@@6B@; const UnBCL::NotSupportedException::`local vftable'
0x18002c7e9  mov     [rbx], rax
0x18002c7ec  jmp     short loc_18002C7F0
0x18002c7ee  xor     ebx, ebx
0x18002c7f0  lea     rdx, aVoidCdeclUnbcl_20; "void __cdecl UnBCL::Array<unsigned long"...
0x18002c7f7  mov     rcx, rbx
0x18002c7fa  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002c7ff  mov     [rsp+28h+pExceptionObject], rax
0x18002c804  lea     rdx, _TI5PEAVNotSupportedException@UnBCL@@; pThrowInfo
0x18002c80b  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002c810  call    _CxxThrowException_0
```
