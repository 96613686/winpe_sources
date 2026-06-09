# _UnBCL::ArrayList_UnBCL::SmartPtr_UnBCL::String___::BinarySearch_::_1_::catch$12

- ea: `0x180034074`
- end: `0x1800340db`
- name: `_UnBCL::ArrayList_UnBCL::SmartPtr_UnBCL::String___::BinarySearch_::_1_::catch$12`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x180034074`

## import_xrefs

- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x1800340a3`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x1800340a3`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180034087`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180034087`

## string_xrefs

- `0x180034099`: `sort failed -- bad comparison routines?`
- `0x1800340b7`: `int __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::BinarySearch(int,int,class UnBCL::SmartPtr<class UnBCL::String>,struct UnBCL::IComparer<class UnBCL::SmartPtr<class UnBCL::String> > *)`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_UnBCL::SmartPtr_UnBCL::String___::BinarySearch_::_1_::catch_12(
        __int64 a1,
        __int64 a2)
{
  UnBCL::InvalidOperationException *v3; // rax
  UnBCL::Exception *v4; // rbx

  v3 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
  v4 = v3;
  *(_QWORD *)(a2 + 32) = v3;
  if ( v3 )
  {
    UnBCL::InvalidOperationException::InvalidOperationException(v3, L"sort failed -- bad comparison routines?");
    *(_QWORD *)v4 = &UnBCL::InvalidOperationException::`local vftable';
  }
  else
  {
    v4 = 0;
  }
  *(_QWORD *)(a2 + 80) = AddStackTraceToException<SetupCleanupTaskException>(
                           v4,
                           "int __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::BinarySearch(int,i"
                           "nt,class UnBCL::SmartPtr<class UnBCL::String>,struct UnBCL::IComparer<class UnBCL::SmartPtr<c"
                           "lass UnBCL::String> > *)");
  throw (UnBCL::InvalidOperationException **)(a2 + 80);
}

```

## disassembly

```asm
0x180034074  mov     [rsp+arg_8], rdx
0x180034079  push    rbx
0x18003407a  push    rbp
0x18003407b  sub     rsp, 28h
0x18003407f  mov     rbp, rdx
0x180034082  mov     ecx, 38h ; '8'
0x180034087  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003408d  mov     rbx, rax
0x180034090  mov     [rbp+20h], rax
0x180034094  test    rax, rax
0x180034097  jz      short loc_1800340B5
0x180034099  lea     rdx, aSortFailedBadC; "sort failed -- bad comparison routines?"
0x1800340a0  mov     rcx, rax
0x1800340a3  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x1800340a9  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x1800340b0  mov     [rbx], rax
0x1800340b3  jmp     short loc_1800340B7
0x1800340b5  xor     ebx, ebx
0x1800340b7  lea     rdx, aIntCdeclUnbclA_2; "int __cdecl UnBCL::ArrayList<class UnBC"...
0x1800340be  mov     rcx, rbx
0x1800340c1  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x1800340c6  mov     [rbp+50h], rax
0x1800340ca  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x1800340d1  lea     rcx, [rbp+50h]; pExceptionObject
0x1800340d5  call    _CxxThrowException_0
```
