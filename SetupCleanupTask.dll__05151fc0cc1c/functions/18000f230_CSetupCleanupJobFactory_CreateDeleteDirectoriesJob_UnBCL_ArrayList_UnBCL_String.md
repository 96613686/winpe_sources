# CSetupCleanupJobFactory::CreateDeleteDirectoriesJob(UnBCL::ArrayList<UnBCL::String *> *)

- ea: `0x18000f230`
- end: `0x18000f3b6`
- name: `?CreateDeleteDirectoriesJob@CSetupCleanupJobFactory@@SAPEAVISetupCleanupJob@@PEAV?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@Z`
- size: `390`
- prototype: `UnBCL::Object *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x18000f3bc`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x18000cfbc`
- `0x18000f230`
- `0x180036010`

## import_xrefs

- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18000f2c6`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18000f2c6`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18000f2a7`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18000f2a7`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000f2d2`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000f2d2`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x18000f2b6`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x18000f2b6`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18000f37c`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18000f37c`
- `unbcl!??0Object@UnBCL@@QEAA@XZ` at `0x18000f288`
- `unbcl!??0Object@UnBCL@@QEAA@XZ` at `0x18000f288`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000f272`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000f314`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000f35f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000f272`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000f314`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000f35f`

## string_xrefs

- `0x18000f334`: `class ISetupCleanupJob *__cdecl CSetupCleanupJobFactory::CreateDeleteDirectoriesJob(class UnBCL::ArrayList<class UnBCL::String *> *)`
- `0x18000f390`: `class ISetupCleanupJob *__cdecl CSetupCleanupJobFactory::CreateDeleteDirectoriesJob(class UnBCL::ArrayList<class UnBCL::String *> *)`
- `0x18000f372`: `DirectoriesToDelete`
- `0x18000f324`: `Cannot create a DeleteDirectories cleanup job without any target directories`

## pseudocode

```c
UnBCL::Object *__fastcall CSetupCleanupJobFactory::CreateDeleteDirectoriesJob(__int64 a1)
{
  unsigned int (__fastcall ***v2)(_QWORD); // rcx
  UnBCL::Object *v3; // rax
  UnBCL::Object *v4; // rdi
  void (__fastcall ***v6)(_QWORD, __int64); // rcx
  SetupCleanupTaskException *v7; // rax
  UnBCL::ArgumentNullException *v8; // rax
  UnBCL::ArgumentNullException *v9; // rbx
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF
  __int64 pExceptionObject; // [rsp+40h] [rbp+8h] BYREF
  UnBCL::ArgumentNullException *v12; // [rsp+48h] [rbp+10h]

  if ( !a1 )
  {
    v8 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v9 = v8;
    v12 = v8;
    if ( v8 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v8, L"DirectoriesToDelete");
      *(_QWORD *)v9 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v9 = 0;
    }
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v9,
                         "class ISetupCleanupJob *__cdecl CSetupCleanupJobFactory::CreateDeleteDirectoriesJob(class UnBCL"
                         "::ArrayList<class UnBCL::String *> *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  v2 = (unsigned int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 + 8) + 12LL) + 8LL);
  if ( !(**v2)(v2) )
  {
    v6 = (void (__fastcall ***)(_QWORD, __int64))(a1 + *(int *)(*(_QWORD *)(a1 + 8) + 4LL) + 8LL);
    (**v6)(v6, 1);
    v7 = (SetupCleanupTaskException *)UnBCL::Object::operator new(0x38u);
    v12 = v7;
    if ( v7 )
      v7 = SetupCleanupTaskException::SetupCleanupTaskException(
             v7,
             L"Cannot create a DeleteDirectories cleanup job without any target directories");
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v7,
                         "class ISetupCleanupJob *__cdecl CSetupCleanupJobFactory::CreateDeleteDirectoriesJob(class UnBCL"
                         "::ArrayList<class UnBCL::String *> *)");
    throw (SetupCleanupTaskException **)&pExceptionObject;
  }
  v3 = (UnBCL::Object *)UnBCL::Object::operator new(0x20u);
  v4 = v3;
  pExceptionObject = (__int64)v3;
  if ( !v3 )
    return 0;
  UnBCL::Object::Object(v3);
  *(_QWORD *)v4 = &ISetupCleanupJob::`vftable';
  *(_QWORD *)v4 = &CDeleteDirectoriesJob::`vftable';
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>((char *)v4 + 16);
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v10, a1);
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=((char *)v4 + 16, v10);
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v10);
  return v4;
}

```

## disassembly

