# UnBCL::_::ArrayListEnumerator<CFileObject *>::MoveNext(void)

- ea: `0x18002a084`
- end: `0x18002a139`
- name: `?MoveNext@?$ArrayListEnumerator@PEAVCFileObject@@@_@UnBCL@@UEAAHXZ`
- size: `181`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002a070`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x18002a084`
- `0x180053010`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002a0e2`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002a0e2`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002a0ff`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002a0ff`

## string_xrefs

- `0x18002a0f5`: `MoveNext() called on invalidated enumerator`
- `0x18002a113`: `int __cdecl UnBCL::_::ArrayListEnumerator<class CFileObject *>::MoveNext(void)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::_::ArrayListEnumerator<CFileObject *>::MoveNext(__int64 a1)
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
                         "int __cdecl UnBCL::_::ArrayListEnumerator<class CFileObject *>::MoveNext(void)");
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
0x18002a084  push    rbx
0x18002a086  sub     rsp, 20h
0x18002a08a  mov     rbx, rcx
0x18002a08d  mov     r8, [rcx-40h]
0x18002a091  mov     eax, [r8+18h]
0x18002a095  cmp     [rcx-20h], eax
0x18002a098  jnz     short loc_18002A0DD
0x18002a09a  mov     edx, [rcx-30h]
0x18002a09d  cmp     edx, [rcx-34h]
0x18002a0a0  jg      short loc_18002A0D5
0x18002a0a2  inc     edx
0x18002a0a4  mov     [rcx-30h], edx
0x18002a0a7  cmp     edx, [rcx-34h]
0x18002a0aa  jg      short loc_18002A0D5
0x18002a0ac  mov     rax, [r8+8]
0x18002a0b0  movsxd  rcx, dword ptr [rax+10h]
0x18002a0b4  add     r8, 8
0x18002a0b8  add     rcx, r8
0x18002a0bb  mov     rax, [rcx]
0x18002a0be  mov     rax, [rax+10h]
0x18002a0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0c7  mov     rcx, [rax]
0x18002a0ca  mov     [rbx-28h], rcx
0x18002a0ce  mov     eax, 1
0x18002a0d3  jmp     short loc_18002A0D7
0x18002a0d5  xor     eax, eax
0x18002a0d7  add     rsp, 20h
0x18002a0db  pop     rbx
0x18002a0dc  retn
0x18002a0dd  mov     ecx, 38h ; '8'
0x18002a0e2  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002a0e8  mov     rbx, rax
0x18002a0eb  mov     [rsp+28h+arg_8], rax
0x18002a0f0  test    rax, rax
0x18002a0f3  jz      short loc_18002A111
0x18002a0f5  lea     rdx, aMovenextCalled; "MoveNext() called on invalidated enumer"...
0x18002a0fc  mov     rcx, rax
0x18002a0ff  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18002a105  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18002a10c  mov     [rbx], rax
0x18002a10f  jmp     short loc_18002A113
0x18002a111  xor     ebx, ebx
0x18002a113  lea     rdx, aIntCdeclUnbclA_9; "int __cdecl UnBCL::_::ArrayListEnumerat"...
0x18002a11a  mov     rcx, rbx
0x18002a11d  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002a122  mov     [rsp+28h+pExceptionObject], rax
0x18002a127  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18002a12e  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002a133  call    _CxxThrowException_0
```
