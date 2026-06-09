# UnBCL::_::ArrayListEnumerator<CPITRSnapshot *>::get_Current(void)

- ea: `0x18001e614`
- end: `0x18001e6e9`
- name: `?get_Current@?$ArrayListEnumerator@PEAVCPITRSnapshot@@@_@UnBCL@@UEBAPEAVCPITRSnapshot@@XZ`
- size: `213`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001e600`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x18001e614`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18001e636`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18001e692`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18001e636`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18001e692`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18001e653`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18001e6af`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18001e653`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18001e6af`

## string_xrefs

- `0x18001e6a5`: `Current retrieved on enumerator before MoveNext()`

## pseudocode

```c
__int64 __fastcall UnBCL::_::ArrayListEnumerator<CPITRSnapshot *>::get_Current(__int64 a1)
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
                         "class CPITRSnapshot *__cdecl UnBCL::_::ArrayListEnumerator<class CPITRSnapshot *>::get_Current(void) const");
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
                         "class CPITRSnapshot *__cdecl UnBCL::_::ArrayListEnumerator<class CPITRSnapshot *>::get_Current(void) const");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  return *(_QWORD *)(a1 - 40);
}

```

## disassembly

```asm
0x18001e614  push    rbx
0x18001e616  sub     rsp, 20h
0x18001e61a  mov     eax, [rcx-30h]
0x18001e61d  cmp     eax, [rcx-38h]
0x18001e620  jl      short loc_18001E68D
0x18001e622  cmp     eax, [rcx-34h]
0x18001e625  jg      short loc_18001E631
0x18001e627  mov     rax, [rcx-28h]
0x18001e62b  add     rsp, 20h
0x18001e62f  pop     rbx
0x18001e630  retn
0x18001e631  mov     ecx, 38h ; '8'
0x18001e636  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18001e63c  mov     rbx, rax
0x18001e63f  mov     [rsp+28h+arg_8], rax
0x18001e644  test    rax, rax
0x18001e647  jz      short loc_18001E665
0x18001e649  lea     rdx, aCurrentRetriev_1; "Current retrieved on enumerator beyond "...
0x18001e650  mov     rcx, rax
0x18001e653  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18001e659  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18001e660  mov     [rbx], rax
0x18001e663  jmp     short loc_18001E667
0x18001e665  xor     ebx, ebx
0x18001e667  lea     rdx, aClassCpitrsnap_0; "class CPITRSnapshot *__cdecl UnBCL::_::"...
0x18001e66e  mov     rcx, rbx
0x18001e671  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18001e676  mov     [rsp+28h+pExceptionObject], rax
0x18001e67b  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18001e682  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18001e687  call    _CxxThrowException_0
0x18001e68d  mov     ecx, 38h ; '8'
0x18001e692  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18001e698  mov     rbx, rax
0x18001e69b  mov     [rsp+28h+arg_8], rax
0x18001e6a0  test    rax, rax
0x18001e6a3  jz      short loc_18001E6C1
0x18001e6a5  lea     rdx, aCurrentRetriev; "Current retrieved on enumerator before "...
0x18001e6ac  mov     rcx, rax
0x18001e6af  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18001e6b5  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18001e6bc  mov     [rbx], rax
0x18001e6bf  jmp     short loc_18001E6C3
0x18001e6c1  xor     ebx, ebx
0x18001e6c3  lea     rdx, aClassCpitrsnap_0; "class CPITRSnapshot *__cdecl UnBCL::_::"...
0x18001e6ca  mov     rcx, rbx
0x18001e6cd  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18001e6d2  mov     [rsp+28h+pExceptionObject], rax
0x18001e6d7  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18001e6de  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18001e6e3  call    _CxxThrowException_0
```
