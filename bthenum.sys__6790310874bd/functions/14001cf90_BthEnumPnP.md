# BthEnumPnP

- ea: `0x14001cf90`
- end: `0x14001d438`
- name: `BthEnumPnP`
- size: `1192`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x140001328`
- `0x1400013e8`
- `0x1400024c0`
- `0x140002568`
- `0x140002634`
- `0x140002a28`
- `0x140002e4c`
- `0x140007d00`
- `0x140007d40`
- `0x140019058`
- `0x14001ce58`
- `0x14001cf90`
- `0x14001d4fc`
- `0x14001d7d8`
- `0x14001de14`
- `0x14001f520`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14001d3e4`
- `ntoskrnl!ZwClose` at `0x14001d3e4`
- `ntoskrnl!IofCompleteRequest` at `0x14001d049`
- `ntoskrnl!IofCompleteRequest` at `0x14001d3f8`
- `ntoskrnl!IofCompleteRequest` at `0x14001d049`
- `ntoskrnl!IofCompleteRequest` at `0x14001d3f8`
- `ntoskrnl!IofCallDriver` at `0x14001d1a4`
- `ntoskrnl!IofCallDriver` at `0x14001d1a4`
- `ntoskrnl!IoDeleteDevice` at `0x14001d2cb`
- `ntoskrnl!IoDeleteDevice` at `0x14001d2cb`
- `ntoskrnl!IoDetachDevice` at `0x14001d1be`
- `ntoskrnl!IoDetachDevice` at `0x14001d1be`
- `ntoskrnl!ExFreePool` at `0x14001d223`
- `ntoskrnl!ExFreePool` at `0x14001d282`
- `ntoskrnl!ExFreePool` at `0x14001d29c`
- `ntoskrnl!ExFreePool` at `0x14001d2b8`
- `ntoskrnl!ExFreePool` at `0x14001d223`
- `ntoskrnl!ExFreePool` at `0x14001d282`
- `ntoskrnl!ExFreePool` at `0x14001d29c`
- `ntoskrnl!ExFreePool` at `0x14001d2b8`

## string_xrefs

- `0x14001d39c`: `\Registry\Machine\System\CurrentControlSet\Services\BTHPORT\Parameters`

## pseudocode

