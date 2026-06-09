# UnBCL::Array<ISetupCleanupJob *>::RemoveAt(int)

- ea: `0x18000b584`
- end: `0x18000b5e6`
- name: `?RemoveAt@?$Array@PEAVISetupCleanupJob@@@UnBCL@@UEAAXH@Z`
- size: `98`
- prototype: `void __noreturn()`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x18000b570`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x18000b584`

## import_xrefs

- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x18000b5ac`
- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x18000b5ac`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000b58f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000b58f`

## string_xrefs

- `0x18000b5c0`: `void __cdecl UnBCL::Array<class ISetupCleanupJob *>::RemoveAt(int)`
- `0x18000b5a2`: `Array doesn't support RemoveAt()`

## pseudocode

```c
void __noreturn UnBCL::Array<ISetupCleanupJob *>::RemoveAt()
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
  pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                       v1,
                       "void __cdecl UnBCL::Array<class ISetupCleanupJob *>::RemoveAt(int)");
  throw (UnBCL::NotSupportedException **)&pExceptionObject;
}

```

## disassembly

```asm
0x18000b584  push    rbx
0x18000b586  sub     rsp, 20h
0x18000b58a  mov     ecx, 38h ; '8'
0x18000b58f  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000b595  mov     rbx, rax
0x18000b598  mov     [rsp+28h+arg_18], rax
0x18000b59d  test    rax, rax
0x18000b5a0  jz      short loc_18000B5BE
0x18000b5a2  lea     rdx, aArrayDoesnTSup; "Array doesn't support RemoveAt()"
0x18000b5a9  mov     rcx, rax
0x18000b5ac  call    cs:__imp_??0NotSupportedException@UnBCL@@QEAA@PEBG@Z; UnBCL::NotSupportedException::NotSupportedException(ushort const *)
0x18000b5b2  lea     rax, ??_SNotSupportedException@UnBCL@@6B@; const UnBCL::NotSupportedException::`local vftable'
0x18000b5b9  mov     [rbx], rax
0x18000b5bc  jmp     short loc_18000B5C0
0x18000b5be  xor     ebx, ebx
0x18000b5c0  lea     rdx, aVoidCdeclUnbcl_5; "void __cdecl UnBCL::Array<class ISetupC"...
0x18000b5c7  mov     rcx, rbx
0x18000b5ca  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x18000b5cf  mov     [rsp+28h+pExceptionObject], rax
0x18000b5d4  lea     rdx, _TI5PEAVNotSupportedException@UnBCL@@; pThrowInfo
0x18000b5db  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000b5e0  call    _CxxThrowException_0
```
