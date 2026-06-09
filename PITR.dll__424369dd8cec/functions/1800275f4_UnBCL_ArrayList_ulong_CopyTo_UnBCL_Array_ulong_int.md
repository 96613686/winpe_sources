# UnBCL::ArrayList<ulong>::CopyTo(UnBCL::Array<ulong> *,int)

- ea: `0x1800275f4`
- end: `0x180027823`
- name: `?CopyTo@?$ArrayList@K@UnBCL@@UEBAXPEAV?$Array@K@2@H@Z`
- size: `559`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800275e0`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x1800275f4`
- `0x180053010`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027714`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027770`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800277cc`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027714`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027770`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800277cc`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18002778d`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18002778d`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x1800277e9`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x1800277e9`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180027731`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180027731`

## string_xrefs

- `0x180027783`: `null array argument to ArrayList#CopyTo`
- `0x180027727`: `index out of range to ArrayList#CopyTo`
- `0x180027745`: `void __cdecl UnBCL::ArrayList<unsigned long>::CopyTo(class UnBCL::Array<unsigned long> *,int) const`
- `0x1800277a1`: `void __cdecl UnBCL::ArrayList<unsigned long>::CopyTo(class UnBCL::Array<unsigned long> *,int) const`
- `0x1800277fd`: `void __cdecl UnBCL::ArrayList<unsigned long>::CopyTo(class UnBCL::Array<unsigned long> *,int) const`

## pseudocode

