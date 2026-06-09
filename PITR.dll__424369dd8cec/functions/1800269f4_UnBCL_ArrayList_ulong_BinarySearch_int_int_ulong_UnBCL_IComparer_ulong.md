# UnBCL::ArrayList<ulong>::BinarySearch(int,int,ulong,UnBCL::IComparer<ulong> *)

- ea: `0x1800269f4`
- end: `0x180026b7a`
- name: `?BinarySearch@?$ArrayList@K@UnBCL@@AEAAHHHKPEAU?$IComparer@K@2@@Z`
- size: `390`
- prototype: `__int64 __fastcall(__int64, __int64, int, unsigned int, __int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180026b80`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x1800269f4`
- `0x18002727c`
- `0x180053010`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180026ac7`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180026b23`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180026ac7`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180026b23`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x180026b40`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x180026b40`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180026ae4`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180026ae4`

## string_xrefs

- `0x180026af8`: `int __cdecl UnBCL::ArrayList<unsigned long>::BinarySearch(int,int,unsigned long,struct UnBCL::IComparer<unsigned long> *)`
- `0x180026b54`: `int __cdecl UnBCL::ArrayList<unsigned long>::BinarySearch(int,int,unsigned long,struct UnBCL::IComparer<unsigned long> *)`

## pseudocode

```c
__int64 __fastcall UnBCL::ArrayList<unsigned long>::BinarySearch(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned int a4,
        __int64 (__fastcall ***a5)(_QWORD, _QWORD, _QWORD))
{
  int (__fastcall ***v8)(_QWORD); // rcx
  signed int v9; // ebx
  int i; // edi
  unsigned int v11; // esi
  __int64 v12; // rcx
  unsigned int v13; // edx
  int v14; // ecx
  unsigned int v16; // eax
  UnBCL::ArgumentOutOfRangeException *v17; // rax
  UnBCL::Exception *v18; // rbx
  UnBCL::ArgumentException *v19; // rax
  UnBCL::Exception *v20; // rbx
  UnBCL::InvalidOperationException *v21; // rbx
  UnBCL::String *v22; // rax
  const struct UnBCL::String *v23; // rdi
  UnBCL::InvalidOperationException *v24; // rax
  UnBCL::Exception *v25; // rbx
  UnBCL::Exception *v26; // [rsp+20h] [rbp-78h] BYREF
  UnBCL::Exception *v27; // [rsp+28h] [rbp-70h] BYREF
  UnBCL::Exception *v28; // [rsp+30h] [rbp-68h] BYREF
  UnBCL::Exception *pExceptionObject; // [rsp+38h] [rbp-60h] BYREF
  UnBCL::ArgumentException *v30; // [rsp+40h] [rbp-58h]
  UnBCL::ArgumentOutOfRangeException *v31; // [rsp+48h] [rbp-50h]
  struct UnBCL::Exception *v32; // [rsp+50h] [rbp-48h] BYREF

  if ( a3 < 0 )
  {
    v17 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v18 = v17;
    v31 = v17;
    if ( v17 )
    {
      UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
        v17,
        L"negative index or count to ArrayList#BinarySearch");
      *(_QWORD *)v18 = &UnBCL::ArgumentOutOfRangeException::`local vftable';
    }
    else
    {
      v18 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v18,
                         "int __cdecl UnBCL::ArrayList<unsigned long>::BinarySearch(int,int,unsigned long,struct UnBCL::I"
                         "Comparer<unsigned long> *)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v8 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 + 8) + 12LL) + 8LL);
  if ( (**v8)(v8) < a3 )
  {
    v19 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v20 = v19;
    v30 = v19;
    if ( v19 )
    {
      UnBCL::ArgumentException::ArgumentException(
        v19,
        L"index and count do not denote a valid range of elements in ArrayList#BinarySearch");
      *(_QWORD *)v20 = &UnBCL::ArgumentException::`local vftable';
    }
    else
    {
      v20 = 0;
    }
    v26 = AddStackTraceToException<UnBCL::InvalidOperationException>(
            v20,
            "int __cdecl UnBCL::ArrayList<unsigned long>::BinarySearch(int,int,unsigned long,struct UnBCL::IComparer<unsigned long> *)");
    throw (UnBCL::ArgumentException **)&v26;
  }
  v9 = 0;
  for ( i = a3 - 1; v9 <= i; i = v16 )
  {
    v11 = (i + v9) / 2;
    v12 = a1 + *(int *)(*(_QWORD *)(a1 + 8) + 16LL) + 8LL;
    v13 = *(_DWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 24LL))(v12, v11);
    try
    {
      if ( a5 )
        v14 = (**a5)(a5, a4, v13);
      else
        v14 = UnBCL::MP::OperatorCompare<unsigned long>::Compare(a4);
    }
    catch ( UnBCL::Exception *v32 )
    {
      v21 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
      v30 = v21;
      if ( v21 )
      {
        v22 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v23 = v22;
        v31 = v22;
        if ( v22 )
        {
          UnBCL::String::String(v22, L"Compare failed -- bad comparison routines?");
          *(_QWORD *)v23 = &UnBCL::String::`local vftable';
        }
        else
        {
          v23 = 0;
        }
        UnBCL::InvalidOperationException::InvalidOperationException(v21, v23, v32);
        *(_QWORD *)v21 = &UnBCL::InvalidOperationException::`local vftable';
      }
      else
      {
        v21 = 0;
      }
      v27 = AddStackTraceToException<UnBCL::InvalidOperationException>(
              v21,
              "int __cdecl UnBCL::ArrayList<unsigned long>::BinarySearch(int,int,unsigned long,struct UnBCL::IComparer<unsigned long> *)");
      throw (UnBCL::InvalidOperationException **)&v27;
    }
    catch ( ... )
    {
      v24 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
      v25 = v24;
      v31 = v24;
      if ( v24 )
      {
        UnBCL::InvalidOperationException::InvalidOperationException(v24, L"sort failed -- bad comparison routines?");
        *(_QWORD *)v25 = &UnBCL::InvalidOperationException::`local vftable';
      }
      else
      {
        v25 = 0;
      }
      v28 = AddStackTraceToException<UnBCL::InvalidOperationException>(
              v25,
              "int __cdecl UnBCL::ArrayList<unsigned long>::BinarySearch(int,int,unsigned long,struct UnBCL::IComparer<unsigned long> *)");
      throw (UnBCL::InvalidOperationException **)&v28;
    }
    if ( !v14 )
      return v11;
    if ( v14 >= 0 )
      v9 = v11 + 1;
    v16 = v11 - 1;
    if ( v14 >= 0 )
      v16 = i;
  }
  return (unsigned int)~v9;
}

```

## disassembly

```asm
0x1800269f4  push    rbx
0x1800269f6  push    rsi
0x1800269f7  push    rdi
0x1800269f8  push    r12
0x1800269fa  push    r14
0x1800269fc  push    r15
0x1800269fe  sub     rsp, 68h
0x180026a02  mov     r12d, r9d
0x180026a05  mov     edi, r8d
0x180026a08  mov     r15, rcx
0x180026a0b  test    r8d, r8d
0x180026a0e  js      loc_180026AC2
0x180026a14  mov     rax, [rcx+8]
0x180026a18  movsxd  rcx, dword ptr [rax+0Ch]
0x180026a1c  add     rcx, 8
0x180026a20  add     rcx, r15
0x180026a23  mov     rax, [rcx]
0x180026a26  mov     rax, [rax]
0x180026a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a2e  cmp     eax, edi
0x180026a30  jl      loc_180026B1E
0x180026a36  xor     ebx, ebx
0x180026a38  dec     edi
0x180026a3a  mov     r14, [rsp+98h+arg_20]
0x180026a42  cmp     ebx, edi
0x180026a44  jg      short loc_180026ABC
0x180026a46  lea     eax, [rdi+rbx]
0x180026a49  cdq
0x180026a4a  sub     eax, edx
0x180026a4c  sar     eax, 1
0x180026a4e  mov     esi, eax
0x180026a50  mov     rcx, [r15+8]
0x180026a54  movsxd  rcx, dword ptr [rcx+10h]
0x180026a58  add     rcx, 8
0x180026a5c  add     rcx, r15
0x180026a5f  mov     rdx, [rcx]
0x180026a62  mov     rax, [rdx+18h]
0x180026a66  mov     edx, esi
0x180026a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a6d  mov     edx, [rax]
0x180026a6f  test    r14, r14
0x180026a72  jz      short loc_180026A8C
0x180026a74  mov     rax, [r14]
0x180026a77  mov     r8d, edx
0x180026a7a  mov     edx, r12d
0x180026a7d  mov     rcx, r14
0x180026a80  mov     rax, [rax]
0x180026a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a88  mov     ecx, eax
0x180026a8a  jmp     short loc_180026A96
0x180026a8c  mov     ecx, r12d
0x180026a8f  call    ?Compare@?$OperatorCompare@K@MP@UnBCL@@SAHKK@Z; UnBCL::MP::OperatorCompare<ulong>::Compare(ulong,ulong)
0x180026a94  mov     ecx, eax
0x180026a96  test    ecx, ecx
0x180026a98  jnz     short loc_180026AAA
0x180026a9a  mov     eax, esi
0x180026a9c  add     rsp, 68h
0x180026aa0  pop     r15
0x180026aa2  pop     r14
0x180026aa4  pop     r12
0x180026aa6  pop     rdi
0x180026aa7  pop     rsi
0x180026aa8  pop     rbx
0x180026aa9  retn
0x180026aaa  lea     eax, [rsi+1]
0x180026aad  test    ecx, ecx
0x180026aaf  cmovns  ebx, eax
0x180026ab2  lea     eax, [rsi-1]
0x180026ab5  cmovns  eax, edi
0x180026ab8  mov     edi, eax
0x180026aba  jmp     short loc_180026A42
0x180026abc  not     ebx
0x180026abe  mov     eax, ebx
0x180026ac0  jmp     short loc_180026A9C
0x180026ac2  mov     ecx, 38h ; '8'
0x180026ac7  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180026acd  mov     rbx, rax
0x180026ad0  mov     [rsp+98h+var_50], rax
0x180026ad5  test    rax, rax
0x180026ad8  jz      short loc_180026AF6
0x180026ada  lea     rdx, aNegativeIndexO; "negative index or count to ArrayList#Bi"...
0x180026ae1  mov     rcx, rax
0x180026ae4  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180026aea  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x180026af1  mov     [rbx], rax
0x180026af4  jmp     short loc_180026AF8
0x180026af6  xor     ebx, ebx
0x180026af8  lea     rdx, aIntCdeclUnbclA_16; "int __cdecl UnBCL::ArrayList<unsigned l"...
0x180026aff  mov     rcx, rbx
0x180026b02  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180026b07  mov     [rsp+98h+pExceptionObject], rax
0x180026b0c  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180026b13  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180026b18  call    _CxxThrowException_0
0x180026b1e  mov     ecx, 38h ; '8'
0x180026b23  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180026b29  mov     rbx, rax
0x180026b2c  mov     [rsp+98h+var_58], rax
0x180026b31  test    rax, rax
0x180026b34  jz      short loc_180026B52
0x180026b36  lea     rdx, aIndexAndCountD; "index and count do not denote a valid r"...
0x180026b3d  mov     rcx, rax
0x180026b40  call    cs:__imp_??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180026b46  lea     rax, ??_SArgumentException@UnBCL@@6B@; const UnBCL::ArgumentException::`local vftable'
0x180026b4d  mov     [rbx], rax
0x180026b50  jmp     short loc_180026B54
0x180026b52  xor     ebx, ebx
0x180026b54  lea     rdx, aIntCdeclUnbclA_16; "int __cdecl UnBCL::ArrayList<unsigned l"...
0x180026b5b  mov     rcx, rbx
0x180026b5e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180026b63  mov     [rsp+98h+var_78], rax
0x180026b68  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180026b6f  lea     rcx, [rsp+98h+var_78]; pExceptionObject
0x180026b74  call    _CxxThrowException_0
```
