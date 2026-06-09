# UnBCL::ArrayList<CFileObject *>::BinarySearch(int,int,CFileObject *,UnBCL::IComparer<CFileObject *> *)

- ea: `0x180026c00`
- end: `0x180026d87`
- name: `?BinarySearch@?$ArrayList@PEAVCFileObject@@@UnBCL@@AEAAHHHPEAVCFileObject@@PEAU?$IComparer@PEAVCFileObject@@@2@@Z`
- size: `391`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64 (__fastcall ***)(_QWORD, __int64, _QWORD))`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180026d90`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180026c00`
- `0x18002722c`
- `0x180053010`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180026cd4`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180026d30`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180026cd4`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180026d30`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x180026d4d`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x180026d4d`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180026cf1`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180026cf1`

## string_xrefs

- `0x180026d05`: `int __cdecl UnBCL::ArrayList<class CFileObject *>::BinarySearch(int,int,class CFileObject *,struct UnBCL::IComparer<class CFileObject *> *)`
- `0x180026d61`: `int __cdecl UnBCL::ArrayList<class CFileObject *>::BinarySearch(int,int,class CFileObject *,struct UnBCL::IComparer<class CFileObject *> *)`

## pseudocode

```c
__int64 __fastcall UnBCL::ArrayList<CFileObject *>::BinarySearch(
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
                         "int __cdecl UnBCL::ArrayList<class CFileObject *>::BinarySearch(int,int,class CFileObject *,str"
                         "uct UnBCL::IComparer<class CFileObject *> *)");
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
            "int __cdecl UnBCL::ArrayList<class CFileObject *>::BinarySearch(int,int,class CFileObject *,struct UnBCL::IC"
            "omparer<class CFileObject *> *)");
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
        v14 = UnBCL::MP::ObjectPtrCompare<CFileObject *>::Compare(a4);
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
              "int __cdecl UnBCL::ArrayList<class CFileObject *>::BinarySearch(int,int,class CFileObject *,struct UnBCL::"
              "IComparer<class CFileObject *> *)");
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
              "int __cdecl UnBCL::ArrayList<class CFileObject *>::BinarySearch(int,int,class CFileObject *,struct UnBCL::"
              "IComparer<class CFileObject *> *)");
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
0x180026c00  push    rbx
0x180026c02  push    rsi
0x180026c03  push    rdi
0x180026c04  push    r12
0x180026c06  push    r14
0x180026c08  push    r15
0x180026c0a  sub     rsp, 68h
0x180026c0e  mov     r12, r9
0x180026c11  mov     edi, r8d
0x180026c14  mov     r15, rcx
0x180026c17  test    r8d, r8d
0x180026c1a  js      loc_180026CCF
0x180026c20  mov     rax, [rcx+8]
0x180026c24  movsxd  rcx, dword ptr [rax+0Ch]
0x180026c28  add     rcx, 8
0x180026c2c  add     rcx, r15
0x180026c2f  mov     rax, [rcx]
0x180026c32  mov     rax, [rax]
0x180026c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c3a  cmp     eax, edi
0x180026c3c  jl      loc_180026D2B
0x180026c42  xor     ebx, ebx
0x180026c44  dec     edi
0x180026c46  mov     r14, [rsp+98h+arg_20]
0x180026c4e  cmp     ebx, edi
0x180026c50  jg      short loc_180026CC9
0x180026c52  lea     eax, [rdi+rbx]
0x180026c55  cdq
0x180026c56  sub     eax, edx
0x180026c58  sar     eax, 1
0x180026c5a  mov     esi, eax
0x180026c5c  mov     rcx, [r15+8]
0x180026c60  movsxd  rcx, dword ptr [rcx+10h]
0x180026c64  add     rcx, 8
0x180026c68  add     rcx, r15
0x180026c6b  mov     rdx, [rcx]
0x180026c6e  mov     rax, [rdx+18h]
0x180026c72  mov     edx, esi
0x180026c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c79  mov     rdx, [rax]
0x180026c7c  test    r14, r14
0x180026c7f  jz      short loc_180026C99
0x180026c81  mov     rax, [r14]
0x180026c84  mov     r8, rdx
0x180026c87  mov     rdx, r12
0x180026c8a  mov     rcx, r14
0x180026c8d  mov     rax, [rax]
0x180026c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c95  mov     ecx, eax
0x180026c97  jmp     short loc_180026CA3
0x180026c99  mov     rcx, r12
0x180026c9c  call    ?Compare@?$ObjectPtrCompare@PEAVCFileObject@@@MP@UnBCL@@SAHPEAVCFileObject@@0@Z; UnBCL::MP::ObjectPtrCompare<CFileObject *>::Compare(CFileObject *,CFileObject *)
0x180026ca1  mov     ecx, eax
0x180026ca3  test    ecx, ecx
0x180026ca5  jnz     short loc_180026CB7
0x180026ca7  mov     eax, esi
0x180026ca9  add     rsp, 68h
0x180026cad  pop     r15
0x180026caf  pop     r14
0x180026cb1  pop     r12
0x180026cb3  pop     rdi
0x180026cb4  pop     rsi
0x180026cb5  pop     rbx
0x180026cb6  retn
0x180026cb7  lea     eax, [rsi+1]
0x180026cba  test    ecx, ecx
0x180026cbc  cmovns  ebx, eax
0x180026cbf  lea     eax, [rsi-1]
0x180026cc2  cmovns  eax, edi
0x180026cc5  mov     edi, eax
0x180026cc7  jmp     short loc_180026C4E
0x180026cc9  not     ebx
0x180026ccb  mov     eax, ebx
0x180026ccd  jmp     short loc_180026CA9
0x180026ccf  mov     ecx, 38h ; '8'
0x180026cd4  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180026cda  mov     rbx, rax
0x180026cdd  mov     [rsp+98h+var_50], rax
0x180026ce2  test    rax, rax
0x180026ce5  jz      short loc_180026D03
0x180026ce7  lea     rdx, aNegativeIndexO; "negative index or count to ArrayList#Bi"...
0x180026cee  mov     rcx, rax
0x180026cf1  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180026cf7  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x180026cfe  mov     [rbx], rax
0x180026d01  jmp     short loc_180026D05
0x180026d03  xor     ebx, ebx
0x180026d05  lea     rdx, aIntCdeclUnbclA_4; "int __cdecl UnBCL::ArrayList<class CFil"...
0x180026d0c  mov     rcx, rbx
0x180026d0f  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180026d14  mov     [rsp+98h+pExceptionObject], rax
0x180026d19  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180026d20  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180026d25  call    _CxxThrowException_0
0x180026d2b  mov     ecx, 38h ; '8'
0x180026d30  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180026d36  mov     rbx, rax
0x180026d39  mov     [rsp+98h+var_58], rax
0x180026d3e  test    rax, rax
0x180026d41  jz      short loc_180026D5F
0x180026d43  lea     rdx, aIndexAndCountD; "index and count do not denote a valid r"...
0x180026d4a  mov     rcx, rax
0x180026d4d  call    cs:__imp_??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180026d53  lea     rax, ??_SArgumentException@UnBCL@@6B@; const UnBCL::ArgumentException::`local vftable'
0x180026d5a  mov     [rbx], rax
0x180026d5d  jmp     short loc_180026D61
0x180026d5f  xor     ebx, ebx
0x180026d61  lea     rdx, aIntCdeclUnbclA_4; "int __cdecl UnBCL::ArrayList<class CFil"...
0x180026d68  mov     rcx, rbx
0x180026d6b  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180026d70  mov     [rsp+98h+var_78], rax
0x180026d75  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180026d7c  lea     rcx, [rsp+98h+var_78]; pExceptionObject
0x180026d81  call    _CxxThrowException_0
```