```c
__int64 __fastcall UnBCL::ArrayList<unsigned long>::CopyTo(__int64 a1, __int64 a2, int a3)
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
                         "void __cdecl UnBCL::ArrayList<unsigned long>::CopyTo(class UnBCL::Array<unsigned long> *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<unsigned long>::CopyTo(class UnBCL::Array<unsigned long> *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<unsigned long>::CopyTo(class UnBCL::Array<unsigned long> *,int) const");
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
      *(_DWORD *)(v12 + 4LL * (i + a3)) = *(_DWORD *)(v11 + 4LL * i);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800275f4  mov     [rsp+arg_0], rbx
0x1800275f9  mov     [rsp+arg_10], rsi
0x1800275fe  push    rdi
0x1800275ff  push    r14
0x180027601  push    r15
0x180027603  sub     rsp, 20h
0x180027607  mov     esi, r8d
0x18002760a  mov     r14, rdx
0x18002760d  mov     rdi, rcx
0x180027610  test    rdx, rdx
0x180027613  jz      loc_18002776B
0x180027619  test    r8d, r8d
0x18002761c  js      loc_18002770F
0x180027622  mov     rax, [rcx-50h]
0x180027626  movsxd  rcx, dword ptr [rax+0Ch]
0x18002762a  add     rcx, 0FFFFFFFFFFFFFFB0h
0x18002762e  add     rcx, rdi
0x180027631  mov     rax, [rcx]
0x180027634  mov     rax, [rax]
0x180027637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002763c  mov     ecx, 7FFFFFFFh
0x180027641  sub     ecx, esi
0x180027643  cmp     ecx, eax
0x180027645  jl      loc_18002770F
0x18002764b  mov     rax, [r14]
0x18002764e  mov     rcx, r14
0x180027651  mov     rax, [rax]
0x180027654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027659  mov     ebx, eax
0x18002765b  mov     rcx, [rdi-50h]
0x18002765f  movsxd  rcx, dword ptr [rcx+0Ch]
0x180027663  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180027667  add     rcx, rdi
0x18002766a  mov     rdx, [rcx]
0x18002766d  mov     rax, [rdx]
0x180027670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027675  add     eax, esi
0x180027677  cmp     eax, ebx
0x180027679  jg      loc_1800277C7
0x18002767f  mov     rax, [rdi-50h]
0x180027683  movsxd  rcx, dword ptr [rax+0Ch]
0x180027687  add     rcx, 0FFFFFFFFFFFFFFB0h
0x18002768b  add     rcx, rdi
0x18002768e  mov     rax, [rcx]
0x180027691  mov     rax, [rax]
0x180027694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027699  test    eax, eax
0x18002769b  jz      short loc_1800276FB
0x18002769d  lea     rcx, [rdi-58h]
0x1800276a1  mov     rax, [rcx]
0x1800276a4  xor     edx, edx
0x1800276a6  mov     rax, [rax+68h]
0x1800276aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276af  mov     r15, rax
0x1800276b2  mov     rcx, [r14]
0x1800276b5  mov     rax, [rcx+38h]
0x1800276b9  xor     edx, edx
0x1800276bb  mov     rcx, r14
0x1800276be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276c3  mov     r14, rax
0x1800276c6  xor     ebx, ebx
0x1800276c8  mov     rcx, [rdi-50h]
0x1800276cc  movsxd  rcx, dword ptr [rcx+0Ch]
0x1800276d0  add     rcx, 0FFFFFFFFFFFFFFB0h
0x1800276d4  add     rcx, rdi
0x1800276d7  mov     rdx, [rcx]
0x1800276da  mov     rax, [rdx]
0x1800276dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276e2  cmp     ebx, eax
0x1800276e4  jge     short loc_1800276FB
0x1800276e6  movsxd  rdx, ebx
0x1800276e9  lea     eax, [rbx+rsi]
0x1800276ec  movsxd  rcx, eax
0x1800276ef  mov     eax, [r15+rdx*4]
0x1800276f3  mov     [r14+rcx*4], eax
0x1800276f7  inc     ebx
0x1800276f9  jmp     short loc_1800276C8
0x1800276fb  mov     rbx, [rsp+38h+arg_0]
0x180027700  mov     rsi, [rsp+38h+arg_10]
0x180027705  add     rsp, 20h
0x180027709  pop     r15
0x18002770b  pop     r14
0x18002770d  pop     rdi
0x18002770e  retn
0x18002770f  mov     ecx, 38h ; '8'
0x180027714  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002771a  mov     rbx, rax
0x18002771d  mov     [rsp+38h+arg_18], rax
0x180027722  test    rax, rax
0x180027725  jz      short loc_180027743
0x180027727  lea     rdx, aIndexOutOfRang; "index out of range to ArrayList#CopyTo"
0x18002772e  mov     rcx, rax
0x180027731  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180027737  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x18002773e  mov     [rbx], rax
0x180027741  jmp     short loc_180027745
0x180027743  xor     ebx, ebx
0x180027745  lea     rdx, aVoidCdeclUnbcl_48; "void __cdecl UnBCL::ArrayList<unsigned "...
0x18002774c  mov     rcx, rbx
0x18002774f  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180027754  mov     [rsp+38h+pExceptionObject], rax
0x180027759  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180027760  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180027765  call    _CxxThrowException_0
0x18002776b  mov     ecx, 38h ; '8'
0x180027770  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180027776  mov     rbx, rax
0x180027779  mov     [rsp+38h+arg_18], rax
0x18002777e  test    rax, rax
0x180027781  jz      short loc_18002779F
0x180027783  lea     rdx, aNullArrayArgum; "null array argument to ArrayList#CopyTo"
0x18002778a  mov     rcx, rax
0x18002778d  call    cs:__imp_??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180027793  lea     rax, ??_SArgumentNullException@UnBCL@@6B@; const UnBCL::ArgumentNullException::`local vftable'
0x18002779a  mov     [rbx], rax
0x18002779d  jmp     short loc_1800277A1
0x18002779f  xor     ebx, ebx
0x1800277a1  lea     rdx, aVoidCdeclUnbcl_48; "void __cdecl UnBCL::ArrayList<unsigned "...
0x1800277a8  mov     rcx, rbx
0x1800277ab  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800277b0  mov     [rsp+38h+pExceptionObject], rax
0x1800277b5  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x1800277bc  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x1800277c1  call    _CxxThrowException_0
0x1800277c7  mov     ecx, 38h ; '8'
0x1800277cc  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800277d2  mov     rbx, rax
0x1800277d5  mov     [rsp+38h+arg_18], rax
0x1800277da  test    rax, rax
0x1800277dd  jz      short loc_1800277FB
0x1800277df  lea     rdx, aInsufficientSp; "insufficient space available in target "...
0x1800277e6  mov     rcx, rax
0x1800277e9  call    cs:__imp_??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x1800277ef  lea     rax, ??_SArgumentException@UnBCL@@6B@; const UnBCL::ArgumentException::`local vftable'
0x1800277f6  mov     [rbx], rax
0x1800277f9  jmp     short loc_1800277FD
0x1800277fb  xor     ebx, ebx
0x1800277fd  lea     rdx, aVoidCdeclUnbcl_48; "void __cdecl UnBCL::ArrayList<unsigned "...
0x180027804  mov     rcx, rbx
0x180027807  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002780c  mov     [rsp+38h+pExceptionObject], rax
0x180027811  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180027818  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18002781d  call    _CxxThrowException_0
```
