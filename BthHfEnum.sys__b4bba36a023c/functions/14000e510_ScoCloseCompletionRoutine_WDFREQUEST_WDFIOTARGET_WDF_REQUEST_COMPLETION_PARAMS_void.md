# ScoCloseCompletionRoutine(WDFREQUEST__ *,WDFIOTARGET__ *,_WDF_REQUEST_COMPLETION_PARAMS *,void *)

- ea: `0x14000e510`
- end: `0x14000e874`
- name: `?ScoCloseCompletionRoutine@@YAXPEAUWDFREQUEST__@@PEAUWDFIOTARGET__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@PEAX@Z`
- size: `868`
- prototype: `void __fastcall(struct WDFREQUEST__ *, struct WDFIOTARGET__ *, struct _WDF_REQUEST_COMPLETION_PARAMS *, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000a594`
- `0x14000a914`
- `0x14000c570`
- `0x14000cb04`
- `0x14000cbd0`
- `0x14000e510`
- `0x1400112c4`
- `0x140011484`
- `0x140014c60`
- `0x14001ae00`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000e7ba`
- `ntoskrnl!KeSetEvent` at `0x14000e7ba`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e7c9`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e7c9`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x14000e79b`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x14000e79b`

## pseudocode

```c
void __fastcall ScoCloseCompletionRoutine(
        struct WDFREQUEST__ *a1,
        struct WDFIOTARGET__ *a2,
        struct _WDF_REQUEST_COMPLETION_PARAMS *a3,
        void *a4)
{
  __int64 v7; // rdi
  __int64 v8; // rbx
  int v9; // edx
  int v10; // esi
  int v11; // r8d
  char v12; // bp
  __int64 v13; // rdx
  bool v14; // r14
  int v15; // ebx
  char ScoState; // al
  int v17; // r8d
  int v18; // edx
  __int64 v19; // rax
  struct _KEVENT *v20; // rbx
  __int64 v21; // rdx
  __int64 v22; // rdx
  int v23; // [rsp+20h] [rbp-58h]
  int v24; // [rsp+28h] [rbp-50h]
  int v25; // [rsp+38h] [rbp-40h]
  char v26; // [rsp+90h] [rbp+18h] BYREF

  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, void *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a4,
         off_140022150);
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, ULONG_PTR, _QWORD))(WdfFunctions_01015 + 1552))(
         WdfDriverGlobals,
         a3->Parameters.Others.Argument1.Value,
         0);
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *))(WdfFunctions_01015 + 2032))(
          WdfDriverGlobals,
          a1);
  if ( v10 < 0 )
  {
    v12 = 1;
    LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v11,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        5,
        20,
        (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids,
        v10,
        *(_DWORD *)(v7 + 108));
    }
  }
  else
  {
    v10 = *(_DWORD *)(v8 + 28);
    v12 = 1;
    LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v11,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        5,
        19,
        (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids,
        v10,
        *(_DWORD *)(v7 + 108));
    }
  }
  wil::acquire_wdf_spin_lock(&v26, *(_QWORD *)(v7 + 368));
  v13 = *(_QWORD *)(v7 + 296);
  *(_DWORD *)(v7 + 456) = 1;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2552))(
    WdfDriverGlobals,
    v13,
    -500000);
  wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(&v26);
  if ( v10 >= 0 || v10 == -1073741667 || v10 == -1073741643 )
  {
    *(_QWORD *)(v7 + 128) = 0;
    SetScoState(v7, 0);
    v19 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, void *, __int64 *))(WdfFunctions_01015 + 1616))(
            WdfDriverGlobals,
            a4,
            off_1400220B0);
    SleepstudyHelper_ComponentInactive(*(_QWORD *)(v19 + 408));
    v20 = (struct _KEVENT *)_InterlockedExchange64((volatile __int64 *)(v7 + 112), 0);
    if ( v20 )
    {
      KeSetEvent(v20, 0, 0);
      ObfDereferenceObject(v20);
    }
    else if ( *(_DWORD *)(v7 + 108) )
    {
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 2552))(
        WdfDriverGlobals,
        *(_QWORD *)(v7 + 328),
        -50000000);
    }
    v10 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v12 = 0;
    }
    v14 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = *(_DWORD *)(v7 + 108);
      ScoState = GetScoState(v7);
      LOBYTE(v17) = v14;
      LOBYTE(v18) = v12;
      WPP_RECORDER_AND_TRACE_SF_SCOSTATESCOSTATE(
        WPP_GLOBAL_Control->AttachedDevice,
        v18,
        v17,
        WPP_GLOBAL_Control->DeviceExtension,
        v23,
        v24,
        21,
        v25,
        ScoState,
        v15);
    }
  }
  LogScoDisconnection((struct _SCOCONTEXT *)v7, v10);
  WdfIoQueueFindAndCompleteIoctlRequest(*(_QWORD *)(v7 + 96), v21, 2228271, (unsigned int)v10);
  WdfIoQueueFindAndCompleteIoctlRequest(*(_QWORD *)(v7 + 96), v22, 2752556, (unsigned int)v10);
  _InterlockedExchange((volatile __int32 *)(v7 + 472), 0);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, a1);
}

