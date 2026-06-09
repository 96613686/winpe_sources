# UnBCL::Array<UnBCL::SmartPtr<UnBCL::String>>::Remove(UnBCL::SmartPtr<UnBCL::String>)

- ea: `0x180011f54`
- end: `0x180011fba`
- name: `?Remove@?$Array@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@UnBCL@@UEAAXV?$SmartPtr@VString@UnBCL@@@2@@Z`
- size: `102`
- prototype: `void __noreturn()`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180011f40`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x180011f54`

## import_xrefs

- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x180011f80`
- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x180011f80`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180011f63`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180011f63`

## string_xrefs

- `0x180011f76`: `Array doesn't support Remove()`
- `0x180011f94`: `void __cdecl UnBCL::Array<class UnBCL::SmartPtr<class UnBCL::String> >::Remove(class UnBCL::SmartPtr<class UnBCL::String>)`

## pseudocode

```c
void __noreturn UnBCL::Array<UnBCL::SmartPtr<UnBCL::String>>::Remove()
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
  pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                       v1,
                       "void __cdecl UnBCL::Array<class UnBCL::SmartPtr<class UnBCL::String> >::Remove(class UnBCL::Smart"
                       "Ptr<class UnBCL::String>)");
  throw (UnBCL::NotSupportedException **)&pExceptionObject;
}

```

## disassembly

```asm
0x180011f54  mov     [rsp+arg_8], rdx
0x180011f59  push    rbx
0x180011f5a  sub     rsp, 20h
0x180011f5e  mov     ecx, 38h ; '8'
0x180011f63  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180011f69  mov     rbx, rax
0x180011f6c  mov     [rsp+28h+arg_18], rax
0x180011f71  test    rax, rax
0x180011f74  jz      short loc_180011F92
0x180011f76  lea     rdx, aArrayDoesnTSup_2; "Array doesn't support Remove()"
0x180011f7d  mov     rcx, rax
0x180011f80  call    cs:__imp_??0NotSupportedException@UnBCL@@QEAA@PEBG@Z; UnBCL::NotSupportedException::NotSupportedException(ushort const *)
0x180011f86  lea     rax, ??_SNotSupportedException@UnBCL@@6B@; const UnBCL::NotSupportedException::`local vftable'
0x180011f8d  mov     [rbx], rax
0x180011f90  jmp     short loc_180011F94
0x180011f92  xor     ebx, ebx
0x180011f94  lea     rdx, aVoidCdeclUnbcl_12; "void __cdecl UnBCL::Array<class UnBCL::"...
0x180011f9b  mov     rcx, rbx
0x180011f9e  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x180011fa3  mov     [rsp+28h+pExceptionObject], rax
0x180011fa8  lea     rdx, _TI5PEAVNotSupportedException@UnBCL@@; pThrowInfo
0x180011faf  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180011fb4  call    _CxxThrowException_0
```
