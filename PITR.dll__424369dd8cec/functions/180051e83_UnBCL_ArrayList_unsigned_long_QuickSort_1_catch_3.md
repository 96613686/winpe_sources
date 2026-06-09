# _UnBCL::ArrayList_unsigned_long_::QuickSort_::_1_::catch$3

- ea: `0x180051e83`
- end: `0x180051f26`
- name: `_UnBCL::ArrayList_unsigned_long_::QuickSort_::_1_::catch$3`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180051e83`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051e97`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051eb1`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051e97`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051eb1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180051ed0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180051ed0`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x180051eee`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x180051eee`

## string_xrefs

- `0x180051ec6`: `sort failed -- bad comparison routines?`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_unsigned_long_::QuickSort_::_1_::catch_3(__int64 a1, __int64 a2)
{
  UnBCL::InvalidOperationException *v3; // rbx
  UnBCL::String *v4; // rax
  const struct UnBCL::String *v5; // rdi

  v3 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
  *(_QWORD *)(a2 + 160) = v3;
  if ( v3 )
  {
    v4 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v5 = v4;
    *(_QWORD *)(a2 + 144) = v4;
    if ( v4 )
    {
      UnBCL::String::String(v4, L"sort failed -- bad comparison routines?");
      *(_QWORD *)v5 = &UnBCL::String::`local vftable';
    }
    else
    {
      v5 = 0;
    }
    UnBCL::InvalidOperationException::InvalidOperationException(v3, v5, *(struct UnBCL::Exception **)(a2 + 64));
    *(_QWORD *)v3 = &UnBCL::InvalidOperationException::`local vftable';
  }
  else
  {
    v3 = 0;
  }
  *(_QWORD *)(a2 + 48) = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v3,
                           "void __cdecl UnBCL::ArrayList<unsigned long>::QuickSort(class UnBCL::ArrayList<unsigned long>"
                           " *,class UnBCL::ArrayList<unsigned long> *,int,int)");
  throw (UnBCL::InvalidOperationException **)(a2 + 48);
}

```

## disassembly

```asm
0x180051e83  mov     [rsp+arg_8], rdx
0x180051e88  push    rbx
0x180051e89  push    rbp
0x180051e8a  push    rdi
0x180051e8b  sub     rsp, 30h
0x180051e8f  mov     rbp, rdx
0x180051e92  mov     ecx, 38h ; '8'
0x180051e97  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180051e9d  mov     rbx, rax
0x180051ea0  mov     [rbp+0A0h], rax
0x180051ea7  test    rax, rax
0x180051eaa  jz      short loc_180051F00
0x180051eac  mov     ecx, 18h
0x180051eb1  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180051eb7  mov     rdi, rax
0x180051eba  mov     [rbp+90h], rax
0x180051ec1  test    rax, rax
0x180051ec4  jz      short loc_180051EE2
0x180051ec6  lea     rdx, aSortFailedBadC; "sort failed -- bad comparison routines?"
0x180051ecd  mov     rcx, rax
0x180051ed0  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180051ed6  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180051edd  mov     [rdi], rax
0x180051ee0  jmp     short loc_180051EE4
0x180051ee2  xor     edi, edi
0x180051ee4  mov     r8, [rbp+40h]
0x180051ee8  mov     rdx, rdi
0x180051eeb  mov     rcx, rbx
0x180051eee  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z; UnBCL::InvalidOperationException::InvalidOperationException(UnBCL::String const *,UnBCL::Exception *)
0x180051ef4  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180051efb  mov     [rbx], rax
0x180051efe  jmp     short loc_180051F02
0x180051f00  xor     ebx, ebx
0x180051f02  lea     rdx, aVoidCdeclUnbcl_2; "void __cdecl UnBCL::ArrayList<unsigned "...
0x180051f09  mov     rcx, rbx
0x180051f0c  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180051f11  mov     [rbp+30h], rax
0x180051f15  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180051f1c  lea     rcx, [rbp+30h]; pExceptionObject
0x180051f20  call    _CxxThrowException_0
```
