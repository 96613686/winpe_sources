# UnBCL::Array<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>::Remove(UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *)

- ea: `0x180014974`
- end: `0x1800149d6`
- name: `?Remove@?$Array@PEAV?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@@UnBCL@@UEAAXPEAV?$DictionaryEntry@PEAVString@UnBCL@@_K@2@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180014960`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180014974`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18001497f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18001497f`
- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x18001499c`
- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x18001499c`

## string_xrefs

- `0x180014992`: `Array doesn't support Remove()`
- `0x1800149b0`: `void __cdecl UnBCL::Array<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *>::Remove(class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *)`

## pseudocode

```c
void __noreturn UnBCL::Array<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>::Remove()
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
                       "void __cdecl UnBCL::Array<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *>"
                       "::Remove(class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *)");
  throw (UnBCL::NotSupportedException **)&pExceptionObject;
}

```

## disassembly

```asm
0x180014974  push    rbx
0x180014976  sub     rsp, 20h
0x18001497a  mov     ecx, 38h ; '8'
0x18001497f  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180014985  mov     rbx, rax
0x180014988  mov     [rsp+28h+arg_18], rax
0x18001498d  test    rax, rax
0x180014990  jz      short loc_1800149AE
0x180014992  lea     rdx, aArrayDoesnTSup_2; "Array doesn't support Remove()"
0x180014999  mov     rcx, rax
0x18001499c  call    cs:__imp_??0NotSupportedException@UnBCL@@QEAA@PEBG@Z; UnBCL::NotSupportedException::NotSupportedException(ushort const *)
0x1800149a2  lea     rax, ??_SNotSupportedException@UnBCL@@6B@; const UnBCL::NotSupportedException::`local vftable'
0x1800149a9  mov     [rbx], rax
0x1800149ac  jmp     short loc_1800149B0
0x1800149ae  xor     ebx, ebx
0x1800149b0  lea     rdx, aVoidCdeclUnbcl_15; "void __cdecl UnBCL::Array<class UnBCL::"...
0x1800149b7  mov     rcx, rbx
0x1800149ba  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800149bf  mov     [rsp+28h+pExceptionObject], rax
0x1800149c4  lea     rdx, _TI5PEAVNotSupportedException@UnBCL@@; pThrowInfo
0x1800149cb  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800149d0  call    _CxxThrowException_0
```