```asm
0x18000f230  mov     [rsp+arg_10], rbx
0x18000f235  mov     [rsp+arg_18], rsi
0x18000f23a  push    rdi
0x18000f23b  sub     rsp, 30h
0x18000f23f  mov     rsi, rcx
0x18000f242  test    rcx, rcx
0x18000f245  jz      loc_18000F35A
0x18000f24b  mov     rax, [rcx+8]
0x18000f24f  movsxd  rcx, dword ptr [rax+0Ch]
0x18000f253  add     rcx, 8
0x18000f257  add     rcx, rsi
0x18000f25a  mov     rax, [rcx]
0x18000f25d  mov     rax, [rax]
0x18000f260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f265  test    eax, eax
0x18000f267  jz      loc_18000F2F0
0x18000f26d  mov     ecx, 20h ; ' '
0x18000f272  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000f278  mov     rdi, rax
0x18000f27b  mov     [rsp+38h+pExceptionObject], rax
0x18000f280  test    rax, rax
0x18000f283  jz      short loc_18000F2DB
0x18000f285  mov     rcx, rax
0x18000f288  call    cs:__imp_??0Object@UnBCL@@QEAA@XZ; UnBCL::Object::Object(void)
0x18000f28e  nop
0x18000f28f  lea     rax, ??_7ISetupCleanupJob@@6B@; const ISetupCleanupJob::`vftable'
0x18000f296  mov     [rdi], rax
0x18000f299  lea     rax, ??_7CDeleteDirectoriesJob@@6B@; const CDeleteDirectoriesJob::`vftable'
0x18000f2a0  mov     [rdi], rax
0x18000f2a3  lea     rcx, [rdi+10h]
0x18000f2a7  call    cs:__imp_??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(void)
0x18000f2ad  nop
0x18000f2ae  mov     rdx, rsi
0x18000f2b1  lea     rcx, [rsp+38h+var_18]
0x18000f2b6  call    cs:__imp_??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(UnBCL::ArrayList<UnBCL::String *> *)
0x18000f2bc  nop
0x18000f2bd  lea     rdx, [rsp+38h+var_18]
0x18000f2c2  lea     rcx, [rdi+10h]
0x18000f2c6  call    cs:__imp_??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>> const &)
0x18000f2cc  nop
0x18000f2cd  lea     rcx, [rsp+38h+var_18]
0x18000f2d2  call    cs:__imp_??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(void)
0x18000f2d8  nop
0x18000f2d9  jmp     short loc_18000F2DD
0x18000f2db  xor     edi, edi
0x18000f2dd  mov     rax, rdi
0x18000f2e0  mov     rbx, [rsp+38h+arg_10]
0x18000f2e5  mov     rsi, [rsp+38h+arg_18]
0x18000f2ea  add     rsp, 30h
0x18000f2ee  pop     rdi
0x18000f2ef  retn
0x18000f2f0  mov     rax, [rsi+8]
0x18000f2f4  movsxd  rcx, dword ptr [rax+4]
0x18000f2f8  add     rcx, 8
0x18000f2fc  add     rcx, rsi
0x18000f2ff  mov     rax, [rcx]
0x18000f302  mov     edx, 1
0x18000f307  mov     rax, [rax]
0x18000f30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f30f  mov     ecx, 38h ; '8'
0x18000f314  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000f31a  mov     [rsp+38h+arg_8], rax
0x18000f31f  test    rax, rax
0x18000f322  jz      short loc_18000F334
0x18000f324  lea     rdx, aCannotCreateAD; "Cannot create a DeleteDirectories clean"...
0x18000f32b  mov     rcx, rax; this
0x18000f32e  call    ??0SetupCleanupTaskException@@QEAA@PEBG@Z; SetupCleanupTaskException::SetupCleanupTaskException(ushort const *)
0x18000f333  nop
0x18000f334  lea     rdx, aClassIsetupcle_4; "class ISetupCleanupJob *__cdecl CSetupC"...
0x18000f33b  mov     rcx, rax
0x18000f33e  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x18000f343  mov     [rsp+38h+pExceptionObject], rax
0x18000f348  lea     rdx, _TI4PEAVSetupCleanupTaskException@@; pThrowInfo
0x18000f34f  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000f354  call    _CxxThrowException_0
0x18000f35a  mov     ecx, 38h ; '8'
0x18000f35f  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000f365  mov     rbx, rax
0x18000f368  mov     [rsp+38h+arg_8], rax
0x18000f36d  test    rax, rax
0x18000f370  jz      short loc_18000F38E
0x18000f372  lea     rdx, aDirectoriestod; "DirectoriesToDelete"
0x18000f379  mov     rcx, rax
0x18000f37c  call    cs:__imp_??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18000f382  lea     rax, ??_SArgumentNullException@UnBCL@@6B@; const UnBCL::ArgumentNullException::`local vftable'
0x18000f389  mov     [rbx], rax
0x18000f38c  jmp     short loc_18000F390
0x18000f38e  xor     ebx, ebx
0x18000f390  lea     rdx, aClassIsetupcle_4; "class ISetupCleanupJob *__cdecl CSetupC"...
0x18000f397  mov     rcx, rbx
0x18000f39a  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x18000f39f  mov     [rsp+38h+pExceptionObject], rax
0x18000f3a4  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18000f3ab  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000f3b0  call    _CxxThrowException_0
```
