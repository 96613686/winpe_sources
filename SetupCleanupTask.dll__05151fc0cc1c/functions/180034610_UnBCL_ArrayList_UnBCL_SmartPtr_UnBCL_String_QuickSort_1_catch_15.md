# _UnBCL::ArrayList_UnBCL::SmartPtr_UnBCL::String___::QuickSort_::_1_::catch$15

- ea: `0x180034610`
- end: `0x18003467a`
- name: `_UnBCL::ArrayList_UnBCL::SmartPtr_UnBCL::String___::QuickSort_::_1_::catch$15`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x180034610`

## import_xrefs

- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180034642`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180034642`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180034623`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180034623`

## string_xrefs

- `0x180034638`: `sort failed -- bad comparison routines?`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_UnBCL::SmartPtr_UnBCL::String___::QuickSort_::_1_::catch_15(
        __int64 a1,
        __int64 a2)
{
  UnBCL::InvalidOperationException *v3; // rax
  UnBCL::Exception *v4; // rbx

  v3 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
  v4 = v3;
  *(_QWORD *)(a2 + 312) = v3;
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
                           "void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::QuickSort(class U"
                           "nBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> > *,class UnBCL::ArrayList<class U"
                           "nBCL::SmartPtr<class UnBCL::String> > *,int,int)");
  throw (UnBCL::InvalidOperationException **)(a2 + 64);
}

```

## disassembly

```asm
0x180034610  mov     [rsp+arg_8], rdx
0x180034615  push    rbx
0x180034616  push    rbp
0x180034617  sub     rsp, 38h
0x18003461b  mov     rbp, rdx
0x18003461e  mov     ecx, 38h ; '8'
0x180034623  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180034629  mov     rbx, rax
0x18003462c  mov     [rbp+138h], rax
0x180034633  test    rax, rax
0x180034636  jz      short loc_180034654
0x180034638  lea     rdx, aSortFailedBadC; "sort failed -- bad comparison routines?"
0x18003463f  mov     rcx, rax
0x180034642  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x180034648  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18003464f  mov     [rbx], rax
0x180034652  jmp     short loc_180034656
0x180034654  xor     ebx, ebx
0x180034656  lea     rdx, aVoidCdeclUnbcl_4; "void __cdecl UnBCL::ArrayList<class UnB"...
0x18003465d  mov     rcx, rbx
0x180034660  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x180034665  mov     [rbp+40h], rax
0x180034669  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180034670  lea     rcx, [rbp+40h]; pExceptionObject
0x180034674  call    _CxxThrowException_0
```
