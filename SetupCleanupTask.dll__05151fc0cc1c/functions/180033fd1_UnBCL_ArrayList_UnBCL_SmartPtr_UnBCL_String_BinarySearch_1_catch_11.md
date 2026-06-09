# _UnBCL::ArrayList_UnBCL::SmartPtr_UnBCL::String___::BinarySearch_::_1_::catch$11

- ea: `0x180033fd1`
- end: `0x18003406e`
- name: `_UnBCL::ArrayList_UnBCL::SmartPtr_UnBCL::String___::BinarySearch_::_1_::catch$11`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x180033fd1`

## import_xrefs

- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x180034036`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x180034036`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180033fe5`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180033ffc`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180033fe5`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180033ffc`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180034018`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180034018`

## string_xrefs

- `0x18003400e`: `Compare failed -- bad comparison routines?`
- `0x18003404a`: `int __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::BinarySearch(int,int,class UnBCL::SmartPtr<class UnBCL::String>,struct UnBCL::IComparer<class UnBCL::SmartPtr<class UnBCL::String> > *)`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_UnBCL::SmartPtr_UnBCL::String___::BinarySearch_::_1_::catch_11(
        __int64 a1,
        __int64 a2)
{
  UnBCL::InvalidOperationException *v3; // rbx
  UnBCL::String *v4; // rax
  const struct UnBCL::String *v5; // rdi

  v3 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
  *(_QWORD *)(a2 + 32) = v3;
  if ( v3 )
  {
    v4 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v5 = v4;
    *(_QWORD *)(a2 + 104) = v4;
    if ( v4 )
    {
      UnBCL::String::String(v4, L"Compare failed -- bad comparison routines?");
      *(_QWORD *)v5 = &UnBCL::String::`local vftable';
    }
    else
    {
      v5 = 0;
    }
    UnBCL::InvalidOperationException::InvalidOperationException(v3, v5, *(struct UnBCL::Exception **)(a2 + 120));
    *(_QWORD *)v3 = &UnBCL::InvalidOperationException::`local vftable';
  }
  else
  {
    v3 = 0;
  }
  *(_QWORD *)(a2 + 72) = AddStackTraceToException<SetupCleanupTaskException>(
                           v3,
                           "int __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::BinarySearch(int,i"
                           "nt,class UnBCL::SmartPtr<class UnBCL::String>,struct UnBCL::IComparer<class UnBCL::SmartPtr<c"
                           "lass UnBCL::String> > *)");
  throw (UnBCL::InvalidOperationException **)(a2 + 72);
}

```

## disassembly

```asm
0x180033fd1  mov     [rsp+arg_8], rdx
0x180033fd6  push    rbx
0x180033fd7  push    rbp
0x180033fd8  push    rdi
0x180033fd9  sub     rsp, 20h
0x180033fdd  mov     rbp, rdx
0x180033fe0  mov     ecx, 38h ; '8'
0x180033fe5  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180033feb  mov     rbx, rax
0x180033fee  mov     [rbp+20h], rax
0x180033ff2  test    rax, rax
0x180033ff5  jz      short loc_180034048
0x180033ff7  mov     ecx, 18h
0x180033ffc  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180034002  mov     rdi, rax
0x180034005  mov     [rbp+68h], rax
0x180034009  test    rax, rax
0x18003400c  jz      short loc_18003402A
0x18003400e  lea     rdx, aCompareFailedB; "Compare failed -- bad comparison routin"...
0x180034015  mov     rcx, rax
0x180034018  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18003401e  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180034025  mov     [rdi], rax
0x180034028  jmp     short loc_18003402C
0x18003402a  xor     edi, edi
0x18003402c  mov     r8, [rbp+78h]
0x180034030  mov     rdx, rdi
0x180034033  mov     rcx, rbx
0x180034036  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z; UnBCL::InvalidOperationException::InvalidOperationException(UnBCL::String const *,UnBCL::Exception *)
0x18003403c  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180034043  mov     [rbx], rax
0x180034046  jmp     short loc_18003404A
0x180034048  xor     ebx, ebx
0x18003404a  lea     rdx, aIntCdeclUnbclA_2; "int __cdecl UnBCL::ArrayList<class UnBC"...
0x180034051  mov     rcx, rbx
0x180034054  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x180034059  mov     [rbp+48h], rax
0x18003405d  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180034064  lea     rcx, [rbp+48h]; pExceptionObject
0x180034068  call    _CxxThrowException_0
```
