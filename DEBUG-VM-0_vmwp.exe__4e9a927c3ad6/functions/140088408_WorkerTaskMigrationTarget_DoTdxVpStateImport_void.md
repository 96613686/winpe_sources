# WorkerTaskMigrationTarget::DoTdxVpStateImport(void)

- ea: `0x140088408`
- end: `0x140088a6b`
- name: `?DoTdxVpStateImport@WorkerTaskMigrationTarget@@AEAAJXZ`
- size: `1635`
- prototype: `__int64 __fastcall(WorkerTaskMigrationTarget *__hidden this)`
- caller_count: `1`
- callee_count: `30`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14008f9b0`

## callees

- `0x14002ecd0`
- `0x140031c88`
- `0x14005348c`
- `0x14005b628`
- `0x14005e7e4`
- `0x14006af38`
- `0x14006fec8`
- `0x14007a72c`
- `0x14007aaa0`
- `0x140081778`
- `0x140088354`
- `0x140088408`
- `0x140089704`
- `0x1400897d8`
- `0x14008b2d4`
- `0x14008f288`
- `0x140090654`
- `0x140090680`
- `0x1400b2708`
- `0x1400c25b0`
- `0x1400c25e0`
- `0x1400ce7c4`
- `0x1400ce884`
- `0x1400fe1bc`
- `0x140132940`
- `0x1401335fc`
- `0x140135935`
- `0x1401dd5f4`
- `0x14021e8ac`
- `0x1402c2010`

## import_xrefs

- `vid!VidTdxImportVpState` at `0x14008891a`
- `vid!VidTdxImportVpState` at `0x14008891a`

## string_xrefs

- `0x14008857c`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140088627`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140088662`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400886eb`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140088726`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400887c2`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008884f`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140088888`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140088932`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140088996`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`

## pseudocode

```c
__int64 __fastcall WorkerTaskMigrationTarget::DoTdxVpStateImport(WorkerTaskMigrationTarget *this)
{
  unsigned __int64 v2; // r15
  char *v3; // r12
  const struct _GUID *v4; // rsi
  const unsigned __int16 *v5; // rdi
  __int64 v6; // rbx
  int v7; // eax
  int v8; // eax
  char *v9; // rbx
  int v10; // eax
  __int64 v11; // rdi
  unsigned __int64 i; // rsi
  _QWORD *v13; // rbx
  char v14; // al
  __int64 v15; // r9
  __int64 v16; // r13
  __int64 v17; // rax
  const char *v18; // r9
  int v19; // eax
  const struct Vml::ExceptionTraceParameters *v20; // r8
  unsigned int v21; // r13d
  const struct _GUID *v22; // rdi
  const unsigned __int16 *v23; // rbx
  int v25; // [rsp+20h] [rbp-3F8h]
  int v26; // [rsp+20h] [rbp-3F8h]
  char *v27; // [rsp+30h] [rbp-3E8h] BYREF
  unsigned __int64 VmName; // [rsp+38h] [rbp-3E0h] BYREF
  __int64 v29; // [rsp+40h] [rbp-3D8h] BYREF
  unsigned __int64 v30; // [rsp+48h] [rbp-3D0h]
  struct _GUID v31; // [rsp+50h] [rbp-3C8h] BYREF
  _BYTE v32[16]; // [rsp+60h] [rbp-3B8h] BYREF
  _BYTE v33[336]; // [rsp+70h] [rbp-3A8h] BYREF
  void *Src[2]; // [rsp+1C0h] [rbp-258h] BYREF
  _BYTE v35[5]; // [rsp+1D0h] [rbp-248h] BYREF
  __int16 v36; // [rsp+1D5h] [rbp-243h]
  char v37; // [rsp+1D7h] [rbp-241h]
  __int64 v38; // [rsp+1D8h] [rbp-240h]
  __int64 v39; // [rsp+1E0h] [rbp-238h]
  char v40; // [rsp+1E8h] [rbp-230h]
  int v41; // [rsp+1E9h] [rbp-22Fh]
  __int16 v42; // [rsp+1EDh] [rbp-22Bh]
  char v43; // [rsp+1EFh] [rbp-229h]
  __int128 v44; // [rsp+1F0h] [rbp-228h] BYREF
  unsigned __int8 *v45[2]; // [rsp+200h] [rbp-218h] BYREF
  __int64 v46; // [rsp+210h] [rbp-208h]
  _BYTE v47[40]; // [rsp+220h] [rbp-1F8h] BYREF
  _BYTE v48[72]; // [rsp+248h] [rbp-1D0h] BYREF
  _QWORD v49[42]; // [rsp+290h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+418h] [rbp+0h]

  LODWORD(v27) = 0;
  v2 = 0;
  v30 = 0;
  v31 = 0;
  v3 = (char *)this + 16;
  v29 = (__int64)this + 16;
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v47,
    (struct Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace,
    (const struct _GUID *)(*((_QWORD *)this + 2) + 1136LL),
    &v31);
  VmName = (unsigned __int64)VirtualMachine::GetVmName((VirtualMachine *)(*(_QWORD *)v3 + 16LL));
  Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
    (Vml::VmPerfTraceOperation *)v47,
    &VMWP_PERF_MIGRATION_TARGET_TDX_START_IMPORT_VP_STATES);
  memset_0(v49, 0, sizeof(v49));
  v4 = *(const struct _GUID **)v3;
  v5 = VirtualMachine::GetVmName((VirtualMachine *)(*(_QWORD *)v3 + 16LL));
  v6 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::TargetMigrationTask>::GetCurrentActivity(this, v33) + 272);
  memset_0(v49, 0, sizeof(v49));
  wil::ActivityBase<VmWorkerTrace,0,262144,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,262144,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v49);
  v49[0] = &VmWorkerTrace::MigrationTransferTdxVpState::`vftable';
  v27 = (char *)2;
  wil::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(v49, v6 + 8);
  VmWorkerTrace::MigrationTransferTdxVpState::StartActivity(
    (VmWorkerTrace::MigrationTransferTdxVpState *)v49,
    v4 + 71,
    v5);
  VmWorkerTrace::TargetMigrationTask::~TargetMigrationTask((VmWorkerTrace::TargetMigrationTask *)v33);
  v7 = VmMigrationConnection::BeginMessageSequence(*((_QWORD *)this + 55), 53);
  try
  {
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD71,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v7,
        v25);
    LODWORD(v27) = 0;
    do
    {
      Src[0] = 0;
      VmName = 0;
      v35[0] = -1;
      *(_DWORD *)&v35[1] = 0;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      v39 = 0;
      v40 = 0;
      v41 = 0;
      v42 = 0;
      v43 = 0;
      v8 = VmMigrationConnection::ReceiveMessage(
             *((VmMigrationConnection **)this + 55),
             (unsigned __int64 *)Src,
             &VmName,
             (int *)&v27,
             (struct _SECURE_MIGRATION_CONTROL_DATA *)v35);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD7D,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v8,
          v26);
      if ( v8 == 294977 )
      {
        LODWORD(v27) = 0;
        if ( !(unsigned int)VmMigrationConnection::GetAsyncSendError(
                              *((VmMigrationConnection **)this + 55),
                              (int *)&v27) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD7E,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)0x8007054FLL,
            v26);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD7E,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v27,
          v26);
      }
      *(_OWORD *)v45 = 0;
      v46 = 0;
      v9 = (char *)Src[0];
      std::vector<enum gsl::byte>::vector<enum gsl::byte>(v45, Src[0]);
      v10 = VmMigrationConnection::ReceiveMessageData(
              *((VmMigrationConnection **)this + 55),
              v45[0],
              (unsigned __int64)v9,
              (struct _SECURE_MIGRATION_CONTROL_DATA *)v35);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD84,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v10,
          v26);
      if ( v10 == 294977 )
      {
        LODWORD(v27) = 0;
        if ( !(unsigned int)VmMigrationConnection::GetAsyncSendError(
                              *((VmMigrationConnection **)this + 55),
                              (int *)&v27) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD85,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)0x8007054FLL,
            v26);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD85,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v27,
          v26);
      }
      v44 = 0;
      gsl::span<unsigned char,-1>::span<unsigned char,-1>(v32, v45);
      gsl::span<enum gsl::byte const,-1>::subspan(v32, &v44, v39, &v9[-v39]);
      v11 = 0;
      for ( i = 0; i < VmName; ++i )
      {
        if ( v11 + 16 > (unsigned __int64)v44 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD8E,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)0x8007000DLL,
            v26);
        *(_OWORD *)Src = 0;
        gsl::span<enum gsl::byte const,-1>::subspan(&v44, Src, v11, 16);
        v13 = Src[1];
        v31 = *(struct _GUID *)Src;
        if ( (unsigned __int64)gsl::span<unsigned char,-1>::size_bytes(&v31) < 0x10 )
        {
          v13 = 0;
        }
        else
        {
          gsl::span<unsigned char,-1>::size_bytes(&v31);
          if ( v13 )
          {
            v14 = 0;
            goto LABEL_26;
          }
        }
        v14 = 1;
LABEL_26:
        if ( v14 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD92,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)0x8000FFFFLL,
            v26);
        v15 = v13[1];
        if ( v11 + v15 + 16 > (unsigned __int64)v44 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD94,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)0x8007000DLL,
            v26);
        *(_OWORD *)Src = 0;
        gsl::span<enum gsl::byte const,-1>::subspan(&v44, Src, v11 + 16, v15);
        memcpy_0(*(void **)(*((_QWORD *)this + 105) + 8LL), Src[1], v13[1]);
        v16 = v13[1];
        Src[0] = *(void **)(*((_QWORD *)this + 105) + 24LL);
        v17 = (**(__int64 (__fastcall ***)(__int64))(*(_QWORD *)(*(_QWORD *)v3 + 1024LL) + 24LL))(*(_QWORD *)(*(_QWORD *)v3 + 1024LL) + 24LL);
        if ( !(unsigned int)VidTdxImportVpState(v17, Src[0], 0, v16) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xDA0,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            v18);
        v11 += v13[1] + 16LL;
        v30 = ++v2;
      }
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v45);
    }
    while ( !(_DWORD)v27 );
    v19 = VmMigrationConnection::AcknowledgeMessageSequence(*((VmMigrationConnection **)this + 55), 0, 0);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDA8,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v19,
        v26);
  }
  catch ( ... )
  {
    HIDWORD(v27) = Vml::GetHResultFromThrownExceptionAndTrace((Vml *)0x41E2, (unsigned __int16)&off_1402DB430, v20);
    v2 = v30;
    v3 = (char *)v29;
  }
  v21 = HIDWORD(v27);
  v22 = *(const struct _GUID **)v3;
  v23 = VirtualMachine::GetVmName((VirtualMachine *)(*(_QWORD *)v3 + 16LL));
  wil::ActivityBase<VmWorkerTrace,0,262144,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(v49, v21);
  VmWorkerTrace::MigrationTransferTdxVpState::Stop((VmWorkerTrace::MigrationTransferTdxVpState *)v49, v22 + 71, v23, v2);
  v29 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(*(_QWORD *)v3 + 16LL));
  Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
    (Vml::VmPerfTraceOperation *)v47,
    &VMWP_PERF_MIGRATION_TARGET_TDX_STOP_IMPORT_VP_STATES,
    (__int64)&v29);
  VmWorkerTrace::MigrationTransferTdxVpState::~MigrationTransferTdxVpState((VmWorkerTrace::MigrationTransferTdxVpState *)v49);
  std::wstring::_Tidy_deallocate(v48);
  return v21;
}

```

