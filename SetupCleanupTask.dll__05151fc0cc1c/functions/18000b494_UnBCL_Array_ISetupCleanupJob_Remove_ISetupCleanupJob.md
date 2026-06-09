# UnBCL::Array<ISetupCleanupJob *>::Remove(ISetupCleanupJob *)

- ea: `0x18000b494`
- end: `0x18000b4f6`
- name: `?Remove@?$Array@PEAVISetupCleanupJob@@@UnBCL@@UEAAXPEAVISetupCleanupJob@@@Z`
- size: `98`
- prototype: `void __noreturn()`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18000b480`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x18000b494`

## import_xrefs

- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x18000b4bc`
- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x18000b4bc`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000b49f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000b49f`

## string_xrefs

- `0x18000b4d0`: `void __cdecl UnBCL::Array<class ISetupCleanupJob *>::Remove(class ISetupCleanupJob *)`
- `0x18000b4b2`: `Array doesn't support Remove()`

## pseudocode

```c
void __noreturn UnBCL::Array<ISetupCleanupJob *>::Remove()
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
                       "void __cdecl UnBCL::Array<class ISetupCleanupJob *>::Remove(class ISetupCleanupJob *)");
  throw (UnBCL::NotSupportedException **)&pExceptionObject;
}

```

## disassembly

```asm
0x18000b494  push    rbx
0x18000b496  sub     rsp, 20h
0x18000b49a  mov     ecx, 38h ; '8'
0x18000b49f  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000b4a5  mov     rbx, rax
0x18000b4a8  mov     [rsp+28h+arg_18], rax
0x18000b4ad  test    rax, rax
0x18000b4b0  jz      short loc_18000B4CE
0x18000b4b2  lea     rdx, aArrayDoesnTSup_2; "Array doesn't support Remove()"
0x18000b4b9  mov     rcx, rax
0x18000b4bc  call    cs:__imp_??0NotSupportedException@UnBCL@@QEAA@PEBG@Z; UnBCL::NotSupportedException::NotSupportedException(ushort const *)
0x18000b4c2  lea     rax, ??_SNotSupportedException@UnBCL@@6B@; const UnBCL::NotSupportedException::`local vftable'
0x18000b4c9  mov     [rbx], rax
0x18000b4cc  jmp     short loc_18000B4D0
0x18000b4ce  xor     ebx, ebx
0x18000b4d0  lea     rdx, aVoidCdeclUnbcl_22; "void __cdecl UnBCL::Array<class ISetupC"...
0x18000b4d7  mov     rcx, rbx
0x18000b4da  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x18000b4df  mov     [rsp+28h+pExceptionObject], rax
0x18000b4e4  lea     rdx, _TI5PEAVNotSupportedException@UnBCL@@; pThrowInfo
0x18000b4eb  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000b4f0  call    _CxxThrowException_0
```
