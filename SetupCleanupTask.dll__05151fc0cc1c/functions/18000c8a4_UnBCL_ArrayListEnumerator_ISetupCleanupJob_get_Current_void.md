# UnBCL::_::ArrayListEnumerator<ISetupCleanupJob *>::get_Current(void)

- ea: `0x18000c8a4`
- end: `0x18000c979`
- name: `?get_Current@?$ArrayListEnumerator@PEAVISetupCleanupJob@@@_@UnBCL@@UEBAPEAVISetupCleanupJob@@XZ`
- size: `213`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x18000c890`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x18000c8a4`

## import_xrefs

- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18000c8e3`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18000c93f`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18000c8e3`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18000c93f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000c8c6`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000c922`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000c8c6`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000c922`

## string_xrefs

- `0x18000c935`: `Current retrieved on enumerator before MoveNext()`

## pseudocode

```c
__int64 __fastcall UnBCL::_::ArrayListEnumerator<ISetupCleanupJob *>::get_Current(__int64 a1)
{
  int v1; // eax
  UnBCL::InvalidOperationException *v3; // rax
  UnBCL::Exception *v4; // rbx
  UnBCL::InvalidOperationException *v5; // rax
  UnBCL::Exception *v6; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  UnBCL::InvalidOperationException *v8; // [rsp+38h] [rbp+10h]

  v1 = *(_DWORD *)(a1 - 48);
  if ( v1 < *(_DWORD *)(a1 - 56) )
  {
    v5 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
    v6 = v5;
    v8 = v5;
    if ( v5 )
    {
      UnBCL::InvalidOperationException::InvalidOperationException(
        v5,
        L"Current retrieved on enumerator before MoveNext()");
      *(_QWORD *)v6 = &UnBCL::InvalidOperationException::`local vftable';
    }
    else
    {
      v6 = 0;
    }
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v6,
                         "class ISetupCleanupJob *__cdecl UnBCL::_::ArrayListEnumerator<class ISetupCleanupJob *>::get_Cu"
                         "rrent(void) const");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  if ( v1 > *(_DWORD *)(a1 - 52) )
  {
    v3 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
    v4 = v3;
    v8 = v3;
    if ( v3 )
    {
      UnBCL::InvalidOperationException::InvalidOperationException(
        v3,
        L"Current retrieved on enumerator beyond list end");
      *(_QWORD *)v4 = &UnBCL::InvalidOperationException::`local vftable';
    }
    else
    {
      v4 = 0;
    }
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v4,
                         "class ISetupCleanupJob *__cdecl UnBCL::_::ArrayListEnumerator<class ISetupCleanupJob *>::get_Cu"
                         "rrent(void) const");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  return *(_QWORD *)(a1 - 40);
}

```

## disassembly

```asm
0x18000c8a4  push    rbx
0x18000c8a6  sub     rsp, 20h
0x18000c8aa  mov     eax, [rcx-30h]
0x18000c8ad  cmp     eax, [rcx-38h]
0x18000c8b0  jl      short loc_18000C91D
0x18000c8b2  cmp     eax, [rcx-34h]
0x18000c8b5  jg      short loc_18000C8C1
0x18000c8b7  mov     rax, [rcx-28h]
0x18000c8bb  add     rsp, 20h
0x18000c8bf  pop     rbx
0x18000c8c0  retn
0x18000c8c1  mov     ecx, 38h ; '8'
0x18000c8c6  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000c8cc  mov     rbx, rax
0x18000c8cf  mov     [rsp+28h+arg_8], rax
0x18000c8d4  test    rax, rax
0x18000c8d7  jz      short loc_18000C8F5
0x18000c8d9  lea     rdx, aCurrentRetriev_0; "Current retrieved on enumerator beyond "...
0x18000c8e0  mov     rcx, rax
0x18000c8e3  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18000c8e9  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18000c8f0  mov     [rbx], rax
0x18000c8f3  jmp     short loc_18000C8F7
0x18000c8f5  xor     ebx, ebx
0x18000c8f7  lea     rdx, aClassIsetupcle; "class ISetupCleanupJob *__cdecl UnBCL::"...
0x18000c8fe  mov     rcx, rbx
0x18000c901  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x18000c906  mov     [rsp+28h+pExceptionObject], rax
0x18000c90b  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18000c912  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000c917  call    _CxxThrowException_0
0x18000c91d  mov     ecx, 38h ; '8'
0x18000c922  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000c928  mov     rbx, rax
0x18000c92b  mov     [rsp+28h+arg_8], rax
0x18000c930  test    rax, rax
0x18000c933  jz      short loc_18000C951
0x18000c935  lea     rdx, aCurrentRetriev; "Current retrieved on enumerator before "...
0x18000c93c  mov     rcx, rax
0x18000c93f  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18000c945  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18000c94c  mov     [rbx], rax
0x18000c94f  jmp     short loc_18000C953
0x18000c951  xor     ebx, ebx
0x18000c953  lea     rdx, aClassIsetupcle; "class ISetupCleanupJob *__cdecl UnBCL::"...
0x18000c95a  mov     rcx, rbx
0x18000c95d  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x18000c962  mov     [rsp+28h+pExceptionObject], rax
0x18000c967  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18000c96e  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000c973  call    _CxxThrowException_0
```
