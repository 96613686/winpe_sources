# UnBCL::_::ArrayListEnumerator<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>::get_Current(void)

- ea: `0x18001e524`
- end: `0x18001e5f9`
- name: `?get_Current@?$ArrayListEnumerator@PEAV?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@@_@UnBCL@@UEBAPEAV?$DictionaryEntry@PEAVString@UnBCL@@_K@3@XZ`
- size: `213`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001e510`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x18001e524`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18001e546`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18001e5a2`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18001e546`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18001e5a2`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18001e563`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18001e5bf`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18001e563`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18001e5bf`

## string_xrefs

- `0x18001e5b5`: `Current retrieved on enumerator before MoveNext()`

## pseudocode

```c
__int64 __fastcall UnBCL::_::ArrayListEnumerator<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>::get_Current(
        __int64 a1)
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
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v6,
                         "class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *__cdecl UnBCL::_::ArrayLi"
                         "stEnumerator<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *>::get_Current(void) const");
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
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v4,
                         "class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *__cdecl UnBCL::_::ArrayLi"
                         "stEnumerator<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *>::get_Current(void) const");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  return *(_QWORD *)(a1 - 40);
}

```

## disassembly

```asm
0x18001e524  push    rbx
0x18001e526  sub     rsp, 20h
0x18001e52a  mov     eax, [rcx-30h]
0x18001e52d  cmp     eax, [rcx-38h]
0x18001e530  jl      short loc_18001E59D
0x18001e532  cmp     eax, [rcx-34h]
0x18001e535  jg      short loc_18001E541
0x18001e537  mov     rax, [rcx-28h]
0x18001e53b  add     rsp, 20h
0x18001e53f  pop     rbx
0x18001e540  retn
0x18001e541  mov     ecx, 38h ; '8'
0x18001e546  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18001e54c  mov     rbx, rax
0x18001e54f  mov     [rsp+28h+arg_8], rax
0x18001e554  test    rax, rax
0x18001e557  jz      short loc_18001E575
0x18001e559  lea     rdx, aCurrentRetriev_1; "Current retrieved on enumerator beyond "...
0x18001e560  mov     rcx, rax
0x18001e563  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18001e569  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18001e570  mov     [rbx], rax
0x18001e573  jmp     short loc_18001E577
0x18001e575  xor     ebx, ebx
0x18001e577  lea     rdx, aClassUnbclDict_0; "class UnBCL::DictionaryEntry<class UnBC"...
0x18001e57e  mov     rcx, rbx
0x18001e581  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18001e586  mov     [rsp+28h+pExceptionObject], rax
0x18001e58b  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18001e592  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18001e597  call    _CxxThrowException_0
0x18001e59d  mov     ecx, 38h ; '8'
0x18001e5a2  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18001e5a8  mov     rbx, rax
0x18001e5ab  mov     [rsp+28h+arg_8], rax
0x18001e5b0  test    rax, rax
0x18001e5b3  jz      short loc_18001E5D1
0x18001e5b5  lea     rdx, aCurrentRetriev; "Current retrieved on enumerator before "...
0x18001e5bc  mov     rcx, rax
0x18001e5bf  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18001e5c5  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18001e5cc  mov     [rbx], rax
0x18001e5cf  jmp     short loc_18001E5D3
0x18001e5d1  xor     ebx, ebx
0x18001e5d3  lea     rdx, aClassUnbclDict_0; "class UnBCL::DictionaryEntry<class UnBC"...
0x18001e5da  mov     rcx, rbx
0x18001e5dd  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18001e5e2  mov     [rsp+28h+pExceptionObject], rax
0x18001e5e7  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18001e5ee  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18001e5f3  call    _CxxThrowException_0
```
