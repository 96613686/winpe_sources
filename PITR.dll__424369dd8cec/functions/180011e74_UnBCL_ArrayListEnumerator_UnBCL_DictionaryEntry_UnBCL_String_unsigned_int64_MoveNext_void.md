# UnBCL::_::ArrayListEnumerator<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>::MoveNext(void)

- ea: `0x180011e74`
- end: `0x180011f29`
- name: `?MoveNext@?$ArrayListEnumerator@PEAV?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@@_@UnBCL@@UEAAHXZ`
- size: `181`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011e60`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180011e74`
- `0x180053010`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180011ed2`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180011ed2`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180011eef`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180011eef`

## string_xrefs

- `0x180011ee5`: `MoveNext() called on invalidated enumerator`
- `0x180011f03`: `int __cdecl UnBCL::_::ArrayListEnumerator<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *>::MoveNext(void)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::_::ArrayListEnumerator<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>::MoveNext(
        __int64 a1)
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
                         "int __cdecl UnBCL::_::ArrayListEnumerator<class UnBCL::DictionaryEntry<class UnBCL::String *,un"
                         "signed __int64> *>::MoveNext(void)");
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
0x180011e74  push    rbx
0x180011e76  sub     rsp, 20h
0x180011e7a  mov     rbx, rcx
0x180011e7d  mov     r8, [rcx-40h]
0x180011e81  mov     eax, [r8+18h]
0x180011e85  cmp     [rcx-20h], eax
0x180011e88  jnz     short loc_180011ECD
0x180011e8a  mov     edx, [rcx-30h]
0x180011e8d  cmp     edx, [rcx-34h]
0x180011e90  jg      short loc_180011EC5
0x180011e92  inc     edx
0x180011e94  mov     [rcx-30h], edx
0x180011e97  cmp     edx, [rcx-34h]
0x180011e9a  jg      short loc_180011EC5
0x180011e9c  mov     rax, [r8+8]
0x180011ea0  movsxd  rcx, dword ptr [rax+10h]
0x180011ea4  add     r8, 8
0x180011ea8  add     rcx, r8
0x180011eab  mov     rax, [rcx]
0x180011eae  mov     rax, [rax+10h]
0x180011eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011eb7  mov     rcx, [rax]
0x180011eba  mov     [rbx-28h], rcx
0x180011ebe  mov     eax, 1
0x180011ec3  jmp     short loc_180011EC7
0x180011ec5  xor     eax, eax
0x180011ec7  add     rsp, 20h
0x180011ecb  pop     rbx
0x180011ecc  retn
0x180011ecd  mov     ecx, 38h ; '8'
0x180011ed2  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180011ed8  mov     rbx, rax
0x180011edb  mov     [rsp+28h+arg_8], rax
0x180011ee0  test    rax, rax
0x180011ee3  jz      short loc_180011F01
0x180011ee5  lea     rdx, aMovenextCalled; "MoveNext() called on invalidated enumer"...
0x180011eec  mov     rcx, rax
0x180011eef  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x180011ef5  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180011efc  mov     [rbx], rax
0x180011eff  jmp     short loc_180011F03
0x180011f01  xor     ebx, ebx
0x180011f03  lea     rdx, aIntCdeclUnbclA_11; "int __cdecl UnBCL::_::ArrayListEnumerat"...
0x180011f0a  mov     rcx, rbx
0x180011f0d  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180011f12  mov     [rsp+28h+pExceptionObject], rax
0x180011f17  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180011f1e  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180011f23  call    _CxxThrowException_0
```
