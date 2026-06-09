# UnBCL::ArrayList<CPITRSnapshot *>::BinarySearch(int,int,CPITRSnapshot *,UnBCL::IComparer<CPITRSnapshot *> *)

- ea: `0x180008520`
- end: `0x1800086dc`
- name: `?BinarySearch@?$ArrayList@PEAVCPITRSnapshot@@@UnBCL@@AEAAHHHPEAVCPITRSnapshot@@PEAU?$IComparer@PEAVCPITRSnapshot@@@2@@Z`
- size: `444`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64 (__fastcall ***)(_QWORD, __int64, _QWORD))`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800086f0`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180008520`
- `0x180053010`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180008629`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180008685`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180008629`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180008685`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x1800086a2`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x1800086a2`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180008646`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180008646`

## string_xrefs

- `0x18000865a`: `int __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::BinarySearch(int,int,class CPITRSnapshot *,struct UnBCL::IComparer<class CPITRSnapshot *> *)`
- `0x1800086b6`: `int __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::BinarySearch(int,int,class CPITRSnapshot *,struct UnBCL::IComparer<class CPITRSnapshot *> *)`

## pseudocode

```c
__int64 __fastcall UnBCL::ArrayList<CPITRSnapshot *>::BinarySearch(
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
  __int64 v14; // rdx
  int v15; // ecx
  unsigned int v17; // eax
  UnBCL::ArgumentOutOfRangeException *v18; // rax
  UnBCL::Exception *v19; // rbx
  UnBCL::ArgumentException *v20; // rax
  UnBCL::Exception *v21; // rbx
  UnBCL::InvalidOperationException *v22; // rbx
  UnBCL::String *v23; // rax
  const struct UnBCL::String *v24; // rdi
  UnBCL::InvalidOperationException *v25; // rax
  UnBCL::Exception *v26; // rbx
  UnBCL::Exception *v27; // [rsp+20h] [rbp-78h] BYREF
  UnBCL::Exception *v28; // [rsp+28h] [rbp-70h] BYREF
  UnBCL::Exception *v29; // [rsp+30h] [rbp-68h] BYREF
  UnBCL::Exception *pExceptionObject; // [rsp+38h] [rbp-60h] BYREF
  UnBCL::ArgumentException *v31; // [rsp+40h] [rbp-58h]
  UnBCL::ArgumentOutOfRangeException *v32; // [rsp+48h] [rbp-50h]
  struct UnBCL::Exception *v33; // [rsp+50h] [rbp-48h] BYREF

  if ( a3 < 0 )
  {
    v18 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v19 = v18;
    v32 = v18;
    if ( v18 )
    {
      UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
        v18,
        L"negative index or count to ArrayList#BinarySearch");
      *(_QWORD *)v19 = &UnBCL::ArgumentOutOfRangeException::`local vftable';
    }
    else
    {
      v19 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v19,
                         "int __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::BinarySearch(int,int,class CPITRSnapshot *"
                         ",struct UnBCL::IComparer<class CPITRSnapshot *> *)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v8 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 + 8) + 12LL) + 8LL);
  if ( (**v8)(v8) < a3 )
  {
    v20 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v21 = v20;
    v31 = v20;
    if ( v20 )
    {
      UnBCL::ArgumentException::ArgumentException(
        v20,
        L"index and count do not denote a valid range of elements in ArrayList#BinarySearch");
      *(_QWORD *)v21 = &UnBCL::ArgumentException::`local vftable';
    }
    else
    {
      v21 = 0;
    }
    v27 = AddStackTraceToException<UnBCL::InvalidOperationException>(
            v21,
            "int __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::BinarySearch(int,int,class CPITRSnapshot *,struct UnBCL"
            "::IComparer<class CPITRSnapshot *> *)");
    throw (UnBCL::ArgumentException **)&v27;
  }
  v9 = 0;
  for ( i = a3 - 1; v9 <= i; i = v17 )
  {
    v11 = (i + v9) / 2;
    v12 = a1 + *(int *)(*(_QWORD *)(a1 + 8) + 16LL) + 8LL;
    v13 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 24LL))(v12, v11);
    v14 = *v13;
    try
    {
      if ( a5 )
      {
        v15 = (**a5)(a5, a4, *v13);
        goto LABEL_43;
      }
      if ( a4 )
      {
        if ( !v14 )
        {
          v15 = 1;
          goto LABEL_43;
        }
      }
      else if ( v14 )
      {
        v15 = -1;
        goto LABEL_43;
      }
      v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(a4 + 8) + 48LL))(
              a4 + 8,
              (v14 + 8) & -(__int64)(v14 != 0));
    }
    catch ( UnBCL::Exception *v33 )
    {
      v22 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
      v31 = v22;
      if ( v22 )
      {
        v23 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v24 = v23;
        v32 = v23;
        if ( v23 )
        {
          UnBCL::String::String(v23, L"Compare failed -- bad comparison routines?");
          *(_QWORD *)v24 = &UnBCL::String::`local vftable';
        }
        else
        {
          v24 = 0;
        }
        UnBCL::InvalidOperationException::InvalidOperationException(v22, v24, v33);
        *(_QWORD *)v22 = &UnBCL::InvalidOperationException::`local vftable';
      }
      else
      {
        v22 = 0;
      }
      v28 = AddStackTraceToException<UnBCL::InvalidOperationException>(
              v22,
              "int __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::BinarySearch(int,int,class CPITRSnapshot *,struct UnB"
              "CL::IComparer<class CPITRSnapshot *> *)");
      throw (UnBCL::InvalidOperationException **)&v28;
    }
    catch ( ... )
    {
      v25 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
      v26 = v25;
      v32 = v25;
      if ( v25 )
      {
        UnBCL::InvalidOperationException::InvalidOperationException(v25, L"sort failed -- bad comparison routines?");
        *(_QWORD *)v26 = &UnBCL::InvalidOperationException::`local vftable';
      }
      else
      {
        v26 = 0;
      }
      v29 = AddStackTraceToException<UnBCL::InvalidOperationException>(
              v26,
              "int __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::BinarySearch(int,int,class CPITRSnapshot *,struct UnB"
              "CL::IComparer<class CPITRSnapshot *> *)");
      throw (UnBCL::InvalidOperationException **)&v29;
    }
LABEL_43:
    if ( !v15 )
      return v11;
    if ( v15 >= 0 )
      v9 = v11 + 1;
    v17 = v11 - 1;
    if ( v15 >= 0 )
      v17 = i;
  }
  return (unsigned int)~v9;
}

```

## disassembly

```asm
0x180008520  push    rbx
0x180008522  push    rsi
0x180008523  push    rdi
0x180008524  push    r13
0x180008526  push    r14
0x180008528  push    r15
0x18000852a  sub     rsp, 68h
0x18000852e  mov     r15, r9
0x180008531  mov     edi, r8d
0x180008534  mov     r13, rcx
0x180008537  test    r8d, r8d
0x18000853a  js      loc_180008624
0x180008540  mov     rax, [rcx+8]
0x180008544  movsxd  rcx, dword ptr [rax+0Ch]
0x180008548  add     rcx, 8
0x18000854c  add     rcx, r13
0x18000854f  mov     rax, [rcx]
0x180008552  mov     rax, [rax]
0x180008555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000855a  cmp     eax, edi
0x18000855c  jl      loc_180008680
0x180008562  xor     ebx, ebx
0x180008564  dec     edi
0x180008566  mov     r14, [rsp+98h+arg_20]
0x18000856e  cmp     ebx, edi
0x180008570  jg      loc_18000861E
0x180008576  lea     eax, [rdi+rbx]
0x180008579  cdq
0x18000857a  sub     eax, edx
0x18000857c  sar     eax, 1
0x18000857e  mov     esi, eax
0x180008580  mov     rcx, [r13+8]
0x180008584  movsxd  rcx, dword ptr [rcx+10h]
0x180008588  add     rcx, 8
0x18000858c  add     rcx, r13
0x18000858f  mov     rdx, [rcx]
0x180008592  mov     rax, [rdx+18h]
0x180008596  mov     edx, esi
0x180008598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000859d  mov     rdx, [rax]
0x1800085a0  test    r14, r14
0x1800085a3  jz      short loc_1800085BD
0x1800085a5  mov     rax, [r14]
0x1800085a8  mov     r8, rdx
0x1800085ab  mov     rdx, r15
0x1800085ae  mov     rcx, r14
0x1800085b1  mov     rax, [rax]
0x1800085b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085b9  mov     ecx, eax
0x1800085bb  jmp     short loc_1800085F5
0x1800085bd  test    r15, r15
0x1800085c0  jnz     short loc_1800085CC
0x1800085c2  test    rdx, rdx
0x1800085c5  jz      short loc_1800085D6
0x1800085c7  or      ecx, 0FFFFFFFFh
0x1800085ca  jmp     short loc_1800085F5
0x1800085cc  test    rdx, rdx
0x1800085cf  jnz     short loc_1800085D6
0x1800085d1  lea     ecx, [rdx+1]
0x1800085d4  jmp     short loc_1800085F5
0x1800085d6  lea     rcx, [r15+8]
0x1800085da  mov     r8, [rcx]
0x1800085dd  lea     rax, [rdx+8]
0x1800085e1  neg     rdx
0x1800085e4  sbb     rdx, rdx
0x1800085e7  and     rdx, rax
0x1800085ea  mov     rax, [r8+30h]
0x1800085ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085f3  mov     ecx, eax
0x1800085f5  test    ecx, ecx
0x1800085f7  jnz     short loc_180008609
0x1800085f9  mov     eax, esi
0x1800085fb  add     rsp, 68h
0x1800085ff  pop     r15
0x180008601  pop     r14
0x180008603  pop     r13
0x180008605  pop     rdi
0x180008606  pop     rsi
0x180008607  pop     rbx
0x180008608  retn
0x180008609  lea     eax, [rsi+1]
0x18000860c  test    ecx, ecx
0x18000860e  cmovns  ebx, eax
0x180008611  lea     eax, [rsi-1]
0x180008614  cmovns  eax, edi
0x180008617  mov     edi, eax
0x180008619  jmp     loc_18000856E
0x18000861e  not     ebx
0x180008620  mov     eax, ebx
0x180008622  jmp     short loc_1800085FB
0x180008624  mov     ecx, 38h ; '8'
0x180008629  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000862f  mov     rbx, rax
0x180008632  mov     [rsp+98h+var_50], rax
0x180008637  test    rax, rax
0x18000863a  jz      short loc_180008658
0x18000863c  lea     rdx, aNegativeIndexO; "negative index or count to ArrayList#Bi"...
0x180008643  mov     rcx, rax
0x180008646  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18000864c  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x180008653  mov     [rbx], rax
0x180008656  jmp     short loc_18000865A
0x180008658  xor     ebx, ebx
0x18000865a  lea     rdx, aIntCdeclUnbclA_2; "int __cdecl UnBCL::ArrayList<class CPIT"...
0x180008661  mov     rcx, rbx
0x180008664  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180008669  mov     [rsp+98h+pExceptionObject], rax
0x18000866e  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180008675  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18000867a  call    _CxxThrowException_0
0x180008680  mov     ecx, 38h ; '8'
0x180008685  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000868b  mov     rbx, rax
0x18000868e  mov     [rsp+98h+var_58], rax
0x180008693  test    rax, rax
0x180008696  jz      short loc_1800086B4
0x180008698  lea     rdx, aIndexAndCountD; "index and count do not denote a valid r"...
0x18000869f  mov     rcx, rax
0x1800086a2  call    cs:__imp_??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x1800086a8  lea     rax, ??_SArgumentException@UnBCL@@6B@; const UnBCL::ArgumentException::`local vftable'
0x1800086af  mov     [rbx], rax
0x1800086b2  jmp     short loc_1800086B6
0x1800086b4  xor     ebx, ebx
0x1800086b6  lea     rdx, aIntCdeclUnbclA_2; "int __cdecl UnBCL::ArrayList<class CPIT"...
0x1800086bd  mov     rcx, rbx
0x1800086c0  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800086c5  mov     [rsp+98h+var_78], rax
0x1800086ca  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x1800086d1  lea     rcx, [rsp+98h+var_78]; pExceptionObject
0x1800086d6  call    _CxxThrowException_0
```
