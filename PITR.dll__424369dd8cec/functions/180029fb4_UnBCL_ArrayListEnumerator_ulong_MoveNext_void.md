# UnBCL::_::ArrayListEnumerator<ulong>::MoveNext(void)

- ea: `0x180029fb4`
- end: `0x18002a067`
- name: `?MoveNext@?$ArrayListEnumerator@K@_@UnBCL@@UEAAHXZ`
- size: `179`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180029fa0`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180029fb4`
- `0x180053010`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002a010`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002a010`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002a02d`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002a02d`

## string_xrefs

- `0x18002a023`: `MoveNext() called on invalidated enumerator`
- `0x18002a041`: `int __cdecl UnBCL::_::ArrayListEnumerator<unsigned long>::MoveNext(void)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::_::ArrayListEnumerator<unsigned long>::MoveNext(__int64 a1)
{
  __int64 v2; // r8
  int v3; // edx
  int v4; // edx
  __int64 v5; // rcx
  UnBCL::InvalidOperationException *v7; // rax
  UnBCL::Exception *v8; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  UnBCL::InvalidOperationException *v10; // [rsp+38h] [rbp+10h]

  v2 = *(_QWORD *)(a1 - 56);
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
                         "int __cdecl UnBCL::_::ArrayListEnumerator<unsigned long>::MoveNext(void)");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  v3 = *(_DWORD *)(a1 - 40);
  if ( v3 > *(_DWORD *)(a1 - 44) )
    return 0;
  v4 = v3 + 1;
  *(_DWORD *)(a1 - 40) = v4;
  if ( v4 > *(_DWORD *)(a1 - 44) )
    return 0;
  v5 = v2 + 8 + *(int *)(*(_QWORD *)(v2 + 8) + 16LL);
  *(_DWORD *)(a1 - 36) = *(_DWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  return 1;
}

```

## disassembly

```asm
0x180029fb4  push    rbx
0x180029fb6  sub     rsp, 20h
0x180029fba  mov     rbx, rcx
0x180029fbd  mov     r8, [rcx-38h]
0x180029fc1  mov     eax, [r8+18h]
0x180029fc5  cmp     [rcx-20h], eax
0x180029fc8  jnz     short loc_18002A00B
0x180029fca  mov     edx, [rcx-28h]
0x180029fcd  cmp     edx, [rcx-2Ch]
0x180029fd0  jg      short loc_18002A003
0x180029fd2  inc     edx
0x180029fd4  mov     [rcx-28h], edx
0x180029fd7  cmp     edx, [rcx-2Ch]
0x180029fda  jg      short loc_18002A003
0x180029fdc  mov     rax, [r8+8]
0x180029fe0  movsxd  rcx, dword ptr [rax+10h]
0x180029fe4  add     r8, 8
0x180029fe8  add     rcx, r8
0x180029feb  mov     rax, [rcx]
0x180029fee  mov     rax, [rax+10h]
0x180029ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ff7  mov     ecx, [rax]
0x180029ff9  mov     [rbx-24h], ecx
0x180029ffc  mov     eax, 1
0x18002a001  jmp     short loc_18002A005
0x18002a003  xor     eax, eax
0x18002a005  add     rsp, 20h
0x18002a009  pop     rbx
0x18002a00a  retn
0x18002a00b  mov     ecx, 38h ; '8'
0x18002a010  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002a016  mov     rbx, rax
0x18002a019  mov     [rsp+28h+arg_8], rax
0x18002a01e  test    rax, rax
0x18002a021  jz      short loc_18002A03F
0x18002a023  lea     rdx, aMovenextCalled; "MoveNext() called on invalidated enumer"...
0x18002a02a  mov     rcx, rax
0x18002a02d  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18002a033  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18002a03a  mov     [rbx], rax
0x18002a03d  jmp     short loc_18002A041
0x18002a03f  xor     ebx, ebx
0x18002a041  lea     rdx, aIntCdeclUnbclA_3; "int __cdecl UnBCL::_::ArrayListEnumerat"...
0x18002a048  mov     rcx, rbx
0x18002a04b  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002a050  mov     [rsp+28h+pExceptionObject], rax
0x18002a055  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18002a05c  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002a061  call    _CxxThrowException_0
```
