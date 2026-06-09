# UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::CopyTo(UnBCL::Array<UnBCL::SmartPtr<UnBCL::String>> *,int)

- ea: `0x18000eff4`
- end: `0x18000f22a`
- name: `?CopyTo@?$ArrayList@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@UnBCL@@UEBAXPEAV?$Array@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@2@H@Z`
- size: `566`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18000efe0`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x18000eff4`
- `0x180036010`

## import_xrefs

- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x18000f1f0`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x18000f1f0`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18000f194`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18000f194`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18000f138`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18000f138`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18000f0fb`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18000f0fb`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000f11b`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000f177`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000f1d3`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000f11b`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000f177`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000f1d3`

## string_xrefs

- `0x18000f18a`: `null array argument to ArrayList#CopyTo`
- `0x18000f12e`: `index out of range to ArrayList#CopyTo`
- `0x18000f14c`: `void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::CopyTo(class UnBCL::Array<class UnBCL::SmartPtr<class UnBCL::String> > *,int) const`
- `0x18000f1a8`: `void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::CopyTo(class UnBCL::Array<class UnBCL::SmartPtr<class UnBCL::String> > *,int) const`
- `0x18000f204`: `void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::CopyTo(class UnBCL::Array<class UnBCL::SmartPtr<class UnBCL::String> > *,int) const`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::CopyTo(__int64 a1, __int64 a2, int a3)
{
  int (__fastcall ***v6)(_QWORD); // rcx
  signed int v7; // ebx
  __int64 (__fastcall ***v8)(_QWORD); // rcx
  __int64 (__fastcall ***v9)(_QWORD); // rcx
  __int64 result; // rax
  __int64 v11; // rbp
  __int64 v12; // r14
  int i; // ebx
  __int64 (__fastcall ***v14)(_QWORD); // rcx
  UnBCL::ArgumentOutOfRangeException *v15; // rax
  UnBCL::Exception *v16; // rbx
  UnBCL::ArgumentNullException *v17; // rax
  UnBCL::Exception *v18; // rbx
  UnBCL::ArgumentException *v19; // rax
  UnBCL::Exception *v20; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+58h] [rbp+10h] BYREF
  UnBCL::ArgumentNullException *v22; // [rsp+68h] [rbp+20h]

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
                         "void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::CopyTo(class UnBCL:"
                         ":Array<class UnBCL::SmartPtr<class UnBCL::String> > *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::CopyTo(class UnBCL:"
                         ":Array<class UnBCL::SmartPtr<class UnBCL::String> > *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::CopyTo(class UnBCL:"
                         ":Array<class UnBCL::SmartPtr<class UnBCL::String> > *,int) const");
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
      UnBCL::SmartPtr<UnBCL::String>::operator=(v12 + 16LL * (i + a3), v11 + 16LL * i);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000eff4  mov     [rsp+arg_0], rbx
