# _UnBCL::ArrayList_ISetupCleanupJob___::BinarySearch_::_1_::catch$6

- ea: `0x180032cae`
- end: `0x180032d15`
- name: `_UnBCL::ArrayList_ISetupCleanupJob___::BinarySearch_::_1_::catch$6`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x180032cae`

## import_xrefs

- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180032cdd`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180032cdd`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180032cc1`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180032cc1`

## string_xrefs

- `0x180032cf1`: `int __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::BinarySearch(int,int,class ISetupCleanupJob *,struct UnBCL::IComparer<class ISetupCleanupJob *> *)`
- `0x180032cd3`: `sort failed -- bad comparison routines?`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_ISetupCleanupJob___::BinarySearch_::_1_::catch_6(__int64 a1, __int64 a2)
{
  UnBCL::InvalidOperationException *v3; // rax
  UnBCL::Exception *v4; // rbx

  v3 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
  v4 = v3;
  *(_QWORD *)(a2 + 80) = v3;
  if ( v3 )
  {
    UnBCL::InvalidOperationException::InvalidOperationException(v3, L"sort failed -- bad comparison routines?");
    *(_QWORD *)v4 = &UnBCL::InvalidOperationException::`local vftable';
  }
  else
  {
    v4 = 0;
  }
  *(_QWORD *)(a2 + 56) = AddStackTraceToException<SetupCleanupTaskException>(
                           v4,
                           "int __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::BinarySearch(int,int,class ISetupClea"
                           "nupJob *,struct UnBCL::IComparer<class ISetupCleanupJob *> *)");
  throw (UnBCL::InvalidOperationException **)(a2 + 56);
}

```

## disassembly

```asm
0x180032cae  mov     [rsp+arg_8], rdx
0x180032cb3  push    rbx
0x180032cb4  push    rbp
0x180032cb5  sub     rsp, 28h
0x180032cb9  mov     rbp, rdx
0x180032cbc  mov     ecx, 38h ; '8'
0x180032cc1  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180032cc7  mov     rbx, rax
0x180032cca  mov     [rbp+50h], rax
0x180032cce  test    rax, rax
0x180032cd1  jz      short loc_180032CEF
0x180032cd3  lea     rdx, aSortFailedBadC; "sort failed -- bad comparison routines?"
0x180032cda  mov     rcx, rax
0x180032cdd  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x180032ce3  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180032cea  mov     [rbx], rax
0x180032ced  jmp     short loc_180032CF1
0x180032cef  xor     ebx, ebx
0x180032cf1  lea     rdx, aIntCdeclUnbclA_4; "int __cdecl UnBCL::ArrayList<class ISet"...
0x180032cf8  mov     rcx, rbx
0x180032cfb  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x180032d00  mov     [rbp+38h], rax
0x180032d04  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180032d0b  lea     rcx, [rbp+38h]; pExceptionObject
0x180032d0f  call    _CxxThrowException_0
```
