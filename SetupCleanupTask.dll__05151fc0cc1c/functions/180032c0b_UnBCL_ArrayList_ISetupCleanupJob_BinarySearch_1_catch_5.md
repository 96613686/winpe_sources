# _UnBCL::ArrayList_ISetupCleanupJob___::BinarySearch_::_1_::catch$5

- ea: `0x180032c0b`
- end: `0x180032ca8`
- name: `_UnBCL::ArrayList_ISetupCleanupJob___::BinarySearch_::_1_::catch$5`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x180032c0b`

## import_xrefs

- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x180032c70`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x180032c70`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180032c1f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180032c36`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180032c1f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180032c36`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180032c52`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180032c52`

## string_xrefs

- `0x180032c84`: `int __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::BinarySearch(int,int,class ISetupCleanupJob *,struct UnBCL::IComparer<class ISetupCleanupJob *> *)`
- `0x180032c48`: `Compare failed -- bad comparison routines?`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_ISetupCleanupJob___::BinarySearch_::_1_::catch_5(__int64 a1, __int64 a2)
{
  UnBCL::InvalidOperationException *v3; // rbx
  UnBCL::String *v4; // rax
  const struct UnBCL::String *v5; // rdi

  v3 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
  *(_QWORD *)(a2 + 72) = v3;
  if ( v3 )
  {
    v4 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v5 = v4;
    *(_QWORD *)(a2 + 80) = v4;
    if ( v4 )
    {
      UnBCL::String::String(v4, L"Compare failed -- bad comparison routines?");
      *(_QWORD *)v5 = &UnBCL::String::`local vftable';
    }
    else
    {
      v5 = 0;
    }
    UnBCL::InvalidOperationException::InvalidOperationException(v3, v5, *(struct UnBCL::Exception **)(a2 + 88));
    *(_QWORD *)v3 = &UnBCL::InvalidOperationException::`local vftable';
  }
  else
  {
    v3 = 0;
  }
  *(_QWORD *)(a2 + 48) = AddStackTraceToException<SetupCleanupTaskException>(
                           v3,
                           "int __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::BinarySearch(int,int,class ISetupClea"
                           "nupJob *,struct UnBCL::IComparer<class ISetupCleanupJob *> *)");
  throw (UnBCL::InvalidOperationException **)(a2 + 48);
}

```

## disassembly

```asm
0x180032c0b  mov     [rsp+arg_8], rdx
0x180032c10  push    rbx
0x180032c11  push    rbp
0x180032c12  push    rdi
0x180032c13  sub     rsp, 20h
0x180032c17  mov     rbp, rdx
0x180032c1a  mov     ecx, 38h ; '8'
0x180032c1f  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180032c25  mov     rbx, rax
0x180032c28  mov     [rbp+48h], rax
0x180032c2c  test    rax, rax
0x180032c2f  jz      short loc_180032C82
0x180032c31  mov     ecx, 18h
0x180032c36  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180032c3c  mov     rdi, rax
0x180032c3f  mov     [rbp+50h], rax
0x180032c43  test    rax, rax
0x180032c46  jz      short loc_180032C64
0x180032c48  lea     rdx, aCompareFailedB; "Compare failed -- bad comparison routin"...
0x180032c4f  mov     rcx, rax
0x180032c52  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180032c58  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180032c5f  mov     [rdi], rax
0x180032c62  jmp     short loc_180032C66
0x180032c64  xor     edi, edi
0x180032c66  mov     r8, [rbp+58h]
0x180032c6a  mov     rdx, rdi
0x180032c6d  mov     rcx, rbx
0x180032c70  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z; UnBCL::InvalidOperationException::InvalidOperationException(UnBCL::String const *,UnBCL::Exception *)
0x180032c76  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180032c7d  mov     [rbx], rax
0x180032c80  jmp     short loc_180032C84
0x180032c82  xor     ebx, ebx
0x180032c84  lea     rdx, aIntCdeclUnbclA_4; "int __cdecl UnBCL::ArrayList<class ISet"...
0x180032c8b  mov     rcx, rbx
0x180032c8e  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x180032c93  mov     [rbp+30h], rax
0x180032c97  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180032c9e  lea     rcx, [rbp+30h]; pExceptionObject
0x180032ca2  call    _CxxThrowException_0
```