```c
__int64 __fastcall BthEnumPnP(PDEVICE_OBJECT DeviceObject, __int64 Irp, int a3, int a4)
{
  int *DeviceExtension; // rbx
  PIRP v6; // rdi
  int v7; // ecx
  unsigned __int64 v8; // rax
  _IO_STACK_LOCATION *CurrentStackLocation; // r15
  PIRP v11; // rdx
  int DeviceList; // eax
  int LocalRadioInfo; // ebp
  _IO_STACK_LOCATION *v14; // rax
  unsigned int v15; // edi
  int v16; // edx
  void *v17; // rcx
  int v18; // edx
  __int64 v19; // rcx
  void *v20; // r14
  __int64 v21; // rbx
  HANDLE Handle; // [rsp+40h] [rbp-68h] BYREF
  _QWORD v23[2]; // [rsp+48h] [rbp-60h]
  _BYTE v24[24]; // [rsp+58h] [rbp-50h] BYREF

  DeviceExtension = (int *)DeviceObject->DeviceExtension;
  v6 = (PIRP)Irp;
  v7 = *DeviceExtension;
  if ( *DeviceExtension == 542065744 )
    return BthEnumPdoPnp(DeviceObject, v6);
  v8 = (unsigned int)(v7 - 1329877060);
  if ( (unsigned int)v8 <= 0x34 )
  {
    Irp = 0x10000000010001LL;
    if ( _bittest64(&Irp, v8) )
      return BthEnumPdoPnp(DeviceObject, v6);
  }
  if ( v7 == 1146115192 || v7 == 1146111096 )
    return BthEnumPdoPnp(DeviceObject, v6);
  if ( v7 != 542065734 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        Irp,
        1,
        15,
        (__int64)WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids);
    v6->IoStatus.Status = 0;
    IofCompleteRequest(v6, 0);
    return 0;
  }
  CurrentStackLocation = v6->Tail.Overlay.CurrentStackLocation;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_c(WPP_GLOBAL_Control->DeviceExtension, Irp, a3, a4);
  if ( !CurrentStackLocation->MinorFunction )
  {
    v11 = v6;
    if ( *((_BYTE *)DeviceExtension + 34) )
      goto LABEL_44;
    LocalRadioInfo = WaitForLowerDriverToCompleteIrp(*((PDEVICE_OBJECT *)DeviceExtension + 3), v6);
    if ( LocalRadioInfo >= 0 )
    {
      if ( *((_QWORD *)DeviceExtension + 29) )
      {
        *((_BYTE *)DeviceExtension + 34) = 1;
        DeviceExtension[9] = 1;
      }
      else
      {
        LocalRadioInfo = BthEnumGetLocalRadioInfo(DeviceObject);
        if ( LocalRadioInfo >= 0 )
        {
          LocalRadioInfo = BthEnumQueryProtocol(DeviceObject);
          if ( LocalRadioInfo >= 0 )
          {
            LocalRadioInfo = BthEnumQueryEnumeratorInterface(DeviceObject);
            if ( LocalRadioInfo >= 0 )
            {
              DeviceExtension[9] = 1;
              *((_BYTE *)DeviceExtension + 34) = 1;
              v20 = DeviceObject->DeviceExtension;
              v23[0] = &BthEnumRegUpdateWWCapableCodMasks;
              Handle = 0;
              v23[1] = 0;
              if ( (int)BthOpenKey(
                          v19,
                          L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\BTHPORT\\Parameters",
                          &Handle) >= 0 )
              {
                LODWORD(v21) = 0;
                do
                {
                  ((void (__fastcall *)(void *, HANDLE, _BYTE *))v23[(unsigned int)v21])(v20, Handle, v24);
                  v21 = (unsigned int)(v21 + 1);
                }
                while ( v23[v21] );
                ZwClose(Handle);
              }
            }
          }
        }
      }
    }
    v6->IoStatus.Status = LocalRadioInfo;
    goto LABEL_57;
  }
  if ( CurrentStackLocation->MinorFunction == 1 )
  {
LABEL_29:
    v11 = v6;
LABEL_44:
    v6->IoStatus.Status = 0;
    return ForwardIrp(*((_QWORD *)DeviceExtension + 3), v11);
  }
  if ( CurrentStackLocation->MinorFunction != 2 )
  {
    if ( CurrentStackLocation->MinorFunction != 3 )
    {
      switch ( CurrentStackLocation->MinorFunction )
      {
        case 4u:
          *((_BYTE *)DeviceExtension + 34) = 0;
          break;
        case 5u:
        case 6u:
          break;
        case 7u:
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_dD(WPP_GLOBAL_Control->DeviceExtension, Irp, a3, a4);
          v11 = v6;
          if ( CurrentStackLocation->Parameters.Read.Length )
            return ForwardIrp(*((_QWORD *)DeviceExtension + 3), v11);
          DeviceList = BthEnumGetDeviceList((__int64)DeviceExtension, (__int64)v6);
          v6->IoStatus.Status = DeviceList;
          LocalRadioInfo = DeviceList;
          if ( DeviceList >= 0 )
            goto LABEL_27;
LABEL_57:
          IofCompleteRequest(v6, 0);
          return (unsigned int)LocalRadioInfo;
        case 0x17u:
          goto LABEL_29;
        default:
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              Irp,
              3,
              21,
              (__int64)WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids);
LABEL_27:
          v11 = v6;
          return ForwardIrp(*((_QWORD *)DeviceExtension + 3), v11);
      }
    }
    goto LABEL_29;
  }
  *((_WORD *)DeviceExtension + 16) = 257;
  v14 = v6->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&v14[-1].MajorFunction = *(_OWORD *)&v14->MajorFunction;
  *(_OWORD *)&v14[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v14->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v14[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v14->Parameters.SetQuota + 6);
  v14[-1].FileObject = v14->FileObject;
  v14[-1].Control = 0;
  v15 = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 3), v6);
  BthEnumDeleteAllPdos(DeviceExtension);
  IoDetachDevice(*((PDEVICE_OBJECT *)DeviceExtension + 3));
  *DeviceExtension = 1329874552;
  if ( *((_QWORD *)DeviceExtension + 29) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        3,
        18,
        (__int64)WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids);
    (*(void (__fastcall **)(_QWORD))(*((_QWORD *)DeviceExtension + 29) + 24LL))(*(_QWORD *)(*((_QWORD *)DeviceExtension
                                                                                            + 29)
                                                                                          + 8LL));
    ExFreePool(*((PVOID *)DeviceExtension + 29));
    *((_QWORD *)DeviceExtension + 29) = 0;
  }
  if ( *((_QWORD *)DeviceExtension + 30) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        3,
        19,
        (__int64)WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids);
    (*(void (__fastcall **)(_QWORD))(*((_QWORD *)DeviceExtension + 30) + 24LL))(*(_QWORD *)(*((_QWORD *)DeviceExtension
                                                                                            + 30)
                                                                                          + 8LL));
    ExFreePool(*((PVOID *)DeviceExtension + 30));
    *((_QWORD *)DeviceExtension + 30) = 0;
  }
  ExFreePool(*((PVOID *)DeviceExtension + 28));
  v17 = (void *)*((_QWORD *)DeviceExtension + 15);
  *((_QWORD *)DeviceExtension + 28) = 0;
  if ( v17 )
  {
    ExFreePool(v17);
    *((_QWORD *)DeviceExtension + 15) = 0;
  }
  IoDeleteDevice(DeviceObject);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v18,
      3,
      20,
      (__int64)WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids,
      v15);
  return v15;
}

```

