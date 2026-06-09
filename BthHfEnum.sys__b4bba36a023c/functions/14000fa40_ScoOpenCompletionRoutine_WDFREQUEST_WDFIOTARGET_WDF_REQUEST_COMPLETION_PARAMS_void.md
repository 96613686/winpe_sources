# ScoOpenCompletionRoutine(WDFREQUEST__ *,WDFIOTARGET__ *,_WDF_REQUEST_COMPLETION_PARAMS *,void *)

- ea: `0x14000fa40`
- end: `0x14000ff1a`
- name: `?ScoOpenCompletionRoutine@@YAXPEAUWDFREQUEST__@@PEAUWDFIOTARGET__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@PEAX@Z`
- size: `1242`
- prototype: `void(struct WDFREQUEST__ *, struct WDFIOTARGET__ *, struct _WDF_REQUEST_COMPLETION_PARAMS *, void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400041d0`
- `0x140004810`
- `0x14000498c`
- `0x14000c570`
- `0x14000cb40`
- `0x14000dcf0`
- `0x14000f700`
- `0x14000f9e0`
- `0x14000fa40`
- `0x1400112c4`
- `0x140011484`
- `0x140012100`
- `0x14001ae00`
- `0x14002eacc`

## import_xrefs

- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x14000fd5b`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x14000fd5b`

## pseudocode

```c
void __fastcall ScoOpenCompletionRoutine(
        struct WDFREQUEST__ *a1,
        struct WDFIOTARGET__ *a2,
        struct _WDF_REQUEST_COMPLETION_PARAMS *a3,
        struct WDFDEVICE__ *a4)
{
  __int64 v7; // rdi
  int *v8; // r15
  struct _BRB *v9; // r12
  int v10; // edx
  int ChannelHandle; // esi
  int v12; // r8d
  bool v13; // bp
  char v14; // bl
  __int64 *v15; // r9
  int v16; // edx
  int v17; // r8d
  __int64 v18; // rdx
  int v19; // edx
  int v20; // r8d
  int v21; // edx
  __int64 v22; // r8
  __int64 v23; // rax
  int v24; // r9d
  __int64 v25; // rdx
  __int128 v26; // xmm1
  __int64 *v27; // rdx
  char v28; // [rsp+B0h] [rbp+18h] BYREF

  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a4,
         off_140022150);
  v8 = (int *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *, __int64 *))(WdfFunctions_01015
                                                                                               + 1616))(
                WdfDriverGlobals,
                a1,
                off_140022178);
  v9 = (struct _BRB *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, ULONG_PTR, _QWORD))(WdfFunctions_01015 + 1552))(
                        WdfDriverGlobals,
                        a3->Parameters.Others.Argument1.Value,
                        0);
  ChannelHandle = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *))(WdfFunctions_01015 + 2032))(
                    WdfDriverGlobals,
                    a1);
  v13 = 0;
  v14 = 1;
  LOBYTE(v10) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  v15 = WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids;
  if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
      WPP_GLOBAL_Control->AttachedDevice,
      v10,
      v12,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      14,
      (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids,
      ChannelHandle);
  }
  if ( !(*(unsigned __int8 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int64 *))(WdfFunctions_01015 + 2560))(
          WdfDriverGlobals,
          *(_QWORD *)(v7 + 480),
          0,
          v15) )
  {
    LOBYTE(v16) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( (_BYTE)v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v16,
        v17,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        5,
        15,
        (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
    }
  }
  wil::acquire_wdf_spin_lock(&v28, *(_QWORD *)(v7 + 368));
  v18 = *(_QWORD *)(v7 + 464);
  if ( v18 )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1648))(
      WdfDriverGlobals,
      v18,
      0,
      515,
      "onecoreuap\\drivers\\wdm\\audio\\drivers\\bluetooth\\bthhfenum\\bthscoserver.cpp");
    *(_QWORD *)(v7 + 464) = 0;
  }
  else
  {
    v13 = *(_DWORD *)(v7 + 108) == 0;
  }
  if ( ChannelHandle >= 0 )
  {
    ChannelHandle = ScoOpenCompletionGetChannelHandle((struct _SCOCONTEXT *)v7, v9);
    LOBYTE(v19) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v19 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v19,
        v20,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        5,
        16,
        (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids,
        *(_QWORD *)(v7 + 128));
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(&v28);
  LogScoConnection((struct _SCOCONTEXT *)v7, ChannelHandle);
  if ( ChannelHandle >= 0 )
  {
    if ( v13 )
    {
      ScoChannelClose(a4, 0);
    }
    else
    {
      v23 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, __int64 *))(WdfFunctions_01015 + 1616))(
              WdfDriverGlobals,
              a4,
              off_1400220B0);
      SleepstudyHelper_ComponentActive(*(_QWORD *)(v23 + 408));
      AudioQueue_StreamStart(*(_QWORD *)(v7 + 160));
      AudioQueue_StreamStart(*(_QWORD *)(v7 + 240));
      SetScoState(v7, 6);
    }
    goto LABEL_53;
  }
  v24 = v8[4];
  *v8 = ChannelHandle;
  if ( v24 <= 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v14 = 0;
    }
    if ( v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v27 = WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids;
      LOBYTE(v27) = v14;
      LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v27,
        v22,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        5,
        18,
        (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
    }
    goto LABEL_52;
  }
  LOBYTE(v21) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
  LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v21 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
      WPP_GLOBAL_Control->AttachedDevice,
      v21,
      v22,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      5,
      17,
      (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids,
      v24);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 2528))(
    WdfDriverGlobals,
    *(_QWORD *)(v7 + 368),
    v22);
  v25 = *(_QWORD *)(v7 + 368);
  *(_OWORD *)(v7 + 424) = *(_OWORD *)v8;
  v26 = *((_OWORD *)v8 + 1);
  *(_DWORD *)(v7 + 416) = 1;
  *(_OWORD *)(v7 + 440) = v26;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2536))(WdfDriverGlobals, v25);
  ChannelHandle = ScoChannelOpenAsync(a4);
  if ( ChannelHandle < 0 )
LABEL_52:
    ScoHandleStreamFailure(ChannelHandle, a4);
LABEL_53:
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, a1);
}

```

