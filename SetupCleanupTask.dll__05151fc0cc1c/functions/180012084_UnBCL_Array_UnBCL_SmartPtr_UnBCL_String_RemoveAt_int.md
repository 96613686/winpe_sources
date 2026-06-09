# UnBCL::Array<UnBCL::SmartPtr<UnBCL::String>>::RemoveAt(int)

- ea: `0x180012084`
- end: `0x1800120e6`
- name: `?RemoveAt@?$Array@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@UnBCL@@UEAAXH@Z`
- size: `98`
- prototype: `void __noreturn()`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180012070`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x180012084`

## import_xrefs

- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x1800120ac`
- `unbcl!??0NotSupportedException@UnBCL@@QEAA@PEBG@Z` at `0x1800120ac`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18001208f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18001208f`

## string_xrefs

- `0x1800120a2`: `Array doesn't support RemoveAt()`
- `0x1800120c0`: `void __cdecl UnBCL::Array<class UnBCL::SmartPtr<class UnBCL::String> >::RemoveAt(int)`

## pseudocode

```c
void __noreturn UnBCL::Array<UnBCL::SmartPtr<UnBCL::String>>::RemoveAt()
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
                       "void __cdecl UnBCL::Array<class UnBCL::SmartPtr<class UnBCL::String> >::RemoveAt(int)");
  throw (UnBCL::NotSupportedException **)&pExceptionObject;
}

```

## disassembly

```asm
0x180012084  push    rbx
0x180012086  sub     rsp, 20h
0x18001208a  mov     ecx, 38h ; '8'
0x18001208f  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180012095  mov     rbx, rax
0x180012098  mov     [rsp+28h+arg_18], rax
0x18001209d  test    rax, rax
0x1800120a0  jz      short loc_1800120BE
0x1800120a2  lea     rdx, aArrayDoesnTSup; "Array doesn't support RemoveAt()"
0x1800120a9  mov     rcx, rax
0x1800120ac  call    cs:__imp_??0NotSupportedException@UnBCL@@QEAA@PEBG@Z; UnBCL::NotSupportedException::NotSupportedException(ushort const *)
0x1800120b2  lea     rax, ??_SNotSupportedException@UnBCL@@6B@; const UnBCL::NotSupportedException::`local vftable'
0x1800120b9  mov     [rbx], rax
0x1800120bc  jmp     short loc_1800120C0
0x1800120be  xor     ebx, ebx
0x1800120c0  lea     rdx, aVoidCdeclUnbcl_10; "void __cdecl UnBCL::Array<class UnBCL::"...
0x1800120c7  mov     rcx, rbx
0x1800120ca  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x1800120cf  mov     [rsp+28h+pExceptionObject], rax
0x1800120d4  lea     rdx, _TI5PEAVNotSupportedException@UnBCL@@; pThrowInfo
0x1800120db  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800120e0  call    _CxxThrowException_0
```
