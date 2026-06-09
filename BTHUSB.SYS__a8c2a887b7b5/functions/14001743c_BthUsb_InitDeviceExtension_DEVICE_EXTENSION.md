# BthUsb_InitDeviceExtension(_DEVICE_EXTENSION *)

- ea: `0x14001743c`
- end: `0x140017850`
- name: `?BthUsb_InitDeviceExtension@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `1044`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140018b90`

## callees

- `0x14000175c`
- `0x1400017d4`
- `0x14000187c`
- `0x14000d4a8`
- `0x14001743c`
- `0x14001accc`
- `0x14001c0a4`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1400175db`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400175ee`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400175db`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400175ee`
- `ntoskrnl!ZwClose` at `0x140017750`
- `ntoskrnl!ZwClose` at `0x140017750`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400176b0`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400176b0`
- `ntoskrnl!ExUuidCreate` at `0x1400174af`
- `ntoskrnl!ExUuidCreate` at `0x1400174af`

## pseudocode

```c
__int64 __fastcall BthUsb_InitDeviceExtension(struct _DEVICE_EXTENSION *a1, __int64 a2, int a3)
{
  char v4; // bl
  bool v5; // dl
  NTSTATUS v6; // eax
  int v7; // edx
  int v8; // r8d
  _USB_INTERFACE_DESCRIPTOR *OffInterface; // rdx
  int MaxIsoInterface; // esi
  unsigned __int8 bInterfaceNumber; // dl
  unsigned int *p_MaxFrameSize; // r14
  int v13; // edx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rax
  _BTDEVICE *BtDevice; // rcx
  _USB_DEVICE_DESCRIPTOR *DeviceDescriptor; // rbp
  int v19; // edx
  int v20; // r8d
  __int64 v21; // rcx
  int v22; // edx
  int v23; // r8d
  void *DeviceRegKey; // [rsp+88h] [rbp+10h] BYREF

  DeviceRegKey = 0;
  v4 = 1;
  v5 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_q(
    WPP_GLOBAL_Control->AttachedDevice,
    v5,
    a3,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    2,
    23,
    (__int64)WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids,
    (char)a1);
  v6 = ExUuidCreate(&a1->DeviceExtensionSessionId);
  if ( v6 < 0 )
  {
    LOBYTE(v7) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v7,
      (_DWORD)WPP_GLOBAL_Control,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      2,
      24,
      (__int64)WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids,
      v6);
    a1->DeviceExtensionSessionId = 0;
  }
  OffInterface = a1->Sco.OffInterface;
  MaxIsoInterface = -1073741637;
  if ( OffInterface )
  {
    a1->Sco.CurInterface = OffInterface;
    bInterfaceNumber = OffInterface->bInterfaceNumber;
    p_MaxFrameSize = &a1->Sco.MaxFrameSize;
    a1->Sco.InterfaceNumber = bInterfaceNumber;
    MaxIsoInterface = BthUsb_GetMaxIsoInterface(
                        a1,
                        bInterfaceNumber,
                        &a1->Sco.MaxInterface,
                        &a1->Sco.MaxFrameSize,
                        &a1->Sco.RealMaxInterface,
                        &a1->Sco.RealMaxFrameSize);
    if ( MaxIsoInterface >= 0 )
    {
      v14 = *p_MaxFrameSize;
      if ( *p_MaxFrameSize > 0x56 )
        v14 = 86;
      *p_MaxFrameSize = v14;
      a1->Sco.MaxBandwidth = 1000 * v14 - 1000;
      KeInitializeSpinLock(&a1->Sco.ReadLock);
      KeInitializeSpinLock(&a1->Sco.WriteLock);
      OffInterface = 0;
      do
      {
        v15 = 152LL * (_QWORD)&OffInterface->bAlternateSetting;
        v16 = (__int64)OffInterface;
        OffInterface = (_USB_INTERFACE_DESCRIPTOR *)((char *)OffInterface + 1);
        *(_WORD *)((char *)&a1->Sco.InitStatus + v15) = -1;
        a1->Sco.Channel[v16].WriteFrameInterval = -1;
      }
      while ( OffInterface != (_USB_INTERFACE_DESCRIPTOR *)3 );
      MaxIsoInterface = 0;
      a1->Sco.UsbAltSetting = (const ScoUsbAltSetting *)qword_140010050;
    }
    else
    {
      LOBYTE(v13) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v13,
        (_DWORD)WPP_GLOBAL_Control,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        4,
        13,
        (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
    }
  }
  LOBYTE(OffInterface) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_D(
    WPP_GLOBAL_Control->AttachedDevice,
    (_DWORD)OffInterface,
    v8,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    14,
    (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
    MaxIsoInterface);
  a1->Sco.InitStatus = MaxIsoInterface;
  BtDevice = a1->BtDevice;
  DeviceDescriptor = a1->DeviceDescriptor;
  a1->BulkInSize = 4096;
  if ( IoOpenDeviceRegistryKey(BtDevice->PhysicalDeviceObject, 1u, 0x20000u, &DeviceRegKey) >= 0 )
  {
    BthQueryKeyValue(DeviceRegKey);
    ZwClose(DeviceRegKey);
    DeviceRegKey = 0;
  }
  if ( DeviceDescriptor->bDeviceClass == 0xE0
    && DeviceDescriptor->bDeviceSubClass == 1
    && DeviceDescriptor->bDeviceProtocol == 1 )
  {
    LOBYTE(v19) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v19,
      v20,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      2,
      26,
      (__int64)WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids);
  }
  else
  {
    LOBYTE(v19) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v19,
      v20,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      2,
      27,
      (__int64)WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids);
  }
  LockedList_EnqueueTail(v21, &a1->DevExtListEntry);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v4 = 0;
  LOBYTE(v22) = v4;
  WPP_RECORDER_AND_TRACE_SF_D(
    WPP_GLOBAL_Control->AttachedDevice,
    v22,
    v23,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    2,
    28,
    (__int64)WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids,
    0);
  return 0;
}

```

