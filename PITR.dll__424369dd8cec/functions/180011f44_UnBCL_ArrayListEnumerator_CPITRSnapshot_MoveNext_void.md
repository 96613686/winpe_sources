# UnBCL::_::ArrayListEnumerator<CPITRSnapshot *>::MoveNext(void)

- ea: `0x180011f44`
- end: `0x180011ff9`
- name: `?MoveNext@?$ArrayListEnumerator@PEAVCPITRSnapshot@@@_@UnBCL@@UEAAHXZ`
- size: `181`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011f30`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180011f44`
- `0x180053010`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180011fa2`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180011fa2`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180011fbf`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180011fbf`

## string_xrefs

- `0x180011fd3`: `int __cdecl UnBCL::_::ArrayListEnumerator<class CPITRSnapshot *>::MoveNext(void)`
- `0x180011fb5`: `MoveNext() called on invalidated enumerator`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::_::ArrayListEnumerator<CPITRSnapshot *>::MoveNext(__int64 a1)
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
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v8,
                         "int __cdecl UnBCL::_::ArrayListEnumerator<class CPITRSnapshot *>::MoveNext(void)");
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
0x180011f44  push    rbx
0x180011f46  sub     rsp, 20h
0x180011f4a  mov     rbx, rcx
0x180011f4d  mov     r8, [rcx-40h]
0x180011f51  mov     eax, [r8+18h]
0x180011f55  cmp     [rcx-20h], eax
0x180011f58  jnz     short loc_180011F9D
0x180011f5a  mov     edx, [rcx-30h]
0x180011f5d  cmp     edx, [rcx-34h]
0x180011f60  jg      short loc_180011F95
0x180011f62  inc     edx
0x180011f64  mov     [rcx-30h], edx
0x180011f67  cmp     edx, [rcx-34h]
0x180011f6a  jg      short loc_180011F95
0x180011f6c  mov     rax, [r8+8]
0x180011f70  movsxd  rcx, dword ptr [rax+10h]
0x180011f74  add     r8, 8
0x180011f78  add     rcx, r8
0x180011f7b  mov     rax, [rcx]
0x180011f7e  mov     rax, [rax+10h]
0x180011f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f87  mov     rcx, [rax]
0x180011f8a  mov     [rbx-28h], rcx
0x180011f8e  mov     eax, 1
0x180011f93  jmp     short loc_180011F97
0x180011f95  xor     eax, eax
0x180011f97  add     rsp, 20h
0x180011f9b  pop     rbx
0x180011f9c  retn
0x180011f9d  mov     ecx, 38h ; '8'
0x180011fa2  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180011fa8  mov     rbx, rax
0x180011fab  mov     [rsp+28h+arg_8], rax
0x180011fb0  test    rax, rax
0x180011fb3  jz      short loc_180011FD1
0x180011fb5  lea     rdx, aMovenextCalled; "MoveNext() called on invalidated enumer"...
0x180011fbc  mov     rcx, rax
0x180011fbf  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x180011fc5  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180011fcc  mov     [rbx], rax
0x180011fcf  jmp     short loc_180011FD3
0x180011fd1  xor     ebx, ebx
0x180011fd3  lea     rdx, aIntCdeclUnbclA_7; "int __cdecl UnBCL::_::ArrayListEnumerat"...
0x180011fda  mov     rcx, rbx
0x180011fdd  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180011fe2  mov     [rsp+28h+pExceptionObject], rax
0x180011fe7  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180011fee  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180011ff3  call    _CxxThrowException_0
```
