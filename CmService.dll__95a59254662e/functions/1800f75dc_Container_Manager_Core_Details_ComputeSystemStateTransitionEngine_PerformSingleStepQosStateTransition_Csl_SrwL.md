# Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::PerformSingleStepQosStateTransition(Csl::SrwLock::ReleaseOnScopeExit<0> &)

- ea: `0x1800f75dc`
- end: `0x1800f81e8`
- name: `?PerformSingleStepQosStateTransition@ComputeSystemStateTransitionEngine@Details@Core@Manager@Container@@AEAAJAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z`
- size: `3084`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800f6828`

## callees

- `0x180004bd0`
- `0x180005704`
- `0x180007b48`
- `0x180007dd4`
- `0x180009ba0`
- `0x18000da88`
- `0x18000dab0`
- `0x1800103a4`
- `0x18002da58`
- `0x1800f4208`
- `0x1800f42b4`
- `0x1800f439c`
- `0x1800f4448`
- `0x1800f45e0`
- `0x1800f46c4`
- `0x1800f47b4`
- `0x1800f4860`
- `0x1800f4950`
- `0x1800f75dc`
- `0x1800f81f0`
- `0x1800f8544`
- `0x1800f9600`
- `0x180123bb8`
- `0x180187398`

## import_xrefs

- `ntdll!NtSetInformationJobObject` at `0x1800f7891`
- `ntdll!NtSetInformationJobObject` at `0x1800f7996`
- `ntdll!NtSetInformationJobObject` at `0x1800f7ab4`
- `ntdll!NtSetInformationJobObject` at `0x1800f7bc1`
- `ntdll!NtSetInformationJobObject` at `0x1800f7bee`
- `ntdll!NtSetInformationJobObject` at `0x1800f7c1e`
- `ntdll!NtSetInformationJobObject` at `0x1800f7c48`
- `ntdll!NtSetInformationJobObject` at `0x1800f7c72`
- `ntdll!NtSetInformationJobObject` at `0x1800f7ca0`
- `ntdll!NtSetInformationJobObject` at `0x1800f7dcc`
- `ntdll!NtSetInformationJobObject` at `0x1800f7eed`
- `ntdll!NtSetInformationJobObject` at `0x1800f8000`
- `ntdll!NtSetInformationJobObject` at `0x1800f8121`
- `ntdll!NtSetInformationJobObject` at `0x1800f7891`
- `ntdll!NtSetInformationJobObject` at `0x1800f7996`
- `ntdll!NtSetInformationJobObject` at `0x1800f7ab4`
- `ntdll!NtSetInformationJobObject` at `0x1800f7bc1`
- `ntdll!NtSetInformationJobObject` at `0x1800f7bee`
- `ntdll!NtSetInformationJobObject` at `0x1800f7c1e`
- `ntdll!NtSetInformationJobObject` at `0x1800f7c48`
- `ntdll!NtSetInformationJobObject` at `0x1800f7c72`
- `ntdll!NtSetInformationJobObject` at `0x1800f7ca0`
- `ntdll!NtSetInformationJobObject` at `0x1800f7dcc`
- `ntdll!NtSetInformationJobObject` at `0x1800f7eed`
- `ntdll!NtSetInformationJobObject` at `0x1800f8000`
- `ntdll!NtSetInformationJobObject` at `0x1800f8121`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7776`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f78a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f79a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7ac6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7cce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7dde`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7eff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8012`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8138`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7776`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f78a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f79a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7ac6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7cce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7dde`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7eff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8012`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8138`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7752`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f77a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f77bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7854`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f78d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f78ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f795c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f79d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f79ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7a92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7af6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7b0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7b81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7cfe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7d15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7da9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7e0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7e25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7ec8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7f2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7f46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7fdc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8042`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8059`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f80eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8167`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f817e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7752`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f77a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f77bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7854`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f78d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f78ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f795c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f79d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f79ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7a92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7af6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7b0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7b81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7cfe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7d15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7da9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7e0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7e25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7ec8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7f2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7f46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7fdc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8042`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8059`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f80eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8167`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f817e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7782`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f78af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f79b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7ad2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7cda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7dea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7f0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f801e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f8144`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7782`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f78af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f79b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7ad2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7cda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7dea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7f0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f801e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f8144`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::PerformSingleStepQosStateTransition(
        PSRWLOCK SRWLock,
        char *a2)
{
  PSRWLOCK v4; // r14
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // r14d
  __int64 v14; // rdx
  unsigned int v15; // eax
  unsigned int Ptr_high; // ecx
  unsigned int v17; // r15d
  __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned __int8 v20; // r14
  char v21; // r12
  __int64 v22; // rcx
  NTSTATUS v23; // r14d
  __int64 v24; // rcx
  __int64 v25; // rdx
  _DWORD *v26; // rax
  int v27; // r12d
  char v28; // r14
  __int64 v29; // rcx
  __int64 v30; // rcx
  char *v31; // rcx
  char v32; // al
  int v33; // eax
  int v34; // edx
  __int64 v35; // rcx
  __int64 v36; // rcx
  int Ptr; // edx
  unsigned int v38; // ecx
  __int64 v39; // rcx
  PVOID v40; // rcx
  NTSTATUS v41; // eax
  __int64 v42; // rdx
  __int64 v43; // rcx
  char *v44; // rcx
  char v45; // al
  int v46; // eax
  int v47; // edx
  __int64 v48; // rcx
  __int64 v49; // rcx
  char *v50; // rdx
  char v51; // al
  int v52; // eax
  int v53; // ecx
  __int64 v54; // rcx
  __int64 v55; // rcx
  char *v56; // rdx
  char v57; // al
  int v58; // eax
  int v59; // ecx
  __int64 v60; // rcx
  __int64 v61; // rcx
  char v63; // r14
  unsigned int v64; // ecx
  __int64 v65; // rcx
  NTSTATUS v66; // eax
  void *v67; // rdx
  unsigned int v68; // r8d
  __int64 v69; // rcx
  int v70; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v71; // [rsp+28h] [rbp-D8h] BYREF
  __int64 JobInformation; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v73; // [rsp+38h] [rbp-C8h] BYREF
  char v74; // [rsp+40h] [rbp-C0h] BYREF
  char v75; // [rsp+48h] [rbp-B8h] BYREF
  char v76; // [rsp+50h] [rbp-B0h] BYREF
  char v77; // [rsp+58h] [rbp-A8h] BYREF
  char v78; // [rsp+60h] [rbp-A0h] BYREF
  char v79; // [rsp+68h] [rbp-98h] BYREF
  char v80; // [rsp+70h] [rbp-90h] BYREF
  char v81; // [rsp+78h] [rbp-88h] BYREF
  char v82; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v83[36]; // [rsp+90h] [rbp-70h] BYREF
  int v84; // [rsp+B4h] [rbp-4Ch]
  __int64 v85; // [rsp+100h] [rbp+0h]
  __int128 v86; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v87[42]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v87,
    "ContainerStateTransition");
  v87[0] = &CmTraceProvider::ContainerStateTransition::`vftable';
  CmTraceProvider::ContainerStateTransition::StartActivity(
    (CmTraceProvider::ContainerStateTransition *)v87,
    (const struct _GUID *)&SRWLock[21]);
  v4 = SRWLock + 6;
  v5 = Container::Manager::Core::Details::SelectSingleStepQosStateTransition((char *)&SRWLock[2].Ptr + 4, &SRWLock[6])
     - 1;
  if ( !v5 )
  {
    v63 = (__int64)v4->Ptr & 1;
    LOBYTE(v70) = v63;
    v64 = HIDWORD(SRWLock[16].Ptr) | 1;
    if ( !v63 )
      v64 = HIDWORD(SRWLock[16].Ptr) & 0xFFFFFFFE;
    HIDWORD(SRWLock[16].Ptr) = v64;
    CmTraceProvider::ContainerStateTransition::FreezeComputeSystemJob<bool &>(v87, &v70);
    v65 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_DWORD *)(v65 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v65);
      *(_QWORD *)a2 = 0;
    }
    v86 = 0;
    LODWORD(v86) = 1;
    BYTE4(v86) = v63;
    v66 = NtSetInformationJobObject(SRWLock[180].Ptr, (JOBOBJECTINFOCLASS)18, &v86, 0x10u);
    if ( v66 < 0 )
      wil::details::in1diag3::_FailFast_NtStatus(retaddr, v67, v68, (const char *)(unsigned int)v66, v70);
    AcquireSRWLockExclusive(SRWLock);
    LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
    if ( a2 == &v82 )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(SRWLock);
    }
    else
    {
      v69 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 )
      {
        *(_DWORD *)(v69 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v69);
      }
      *(_QWORD *)a2 = SRWLock;
    }
    goto LABEL_152;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    *(_QWORD *)&v86 = 0;
    v56 = (char *)&SRWLock[6].Ptr + 4;
    if ( ((__int64)v4->Ptr & 2) != 0 )
    {
      v57 = *v56;
      HIDWORD(SRWLock[16].Ptr) |= 2u;
      LOBYTE(SRWLock[17].Ptr) = v57;
      LODWORD(v86) = 5;
      DWORD1(v86) = 100 * (unsigned __int8)*v56;
    }
    else
    {
      HIDWORD(SRWLock[16].Ptr) &= ~2u;
      LOBYTE(SRWLock[17].Ptr) = 0;
    }
    v58 = (__int64)v4->Ptr & 2;
    if ( v58 )
      v59 = (unsigned __int8)*v56;
    else
      v59 = 0;
    LODWORD(v71) = v59;
    LOBYTE(v70) = v58 != 0;
    CmTraceProvider::ContainerStateTransition::CpuHardCapComputeSystemJob<bool,int>(v87, &v70, &v71);
    v60 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_DWORD *)(v60 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v60);
      *(_QWORD *)a2 = 0;
    }
    v23 = NtSetInformationJobObject(SRWLock[180].Ptr, MaxJobObjectInfoClass|JobObjectBasicProcessIdList, &v86, 8u);
    AcquireSRWLockExclusive(SRWLock);
    LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
    if ( a2 == &v81 )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(SRWLock);
    }
    else
    {
      v61 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 )
      {
        *(_DWORD *)(v61 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v61);
      }
      *(_QWORD *)a2 = SRWLock;
    }
    if ( v23 >= 0 )
      goto LABEL_152;
    v25 = 1435;
    goto LABEL_140;
  }
  v7 = v6 - 2;
  if ( !v7 )
  {
    JobInformation = 0;
    v50 = (char *)&SRWLock[6].Ptr + 4;
    if ( ((__int64)v4->Ptr & 4) != 0 )
    {
      v51 = *v50;
      HIDWORD(SRWLock[16].Ptr) |= 4u;
      LOBYTE(SRWLock[17].Ptr) = v51;
      LODWORD(JobInformation) = 17;
      WORD2(JobInformation) = 100 * (unsigned __int8)*v50;
      HIWORD(JobInformation) = 10000;
    }
    else
    {
      HIDWORD(SRWLock[16].Ptr) &= ~4u;
      LOBYTE(SRWLock[17].Ptr) = 0;
    }
    v52 = (__int64)v4->Ptr & 4;
    if ( v52 )
      v53 = (unsigned __int8)*v50;
    else
      v53 = 0;
    LODWORD(v71) = v53;
    LOBYTE(v70) = v52 != 0;
    CmTraceProvider::ContainerStateTransition::CpuSoftCapComputeSystemJob<bool,int>(v87, &v70, &v71);
    v54 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_DWORD *)(v54 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v54);
      *(_QWORD *)a2 = 0;
    }
    v23 = NtSetInformationJobObject(
            SRWLock[180].Ptr,
            MaxJobObjectInfoClass|JobObjectBasicProcessIdList,
            &JobInformation,
            8u);
    AcquireSRWLockExclusive(SRWLock);
    LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
    if ( a2 == &v80 )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(SRWLock);
    }
    else
    {
      v55 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 )
      {
        *(_DWORD *)(v55 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v55);
      }
      *(_QWORD *)a2 = SRWLock;
    }
    if ( v23 >= 0 )
      goto LABEL_152;
    v25 = 1496;
    goto LABEL_140;
  }
  v8 = v7 - 4;
  if ( !v8 )
  {
    v73 = 0;
    v44 = (char *)&SRWLock[6].Ptr + 4;
    if ( ((__int64)v4->Ptr & 8) != 0 )
    {
      v45 = *v44;
      HIDWORD(SRWLock[16].Ptr) |= 8u;
      LOBYTE(SRWLock[17].Ptr) = v45;
      LODWORD(v73) = 3;
      HIDWORD(v73) = (unsigned __int8)*v44;
    }
    else
    {
      HIDWORD(SRWLock[16].Ptr) &= ~8u;
      LOBYTE(SRWLock[17].Ptr) = 0;
    }
    v46 = (__int64)v4->Ptr & 8;
    if ( v46 )
      v47 = (unsigned __int8)*v44;
    else
      v47 = 0;
    LODWORD(v71) = v47;
    LOBYTE(v70) = v46 != 0;
    CmTraceProvider::ContainerStateTransition::CpuWeightComputeSystemJob<bool,int>(v87, &v70, &v71);
    v48 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_DWORD *)(v48 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v48);
      *(_QWORD *)a2 = 0;
    }
    v23 = NtSetInformationJobObject(SRWLock[180].Ptr, MaxJobObjectInfoClass|JobObjectBasicProcessIdList, &v73, 8u);
    AcquireSRWLockExclusive(SRWLock);
    LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
    if ( a2 == &v79 )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(SRWLock);
    }
    else
    {
      v49 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 )
      {
        *(_DWORD *)(v49 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v49);
      }
      *(_QWORD *)a2 = SRWLock;
    }
    if ( v23 >= 0 )
      goto LABEL_152;
    v25 = 1554;
    goto LABEL_140;
  }
  v9 = v8 - 8;
  if ( !v9 )
  {
    Ptr = (int)v4->Ptr;
    v38 = HIDWORD(SRWLock[16].Ptr) | 0x10;
    if ( ((__int64)v4->Ptr & 0x10) == 0 )
      v38 = HIDWORD(SRWLock[16].Ptr) & 0xFFFFFFEF;
    HIDWORD(SRWLock[16].Ptr) = v38;
    BYTE1(v70) = (Ptr & 0x10) != 0;
    CmTraceProvider::ContainerStateTransition::CpuRankBiasComputeSystemJob<unsigned char &>(v87, (char *)&v70 + 1);
    v39 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_DWORD *)(v39 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v39);
      *(_QWORD *)a2 = 0;
    }
    v40 = SRWLock[180].Ptr;
    if ( BYTE1(v70) )
    {
      v71 = 0x500000003LL;
      v23 = NtSetInformationJobObject(v40, MaxJobObjectInfoClass|JobObjectBasicProcessIdList, &v71, 8u);
      if ( v23 < 0 )
        goto LABEL_88;
      v23 = NtSetInformationJobObject(SRWLock[180].Ptr, JobObjectEndOfJobTimeInformation|0x10, (char *)&v70 + 1, 1u);
      if ( v23 >= 0 )
        goto LABEL_88;
      v71 = 0;
      v41 = NtSetInformationJobObject(SRWLock[180].Ptr, MaxJobObjectInfoClass|JobObjectBasicProcessIdList, &v71, 8u);
      if ( v41 >= 0 )
        goto LABEL_88;
      v42 = 1626;
    }
    else
    {
      v23 = NtSetInformationJobObject(v40, JobObjectEndOfJobTimeInformation|0x10, (char *)&v70 + 1, 1u);
      if ( v23 < 0 )
        goto LABEL_88;
      *(_QWORD *)&v86 = 0;
      v23 = NtSetInformationJobObject(SRWLock[180].Ptr, MaxJobObjectInfoClass|JobObjectBasicProcessIdList, &v86, 8u);
      if ( v23 >= 0 )
        goto LABEL_88;
      LOBYTE(v70) = 1;
      v41 = NtSetInformationJobObject(SRWLock[180].Ptr, JobObjectEndOfJobTimeInformation|0x10, &v70, 1u);
      if ( v41 >= 0 )
        goto LABEL_88;
      v42 = 1658;
    }
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)v42,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)(unsigned int)v41,
      v70);
