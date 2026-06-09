# AppReadiness::Impl::BaseTaskGroup::OnProgress(IAppReadinessTask *)

- ea: `0x180014450`
- end: `0x18001481a`
- name: `?OnProgress@BaseTaskGroup@Impl@AppReadiness@@UEAAJPEAUIAppReadinessTask@@@Z`
- size: `970`
- prototype: `__int64 __fastcall(AppReadiness::Impl::BaseTaskGroup *__hidden this, struct IAppReadinessTask *)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002958`
- `0x180002a48`
- `0x1800054c0`
- `0x18000b464`
- `0x1800130b0`
- `0x18001441c`
- `0x180014450`
- `0x180014820`
- `0x18001488c`
- `0x1800148b0`
- `0x18001555c`
- `0x1800155b0`
- `0x1800155e8`
- `0x18001f08c`
- `0x180027a4c`
- `0x180031f64`
- `0x180032198`
- `0x1800351ec`
- `0x18003e210`
- `0x18003ecb4`
- `0x1800465f8`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014694`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001474b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014694`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001474b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800145c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001461a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800145c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001461a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014489`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800145f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014489`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800145f0`

## string_xrefs

- `0x180014549`: `onecoreuap\shell\appreadiness\src\core\basetaskgroup.cpp`
- `0x180014587`: `onecoreuap\shell\appreadiness\src\core\basetaskgroup.cpp`
- `0x180014555`: `AppReadiness::Impl::BaseTaskGroup::OnProgress`
- `0x180014593`: `AppReadiness::Impl::BaseTaskGroup::OnProgress`
- `0x18001459a`: `iter.first.As(&taskInf)`
- `0x18001455c`: `taskInf->GetPercentComplete(&percent)`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall AppReadiness::Impl::BaseTaskGroup::OnProgress(RTL_SRWLOCK *this, struct IAppReadinessTask *a2)
{
  int v3; // r12d
  unsigned int v4; // esi
  RTL_SRWLOCK *v5; // r15
  RTL_SRWLOCK *Ptr; // r14
  RTL_SRWLOCK *v7; // rax
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rbx
  int v10; // edx
  int v11; // eax
  __int64 v12; // rcx
  RTL_SRWLOCK *v13; // rdi
  unsigned int v14; // r15d
  char v15; // bl
  __int64 *v16; // rsi
  __int64 *v17; // r12
  __int64 v18; // rbx
  _BYTE *v19; // rdx
  _BYTE *v20; // rdx
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *pExceptionObject[5]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v28[56]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE *v29; // [rsp+B8h] [rbp-48h]
  _BYTE v30[56]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE *v31; // [rsp+F8h] [rbp-8h]

  v3 = 0;
  v4 = 0;
  v5 = this - 22;
  AcquireSRWLockShared(this - 22);
  v23 = (__int64)v5;
  Ptr = (RTL_SRWLOCK *)this[2].Ptr;
  v7 = (RTL_SRWLOCK *)this[3].Ptr;
  SRWLock = v7;
  while ( Ptr != v7 )
  {
    v22 = 0;
    v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))Ptr->Ptr;
    v9 = **(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))Ptr->Ptr;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    v10 = v9(v8, &GUID_96080be3_6332_4825_92ef_ba6c9ac6d91d, &v22);
    if ( v10 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v10,
        "iter.first.As(&taskInf)",
        "AppReadiness::Impl::BaseTaskGroup::OnProgress",
        "onecoreuap\\shell\\appreadiness\\src\\core\\basetaskgroup.cpp",
        134);
      throw (Windows::HResultException *)pExceptionObject;
    }
    LODWORD(v25) = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 40LL))(v22, &v25);
    if ( v11 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v11,
        "taskInf->GetPercentComplete(&percent)",
        "AppReadiness::Impl::BaseTaskGroup::OnProgress",
        "onecoreuap\\shell\\appreadiness\\src\\core\\basetaskgroup.cpp",
        136);
      throw (Windows::HResultException *)pExceptionObject;
    }
    v3 += v25;
    v4 += 100;
    v12 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 16LL))(v12, (unsigned int)v11);
    }
    Ptr += 2;
    v7 = SRWLock;
  }
  if ( v5 )
    ReleaseSRWLockShared(v5);
  v13 = this - 29;
  if ( v4 )
    v14 = 100 * v3 / v4;
  else
    v14 = 0;
  AcquireSRWLockShared(v13 + 7);
  if ( v14 == HIDWORD(v13[9].Ptr) || (v15 = 1, (unsigned __int8)AppReadiness::Impl::BaseTask::CheckState(v13, 7)) )
    v15 = 0;
  if ( this != (RTL_SRWLOCK *)176 )
    ReleaseSRWLockShared(v13 + 7);
  if ( v15 )
  {
    std::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,enum AppReadiness::Impl::BaseTaskGroup::TaskState>>::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,enum AppReadiness::Impl::BaseTaskGroup::TaskState>>(pExceptionObject);
    Microsoft::WRL::ComPtr<IAppReadinessTask>::ComPtr<IAppReadinessTask>(&v25, (__int64)v13);
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &v13[7]);
    std::vector<Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>>::reserve(
      pExceptionObject,
      ((char *)v13[12].Ptr - (char *)v13[11].Ptr) >> 3);
    std::vector<Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>>>>,0>(
      pExceptionObject,
      &v23,
      pExceptionObject[0],
      (__int64)v13[11].Ptr,
      (__int64)v13[12].Ptr);
    HIDWORD(v13[9].Ptr) = v14;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v16 = pExceptionObject[0];
    v17 = pExceptionObject[1];
    v18 = v25;
    while ( v16 != v17 )
    {
      v23 = *v16;
      Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(&v23);
      v24 = v18;
      Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(&v24);
      v29 = 0;
      v29 = (_BYTE *)std::_Func_impl_no_alloc__lambda_b62627bf7d4402e1b915d8f4360132e2__void_::_Func_impl_no_alloc__lambda_b62627bf7d4402e1b915d8f4360132e2__void___lambda_b62627bf7d4402e1b915d8f4360132e2__0_(
                       v28,
                       &v23);
      Windows::StdNoThrowBoundry(v28);
      if ( v29 )
      {
        v19 = v28;
        LOBYTE(v19) = v29 != v28;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v29 + 32LL))(v29, v19);
        v29 = 0;
      }
      lambda_b62627bf7d4402e1b915d8f4360132e2_::__lambda_b62627bf7d4402e1b915d8f4360132e2_(&v23);
      ++v16;
    }
    v22 = 0;
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &v13[7]);
    wil::com_ptr_t<IAgileReference,wil::err_exception_policy>::operator=(&v22, &v13[8]);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( v22 )
    {
      wil::com_ptr_t<IAgileReference,wil::err_exception_policy>::com_ptr_t<IAgileReference,wil::err_exception_policy>(
        &v23,
        &v22);
      v24 = v18;
      Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(&v24);
      v31 = 0;
      v31 = (_BYTE *)std::_Func_impl_no_alloc__lambda_4698ab28ec52e54293df26a96b734ce8__void_::_Func_impl_no_alloc__lambda_4698ab28ec52e54293df26a96b734ce8__void___lambda_4698ab28ec52e54293df26a96b734ce8__0_(
                       v30,
                       &v23);
      Windows::StdNoThrowBoundry(v30);
      if ( v31 )
      {
        v20 = v30;
        LOBYTE(v20) = v31 != v30;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v31 + 32LL))(v31, v20);
        v31 = 0;
      }
      lambda_e47fd043e2dca7ef4575152d5d90605d_::__lambda_e47fd043e2dca7ef4575152d5d90605d_(&v23);
    }
    (*((void (__fastcall **)(RTL_SRWLOCK *, _QWORD))v13->Ptr + 23))(v13, v14);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v22);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    std::vector<Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>>::_Tidy(pExceptionObject);
  }
  return 0;
}

```

