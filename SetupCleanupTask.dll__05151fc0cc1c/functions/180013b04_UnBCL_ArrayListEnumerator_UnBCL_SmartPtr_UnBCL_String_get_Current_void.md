# UnBCL::_::ArrayListEnumerator<UnBCL::SmartPtr<UnBCL::String>>::get_Current(void)

- ea: `0x180013b04`
- end: `0x180013c01`
- name: `?get_Current@?$ArrayListEnumerator@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@_@UnBCL@@UEBA?AV?$SmartPtr@VString@UnBCL@@@3@XZ`
- size: `253`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180013af0`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x180013b04`

## import_xrefs

- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x180013b31`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x180013b31`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180013b6b`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180013bc7`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180013b6b`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180013bc7`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180013b4e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180013baa`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180013b4e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180013baa`

## string_xrefs

- `0x180013bbd`: `Current retrieved on enumerator before MoveNext()`

## pseudocode

```c
__int64 __fastcall UnBCL::_::ArrayListEnumerator<UnBCL::SmartPtr<UnBCL::String>>::get_Current(__int64 a1, __int64 a2)
{
  int v3; // eax
  UnBCL::InvalidOperationException *v5; // rax
  UnBCL::Exception *v6; // rbx
  UnBCL::InvalidOperationException *v7; // rax
  UnBCL::Exception *v8; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+48h] [rbp+10h]
  UnBCL::InvalidOperationException *v11; // [rsp+50h] [rbp+18h]

  v10 = a2;
  v3 = *(_DWORD *)(a1 - 56);
  if ( v3 < *(_DWORD *)(a1 - 64) )
  {
    v7 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
    v8 = v7;
    v11 = v7;
    if ( v7 )
    {
      UnBCL::InvalidOperationException::InvalidOperationException(
        v7,
        L"Current retrieved on enumerator before MoveNext()");
      *(_QWORD *)v8 = &UnBCL::InvalidOperationException::`local vftable';
    }
    else
    {
      v8 = 0;
    }
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v8,
                         "class UnBCL::SmartPtr<class UnBCL::String> __cdecl UnBCL::_::ArrayListEnumerator<class UnBCL::S"
                         "martPtr<class UnBCL::String> >::get_Current(void) const");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  if ( v3 > *(_DWORD *)(a1 - 60) )
  {
    v5 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
    v6 = v5;
    v11 = v5;
    if ( v5 )
    {
      UnBCL::InvalidOperationException::InvalidOperationException(
        v5,
        L"Current retrieved on enumerator beyond list end");
      *(_QWORD *)v6 = &UnBCL::InvalidOperationException::`local vftable';
    }
    else
    {
      v6 = 0;
    }
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v6,
                         "class UnBCL::SmartPtr<class UnBCL::String> __cdecl UnBCL::_::ArrayListEnumerator<class UnBCL::S"
                         "martPtr<class UnBCL::String> >::get_Current(void) const");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(a2, a1 - 48);
  return a2;
}

```

## disassembly

```asm
0x180013b04  mov     [rsp+arg_8], rdx
0x180013b09  push    rbx
0x180013b0a  sub     rsp, 30h
0x180013b0e  mov     rbx, rdx
0x180013b11  mov     [rsp+38h+var_18], 0
0x180013b19  mov     eax, [rcx-38h]
0x180013b1c  cmp     eax, [rcx-40h]
0x180013b1f  jl      loc_180013BA5
0x180013b25  cmp     eax, [rcx-3Ch]
0x180013b28  jg      short loc_180013B49
0x180013b2a  lea     rdx, [rcx-30h]
0x180013b2e  mov     rcx, rbx
0x180013b31  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x180013b37  nop
0x180013b38  mov     [rsp+38h+var_18], 1
0x180013b40  mov     rax, rbx
0x180013b43  add     rsp, 30h
0x180013b47  pop     rbx
0x180013b48  retn
0x180013b49  mov     ecx, 38h ; '8'
0x180013b4e  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180013b54  mov     rbx, rax
0x180013b57  mov     [rsp+38h+arg_10], rax
0x180013b5c  test    rax, rax
0x180013b5f  jz      short loc_180013B7D
0x180013b61  lea     rdx, aCurrentRetriev_0; "Current retrieved on enumerator beyond "...
0x180013b68  mov     rcx, rax
0x180013b6b  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x180013b71  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180013b78  mov     [rbx], rax
0x180013b7b  jmp     short loc_180013B7F
0x180013b7d  xor     ebx, ebx
0x180013b7f  lea     rdx, aClassUnbclSmar_2; "class UnBCL::SmartPtr<class UnBCL::Stri"...
0x180013b86  mov     rcx, rbx
0x180013b89  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x180013b8e  mov     [rsp+38h+pExceptionObject], rax
0x180013b93  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180013b9a  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180013b9f  call    _CxxThrowException_0
0x180013ba5  mov     ecx, 38h ; '8'
0x180013baa  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180013bb0  mov     rbx, rax
0x180013bb3  mov     [rsp+38h+arg_10], rax
0x180013bb8  test    rax, rax
0x180013bbb  jz      short loc_180013BD9
0x180013bbd  lea     rdx, aCurrentRetriev; "Current retrieved on enumerator before "...
0x180013bc4  mov     rcx, rax
0x180013bc7  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x180013bcd  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180013bd4  mov     [rbx], rax
0x180013bd7  jmp     short loc_180013BDB
0x180013bd9  xor     ebx, ebx
0x180013bdb  lea     rdx, aClassUnbclSmar_2; "class UnBCL::SmartPtr<class UnBCL::Stri"...
0x180013be2  mov     rcx, rbx
0x180013be5  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x180013bea  mov     [rsp+38h+pExceptionObject], rax
0x180013bef  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180013bf6  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180013bfb  call    _CxxThrowException_0
```