## disassembly

```asm
0x14000fa40  push    rbx
0x14000fa42  push    rbp
0x14000fa43  push    rsi
0x14000fa44  push    rdi
0x14000fa45  push    r12
0x14000fa47  push    r13
0x14000fa49  push    r14
0x14000fa4b  push    r15
0x14000fa4d  sub     rsp, 58h
0x14000fa51  mov     rax, cs:WdfFunctions_01015
0x14000fa58  mov     rbx, r8
0x14000fa5b  mov     r8, cs:off_140022150
0x14000fa62  mov     r13, rcx
0x14000fa65  mov     rcx, cs:WdfDriverGlobals
0x14000fa6c  mov     rdx, r9
0x14000fa6f  mov     r14, r9
0x14000fa72  mov     rax, [rax+650h]
0x14000fa79  call    _guard_dispatch_icall
0x14000fa7e  mov     rdx, cs:WdfFunctions_01015
0x14000fa85  mov     rdi, rax
0x14000fa88  mov     r8, cs:off_140022178
0x14000fa8f  mov     rcx, cs:WdfDriverGlobals
0x14000fa96  mov     rax, [rdx+650h]
0x14000fa9d  mov     rdx, r13
0x14000faa0  call    _guard_dispatch_icall
0x14000faa5  mov     rcx, cs:WdfFunctions_01015
0x14000faac  mov     r15, rax
0x14000faaf  mov     rdx, [rbx+18h]
0x14000fab3  xor     r8d, r8d
0x14000fab6  mov     rax, [rcx+610h]
0x14000fabd  mov     rcx, cs:WdfDriverGlobals
0x14000fac4  call    _guard_dispatch_icall
0x14000fac9  mov     rcx, cs:WdfFunctions_01015
0x14000fad0  mov     r12, rax
0x14000fad3  mov     rdx, r13
0x14000fad6  mov     rax, [rcx+7F0h]
0x14000fadd  mov     rcx, cs:WdfDriverGlobals
0x14000fae4  call    _guard_dispatch_icall
0x14000fae9  mov     esi, eax
0x14000faeb  xor     bpl, bpl
0x14000faee  mov     rax, cs:WPP_GLOBAL_Control
0x14000faf5  lea     rcx, WPP_GLOBAL_Control
0x14000fafc  mov     ebx, 1
0x14000fb01  cmp     rax, rcx
0x14000fb04  jz      short loc_14000FB18
0x14000fb06  mov     ecx, [rax+2Ch]
0x14000fb09  test    cl, 10h
0x14000fb0c  jz      short loc_14000FB18
0x14000fb0e  cmp     byte ptr [rax+29h], 4
0x14000fb12  jb      short loc_14000FB18
0x14000fb14  mov     dl, bl
0x14000fb16  jmp     short loc_14000FB1A
0x14000fb18  xor     dl, dl
0x14000fb1a  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000fb21  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000fb28  lea     r9, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000fb2f  setnz   r8b
0x14000fb33  test    dl, dl
0x14000fb35  jnz     short loc_14000FB3C
0x14000fb37  test    r8b, r8b
0x14000fb3a  jz      short loc_14000FB66
0x14000fb3c  mov     rcx, [rax+18h]
0x14000fb40  mov     dword ptr [rsp+98h+var_58], esi
0x14000fb44  mov     [rsp+98h+var_60], r9
0x14000fb49  mov     r9, [rax+40h]
0x14000fb4d  mov     [rsp+98h+var_68], 0Eh
0x14000fb54  mov     [rsp+98h+var_70], 5
0x14000fb5c  mov     byte ptr [rsp+98h+var_78], 4
0x14000fb61  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x14000fb66  mov     rax, cs:WdfFunctions_01015
0x14000fb6d  xor     r8d, r8d
0x14000fb70  mov     rdx, [rdi+1E0h]
0x14000fb77  mov     rcx, cs:WdfDriverGlobals
0x14000fb7e  mov     rax, [rax+0A00h]
0x14000fb85  call    _guard_dispatch_icall
0x14000fb8a  test    al, al
0x14000fb8c  jnz     short loc_14000FBFC
0x14000fb8e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fb95  lea     rax, WPP_GLOBAL_Control
0x14000fb9c  cmp     rcx, rax
0x14000fb9f  jz      short loc_14000FBB2
0x14000fba1  mov     eax, [rcx+2Ch]
0x14000fba4  test    al, 10h
0x14000fba6  jz      short loc_14000FBB2
0x14000fba8  cmp     byte ptr [rcx+29h], 2
0x14000fbac  jb      short loc_14000FBB2
0x14000fbae  mov     dl, bl
0x14000fbb0  jmp     short loc_14000FBB4
0x14000fbb2  xor     dl, dl
0x14000fbb4  lea     rax, WPP_RECORDER_INITIALIZED
0x14000fbbb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000fbc2  setnz   r8b
0x14000fbc6  test    dl, dl
0x14000fbc8  jnz     short loc_14000FBCF
0x14000fbca  test    r8b, r8b
0x14000fbcd  jz      short loc_14000FBFC
0x14000fbcf  lea     r9, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000fbd6  mov     [rsp+98h+var_60], r9
0x14000fbdb  mov     r9, [rcx+40h]
0x14000fbdf  mov     rcx, [rcx+18h]
0x14000fbe3  mov     [rsp+98h+var_68], 0Fh
0x14000fbea  mov     [rsp+98h+var_70], 5
0x14000fbf2  mov     byte ptr [rsp+98h+var_78], 2
0x14000fbf7  call    WPP_RECORDER_AND_TRACE_SF_
0x14000fbfc  mov     rdx, [rdi+170h]
0x14000fc03  lea     rcx, [rsp+98h+arg_10]
0x14000fc0b  call    ?acquire_wdf_spin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAUWDFSPINLOCK__@@@Z; wil::acquire_wdf_spin_lock(WDFSPINLOCK__ *)
0x14000fc10  mov     rdx, [rdi+1D0h]
0x14000fc17  test    rdx, rdx
0x14000fc1a  jz      short loc_14000FC58
0x14000fc1c  mov     rax, cs:WdfFunctions_01015
0x14000fc23  lea     rcx, aOnecoreuapDriv; "onecoreuap\\drivers\\wdm\\audio\\driver"...
0x14000fc2a  mov     [rsp+98h+var_78], rcx
0x14000fc2f  mov     r9d, 203h
0x14000fc35  mov     rcx, cs:WdfDriverGlobals
0x14000fc3c  xor     r8d, r8d
0x14000fc3f  mov     rax, [rax+670h]
0x14000fc46  call    _guard_dispatch_icall
0x14000fc4b  mov     qword ptr [rdi+1D0h], 0
0x14000fc56  jmp     short loc_14000FC63
0x14000fc58  cmp     dword ptr [rdi+6Ch], 0
0x14000fc5c  movzx   ebp, bpl
0x14000fc60  cmovz   ebp, ebx
0x14000fc63  test    esi, esi
0x14000fc65  js      loc_14000FCFA
0x14000fc6b  mov     rdx, r12; struct _BRB *
0x14000fc6e  mov     rcx, rdi; struct _SCOCONTEXT *
0x14000fc71  call    ?ScoOpenCompletionGetChannelHandle@@YAJPEAU_SCOCONTEXT@@PEAU_BRB@@@Z; ScoOpenCompletionGetChannelHandle(_SCOCONTEXT *,_BRB *)
0x14000fc76  mov     esi, eax
0x14000fc78  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc7f  lea     rax, WPP_GLOBAL_Control
0x14000fc86  mov     r9d, 10h
0x14000fc8c  cmp     rcx, rax
0x14000fc8f  jz      short loc_14000FCA3
0x14000fc91  mov     eax, [rcx+2Ch]
0x14000fc94  test    r9b, al
0x14000fc97  jz      short loc_14000FCA3
0x14000fc99  cmp     byte ptr [rcx+29h], 4
0x14000fc9d  jb      short loc_14000FCA3
0x14000fc9f  mov     dl, bl
0x14000fca1  jmp     short loc_14000FCA5
0x14000fca3  xor     dl, dl
0x14000fca5  lea     r12, WPP_RECORDER_INITIALIZED
0x14000fcac  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000fcb3  setnz   r8b
0x14000fcb7  test    dl, dl
0x14000fcb9  jnz     short loc_14000FCC0
0x14000fcbb  test    r8b, r8b
0x14000fcbe  jz      short loc_14000FD01
0x14000fcc0  mov     rax, [rdi+80h]
0x14000fcc7  mov     [rsp+98h+var_58], rax
0x14000fccc  lea     rax, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000fcd3  mov     [rsp+98h+var_60], rax
0x14000fcd8  mov     [rsp+98h+var_68], r9w
0x14000fcde  mov     r9, [rcx+40h]
0x14000fce2  mov     rcx, [rcx+18h]
0x14000fce6  mov     [rsp+98h+var_70], 5
0x14000fcee  mov     byte ptr [rsp+98h+var_78], 4
0x14000fcf3  call    WPP_RECORDER_AND_TRACE_SF_q
0x14000fcf8  jmp     short loc_14000FD01
0x14000fcfa  lea     r12, WPP_RECORDER_INITIALIZED
0x14000fd01  lea     rcx, [rsp+98h+arg_10]
0x14000fd09  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)
0x14000fd0e  mov     edx, esi; int
0x14000fd10  mov     rcx, rdi; struct _SCOCONTEXT *
0x14000fd13  call    ?LogScoConnection@@YAXPEAU_SCOCONTEXT@@J@Z; LogScoConnection(_SCOCONTEXT *,long)
0x14000fd18  test    esi, esi
0x14000fd1a  js      short loc_14000FD91
0x14000fd1c  test    bpl, bpl
0x14000fd1f  jz      short loc_14000FD30
0x14000fd21  xor     edx, edx
0x14000fd23  mov     rcx, r14
0x14000fd26  call    ScoChannelClose
0x14000fd2b  jmp     loc_14000FEEB
0x14000fd30  mov     rax, cs:WdfFunctions_01015
0x14000fd37  mov     rdx, r14
0x14000fd3a  mov     r8, cs:off_1400220B0
0x14000fd41  mov     rcx, cs:WdfDriverGlobals
0x14000fd48  mov     rax, [rax+650h]
0x14000fd4f  call    _guard_dispatch_icall
0x14000fd54  mov     rcx, [rax+198h]
0x14000fd5b  call    cs:__imp_SleepstudyHelper_ComponentActive
0x14000fd62  nop     dword ptr [rax+rax+00h]
0x14000fd67  mov     rcx, [rdi+0A0h]
0x14000fd6e  call    AudioQueue_StreamStart
0x14000fd73  mov     rcx, [rdi+0F0h]
0x14000fd7a  call    AudioQueue_StreamStart
0x14000fd7f  mov     edx, 6
0x14000fd84  mov     rcx, rdi
0x14000fd87  call    SetScoState
0x14000fd8c  jmp     loc_14000FEEB
0x14000fd91  mov     r9d, [r15+10h]
0x14000fd95  mov     [r15], esi
0x14000fd98  test    r9d, r9d
0x14000fd9b  jle     loc_14000FE7C
0x14000fda1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fda8  lea     rax, WPP_GLOBAL_Control
0x14000fdaf  cmp     rcx, rax
0x14000fdb2  jz      short loc_14000FDC5
0x14000fdb4  mov     eax, [rcx+2Ch]
0x14000fdb7  test    al, 10h
0x14000fdb9  jz      short loc_14000FDC5
0x14000fdbb  cmp     byte ptr [rcx+29h], 3
0x14000fdbf  jb      short loc_14000FDC5
0x14000fdc1  mov     dl, bl
0x14000fdc3  jmp     short loc_14000FDC7
0x14000fdc5  xor     dl, dl
0x14000fdc7  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000fdce  setnz   r8b
0x14000fdd2  test    dl, dl
0x14000fdd4  jnz     short loc_14000FDDB
0x14000fdd6  test    r8b, r8b
0x14000fdd9  jz      short loc_14000FE0D
0x14000fddb  mov     dword ptr [rsp+98h+var_58], r9d
0x14000fde0  lea     r9, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000fde7  mov     [rsp+98h+var_60], r9
0x14000fdec  mov     r9, [rcx+40h]
0x14000fdf0  mov     rcx, [rcx+18h]
0x14000fdf4  mov     [rsp+98h+var_68], 11h
0x14000fdfb  mov     [rsp+98h+var_70], 5
0x14000fe03  mov     byte ptr [rsp+98h+var_78], 3
0x14000fe08  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x14000fe0d  mov     rax, cs:WdfFunctions_01015
0x14000fe14  mov     rdx, [rdi+170h]
0x14000fe1b  mov     rcx, cs:WdfDriverGlobals
0x14000fe22  mov     rax, [rax+9E0h]
0x14000fe29  call    _guard_dispatch_icall
0x14000fe2e  movups  xmm0, xmmword ptr [r15]
0x14000fe32  mov     rdx, [rdi+170h]
0x14000fe39  movups  xmmword ptr [rdi+1A8h], xmm0
0x14000fe40  movups  xmm1, xmmword ptr [r15+10h]
0x14000fe45  mov     [rdi+1A0h], ebx
0x14000fe4b  movups  xmmword ptr [rdi+1B8h], xmm1
0x14000fe52  mov     rax, cs:WdfFunctions_01015
0x14000fe59  mov     rcx, cs:WdfDriverGlobals
0x14000fe60  mov     rax, [rax+9E8h]
0x14000fe67  call    _guard_dispatch_icall
0x14000fe6c  mov     rcx, r14; struct WDFDEVICE__ *
0x14000fe6f  call    ?ScoChannelOpenAsync@@YAJPEAUWDFDEVICE__@@@Z; ScoChannelOpenAsync(WDFDEVICE__ *)
0x14000fe74  mov     esi, eax
0x14000fe76  test    eax, eax
0x14000fe78  jns     short loc_14000FEEB
0x14000fe7a  jmp     short loc_14000FEE1
0x14000fe7c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe83  lea     rax, WPP_GLOBAL_Control
0x14000fe8a  cmp     rcx, rax
0x14000fe8d  jz      short loc_14000FE9C
0x14000fe8f  mov     eax, [rcx+2Ch]
0x14000fe92  test    al, 10h
0x14000fe94  jz      short loc_14000FE9C
0x14000fe96  cmp     byte ptr [rcx+29h], 2
0x14000fe9a  jnb     short loc_14000FE9E
0x14000fe9c  xor     bl, bl
0x14000fe9e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000fea5  setnz   r8b
0x14000fea9  test    bl, bl
0x14000feab  jnz     short loc_14000FEB2
0x14000fead  test    r8b, r8b
0x14000feb0  jz      short loc_14000FEE1
0x14000feb2  mov     r9, [rcx+40h]
0x14000feb6  lea     rdx, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000febd  mov     rcx, [rcx+18h]
0x14000fec1  mov     [rsp+98h+var_60], rdx
0x14000fec6  mov     dl, bl
0x14000fec8  mov     [rsp+98h+var_68], 12h
0x14000fecf  mov     [rsp+98h+var_70], 5
0x14000fed7  mov     byte ptr [rsp+98h+var_78], 2
0x14000fedc  call    WPP_RECORDER_AND_TRACE_SF_
0x14000fee1  mov     rdx, r14; struct WDFDEVICE__ *
0x14000fee4  mov     ecx, esi; int
0x14000fee6  call    ?ScoHandleStreamFailure@@YAXJPEAUWDFDEVICE__@@@Z; ScoHandleStreamFailure(long,WDFDEVICE__ *)
0x14000feeb  mov     rax, cs:WdfFunctions_01015
0x14000fef2  mov     rdx, r13
0x14000fef5  mov     rcx, cs:WdfDriverGlobals
0x14000fefc  mov     rax, [rax+680h]
0x14000ff03  call    _guard_dispatch_icall
0x14000ff08  add     rsp, 58h
0x14000ff0c  pop     r15
0x14000ff0e  pop     r14
0x14000ff10  pop     r13
0x14000ff12  pop     r12
0x14000ff14  pop     rdi
0x14000ff15  pop     rsi
0x14000ff16  pop     rbp
0x14000ff17  pop     rbx
0x14000ff18  retn
```