LABEL_88:
    AcquireSRWLockExclusive(SRWLock);
    LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
    if ( a2 == &v78 )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(SRWLock);
    }
    else
    {
      v43 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 )
      {
        *(_DWORD *)(v43 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v43);
      }
      *(_QWORD *)a2 = SRWLock;
    }
    if ( v23 >= 0 )
      goto LABEL_152;
    v25 = 1667;
    goto LABEL_140;
  }
  v10 = v9 - 16;
  if ( !v10 )
  {
    memset_0(v83, 0, 0x90u);
    v31 = (char *)&SRWLock[6].Ptr + 5;
    if ( ((__int64)v4->Ptr & 0x20) != 0 )
    {
      v32 = *v31;
      HIDWORD(SRWLock[16].Ptr) |= 0x20u;
      BYTE1(SRWLock[17].Ptr) = v32;
      v84 = 1;
      v85 = (unsigned __int8)*v31;
    }
    else
    {
      HIDWORD(SRWLock[16].Ptr) &= ~0x20u;
      BYTE1(SRWLock[17].Ptr) = 0;
    }
    v33 = (__int64)v4->Ptr & 0x20;
    if ( v33 )
      v34 = (unsigned __int8)*v31;
    else
      v34 = 0;
    LODWORD(v71) = v34;
    LOBYTE(v70) = v33 != 0;
    CmTraceProvider::ContainerStateTransition::IoSoftCapComputeSystemJob<bool,int>(v87, &v70, &v71);
    v35 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_DWORD *)(v35 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v35);
      *(_QWORD *)a2 = 0;
    }
    v23 = NtSetInformationJobObject(
            SRWLock[180].Ptr,
            MaxJobObjectInfoClass|JobObjectBasicProcessIdList|0x10,
            v83,
            0x90u);
    AcquireSRWLockExclusive(SRWLock);
    LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
    if ( a2 == &v77 )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(SRWLock);
    }
    else
    {
      v36 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 )
      {
        *(_DWORD *)(v36 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v36);
      }
      *(_QWORD *)a2 = SRWLock;
    }
    if ( v23 == -1073741822 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      goto LABEL_152;
    }
    if ( v23 >= 0 )
      goto LABEL_152;
    v25 = 1734;
