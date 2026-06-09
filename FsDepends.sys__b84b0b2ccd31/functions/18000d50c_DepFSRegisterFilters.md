# DepFSRegisterFilters

- ea: `0x18000d50c`
- end: `0x18000d9c3`
- name: `DepFSRegisterFilters`
- size: `1207`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT Driver)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000db70`

## callees

- `0x180001020`
- `0x180001150`
- `0x180001c34`
- `0x180001f70`
- `0x18000d50c`

## import_xrefs

- `ntoskrnl!PsCreateSystemThread` at `0x18000d97e`
- `ntoskrnl!PsCreateSystemThread` at `0x18000d97e`
- `ntoskrnl!ZwClose` at `0x18000d995`
- `ntoskrnl!ZwClose` at `0x18000d995`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000d80d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000d847`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000d8ef`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000d80d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000d847`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000d8ef`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x18000d76b`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x18000d76b`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000d801`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000d83b`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000d8e3`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000d801`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000d83b`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000d8e3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000d8ad`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000d8ad`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000d89c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000d89c`
- `FLTMGR!FltStartFiltering` at `0x18000d858`
- `FLTMGR!FltStartFiltering` at `0x18000d858`
- `FLTMGR!FltRegisterFilter` at `0x18000d7aa`
- `FLTMGR!FltRegisterFilter` at `0x18000d7aa`
- `FLTMGR!FltUnregisterFilter` at `0x18000d909`
- `FLTMGR!FltUnregisterFilter` at `0x18000d909`

## pseudocode

```c
__int64 __fastcall DepFSRegisterFilters(PDRIVER_OBJECT Driver)
{
  NTSTATUS (__stdcall *FilterUnloadCallback)(FLT_FILTER_UNLOAD_FLAGS); // rcx
  NTSTATUS v3; // edi
  __int64 v4; // r8
  unsigned int started; // eax
  PFLT_FILTER RetFilter; // [rsp+40h] [rbp-C0h] BYREF
  void *ThreadHandle; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  FLT_REGISTRATION Registration; // [rsp+80h] [rbp-80h] BYREF
  __int64 v11; // [rsp+E8h] [rbp-18h]
  int v12; // [rsp+F0h] [rbp-10h] BYREF
  __int64 (__fastcall *v13)(); // [rsp+F8h] [rbp-8h]
  __int64 v14; // [rsp+100h] [rbp+0h]
  int v15; // [rsp+108h] [rbp+8h]
  __int128 v16; // [rsp+110h] [rbp+10h]
  __int64 v17; // [rsp+120h] [rbp+20h]
  __int16 v18; // [rsp+128h] [rbp+28h]
  __int128 v19; // [rsp+12Ah] [rbp+2Ah]
  __int128 v20; // [rsp+13Ah] [rbp+3Ah]
  _BYTE v21[22]; // [rsp+14Ah] [rbp+4Ah] BYREF
  char v22; // [rsp+160h] [rbp+60h] BYREF
  int v23; // [rsp+164h] [rbp+64h]
  __int64 (__fastcall *v24)(); // [rsp+168h] [rbp+68h]
  __int64 (__fastcall *v25)(); // [rsp+170h] [rbp+70h]
  __int64 v26; // [rsp+178h] [rbp+78h]
  char v27; // [rsp+180h] [rbp+80h]
  int v28; // [rsp+184h] [rbp+84h]
  __int64 (__fastcall *v29)(); // [rsp+188h] [rbp+88h]
  __int64 v30; // [rsp+190h] [rbp+90h]
  __int64 v31; // [rsp+198h] [rbp+98h]
  char v32; // [rsp+1A0h] [rbp+A0h]
  int v33; // [rsp+1A4h] [rbp+A4h]
  __int64 (__fastcall *v34)(); // [rsp+1A8h] [rbp+A8h]
  __int64 (__fastcall *v35)(); // [rsp+1B0h] [rbp+B0h]
  __int64 v36; // [rsp+1B8h] [rbp+B8h]
  char v37; // [rsp+1C0h] [rbp+C0h]
  int v38; // [rsp+1C4h] [rbp+C4h]
  __int64 (__fastcall *v39)(); // [rsp+1C8h] [rbp+C8h]
  void *v40; // [rsp+1D0h] [rbp+D0h]
  __int64 v41; // [rsp+1D8h] [rbp+D8h]
  char v42; // [rsp+1E0h] [rbp+E0h]
  int v43; // [rsp+1E4h] [rbp+E4h]
  __int64 (__fastcall *v44)(__int64, __int64); // [rsp+1E8h] [rbp+E8h]
  __int64 (__fastcall *v45)(); // [rsp+1F0h] [rbp+F0h]
  __int64 v46; // [rsp+1F8h] [rbp+F8h]
  char v47; // [rsp+200h] [rbp+100h]
  int v48; // [rsp+204h] [rbp+104h]
  __int64 v49; // [rsp+208h] [rbp+108h]
  __int64 (__fastcall *v50)(); // [rsp+210h] [rbp+110h]
  __int64 v51; // [rsp+218h] [rbp+118h]
  char v52; // [rsp+220h] [rbp+120h]
  _BYTE v53[28]; // [rsp+224h] [rbp+124h] BYREF

  v22 = 13;
  RetFilter = 0;
  v23 = 1;
  v24 = DepFSPreFSControl;
  v27 = 16;
  v25 = DepFSPostFSControl;
  v28 = 1;
  v26 = 0;
  v30 = 0;
  v29 = DepFSPreShutdown;
  v31 = 0;
  v34 = DepFSPrePnp;
  v35 = DepFSPostPnp;
  v36 = 0;
  v39 = DepFSPreVolumeMount;
  v40 = &DepFSPostVolumeMount;
  v41 = 0;
  v44 = DepFSPreCreate;
  v45 = DepFSPostCreate;
  v46 = 0;
  v50 = DepFSPostCleanup;
  v51 = 0;
  v13 = DepFSContextCleanup;
  v17 = 0;
  v18 = -1;
  memset(v21, 0, sizeof(v21));
  Registration.ContextRegistration = (const FLT_CONTEXT_REGISTRATION *)&v12;
  Registration.OperationRegistration = (const FLT_OPERATION_REGISTRATION *)&v22;
  Registration.FilterUnloadCallback = (PFLT_FILTER_UNLOAD_CALLBACK)DepFSUnload;
  Registration.InstanceSetupCallback = (PFLT_INSTANCE_SETUP_CALLBACK)DepFSInstanceSetup;
  memset(v53, 0, sizeof(v53));
  v32 = 27;
  v33 = 1;
  v37 = -19;
  v38 = 1;
  v42 = 0;
  v43 = 5;
  v47 = 18;
  v48 = 5;
  v49 = 0;
  v52 = 0x80;
  v12 = 2;
  v14 = -1;
  v15 = 1666609220;
  v16 = 0;
  *(_DWORD *)&Registration.Size = 33751152;
  v19 = 0;
  Registration.Flags = 8;
  v20 = 0;
  Registration.InstanceQueryTeardownCallback = (PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK)DepFSInstanceQueryTeardown;
  Registration.InstanceTeardownStartCallback = (PFLT_INSTANCE_TEARDOWN_CALLBACK)DepFSInstanceTeardownStart;
  Registration.InstanceTeardownCompleteCallback = (PFLT_INSTANCE_TEARDOWN_CALLBACK)DepFSInstanceTeardownComplete;
  v11 = 0;
  memset(&Registration.GenerateFileNameCallback, 0, 40);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      26,
      WPP_d7b1782a7daa350f3d08b40019c93e7e_Traceguids,
      Driver,
      &Registration);
  }
  if ( FsRtlAreVolumeStartupApplicationsComplete() )
    v47 = 0x80;
  else
    byte_180005199 = 1;
  FilterUnloadCallback = Registration.FilterUnloadCallback;
  if ( byte_180005198 )
    FilterUnloadCallback = 0;
  Registration.FilterUnloadCallback = FilterUnloadCallback;
  v3 = FltRegisterFilter(Driver, &Registration, &RetFilter);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Dqqq(WPP_GLOBAL_Control->AttachedDevice, RetFilter, v4, (unsigned int)v3, Driver, &Registration, RetFilter);
  }
  if ( v3 < 0 )
    goto LABEL_15;
  byte_180005197 = 1;
  Filter = RetFilter;
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
  started = FltStartFiltering(RetFilter);
  v3 = started;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_d7b1782a7daa350f3d08b40019c93e7e_Traceguids, started);
  }
  if ( v3 >= 0 )
  {
    if ( byte_180005199 )
    {
      if ( dword_1800051C4 != 4 )
      {
        *(_QWORD *)&ObjectAttributes.Length = 48;
        *(_QWORD *)&ObjectAttributes.Attributes = 512;
        ThreadHandle = 0;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.ObjectName = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v3 = PsCreateSystemThread(
               &ThreadHandle,
               0x1FFFFFu,
               &ObjectAttributes,
               0,
               0,
               (PKSTART_ROUTINE)DepFSAutochkWaitWorker,
               0);
        if ( v3 >= 0 )
          ZwClose(ThreadHandle);
      }
    }
  }
  else
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    if ( !byte_180005197 )
    {
LABEL_15:
      ExReleaseResourceLite(&Resource);
      KeLeaveCriticalRegion();
      return (unsigned int)v3;
    }
    RetFilter = (PFLT_FILTER)Filter;
    byte_180005197 = 0;
    Filter = 0;
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    if ( RetFilter )
      FltUnregisterFilter(RetFilter);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000d50c  push    rbp