0x18000eff9  push    rbp
0x18000effa  push    rsi
0x18000effb  push    rdi
0x18000effc  push    r14
0x18000effe  push    r15
0x18000f000  sub     rsp, 20h
0x18000f004  mov     esi, r8d
0x18000f007  mov     r14, rdx
0x18000f00a  mov     rdi, rcx
0x18000f00d  test    rdx, rdx
0x18000f010  jz      loc_18000F172
0x18000f016  test    r8d, r8d
0x18000f019  js      loc_18000F116
0x18000f01f  mov     rax, [rcx-50h]
0x18000f023  movsxd  rcx, dword ptr [rax+0Ch]
0x18000f027  add     rcx, 0FFFFFFFFFFFFFFB0h
0x18000f02b  add     rcx, rdi
0x18000f02e  mov     rax, [rcx]
0x18000f031  mov     rax, [rax]
0x18000f034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f039  mov     ecx, 7FFFFFFFh
0x18000f03e  sub     ecx, esi
0x18000f040  cmp     ecx, eax
0x18000f042  jl      loc_18000F116
0x18000f048  mov     rax, [r14]
0x18000f04b  mov     rcx, r14
0x18000f04e  mov     rax, [rax]
0x18000f051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f056  mov     ebx, eax
0x18000f058  mov     rcx, [rdi-50h]
0x18000f05c  movsxd  rcx, dword ptr [rcx+0Ch]
0x18000f060  add     rcx, 0FFFFFFFFFFFFFFB0h
0x18000f064  add     rcx, rdi
0x18000f067  mov     rdx, [rcx]
0x18000f06a  mov     rax, [rdx]
0x18000f06d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f072  add     eax, esi
0x18000f074  cmp     eax, ebx
0x18000f076  jg      loc_18000F1CE
0x18000f07c  mov     rax, [rdi-50h]
0x18000f080  movsxd  rcx, dword ptr [rax+0Ch]
0x18000f084  add     rcx, 0FFFFFFFFFFFFFFB0h
0x18000f088  add     rcx, rdi
0x18000f08b  mov     rax, [rcx]
0x18000f08e  mov     rax, [rax]
0x18000f091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f096  test    eax, eax
0x18000f098  jz      short loc_18000F105
0x18000f09a  mov     rax, [rdi-58h]
0x18000f09e  xor     edx, edx
0x18000f0a0  lea     rcx, [rdi-58h]
0x18000f0a4  mov     rax, [rax+68h]
0x18000f0a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0ad  mov     rbp, rax
0x18000f0b0  mov     rcx, [r14]
0x18000f0b3  mov     rax, [rcx+38h]
0x18000f0b7  xor     edx, edx
0x18000f0b9  mov     rcx, r14
0x18000f0bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0c1  mov     r14, rax
0x18000f0c4  xor     ebx, ebx
0x18000f0c6  mov     rcx, [rdi-50h]
0x18000f0ca  movsxd  rcx, dword ptr [rcx+0Ch]
0x18000f0ce  add     rcx, 0FFFFFFFFFFFFFFB0h
0x18000f0d2  add     rcx, rdi
0x18000f0d5  mov     rdx, [rcx]
0x18000f0d8  mov     rax, [rdx]
0x18000f0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0e0  cmp     ebx, eax
0x18000f0e2  jge     short loc_18000F105
0x18000f0e4  movsxd  rdx, ebx
0x18000f0e7  shl     rdx, 4
0x18000f0eb  add     rdx, rbp
0x18000f0ee  lea     eax, [rbx+rsi]
0x18000f0f1  movsxd  rcx, eax
0x18000f0f4  shl     rcx, 4
0x18000f0f8  add     rcx, r14
0x18000f0fb  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18000f101  inc     ebx
0x18000f103  jmp     short loc_18000F0C6
0x18000f105  mov     rbx, [rsp+48h+arg_0]
0x18000f10a  add     rsp, 20h
0x18000f10e  pop     r15
0x18000f110  pop     r14
0x18000f112  pop     rdi
0x18000f113  pop     rsi
0x18000f114  pop     rbp
0x18000f115  retn
0x18000f116  mov     ecx, 38h ; '8'
0x18000f11b  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000f121  mov     rbx, rax
0x18000f124  mov     [rsp+48h+arg_18], rax
0x18000f129  test    rax, rax
0x18000f12c  jz      short loc_18000F14A
0x18000f12e  lea     rdx, aIndexOutOfRang; "index out of range to ArrayList#CopyTo"
0x18000f135  mov     rcx, rax
0x18000f138  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18000f13e  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x18000f145  mov     [rbx], rax
0x18000f148  jmp     short loc_18000F14C
0x18000f14a  xor     ebx, ebx
0x18000f14c  lea     rdx, aVoidCdeclUnbcl_13; "void __cdecl UnBCL::ArrayList<class UnB"...
0x18000f153  mov     rcx, rbx
0x18000f156  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x18000f15b  mov     [rsp+48h+pExceptionObject], rax
0x18000f160  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18000f167  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000f16c  call    _CxxThrowException_0
0x18000f172  mov     ecx, 38h ; '8'
0x18000f177  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000f17d  mov     rbx, rax
0x18000f180  mov     [rsp+48h+arg_18], rax
0x18000f185  test    rax, rax
0x18000f188  jz      short loc_18000F1A6
0x18000f18a  lea     rdx, aNullArrayArgum; "null array argument to ArrayList#CopyTo"
0x18000f191  mov     rcx, rax
0x18000f194  call    cs:__imp_??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18000f19a  lea     rax, ??_SArgumentNullException@UnBCL@@6B@; const UnBCL::ArgumentNullException::`local vftable'
0x18000f1a1  mov     [rbx], rax
0x18000f1a4  jmp     short loc_18000F1A8
0x18000f1a6  xor     ebx, ebx
0x18000f1a8  lea     rdx, aVoidCdeclUnbcl_13; "void __cdecl UnBCL::ArrayList<class UnB"...
0x18000f1af  mov     rcx, rbx
0x18000f1b2  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x18000f1b7  mov     [rsp+48h+pExceptionObject], rax
0x18000f1bc  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18000f1c3  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000f1c8  call    _CxxThrowException_0
0x18000f1ce  mov     ecx, 38h ; '8'
0x18000f1d3  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000f1d9  mov     rbx, rax
0x18000f1dc  mov     [rsp+48h+arg_18], rax
0x18000f1e1  test    rax, rax
0x18000f1e4  jz      short loc_18000F202
0x18000f1e6  lea     rdx, aInsufficientSp; "insufficient space available in target "...
0x18000f1ed  mov     rcx, rax
0x18000f1f0  call    cs:__imp_??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18000f1f6  lea     rax, ??_SArgumentException@UnBCL@@6B@; const UnBCL::ArgumentException::`local vftable'
0x18000f1fd  mov     [rbx], rax
0x18000f200  jmp     short loc_18000F204
0x18000f202  xor     ebx, ebx
0x18000f204  lea     rdx, aVoidCdeclUnbcl_13; "void __cdecl UnBCL::ArrayList<class UnB"...
0x18000f20b  mov     rcx, rbx
0x18000f20e  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x18000f213  mov     [rsp+48h+pExceptionObject], rax
0x18000f218  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18000f21f  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000f224  call    _CxxThrowException_0
```
