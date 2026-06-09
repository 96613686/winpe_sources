# UnBCL::ArrayList<ISetupCleanupJob *>::BinarySearch(int,int,ISetupCleanupJob *,UnBCL::IComparer<ISetupCleanupJob *> *)

- ea: `0x180005f20`
- end: `0x1800060cb`
- name: `?BinarySearch@?$ArrayList@PEAVISetupCleanupJob@@@UnBCL@@AEAAHHHPEAVISetupCleanupJob@@PEAU?$IComparer@PEAVISetupCleanupJob@@@2@@Z`
- size: `427`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64 (__fastcall ***)(_QWORD, __int64, _QWORD))`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800060e0`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x180005f20`
- `0x180036010`

## import_xrefs

- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x180006091`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x180006091`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180006035`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180006035`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180006018`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180006074`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180006018`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180006074`

## string_xrefs

- `0x180006049`: `int __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::BinarySearch(int,int,class ISetupCleanupJob *,struct UnBCL::IComparer<class ISetupCleanupJob *> *)`
- `0x1800060a5`: `int __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::BinarySearch(int,int,class ISetupCleanupJob *,struct UnBCL::IComparer<class ISetupCleanupJob *> *)`

## pseudocode

```c
__int64 __fastcall UnBCL::ArrayList<ISetupCleanupJob *>::BinarySearch(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 (__fastcall ***a5)(_QWORD, __int64, _QWORD))
{
  unsigned int v6; // edi
  int (__fastcall ***v8)(_QWORD); // rcx
  signed int v9; // ebx
  signed int v10; // r14d
  __int64 v11; // rcx
  _QWORD *v12; // rax
  __int64 v13; // rdx
  int v14; // eax
  UnBCL::ArgumentOutOfRangeException *v16; // rax
  UnBCL::Exception *v17; // rbx
  UnBCL::ArgumentException *v18; // rax
  UnBCL::Exception *v19; // rbx
  UnBCL::InvalidOperationException *v20; // rbx
  UnBCL::String *v21; // rax
  const struct UnBCL::String *v22; // rdi
  UnBCL::InvalidOperationException *v23; // rax
  UnBCL::Exception *v24; // rbx
  UnBCL::Exception *v25; // [rsp+28h] [rbp-70h] BYREF
  UnBCL::Exception *v26; // [rsp+30h] [rbp-68h] BYREF
  UnBCL::Exception *v27; // [rsp+38h] [rbp-60h] BYREF
  UnBCL::Exception *pExceptionObject; // [rsp+40h] [rbp-58h] BYREF
  UnBCL::ArgumentException *v29; // [rsp+48h] [rbp-50h]
  UnBCL::ArgumentOutOfRangeException *v30; // [rsp+50h] [rbp-48h]
  struct UnBCL::Exception *v31; // [rsp+58h] [rbp-40h] BYREF

  v6 = a3;
  if ( a3 < 0 )
  {
    v16 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v17 = v16;
    v30 = v16;
    if ( v16 )
    {
      UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
        v16,
        L"negative index or count to ArrayList#BinarySearch");
      *(_QWORD *)v17 = &UnBCL::ArgumentOutOfRangeException::`local vftable';
    }
    else
    {
      v17 = 0;
    }
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v17,
                         "int __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::BinarySearch(int,int,class ISetupCleanu"
                         "pJob *,struct UnBCL::IComparer<class ISetupCleanupJob *> *)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v8 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 + 8) + 12LL) + 8LL);
  if ( (**v8)(v8) < a3 )
  {
    v18 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v19 = v18;
    v29 = v18;
    if ( v18 )
    {
      UnBCL::ArgumentException::ArgumentException(
        v18,
        L"index and count do not denote a valid range of elements in ArrayList#BinarySearch");
      *(_QWORD *)v19 = &UnBCL::ArgumentException::`local vftable';
    }
    else
    {
      v19 = 0;
    }
    v25 = AddStackTraceToException<SetupCleanupTaskException>(
            v19,
            "int __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::BinarySearch(int,int,class ISetupCleanupJob *,struct"
            " UnBCL::IComparer<class ISetupCleanupJob *> *)");
    throw (UnBCL::ArgumentException **)&v25;
  }
  v9 = 0;