LABEL_140:
    v13 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v25,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
            (const char *)(unsigned int)v23,
            v70);
    goto LABEL_141;
  }
  v11 = v10 - 32;
  if ( !v11 )
  {
    v26 = (_DWORD *)&SRWLock[16].Ptr + 1;
    if ( ((__int64)v4->Ptr & 0x40) != 0 )
    {
      v27 = (int)SRWLock[7].Ptr;
      *v26 |= 0x40u;
      v28 = 1;
    }
    else
    {
      v27 = 5;
      *v26 &= ~0x40u;
      v28 = 0;
    }
    LOBYTE(v70) = v28;
    HIDWORD(SRWLock[17].Ptr) = v27;
    LODWORD(v71) = v27;
    CmTraceProvider::ContainerStateTransition::IoPriorityLimitComputeSystemJob<unsigned char &,unsigned long>(
      v87,
      &v70,
      &v71);
    v29 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_DWORD *)(v29 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v29);
      *(_QWORD *)a2 = 0;
    }
    JobInformation = 0;
    if ( v28 )
    {
      LODWORD(JobInformation) = 1;
      HIDWORD(JobInformation) = v27;
    }
    v23 = NtSetInformationJobObject(SRWLock[180].Ptr, (JOBOBJECTINFOCLASS)48, &JobInformation, 8u);
    AcquireSRWLockExclusive(SRWLock);
    LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
    if ( a2 == &v76 )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(SRWLock);
    }
    else
    {
      v30 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 )
      {
        *(_DWORD *)(v30 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v30);
      }
      *(_QWORD *)a2 = SRWLock;
    }
    if ( v23 >= 0 )
      goto LABEL_152;
    v25 = 1793;
    goto LABEL_140;
  }
  v12 = v11 - 64;
  if ( !v12 )
  {
    if ( SLOBYTE(v4->Ptr) >= 0 )
    {
      BYTE1(v70) = 8;
      HIDWORD(SRWLock[16].Ptr) &= ~0x80u;
      LOBYTE(SRWLock[18].Ptr) = 8;
      v21 = 0;
      v20 = 8;
    }
    else
    {
      BYTE1(v70) = BYTE4(SRWLock[7].Ptr);
      v20 = BYTE1(v70);
      HIDWORD(SRWLock[16].Ptr) |= 0x80u;
      LOBYTE(SRWLock[18].Ptr) = BYTE1(v70);
      v21 = 1;
    }
    LOBYTE(v70) = v21;
    CmTraceProvider::ContainerStateTransition::PagePriorityLimitComputeSystemJob<unsigned char &,unsigned char &>(
      v87,
      &v70,
      (char *)&v70 + 1);
    v22 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_DWORD *)(v22 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v22);
      *(_QWORD *)a2 = 0;
    }
    JobInformation = 0;
    if ( v21 )
    {
      LODWORD(JobInformation) = 1;
      HIDWORD(JobInformation) = v20;
    }
    v23 = NtSetInformationJobObject(SRWLock[180].Ptr, (JOBOBJECTINFOCLASS)49, &JobInformation, 8u);
    AcquireSRWLockExclusive(SRWLock);
    LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
    if ( a2 == &v75 )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(SRWLock);
    }
    else
    {
      v24 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 )
      {
        *(_DWORD *)(v24 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v24);
      }
      *(_QWORD *)a2 = SRWLock;
    }
    if ( v23 >= 0 )
      goto LABEL_152;
    v25 = 1852;
    goto LABEL_140;
  }
  if ( v12 != 128 )
  {
    v13 = -2147418113;
    v14 = 1936;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)(unsigned int)v13,
      v70);
    goto LABEL_141;
  }
  if ( ((__int64)v4->Ptr & 0x100) != 0 )
  {
    v15 = BYTE5(SRWLock[7].Ptr);
    BYTE1(v70) = BYTE5(SRWLock[7].Ptr);
    if ( LODWORD(SRWLock[23].Ptr) != 1 )
    {
      v13 = 50;
LABEL_141:
      v87[0] = &CmTraceProvider::ContainerStateTransition::`vftable';
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v87);
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v87);
      return (unsigned int)v13;
    }
    Ptr_high = HIDWORD(SRWLock[57].Ptr);
    if ( v15 < Ptr_high )
      v17 = Ptr_high - v15;
    else
      v17 = Ptr_high > 1;
    HIDWORD(SRWLock[16].Ptr) |= 0x100u;
    BYTE1(SRWLock[18].Ptr) = v15;
  }
  else
  {
    HIDWORD(SRWLock[16].Ptr) &= ~0x100u;
    BYTE1(SRWLock[18].Ptr) = 0;
    BYTE1(v70) = 0;
    v17 = 0;
  }
  LODWORD(v71) = v17;
  LOBYTE(v70) = BYTE1(LODWORD(v4->Ptr)) & 1;
  CmTraceProvider::ContainerStateTransition::ParkComputeSystemCores<bool,unsigned char &,unsigned long &>(
    v87,
    &v70,
    (char *)&v70 + 1,
    &v71);
  v18 = *(_QWORD *)a2;
  if ( *(_QWORD *)a2 )
  {
    *(_DWORD *)(v18 + 8) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v18);
    *(_QWORD *)a2 = 0;
  }
  v13 = Container::Manager::Hcs::ComputeSystem::ParkCores(
          (Container::Manager::Hcs::ComputeSystem *)SRWLock[20].Ptr,
          v17);
  AcquireSRWLockExclusive(SRWLock);
  LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
  if ( a2 == &v74 )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(SRWLock);
  }
  else
  {
    v19 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_DWORD *)(v19 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v19);
    }
    *(_QWORD *)a2 = SRWLock;
  }
  if ( v13 < 0 )
  {
    v14 = 1929;
    goto LABEL_28;
  }
LABEL_152:
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v87, 0);
  v87[0] = &CmTraceProvider::ContainerStateTransition::`vftable';
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v87);
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v87);
  return 0;
}

