# UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>::BinarySearch(int,int,UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *,UnBCL::IComparer<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *> *)

- ea: `0x18000830c`
- end: `0x180008493`
- name: `?BinarySearch@?$ArrayList@PEAV?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@@UnBCL@@AEAAHHHPEAV?$DictionaryEntry@PEAVString@UnBCL@@_K@2@PEAU?$IComparer@PEAV?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@@2@@Z`
- size: `391`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64 (__fastcall ***)(_QWORD, __int64, _QWORD))`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800084a0`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x18000830c`
- `0x180009d24`
- `0x180053010`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800083e0`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000843c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800083e0`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000843c`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x180008459`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x180008459`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x1800083fd`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x1800083fd`

## string_xrefs

- `0x180008411`: `int __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *>::BinarySearch(int,int,class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *,struct UnBCL::IComparer<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *> *)`
- `0x18000846d`: `int __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *>::BinarySearch(int,int,class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *,struct UnBCL::IComparer<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *> *)`

## pseudocode

```c
__int64 __fastcall UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>::BinarySearch(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 (__fastcall ***a5)(_QWORD, __int64, _QWORD))
{
  int (__fastcall ***v8)(_QWORD); // rcx
  signed int v9; // ebx
  int i; // edi
  unsigned int v11; // esi
  __int64 v12; // rcx
  _QWORD *v13; // rax
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
                         "int __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int6"
                         "4> *>::BinarySearch(int,int,class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64"
                         "> *,struct UnBCL::IComparer<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *> *)");
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
            "int __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *>::Binary"
            "Search(int,int,class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *,struct UnBCL::ICompare"
            "r<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *> *)");
    throw (UnBCL::ArgumentException **)&v26;
  }
  v9 = 0;
  for ( i = a3 - 1; v9 <= i; i = v16 )
  {
    v11 = (i + v9) / 2;
    v12 = a1 + *(int *)(*(_QWORD *)(a1 + 8) + 16LL) + 8LL;
    v13 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 24LL))(v12, v11);
    try
    {
      if ( a5 )
        v14 = (**a5)(a5, a4, *v13);
      else
        v14 = UnBCL::MP::ObjectPtrCompare<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>::Compare(a4);
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
              "int __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *>::Bina"
              "rySearch(int,int,class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *,struct UnBCL::ICom"
              "parer<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *> *)");
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
              "int __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *>::Bina"
              "rySearch(int,int,class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *,struct UnBCL::ICom"
              "parer<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *> *)");
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
0x18000830c  push    rbx
0x18000830e  push    rsi
0x18000830f  push    rdi
0x180008310  push    r12
0x180008312  push    r14
0x180008314  push    r15
0x180008316  sub     rsp, 68h
0x18000831a  mov     r12, r9
0x18000831d  mov     edi, r8d
0x180008320  mov     r15, rcx
0x180008323  test    r8d, r8d
0x180008326  js      loc_1800083DB
0x18000832c  mov     rax, [rcx+8]
0x180008330  movsxd  rcx, dword ptr [rax+0Ch]
0x180008334  add     rcx, 8
0x180008338  add     rcx, r15
0x18000833b  mov     rax, [rcx]
0x18000833e  mov     rax, [rax]
0x180008341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008346  cmp     eax, edi
0x180008348  jl      loc_180008437
0x18000834e  xor     ebx, ebx
0x180008350  dec     edi
0x180008352  mov     r14, [rsp+98h+arg_20]
0x18000835a  cmp     ebx, edi
0x18000835c  jg      short loc_1800083D5
0x18000835e  lea     eax, [rdi+rbx]
0x180008361  cdq
0x180008362  sub     eax, edx
0x180008364  sar     eax, 1
0x180008366  mov     esi, eax
0x180008368  mov     rcx, [r15+8]
0x18000836c  movsxd  rcx, dword ptr [rcx+10h]
0x180008370  add     rcx, 8
0x180008374  add     rcx, r15
0x180008377  mov     rdx, [rcx]
0x18000837a  mov     rax, [rdx+18h]
0x18000837e  mov     edx, esi
0x180008380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008385  mov     rdx, [rax]
0x180008388  test    r14, r14
0x18000838b  jz      short loc_1800083A5
0x18000838d  mov     rax, [r14]
0x180008390  mov     r8, rdx
0x180008393  mov     rdx, r12
0x180008396  mov     rcx, r14
0x180008399  mov     rax, [rax]
0x18000839c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083a1  mov     ecx, eax
0x1800083a3  jmp     short loc_1800083AF
0x1800083a5  mov     rcx, r12
0x1800083a8  call    ?Compare@?$ObjectPtrCompare@PEAV?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@@MP@UnBCL@@SAHPEAV?$DictionaryEntry@PEAVString@UnBCL@@_K@3@0@Z; UnBCL::MP::ObjectPtrCompare<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>::Compare(UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *,UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *)
0x1800083ad  mov     ecx, eax
0x1800083af  test    ecx, ecx
0x1800083b1  jnz     short loc_1800083C3
0x1800083b3  mov     eax, esi
0x1800083b5  add     rsp, 68h
0x1800083b9  pop     r15
0x1800083bb  pop     r14
0x1800083bd  pop     r12
0x1800083bf  pop     rdi
0x1800083c0  pop     rsi
0x1800083c1  pop     rbx
0x1800083c2  retn
0x1800083c3  lea     eax, [rsi+1]
0x1800083c6  test    ecx, ecx
0x1800083c8  cmovns  ebx, eax
0x1800083cb  lea     eax, [rsi-1]
0x1800083ce  cmovns  eax, edi
0x1800083d1  mov     edi, eax
0x1800083d3  jmp     short loc_18000835A
0x1800083d5  not     ebx
0x1800083d7  mov     eax, ebx
0x1800083d9  jmp     short loc_1800083B5
0x1800083db  mov     ecx, 38h ; '8'
0x1800083e0  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800083e6  mov     rbx, rax
0x1800083e9  mov     [rsp+98h+var_50], rax
0x1800083ee  test    rax, rax
0x1800083f1  jz      short loc_18000840F
0x1800083f3  lea     rdx, aNegativeIndexO; "negative index or count to ArrayList#Bi"...
0x1800083fa  mov     rcx, rax
0x1800083fd  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180008403  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x18000840a  mov     [rbx], rax
0x18000840d  jmp     short loc_180008411
0x18000840f  xor     ebx, ebx
0x180008411  lea     rdx, aIntCdeclUnbclA_17; "int __cdecl UnBCL::ArrayList<class UnBC"...
0x180008418  mov     rcx, rbx
0x18000841b  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180008420  mov     [rsp+98h+pExceptionObject], rax
0x180008425  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18000842c  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180008431  call    _CxxThrowException_0
0x180008437  mov     ecx, 38h ; '8'
0x18000843c  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180008442  mov     rbx, rax
0x180008445  mov     [rsp+98h+var_58], rax
0x18000844a  test    rax, rax
0x18000844d  jz      short loc_18000846B
0x18000844f  lea     rdx, aIndexAndCountD; "index and count do not denote a valid r"...
0x180008456  mov     rcx, rax
0x180008459  call    cs:__imp_??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18000845f  lea     rax, ??_SArgumentException@UnBCL@@6B@; const UnBCL::ArgumentException::`local vftable'
0x180008466  mov     [rbx], rax
0x180008469  jmp     short loc_18000846D
0x18000846b  xor     ebx, ebx
0x18000846d  lea     rdx, aIntCdeclUnbclA_17; "int __cdecl UnBCL::ArrayList<class UnBC"...
0x180008474  mov     rcx, rbx
0x180008477  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18000847c  mov     [rsp+98h+var_78], rax
0x180008481  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180008488  lea     rcx, [rsp+98h+var_78]; pExceptionObject
0x18000848d  call    _CxxThrowException_0
```