0x18000d50e  push    rbx
0x18000d50f  push    rsi
0x18000d510  push    rdi
0x18000d511  push    r12
0x18000d513  push    r15
0x18000d515  lea     rbp, [rsp-158h]
0x18000d51d  sub     rsp, 258h
0x18000d524  mov     rax, cs:__security_cookie
0x18000d52b  xor     rax, rsp
0x18000d52e  mov     [rbp+180h+var_40], rax
0x18000d535  xor     esi, esi
0x18000d537  mov     [rbp+180h+var_120], 0Dh
0x18000d53b  xorps   xmm0, xmm0
0x18000d53e  mov     [rsp+280h+RetFilter], rsi
0x18000d543  lea     rax, DepFSPreFSControl
0x18000d54a  mov     [rbp+180h+var_11C], 1
0x18000d551  mov     [rbp+180h+var_118], rax
0x18000d555  mov     rbx, rcx
0x18000d558  lea     rax, DepFSPostFSControl
0x18000d55f  mov     [rbp+180h+var_100], 10h
0x18000d566  mov     [rbp+180h+var_110], rax
0x18000d56a  lea     ecx, [rsi+5]
0x18000d56d  xor     eax, eax
0x18000d56f  mov     [rbp+180h+var_FC], 1
0x18000d579  mov     [rbp+180h+var_108], rax
0x18000d57d  lea     r15d, [rsi+2]
0x18000d581  lea     rax, DepFSPreShutdown
0x18000d588  mov     [rbp+180h+var_F0], rsi
0x18000d58f  mov     [rbp+180h+var_F8], rax
0x18000d596  xor     eax, eax
0x18000d598  mov     [rbp+180h+var_E8], rax
0x18000d59f  lea     rax, DepFSPrePnp
0x18000d5a6  mov     [rbp+180h+var_D8], rax
0x18000d5ad  lea     rax, DepFSPostPnp
0x18000d5b4  mov     [rbp+180h+var_D0], rax
0x18000d5bb  xor     eax, eax
0x18000d5bd  mov     [rbp+180h+var_C8], rax
0x18000d5c4  lea     rax, DepFSPreVolumeMount
0x18000d5cb  mov     [rbp+180h+var_B8], rax
0x18000d5d2  lea     rax, DepFSPostVolumeMount
0x18000d5d9  mov     [rbp+180h+var_B0], rax
0x18000d5e0  xor     eax, eax
0x18000d5e2  mov     [rbp+180h+var_A8], rax
0x18000d5e9  lea     rax, DepFSPreCreate
0x18000d5f0  mov     [rbp+180h+var_98], rax
0x18000d5f7  lea     rax, DepFSPostCreate
0x18000d5fe  mov     [rbp+180h+var_90], rax
0x18000d605  xor     eax, eax
0x18000d607  mov     [rbp+180h+var_88], rax
0x18000d60e  lea     rax, DepFSPostCleanup
0x18000d615  mov     [rbp+180h+var_70], rax
0x18000d61c  xor     eax, eax
0x18000d61e  mov     [rbp+180h+var_68], rax
0x18000d625  lea     rax, DepFSContextCleanup
0x18000d62c  mov     [rbp+180h+var_188], rax
0x18000d630  xor     eax, eax
0x18000d632  mov     [rbp+180h+var_160], rax
0x18000d636  mov     eax, 0FFFFh
0x18000d63b  mov     [rbp+180h+var_158], ax
0x18000d63f  xor     eax, eax
0x18000d641  movups  xmmword ptr [rbp+180h+var_136], xmm0
0x18000d645  mov     qword ptr [rbp+180h+var_136+0Eh], rax
0x18000d649  lea     rax, [rbp+180h+var_190]
0x18000d64d  mov     [rbp+180h+Registration.ContextRegistration], rax
0x18000d651  lea     rax, [rbp+180h+var_120]
0x18000d655  mov     [rbp+180h+Registration.OperationRegistration], rax
0x18000d659  lea     rax, DepFSUnload
0x18000d660  mov     [rbp+180h+Registration.FilterUnloadCallback], rax
0x18000d664  lea     rax, DepFSInstanceSetup
0x18000d66b  mov     [rbp+180h+Registration.InstanceSetupCallback], rax
0x18000d66f  lea     rax, DepFSInstanceQueryTeardown
0x18000d676  movups  xmmword ptr [rbp+180h+var_5C], xmm0
0x18000d67d  mov     [rbp+180h+var_E0], 1Bh
0x18000d684  mov     [rbp+180h+var_DC], 1
0x18000d68e  mov     [rbp+180h+var_C0], 0EDh
0x18000d695  mov     [rbp+180h+var_BC], 1
0x18000d69f  mov     [rbp+180h+var_A0], sil
0x18000d6a6  mov     [rbp+180h+var_9C], ecx
0x18000d6ac  mov     [rbp+180h+var_80], 12h
0x18000d6b3  mov     [rbp+180h+var_7C], ecx
0x18000d6b9  mov     [rbp+180h+var_78], rsi
0x18000d6c0  mov     [rbp+180h+var_60], 80h
0x18000d6c7  movups  xmmword ptr [rbp+180h+var_5C+0Ch], xmm0
0x18000d6ce  mov     [rbp+180h+var_190], r15d
0x18000d6d2  mov     [rbp+180h+var_180], 0FFFFFFFFFFFFFFFFh
0x18000d6da  mov     [rbp+180h+var_178], 63567044h
0x18000d6e1  movups  [rbp+180h+var_170], xmm0
0x18000d6e5  mov     dword ptr [rbp+180h+Registration.Size], 2030070h
0x18000d6ec  movups  [rbp+180h+var_156], xmm0
0x18000d6f0  mov     [rbp+180h+Registration.Flags], 8
0x18000d6f7  movups  [rbp+180h+var_146], xmm0
0x18000d6fb  mov     [rbp+180h+Registration.InstanceQueryTeardownCallback], rax
0x18000d6ff  lea     rax, DepFSInstanceTeardownStart
0x18000d706  mov     [rbp+180h+Registration.InstanceTeardownStartCallback], rax
0x18000d70a  lea     rax, DepFSInstanceTeardownComplete
0x18000d711  mov     [rbp+180h+Registration.InstanceTeardownCompleteCallback], rax
0x18000d715  xor     eax, eax
0x18000d717  mov     [rbp+180h+var_198], rax
0x18000d71b  mov     [rbp+180h+Registration.GenerateFileNameCallback], rsi
0x18000d71f  mov     [rbp+180h+Registration.NormalizeNameComponentCallback], rsi
0x18000d723  mov     [rbp+180h+Registration.NormalizeContextCleanupCallback], rsi
0x18000d727  movups  xmmword ptr [rbp+180h+Registration.TransactionNotificationCallback], xmm0
0x18000d72b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d732  lea     r12, WPP_GLOBAL_Control
0x18000d739  cmp     rcx, r12
0x18000d73c  jz      short loc_18000D76B
0x18000d73e  mov     eax, [rcx+2Ch]
0x18000d741  test    r15b, al
0x18000d744  jz      short loc_18000D76B
0x18000d746  cmp     byte ptr [rcx+29h], 4
0x18000d74a  jb      short loc_18000D76B
0x18000d74c  mov     rcx, [rcx+18h]
0x18000d750  lea     rax, [rbp+180h+Registration]
0x18000d754  lea     edx, [rsi+1Ah]
0x18000d757  mov     [rsp+280h+ClientId], rax
0x18000d75c  mov     r9, rbx
0x18000d75f  lea     r8, WPP_d7b1782a7daa350f3d08b40019c93e7e_Traceguids
0x18000d766  call    WPP_SF_qq
0x18000d76b  call    cs:__imp_FsRtlAreVolumeStartupApplicationsComplete
0x18000d772  nop     dword ptr [rax+rax+00h]
0x18000d777  test    al, al
0x18000d779  jz      short loc_18000D784
0x18000d77b  mov     [rbp+180h+var_80], 80h
0x18000d782  jmp     short loc_18000D78B
0x18000d784  mov     cs:byte_180005199, 1
0x18000d78b  mov     rcx, [rbp+180h+Registration.FilterUnloadCallback]
0x18000d78f  lea     r8, [rsp+280h+RetFilter]; RetFilter
0x18000d794  cmp     cs:byte_180005198, sil
0x18000d79b  lea     rdx, [rbp+180h+Registration]; Registration
0x18000d79f  cmovnz  rcx, rsi
0x18000d7a3  mov     [rbp+180h+Registration.FilterUnloadCallback], rcx
0x18000d7a7  mov     rcx, rbx; Driver
0x18000d7aa  call    cs:__imp_FltRegisterFilter
0x18000d7b1  nop     dword ptr [rax+rax+00h]
0x18000d7b6  mov     edi, eax
0x18000d7b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7bf  cmp     rcx, r12
0x18000d7c2  jz      short loc_18000D7F6
0x18000d7c4  mov     edx, [rcx+2Ch]
0x18000d7c7  test    r15b, dl
0x18000d7ca  jz      short loc_18000D7F6
0x18000d7cc  cmp     byte ptr [rcx+29h], 4
0x18000d7d0  jb      short loc_18000D7F6
0x18000d7d2  mov     rdx, [rsp+280h+RetFilter]
0x18000d7d7  lea     rax, [rbp+180h+Registration]
0x18000d7db  mov     rcx, [rcx+18h]
0x18000d7df  mov     r9d, edi
0x18000d7e2  mov     [rsp+280h+StartContext], rdx
0x18000d7e7  mov     [rsp+280h+StartRoutine], rax
0x18000d7ec  mov     [rsp+280h+ClientId], rbx
0x18000d7f1  call    WPP_SF_Dqqq
0x18000d7f6  test    edi, edi
0x18000d7f8  jns     short loc_18000D81E
0x18000d7fa  lea     rcx, Resource; Resource
0x18000d801  call    cs:__imp_ExReleaseResourceLite
0x18000d808  nop     dword ptr [rax+rax+00h]
0x18000d80d  call    cs:__imp_KeLeaveCriticalRegion
0x18000d814  nop     dword ptr [rax+rax+00h]
0x18000d819  jmp     loc_18000D9A1
0x18000d81e  mov     rax, [rsp+280h+RetFilter]
0x18000d823  lea     rbx, Resource
0x18000d82a  mov     rcx, rbx; Resource
0x18000d82d  mov     cs:byte_180005197, 1
0x18000d834  mov     cs:Filter, rax
0x18000d83b  call    cs:__imp_ExReleaseResourceLite
0x18000d842  nop     dword ptr [rax+rax+00h]
0x18000d847  call    cs:__imp_KeLeaveCriticalRegion
0x18000d84e  nop     dword ptr [rax+rax+00h]
0x18000d853  mov     rcx, [rsp+280h+RetFilter]; Filter
0x18000d858  call    cs:__imp_FltStartFiltering
0x18000d85f  nop     dword ptr [rax+rax+00h]
0x18000d864  mov     edi, eax
0x18000d866  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d86d  cmp     rcx, r12
0x18000d870  jz      short loc_18000D898
0x18000d872  mov     edx, [rcx+2Ch]
0x18000d875  test    r15b, dl
0x18000d878  jz      short loc_18000D898
0x18000d87a  cmp     byte ptr [rcx+29h], 4
0x18000d87e  jb      short loc_18000D898
0x18000d880  mov     rcx, [rcx+18h]
0x18000d884  lea     r8, WPP_d7b1782a7daa350f3d08b40019c93e7e_Traceguids
0x18000d88b  mov     edx, 1Ch
0x18000d890  mov     r9d, eax
0x18000d893  call    WPP_SF_D
0x18000d898  test    edi, edi
0x18000d89a  jns     short loc_18000D91A
0x18000d89c  call    cs:__imp_KeEnterCriticalRegion
0x18000d8a3  nop     dword ptr [rax+rax+00h]
0x18000d8a8  mov     dl, 1; Wait
0x18000d8aa  mov     rcx, rbx; Resource
0x18000d8ad  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000d8b4  nop     dword ptr [rax+rax+00h]
0x18000d8b9  cmp     cs:byte_180005197, sil
0x18000d8c0  mov     rcx, rbx; Resource
0x18000d8c3  jz      loc_18000D801
0x18000d8c9  mov     rax, cs:Filter
0x18000d8d0  mov     [rsp+280h+RetFilter], rax
0x18000d8d5  mov     cs:byte_180005197, sil
0x18000d8dc  mov     cs:Filter, rsi
0x18000d8e3  call    cs:__imp_ExReleaseResourceLite
0x18000d8ea  nop     dword ptr [rax+rax+00h]
0x18000d8ef  call    cs:__imp_KeLeaveCriticalRegion
0x18000d8f6  nop     dword ptr [rax+rax+00h]
0x18000d8fb  mov     rcx, [rsp+280h+RetFilter]; Filter
0x18000d900  test    rcx, rcx
0x18000d903  jz      loc_18000D9A1
0x18000d909  call    cs:__imp_FltUnregisterFilter
0x18000d910  nop     dword ptr [rax+rax+00h]
0x18000d915  jmp     loc_18000D9A1
0x18000d91a  cmp     cs:byte_180005199, sil
0x18000d921  jz      short loc_18000D9A1
0x18000d923  cmp     cs:dword_1800051C4, 4
0x18000d92a  jz      short loc_18000D9A1
0x18000d92c  lea     rax, DepFSAutochkWaitWorker
0x18000d933  mov     [rsp+280h+StartContext], rsi; StartContext
0x18000d938  xorps   xmm0, xmm0
0x18000d93b  mov     [rsp+280h+StartRoutine], rax; StartRoutine
0x18000d940  xor     r9d, r9d; ProcessHandle
0x18000d943  mov     [rsp+280h+ClientId], rsi; ClientId
0x18000d948  lea     r8, [rsp+280h+ObjectAttributes]; ObjectAttributes
0x18000d94d  mov     qword ptr [rsp+280h+ObjectAttributes.Length], 30h ; '0'
0x18000d956  mov     edx, 1FFFFFh; DesiredAccess
0x18000d95b  mov     qword ptr [rsp+280h+ObjectAttributes.Attributes], 200h
0x18000d964  lea     rcx, [rsp+280h+ThreadHandle]; ThreadHandle
0x18000d969  mov     [rsp+280h+ThreadHandle], rsi
0x18000d96e  mov     [rsp+280h+ObjectAttributes.RootDirectory], rsi
0x18000d973  mov     [rsp+280h+ObjectAttributes.ObjectName], rsi
0x18000d978  movdqu  xmmword ptr [rsp+280h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d97e  call    cs:__imp_PsCreateSystemThread
0x18000d985  nop     dword ptr [rax+rax+00h]
0x18000d98a  mov     edi, eax
0x18000d98c  test    eax, eax
0x18000d98e  js      short loc_18000D9A1
0x18000d990  mov     rcx, [rsp+280h+ThreadHandle]; Handle
0x18000d995  call    cs:__imp_ZwClose
0x18000d99c  nop     dword ptr [rax+rax+00h]
0x18000d9a1  mov     eax, edi
0x18000d9a3  mov     rcx, [rbp+180h+var_40]
0x18000d9aa  xor     rcx, rsp; StackCookie
0x18000d9ad  call    __security_check_cookie
0x18000d9b2  add     rsp, 258h
0x18000d9b9  pop     r15
0x18000d9bb  pop     r12
0x18000d9bd  pop     rdi
0x18000d9be  pop     rsi
0x18000d9bf  pop     rbx
0x18000d9c0  pop     rbp
0x18000d9c1  retn
```
