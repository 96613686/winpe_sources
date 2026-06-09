# UnBCL::_::ArrayListEnumerator<UnBCL::SmartPtr<UnBCL::String>>::MoveNext(void)

- ea: `0x180010bd4`
- end: `0x180010c8f`
- name: `?MoveNext@?$ArrayListEnumerator@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@_@UnBCL@@UEAAHXZ`
- size: `187`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180010bc0`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x180010bd4`
- `0x180036010`

## import_xrefs

- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180010c55`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180010c55`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180010c1e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180010c1e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180010c38`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180010c38`

## string_xrefs

- `0x180010c4b`: `MoveNext() called on invalidated enumerator`
- `0x180010c69`: `int __cdecl UnBCL::_::ArrayListEnumerator<class UnBCL::SmartPtr<class UnBCL::String> >::MoveNext(void)`

## pseudocode

```c
__int64 __fastcall UnBCL::_::ArrayListEnumerator<UnBCL::SmartPtr<UnBCL::String>>::MoveNext(__int64 a1)
{
  __int64 v2; // r8
  int v3; // edx
  int v4; // edx
  __int64 v5; // rcx
  __int64 v6; // rax
  UnBCL::InvalidOperationException *v8; // rax
  UnBCL::Exception *v9; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  UnBCL::InvalidOperationException *v11; // [rsp+38h] [rbp+10h]

  v2 = *(_QWORD *)(a1 - 72);
  if ( *(_DWORD *)(a1 - 32) != *(_DWORD *)(v2 + 24) )
  {
    v8 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
    v9 = v8;
    v11 = v8;
    if ( v8 )
    {
      UnBCL::InvalidOperationException::InvalidOperationException(v8, L"MoveNext() called on invalidated enumerator");
      *(_QWORD *)v9 = &UnBCL::InvalidOperationException::`local vftable';
    }
    else
    {
      v9 = 0;
    }
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v9,
                         "int __cdecl UnBCL::_::ArrayListEnumerator<class UnBCL::SmartPtr<class UnBCL::String> >::MoveNext(void)");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  v3 = *(_DWORD *)(a1 - 56);
  if ( v3 > *(_DWORD *)(a1 - 60) )
    return 0;
  v4 = v3 + 1;
  *(_DWORD *)(a1 - 56) = v4;
  if ( v4 > *(_DWORD *)(a1 - 60) )
    return 0;
  v5 = v2 + 8 + *(int *)(*(_QWORD *)(v2 + 8) + 16LL);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  UnBCL::SmartPtr<UnBCL::String>::operator=(a1 - 48, v6);
  return 1;
}

```

## disassembly

```asm
0x180010bd4  push    rbx
0x180010bd6  sub     rsp, 20h
0x180010bda  mov     rbx, rcx
0x180010bdd  mov     r8, [rcx-48h]
0x180010be1  mov     eax, [r8+18h]
0x180010be5  cmp     [rcx-20h], eax
0x180010be8  jnz     short loc_180010C33
0x180010bea  mov     edx, [rcx-38h]
0x180010bed  cmp     edx, [rcx-3Ch]
0x180010bf0  jg      short loc_180010C2B
0x180010bf2  inc     edx
0x180010bf4  mov     [rcx-38h], edx
0x180010bf7  cmp     edx, [rcx-3Ch]
0x180010bfa  jg      short loc_180010C2B
0x180010bfc  mov     rax, [r8+8]
0x180010c00  movsxd  rcx, dword ptr [rax+10h]
0x180010c04  add     r8, 8
0x180010c08  add     rcx, r8
0x180010c0b  mov     rax, [rcx]
0x180010c0e  mov     rax, [rax+10h]
0x180010c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c17  mov     rdx, rax
0x180010c1a  lea     rcx, [rbx-30h]
0x180010c1e  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180010c24  mov     eax, 1
0x180010c29  jmp     short loc_180010C2D
0x180010c2b  xor     eax, eax
0x180010c2d  add     rsp, 20h
0x180010c31  pop     rbx
0x180010c32  retn
0x180010c33  mov     ecx, 38h ; '8'
0x180010c38  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180010c3e  mov     rbx, rax
0x180010c41  mov     [rsp+28h+arg_8], rax
0x180010c46  test    rax, rax
0x180010c49  jz      short loc_180010C67
0x180010c4b  lea     rdx, aMovenextCalled; "MoveNext() called on invalidated enumer"...
0x180010c52  mov     rcx, rax
0x180010c55  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x180010c5b  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180010c62  mov     [rbx], rax
0x180010c65  jmp     short loc_180010C69
0x180010c67  xor     ebx, ebx
0x180010c69  lea     rdx, aIntCdeclUnbclA_7; "int __cdecl UnBCL::_::ArrayListEnumerat"...
0x180010c70  mov     rcx, rbx
0x180010c73  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x180010c78  mov     [rsp+28h+pExceptionObject], rax
0x180010c7d  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180010c84  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180010c89  call    _CxxThrowException_0
```