## disassembly

```asm
0x140088408  mov     [rsp+arg_8], rbx
0x14008840d  mov     [rsp+arg_10], rsi
0x140088412  push    rdi
0x140088413  push    r12
0x140088415  push    r13
0x140088417  push    r14
0x140088419  push    r15
0x14008841b  sub     rsp, 3F0h
0x140088422  mov     rax, cs:__security_cookie
0x140088429  xor     rax, rsp
0x14008842c  mov     [rsp+418h+var_38], rax
0x140088434  mov     r14, rcx
0x140088437  mov     dword ptr [rsp+418h+var_3E8], 0
0x14008843f  xor     r15d, r15d
0x140088442  mov     [rsp+418h+var_3D0], r15
0x140088447  xorps   xmm0, xmm0
0x14008844a  movups  xmmword ptr [rsp+418h+var_3C8.Data1], xmm0
0x14008844f  lea     r12, [rcx+10h]
0x140088453  mov     [rsp+418h+var_3D8], r12
0x140088458  mov     r8, [r12]
0x14008845c  add     r8, 470h; struct _GUID *
0x140088463  lea     r9, [rsp+418h+var_3C8]; struct _GUID *
0x140088468  lea     rdx, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; struct Vml::VmPerfTraceComponent *
0x14008846f  lea     rcx, [rsp+418h+var_1F8]; this
0x140088477  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x14008847c  nop
0x14008847d  mov     rcx, [r12]
0x140088481  add     rcx, 10h; this
0x140088485  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x14008848a  mov     [rsp+418h+var_3E0], rax
0x14008848f  lea     r8, [rsp+418h+var_3E0]
0x140088494  lea     rdx, VMWP_PERF_MIGRATION_TARGET_TDX_START_IMPORT_VP_STATES; EventDescriptor
0x14008849b  lea     rcx, [rsp+418h+var_1F8]; this
0x1400884a3  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400884a8  mov     r13d, 150h
0x1400884ae  mov     r8d, r13d; Size
0x1400884b1  xor     edx, edx; Val
0x1400884b3  lea     rcx, [rsp+418h+var_188]; void *
0x1400884bb  call    memset_0
0x1400884c0  mov     rsi, [r12]
0x1400884c4  lea     rcx, [rsi+10h]; this
0x1400884c8  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400884cd  mov     rdi, rax
0x1400884d0  lea     rdx, [rsp+418h+var_3A8]
0x1400884d5  mov     rcx, r14
0x1400884d8  call    ?GetCurrentActivity@?$WorkerAsyncTask@VTargetMigrationTask@VmWorkerTrace@@@@IEAA?AVTargetMigrationTask@VmWorkerTrace@@XZ; WorkerAsyncTask<VmWorkerTrace::TargetMigrationTask>::GetCurrentActivity(void)
0x1400884dd  nop
0x1400884de  mov     rbx, [rax+110h]
0x1400884e5  mov     r8d, r13d; Size
0x1400884e8  xor     edx, edx; Val
0x1400884ea  lea     rcx, [rsp+418h+var_188]; void *
0x1400884f2  call    memset_0
0x1400884f7  lea     rdx, aMigrationtrans_6; "MigrationTransferTdxVpState"
0x1400884fe  lea     rcx, [rsp+418h+var_188]; struct wil::details::IFailureCallback *
0x140088506  call    ??0?$ActivityBase@VVmWorkerTrace@@$0A@$0EAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VmWorkerTrace,0,262144,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,262144,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14008850b  lea     rax, ??_7MigrationTransferTdxVpState@VmWorkerTrace@@6B@; const VmWorkerTrace::MigrationTransferTdxVpState::`vftable'
0x140088512  mov     [rsp+418h+var_188], rax
0x14008851a  mov     dword ptr [rsp+418h+var_3E8], 2
0x140088522  lea     rdx, [rbx+8]
0x140088526  lea     rcx, [rsp+418h+var_188]
0x14008852e  call    ?SetRelatedActivityId@?$ActivityBase@VVmWorkerTrace@@$01$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x140088533  lea     rdx, [rsi+470h]; struct _GUID *
0x14008853a  mov     r8, rdi; unsigned __int16 *
0x14008853d  lea     rcx, [rsp+418h+var_188]; this
0x140088545  call    ?StartActivity@MigrationTransferTdxVpState@VmWorkerTrace@@QEAAXAEBU_GUID@@PEBG@Z; VmWorkerTrace::MigrationTransferTdxVpState::StartActivity(_GUID const &,ushort const *)
0x14008854a  nop
0x14008854b  lea     rcx, [rsp+418h+var_3A8]; this
0x140088550  call    ??1TargetMigrationTask@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::TargetMigrationTask::~TargetMigrationTask(void)
0x140088555  xor     r13d, r13d
0x140088558  mov     dword ptr [rsp+418h+var_3E8+4], r13d
0x14008855d  lea     edx, [r15+35h]
0x140088561  mov     rcx, [r14+1B8h]
0x140088568  call    ?BeginMessageSequence@VmMigrationConnection@@QEAAJW4MESSAGE_SEQUENCE_TYPE@1@@Z; VmMigrationConnection::BeginMessageSequence(VmMigrationConnection::MESSAGE_SEQUENCE_TYPE)
0x14008856d  mov     rcx, [rsp+418h]; this
0x140088575  test    eax, eax
0x140088577  jns     short loc_14008858D
0x140088579  mov     r9d, eax; char *
0x14008857c  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x140088583  mov     edx, 0D71h; void *
0x140088588  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008858d  mov     dword ptr [rsp+418h+var_3E8], r13d
0x140088592  mov     [rsp+418h+Src], r13
0x14008859a  mov     [rsp+418h+var_3E0], r13
0x14008859f  mov     [rsp+418h+var_248], 0FFh
0x1400885a7  xor     eax, eax
0x1400885a9  mov     dword ptr [rsp+418h+var_248+1], eax
0x1400885b0  mov     [rsp+418h+var_243], ax
0x1400885b8  mov     [rsp+418h+var_241], al
0x1400885bf  mov     [rsp+418h+var_240], r13
0x1400885c7  mov     [rsp+418h+var_238], r13
0x1400885cf  mov     [rsp+418h+var_230], r13b
0x1400885d7  mov     [rsp+418h+var_22F], eax
0x1400885de  mov     [rsp+418h+var_22B], ax
0x1400885e6  mov     [rsp+418h+var_229], al
0x1400885ed  lea     rax, [rsp+418h+var_248]
0x1400885f5  mov     qword ptr [rsp+418h+var_3F8], rax; int
0x1400885fa  lea     r9, [rsp+418h+var_3E8]; int *
0x1400885ff  lea     r8, [rsp+418h+var_3E0]; unsigned __int64 *
0x140088604  lea     rdx, [rsp+418h+Src]; unsigned __int64 *
0x14008860c  mov     rcx, [r14+1B8h]; this
0x140088613  call    ?ReceiveMessage@VmMigrationConnection@@QEAAJAEA_K0AEAHAEAU_SECURE_MIGRATION_CONTROL_DATA@@@Z; VmMigrationConnection::ReceiveMessage(unsigned __int64 &,unsigned __int64 &,int &,_SECURE_MIGRATION_CONTROL_DATA &)
0x140088618  mov     rcx, [rsp+418h]; this
0x140088620  test    eax, eax
0x140088622  jns     short loc_140088638
0x140088624  mov     r9d, eax; char *
0x140088627  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008862e  mov     edx, 0D7Dh; void *
0x140088633  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140088638  cmp     eax, 48041h
0x14008863d  jnz     short loc_14008868F
0x14008863f  mov     dword ptr [rsp+418h+var_3E8], r13d
0x140088644  lea     rdx, [rsp+418h+var_3E8]; int *
0x140088649  mov     rcx, [r14+1B8h]; this
0x140088650  call    ?GetAsyncSendError@VmMigrationConnection@@QEAAHAEAJ@Z; VmMigrationConnection::GetAsyncSendError(long &)
0x140088655  test    eax, eax
0x140088657  setz    al
0x14008865a  mov     rcx, [rsp+418h]; this
0x140088662  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x140088669  mov     edx, 0D7Eh; void *
0x14008866e  test    al, al
0x140088670  jz      short loc_14008867D
0x140088672  mov     r9d, 8007054Fh; char *
0x140088678  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008867d  mov     rcx, [rsp+418h]; this
0x140088685  mov     r9d, dword ptr [rsp+418h+var_3E8]; char *
0x14008868a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008868f  xorps   xmm0, xmm0
0x140088692  xor     eax, eax
0x140088694  movups  xmmword ptr [rsp+418h+var_218], xmm0
0x14008869c  mov     [rsp+418h+var_208], rax
0x1400886a4  mov     rbx, [rsp+418h+Src]
0x1400886ac  mov     rdx, rbx
0x1400886af  lea     rcx, [rsp+418h+var_218]
0x1400886b7  call    ??0?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,std::allocator<gsl::byte> const &)
0x1400886bc  nop
0x1400886bd  lea     r9, [rsp+418h+var_248]; struct _SECURE_MIGRATION_CONTROL_DATA *
0x1400886c5  mov     r8, rbx; unsigned __int64
0x1400886c8  mov     rdx, [rsp+418h+var_218]; unsigned __int8 *
0x1400886d0  mov     rcx, [r14+1B8h]; this
0x1400886d7  call    ?ReceiveMessageData@VmMigrationConnection@@QEAAJPEAE_KAEAU_SECURE_MIGRATION_CONTROL_DATA@@@Z; VmMigrationConnection::ReceiveMessageData(uchar *,unsigned __int64,_SECURE_MIGRATION_CONTROL_DATA &)
0x1400886dc  mov     rcx, [rsp+418h]; this
0x1400886e4  test    eax, eax
0x1400886e6  jns     short loc_1400886FC
0x1400886e8  mov     r9d, eax; char *
0x1400886eb  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400886f2  mov     edx, 0D84h; void *
0x1400886f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400886fc  cmp     eax, 48041h
0x140088701  jnz     short loc_140088753
0x140088703  mov     dword ptr [rsp+418h+var_3E8], r13d
0x140088708  lea     rdx, [rsp+418h+var_3E8]; int *
0x14008870d  mov     rcx, [r14+1B8h]; this
0x140088714  call    ?GetAsyncSendError@VmMigrationConnection@@QEAAHAEAJ@Z; VmMigrationConnection::GetAsyncSendError(long &)
0x140088719  test    eax, eax
0x14008871b  setz    al
0x14008871e  mov     rcx, [rsp+418h]; this
0x140088726  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008872d  mov     edx, 0D85h; void *
0x140088732  test    al, al
0x140088734  jz      short loc_140088741
0x140088736  mov     r9d, 8007054Fh; char *
0x14008873c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140088741  mov     rcx, [rsp+418h]; this
0x140088749  mov     r9d, dword ptr [rsp+418h+var_3E8]; char *
0x14008874e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140088753  xorps   xmm0, xmm0
0x140088756  movups  [rsp+418h+var_228], xmm0
0x14008875e  lea     rdx, [rsp+418h+var_218]
0x140088766  lea     rcx, [rsp+418h+var_3B8]
0x14008876b  call    ??$?0$0?0V?$vector@EV?$allocator@E@std@@@std@@$0A@@?$span@E$0?0@gsl@@QEAA@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; gsl::span<uchar,-1>::span<uchar,-1>(std::vector<uchar> &)
0x140088770  mov     r8, [rsp+418h+var_238]
0x140088778  sub     rbx, r8
0x14008877b  mov     r9, rbx
0x14008877e  lea     rdx, [rsp+418h+var_228]
0x140088786  lea     rcx, [rsp+418h+var_3B8]
0x14008878b  call    ?subspan@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<gsl::byte const,-1>::subspan(unsigned __int64,unsigned __int64)
0x140088790  mov     rdi, r13
0x140088793  mov     rsi, r13
0x140088796  cmp     rsi, [rsp+418h+var_3E0]
0x14008879b  jnb     loc_14008895B
0x1400887a1  lea     r13, [rdi+10h]
0x1400887a5  cmp     r13, qword ptr [rsp+418h+var_228]
0x1400887ad  setnbe  al
0x1400887b0  mov     rcx, [rsp+418h]; this
0x1400887b8  test    al, al
0x1400887ba  jz      short loc_1400887D3
0x1400887bc  mov     r9d, 8007000Dh; char *
0x1400887c2  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400887c9  mov     edx, 0D8Eh; void *
0x1400887ce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400887d3  xorps   xmm0, xmm0
0x1400887d6  movups  xmmword ptr [rsp+418h+Src], xmm0
0x1400887de  mov     r9d, 10h
0x1400887e4  mov     r8, rdi
0x1400887e7  lea     rdx, [rsp+418h+Src]
0x1400887ef  lea     rcx, [rsp+418h+var_228]
0x1400887f7  call    ?subspan@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<gsl::byte const,-1>::subspan(unsigned __int64,unsigned __int64)
0x1400887fc  mov     rbx, [rsp+418h+Src+8]
0x140088804  mov     rax, [rsp+418h+Src]
0x14008880c  mov     qword ptr [rsp+418h+var_3C8.Data1], rax
0x140088811  mov     qword ptr [rsp+418h+var_3C8.Data4], rbx
0x140088816  lea     rcx, [rsp+418h+var_3C8]
0x14008881b  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140088820  cmp     rax, 10h
0x140088824  jb      short loc_140088839
0x140088826  lea     rcx, [rsp+418h+var_3C8]
0x14008882b  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140088830  test    rbx, rbx
0x140088833  jz      short loc_14008883B
0x140088835  xor     al, al
0x140088837  jmp     short loc_14008883D
0x140088839  xor     ebx, ebx
0x14008883b  mov     al, 1
0x14008883d  mov     rcx, [rsp+418h]; this
0x140088845  test    al, al
0x140088847  jz      short loc_140088860
0x140088849  mov     r9d, 8000FFFFh; char *
0x14008884f  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x140088856  mov     edx, 0D92h; void *
0x14008885b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140088860  mov     r9, [rbx+8]
0x140088864  lea     rax, [r9+10h]
0x140088868  add     rax, rdi
0x14008886b  cmp     rax, qword ptr [rsp+418h+var_228]
0x140088873  setnbe  al
0x140088876  mov     rcx, [rsp+418h]; this
0x14008887e  test    al, al
0x140088880  jz      short loc_140088899
0x140088882  mov     r9d, 8007000Dh; char *
0x140088888  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008888f  mov     edx, 0D94h; void *
0x140088894  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140088899  xorps   xmm0, xmm0
0x14008889c  movups  xmmword ptr [rsp+418h+Src], xmm0
0x1400888a4  mov     r8, r13
0x1400888a7  lea     rdx, [rsp+418h+Src]
0x1400888af  lea     rcx, [rsp+418h+var_228]
0x1400888b7  call    ?subspan@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<gsl::byte const,-1>::subspan(unsigned __int64,unsigned __int64)
0x1400888bc  mov     rcx, [r14+348h]
0x1400888c3  mov     r8, [rbx+8]; Size
0x1400888c7  mov     rdx, [rsp+418h+Src+8]; Src
0x1400888cf  mov     rcx, [rcx+8]; void *
0x1400888d3  call    memcpy_0
0x1400888d8  mov     r13, [rbx+8]
0x1400888dc  mov     rax, [r14+348h]
0x1400888e3  mov     rax, [rax+18h]
0x1400888e7  mov     [rsp+418h+Src], rax
0x1400888ef  mov     rax, [r12]
0x1400888f3  mov     rcx, [rax+400h]
0x1400888fa  add     rcx, 18h
0x1400888fe  mov     rax, [rcx]
0x140088901  mov     rax, [rax]
0x140088904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140088909  xor     r8d, r8d
0x14008890c  mov     r9, r13
0x14008890f  mov     rdx, [rsp+418h+Src]
0x140088917  mov     rcx, rax
0x14008891a  call    cs:__imp_VidTdxImportVpState
0x140088921  nop     dword ptr [rax+rax+00h]
0x140088926  mov     rcx, [rsp+418h]; this
0x14008892e  test    eax, eax
0x140088930  jnz     short loc_140088943
0x140088932  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x140088939  mov     edx, 0DA0h; void *
0x14008893e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140088943  add     rdi, 10h
0x140088947  add     rdi, [rbx+8]
0x14008894b  inc     r15
0x14008894e  mov     [rsp+418h+var_3D0], r15
0x140088953  inc     rsi
0x140088956  jmp     loc_140088796
0x14008895b  lea     rcx, [rsp+418h+var_218]
0x140088963  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140088968  xor     r13d, r13d
0x14008896b  cmp     dword ptr [rsp+418h+var_3E8], r13d
0x140088970  jz      loc_140088592
0x140088976  xor     r8d, r8d; unsigned __int64
0x140088979  xor     edx, edx; struct VmMigrationNetworkBuffer *
0x14008897b  mov     rcx, [r14+1B8h]; this
0x140088982  call    ?AcknowledgeMessageSequence@VmMigrationConnection@@QEAAJPEBVVmMigrationNetworkBuffer@@_K@Z; VmMigrationConnection::AcknowledgeMessageSequence(VmMigrationNetworkBuffer const *,unsigned __int64)
0x140088987  mov     rcx, [rsp+418h]; this
0x14008898f  test    eax, eax
0x140088991  jns     short loc_1400889A8
0x140088993  mov     r9d, eax; char *
0x140088996  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008899d  mov     edx, 0DA8h; void *
0x1400889a2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400889a8  jmp     short loc_1400889B4
0x1400889aa  mov     r15, [rsp+418h+var_3D0]
0x1400889af  mov     r12, [rsp+418h+var_3D8]
0x1400889b4  mov     r13d, dword ptr [rsp+418h+var_3E8+4]
0x1400889b9  mov     rdi, [r12]
0x1400889bd  lea     rcx, [rdi+10h]; this
0x1400889c1  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400889c6  mov     rbx, rax
0x1400889c9  mov     edx, r13d
0x1400889cc  lea     rcx, [rsp+418h+var_188]
0x1400889d4  call    ?SetStopResult@?$ActivityBase@VVmWorkerTrace@@$0A@$0EAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<VmWorkerTrace,0,262144,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1400889d9  lea     rdx, [rdi+470h]; struct _GUID *
0x1400889e0  mov     r9, r15; unsigned __int64
  ... truncated ...
```
