# UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>::CopyTo(UnBCL::Array<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *> *,int)

- ea: `0x180009f34`
- end: `0x18000a163`
- name: `?CopyTo@?$ArrayList@PEAV?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@@UnBCL@@UEBAXPEAV?$Array@PEAV?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@@2@H@Z`
- size: `559`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009f20`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180009f34`
- `0x180053010`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000a054`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000a0b0`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000a10c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000a054`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000a0b0`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000a10c`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18000a0cd`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18000a0cd`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x18000a129`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x18000a129`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18000a071`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18000a071`

## string_xrefs

- `0x18000a0c3`: `null array argument to ArrayList#CopyTo`
- `0x18000a067`: `index out of range to ArrayList#CopyTo`
- `0x18000a085`: `void __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *>::CopyTo(class UnBCL::Array<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *> *,int) const`
- `0x18000a0e1`: `void __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *>::CopyTo(class UnBCL::Array<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *> *,int) const`
- `0x18000a13d`: `void __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *>::CopyTo(class UnBCL::Array<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *> *,int) const`

## pseudocode

```c
__int64 __fastcall UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>::CopyTo(
        __int64 a1,
        __int64 a2,
        int a3)
{
  int (__fastcall ***v6)(_QWORD); // rcx
  signed int v7; // ebx
  __int64 (__fastcall ***v8)(_QWORD); // rcx
  __int64 (__fastcall ***v9)(_QWORD); // rcx
  __int64 result; // rax
  __int64 v11; // r15
  __int64 v12; // r14
  int i; // ebx
  __int64 (__fastcall ***v14)(_QWORD); // rcx
  UnBCL::ArgumentOutOfRangeException *v15; // rax
  UnBCL::Exception *v16; // rbx
  UnBCL::ArgumentNullException *v17; // rax
  UnBCL::Exception *v18; // rbx
  UnBCL::ArgumentException *v19; // rax
  UnBCL::Exception *v20; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+48h] [rbp+10h] BYREF
  UnBCL::ArgumentNullException *v22; // [rsp+58h] [rbp+20h]

  if ( !a2 )
  {
    v17 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v18 = v17;
    v22 = v17;
    if ( v17 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v17, L"null array argument to ArrayList#CopyTo");
      *(_QWORD *)v18 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v18 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v18,
                         "void __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int"
                         "64> *>::CopyTo(class UnBCL::Array<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned _"
                         "_int64> *> *,int) const");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( a3 < 0
    || (v6 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 80) + 12LL) - 80LL),
        0x7FFFFFFF - a3 < (**v6)(v6)) )
  {
    v15 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v16 = v15;
    v22 = v15;
    if ( v15 )
    {
      UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(v15, L"index out of range to ArrayList#CopyTo");
      *(_QWORD *)v16 = &UnBCL::ArgumentOutOfRangeException::`local vftable';
    }
    else
    {
      v16 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v16,
                         "void __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int"
                         "64> *>::CopyTo(class UnBCL::Array<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned _"
                         "_int64> *> *,int) const");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v7 = (**(__int64 (__fastcall ***)(__int64))a2)(a2);
  v8 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 80) + 12LL) - 80LL);
  if ( (int)(a3 + (**v8)(v8)) > v7 )
  {
    v19 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v20 = v19;
    v22 = v19;
    if ( v19 )
    {
      UnBCL::ArgumentException::ArgumentException(v19, L"insufficient space available in target array");
      *(_QWORD *)v20 = &UnBCL::ArgumentException::`local vftable';
    }
    else
    {
      v20 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v20,
                         "void __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int"
                         "64> *>::CopyTo(class UnBCL::Array<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned _"
                         "_int64> *> *,int) const");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  v9 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 80) + 12LL) - 80LL);
  result = (**v9)(v9);
  if ( (_DWORD)result )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 - 88) + 104LL))(a1 - 88, 0);
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a2 + 56LL))(a2, 0);
    for ( i = 0; ; ++i )
    {
      v14 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 80) + 12LL) - 80LL);
      result = (**v14)(v14);
      if ( i >= (int)result )
        break;
      *(_QWORD *)(v12 + 8LL * (i + a3)) = *(_QWORD *)(v11 + 8LL * i);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009f34  mov     [rsp+arg_0], rbx
0x180009f39  mov     [rsp+arg_10], rsi
0x180009f3e  push    rdi
0x180009f3f  push    r14
0x180009f41  push    r15
0x180009f43  sub     rsp, 20h
0x180009f47  mov     esi, r8d
0x180009f4a  mov     r14, rdx
0x180009f4d  mov     rdi, rcx
0x180009f50  test    rdx, rdx
0x180009f53  jz      loc_18000A0AB
0x180009f59  test    r8d, r8d
0x180009f5c  js      loc_18000A04F
0x180009f62  mov     rax, [rcx-50h]
0x180009f66  movsxd  rcx, dword ptr [rax+0Ch]
0x180009f6a  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180009f6e  add     rcx, rdi
0x180009f71  mov     rax, [rcx]
0x180009f74  mov     rax, [rax]
0x180009f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f7c  mov     ecx, 7FFFFFFFh
0x180009f81  sub     ecx, esi
0x180009f83  cmp     ecx, eax
0x180009f85  jl      loc_18000A04F
0x180009f8b  mov     rax, [r14]
0x180009f8e  mov     rcx, r14
0x180009f91  mov     rax, [rax]
0x180009f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f99  mov     ebx, eax
0x180009f9b  mov     rcx, [rdi-50h]
0x180009f9f  movsxd  rcx, dword ptr [rcx+0Ch]
0x180009fa3  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180009fa7  add     rcx, rdi
0x180009faa  mov     rdx, [rcx]
0x180009fad  mov     rax, [rdx]
0x180009fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fb5  add     eax, esi
0x180009fb7  cmp     eax, ebx
0x180009fb9  jg      loc_18000A107
0x180009fbf  mov     rax, [rdi-50h]
0x180009fc3  movsxd  rcx, dword ptr [rax+0Ch]
0x180009fc7  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180009fcb  add     rcx, rdi
0x180009fce  mov     rax, [rcx]
0x180009fd1  mov     rax, [rax]
0x180009fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fd9  test    eax, eax
0x180009fdb  jz      short loc_18000A03B
0x180009fdd  lea     rcx, [rdi-58h]
0x180009fe1  mov     rax, [rcx]
0x180009fe4  xor     edx, edx
0x180009fe6  mov     rax, [rax+68h]
0x180009fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fef  mov     r15, rax
0x180009ff2  mov     rcx, [r14]
0x180009ff5  mov     rax, [rcx+38h]
0x180009ff9  xor     edx, edx
0x180009ffb  mov     rcx, r14
0x180009ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a003  mov     r14, rax
0x18000a006  xor     ebx, ebx
0x18000a008  mov     rcx, [rdi-50h]
0x18000a00c  movsxd  rcx, dword ptr [rcx+0Ch]
0x18000a010  add     rcx, 0FFFFFFFFFFFFFFB0h
0x18000a014  add     rcx, rdi
0x18000a017  mov     rdx, [rcx]
0x18000a01a  mov     rax, [rdx]
0x18000a01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a022  cmp     ebx, eax
0x18000a024  jge     short loc_18000A03B
0x18000a026  movsxd  rdx, ebx
0x18000a029  lea     eax, [rbx+rsi]
0x18000a02c  movsxd  rcx, eax
0x18000a02f  mov     rax, [r15+rdx*8]
0x18000a033  mov     [r14+rcx*8], rax
0x18000a037  inc     ebx
0x18000a039  jmp     short loc_18000A008
0x18000a03b  mov     rbx, [rsp+38h+arg_0]
0x18000a040  mov     rsi, [rsp+38h+arg_10]
0x18000a045  add     rsp, 20h
0x18000a049  pop     r15
0x18000a04b  pop     r14
0x18000a04d  pop     rdi
0x18000a04e  retn
0x18000a04f  mov     ecx, 38h ; '8'
0x18000a054  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000a05a  mov     rbx, rax
0x18000a05d  mov     [rsp+38h+arg_18], rax
0x18000a062  test    rax, rax
0x18000a065  jz      short loc_18000A083
0x18000a067  lea     rdx, aIndexOutOfRang; "index out of range to ArrayList#CopyTo"
0x18000a06e  mov     rcx, rax
0x18000a071  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18000a077  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x18000a07e  mov     [rbx], rax
0x18000a081  jmp     short loc_18000A085
0x18000a083  xor     ebx, ebx
0x18000a085  lea     rdx, aVoidCdeclUnbcl_31; "void __cdecl UnBCL::ArrayList<class UnB"...
0x18000a08c  mov     rcx, rbx
0x18000a08f  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18000a094  mov     [rsp+38h+pExceptionObject], rax
0x18000a099  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18000a0a0  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000a0a5  call    _CxxThrowException_0
0x18000a0ab  mov     ecx, 38h ; '8'
0x18000a0b0  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000a0b6  mov     rbx, rax
0x18000a0b9  mov     [rsp+38h+arg_18], rax
0x18000a0be  test    rax, rax
0x18000a0c1  jz      short loc_18000A0DF
0x18000a0c3  lea     rdx, aNullArrayArgum; "null array argument to ArrayList#CopyTo"
0x18000a0ca  mov     rcx, rax
0x18000a0cd  call    cs:__imp_??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18000a0d3  lea     rax, ??_SArgumentNullException@UnBCL@@6B@; const UnBCL::ArgumentNullException::`local vftable'
0x18000a0da  mov     [rbx], rax
0x18000a0dd  jmp     short loc_18000A0E1
0x18000a0df  xor     ebx, ebx
0x18000a0e1  lea     rdx, aVoidCdeclUnbcl_31; "void __cdecl UnBCL::ArrayList<class UnB"...
0x18000a0e8  mov     rcx, rbx
0x18000a0eb  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18000a0f0  mov     [rsp+38h+pExceptionObject], rax
0x18000a0f5  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18000a0fc  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000a101  call    _CxxThrowException_0
0x18000a107  mov     ecx, 38h ; '8'
0x18000a10c  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000a112  mov     rbx, rax
0x18000a115  mov     [rsp+38h+arg_18], rax
0x18000a11a  test    rax, rax
0x18000a11d  jz      short loc_18000A13B
0x18000a11f  lea     rdx, aInsufficientSp; "insufficient space available in target "...
0x18000a126  mov     rcx, rax
0x18000a129  call    cs:__imp_??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18000a12f  lea     rax, ??_SArgumentException@UnBCL@@6B@; const UnBCL::ArgumentException::`local vftable'
0x18000a136  mov     [rbx], rax
0x18000a139  jmp     short loc_18000A13D
0x18000a13b  xor     ebx, ebx
0x18000a13d  lea     rdx, aVoidCdeclUnbcl_31; "void __cdecl UnBCL::ArrayList<class UnB"...
0x18000a144  mov     rcx, rbx
0x18000a147  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18000a14c  mov     [rsp+38h+pExceptionObject], rax
0x18000a151  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18000a158  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000a15d  call    _CxxThrowException_0
```
