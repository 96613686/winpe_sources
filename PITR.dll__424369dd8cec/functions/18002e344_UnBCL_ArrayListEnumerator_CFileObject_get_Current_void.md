# UnBCL::_::ArrayListEnumerator<CFileObject *>::get_Current(void)

- ea: `0x18002e344`
- end: `0x18002e419`
- name: `?get_Current@?$ArrayListEnumerator@PEAVCFileObject@@@_@UnBCL@@UEBAPEAVCFileObject@@XZ`
- size: `213`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002e330`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x18002e344`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e366`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e3c2`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e366`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e3c2`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e383`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e3df`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e383`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e3df`

## string_xrefs

- `0x18002e3d5`: `Current retrieved on enumerator before MoveNext()`

## pseudocode

```c
__int64 __fastcall UnBCL::_::ArrayListEnumerator<CFileObject *>::get_Current(__int64 a1)
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
                         "class CFileObject *__cdecl UnBCL::_::ArrayListEnumerator<class CFileObject *>::get_Current(void) const");
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
                         "class CFileObject *__cdecl UnBCL::_::ArrayListEnumerator<class CFileObject *>::get_Current(void) const");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  return *(_QWORD *)(a1 - 40);
}

```

## disassembly

```asm
0x18002e344  push    rbx
0x18002e346  sub     rsp, 20h
0x18002e34a  mov     eax, [rcx-30h]
0x18002e34d  cmp     eax, [rcx-38h]
0x18002e350  jl      short loc_18002E3BD
0x18002e352  cmp     eax, [rcx-34h]
0x18002e355  jg      short loc_18002E361
0x18002e357  mov     rax, [rcx-28h]
0x18002e35b  add     rsp, 20h
0x18002e35f  pop     rbx
0x18002e360  retn
0x18002e361  mov     ecx, 38h ; '8'
0x18002e366  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002e36c  mov     rbx, rax
0x18002e36f  mov     [rsp+28h+arg_8], rax
0x18002e374  test    rax, rax
0x18002e377  jz      short loc_18002E395
0x18002e379  lea     rdx, aCurrentRetriev_1; "Current retrieved on enumerator beyond "...
0x18002e380  mov     rcx, rax
0x18002e383  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18002e389  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18002e390  mov     [rbx], rax
0x18002e393  jmp     short loc_18002E397
0x18002e395  xor     ebx, ebx
0x18002e397  lea     rdx, aClassCfileobje_1; "class CFileObject *__cdecl UnBCL::_::Ar"...
0x18002e39e  mov     rcx, rbx
0x18002e3a1  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002e3a6  mov     [rsp+28h+pExceptionObject], rax
0x18002e3ab  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18002e3b2  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002e3b7  call    _CxxThrowException_0
0x18002e3bd  mov     ecx, 38h ; '8'
0x18002e3c2  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002e3c8  mov     rbx, rax
0x18002e3cb  mov     [rsp+28h+arg_8], rax
0x18002e3d0  test    rax, rax
0x18002e3d3  jz      short loc_18002E3F1
0x18002e3d5  lea     rdx, aCurrentRetriev; "Current retrieved on enumerator before "...
0x18002e3dc  mov     rcx, rax
0x18002e3df  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18002e3e5  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18002e3ec  mov     [rbx], rax
0x18002e3ef  jmp     short loc_18002E3F3
0x18002e3f1  xor     ebx, ebx
0x18002e3f3  lea     rdx, aClassCfileobje_1; "class CFileObject *__cdecl UnBCL::_::Ar"...
0x18002e3fa  mov     rcx, rbx
0x18002e3fd  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002e402  mov     [rsp+28h+pExceptionObject], rax
0x18002e407  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18002e40e  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002e413  call    _CxxThrowException_0
```