```

## disassembly

```asm
0x14000e510  mov     [rsp+arg_0], rbx
0x14000e515  mov     [rsp+arg_8], rbp
0x14000e51a  push    rsi
0x14000e51b  push    rdi
0x14000e51c  push    r12
0x14000e51e  push    r14
0x14000e520  push    r15
0x14000e522  sub     rsp, 50h
0x14000e526  mov     rax, cs:WdfFunctions_01015
0x14000e52d  mov     rbx, r8
0x14000e530  mov     r8, cs:off_140022150
0x14000e537  mov     r12, rcx
0x14000e53a  mov     rcx, cs:WdfDriverGlobals
0x14000e541  mov     rdx, r9
0x14000e544  mov     r15, r9
0x14000e547  mov     rax, [rax+650h]
0x14000e54e  call    _guard_dispatch_icall
0x14000e553  mov     rdx, cs:WdfFunctions_01015
0x14000e55a  mov     rdi, rax
0x14000e55d  mov     rcx, cs:WdfDriverGlobals
0x14000e564  xor     r8d, r8d
0x14000e567  mov     rax, [rdx+610h]
0x14000e56e  mov     rdx, [rbx+18h]
0x14000e572  call    _guard_dispatch_icall
0x14000e577  mov     rcx, cs:WdfFunctions_01015
0x14000e57e  mov     rbx, rax
0x14000e581  mov     rdx, r12
0x14000e584  mov     rax, [rcx+7F0h]
0x14000e58b  mov     rcx, cs:WdfDriverGlobals
0x14000e592  call    _guard_dispatch_icall
0x14000e597  mov     esi, eax
0x14000e599  test    eax, eax
0x14000e59b  js      short loc_14000E60B
0x14000e59d  mov     esi, [rbx+1Ch]
0x14000e5a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e5a7  lea     r14, WPP_GLOBAL_Control
0x14000e5ae  mov     ebp, 1
0x14000e5b3  cmp     rcx, r14
0x14000e5b6  jz      short loc_14000E5CA
0x14000e5b8  mov     eax, [rcx+2Ch]
0x14000e5bb  test    al, 10h
0x14000e5bd  jz      short loc_14000E5CA
0x14000e5bf  cmp     byte ptr [rcx+29h], 4
0x14000e5c3  jb      short loc_14000E5CA
0x14000e5c5  mov     dl, bpl
0x14000e5c8  jmp     short loc_14000E5CC
0x14000e5ca  xor     dl, dl
0x14000e5cc  lea     rbx, WPP_RECORDER_INITIALIZED
0x14000e5d3  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14000e5da  setnz   r8b
0x14000e5de  test    dl, dl
0x14000e5e0  jnz     short loc_14000E5EB
0x14000e5e2  test    r8b, r8b
0x14000e5e5  jz      loc_14000E68A
0x14000e5eb  mov     eax, [rdi+6Ch]
0x14000e5ee  mov     [rsp+78h+var_30], eax
0x14000e5f2  lea     rax, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000e5f9  mov     [rsp+78h+var_38], esi
0x14000e5fd  mov     [rsp+78h+var_40], rax
0x14000e602  mov     [rsp+78h+var_48], 13h
0x14000e609  jmp     short loc_14000E670
0x14000e60b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e612  lea     r14, WPP_GLOBAL_Control
0x14000e619  mov     ebp, 1
0x14000e61e  cmp     rcx, r14
0x14000e621  jz      short loc_14000E635
0x14000e623  mov     eax, [rcx+2Ch]
0x14000e626  test    al, 10h
0x14000e628  jz      short loc_14000E635
0x14000e62a  cmp     byte ptr [rcx+29h], 4
0x14000e62e  jb      short loc_14000E635
0x14000e630  mov     dl, bpl
0x14000e633  jmp     short loc_14000E637
0x14000e635  xor     dl, dl
0x14000e637  lea     rbx, WPP_RECORDER_INITIALIZED
0x14000e63e  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14000e645  setnz   r8b
0x14000e649  test    dl, dl
0x14000e64b  jnz     short loc_14000E652
0x14000e64d  test    r8b, r8b
0x14000e650  jz      short loc_14000E68A
0x14000e652  mov     eax, [rdi+6Ch]
0x14000e655  mov     [rsp+78h+var_30], eax
0x14000e659  lea     rax, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000e660  mov     [rsp+78h+var_38], esi
0x14000e664  mov     [rsp+78h+var_40], rax
0x14000e669  mov     [rsp+78h+var_48], 14h
0x14000e670  mov     r9, [rcx+40h]
0x14000e674  mov     rcx, [rcx+18h]
0x14000e678  mov     [rsp+78h+var_50], 5
0x14000e680  mov     [rsp+78h+var_58], 4
0x14000e685  call    WPP_RECORDER_AND_TRACE_SF_dd
0x14000e68a  mov     rdx, [rdi+170h]
0x14000e691  lea     rcx, [rsp+78h+arg_10]
0x14000e699  call    ?acquire_wdf_spin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAUWDFSPINLOCK__@@@Z; wil::acquire_wdf_spin_lock(WDFSPINLOCK__ *)
0x14000e69e  mov     rdx, [rdi+128h]
0x14000e6a5  mov     r8, 0FFFFFFFFFFF85EE0h
0x14000e6ac  mov     [rdi+1C8h], ebp
0x14000e6b2  mov     rax, cs:WdfFunctions_01015
0x14000e6b9  mov     rcx, cs:WdfDriverGlobals
0x14000e6c0  mov     rax, [rax+9F8h]
0x14000e6c7  call    _guard_dispatch_icall
0x14000e6cc  lea     rcx, [rsp+78h+arg_10]
0x14000e6d4  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)
0x14000e6d9  test    esi, esi
0x14000e6db  jns     short loc_14000E75B
0x14000e6dd  cmp     esi, 0C000009Dh
0x14000e6e3  jz      short loc_14000E75B
0x14000e6e5  cmp     esi, 0C00000B5h
0x14000e6eb  jz      short loc_14000E75B
0x14000e6ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e6f4  cmp     rcx, r14
0x14000e6f7  jz      short loc_14000E706
0x14000e6f9  mov     eax, [rcx+2Ch]
0x14000e6fc  test    al, 10h
0x14000e6fe  jz      short loc_14000E706
0x14000e700  cmp     byte ptr [rcx+29h], 4
0x14000e704  jnb     short loc_14000E709
0x14000e706  xor     bpl, bpl
0x14000e709  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14000e710  setnz   r14b
0x14000e714  test    bpl, bpl
0x14000e717  jnz     short loc_14000E722
0x14000e719  test    r14b, r14b
0x14000e71c  jz      loc_14000E807
0x14000e722  mov     ebx, [rdi+6Ch]
0x14000e725  mov     rcx, rdi
0x14000e728  call    ?GetScoState@@YA?AW4SCOSTATE@@PEAU_SCOCONTEXT@@@Z; GetScoState(_SCOCONTEXT *)
0x14000e72d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e734  mov     r8b, r14b
0x14000e737  mov     [rsp+78h+var_30], ebx
0x14000e73b  mov     dl, bpl
0x14000e73e  mov     [rsp+78h+var_38], eax
0x14000e742  mov     [rsp+78h+var_48], 15h
0x14000e749  mov     r9, [rcx+40h]
0x14000e74d  mov     rcx, [rcx+18h]
0x14000e751  call    WPP_RECORDER_AND_TRACE_SF_SCOSTATESCOSTATE
0x14000e756  jmp     loc_14000E807
0x14000e75b  xor     edx, edx
0x14000e75d  mov     qword ptr [rdi+80h], 0
0x14000e768  mov     rcx, rdi
0x14000e76b  call    SetScoState
0x14000e770  mov     rax, cs:WdfFunctions_01015
0x14000e777  mov     rdx, r15
0x14000e77a  mov     r8, cs:off_1400220B0
0x14000e781  mov     rcx, cs:WdfDriverGlobals
0x14000e788  mov     rax, [rax+650h]
0x14000e78f  call    _guard_dispatch_icall
0x14000e794  mov     rcx, [rax+198h]
0x14000e79b  call    cs:__imp_SleepstudyHelper_ComponentInactive
0x14000e7a2  nop     dword ptr [rax+rax+00h]
0x14000e7a7  xor     ebx, ebx
0x14000e7a9  xchg    rbx, [rdi+70h]
0x14000e7ad  test    rbx, rbx
0x14000e7b0  jz      short loc_14000E7D7
0x14000e7b2  xor     r8d, r8d; Wait
0x14000e7b5  xor     edx, edx; Increment
0x14000e7b7  mov     rcx, rbx; Event
0x14000e7ba  call    cs:__imp_KeSetEvent
0x14000e7c1  nop     dword ptr [rax+rax+00h]
0x14000e7c6  mov     rcx, rbx; Object
0x14000e7c9  call    cs:__imp_ObfDereferenceObject
0x14000e7d0  nop     dword ptr [rax+rax+00h]
0x14000e7d5  jmp     short loc_14000E805
0x14000e7d7  cmp     dword ptr [rdi+6Ch], 0
0x14000e7db  jz      short loc_14000E805
0x14000e7dd  mov     rax, cs:WdfFunctions_01015
0x14000e7e4  mov     r8, 0FFFFFFFFFD050F80h
0x14000e7eb  mov     rdx, [rdi+148h]
0x14000e7f2  mov     rcx, cs:WdfDriverGlobals
0x14000e7f9  mov     rax, [rax+9F8h]
0x14000e800  call    _guard_dispatch_icall
0x14000e805  xor     esi, esi
0x14000e807  mov     edx, esi; int
0x14000e809  mov     rcx, rdi; struct _SCOCONTEXT *
0x14000e80c  call    ?LogScoDisconnection@@YAXPEAU_SCOCONTEXT@@J@Z; LogScoDisconnection(_SCOCONTEXT *,long)
0x14000e811  mov     rcx, [rdi+60h]
0x14000e815  mov     r9d, esi
0x14000e818  mov     r8d, 22002Fh
0x14000e81e  call    WdfIoQueueFindAndCompleteIoctlRequest
0x14000e823  mov     rcx, [rdi+60h]
0x14000e827  mov     r9d, esi
0x14000e82a  mov     r8d, 2A002Ch
0x14000e830  call    WdfIoQueueFindAndCompleteIoctlRequest
0x14000e835  xor     eax, eax
0x14000e837  mov     rdx, r12
0x14000e83a  xchg    eax, [rdi+1D8h]
0x14000e840  mov     rcx, cs:WdfFunctions_01015
0x14000e847  mov     rax, [rcx+680h]
0x14000e84e  mov     rcx, cs:WdfDriverGlobals
0x14000e855  call    _guard_dispatch_icall
0x14000e85a  lea     r11, [rsp+78h+var_28]
0x14000e85f  mov     rbx, [r11+30h]
0x14000e863  mov     rbp, [r11+38h]
0x14000e867  mov     rsp, r11
0x14000e86a  pop     r15
0x14000e86c  pop     r14
0x14000e86e  pop     r12
0x14000e870  pop     rdi
0x14000e871  pop     rsi
0x14000e872  retn
```