## disassembly

```asm
0x14001cf90  mov     [rsp+arg_10], rbx
0x14001cf95  push    rbp
0x14001cf96  push    rsi
0x14001cf97  push    rdi
0x14001cf98  push    r14
0x14001cf9a  push    r15
0x14001cf9c  sub     rsp, 80h
0x14001cfa3  mov     rax, cs:__security_cookie
0x14001cfaa  xor     rax, rsp
0x14001cfad  mov     [rsp+0A8h+var_38], rax
0x14001cfb2  mov     rbx, [rcx+40h]
0x14001cfb6  mov     r14, rcx
0x14001cfb9  mov     rdi, rdx
0x14001cfbc  mov     ecx, [rbx]
0x14001cfbe  cmp     ecx, 204F4450h
0x14001cfc4  jz      loc_14001D408
0x14001cfca  lea     eax, [rcx-4F445044h]
0x14001cfd0  cmp     eax, 34h ; '4'
0x14001cfd3  ja      short loc_14001CFE9
0x14001cfd5  mov     rdx, 10000000010001h
0x14001cfdf  bt      rdx, rax
0x14001cfe3  jb      loc_14001D408
0x14001cfe9  cmp     ecx, 44505478h
0x14001cfef  jz      loc_14001D408
0x14001cff5  cmp     ecx, 44504478h
0x14001cffb  jz      loc_14001D408
0x14001d001  cmp     ecx, 204F4446h
0x14001d007  jz      short loc_14001D05C
0x14001d009  lea     rbp, WPP_RECORDER_INITIALIZED
0x14001d010  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001d017  jz      short loc_14001D03F
0x14001d019  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d020  lea     r15, WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids
0x14001d027  mov     r9d, 0Fh
0x14001d02d  mov     [rsp+0A8h+var_88], r15
0x14001d032  mov     rcx, [rcx+40h]
0x14001d036  lea     r8d, [r9-0Eh]
0x14001d03a  call    WPP_RECORDER_SF_
0x14001d03f  xor     esi, esi
0x14001d041  xor     edx, edx; PriorityBoost
0x14001d043  mov     rcx, rdi; Irp
0x14001d046  mov     [rdi+30h], esi
0x14001d049  call    cs:__imp_IofCompleteRequest
0x14001d050  nop     dword ptr [rax+rax+00h]
0x14001d055  xor     eax, eax
0x14001d057  jmp     loc_14001D413
0x14001d05c  mov     r15, [rdi+0B8h]
0x14001d063  lea     rbp, WPP_RECORDER_INITIALIZED
0x14001d06a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001d071  jz      short loc_14001D08B
0x14001d073  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d07a  mov     al, [r15+1]
0x14001d07e  mov     byte ptr [rsp+0A8h+var_80], al
0x14001d082  mov     rcx, [rcx+40h]
0x14001d086  call    WPP_RECORDER_SF_c
0x14001d08b  movzx   ecx, byte ptr [r15+1]
0x14001d090  xor     esi, esi
0x14001d092  test    ecx, ecx
0x14001d094  jz      loc_14001D30A
0x14001d09a  sub     ecx, 1
0x14001d09d  jz      loc_14001D163
0x14001d0a3  sub     ecx, 1
0x14001d0a6  jz      loc_14001D16B
0x14001d0ac  sub     ecx, 1
0x14001d0af  jz      loc_14001D163
0x14001d0b5  sub     ecx, 1
0x14001d0b8  jz      loc_14001D15F
0x14001d0be  sub     ecx, 1
0x14001d0c1  jz      loc_14001D163
0x14001d0c7  sub     ecx, 1
0x14001d0ca  jz      loc_14001D163
0x14001d0d0  sub     ecx, 1
0x14001d0d3  jz      short loc_14001D10D
0x14001d0d5  cmp     ecx, 10h
0x14001d0d8  jz      loc_14001D163
0x14001d0de  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001d0e5  jz      short loc_14001D157
0x14001d0e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d0ee  lea     r15, WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids
0x14001d0f5  lea     r9d, [rsi+15h]
0x14001d0f9  mov     [rsp+0A8h+var_88], r15
0x14001d0fe  lea     r8d, [rsi+3]
0x14001d102  mov     rcx, [rcx+40h]
0x14001d106  call    WPP_RECORDER_SF_
0x14001d10b  jmp     short loc_14001D157
0x14001d10d  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001d114  jz      short loc_14001D135
0x14001d116  mov     eax, [rdi+38h]
0x14001d119  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d120  mov     [rsp+0A8h+var_78], eax
0x14001d124  mov     eax, [r15+8]
0x14001d128  mov     [rsp+0A8h+var_80], eax
0x14001d12c  mov     rcx, [rcx+40h]
0x14001d130  call    WPP_RECORDER_SF_dD
0x14001d135  mov     rdx, rdi
0x14001d138  cmp     [r15+8], esi
0x14001d13c  jnz     loc_14001D316
0x14001d142  mov     rcx, rbx
0x14001d145  call    BthEnumGetDeviceList
0x14001d14a  mov     [rdi+30h], eax
0x14001d14d  mov     ebp, eax
0x14001d14f  test    eax, eax
0x14001d151  js      loc_14001D3F3
0x14001d157  mov     rdx, rdi
0x14001d15a  jmp     loc_14001D316
0x14001d15f  mov     [rbx+22h], sil
0x14001d163  mov     rdx, rdi
0x14001d166  jmp     loc_14001D313
0x14001d16b  mov     word ptr [rbx+20h], 101h
0x14001d171  mov     rdx, rdi; Irp
0x14001d174  mov     rax, [rdi+0B8h]
0x14001d17b  movups  xmm0, xmmword ptr [rax]
0x14001d17e  movups  xmmword ptr [rax-48h], xmm0
0x14001d182  movups  xmm1, xmmword ptr [rax+10h]
0x14001d186  movups  xmmword ptr [rax-38h], xmm1
0x14001d18a  movups  xmm0, xmmword ptr [rax+20h]
0x14001d18e  movups  xmmword ptr [rax-28h], xmm0
0x14001d192  movsd   xmm1, qword ptr [rax+30h]
0x14001d197  movsd   qword ptr [rax-18h], xmm1
0x14001d19c  mov     [rax-45h], sil
0x14001d1a0  mov     rcx, [rbx+18h]; DeviceObject
0x14001d1a4  call    cs:__imp_IofCallDriver
0x14001d1ab  nop     dword ptr [rax+rax+00h]
0x14001d1b0  mov     rcx, rbx
0x14001d1b3  mov     edi, eax
0x14001d1b5  call    BthEnumDeleteAllPdos
0x14001d1ba  mov     rcx, [rbx+18h]; TargetDevice
0x14001d1be  call    cs:__imp_IoDetachDevice
0x14001d1c5  nop     dword ptr [rax+rax+00h]
0x14001d1ca  lea     r15, WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids
0x14001d1d1  mov     dword ptr [rbx], 4F444678h
0x14001d1d7  cmp     [rbx+0E8h], rsi
0x14001d1de  jz      short loc_14001D236
0x14001d1e0  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001d1e7  jz      short loc_14001D208
0x14001d1e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d1f0  mov     r9d, 12h
0x14001d1f6  mov     [rsp+0A8h+var_88], r15
0x14001d1fb  mov     rcx, [rcx+40h]
0x14001d1ff  lea     r8d, [r9-0Fh]
0x14001d203  call    WPP_RECORDER_SF_
0x14001d208  mov     rcx, [rbx+0E8h]
0x14001d20f  mov     rax, [rcx+18h]
0x14001d213  mov     rcx, [rcx+8]
0x14001d217  call    _guard_dispatch_icall
0x14001d21c  mov     rcx, [rbx+0E8h]; P
0x14001d223  call    cs:__imp_ExFreePool
0x14001d22a  nop     dword ptr [rax+rax+00h]
0x14001d22f  mov     [rbx+0E8h], rsi
0x14001d236  cmp     [rbx+0F0h], rsi
0x14001d23d  jz      short loc_14001D295
0x14001d23f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001d246  jz      short loc_14001D267
0x14001d248  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d24f  mov     r9d, 13h
0x14001d255  mov     [rsp+0A8h+var_88], r15
0x14001d25a  mov     rcx, [rcx+40h]
0x14001d25e  lea     r8d, [r9-10h]
0x14001d262  call    WPP_RECORDER_SF_
0x14001d267  mov     rcx, [rbx+0F0h]
0x14001d26e  mov     rax, [rcx+18h]
0x14001d272  mov     rcx, [rcx+8]
0x14001d276  call    _guard_dispatch_icall
0x14001d27b  mov     rcx, [rbx+0F0h]; P
0x14001d282  call    cs:__imp_ExFreePool
0x14001d289  nop     dword ptr [rax+rax+00h]
0x14001d28e  mov     [rbx+0F0h], rsi
0x14001d295  mov     rcx, [rbx+0E0h]; P
0x14001d29c  call    cs:__imp_ExFreePool
0x14001d2a3  nop     dword ptr [rax+rax+00h]
0x14001d2a8  mov     rcx, [rbx+78h]; P
0x14001d2ac  mov     [rbx+0E0h], rsi
0x14001d2b3  test    rcx, rcx
0x14001d2b6  jz      short loc_14001D2C8
0x14001d2b8  call    cs:__imp_ExFreePool
0x14001d2bf  nop     dword ptr [rax+rax+00h]
0x14001d2c4  mov     [rbx+78h], rsi
0x14001d2c8  mov     rcx, r14; DeviceObject
0x14001d2cb  call    cs:__imp_IoDeleteDevice
0x14001d2d2  nop     dword ptr [rax+rax+00h]
0x14001d2d7  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001d2de  jz      short loc_14001D303
0x14001d2e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d2e7  mov     r9d, 14h
0x14001d2ed  mov     [rsp+0A8h+var_80], edi
0x14001d2f1  mov     [rsp+0A8h+var_88], r15
0x14001d2f6  mov     rcx, [rcx+40h]
0x14001d2fa  lea     r8d, [r9-11h]
0x14001d2fe  call    WPP_RECORDER_SF_d
0x14001d303  mov     eax, edi
0x14001d305  jmp     loc_14001D413
0x14001d30a  mov     rdx, rdi; Irp
0x14001d30d  cmp     [rbx+22h], sil
0x14001d311  jz      short loc_14001D324
0x14001d313  mov     [rdi+30h], esi
0x14001d316  mov     rcx, [rbx+18h]
0x14001d31a  call    ForwardIrp
0x14001d31f  jmp     loc_14001D413
0x14001d324  mov     rcx, [rbx+18h]; DeviceObject
0x14001d328  mov     r8b, 1
0x14001d32b  call    WaitForLowerDriverToCompleteIrp
0x14001d330  mov     ebp, eax
0x14001d332  test    eax, eax
0x14001d334  js      loc_14001D3F0
0x14001d33a  cmp     [rbx+0E8h], rsi
0x14001d341  jz      short loc_14001D353
0x14001d343  mov     byte ptr [rbx+22h], 1
0x14001d347  mov     dword ptr [rbx+24h], 1
0x14001d34e  jmp     loc_14001D3F0
0x14001d353  mov     rcx, r14
0x14001d356  call    BthEnumGetLocalRadioInfo
0x14001d35b  mov     ebp, eax
0x14001d35d  test    eax, eax
0x14001d35f  js      loc_14001D3F0
0x14001d365  mov     rcx, r14
0x14001d368  call    BthEnumQueryProtocol
0x14001d36d  mov     ebp, eax
0x14001d36f  test    eax, eax
0x14001d371  js      short loc_14001D3F0
0x14001d373  mov     rcx, r14
0x14001d376  call    BthEnumQueryEnumeratorInterface
0x14001d37b  mov     ebp, eax
0x14001d37d  test    eax, eax
0x14001d37f  js      short loc_14001D3F0
0x14001d381  lea     rax, BthEnumRegUpdateWWCapableCodMasks
0x14001d388  mov     dword ptr [rbx+24h], 1
0x14001d38f  mov     byte ptr [rbx+22h], 1
0x14001d393  lea     r8, [rsp+0A8h+Handle]
0x14001d398  mov     r14, [r14+40h]
0x14001d39c  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x14001d3a3  mov     [rsp+0A8h+var_60], rax
0x14001d3a8  mov     [rsp+0A8h+Handle], rsi
0x14001d3ad  mov     [rsp+0A8h+var_58], rsi
0x14001d3b2  call    BthOpenKey
0x14001d3b7  test    eax, eax
0x14001d3b9  js      short loc_14001D3F0
0x14001d3bb  mov     ebx, esi
0x14001d3bd  mov     rdx, [rsp+0A8h+Handle]
0x14001d3c2  lea     r8, [rsp+0A8h+var_50]
0x14001d3c7  mov     eax, ebx
0x14001d3c9  mov     rcx, r14
0x14001d3cc  mov     rax, [rsp+rax*8+0A8h+var_60]
0x14001d3d1  call    _guard_dispatch_icall
0x14001d3d6  inc     ebx
0x14001d3d8  cmp     [rsp+rbx*8+0A8h+var_60], rsi
0x14001d3dd  jnz     short loc_14001D3BD
0x14001d3df  mov     rcx, [rsp+0A8h+Handle]; Handle
0x14001d3e4  call    cs:__imp_ZwClose
0x14001d3eb  nop     dword ptr [rax+rax+00h]
0x14001d3f0  mov     [rdi+30h], ebp
0x14001d3f3  xor     edx, edx; PriorityBoost
0x14001d3f5  mov     rcx, rdi; Irp
0x14001d3f8  call    cs:__imp_IofCompleteRequest
0x14001d3ff  nop     dword ptr [rax+rax+00h]
0x14001d404  mov     eax, ebp
0x14001d406  jmp     short loc_14001D413
0x14001d408  mov     rdx, rdi; Irp
0x14001d40b  mov     rcx, r14; DeviceObject
0x14001d40e  call    BthEnumPdoPnp
0x14001d413  mov     rcx, [rsp+0A8h+var_38]
0x14001d418  xor     rcx, rsp; StackCookie
0x14001d41b  call    __security_check_cookie
0x14001d420  mov     rbx, [rsp+0A8h+arg_10]
0x14001d428  add     rsp, 80h
0x14001d42f  pop     r15
0x14001d431  pop     r14
0x14001d433  pop     rdi
0x14001d434  pop     rsi
0x14001d435  pop     rbp
0x14001d436  retn
```
