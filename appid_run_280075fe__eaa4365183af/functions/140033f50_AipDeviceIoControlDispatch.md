# AipDeviceIoControlDispatch

- ea: `0x140033f50`
- end: `0x140034548`
- name: `AipDeviceIoControlDispatch`
- size: `1528`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1400016a8`
- `0x1400016d8`
- `0x140006a20`
- `0x14001f340`
- `0x14001fef0`
- `0x140021860`
- `0x140021924`
- `0x140021c3c`
- `0x1400232c8`
- `0x14002351c`
- `0x1400236ac`
- `0x140023a40`
- `0x140024184`
- `0x140024218`
- `0x140025ba0`
- `0x140025e3c`
- `0x140025f90`
- `0x140033f50`
- `0x140034550`
- `0x1400360a0`

## import_xrefs

- `ntoskrnl!ZwSetEvent` at `0x140034087`
- `ntoskrnl!ZwSetEvent` at `0x140034087`
- `ntoskrnl!ExGetPreviousMode` at `0x140034152`
- `ntoskrnl!ExGetPreviousMode` at `0x1400341a2`
- `ntoskrnl!ExGetPreviousMode` at `0x140034152`
- `ntoskrnl!ExGetPreviousMode` at `0x1400341a2`
- `ntoskrnl!ZwResetEvent` at `0x1400340e7`
- `ntoskrnl!ZwResetEvent` at `0x1400340e7`
- `ntoskrnl!IofCompleteRequest` at `0x140034512`
- `ntoskrnl!IofCompleteRequest` at `0x140034512`

## pseudocode

```c
__int64 __fastcall AipDeviceIoControlDispatch(struct _DEVICE_OBJECT *a1, __int64 a2)
{
  __int64 v4; // rsi
  __int64 v5; // r9
  int ConfigOptions; // eax
  int v7; // edi
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  PDEVICE_OBJECT v10; // rcx
  int v11; // eax
  int v12; // eax
  LONG PreviousState[4]; // [rsp+30h] [rbp-98h] BYREF
  _QWORD v15[3]; // [rsp+40h] [rbp-88h] BYREF
  int v16; // [rsp+58h] [rbp-70h]
  int v17; // [rsp+5Ch] [rbp-6Ch]
  __int64 v18; // [rsp+60h] [rbp-68h]
  int v19; // [rsp+68h] [rbp-60h]
  int v20; // [rsp+6Ch] [rbp-5Ch]
  __int64 v21; // [rsp+70h] [rbp-58h]
  int v22; // [rsp+78h] [rbp-50h]
  int v23; // [rsp+7Ch] [rbp-4Ch]
  __int64 v24; // [rsp+80h] [rbp-48h]
  __int64 v25; // [rsp+88h] [rbp-40h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
  v4 = *(_QWORD *)(a2 + 184);
  *(_QWORD *)(a2 + 56) = 0;
  v5 = *(unsigned int *)(v4 + 24);
  if ( WPP_MAIN_CB.DeviceExtension == a1 )
  {
    switch ( (int)v5 )
    {
      case 2269184:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
        ConfigOptions = AiReloadCertificate(*(_QWORD *)(a2 + 24), *(unsigned int *)(v4 + 16));
        goto LABEL_95;
      case 2269192:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
        v7 = AiServiceStarted(*(void **)(v4 + 48));
        if ( v7 >= 0 )
          WPP_MAIN_CB.Dpc.SystemArgument2 = *(PVOID *)(v4 + 48);
        PreviousState[0] = 0;
        ZwSetEvent(Handle, PreviousState);
        goto LABEL_96;
      case 2269196:
        PreviousState[0] = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
        v7 = AiServiceStopped(*(_QWORD *)(v4 + 48));
        if ( v7 >= 0 )
          WPP_MAIN_CB.Dpc.SystemArgument2 = 0;
        ZwResetEvent(Handle, PreviousState);
        goto LABEL_96;
      case 2269200:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
        ConfigOptions = AipReadConfigOptions();
        goto LABEL_95;
      case 2269204:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
        if ( ExGetPreviousMode() )
          goto LABEL_42;
        ConfigOptions = AipGetTrackObjects(*(_QWORD *)(a2 + 24), *(unsigned int *)(v4 + 8), a2 + 56);
        goto LABEL_95;
      case 2269208:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
        if ( ExGetPreviousMode() )
          goto LABEL_42;
        if ( *(_DWORD *)(v4 + 16) != 32 )
          goto LABEL_36;
        ConfigOptions = AipSmartHashImageFile(*(_QWORD *)(a2 + 24), 0, 0, 0);
        break;
      default:
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
          goto LABEL_42;
        v9 = 28;
        goto LABEL_41;
    }
    goto LABEL_95;
  }
  if ( DeviceObject != a1 )
  {
    v11 = *(_DWORD *)(v4 + 16);
    v18 = *(_QWORD *)(a2 + 24);
    v21 = v18;
    v19 = v11;
    v12 = *(_DWORD *)(v4 + 8);
    v15[0] = 0;
    v15[1] = 0;
    v17 = 0;
    v20 = 0;
    v23 = 0;
    v25 = 0;
    v15[2] = a1;
    v16 = v5;
    v22 = v12;
    v24 = a2 + 56;
    ConfigOptions = AipPluginsDeviceIoControlDispatch(v15);
    goto LABEL_95;
  }
  if ( (_DWORD)v5 == 2250756 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
    ConfigOptions = SrpVerifyDll(
                      *(_QWORD *)(a2 + 24),
                      *(_DWORD *)(v4 + 16),
                      *(int **)(a2 + 24),
                      *(_DWORD *)(v4 + 8),
                      *(_BYTE *)(a2 + 64),
                      (_QWORD *)(a2 + 56));
    goto LABEL_95;
  }
  if ( (unsigned int)v5 <= 0x229808 )
  {
    switch ( (_DWORD)v5 )
    {
      case 0x229808:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
        ConfigOptions = SrpGetHitCount(*(wchar_t **)(a2 + 24), a2 + 56);
        goto LABEL_95;
      case 0x225818:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
        ConfigOptions = SrpInheritOrigin(*(_QWORD *)(a2 + 24), *(unsigned int *)(v4 + 16));
        goto LABEL_95;
      case 0x22581C:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
        ConfigOptions = SrpOpenTrackInstallIoctl();
        goto LABEL_95;
      case 0x225820:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
        ConfigOptions = SrpCloseTrackInstallIoctl();
        goto LABEL_95;
      case 0x229800:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
        ConfigOptions = SrpUpdatePolicy();
        goto LABEL_95;
    }
    goto LABEL_74;
  }
  if ( (_DWORD)v5 == 2267148 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
    ConfigOptions = AipTransactionBegin(
                      *(_QWORD *)(a2 + 24),
                      *(_DWORD *)(v4 + 16),
                      *(_QWORD *)(a2 + 24),
                      *(_DWORD *)(v4 + 8),
                      a2 + 56);
    goto LABEL_95;
  }
  if ( (_DWORD)v5 == 2267152 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
    if ( *(_DWORD *)(v4 + 16) != 16 )
    {
LABEL_36:
      v7 = -1073741811;
      goto LABEL_96;
    }
    ConfigOptions = SrpPolicyTransactionCommit(*(_QWORD *)(a2 + 24));
LABEL_95:
    v7 = ConfigOptions;
    goto LABEL_96;
  }
  if ( (_DWORD)v5 != 2267156 )
  {
LABEL_74:
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      v9 = 38;
LABEL_41:
      WPP_SF_D(v8->AttachedDevice, v9, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids, v5);
    }
LABEL_42:
    v7 = -1073741808;
    goto LABEL_96;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
  SrpPolicyTransactionRollback(v10, a2);
  v7 = 0;
LABEL_96:
  *(_DWORD *)(a2 + 48) = v7;
  IofCompleteRequest((PIRP)a2, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140033f50  mov     [rsp+arg_10], rbx
0x140033f55  push    rbp
0x140033f56  push    rsi
0x140033f57  push    rdi
0x140033f58  push    r14
0x140033f5a  push    r15
0x140033f5c  sub     rsp, 0A0h
0x140033f63  mov     rax, cs:__security_cookie
0x140033f6a  xor     rax, rsp
0x140033f6d  mov     [rsp+0C8h+var_38], rax
0x140033f75  mov     rbx, rdx
0x140033f78  mov     rdi, rcx
0x140033f7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140033f82  lea     rbp, WPP_GLOBAL_Control
0x140033f89  cmp     rcx, rbp
0x140033f8c  jz      short loc_140033FAA
0x140033f8e  mov     eax, [rcx+2Ch]
0x140033f91  test    al, 2
0x140033f93  jz      short loc_140033FAA
0x140033f95  mov     rcx, [rcx+18h]
0x140033f99  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x140033fa0  mov     edx, 14h
0x140033fa5  call    WPP_SF_
0x140033faa  mov     rsi, [rbx+0B8h]
0x140033fb1  lea     r14, [rbx+38h]
0x140033fb5  xor     r15d, r15d
0x140033fb8  mov     [r14], r15
0x140033fbb  cmp     cs:WPP_MAIN_CB.DeviceExtension, rdi
0x140033fc2  mov     r9d, [rsi+18h]
0x140033fc6  jnz     loc_14003420A
0x140033fcc  lea     eax, [r9-22A000h]; switch 25 cases
0x140033fd3  cmp     eax, 18h
0x140033fd6  ja      def_140033FF5; jumptable 0000000140033FF5 default case, cases 2269185-2269191,2269193-2269195,2269197-2269199,2269201-2269203,2269205-2269207
0x140033fdc  lea     rdx, cs:140000000h
0x140033fe3  movzx   eax, ds:(byte_140015D1C - 140000000h)[rdx+rax]
0x140033feb  mov     ecx, ds:(jpt_140033FF5 - 140000000h)[rdx+rax*4]
0x140033ff2  add     rcx, rdx
0x140033ff5  jmp     rcx; switch jump
0x140033ffb  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000140033FF5 case 2269184
0x140034002  cmp     rcx, rbp
0x140034005  jz      short loc_140034023
0x140034007  mov     eax, [rcx+2Ch]
0x14003400a  test    al, 2
0x14003400c  jz      short loc_140034023
0x14003400e  mov     rcx, [rcx+18h]
0x140034012  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x140034019  mov     edx, 15h
0x14003401e  call    WPP_SF_
0x140034023  mov     edx, [rsi+10h]
0x140034026  mov     rcx, [rbx+18h]
0x14003402a  call    AiReloadCertificate
0x14003402f  jmp     loc_140034508
0x140034034  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000140033FF5 case 2269192
0x14003403b  cmp     rcx, rbp
0x14003403e  jz      short loc_14003405C
0x140034040  mov     eax, [rcx+2Ch]
0x140034043  test    al, 2
0x140034045  jz      short loc_14003405C
0x140034047  mov     rcx, [rcx+18h]
0x14003404b  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x140034052  mov     edx, 17h
0x140034057  call    WPP_SF_
0x14003405c  mov     rcx, [rsi+30h]
0x140034060  call    AiServiceStarted
0x140034065  mov     edi, eax
0x140034067  test    eax, eax
0x140034069  js      short loc_140034076
0x14003406b  mov     rax, [rsi+30h]
0x14003406f  mov     cs:WPP_MAIN_CB.Dpc.SystemArgument2, rax
0x140034076  mov     rcx, cs:Handle; EventHandle
0x14003407d  lea     rdx, [rsp+0C8h+PreviousState]; PreviousState
0x140034082  mov     [rsp+0C8h+PreviousState], r15d
0x140034087  call    cs:__imp_ZwSetEvent
0x14003408e  nop     dword ptr [rax+rax+00h]
0x140034093  jmp     loc_14003450A
0x140034098  mov     [rsp+0C8h+PreviousState], r15d; jumptable 0000000140033FF5 case 2269196
0x14003409d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400340a4  cmp     rcx, rbp
0x1400340a7  jz      short loc_1400340C5
0x1400340a9  mov     eax, [rcx+2Ch]
0x1400340ac  test    al, 2
0x1400340ae  jz      short loc_1400340C5
0x1400340b0  mov     rcx, [rcx+18h]
0x1400340b4  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x1400340bb  mov     edx, 18h
0x1400340c0  call    WPP_SF_
0x1400340c5  mov     rcx, [rsi+30h]
0x1400340c9  call    AiServiceStopped
0x1400340ce  mov     edi, eax
0x1400340d0  test    eax, eax
0x1400340d2  js      short loc_1400340DB
0x1400340d4  mov     cs:WPP_MAIN_CB.Dpc.SystemArgument2, r15
0x1400340db  mov     rcx, cs:Handle; EventHandle
0x1400340e2  lea     rdx, [rsp+0C8h+PreviousState]; NumberOfWaitingThreads
0x1400340e7  call    cs:__imp_ZwResetEvent
0x1400340ee  nop     dword ptr [rax+rax+00h]
0x1400340f3  jmp     loc_14003450A
0x1400340f8  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000140033FF5 case 2269200
0x1400340ff  cmp     rcx, rbp
0x140034102  jz      short loc_140034120
0x140034104  mov     eax, [rcx+2Ch]
0x140034107  test    al, 2
0x140034109  jz      short loc_140034120
0x14003410b  mov     rcx, [rcx+18h]
0x14003410f  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x140034116  mov     edx, 19h
0x14003411b  call    WPP_SF_
0x140034120  call    AipReadConfigOptions
0x140034125  jmp     loc_140034508
0x14003412a  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000140033FF5 case 2269204
0x140034131  cmp     rcx, rbp
0x140034134  jz      short loc_140034152
0x140034136  mov     eax, [rcx+2Ch]
0x140034139  test    al, 2
0x14003413b  jz      short loc_140034152
0x14003413d  mov     rcx, [rcx+18h]
0x140034141  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x140034148  mov     edx, 1Ah
0x14003414d  call    WPP_SF_
0x140034152  call    cs:__imp_ExGetPreviousMode
0x140034159  nop     dword ptr [rax+rax+00h]
0x14003415e  test    al, al
0x140034160  jnz     loc_140034200
0x140034166  mov     rcx, [rbx+18h]
0x14003416a  mov     r8, r14
0x14003416d  mov     edx, [rsi+8]
0x140034170  call    AipGetTrackObjects
0x140034175  jmp     loc_140034508
0x14003417a  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000140033FF5 case 2269208
0x140034181  cmp     rcx, rbp
0x140034184  jz      short loc_1400341A2
0x140034186  mov     eax, [rcx+2Ch]
0x140034189  test    al, 2
0x14003418b  jz      short loc_1400341A2
0x14003418d  mov     rcx, [rcx+18h]
0x140034191  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x140034198  mov     edx, 1Bh
0x14003419d  call    WPP_SF_
0x1400341a2  call    cs:__imp_ExGetPreviousMode
0x1400341a9  nop     dword ptr [rax+rax+00h]
0x1400341ae  test    al, al
0x1400341b0  jnz     short loc_140034200
0x1400341b2  cmp     dword ptr [rsi+10h], 20h ; ' '
0x1400341b6  jz      short loc_1400341C2
0x1400341b8  mov     edi, 0C000000Dh
0x1400341bd  jmp     loc_14003450A
0x1400341c2  mov     rcx, [rbx+18h]
0x1400341c6  xor     r9d, r9d
0x1400341c9  xor     r8d, r8d
0x1400341cc  xor     edx, edx
0x1400341ce  call    AipSmartHashImageFile
0x1400341d3  jmp     loc_140034508
0x1400341d8  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000140033FF5 default case, cases 2269185-2269191,2269193-2269195,2269197-2269199,2269201-2269203,2269205-2269207
0x1400341df  cmp     rcx, rbp
0x1400341e2  jz      short loc_140034200
0x1400341e4  mov     eax, [rcx+2Ch]
0x1400341e7  test    al, 2
0x1400341e9  jz      short loc_140034200
0x1400341eb  mov     edx, 1Ch
0x1400341f0  mov     rcx, [rcx+18h]
0x1400341f4  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x1400341fb  call    WPP_SF_D
0x140034200  mov     edi, 0C0000010h
0x140034205  jmp     loc_14003450A
0x14003420a  cmp     cs:DeviceObject, rdi
0x140034211  jnz     loc_1400344AF
0x140034217  cmp     r9d, 225804h
0x14003421e  jz      loc_140034465
0x140034224  cmp     r9d, 229808h
0x14003422b  ja      loc_14003436E
0x140034231  jz      loc_140034329
0x140034237  mov     eax, r9d
0x14003423a  sub     eax, 225818h
0x14003423f  jz      loc_1400342F0
0x140034245  sub     eax, 4
0x140034248  jz      short loc_1400342BE
0x14003424a  sub     eax, 4
0x14003424d  jz      short loc_14003428C
0x14003424f  cmp     eax, 3FE0h
0x140034254  jnz     loc_140034386
0x14003425a  mov     rcx, cs:WPP_GLOBAL_Control
0x140034261  cmp     rcx, rbp
0x140034264  jz      short loc_140034282
0x140034266  mov     eax, [rcx+2Ch]
0x140034269  test    al, 2
0x14003426b  jz      short loc_140034282
0x14003426d  mov     rcx, [rcx+18h]
0x140034271  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x140034278  mov     edx, 1Dh
0x14003427d  call    WPP_SF_
0x140034282  call    SrpUpdatePolicy
0x140034287  jmp     loc_140034508
0x14003428c  mov     rcx, cs:WPP_GLOBAL_Control
0x140034293  cmp     rcx, rbp
0x140034296  jz      short loc_1400342B4
0x140034298  mov     eax, [rcx+2Ch]
0x14003429b  test    al, 2
0x14003429d  jz      short loc_1400342B4
0x14003429f  mov     rcx, [rcx+18h]
0x1400342a3  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x1400342aa  mov     edx, 25h ; '%'
0x1400342af  call    WPP_SF_
0x1400342b4  call    SrpCloseTrackInstallIoctl
0x1400342b9  jmp     loc_140034508
0x1400342be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400342c5  cmp     rcx, rbp
0x1400342c8  jz      short loc_1400342E6
0x1400342ca  mov     eax, [rcx+2Ch]
0x1400342cd  test    al, 2
0x1400342cf  jz      short loc_1400342E6
0x1400342d1  mov     rcx, [rcx+18h]
0x1400342d5  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x1400342dc  mov     edx, 24h ; '$'
0x1400342e1  call    WPP_SF_
0x1400342e6  call    SrpOpenTrackInstallIoctl
0x1400342eb  jmp     loc_140034508
0x1400342f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400342f7  cmp     rcx, rbp
0x1400342fa  jz      short loc_140034318
0x1400342fc  mov     eax, [rcx+2Ch]
0x1400342ff  test    al, 2
0x140034301  jz      short loc_140034318
0x140034303  mov     rcx, [rcx+18h]
0x140034307  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x14003430e  mov     edx, 23h ; '#'
0x140034313  call    WPP_SF_
0x140034318  mov     edx, [rsi+10h]
0x14003431b  mov     rcx, [rbx+18h]
0x14003431f  call    SrpInheritOrigin
0x140034324  jmp     loc_140034508
0x140034329  mov     rcx, cs:WPP_GLOBAL_Control
0x140034330  cmp     rcx, rbp
0x140034333  jz      short loc_140034351
0x140034335  mov     eax, [rcx+2Ch]
0x140034338  test    al, 2
0x14003433a  jz      short loc_140034351
0x14003433c  mov     rcx, [rcx+18h]
0x140034340  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x140034347  mov     edx, 1Fh
0x14003434c  call    WPP_SF_
0x140034351  mov     rcx, [rbx+18h]; Str1
0x140034355  mov     r9d, [rsi+8]
0x140034359  mov     r8, rcx
0x14003435c  mov     edx, [rsi+10h]
0x14003435f  mov     [rsp+0C8h+var_A8], r14; __int64
0x140034364  call    SrpGetHitCount
0x140034369  jmp     loc_140034508
0x14003436e  mov     eax, r9d
0x140034371  sub     eax, 22980Ch
0x140034376  jz      loc_140034420
0x14003437c  sub     eax, 4
0x14003437f  jz      short loc_1400343E0
0x140034381  cmp     eax, 4
0x140034384  jz      short loc_1400343AB
0x140034386  mov     rcx, cs:WPP_GLOBAL_Control
0x14003438d  cmp     rcx, rbp
0x140034390  jz      loc_140034200
0x140034396  mov     eax, [rcx+2Ch]
0x140034399  test    al, 2
0x14003439b  jz      loc_140034200
0x1400343a1  mov     edx, 26h ; '&'
0x1400343a6  jmp     loc_1400341F0
0x1400343ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400343b2  cmp     rcx, rbp
0x1400343b5  jz      short loc_1400343D3
0x1400343b7  mov     eax, [rcx+2Ch]
0x1400343ba  test    al, 2
0x1400343bc  jz      short loc_1400343D3
0x1400343be  mov     rcx, [rcx+18h]
0x1400343c2  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x1400343c9  mov     edx, 22h ; '"'
0x1400343ce  call    WPP_SF_
0x1400343d3  call    SrpPolicyTransactionRollback
0x1400343d8  mov     edi, r15d
0x1400343db  jmp     loc_14003450A
0x1400343e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400343e7  cmp     rcx, rbp
0x1400343ea  jz      short loc_140034408
0x1400343ec  mov     eax, [rcx+2Ch]
0x1400343ef  test    al, 2
0x1400343f1  jz      short loc_140034408
0x1400343f3  mov     rcx, [rcx+18h]
0x1400343f7  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x1400343fe  mov     edx, 21h ; '!'
0x140034403  call    WPP_SF_
0x140034408  cmp     dword ptr [rsi+10h], 10h
0x14003440c  jnz     loc_1400341B8
0x140034412  mov     rcx, [rbx+18h]
0x140034416  call    SrpPolicyTransactionCommit
0x14003441b  jmp     loc_140034508
0x140034420  mov     rcx, cs:WPP_GLOBAL_Control
0x140034427  cmp     rcx, rbp
0x14003442a  jz      short loc_140034448
0x14003442c  mov     eax, [rcx+2Ch]
0x14003442f  test    al, 2
0x140034431  jz      short loc_140034448
0x140034433  mov     rcx, [rcx+18h]
0x140034437  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x14003443e  mov     edx, 20h ; ' '
0x140034443  call    WPP_SF_
  ... truncated ...
```
