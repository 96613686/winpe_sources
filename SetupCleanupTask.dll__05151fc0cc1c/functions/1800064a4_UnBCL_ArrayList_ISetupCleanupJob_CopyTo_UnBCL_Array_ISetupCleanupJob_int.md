# UnBCL::ArrayList<ISetupCleanupJob *>::CopyTo(UnBCL::Array<ISetupCleanupJob *> *,int)

- ea: `0x1800064a4`
- end: `0x1800066d3`
- name: `?CopyTo@?$ArrayList@PEAVISetupCleanupJob@@@UnBCL@@UEBAXPEAV?$Array@PEAVISetupCleanupJob@@@2@H@Z`
- size: `559`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180006490`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x1800064a4`
- `0x180036010`

## import_xrefs

- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x180006699`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x180006699`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18000663d`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18000663d`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x1800065e1`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x1800065e1`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800065c4`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180006620`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000667c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800065c4`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180006620`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000667c`

## string_xrefs

- `0x1800065f5`: `void __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::CopyTo(class UnBCL::Array<class ISetupCleanupJob *> *,int) const`
- `0x180006651`: `void __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::CopyTo(class UnBCL::Array<class ISetupCleanupJob *> *,int) const`
- `0x1800066ad`: `void __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::CopyTo(class UnBCL::Array<class ISetupCleanupJob *> *,int) const`
- `0x180006633`: `null array argument to ArrayList#CopyTo`
- `0x1800065d7`: `index out of range to ArrayList#CopyTo`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UnBCL::ArrayList<ISetupCleanupJob *>::CopyTo(__int64 a1, __int64 a2, int a3)
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
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v18,
                         "void __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::CopyTo(class UnBCL::Array<class ISetup"
                         "CleanupJob *> *,int) const");
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
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v16,
                         "void __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::CopyTo(class UnBCL::Array<class ISetup"
                         "CleanupJob *> *,int) const");
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
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v20,
                         "void __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::CopyTo(class UnBCL::Array<class ISetup"
                         "CleanupJob *> *,int) const");
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
0x1800064a4  mov     [rsp+arg_0], rbx
0x1800064a9  mov     [rsp+arg_10], rsi
0x1800064ae  push    rdi
0x1800064af  push    r14
0x1800064b1  push    r15
0x1800064b3  sub     rsp, 20h
0x1800064b7  mov     esi, r8d
0x1800064ba  mov     r14, rdx
0x1800064bd  mov     rdi, rcx
0x1800064c0  test    rdx, rdx
0x1800064c3  jz      loc_18000661B
0x1800064c9  test    r8d, r8d
0x1800064cc  js      loc_1800065BF
0x1800064d2  mov     rax, [rcx-50h]
0x1800064d6  movsxd  rcx, dword ptr [rax+0Ch]
0x1800064da  add     rcx, 0FFFFFFFFFFFFFFB0h
0x1800064de  add     rcx, rdi
0x1800064e1  mov     rax, [rcx]
0x1800064e4  mov     rax, [rax]
0x1800064e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ec  mov     ecx, 7FFFFFFFh
0x1800064f1  sub     ecx, esi
0x1800064f3  cmp     ecx, eax
0x1800064f5  jl      loc_1800065BF
0x1800064fb  mov     rax, [r14]
0x1800064fe  mov     rcx, r14
0x180006501  mov     rax, [rax]
0x180006504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006509  mov     ebx, eax
0x18000650b  mov     rcx, [rdi-50h]
0x18000650f  movsxd  rcx, dword ptr [rcx+0Ch]
0x180006513  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180006517  add     rcx, rdi
0x18000651a  mov     rdx, [rcx]
0x18000651d  mov     rax, [rdx]
0x180006520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006525  add     eax, esi
0x180006527  cmp     eax, ebx
0x180006529  jg      loc_180006677
0x18000652f  mov     rax, [rdi-50h]
0x180006533  movsxd  rcx, dword ptr [rax+0Ch]
0x180006537  add     rcx, 0FFFFFFFFFFFFFFB0h
0x18000653b  add     rcx, rdi
0x18000653e  mov     rax, [rcx]
0x180006541  mov     rax, [rax]
0x180006544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006549  test    eax, eax
0x18000654b  jz      short loc_1800065AB
0x18000654d  lea     rcx, [rdi-58h]
0x180006551  mov     rax, [rcx]
0x180006554  xor     edx, edx
0x180006556  mov     rax, [rax+68h]
0x18000655a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000655f  mov     r15, rax
0x180006562  mov     rcx, [r14]
0x180006565  mov     rax, [rcx+38h]
0x180006569  xor     edx, edx
0x18000656b  mov     rcx, r14
0x18000656e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006573  mov     r14, rax
0x180006576  xor     ebx, ebx
0x180006578  mov     rcx, [rdi-50h]
0x18000657c  movsxd  rcx, dword ptr [rcx+0Ch]
0x180006580  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180006584  add     rcx, rdi
0x180006587  mov     rdx, [rcx]
0x18000658a  mov     rax, [rdx]
0x18000658d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006592  cmp     ebx, eax
0x180006594  jge     short loc_1800065AB
0x180006596  movsxd  rdx, ebx
0x180006599  lea     eax, [rbx+rsi]
0x18000659c  movsxd  rcx, eax
0x18000659f  mov     rax, [r15+rdx*8]
0x1800065a3  mov     [r14+rcx*8], rax
0x1800065a7  inc     ebx
0x1800065a9  jmp     short loc_180006578
0x1800065ab  mov     rbx, [rsp+38h+arg_0]
0x1800065b0  mov     rsi, [rsp+38h+arg_10]
0x1800065b5  add     rsp, 20h
0x1800065b9  pop     r15
0x1800065bb  pop     r14
0x1800065bd  pop     rdi
0x1800065be  retn
0x1800065bf  mov     ecx, 38h ; '8'
0x1800065c4  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800065ca  mov     rbx, rax
0x1800065cd  mov     [rsp+38h+arg_18], rax
0x1800065d2  test    rax, rax
0x1800065d5  jz      short loc_1800065F3
0x1800065d7  lea     rdx, aIndexOutOfRang; "index out of range to ArrayList#CopyTo"
0x1800065de  mov     rcx, rax
0x1800065e1  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x1800065e7  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x1800065ee  mov     [rbx], rax
0x1800065f1  jmp     short loc_1800065F5
0x1800065f3  xor     ebx, ebx
0x1800065f5  lea     rdx, aVoidCdeclUnbcl_18; "void __cdecl UnBCL::ArrayList<class ISe"...
0x1800065fc  mov     rcx, rbx
0x1800065ff  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x180006604  mov     [rsp+38h+pExceptionObject], rax
0x180006609  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180006610  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180006615  call    _CxxThrowException_0
0x18000661b  mov     ecx, 38h ; '8'
0x180006620  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180006626  mov     rbx, rax
0x180006629  mov     [rsp+38h+arg_18], rax
0x18000662e  test    rax, rax
0x180006631  jz      short loc_18000664F
0x180006633  lea     rdx, aNullArrayArgum; "null array argument to ArrayList#CopyTo"
0x18000663a  mov     rcx, rax
0x18000663d  call    cs:__imp_??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180006643  lea     rax, ??_SArgumentNullException@UnBCL@@6B@; const UnBCL::ArgumentNullException::`local vftable'
0x18000664a  mov     [rbx], rax
0x18000664d  jmp     short loc_180006651
0x18000664f  xor     ebx, ebx
0x180006651  lea     rdx, aVoidCdeclUnbcl_18; "void __cdecl UnBCL::ArrayList<class ISe"...
0x180006658  mov     rcx, rbx
0x18000665b  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x180006660  mov     [rsp+38h+pExceptionObject], rax
0x180006665  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18000666c  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180006671  call    _CxxThrowException_0
0x180006677  mov     ecx, 38h ; '8'
0x18000667c  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180006682  mov     rbx, rax
0x180006685  mov     [rsp+38h+arg_18], rax
0x18000668a  test    rax, rax
0x18000668d  jz      short loc_1800066AB
0x18000668f  lea     rdx, aInsufficientSp; "insufficient space available in target "...
0x180006696  mov     rcx, rax
0x180006699  call    cs:__imp_??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18000669f  lea     rax, ??_SArgumentException@UnBCL@@6B@; const UnBCL::ArgumentException::`local vftable'
0x1800066a6  mov     [rbx], rax
0x1800066a9  jmp     short loc_1800066AD
0x1800066ab  xor     ebx, ebx
0x1800066ad  lea     rdx, aVoidCdeclUnbcl_18; "void __cdecl UnBCL::ArrayList<class ISe"...
0x1800066b4  mov     rcx, rbx
0x1800066b7  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x1800066bc  mov     [rsp+38h+pExceptionObject], rax
0x1800066c1  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x1800066c8  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x1800066cd  call    _CxxThrowException_0
```
