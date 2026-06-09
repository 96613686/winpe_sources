# DeviceCommandScheduler::OnCtlPlaneWdiOidCompleteCallback(ulong,_WFC_MESSAGE_METADATA *,IWdiMessageMemoryManager *)

- ea: `0x140015220`
- end: `0x1400156c2`
- name: `?OnCtlPlaneWdiOidCompleteCallback@DeviceCommandScheduler@@IEAAXKPEAU_WFC_MESSAGE_METADATA@@PEAVIWdiMessageMemoryManager@@@Z`
- size: `1186`
- prototype: `void __fastcall(DeviceCommandScheduler *__hidden this, unsigned int, struct _WFC_MESSAGE_METADATA *, struct IWdiMessageMemoryManager *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140062360`

## callees

- `0x14000c778`
- `0x14000cf40`
- `0x14000d054`
- `0x140015220`
- `0x1400156d0`
- `0x14001e430`
- `0x14001eed0`
- `0x1400dfd40`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140015472`
- `ntoskrnl!ExAllocatePool2` at `0x140015472`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001563e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001565d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001563e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001565d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400155e4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400155e4`

## pseudocode

```c
void __fastcall DeviceCommandScheduler::OnCtlPlaneWdiOidCompleteCallback(
        DeviceCommandScheduler *this,
        __int64 a2,
        struct _WFC_MESSAGE_METADATA *a3,
        struct IWdiMessageMemoryManager *a4)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  Event *Pool2; // rcx
  _OWORD *v10; // rax
  _OWORD *v11; // rcx
  _QWORD *v12; // rax
  Event *v13; // rbx
  int v14; // r9d
  int v15; // eax
  __int64 v16; // rbp
  _QWORD *v17; // rdi
  __int64 v18; // rsi
  __int64 v19; // r14
  int v20; // edx
  _QWORD *v21; // rax
  char v22; // bl
  __int64 v23; // r14
  _QWORD *v24; // rax
  KIRQL v25; // dl
  KIRQL v26; // dl
  __int64 v27; // [rsp+28h] [rbp-90h]
  __int128 v28; // [rsp+40h] [rbp-78h] BYREF
  __int128 v29; // [rsp+50h] [rbp-68h]
  __int128 v30; // [rsp+60h] [rbp-58h]
  __int64 *v31; // [rsp+70h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+B8h] [rbp+0h]
  _OWORD *v33; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v34; // [rsp+D0h] [rbp+18h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      31,
      (__int64)WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids);
  }
  if ( !g_Feature_56544556_MoveToWDFMemory_IsEnabled )
  {
    Pool2 = (Event *)ExAllocatePool2(64, 72, 1198089303);
    goto LABEL_19;
  }
  v28 = 0;
  v31 = 0;
  v29 = 0;
  v30 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v28) = -1;
    else
      LODWORD(v28) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v28) = 56;
  }
  v31 = off_14010E2B8;
  *((_QWORD *)&v29 + 1) = 0x100000001LL;
  v34 = 0;
  v33 = 0;
  if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64, __int64, __int64, __int64 *, _OWORD **))(WdfFunctions_01031 + 1536))(
         WdfDriverGlobals,
         &v28,
         512,
         1198089303,
         88,
         &v34,
         &v33) >= 0 )
  {
    v10 = v33;
    *v33 = 0;
    v10[1] = 0;
    v10[2] = 0;
    v10[3] = 0;
    v10[4] = 0;
    *((_QWORD *)v10 + 10) = 0;
    v11 = v33;
    *(_QWORD *)v33 = 16;
    *((_QWORD *)v11 + 1) = v34;
    v12 = (_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                      WdfDriverGlobals,
                      v34,
                      off_14010E2B8);
    *v12 = 16;
    v12[1] = retaddr;
    Pool2 = (Event *)(v33 + 1);
    if ( v33 + 1 >= v33 )
      goto LABEL_19;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        1,
        12,
        (__int64)WPP_8af6070512533c37ff8d635f078fb2ba_Traceguids);
LABEL_17:
    Pool2 = 0;
    goto LABEL_19;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_17;
  WPP_RECORDER_SF_(
    WPP_GLOBAL_Control->DeviceExtension,
    2,
    1,
    11,
    (__int64)WPP_8af6070512533c37ff8d635f078fb2ba_Traceguids);
  Pool2 = 0;
LABEL_19:
  if ( !Pool2 || (v13 = Event::Event(Pool2, 0, 0)) == 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        1,
        32,
        (__int64)WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids);
    v13 = (DeviceCommandScheduler *)((char *)this + 96);
  }
  *((_BYTE *)v13 + 47) = 1;
  if ( this )
  {
    if ( !*((_BYTE *)v13 + 45) )
    {
      v15 = *((_DWORD *)a3 + 5);
      *((_DWORD *)v13 + 4) = 8;
      *((_QWORD *)v13 + 1) = this;
      *((_QWORD *)v13 + 4) = a3;
      *((_QWORD *)v13 + 3) = a4;
      *((_DWORD *)v13 + 10) = v15;
      goto LABEL_32;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_32;
    v14 = 11;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_32;
    v14 = 10;
  }
  LOBYTE(v7) = 2;
  WPP_RECORDER_SF_qD(
    WPP_GLOBAL_Control->DeviceExtension,
    v7,
    v8,
    v14,
    (__int64)WPP_36ec87e851083ecb6deb1777feb2ecc6_Traceguids,
    (char)v13,
    *(_DWORD *)v13);
LABEL_32:
  v16 = *((_QWORD *)this + 4);
  v17 = (_QWORD *)((char *)v13 + 48);
  v18 = v16 + 72;
  if ( !(unsigned int)Feature_54699885__private_IsEnabledDeviceUsageNoInline(Pool2, v7, v8) )
  {
    v23 = *(_QWORD *)(v16 + 32);
    *(_BYTE *)(v23 + 8) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v23);
    *(_BYTE *)(v23 + 16) = 1;
    *((_BYTE *)v13 + 45) = 1;
    v24 = *(_QWORD **)(v16 + 80);
    if ( *v24 == v18 )
    {
      *v17 = v18;
      *((_QWORD *)v13 + 7) = v24;
      *v24 = v17;
      *(_QWORD *)(v16 + 80) = v17;
      if ( *(_BYTE *)(v16 + 56) )
      {
        v26 = *(_BYTE *)(v23 + 8);
        *(_BYTE *)(v23 + 16) = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)v23, v26);
        goto LABEL_46;
      }
      *(_QWORD *)(v16 + 88) = KeGetCurrentThread();
      *(_BYTE *)(v16 + 56) = 1;
      v25 = *(_BYTE *)(v23 + 8);
      *(_BYTE *)(v23 + 16) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)v23, v25);
      goto LABEL_44;
    }
LABEL_41:
    __fastfail(3u);
  }
  v19 = *(_QWORD *)(v16 + 40);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01031 + 2528))(WdfDriverGlobals, v19);
  *((_BYTE *)v13 + 45) = 1;
  v21 = *(_QWORD **)(v16 + 80);
  if ( *v21 != v18 )
    goto LABEL_41;
  *v17 = v18;
  v22 = 0;
  v17[1] = v21;
  *v21 = v17;
  *(_QWORD *)(v16 + 80) = v17;
  if ( !*(_BYTE *)(v16 + 56) )
  {
    v22 = 1;
    *(_QWORD *)(v16 + 88) = KeGetCurrentThread();
    *(_BYTE *)(v16 + 56) = 1;
  }
  if ( v19 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01031 + 2536))(WdfDriverGlobals, v19);
  if ( v22 )
LABEL_44:
    EventQueue::ProcessEventQueueUntilEmpty((EventQueue *)v16);
LABEL_46:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v27) = 0;
    LOBYTE(v20) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v20,
      1,
      33,
      (__int64)WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids,
      v27);
  }
}

```