```

## disassembly

```asm
0x1800f75dc  mov     [rsp-8+arg_10], rbx
0x1800f75e1  push    rbp
0x1800f75e2  push    rsi
0x1800f75e3  push    rdi
0x1800f75e4  push    r12
0x1800f75e6  push    r13
0x1800f75e8  push    r14
0x1800f75ea  push    r15
0x1800f75ec  lea     rbp, [rsp-190h]
0x1800f75f4  sub     rsp, 290h
0x1800f75fb  mov     rax, cs:__security_cookie
0x1800f7602  xor     rax, rsp
0x1800f7605  mov     [rbp+1C0h+var_40], rax
0x1800f760c  mov     rsi, rdx
0x1800f760f  mov     rdi, rcx
0x1800f7612  lea     rdx, aContainerstate; "ContainerStateTransition"
0x1800f7619  lea     rcx, [rbp+1C0h+var_190]
0x1800f761d  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800f7622  lea     r13, ??_7ContainerStateTransition@CmTraceProvider@@6B@; const CmTraceProvider::ContainerStateTransition::`vftable'
0x1800f7629  mov     [rbp+1C0h+var_190], r13
0x1800f762d  lea     rdx, [rdi+0A8h]; struct _GUID *
0x1800f7634  lea     rcx, [rbp+1C0h+var_190]; this
0x1800f7638  call    ?StartActivity@ContainerStateTransition@CmTraceProvider@@QEAAXAEBU_GUID@@@Z; CmTraceProvider::ContainerStateTransition::StartActivity(_GUID const &)
0x1800f763d  nop
0x1800f763e  lea     r14, [rdi+30h]
0x1800f7642  lea     rcx, [rdi+14h]
0x1800f7646  mov     rdx, r14
0x1800f7649  call    ?SelectSingleStepQosStateTransition@Details@Core@Manager@Container@@YA?AW4ComputeSystemQosPolicy@1234@AEBVComputeSystemQosState@1234@0@Z; Container::Manager::Core::Details::SelectSingleStepQosStateTransition(Container::Manager::Core::Details::ComputeSystemQosState const &,Container::Manager::Core::Details::ComputeSystemQosState const &)
0x1800f764e  sub     eax, 1
0x1800f7651  jz      loc_1800F80AA
0x1800f7657  sub     eax, 1
0x1800f765a  jz      loc_1800F7F65
0x1800f7660  sub     eax, 2
0x1800f7663  jz      loc_1800F7E44
0x1800f7669  sub     eax, 4
0x1800f766c  mov     r15d, 8
0x1800f7672  jz      loc_1800F7D34
0x1800f7678  sub     eax, r15d
0x1800f767b  jz      loc_1800F7B3F
0x1800f7681  sub     eax, 10h
0x1800f7684  jz      loc_1800F7A0E
0x1800f768a  sub     eax, 20h ; ' '
0x1800f768d  jz      loc_1800F7909
0x1800f7693  sub     eax, 40h ; '@'
0x1800f7696  jz      loc_1800F77F2
0x1800f769c  cmp     eax, 80h
0x1800f76a1  jz      short loc_1800F76B3
0x1800f76a3  mov     r14d, 8000FFFFh
0x1800f76a9  mov     edx, 790h
0x1800f76ae  jmp     loc_1800F77D7
0x1800f76b3  mov     r8d, 100h
0x1800f76b9  test    [r14], r8d
0x1800f76bc  jz      short loc_1800F7707
0x1800f76be  movzx   eax, byte ptr [rdi+3Dh]
0x1800f76c2  mov     byte ptr [rsp+2C0h+var_2A0+1], al
0x1800f76c6  cmp     dword ptr [rdi+0B8h], 1
0x1800f76cd  jz      short loc_1800F76DA
0x1800f76cf  mov     r14d, 32h ; '2'
0x1800f76d5  jmp     loc_1800F808C
0x1800f76da  mov     ecx, [rdi+1CCh]
0x1800f76e0  xor     ebx, ebx
0x1800f76e2  cmp     eax, ecx
0x1800f76e4  jb      short loc_1800F76F2
0x1800f76e6  mov     r15d, ebx
0x1800f76e9  cmp     ecx, 1
0x1800f76ec  setnbe  r15b
0x1800f76f0  jmp     short loc_1800F76F8
0x1800f76f2  mov     r15d, ecx
0x1800f76f5  sub     r15d, eax
0x1800f76f8  or      [rdi+84h], r8d
0x1800f76ff  mov     [rdi+91h], al
0x1800f7705  jmp     short loc_1800F771E
0x1800f7707  btr     dword ptr [rdi+84h], 8
0x1800f770f  xor     ebx, ebx
0x1800f7711  mov     [rdi+91h], bl
0x1800f7717  mov     byte ptr [rsp+2C0h+var_2A0+1], bl
0x1800f771b  mov     r15d, ebx
0x1800f771e  mov     dword ptr [rsp+2C0h+var_298], r15d
0x1800f7723  mov     eax, [r14]
0x1800f7726  shr     eax, 8
0x1800f7729  and     al, 1
0x1800f772b  mov     byte ptr [rsp+2C0h+var_2A0], al; int
0x1800f772f  lea     r9, [rsp+2C0h+var_298]
0x1800f7734  lea     r8, [rsp+2C0h+var_2A0+1]
0x1800f7739  lea     rdx, [rsp+2C0h+var_2A0]
0x1800f773e  lea     rcx, [rbp+1C0h+var_190]
0x1800f7742  call    ??$ParkComputeSystemCores@_NAEAEAEAK@ContainerStateTransition@CmTraceProvider@@QEAAX$$QEA_NAEAEAEAK@Z; CmTraceProvider::ContainerStateTransition::ParkComputeSystemCores<bool,uchar &,ulong &>(bool &&,uchar &,ulong &)
0x1800f7747  mov     rcx, [rsi]; SRWLock
0x1800f774a  test    rcx, rcx
0x1800f774d  jz      short loc_1800F7761
0x1800f774f  mov     [rcx+8], ebx
0x1800f7752  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f7759  nop     dword ptr [rax+rax+00h]
0x1800f775e  mov     [rsi], rbx
0x1800f7761  mov     edx, r15d; unsigned int
0x1800f7764  mov     rcx, [rdi+0A0h]; this
0x1800f776b  call    ?ParkCores@ComputeSystem@Hcs@Manager@Container@@QEAAJI@Z; Container::Manager::Hcs::ComputeSystem::ParkCores(uint)
0x1800f7770  mov     r14d, eax
0x1800f7773  mov     rcx, rdi; SRWLock
0x1800f7776  call    cs:__imp_AcquireSRWLockExclusive
0x1800f777d  nop     dword ptr [rax+rax+00h]
0x1800f7782  call    cs:__imp_GetCurrentThreadId
0x1800f7789  nop     dword ptr [rax+rax+00h]
0x1800f778e  mov     [rdi+8], eax
0x1800f7791  lea     rax, [rsp+2C0h+var_280]
0x1800f7796  cmp     rsi, rax
0x1800f7799  jz      short loc_1800F77B7
0x1800f779b  mov     rcx, [rsi]; SRWLock
0x1800f779e  test    rcx, rcx
0x1800f77a1  jz      short loc_1800F77B2
0x1800f77a3  mov     [rcx+8], ebx
0x1800f77a6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f77ad  nop     dword ptr [rax+rax+00h]
0x1800f77b2  mov     [rsi], rdi
0x1800f77b5  jmp     short loc_1800F77C9
0x1800f77b7  mov     [rdi+8], ebx
0x1800f77ba  mov     rcx, rdi; SRWLock
0x1800f77bd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f77c4  nop     dword ptr [rax+rax+00h]
0x1800f77c9  test    r14d, r14d
0x1800f77cc  jns     loc_1800F818A
0x1800f77d2  mov     edx, 789h; void *
0x1800f77d7  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f77de  mov     r9d, r14d; char *
0x1800f77e1  mov     rcx, [rbp+1C8h]; this
0x1800f77e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f77ed  jmp     loc_1800F808C
0x1800f77f2  xor     ebx, ebx
0x1800f77f4  test    byte ptr [r14], 80h
0x1800f77f8  jz      short loc_1800F7817
0x1800f77fa  mov     r14b, [rdi+3Ch]
0x1800f77fe  mov     byte ptr [rsp+2C0h+var_2A0+1], r14b
0x1800f7803  bts     dword ptr [rdi+84h], 7
0x1800f780b  mov     [rdi+90h], r14b
0x1800f7812  mov     r12b, 1
0x1800f7815  jmp     short loc_1800F7831
0x1800f7817  mov     byte ptr [rsp+2C0h+var_2A0+1], r15b
0x1800f781c  btr     dword ptr [rdi+84h], 7
0x1800f7824  mov     [rdi+90h], r15b
0x1800f782b  mov     r12b, bl
0x1800f782e  mov     r14b, r15b
0x1800f7831  mov     byte ptr [rsp+2C0h+var_2A0], r12b
0x1800f7836  lea     r8, [rsp+2C0h+var_2A0+1]
0x1800f783b  lea     rdx, [rsp+2C0h+var_2A0]
0x1800f7840  lea     rcx, [rbp+1C0h+var_190]
0x1800f7844  call    ??$PagePriorityLimitComputeSystemJob@AEAEAEAE@ContainerStateTransition@CmTraceProvider@@QEAAXAEAE0@Z; CmTraceProvider::ContainerStateTransition::PagePriorityLimitComputeSystemJob<uchar &,uchar &>(uchar &,uchar &)
0x1800f7849  mov     rcx, [rsi]; SRWLock
0x1800f784c  test    rcx, rcx
0x1800f784f  jz      short loc_1800F7863
0x1800f7851  mov     [rcx+8], ebx
0x1800f7854  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f785b  nop     dword ptr [rax+rax+00h]
0x1800f7860  mov     [rsi], rbx
0x1800f7863  mov     [rsp+2C0h+JobInformation], rbx
0x1800f7868  test    r12b, r12b
0x1800f786b  jz      short loc_1800F787D
0x1800f786d  mov     dword ptr [rsp+2C0h+JobInformation], 1
0x1800f7875  movzx   eax, r14b
0x1800f7879  mov     dword ptr [rsp+2C0h+JobInformation+4], eax
0x1800f787d  mov     r9d, r15d; JobInformationLength
0x1800f7880  lea     r8, [rsp+2C0h+JobInformation]; JobInformation
0x1800f7885  mov     edx, 31h ; '1'; JobInformationClass
0x1800f788a  mov     rcx, [rdi+5A0h]; JobHandle
0x1800f7891  call    cs:__imp_NtSetInformationJobObject
0x1800f7898  nop     dword ptr [rax+rax+00h]
0x1800f789d  mov     r14d, eax
0x1800f78a0  mov     rcx, rdi; SRWLock
0x1800f78a3  call    cs:__imp_AcquireSRWLockExclusive
0x1800f78aa  nop     dword ptr [rax+rax+00h]
0x1800f78af  call    cs:__imp_GetCurrentThreadId
0x1800f78b6  nop     dword ptr [rax+rax+00h]
0x1800f78bb  mov     [rdi+8], eax
0x1800f78be  lea     rax, [rsp+2C0h+var_278]
0x1800f78c3  cmp     rsi, rax
0x1800f78c6  jz      short loc_1800F78E4
0x1800f78c8  mov     rcx, [rsi]; SRWLock
0x1800f78cb  test    rcx, rcx
0x1800f78ce  jz      short loc_1800F78DF
0x1800f78d0  mov     [rcx+8], ebx
0x1800f78d3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f78da  nop     dword ptr [rax+rax+00h]
0x1800f78df  mov     [rsi], rdi
0x1800f78e2  jmp     short loc_1800F78F6
0x1800f78e4  mov     [rdi+8], ebx
0x1800f78e7  mov     rcx, rdi; SRWLock
0x1800f78ea  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f78f1  nop     dword ptr [rax+rax+00h]
0x1800f78f6  test    r14d, r14d
0x1800f78f9  jns     loc_1800F818A
0x1800f78ff  mov     edx, 73Ch
0x1800f7904  jmp     loc_1800F8073
0x1800f7909  lea     rax, [rdi+84h]
0x1800f7910  xor     ebx, ebx
0x1800f7912  test    byte ptr [r14], 40h
0x1800f7916  jz      short loc_1800F7924
0x1800f7918  mov     r12d, [rdi+38h]
0x1800f791c  or      dword ptr [rax], 40h
0x1800f791f  mov     r14b, 1
0x1800f7922  jmp     short loc_1800F7930
0x1800f7924  mov     r12d, 5
0x1800f792a  and     dword ptr [rax], 0FFFFFFBFh
0x1800f792d  mov     r14b, bl
0x1800f7930  mov     byte ptr [rsp+2C0h+var_2A0], r14b
0x1800f7935  mov     [rax+8], r12d
0x1800f7939  mov     dword ptr [rsp+2C0h+var_298], r12d
0x1800f793e  lea     r8, [rsp+2C0h+var_298]
0x1800f7943  lea     rdx, [rsp+2C0h+var_2A0]
0x1800f7948  lea     rcx, [rbp+1C0h+var_190]
0x1800f794c  call    ??$IoPriorityLimitComputeSystemJob@AEAEK@ContainerStateTransition@CmTraceProvider@@QEAAXAEAE$$QEAK@Z; CmTraceProvider::ContainerStateTransition::IoPriorityLimitComputeSystemJob<uchar &,ulong>(uchar &,ulong &&)
0x1800f7951  mov     rcx, [rsi]; SRWLock
0x1800f7954  test    rcx, rcx
0x1800f7957  jz      short loc_1800F796B
0x1800f7959  mov     [rcx+8], ebx
0x1800f795c  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f7963  nop     dword ptr [rax+rax+00h]
0x1800f7968  mov     [rsi], rbx
0x1800f796b  mov     [rsp+2C0h+JobInformation], rbx
0x1800f7970  test    r14b, r14b
0x1800f7973  jz      short loc_1800F7982
0x1800f7975  mov     dword ptr [rsp+2C0h+JobInformation], 1
0x1800f797d  mov     dword ptr [rsp+2C0h+JobInformation+4], r12d
0x1800f7982  mov     r9d, r15d; JobInformationLength
0x1800f7985  lea     r8, [rsp+2C0h+JobInformation]; JobInformation
0x1800f798a  mov     edx, 30h ; '0'; JobInformationClass
0x1800f798f  mov     rcx, [rdi+5A0h]; JobHandle
0x1800f7996  call    cs:__imp_NtSetInformationJobObject
0x1800f799d  nop     dword ptr [rax+rax+00h]
0x1800f79a2  mov     r14d, eax
0x1800f79a5  mov     rcx, rdi; SRWLock
0x1800f79a8  call    cs:__imp_AcquireSRWLockExclusive
0x1800f79af  nop     dword ptr [rax+rax+00h]
0x1800f79b4  call    cs:__imp_GetCurrentThreadId
0x1800f79bb  nop     dword ptr [rax+rax+00h]
0x1800f79c0  mov     [rdi+8], eax
0x1800f79c3  lea     rax, [rsp+2C0h+var_270]
0x1800f79c8  cmp     rsi, rax
0x1800f79cb  jz      short loc_1800F79E9
0x1800f79cd  mov     rcx, [rsi]; SRWLock
0x1800f79d0  test    rcx, rcx
0x1800f79d3  jz      short loc_1800F79E4
0x1800f79d5  mov     [rcx+8], ebx
0x1800f79d8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f79df  nop     dword ptr [rax+rax+00h]
0x1800f79e4  mov     [rsi], rdi
0x1800f79e7  jmp     short loc_1800F79FB
0x1800f79e9  mov     [rdi+8], ebx
0x1800f79ec  mov     rcx, rdi; SRWLock
0x1800f79ef  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f79f6  nop     dword ptr [rax+rax+00h]
0x1800f79fb  test    r14d, r14d
0x1800f79fe  jns     loc_1800F818A
0x1800f7a04  mov     edx, 701h
0x1800f7a09  jmp     loc_1800F8073
0x1800f7a0e  mov     r15d, 90h
0x1800f7a14  mov     r8d, r15d; Size
0x1800f7a17  xor     edx, edx; Val
0x1800f7a19  lea     rcx, [rbp+1C0h+var_230]; void *
0x1800f7a1d  call    memset_0
0x1800f7a22  xor     ebx, ebx
0x1800f7a24  lea     rcx, [rdi+35h]
0x1800f7a28  test    byte ptr [r14], 20h
0x1800f7a2c  jz      short loc_1800F7A4D
0x1800f7a2e  mov     al, [rcx]
0x1800f7a30  or      dword ptr [rdi+84h], 20h
0x1800f7a37  mov     [rdi+89h], al
0x1800f7a3d  mov     [rbp+1C0h+var_20C], 1
0x1800f7a44  movzx   eax, byte ptr [rcx]
0x1800f7a47  mov     [rbp+1C0h+var_1C0], rax
0x1800f7a4b  jmp     short loc_1800F7A5A
0x1800f7a4d  and     dword ptr [rdi+84h], 0FFFFFFDFh
0x1800f7a54  mov     [rdi+89h], bl
0x1800f7a5a  mov     eax, [r14]
0x1800f7a5d  and     eax, 20h
0x1800f7a60  jz      short loc_1800F7A67
0x1800f7a62  movzx   edx, byte ptr [rcx]
0x1800f7a65  jmp     short loc_1800F7A69
0x1800f7a67  mov     edx, ebx
0x1800f7a69  mov     dword ptr [rsp+2C0h+var_298], edx
0x1800f7a6d  test    eax, eax
0x1800f7a6f  setnz   byte ptr [rsp+2C0h+var_2A0]
0x1800f7a74  lea     r8, [rsp+2C0h+var_298]
0x1800f7a79  lea     rdx, [rsp+2C0h+var_2A0]
0x1800f7a7e  lea     rcx, [rbp+1C0h+var_190]
0x1800f7a82  call    ??$IoSoftCapComputeSystemJob@_NH@ContainerStateTransition@CmTraceProvider@@QEAAX$$QEA_N$$QEAH@Z; CmTraceProvider::ContainerStateTransition::IoSoftCapComputeSystemJob<bool,int>(bool &&,int &&)
0x1800f7a87  mov     rcx, [rsi]; SRWLock
0x1800f7a8a  test    rcx, rcx
0x1800f7a8d  jz      short loc_1800F7AA1
0x1800f7a8f  mov     [rcx+8], ebx
0x1800f7a92  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f7a99  nop     dword ptr [rax+rax+00h]
0x1800f7a9e  mov     [rsi], rbx
0x1800f7aa1  mov     r9d, r15d; JobInformationLength
0x1800f7aa4  lea     r8, [rbp+1C0h+var_230]; JobInformation
0x1800f7aa8  mov     edx, 1Fh; JobInformationClass
0x1800f7aad  mov     rcx, [rdi+5A0h]; JobHandle
0x1800f7ab4  call    cs:__imp_NtSetInformationJobObject
0x1800f7abb  nop     dword ptr [rax+rax+00h]
0x1800f7ac0  mov     r14d, eax
0x1800f7ac3  mov     rcx, rdi; SRWLock
0x1800f7ac6  call    cs:__imp_AcquireSRWLockExclusive
  ... truncated ...
```
