# _UnBCL::ArrayList_ISetupCleanupJob___::QuickSort_::_1_::catch$4

- ea: `0x1800336dc`
- end: `0x180033746`
- name: `_UnBCL::ArrayList_ISetupCleanupJob___::QuickSort_::_1_::catch$4`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x1800336dc`

## import_xrefs

- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18003370e`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18003370e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800336ef`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800336ef`

## string_xrefs

- `0x180033704`: `sort failed -- bad comparison routines?`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_ISetupCleanupJob___::QuickSort_::_1_::catch_4(__int64 a1, __int64 a2)
{
  UnBCL::InvalidOperationException *v3; // rax
  UnBCL::Exception *v4; // rbx

  v3 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
  v4 = v3;
  *(_QWORD *)(a2 + 160) = v3;
  if ( v3 )
  {
    UnBCL::InvalidOperationException::InvalidOperationException(v3, L"sort failed -- bad comparison routines?");
    *(_QWORD *)v4 = &UnBCL::InvalidOperationException::`local vftable';
  }
  else
  {
    v4 = 0;
  }
  *(_QWORD *)(a2 + 64) = AddStackTraceToException<SetupCleanupTaskException>(
                           v4,
                           "void __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::QuickSort(class UnBCL::ArrayList<cla"
                           "ss ISetupCleanupJob *> *,class UnBCL::ArrayList<class ISetupCleanupJob *> *,int,int)");
  throw (UnBCL::InvalidOperationException **)(a2 + 64);
}

```

## disassembly

```asm
0x1800336dc  mov     [rsp+arg_8], rdx
0x1800336e1  push    rbx
0x1800336e2  push    rbp
0x1800336e3  sub     rsp, 38h
0x1800336e7  mov     rbp, rdx
0x1800336ea  mov     ecx, 38h ; '8'
0x1800336ef  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800336f5  mov     rbx, rax
0x1800336f8  mov     [rbp+0A0h], rax
0x1800336ff  test    rax, rax
0x180033702  jz      short loc_180033720
0x180033704  lea     rdx, aSortFailedBadC; "sort failed -- bad comparison routines?"
0x18003370b  mov     rcx, rax
0x18003370e  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x180033714  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18003371b  mov     [rbx], rax
0x18003371e  jmp     short loc_180033722
0x180033720  xor     ebx, ebx
0x180033722  lea     rdx, aVoidCdeclUnbcl_16; "void __cdecl UnBCL::ArrayList<class ISe"...
0x180033729  mov     rcx, rbx
0x18003372c  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x180033731  mov     [rbp+40h], rax
0x180033735  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18003373c  lea     rcx, [rbp+40h]; pExceptionObject
0x180033740  call    _CxxThrowException_0
```