## disassembly

```asm
0x140015220  push    rbx
0x140015222  push    rbp
0x140015223  push    rsi
0x140015224  push    rdi
0x140015225  push    r12
0x140015227  push    r13
0x140015229  push    r15
0x14001522b  sub     rsp, 80h
0x140015232  mov     rbp, r9
0x140015235  mov     rsi, r8
0x140015238  mov     rdi, rcx
0x14001523b  lea     r15, WPP_RECORDER_INITIALIZED
0x140015242  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140015249  lea     r13, WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids
0x140015250  jz      short loc_140015282
0x140015252  mov     rcx, cs:WPP_GLOBAL_Control
0x140015259  cmp     byte ptr [rcx+29h], 5
0x14001525d  jnb     short loc_140015266
0x14001525f  cmp     word ptr [rcx+48h], 0
0x140015264  jz      short loc_140015282
0x140015266  mov     rcx, [rcx+40h]
0x14001526a  mov     r9d, 1Fh
0x140015270  mov     r8d, 1
0x140015276  mov     [rsp+0B8h+var_98], r13
0x14001527b  mov     dl, 5
0x14001527d  call    WPP_RECORDER_SF_
0x140015282  xor     r12d, r12d
0x140015285  cmp     cs:?g_Feature_56544556_MoveToWDFMemory_IsEnabled@@3_NA, r12b; bool g_Feature_56544556_MoveToWDFMemory_IsEnabled
0x14001528c  jz      loc_140015462
0x140015292  mov     rbx, [rsp+0B8h]
0x14001529a  xorps   xmm0, xmm0
0x14001529d  xor     eax, eax
0x14001529f  cmp     cs:WdfClientVersionHigherThanFramework, al
0x1400152a5  movups  [rsp+0B8h+var_78], xmm0
0x1400152aa  mov     [rsp+0B8h+var_48], rax
0x1400152af  movups  [rsp+0B8h+var_68], xmm0
0x1400152b4  movups  [rsp+0B8h+var_58], xmm0
0x1400152b9  jz      short loc_1400152E1
0x1400152bb  cmp     cs:WdfStructureCount, 26h ; '&'
0x1400152c2  jbe     short loc_1400152D7
0x1400152c4  mov     rax, cs:WdfStructures
0x1400152cb  mov     ecx, [rax+130h]
0x1400152d1  mov     dword ptr [rsp+0B8h+var_78], ecx
0x1400152d5  jmp     short loc_1400152E9
0x1400152d7  mov     dword ptr [rsp+0B8h+var_78], 0FFFFFFFFh
0x1400152df  jmp     short loc_1400152E9
0x1400152e1  mov     dword ptr [rsp+0B8h+var_78], 38h ; '8'
0x1400152e9  mov     rax, cs:off_14010E2B8
0x1400152f0  lea     rcx, [rsp+0B8h+arg_0]
0x1400152f8  mov     [rsp+0B8h+var_88], rcx
0x1400152fd  lea     rdx, [rsp+0B8h+var_78]
0x140015302  mov     [rsp+0B8h+var_48], rax
0x140015307  lea     rcx, [rsp+0B8h+arg_10]
0x14001530f  mov     rax, cs:WdfFunctions_01031
0x140015316  mov     r9d, 47696457h
0x14001531c  mov     [rsp+0B8h+var_90], rcx
0x140015321  mov     r8d, 200h
0x140015327  mov     rcx, cs:WdfDriverGlobals
0x14001532e  mov     dword ptr [rsp+0B8h+var_68+8], 1
0x140015336  mov     dword ptr [rsp+0B8h+var_68+0Ch], 1
0x14001533e  mov     [rsp+0B8h+arg_10], r12
0x140015346  mov     [rsp+0B8h+arg_0], r12
0x14001534e  mov     rax, [rax+600h]
0x140015355  mov     [rsp+0B8h+var_98], 58h ; 'X'
0x14001535e  call    _guard_dispatch_icall
0x140015363  test    eax, eax
0x140015365  jns     short loc_1400153A6
0x140015367  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001536e  jz      loc_14001545D
0x140015374  mov     rcx, cs:WPP_GLOBAL_Control
0x14001537b  lea     rax, WPP_8af6070512533c37ff8d635f078fb2ba_Traceguids
0x140015382  mov     r9d, 0Bh
0x140015388  mov     [rsp+0B8h+var_98], rax
0x14001538d  mov     r8d, 1
0x140015393  mov     dl, 2
0x140015395  mov     rcx, [rcx+40h]
0x140015399  call    WPP_RECORDER_SF_
0x14001539e  mov     rcx, r12
0x1400153a1  jmp     loc_140015481
0x1400153a6  mov     rax, [rsp+0B8h+arg_0]
0x1400153ae  xorps   xmm0, xmm0
0x1400153b1  xor     ecx, ecx
0x1400153b3  movups  xmmword ptr [rax], xmm0
0x1400153b6  movups  xmmword ptr [rax+10h], xmm0
0x1400153ba  movups  xmmword ptr [rax+20h], xmm0
0x1400153be  movups  xmmword ptr [rax+30h], xmm0
0x1400153c2  movups  xmmword ptr [rax+40h], xmm0
0x1400153c6  mov     [rax+50h], rcx
0x1400153ca  mov     rcx, [rsp+0B8h+arg_0]
0x1400153d2  mov     qword ptr [rcx], 10h
0x1400153d9  mov     rax, [rsp+0B8h+arg_10]
0x1400153e1  mov     [rcx+8], rax
0x1400153e5  mov     rax, cs:WdfFunctions_01031
0x1400153ec  mov     r8, cs:off_14010E2B8
0x1400153f3  mov     rdx, [rsp+0B8h+arg_10]
0x1400153fb  mov     rcx, cs:WdfDriverGlobals
0x140015402  mov     rax, [rax+650h]
0x140015409  call    _guard_dispatch_icall
0x14001540e  mov     qword ptr [rax], 10h
0x140015415  mov     [rax+8], rbx
0x140015419  mov     rax, [rsp+0B8h+arg_0]
0x140015421  lea     rcx, [rax+10h]
0x140015425  cmp     rcx, rax
0x140015428  jnb     short loc_140015481
0x14001542a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140015431  jz      short loc_14001545D
0x140015433  mov     rcx, cs:WPP_GLOBAL_Control
0x14001543a  lea     rax, WPP_8af6070512533c37ff8d635f078fb2ba_Traceguids
0x140015441  mov     r9d, 0Ch
0x140015447  mov     [rsp+0B8h+var_98], rax
0x14001544c  mov     r8d, 1
0x140015452  mov     dl, 2
0x140015454  mov     rcx, [rcx+40h]
0x140015458  call    WPP_RECORDER_SF_
0x14001545d  mov     rcx, r12
0x140015460  jmp     short loc_140015481
0x140015462  mov     edx, 48h ; 'H'
0x140015467  mov     ecx, 40h ; '@'
0x14001546c  mov     r8d, 47696457h
0x140015472  call    cs:__imp_ExAllocatePool2
0x140015479  nop     dword ptr [rax+rax+00h]
0x14001547e  mov     rcx, rax; this
0x140015481  test    rcx, rcx
0x140015484  jz      short loc_140015498
0x140015486  xor     r8d, r8d; unsigned int
0x140015489  xor     edx, edx; bool
0x14001548b  call    ??0Event@@QEAA@_NK@Z; Event::Event(bool,ulong)
0x140015490  mov     rbx, rax
0x140015493  test    rax, rax
0x140015496  jnz     short loc_1400154C8
0x140015498  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001549f  jz      short loc_1400154C4
0x1400154a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400154a8  mov     r9d, 20h ; ' '
0x1400154ae  mov     r8d, 1
0x1400154b4  mov     [rsp+0B8h+var_98], r13
0x1400154b9  mov     dl, 4
0x1400154bb  mov     rcx, [rcx+40h]
0x1400154bf  call    WPP_RECORDER_SF_
0x1400154c4  lea     rbx, [rdi+60h]
0x1400154c8  mov     byte ptr [rbx+2Fh], 1
0x1400154cc  test    rdi, rdi
0x1400154cf  jz      short loc_140015503
0x1400154d1  cmp     [rbx+2Dh], r12b
0x1400154d5  jz      short loc_1400154E8
0x1400154d7  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400154de  jz      short loc_14001553B
0x1400154e0  mov     r9d, 0Bh
0x1400154e6  jmp     short loc_140015512
0x1400154e8  mov     eax, [rsi+14h]
0x1400154eb  mov     dword ptr [rbx+10h], 8
0x1400154f2  mov     [rbx+8], rdi
0x1400154f6  mov     [rbx+20h], rsi
0x1400154fa  mov     [rbx+18h], rbp
0x1400154fe  mov     [rbx+28h], eax
0x140015501  jmp     short loc_14001553B
0x140015503  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001550a  jz      short loc_14001553B
0x14001550c  mov     r9d, 0Ah
0x140015512  mov     eax, [rbx]
0x140015514  mov     dl, 2
0x140015516  mov     rcx, cs:WPP_GLOBAL_Control
0x14001551d  mov     dword ptr [rsp+0B8h+var_88], eax
0x140015521  lea     rax, WPP_36ec87e851083ecb6deb1777feb2ecc6_Traceguids
0x140015528  mov     [rsp+0B8h+var_90], rbx
0x14001552d  mov     [rsp+0B8h+var_98], rax
0x140015532  mov     rcx, [rcx+40h]
0x140015536  call    WPP_RECORDER_SF_qD
0x14001553b  mov     rbp, [rdi+20h]
0x14001553f  mov     [rsp+0B8h+arg_8], r14
0x140015547  lea     rdi, [rbx+30h]
0x14001554b  lea     rsi, [rbp+48h]
0x14001554f  call    Feature_54699885__private_IsEnabledDeviceUsageNoInline
0x140015554  test    eax, eax
0x140015556  jz      loc_1400155DD
0x14001555c  mov     rax, cs:WdfFunctions_01031
0x140015563  mov     r14, [rbp+28h]
0x140015567  mov     rcx, cs:WdfDriverGlobals
0x14001556e  mov     rdx, r14
0x140015571  mov     rax, [rax+9E0h]
0x140015578  call    _guard_dispatch_icall
0x14001557d  mov     byte ptr [rbx+2Dh], 1
0x140015581  mov     rax, [rsi+8]
0x140015585  cmp     [rax], rsi
0x140015588  jnz     short loc_140015606
0x14001558a  mov     [rdi], rsi
0x14001558d  xor     bl, bl
0x14001558f  mov     [rdi+8], rax
0x140015593  mov     [rax], rdi
0x140015596  mov     [rsi+8], rdi
0x14001559a  cmp     [rbp+38h], bl
0x14001559d  jnz     short loc_1400155B2
0x14001559f  mov     rax, gs:188h
0x1400155a8  mov     bl, 1
0x1400155aa  mov     [rbp+58h], rax
0x1400155ae  mov     byte ptr [rbp+38h], 1
0x1400155b2  test    r14, r14
0x1400155b5  jz      short loc_1400155D4
0x1400155b7  mov     rax, cs:WdfFunctions_01031
0x1400155be  mov     rdx, r14
0x1400155c1  mov     rcx, cs:WdfDriverGlobals
0x1400155c8  mov     rax, [rax+9E8h]
0x1400155cf  call    _guard_dispatch_icall
0x1400155d4  test    bl, bl
0x1400155d6  jnz     short loc_14001564A
0x1400155d8  jmp     loc_140015669
0x1400155dd  mov     r14, [rbp+20h]
0x1400155e1  mov     rcx, r14; SpinLock
0x1400155e4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400155eb  nop     dword ptr [rax+rax+00h]
0x1400155f0  mov     [r14+8], al
0x1400155f4  mov     byte ptr [r14+10h], 1
0x1400155f9  mov     byte ptr [rbx+2Dh], 1
0x1400155fd  mov     rax, [rsi+8]
0x140015601  cmp     [rax], rsi
0x140015604  jz      short loc_14001560D
0x140015606  mov     ecx, 3
0x14001560b  int     29h; Win8: RtlFailFast(ecx)
0x14001560d  mov     [rdi], rsi
0x140015610  mov     rcx, r14; SpinLock
0x140015613  mov     [rdi+8], rax
0x140015617  mov     [rax], rdi
0x14001561a  mov     [rsi+8], rdi
0x14001561e  cmp     [rbp+38h], r12b
0x140015622  jnz     short loc_140015654
0x140015624  mov     rax, gs:188h
0x14001562d  mov     [rbp+58h], rax
0x140015631  mov     byte ptr [rbp+38h], 1
0x140015635  movzx   edx, byte ptr [r14+8]; NewIrql
0x14001563a  mov     [r14+10h], r12b
0x14001563e  call    cs:__imp_KeReleaseSpinLock
0x140015645  nop     dword ptr [rax+rax+00h]
0x14001564a  mov     rcx, rbp; this
0x14001564d  call    ?ProcessEventQueueUntilEmpty@EventQueue@@IEAAXXZ; EventQueue::ProcessEventQueueUntilEmpty(void)
0x140015652  jmp     short loc_140015669
0x140015654  movzx   edx, byte ptr [r14+8]; NewIrql
0x140015659  mov     [r14+10h], r12b
0x14001565d  call    cs:__imp_KeReleaseSpinLock
0x140015664  nop     dword ptr [rax+rax+00h]
0x140015669  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140015670  jz      short loc_1400156A7
0x140015672  mov     rcx, cs:WPP_GLOBAL_Control
0x140015679  cmp     byte ptr [rcx+29h], 5
0x14001567d  jnb     short loc_140015686
0x14001567f  cmp     [rcx+48h], r12w
0x140015684  jz      short loc_1400156A7
0x140015686  mov     rcx, [rcx+40h]
0x14001568a  mov     r9d, 21h ; '!'
0x140015690  mov     dword ptr [rsp+0B8h+var_90], r12d
0x140015695  mov     r8d, 1
0x14001569b  mov     dl, 5
0x14001569d  mov     [rsp+0B8h+var_98], r13
0x1400156a2  call    WPP_RECORDER_SF_d
0x1400156a7  mov     r14, [rsp+0B8h+arg_8]
0x1400156af  add     rsp, 80h
0x1400156b6  pop     r15
0x1400156b8  pop     r13
0x1400156ba  pop     r12
0x1400156bc  pop     rdi
0x1400156bd  pop     rsi
0x1400156be  pop     rbp
0x1400156bf  pop     rbx
0x1400156c0  retn
```