LABEL_4:
  v10 = v6 - 1;
  while ( v9 <= v10 )
  {
    v6 = (v10 + v9) / 2;
    v11 = a1 + *(int *)(*(_QWORD *)(a1 + 8) + 16LL) + 8LL;
    v12 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 24LL))(v11, v6);
    v13 = *v12;
    try
    {
      if ( a5 )
      {
        v14 = (**a5)(a5, a4, *v12);
        goto LABEL_41;
      }
      if ( a4 )
      {
        if ( !v13 )
        {
          v14 = 1;
          goto LABEL_41;
        }
      }
      else if ( v13 )
      {
        v14 = -1;
        goto LABEL_41;
      }
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a4 + 48LL))(a4);
    }
    catch ( UnBCL::Exception *v31 )
    {
      v20 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
      v29 = v20;
      if ( v20 )
      {
        v21 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v22 = v21;
        v30 = v21;
        if ( v21 )
        {
          UnBCL::String::String(v21, L"Compare failed -- bad comparison routines?");
          *(_QWORD *)v22 = &UnBCL::String::`local vftable';
        }
        else
        {
          v22 = 0;
        }
        UnBCL::InvalidOperationException::InvalidOperationException(v20, v22, v31);
        *(_QWORD *)v20 = &UnBCL::InvalidOperationException::`local vftable';
      }
      else
      {
        v20 = 0;
      }
      v26 = AddStackTraceToException<SetupCleanupTaskException>(
              v20,
              "int __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::BinarySearch(int,int,class ISetupCleanupJob *,stru"
              "ct UnBCL::IComparer<class ISetupCleanupJob *> *)");
      throw (UnBCL::InvalidOperationException **)&v26;
    }
    catch ( ... )
    {
      v23 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
      v24 = v23;
      v30 = v23;
      if ( v23 )
      {
        UnBCL::InvalidOperationException::InvalidOperationException(v23, L"sort failed -- bad comparison routines?");
        *(_QWORD *)v24 = &UnBCL::InvalidOperationException::`local vftable';
      }
      else
      {
        v24 = 0;
      }
      v27 = AddStackTraceToException<SetupCleanupTaskException>(
              v24,
              "int __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::BinarySearch(int,int,class ISetupCleanupJob *,stru"
              "ct UnBCL::IComparer<class ISetupCleanupJob *> *)");
      throw (UnBCL::InvalidOperationException **)&v27;
    }
LABEL_41:
    if ( !v14 )
      return v6;
    if ( v14 < 0 )
      goto LABEL_4;
    v9 = v6 + 1;
  }
  return (unsigned int)~v9;
}

```

## disassembly

```asm
0x180005f20  push    rbx
0x180005f22  push    rsi
0x180005f23  push    rdi
0x180005f24  push    r13
0x180005f26  push    r14
0x180005f28  push    r15
0x180005f2a  sub     rsp, 68h
0x180005f2e  mov     rsi, r9
0x180005f31  mov     edi, r8d
0x180005f34  mov     r13, rcx
0x180005f37  test    r8d, r8d
0x180005f3a  js      loc_180006013
0x180005f40  mov     rax, [rcx+8]
0x180005f44  movsxd  rcx, dword ptr [rax+0Ch]
0x180005f48  add     rcx, 8
0x180005f4c  add     rcx, r13
0x180005f4f  mov     rax, [rcx]
0x180005f52  mov     rax, [rax]
0x180005f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f5a  cmp     eax, edi
0x180005f5c  jl      loc_18000606F
0x180005f62  xor     ebx, ebx
0x180005f64  mov     r15, [rsp+98h+arg_20]
0x180005f6c  lea     r14d, [rdi-1]
0x180005f70  cmp     ebx, r14d
0x180005f73  jg      loc_18000600D
0x180005f79  lea     eax, [r14+rbx]
0x180005f7d  cdq
0x180005f7e  sub     eax, edx
0x180005f80  sar     eax, 1
0x180005f82  mov     edi, eax
0x180005f84  mov     rcx, [r13+8]
0x180005f88  movsxd  rcx, dword ptr [rcx+10h]
0x180005f8c  add     rcx, 8
0x180005f90  add     rcx, r13
0x180005f93  mov     rdx, [rcx]
0x180005f96  mov     rax, [rdx+18h]
0x180005f9a  mov     edx, edi
0x180005f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fa1  mov     rdx, [rax]
0x180005fa4  test    r15, r15
0x180005fa7  jz      short loc_180005FBF
0x180005fa9  mov     rax, [r15]
0x180005fac  mov     r8, rdx
0x180005faf  mov     rdx, rsi
0x180005fb2  mov     rcx, r15
0x180005fb5  mov     rax, [rax]
0x180005fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fbd  jmp     short loc_180005FE7
0x180005fbf  test    rsi, rsi
0x180005fc2  jnz     short loc_180005FCE
0x180005fc4  test    rdx, rdx
0x180005fc7  jz      short loc_180005FD8
0x180005fc9  or      eax, 0FFFFFFFFh
0x180005fcc  jmp     short loc_180005FE7
0x180005fce  test    rdx, rdx
0x180005fd1  jnz     short loc_180005FD8
0x180005fd3  lea     eax, [rdx+1]
0x180005fd6  jmp     short loc_180005FE7
0x180005fd8  mov     rax, [rsi]
0x180005fdb  mov     rcx, rsi
0x180005fde  mov     rax, [rax+30h]
0x180005fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fe7  mov     [rsp+98h+var_78], eax
0x180005feb  test    eax, eax
0x180005fed  jnz     short loc_180005FFF
0x180005fef  mov     eax, edi
0x180005ff1  add     rsp, 68h
0x180005ff5  pop     r15
0x180005ff7  pop     r14
0x180005ff9  pop     r13
0x180005ffb  pop     rdi
0x180005ffc  pop     rsi
0x180005ffd  pop     rbx
0x180005ffe  retn
0x180005fff  js      loc_180005F6C
0x180006005  lea     ebx, [rdi+1]
0x180006008  jmp     loc_180005F70
0x18000600d  not     ebx
0x18000600f  mov     eax, ebx
0x180006011  jmp     short loc_180005FF1
0x180006013  mov     ecx, 38h ; '8'
0x180006018  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000601e  mov     rbx, rax
0x180006021  mov     [rsp+98h+var_48], rax
0x180006026  test    rax, rax
0x180006029  jz      short loc_180006047
0x18000602b  lea     rdx, aNegativeIndexO; "negative index or count to ArrayList#Bi"...
0x180006032  mov     rcx, rax
0x180006035  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18000603b  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x180006042  mov     [rbx], rax
0x180006045  jmp     short loc_180006049
0x180006047  xor     ebx, ebx
0x180006049  lea     rdx, aIntCdeclUnbclA_4; "int __cdecl UnBCL::ArrayList<class ISet"...
0x180006050  mov     rcx, rbx
0x180006053  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x180006058  mov     [rsp+98h+pExceptionObject], rax
0x18000605d  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180006064  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180006069  call    _CxxThrowException_0
0x18000606f  mov     ecx, 38h ; '8'
0x180006074  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000607a  mov     rbx, rax
0x18000607d  mov     [rsp+98h+var_50], rax
0x180006082  test    rax, rax
0x180006085  jz      short loc_1800060A3
0x180006087  lea     rdx, aIndexAndCountD; "index and count do not denote a valid r"...
0x18000608e  mov     rcx, rax
0x180006091  call    cs:__imp_??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180006097  lea     rax, ??_SArgumentException@UnBCL@@6B@; const UnBCL::ArgumentException::`local vftable'
0x18000609e  mov     [rbx], rax
0x1800060a1  jmp     short loc_1800060A5
0x1800060a3  xor     ebx, ebx
0x1800060a5  lea     rdx, aIntCdeclUnbclA_4; "int __cdecl UnBCL::ArrayList<class ISet"...
0x1800060ac  mov     rcx, rbx
0x1800060af  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x1800060b4  mov     [rsp+98h+var_70], rax
0x1800060b9  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x1800060c0  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x1800060c5  call    _CxxThrowException_0
```
