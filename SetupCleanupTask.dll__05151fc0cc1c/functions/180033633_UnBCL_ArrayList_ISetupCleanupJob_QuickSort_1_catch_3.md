# _UnBCL::ArrayList_ISetupCleanupJob___::QuickSort_::_1_::catch$3

- ea: `0x180033633`
- end: `0x1800336d6`
- name: `_UnBCL::ArrayList_ISetupCleanupJob___::QuickSort_::_1_::catch$3`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x180033633`

## import_xrefs

- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x18003369e`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x18003369e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180033647`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180033661`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180033647`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180033661`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180033680`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180033680`

## string_xrefs

- `0x180033676`: `sort failed -- bad comparison routines?`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_ISetupCleanupJob___::QuickSort_::_1_::catch_3(__int64 a1, __int64 a2)
{
  UnBCL::InvalidOperationException *v3; // rbx
  UnBCL::String *v4; // rax
  const struct UnBCL::String *v5; // rdi

  v3 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
  *(_QWORD *)(a2 + 160) = v3;
  if ( v3 )
  {
    v4 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v5 = v4;
    *(_QWORD *)(a2 + 144) = v4;
    if ( v4 )
    {
      UnBCL::String::String(v4, L"sort failed -- bad comparison routines?");
      *(_QWORD *)v5 = &UnBCL::String::`local vftable';
    }
    else
    {
      v5 = 0;
    }
    UnBCL::InvalidOperationException::InvalidOperationException(v3, v5, *(struct UnBCL::Exception **)(a2 + 72));
    *(_QWORD *)v3 = &UnBCL::InvalidOperationException::`local vftable';
  }
  else
  {
    v3 = 0;
  }
  *(_QWORD *)(a2 + 56) = AddStackTraceToException<SetupCleanupTaskException>(
                           v3,
                           "void __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::QuickSort(class UnBCL::ArrayList<cla"
                           "ss ISetupCleanupJob *> *,class UnBCL::ArrayList<class ISetupCleanupJob *> *,int,int)");
  throw (UnBCL::InvalidOperationException **)(a2 + 56);
}

```

## disassembly

```asm
0x180033633  mov     [rsp+arg_8], rdx
0x180033638  push    rbx
0x180033639  push    rbp
0x18003363a  push    rdi
0x18003363b  sub     rsp, 30h
0x18003363f  mov     rbp, rdx
0x180033642  mov     ecx, 38h ; '8'
0x180033647  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003364d  mov     rbx, rax
0x180033650  mov     [rbp+0A0h], rax
0x180033657  test    rax, rax
0x18003365a  jz      short loc_1800336B0
0x18003365c  mov     ecx, 18h
0x180033661  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180033667  mov     rdi, rax
0x18003366a  mov     [rbp+90h], rax
0x180033671  test    rax, rax
0x180033674  jz      short loc_180033692
0x180033676  lea     rdx, aSortFailedBadC; "sort failed -- bad comparison routines?"
0x18003367d  mov     rcx, rax
0x180033680  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180033686  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x18003368d  mov     [rdi], rax
0x180033690  jmp     short loc_180033694
0x180033692  xor     edi, edi
0x180033694  mov     r8, [rbp+48h]
0x180033698  mov     rdx, rdi
0x18003369b  mov     rcx, rbx
0x18003369e  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z; UnBCL::InvalidOperationException::InvalidOperationException(UnBCL::String const *,UnBCL::Exception *)
0x1800336a4  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x1800336ab  mov     [rbx], rax
0x1800336ae  jmp     short loc_1800336B2
0x1800336b0  xor     ebx, ebx
0x1800336b2  lea     rdx, aVoidCdeclUnbcl_16; "void __cdecl UnBCL::ArrayList<class ISe"...
0x1800336b9  mov     rcx, rbx
0x1800336bc  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x1800336c1  mov     [rbp+38h], rax
0x1800336c5  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x1800336cc  lea     rcx, [rbp+38h]; pExceptionObject
0x1800336d0  call    _CxxThrowException_0
```
