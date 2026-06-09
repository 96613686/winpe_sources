# UnBCL::_::ArrayListEnumerator<ulong>::get_Current(void)

- ea: `0x18002e254`
- end: `0x18002e328`
- name: `?get_Current@?$ArrayListEnumerator@K@_@UnBCL@@UEBAKXZ`
- size: `212`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002e240`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x18002e254`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e275`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e2d1`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e275`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e2d1`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e292`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e2ee`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e292`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e2ee`

## string_xrefs

- `0x18002e2e4`: `Current retrieved on enumerator before MoveNext()`

## pseudocode

```c
__int64 __fastcall UnBCL::_::ArrayListEnumerator<unsigned long>::get_Current(__int64 a1)
{
  int v1; // eax
  UnBCL::InvalidOperationException *v3; // rax
  UnBCL::Exception *v4; // rbx
  UnBCL::InvalidOperationException *v5; // rax
  UnBCL::Exception *v6; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  UnBCL::InvalidOperationException *v8; // [rsp+38h] [rbp+10h]

  v1 = *(_DWORD *)(a1 - 40);
  if ( v1 < *(_DWORD *)(a1 - 48) )
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
                         "unsigned long __cdecl UnBCL::_::ArrayListEnumerator<unsigned long>::get_Current(void) const");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  if ( v1 > *(_DWORD *)(a1 - 44) )
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
                         "unsigned long __cdecl UnBCL::_::ArrayListEnumerator<unsigned long>::get_Current(void) const");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  return *(unsigned int *)(a1 - 36);
}

```

## disassembly

```asm
0x18002e254  push    rbx
0x18002e256  sub     rsp, 20h
0x18002e25a  mov     eax, [rcx-28h]
0x18002e25d  cmp     eax, [rcx-30h]
0x18002e260  jl      short loc_18002E2CC
0x18002e262  cmp     eax, [rcx-2Ch]
0x18002e265  jg      short loc_18002E270
0x18002e267  mov     eax, [rcx-24h]
0x18002e26a  add     rsp, 20h
0x18002e26e  pop     rbx
0x18002e26f  retn
0x18002e270  mov     ecx, 38h ; '8'
0x18002e275  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002e27b  mov     rbx, rax
0x18002e27e  mov     [rsp+28h+arg_8], rax
0x18002e283  test    rax, rax
0x18002e286  jz      short loc_18002E2A4
0x18002e288  lea     rdx, aCurrentRetriev_1; "Current retrieved on enumerator beyond "...
0x18002e28f  mov     rcx, rax
0x18002e292  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18002e298  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18002e29f  mov     [rbx], rax
0x18002e2a2  jmp     short loc_18002E2A6
0x18002e2a4  xor     ebx, ebx
0x18002e2a6  lea     rdx, aUnsignedLongCd_1; "unsigned long __cdecl UnBCL::_::ArrayLi"...
0x18002e2ad  mov     rcx, rbx
0x18002e2b0  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002e2b5  mov     [rsp+28h+pExceptionObject], rax
0x18002e2ba  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18002e2c1  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002e2c6  call    _CxxThrowException_0
0x18002e2cc  mov     ecx, 38h ; '8'
0x18002e2d1  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002e2d7  mov     rbx, rax
0x18002e2da  mov     [rsp+28h+arg_8], rax
0x18002e2df  test    rax, rax
0x18002e2e2  jz      short loc_18002E300
0x18002e2e4  lea     rdx, aCurrentRetriev; "Current retrieved on enumerator before "...
0x18002e2eb  mov     rcx, rax
0x18002e2ee  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18002e2f4  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18002e2fb  mov     [rbx], rax
0x18002e2fe  jmp     short loc_18002E302
0x18002e300  xor     ebx, ebx
0x18002e302  lea     rdx, aUnsignedLongCd_1; "unsigned long __cdecl UnBCL::_::ArrayLi"...
0x18002e309  mov     rcx, rbx
0x18002e30c  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002e311  mov     [rsp+28h+pExceptionObject], rax
0x18002e316  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18002e31d  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002e322  call    _CxxThrowException_0
```
