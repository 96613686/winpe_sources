# UnBCL::_::ArrayListEnumerator<ISetupCleanupJob *>::MoveNext(void)

- ea: `0x18000a844`
- end: `0x18000a8f9`
- name: `?MoveNext@?$ArrayListEnumerator@PEAVISetupCleanupJob@@@_@UnBCL@@UEAAHXZ`
- size: `181`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18000a830`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x18000a844`
- `0x180036010`

## import_xrefs

- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18000a8bf`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18000a8bf`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000a8a2`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000a8a2`

## string_xrefs

- `0x18000a8d3`: `int __cdecl UnBCL::_::ArrayListEnumerator<class ISetupCleanupJob *>::MoveNext(void)`
- `0x18000a8b5`: `MoveNext() called on invalidated enumerator`

## pseudocode

```c
__int64 __fastcall UnBCL::_::ArrayListEnumerator<ISetupCleanupJob *>::MoveNext(__int64 a1)
{
  __int64 v2; // r8
  int v3; // edx
  int v4; // edx
  __int64 v5; // rcx
  UnBCL::InvalidOperationException *v7; // rax
  UnBCL::Exception *v8; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  UnBCL::InvalidOperationException *v10; // [rsp+38h] [rbp+10h]

  v2 = *(_QWORD *)(a1 - 64);
  if ( *(_DWORD *)(a1 - 32) != *(_DWORD *)(v2 + 24) )
  {
    v7 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
    v8 = v7;
    v10 = v7;
    if ( v7 )
    {
      UnBCL::InvalidOperationException::InvalidOperationException(v7, L"MoveNext() called on invalidated enumerator");
      *(_QWORD *)v8 = &UnBCL::InvalidOperationException::`local vftable';
    }
    else
    {
      v8 = 0;
    }
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v8,
                         "int __cdecl UnBCL::_::ArrayListEnumerator<class ISetupCleanupJob *>::MoveNext(void)");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  v3 = *(_DWORD *)(a1 - 48);
  if ( v3 > *(_DWORD *)(a1 - 52) )
    return 0;
  v4 = v3 + 1;
  *(_DWORD *)(a1 - 48) = v4;
  if ( v4 > *(_DWORD *)(a1 - 52) )
    return 0;
  v5 = v2 + 8 + *(int *)(*(_QWORD *)(v2 + 8) + 16LL);
  *(_QWORD *)(a1 - 40) = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  return 1;
}

```

## disassembly

```asm
0x18000a844  push    rbx
0x18000a846  sub     rsp, 20h
0x18000a84a  mov     rbx, rcx
0x18000a84d  mov     r8, [rcx-40h]
0x18000a851  mov     eax, [r8+18h]
0x18000a855  cmp     [rcx-20h], eax
0x18000a858  jnz     short loc_18000A89D
0x18000a85a  mov     edx, [rcx-30h]
0x18000a85d  cmp     edx, [rcx-34h]
0x18000a860  jg      short loc_18000A895
0x18000a862  inc     edx
0x18000a864  mov     [rcx-30h], edx
0x18000a867  cmp     edx, [rcx-34h]
0x18000a86a  jg      short loc_18000A895
0x18000a86c  mov     rax, [r8+8]
0x18000a870  movsxd  rcx, dword ptr [rax+10h]
0x18000a874  add     r8, 8
0x18000a878  add     rcx, r8
0x18000a87b  mov     rax, [rcx]
0x18000a87e  mov     rax, [rax+10h]
0x18000a882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a887  mov     rcx, [rax]
0x18000a88a  mov     [rbx-28h], rcx
0x18000a88e  mov     eax, 1
0x18000a893  jmp     short loc_18000A897
0x18000a895  xor     eax, eax
0x18000a897  add     rsp, 20h
0x18000a89b  pop     rbx
0x18000a89c  retn
0x18000a89d  mov     ecx, 38h ; '8'
0x18000a8a2  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000a8a8  mov     rbx, rax
0x18000a8ab  mov     [rsp+28h+arg_8], rax
0x18000a8b0  test    rax, rax
0x18000a8b3  jz      short loc_18000A8D1
0x18000a8b5  lea     rdx, aMovenextCalled; "MoveNext() called on invalidated enumer"...
0x18000a8bc  mov     rcx, rax
0x18000a8bf  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18000a8c5  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18000a8cc  mov     [rbx], rax
0x18000a8cf  jmp     short loc_18000A8D3
0x18000a8d1  xor     ebx, ebx
0x18000a8d3  lea     rdx, aIntCdeclUnbclA_1; "int __cdecl UnBCL::_::ArrayListEnumerat"...
0x18000a8da  mov     rcx, rbx
0x18000a8dd  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x18000a8e2  mov     [rsp+28h+pExceptionObject], rax
0x18000a8e7  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18000a8ee  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000a8f3  call    _CxxThrowException_0
```