## disassembly

```asm
0x14001743c  mov     rax, rsp
0x14001743f  mov     [rax+18h], rbx
0x140017443  push    rbp
0x140017444  push    rsi
0x140017445  push    rdi
0x140017446  push    r12
0x140017448  push    r14
0x14001744a  sub     rsp, 50h
0x14001744e  mov     rdi, rcx
0x140017451  mov     qword ptr [rax+10h], 0
0x140017459  mov     rcx, cs:WPP_GLOBAL_Control
0x140017460  mov     ebx, 1
0x140017465  mov     eax, [rcx+2Ch]
0x140017468  lea     r12d, [rbx+1]
0x14001746c  test    r12b, al
0x14001746f  jz      short loc_14001747B
0x140017471  cmp     byte ptr [rcx+29h], 4
0x140017475  jb      short loc_14001747B
0x140017477  mov     dl, bl
0x140017479  jmp     short loc_14001747D
0x14001747b  xor     dl, dl
0x14001747d  mov     r9, [rcx+40h]
0x140017481  lea     r14, WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids
0x140017488  mov     rcx, [rcx+18h]
0x14001748c  mov     [rsp+78h+var_38], rdi
0x140017491  mov     [rsp+78h+var_40], r14
0x140017496  mov     [rsp+78h+var_48], 17h
0x14001749d  mov     dword ptr [rsp+78h+var_50], r12d
0x1400174a2  mov     byte ptr [rsp+78h+var_58], 4
0x1400174a7  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400174ac  mov     rcx, rdi; Uuid
0x1400174af  call    cs:__imp_ExUuidCreate
0x1400174b6  nop     dword ptr [rax+rax+00h]
0x1400174bb  test    eax, eax
0x1400174bd  jns     short loc_140017509
0x1400174bf  mov     r8, cs:WPP_GLOBAL_Control
0x1400174c6  mov     ecx, [r8+2Ch]
0x1400174ca  test    r12b, cl
0x1400174cd  jz      short loc_1400174DA
0x1400174cf  cmp     byte ptr [r8+29h], 3
0x1400174d4  jb      short loc_1400174DA
0x1400174d6  mov     dl, bl
0x1400174d8  jmp     short loc_1400174DC
0x1400174da  xor     dl, dl
0x1400174dc  mov     r9, [r8+40h]
0x1400174e0  mov     rcx, [r8+18h]
0x1400174e4  mov     dword ptr [rsp+78h+var_38], eax
0x1400174e8  mov     [rsp+78h+var_40], r14
0x1400174ed  mov     [rsp+78h+var_48], 18h
0x1400174f4  mov     dword ptr [rsp+78h+var_50], r12d
0x1400174f9  mov     byte ptr [rsp+78h+var_58], 3
0x1400174fe  call    WPP_RECORDER_AND_TRACE_SF_D
0x140017503  xorps   xmm0, xmm0
0x140017506  movups  xmmword ptr [rdi], xmm0
0x140017509  mov     rdx, [rdi+280h]
0x140017510  lea     rbp, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140017517  mov     esi, 0C00000BBh
0x14001751c  test    rdx, rdx
0x14001751f  jz      loc_140017643
0x140017525  lea     rax, [rdi+2A4h]
0x14001752c  mov     [rdi+298h], rdx
0x140017533  mov     dl, [rdx+2]; unsigned __int8
0x140017536  lea     rcx, [rdi+290h]
0x14001753d  mov     [rsp+78h+var_50], rax; unsigned int *
0x140017542  lea     r14, [rdi+2A0h]
0x140017549  mov     [rsp+78h+var_58], rcx; struct _USB_INTERFACE_DESCRIPTOR **
0x14001754e  lea     r8, [rdi+288h]; struct _USB_INTERFACE_DESCRIPTOR **
0x140017555  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140017558  mov     [rdi+27Ch], dl
0x14001755e  mov     r9, r14; unsigned int *
0x140017561  call    ?BthUsb_GetMaxIsoInterface@@YAJPEAU_DEVICE_EXTENSION@@EPEAPEAU_USB_INTERFACE_DESCRIPTOR@@PEAK12@Z; BthUsb_GetMaxIsoInterface(_DEVICE_EXTENSION *,uchar,_USB_INTERFACE_DESCRIPTOR * *,ulong *,_USB_INTERFACE_DESCRIPTOR * *,ulong *)
0x140017566  mov     esi, eax
0x140017568  test    eax, eax
0x14001756a  jns     short loc_1400175B3
0x14001756c  mov     r8, cs:WPP_GLOBAL_Control
0x140017573  mov     ecx, [r8+2Ch]
0x140017577  test    cl, 8
0x14001757a  jz      short loc_140017586
0x14001757c  cmp     [r8+29h], r12b
0x140017580  jb      short loc_140017586
0x140017582  mov     dl, bl
0x140017584  jmp     short loc_140017588
0x140017586  xor     dl, dl
0x140017588  mov     r9, [r8+40h]
0x14001758c  mov     rcx, [r8+18h]
0x140017590  mov     [rsp+78h+var_40], rbp
0x140017595  mov     [rsp+78h+var_48], 0Dh
0x14001759c  mov     dword ptr [rsp+78h+var_50], 4
0x1400175a4  mov     byte ptr [rsp+78h+var_58], r12b
0x1400175a9  call    WPP_RECORDER_AND_TRACE_SF_
0x1400175ae  jmp     loc_14001763C
0x1400175b3  mov     eax, [r14]
0x1400175b6  mov     ecx, 56h ; 'V'
0x1400175bb  cmp     eax, ecx
0x1400175bd  cmova   eax, ecx
0x1400175c0  lea     rcx, [rdi+248h]; SpinLock
0x1400175c7  mov     [r14], eax
0x1400175ca  imul    eax, 3E8h
0x1400175d0  sub     eax, 3E8h
0x1400175d5  mov     [rdi+2A8h], eax
0x1400175db  call    cs:__imp_KeInitializeSpinLock
0x1400175e2  nop     dword ptr [rax+rax+00h]
0x1400175e7  lea     rcx, [rdi+260h]; SpinLock
0x1400175ee  call    cs:__imp_KeInitializeSpinLock
0x1400175f5  nop     dword ptr [rax+rax+00h]
0x1400175fa  xor     edx, edx
0x1400175fc  lea     rax, [rdx+3]
0x140017600  imul    rcx, rax, 98h
0x140017607  imul    rax, rdx, 98h
0x14001760e  add     rdx, rbx
0x140017611  mov     word ptr [rcx+rdi+0E8h], 0FFFFh
0x14001761b  mov     dword ptr [rax+rdi+344h], 0FFFFFFFFh
0x140017626  cmp     rdx, 3
0x14001762a  jnz     short loc_1400175FC
0x14001762c  lea     rax, qword_140010050
0x140017633  xor     esi, esi
0x140017635  mov     [rdi+478h], rax
0x14001763c  lea     r14, WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids
0x140017643  mov     rcx, cs:WPP_GLOBAL_Control
0x14001764a  mov     eax, [rcx+2Ch]
0x14001764d  test    al, 8
0x14001764f  jz      short loc_14001765B
0x140017651  cmp     byte ptr [rcx+29h], 4
0x140017655  jb      short loc_14001765B
0x140017657  mov     dl, bl
0x140017659  jmp     short loc_14001765D
0x14001765b  xor     dl, dl
0x14001765d  mov     r9, [rcx+40h]
0x140017661  mov     rcx, [rcx+18h]
0x140017665  mov     dword ptr [rsp+78h+var_38], esi
0x140017669  mov     [rsp+78h+var_40], rbp
0x14001766e  mov     [rsp+78h+var_48], 0Eh
0x140017675  mov     dword ptr [rsp+78h+var_50], 4
0x14001767d  mov     byte ptr [rsp+78h+var_58], 4
0x140017682  call    WPP_RECORDER_AND_TRACE_SF_D
0x140017687  mov     [rdi+0E8h], esi
0x14001768d  lea     r9, [rsp+78h+DeviceRegKey]; DeviceRegKey
0x140017695  mov     rcx, [rdi+10h]
0x140017699  mov     r8d, 20000h; DesiredAccess
0x14001769f  mov     rbp, [rdi+60h]
0x1400176a3  mov     edx, ebx; DevInstKeyType
0x1400176a5  mov     dword ptr [rdi+50h], 1000h
0x1400176ac  mov     rcx, [rcx+10h]; DeviceObject
0x1400176b0  call    cs:__imp_IoOpenDeviceRegistryKey
0x1400176b7  nop     dword ptr [rax+rax+00h]
0x1400176bc  test    eax, eax
0x1400176be  js      loc_140017768
0x1400176c4  mov     rcx, [rsp+78h+DeviceRegKey]; KeyHandle
0x1400176cc  lea     r8, [rsp+78h+arg_0]
0x1400176d4  lea     rdx, aBulkinsize; "BulkInSize"
0x1400176db  mov     [rsp+78h+arg_0], 0
0x1400176e6  call    BthQueryKeyValue
0x1400176eb  test    eax, eax
0x1400176ed  js      short loc_140017748
0x1400176ef  mov     esi, [rsp+78h+arg_0]
0x1400176f6  lea     eax, [rsi-400h]
0x1400176fc  cmp     eax, 0FC00h
0x140017701  ja      short loc_140017748
0x140017703  mov     rcx, cs:WPP_GLOBAL_Control
0x14001770a  mov     eax, [rcx+2Ch]
0x14001770d  test    r12b, al
0x140017710  jz      short loc_14001771C
0x140017712  cmp     byte ptr [rcx+29h], 4
0x140017716  jb      short loc_14001771C
0x140017718  mov     dl, bl
0x14001771a  jmp     short loc_14001771E
0x14001771c  xor     dl, dl
0x14001771e  mov     r9, [rcx+40h]
0x140017722  mov     rcx, [rcx+18h]
0x140017726  mov     dword ptr [rsp+78h+var_38], esi
0x14001772a  mov     [rsp+78h+var_40], r14
0x14001772f  mov     [rsp+78h+var_48], 19h
0x140017736  mov     dword ptr [rsp+78h+var_50], r12d
0x14001773b  mov     byte ptr [rsp+78h+var_58], 4
0x140017740  call    WPP_RECORDER_AND_TRACE_SF_D
0x140017745  mov     [rdi+50h], esi
0x140017748  mov     rcx, [rsp+78h+DeviceRegKey]; Handle
0x140017750  call    cs:__imp_ZwClose
0x140017757  nop     dword ptr [rax+rax+00h]
0x14001775c  mov     [rsp+78h+DeviceRegKey], 0
0x140017768  cmp     byte ptr [rbp+4], 0E0h
0x14001776c  jnz     short loc_1400177AB
0x14001776e  cmp     [rbp+5], bl
0x140017771  jnz     short loc_1400177AB
0x140017773  cmp     [rbp+6], bl
0x140017776  jnz     short loc_1400177AB
0x140017778  mov     rcx, cs:WPP_GLOBAL_Control
0x14001777f  mov     eax, [rcx+2Ch]
0x140017782  test    r12b, al
0x140017785  jz      short loc_140017791
0x140017787  cmp     byte ptr [rcx+29h], 4
0x14001778b  jb      short loc_140017791
0x14001778d  mov     dl, bl
0x14001778f  jmp     short loc_140017793
0x140017791  xor     dl, dl
0x140017793  mov     [rsp+78h+var_40], r14
0x140017798  mov     [rsp+78h+var_48], 1Ah
0x14001779f  mov     dword ptr [rsp+78h+var_50], r12d
0x1400177a4  mov     byte ptr [rsp+78h+var_58], 4
0x1400177a9  jmp     short loc_1400177DC
0x1400177ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400177b2  mov     eax, [rcx+2Ch]
0x1400177b5  test    r12b, al
0x1400177b8  jz      short loc_1400177C4
0x1400177ba  cmp     byte ptr [rcx+29h], 3
0x1400177be  jb      short loc_1400177C4
0x1400177c0  mov     dl, bl
0x1400177c2  jmp     short loc_1400177C6
0x1400177c4  xor     dl, dl
0x1400177c6  mov     [rsp+78h+var_40], r14
0x1400177cb  mov     [rsp+78h+var_48], 1Bh
0x1400177d2  mov     dword ptr [rsp+78h+var_50], r12d
0x1400177d7  mov     byte ptr [rsp+78h+var_58], 3
0x1400177dc  mov     r9, [rcx+40h]
0x1400177e0  mov     rcx, [rcx+18h]
0x1400177e4  call    WPP_RECORDER_AND_TRACE_SF_
0x1400177e9  lea     rdx, [rdi+480h]
0x1400177f0  call    LockedList_EnqueueTail
0x1400177f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400177fc  mov     eax, [rcx+2Ch]
0x1400177ff  test    r12b, al
0x140017802  jz      short loc_14001780A
0x140017804  cmp     byte ptr [rcx+29h], 4
0x140017808  jnb     short loc_14001780C
0x14001780a  xor     bl, bl
0x14001780c  mov     r9, [rcx+40h]
0x140017810  mov     dl, bl
0x140017812  mov     rcx, [rcx+18h]
0x140017816  mov     dword ptr [rsp+78h+var_38], 0
0x14001781e  mov     [rsp+78h+var_40], r14
0x140017823  mov     [rsp+78h+var_48], 1Ch
0x14001782a  mov     dword ptr [rsp+78h+var_50], r12d
0x14001782f  mov     byte ptr [rsp+78h+var_58], 4
0x140017834  call    WPP_RECORDER_AND_TRACE_SF_D
0x140017839  mov     rbx, [rsp+78h+arg_10]
0x140017841  xor     eax, eax
0x140017843  add     rsp, 50h
0x140017847  pop     r14
0x140017849  pop     r12
0x14001784b  pop     rdi
0x14001784c  pop     rsi
0x14001784d  pop     rbp
0x14001784e  retn
```