## disassembly

```asm
0x180014450  push    rbp
0x180014452  push    rbx
0x180014453  push    rsi
0x180014454  push    rdi
0x180014455  push    r12
0x180014457  push    r13
0x180014459  push    r14
0x18001445b  push    r15
0x18001445d  lea     rbp, [rsp-18h]
0x180014462  sub     rsp, 118h
0x180014469  mov     rax, cs:__security_cookie
0x180014470  xor     rax, rsp
0x180014473  mov     [rbp+50h+var_50], rax
0x180014477  mov     r13, rcx
0x18001447a  xor     r12d, r12d
0x18001447d  xor     esi, esi
0x18001447f  lea     r15, [rcx-0B0h]
0x180014486  mov     rcx, r15; SRWLock
0x180014489  call    cs:__imp_AcquireSRWLockShared
0x18001448f  mov     [rsp+150h+var_118], r15
0x180014494  mov     r14, [r13+10h]
0x180014498  mov     rax, [r13+18h]
0x18001449c  mov     [rsp+150h+SRWLock], rax
0x1800144a1  cmp     r14, rax
0x1800144a4  jz      loc_1800145BD
0x1800144aa  mov     [rsp+150h+var_120], 0
0x1800144b3  mov     rdi, [r14]
0x1800144b6  mov     rax, [rdi]
0x1800144b9  mov     rbx, [rax]
0x1800144bc  lea     rcx, [rsp+150h+var_120]
0x1800144c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800144c6  lea     r8, [rsp+150h+var_120]
0x1800144cb  lea     rdx, _GUID_96080be3_6332_4825_92ef_ba6c9ac6d91d
0x1800144d2  mov     rcx, rdi
0x1800144d5  mov     rax, rbx
0x1800144d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144dd  mov     edx, eax; int
0x1800144df  test    eax, eax
0x1800144e1  js      loc_18001457F
0x1800144e7  mov     dword ptr [rsp+150h+var_108], 0
0x1800144ef  mov     rcx, [rsp+150h+var_120]
0x1800144f4  mov     rax, [rcx]
0x1800144f7  lea     rdx, [rsp+150h+var_108]
0x1800144fc  mov     rax, [rax+28h]
0x180014500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014505  mov     edx, eax; int
0x180014507  test    eax, eax
0x180014509  js      short loc_180014541
0x18001450b  add     r12d, dword ptr [rsp+150h+var_108]
0x180014510  add     esi, 64h ; 'd'
0x180014513  mov     rcx, [rsp+150h+var_120]
0x180014518  test    rcx, rcx
0x18001451b  jz      short loc_180014533
0x18001451d  mov     [rsp+150h+var_120], 0
0x180014526  mov     rax, [rcx]
0x180014529  mov     rax, [rax+10h]
0x18001452d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014532  nop
0x180014533  add     r14, 10h
0x180014537  mov     rax, [rsp+150h+SRWLock]
0x18001453c  jmp     loc_1800144A1
0x180014541  mov     [rsp+150h+var_128], 88h; int
0x180014549  lea     rax, aOnecoreuapShel_11; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180014550  mov     [rsp+150h+var_130], rax; char *
0x180014555  lea     r9, aAppreadinessIm_4; "AppReadiness::Impl::BaseTaskGroup::OnPr"...
0x18001455c  lea     r8, aTaskinfGetperc; "taskInf->GetPercentComplete(&percent)"
0x180014563  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180014568  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18001456d  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180014574  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180014579  call    _CxxThrowException_0
0x18001457f  mov     [rsp+150h+var_128], 86h; int
0x180014587  lea     rax, aOnecoreuapShel_11; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18001458e  mov     [rsp+150h+var_130], rax; char *
0x180014593  lea     r9, aAppreadinessIm_4; "AppReadiness::Impl::BaseTaskGroup::OnPr"...
0x18001459a  lea     r8, aIterFirstAsTas; "iter.first.As(&taskInf)"
0x1800145a1  lea     rcx, [rsp+150h+pExceptionObject]; this
0x1800145a6  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800145ab  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800145b2  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x1800145b7  call    _CxxThrowException_0
0x1800145bd  test    r15, r15
0x1800145c0  jz      short loc_1800145CB
0x1800145c2  mov     rcx, r15; SRWLock
0x1800145c5  call    cs:__imp_ReleaseSRWLockShared
0x1800145cb  lea     rdi, [r13-0E8h]
0x1800145d2  xor     r13d, r13d
0x1800145d5  test    esi, esi
0x1800145d7  jz      short loc_1800145E6
0x1800145d9  imul    eax, r12d, 64h ; 'd'
0x1800145dd  xor     edx, edx
0x1800145df  div     esi
0x1800145e1  mov     r15d, eax
0x1800145e4  jmp     short loc_1800145E9
0x1800145e6  mov     r15d, r13d
0x1800145e9  lea     r14, [rdi+38h]
0x1800145ed  mov     rcx, r14; SRWLock
0x1800145f0  call    cs:__imp_AcquireSRWLockShared
0x1800145f6  cmp     r15d, [rdi+4Ch]
0x1800145fa  jz      short loc_18001460F
0x1800145fc  mov     edx, 7
0x180014601  mov     rcx, rdi
0x180014604  call    ?CheckState@BaseTask@Impl@AppReadiness@@IEBA_NW4ExecutionState@123@@Z; AppReadiness::Impl::BaseTask::CheckState(AppReadiness::Impl::BaseTask::ExecutionState)
0x180014609  test    al, al
0x18001460b  mov     bl, 1
0x18001460d  jz      short loc_180014612
0x18001460f  mov     bl, r13b
0x180014612  test    r14, r14
0x180014615  jz      short loc_180014620
0x180014617  mov     rcx, r14; SRWLock
0x18001461a  call    cs:__imp_ReleaseSRWLockShared
0x180014620  test    bl, bl
0x180014622  jz      loc_1800147F8
0x180014628  lea     rcx, [rsp+150h+pExceptionObject]
0x18001462d  call    ??0?$vector@U?$pair@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@W4TaskState@BaseTaskGroup@Impl@AppReadiness@@@std@@V?$allocator@U?$pair@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@W4TaskState@BaseTaskGroup@Impl@AppReadiness@@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,AppReadiness::Impl::BaseTaskGroup::TaskState>>::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,AppReadiness::Impl::BaseTaskGroup::TaskState>>(void)
0x180014632  nop
0x180014633  mov     rdx, rdi
0x180014636  lea     rcx, [rsp+150h+var_108]
0x18001463b  call    ??$?0VBaseTask@Impl@AppReadiness@@@?$ComPtr@UIAppReadinessTask@@@WRL@Microsoft@@QEAA@PEAVBaseTask@Impl@AppReadiness@@@Z; Microsoft::WRL::ComPtr<IAppReadinessTask>::ComPtr<IAppReadinessTask>(AppReadiness::Impl::BaseTask *)
0x180014640  nop
0x180014641  mov     rdx, r14
0x180014644  lea     rcx, [rsp+150h+SRWLock]
0x180014649  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001464e  nop
0x18001464f  mov     rdx, [rdi+60h]
0x180014653  sub     rdx, [rdi+58h]
0x180014657  sar     rdx, 3
0x18001465b  lea     rcx, [rsp+150h+pExceptionObject]
0x180014660  call    ?reserve@?$vector@V?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@@std@@@std@@QEAAX_K@Z; std::vector<Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>>::reserve(unsigned __int64)
0x180014665  mov     rax, [rdi+60h]
0x180014669  mov     [rsp+150h+var_130], rax
0x18001466e  mov     r9, [rdi+58h]
0x180014672  mov     r8, [rsp+150h+pExceptionObject]
0x180014677  lea     rdx, [rsp+150h+var_118]
0x18001467c  lea     rcx, [rsp+150h+pExceptionObject]
0x180014681  call    ??$insert@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@@std@@@std@@@std@@$0A@@?$vector@V?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@@std@@@std@@@1@V21@1@Z; std::vector<Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>>>>,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>>>>)
0x180014686  mov     [rdi+4Ch], r15d
0x18001468a  mov     rcx, [rsp+150h+SRWLock]; SRWLock
0x18001468f  test    rcx, rcx
0x180014692  jz      short loc_18001469A
0x180014694  call    cs:__imp_ReleaseSRWLockExclusive
0x18001469a  mov     rsi, [rsp+150h+pExceptionObject]
0x18001469f  mov     r12, [rsp+150h+var_F0]
0x1800146a4  mov     rbx, [rsp+150h+var_108]
0x1800146a9  jmp     short loc_18001471C
0x1800146ab  mov     rax, [rsi]
0x1800146ae  mov     [rsp+150h+var_118], rax
0x1800146b3  lea     rcx, [rsp+150h+var_118]
0x1800146b8  call    ?InternalAddRef@?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(void)
0x1800146bd  mov     [rsp+150h+var_110], rbx
0x1800146c2  lea     rcx, [rsp+150h+var_110]
0x1800146c7  call    ?InternalAddRef@?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(void)
0x1800146cc  mov     [rbp+50h+var_98], r13
0x1800146d0  lea     rdx, [rsp+150h+var_118]
0x1800146d5  lea     rcx, [rbp+50h+var_D0]
0x1800146d9  call    std___Func_impl_no_alloc__lambda_b62627bf7d4402e1b915d8f4360132e2__void____Func_impl_no_alloc__lambda_b62627bf7d4402e1b915d8f4360132e2__void___lambda_b62627bf7d4402e1b915d8f4360132e2__0_
0x1800146de  mov     [rbp+50h+var_98], rax
0x1800146e2  lea     rcx, [rbp+50h+var_D0]
0x1800146e6  call    ?StdNoThrowBoundry@Windows@@YAJAEBV?$function@$$A6AXXZ@std@@@Z; Windows::StdNoThrowBoundry(std::function<void (void)> const &)
0x1800146eb  mov     rcx, [rbp+50h+var_98]
0x1800146ef  test    rcx, rcx
0x1800146f2  jz      short loc_18001470E
0x1800146f4  mov     rax, [rcx]
0x1800146f7  lea     rdx, [rbp+50h+var_D0]
0x1800146fb  cmp     rcx, rdx
0x1800146fe  setnz   dl
0x180014701  mov     rax, [rax+20h]
0x180014705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001470a  mov     [rbp+50h+var_98], r13
0x18001470e  lea     rcx, [rsp+150h+var_118]
0x180014713  call    _lambda_b62627bf7d4402e1b915d8f4360132e2_____lambda_b62627bf7d4402e1b915d8f4360132e2_
0x180014718  add     rsi, 8
0x18001471c  cmp     rsi, r12
0x18001471f  jnz     short loc_1800146AB
0x180014721  mov     [rsp+150h+var_120], r13
0x180014726  mov     rdx, r14
0x180014729  lea     rcx, [rsp+150h+SRWLock]
0x18001472e  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180014733  lea     rdx, [rdi+40h]
0x180014737  lea     rcx, [rsp+150h+var_120]
0x18001473c  call    ??4?$com_ptr_t@UIAgileReference@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IAgileReference,wil::err_exception_policy>::operator=(wil::com_ptr_t<IAgileReference,wil::err_exception_policy> const &)
0x180014741  mov     rcx, [rsp+150h+SRWLock]; SRWLock
0x180014746  test    rcx, rcx
0x180014749  jz      short loc_180014751
0x18001474b  call    cs:__imp_ReleaseSRWLockExclusive
0x180014751  cmp     [rsp+150h+var_120], r13
0x180014756  jz      short loc_1800147C2
0x180014758  lea     rdx, [rsp+150h+var_120]
0x18001475d  lea     rcx, [rsp+150h+var_118]
0x180014762  call    ??0?$com_ptr_t@UIAgileReference@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<IAgileReference,wil::err_exception_policy>::com_ptr_t<IAgileReference,wil::err_exception_policy>(wil::com_ptr_t<IAgileReference,wil::err_exception_policy> const &)
0x180014767  mov     [rsp+150h+var_110], rbx
0x18001476c  lea     rcx, [rsp+150h+var_110]
0x180014771  call    ?InternalAddRef@?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(void)
0x180014776  mov     [rbp+50h+var_58], r13
0x18001477a  lea     rdx, [rsp+150h+var_118]
0x18001477f  lea     rcx, [rbp+50h+var_90]
0x180014783  call    std___Func_impl_no_alloc__lambda_4698ab28ec52e54293df26a96b734ce8__void____Func_impl_no_alloc__lambda_4698ab28ec52e54293df26a96b734ce8__void___lambda_4698ab28ec52e54293df26a96b734ce8__0_
0x180014788  mov     [rbp+50h+var_58], rax
0x18001478c  lea     rcx, [rbp+50h+var_90]
0x180014790  call    ?StdNoThrowBoundry@Windows@@YAJAEBV?$function@$$A6AXXZ@std@@@Z; Windows::StdNoThrowBoundry(std::function<void (void)> const &)
0x180014795  mov     rcx, [rbp+50h+var_58]
0x180014799  test    rcx, rcx
0x18001479c  jz      short loc_1800147B8
0x18001479e  mov     rax, [rcx]
0x1800147a1  lea     rdx, [rbp+50h+var_90]
0x1800147a5  cmp     rcx, rdx
0x1800147a8  setnz   dl
0x1800147ab  mov     rax, [rax+20h]
0x1800147af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147b4  mov     [rbp+50h+var_58], r13
0x1800147b8  lea     rcx, [rsp+150h+var_118]
0x1800147bd  call    _lambda_e47fd043e2dca7ef4575152d5d90605d_____lambda_e47fd043e2dca7ef4575152d5d90605d_
0x1800147c2  mov     rax, [rdi]
0x1800147c5  mov     edx, r15d
0x1800147c8  mov     rcx, rdi
0x1800147cb  mov     rax, [rax+0B8h]
0x1800147d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147d7  nop
0x1800147d8  lea     rcx, [rsp+150h+var_120]
0x1800147dd  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800147e2  nop
0x1800147e3  lea     rcx, [rsp+150h+var_108]
0x1800147e8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800147ed  nop
0x1800147ee  lea     rcx, [rsp+150h+pExceptionObject]
0x1800147f3  call    ?_Tidy@?$vector@V?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>>::_Tidy(void)
0x1800147f8  xor     eax, eax
0x1800147fa  mov     rcx, [rbp+50h+var_50]
0x1800147fe  xor     rcx, rsp; StackCookie
0x180014801  call    __security_check_cookie
0x180014806  add     rsp, 118h
0x18001480d  pop     r15
0x18001480f  pop     r14
0x180014811  pop     r13
0x180014813  pop     r12
0x180014815  pop     rdi
0x180014816  pop     rsi
0x180014817  pop     rbx
0x180014818  pop     rbp
0x180014819  retn
```
