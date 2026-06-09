# _UnBCL::ArrayList_UnBCL::SmartPtr_UnBCL::String___::QuickSort_::_1_::catch$14

- ea: `0x180034564`
- end: `0x18003460a`
- name: `_UnBCL::ArrayList_UnBCL::SmartPtr_UnBCL::String___::QuickSort_::_1_::catch$14`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x180034564`

## import_xrefs

- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x1800345d2`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x1800345d2`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180034578`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180034592`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180034578`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180034592`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800345b1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800345b1`

## string_xrefs

- `0x1800345a7`: `sort failed -- bad comparison routines?`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_UnBCL::SmartPtr_UnBCL::String___::QuickSort_::_1_::catch_14(
        __int64 a1,
        __int64 a2)
{
  UnBCL::InvalidOperationException *v3; // rbx
  UnBCL::String *v4; // rax
  const struct UnBCL::String *v5; // rdi

  v3 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
  *(_QWORD *)(a2 + 312) = v3;
  if ( v3 )
  {
    v4 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v5 = v4;
    *(_QWORD *)(a2 + 320) = v4;
    if ( v4 )
    {
      UnBCL::String::String(v4, L"sort failed -- bad comparison routines?");
      *(_QWORD *)v5 = &UnBCL::String::`local vftable';
    }
    else
    {
      v5 = 0;
    }
    UnBCL::InvalidOperationException::InvalidOperationException(v3, v5, *(struct UnBCL::Exception **)(a2 + 136));
    *(_QWORD *)v3 = &UnBCL::InvalidOperationException::`local vftable';
  }
  else
  {
    v3 = 0;
  }
  *(_QWORD *)(a2 + 56) = AddStackTraceToException<SetupCleanupTaskException>(
                           v3,
                           "void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::QuickSort(class U"
                           "nBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> > *,class UnBCL::ArrayList<class U"
                           "nBCL::SmartPtr<class UnBCL::String> > *,int,int)");
  throw (UnBCL::InvalidOperationException **)(a2 + 56);
}

```

## disassembly

```asm
0x180034564  mov     [rsp+arg_8], rdx
0x180034569  push    rbx
0x18003456a  push    rbp
0x18003456b  push    rdi
0x18003456c  sub     rsp, 30h
0x180034570  mov     rbp, rdx
0x180034573  mov     ecx, 38h ; '8'
0x180034578  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003457e  mov     rbx, rax
0x180034581  mov     [rbp+138h], rax
0x180034588  test    rax, rax
0x18003458b  jz      short loc_1800345E4
0x18003458d  mov     ecx, 18h
0x180034592  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180034598  mov     rdi, rax
0x18003459b  mov     [rbp+140h], rax
0x1800345a2  test    rax, rax
0x1800345a5  jz      short loc_1800345C3
0x1800345a7  lea     rdx, aSortFailedBadC; "sort failed -- bad comparison routines?"
0x1800345ae  mov     rcx, rax
0x1800345b1  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800345b7  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x1800345be  mov     [rdi], rax
0x1800345c1  jmp     short loc_1800345C5
0x1800345c3  xor     edi, edi
0x1800345c5  mov     r8, [rbp+88h]
0x1800345cc  mov     rdx, rdi
0x1800345cf  mov     rcx, rbx
0x1800345d2  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z; UnBCL::InvalidOperationException::InvalidOperationException(UnBCL::String const *,UnBCL::Exception *)
0x1800345d8  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x1800345df  mov     [rbx], rax
0x1800345e2  jmp     short loc_1800345E6
0x1800345e4  xor     ebx, ebx
0x1800345e6  lea     rdx, aVoidCdeclUnbcl_4; "void __cdecl UnBCL::ArrayList<class UnB"...
0x1800345ed  mov     rcx, rbx
0x1800345f0  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x1800345f5  mov     [rbp+38h], rax
0x1800345f9  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180034600  lea     rcx, [rbp+38h]; pExceptionObject
0x180034604  call    _CxxThrowException_0
```
