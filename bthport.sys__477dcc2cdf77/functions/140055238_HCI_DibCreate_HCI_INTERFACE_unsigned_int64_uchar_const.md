# HCI_DibCreate(HCI_INTERFACE *,unsigned __int64 *,uchar const *)

- ea: `0x140055238`
- end: `0x14005567a`
- name: `?HCI_DibCreate@@YAPEAUDEVICE_INFO_BLOCK@@PEAUHCI_INTERFACE@@PEA_KPEBE@Z`
- size: `1090`
- prototype: `struct DEVICE_INFO_BLOCK *__fastcall(struct HCI_INTERFACE *, unsigned __int64 *, const unsigned __int8 *)`
- caller_count: `5`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1400515b0`
- `0x140052554`
- `0x140061018`
- `0x140061900`
- `0x140065b9c`

## callees

- `0x140005608`
- `0x14000764c`
- `0x140050ba4`
- `0x140050d84`
- `0x140050dac`
- `0x140050e1c`
- `0x140055238`
- `0x140161a44`
- `0x140161c78`
- `0x140165540`
- `0x140165580`
- `0x140165940`

## import_xrefs

- `ntoskrnl!ExSystemTimeToLocalTime` at `0x1400554c9`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x1400554c9`
- `ntoskrnl!ExAllocatePool2` at `0x140055280`
- `ntoskrnl!ExAllocatePool2` at `0x1400552ca`
- `ntoskrnl!ExAllocatePool2` at `0x140055280`
- `ntoskrnl!ExAllocatePool2` at `0x1400552ca`
- `ntoskrnl!KeInitializeEvent` at `0x14005554f`
- `ntoskrnl!KeInitializeEvent` at `0x14005554f`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140055426`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140055426`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14005540f`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14005540f`

## pseudocode

```c
struct DEVICE_INFO_BLOCK *__fastcall HCI_DibCreate(struct HCI_INTERFACE *a1, unsigned __int64 *a2, char *a3)
{
  DEVICE_INFO_BLOCK *Pool2; // rax
  int v7; // edx
  int v8; // r8d
  DEVICE_INFO_BLOCK *v9; // rbx
  DEVICE_INFO_BLOCK *v10; // rdi
  __int64 v11; // rsi
  _RTL_RB_TREE *v12; // r14
  PDEVICE_OBJECT v13; // r10
  const char *v14; // rdx
  __int128 *v15; // rax
  __int64 v16; // rcx
  __int64 Default; // rax
  char v18; // al
  int v19; // edx
  int v20; // r8d
  char v22; // [rsp+28h] [rbp-61h]
  __int16 v23; // [rsp+30h] [rbp-59h]
  DEVICE_INFO_BLOCK *v24; // [rsp+50h] [rbp-39h] BYREF
  __int64 v25; // [rsp+58h] [rbp-31h] BYREF
  __int128 v26; // [rsp+60h] [rbp-29h] BYREF
  __int64 v27; // [rsp+70h] [rbp-19h]
  __int64 v28; // [rsp+78h] [rbp-11h]
  __int128 v29; // [rsp+80h] [rbp-9h] BYREF
  __int64 v30; // [rsp+90h] [rbp+7h]

  Pool2 = (DEVICE_INFO_BLOCK *)ExAllocatePool2(64, 2736, 1346917442);
  v9 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, sizeof(DEVICE_INFO_BLOCK));
    v10 = DEVICE_INFO_BLOCK::DEVICE_INFO_BLOCK(v9);
  }
  else
  {
    v10 = 0;
  }
  v24 = v10;
  if ( !v10 )
  {
    v13 = WPP_GLOBAL_Control;
    LOBYTE(v7) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v23 = 26;
    goto LABEL_34;
  }
  v11 = 16;
  v12 = (_RTL_RB_TREE *)ExAllocatePool2(64, 16, 1346917442);
  if ( !v12 )
  {
    v13 = WPP_GLOBAL_Control;
    LOBYTE(v7) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v23 = 27;
LABEL_34:
    LOBYTE(v8) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      v13->AttachedDevice,
      v7,
      v8,
      a1->IfrLog,
      2,
      2,
      v23,
      (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids);
    utl::unique_ptr<DEVICE_INFO_BLOCK,utl::default_delete<DEVICE_INFO_BLOCK>>::~unique_ptr<DEVICE_INFO_BLOCK,utl::default_delete<DEVICE_INFO_BLOCK>>(&v24);
    return 0;
  }
  (**(void (__fastcall ***)(__int64))&v10->VidPidDeviceWorkaroundFlags.m_initCallback._MyDat._Dats[0])((__int64)&v10->VidPidDeviceWorkaroundFlags);
  v24 = 0;
  *(_QWORD *)&v10->VidPidDeviceWorkaroundFlags.m_initCallback._MyDat._Dats[0] = off_140169238;
  *(_QWORD *)&v10->VidPidDeviceWorkaroundFlags.m_initCallback._MyDat._Dats[1] = v10;
  utl::_FuncEmptyOnExit_utl::_FuncSmall__lambda_a1aa9cf0a6a4976a2c448485f150ae8a__bool__BTH_DEVICE_FLAGS____utl::_FuncEmpty_bool__BTH_DEVICE_FLAGS_____::__FuncEmptyOnExit_utl::_FuncSmall__lambda_a1aa9cf0a6a4976a2c448485f150ae8a__bool__BTH_DEVICE_FLAGS____utl::_FuncEmpty_bool__BTH_DEVICE_FLAGS_____(&v24);
  (**(void (__fastcall ***)(__int64))&v10->PairedDeviceWorkaroundFlags.m_initCallback._MyDat._Dats[0])((__int64)&v10->PairedDeviceWorkaroundFlags);
  *(_QWORD *)&v10->PairedDeviceWorkaroundFlags.m_initCallback._MyDat._Dats[0] = off_140169210;
  *(_QWORD *)&v10->PairedDeviceWorkaroundFlags.m_initCallback._MyDat._Dats[1] = v10;
  v24 = 0;
  utl::_FuncEmptyOnExit_utl::_FuncSmall__lambda_6bff374b65e49584243f75d56954e34a__bool__BTH_DEVICE_FLAGS____utl::_FuncEmpty_bool__BTH_DEVICE_FLAGS_____::__FuncEmptyOnExit_utl::_FuncSmall__lambda_6bff374b65e49584243f75d56954e34a__bool__BTH_DEVICE_FLAGS____utl::_FuncEmpty_bool__BTH_DEVICE_FLAGS_____(&v24);
  v14 = "Device";
  v26 = 0;
  v30 = 0;
  v15 = &v29;
  v29 = 0;
  LODWORD(v26) = 56;
  v16 = 2147483646;
  LOBYTE(v29) = 0;
  v27 = 0;
  v28 = 0x1000000000LL;
  while ( v16 )
  {
    if ( *v14 )
    {
      *(_BYTE *)v15 = *v14++;
      v15 = (__int128 *)((char *)v15 + 1);
      --v16;
      if ( --v11 )
        continue;
    }
    if ( !v11 )
      v15 = (__int128 *)((char *)v15 - 1);
    break;
  }
  *(_BYTE *)v15 = 0;
  *(_QWORD *)((char *)&v26 + 4) = 0x80050485442LL;
  v30 = 0x200000002LL;
  HIDWORD(v26) = 256;
  v25 = 0;
  if ( (unsigned int)imp_WppRecorderLogCreate(WPP_GLOBAL_Control, &v26, &v25) )
  {
    Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    v25 = Default;
  }
  else
  {
    Default = v25;
  }
  v10->IfrLog = (RECORDER_LOG__ *)Default;
  v12->Root = 0;
  v12->Min = 0;
  v10->ProtocolRbTree = v12;
  v10->DeviceInfo.address = *a2;
  if ( a3 )
    v18 = *a3;
  else
    v18 = -1;
  v10->LEOriginalAddressType = v18;
  v10->DeviceInfo.flags |= 1u;
  *(_QWORD *)&v10->NumBRWWIrps = 0;
  v10->LESavedAdvertisementInfo.ManufacturerId = -1;
  if ( v18 == 1 )
    v10->DeviceInfo.flags |= 0x100000u;
  *(_QWORD *)&v10->LEClientPresenceRefCount = 0;
  v10->PageScanRepetitionMode = 1;
  *(_WORD *)&v10->LastConnectionStatus = 255;
  v10->LastConnectionIdentifier = -1;
  v10->LastSeenTimestamp.QuadPart = MEMORY[0xFFFFF78000000014];
  ExSystemTimeToLocalTime(&v10->LastSeenTimestamp, &v10->LastSeenTimestamp);
  RefObj_AddRefEx(&a1->RefObj, v10, 584, "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hcidib.cpp");
  v22 = BthLib_RefObjDebugEnabled;
  v10->Hci = a1;
  v10->DeviceChangeStatus = 1;
  RefObj_InitEx(
    (_DWORD)v10,
    (unsigned int)HCI_DibRefDestroy,
    (_DWORD)v10,
    589,
    (__int64)"onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hcidib.cpp",
    v22);
  v10->ProtocolsLock.Count = 1;
  v10->ProtocolsLock.Owner = 0;
  v10->ProtocolsLock.Contention = 0;
  KeInitializeEvent(&v10->ProtocolsLock.Event, SynchronizationEvent, 0);
  v10->Vid = -1;
  v10->IoCapability = IoCaps_Undefined;
  v10->LocalAuthenticationRequirements = a1->DefaultAuthenticationRequirements;
  v10->RemoteAuthenticationRequirements = MITMProtectionNotDefined;
  v10->LocalEvaldIoCap = IoCaps_Undefined;
  v10->StrictMITM = 0;
  v10->LinkedDibAddress = 0;
  v10->LinkedDibAddressType = 0;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 || (LOBYTE(v19) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    LOBYTE(v19) = 0;
  LOBYTE(v20) = 1;
  WPP_RECORDER_AND_TRACE_SF_qi(
    WPP_GLOBAL_Control->AttachedDevice,
    v19,
    v20,
    v10->IfrLog,
    4,
    6,
    28,
    (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids,
    (char)v10,
    *a2);
  v24 = 0;
  utl::unique_ptr<DEVICE_INFO_BLOCK,utl::default_delete<DEVICE_INFO_BLOCK>>::~unique_ptr<DEVICE_INFO_BLOCK,utl::default_delete<DEVICE_INFO_BLOCK>>(&v24);
  return v10;
}

```

## disassembly

```asm
0x140055238  push    rbp
0x14005523a  push    rbx
0x14005523b  push    rsi
0x14005523c  push    rdi
0x14005523d  push    r12
0x14005523f  push    r13
0x140055241  push    r14
0x140055243  push    r15
0x140055245  lea     rbp, [rsp-1Fh]
0x14005524a  sub     rsp, 0A8h
0x140055251  mov     rax, cs:__security_cookie
0x140055258  xor     rax, rsp
0x14005525b  mov     [rbp+57h+var_48], rax
0x14005525f  mov     r15, r8
0x140055262  mov     r12, rdx
0x140055265  mov     r13, rcx
0x140055268  mov     esi, 50485442h
0x14005526d  mov     edi, 0AB0h
0x140055272  mov     r14d, 40h ; '@'
0x140055278  mov     r8d, esi
0x14005527b  mov     edx, edi
0x14005527d  mov     ecx, r14d
0x140055280  call    cs:__imp_ExAllocatePool2
0x140055287  nop     dword ptr [rax+rax+00h]
0x14005528c  mov     rbx, rax
0x14005528f  test    rax, rax
0x140055292  jz      short loc_1400552AE
0x140055294  mov     r8d, edi; Size
0x140055297  xor     edx, edx; Val
0x140055299  mov     rcx, rax; void *
0x14005529c  call    memset
0x1400552a1  mov     rcx, rbx; this
0x1400552a4  call    ??0DEVICE_INFO_BLOCK@@QEAA@XZ; DEVICE_INFO_BLOCK::DEVICE_INFO_BLOCK(void)
0x1400552a9  mov     rdi, rax
0x1400552ac  jmp     short loc_1400552B0
0x1400552ae  xor     edi, edi
0x1400552b0  mov     [rbp+57h+var_90], rdi
0x1400552b4  test    rdi, rdi
0x1400552b7  jz      loc_140055600
0x1400552bd  mov     r8d, esi
0x1400552c0  mov     rcx, r14
0x1400552c3  mov     esi, 10h
0x1400552c8  mov     edx, esi
0x1400552ca  call    cs:__imp_ExAllocatePool2
0x1400552d1  nop     dword ptr [rax+rax+00h]
0x1400552d6  mov     r14, rax
0x1400552d9  test    rax, rax
0x1400552dc  jnz     short loc_140055314
0x1400552de  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400552e5  lea     ecx, [rsi-0Eh]
0x1400552e8  mov     eax, [r10+2Ch]
0x1400552ec  test    cl, al
0x1400552ee  jz      short loc_1400552FA
0x1400552f0  cmp     [r10+29h], cl
0x1400552f4  jb      short loc_1400552FA
0x1400552f6  mov     dl, 1
0x1400552f8  jmp     short loc_1400552FC
0x1400552fa  xor     dl, dl
0x1400552fc  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x140055303  mov     [rsp+0E0h+var_A8], rax
0x140055308  mov     [rsp+0E0h+var_B0], 1Bh
0x14005530f  jmp     loc_140055633
0x140055314  lea     rbx, [rdi+848h]
0x14005531b  mov     rax, [rbx]
0x14005531e  mov     rcx, rbx
0x140055321  mov     rax, [rax]
0x140055324  call    _guard_dispatch_icall
0x140055329  lea     rax, off_140169238
0x140055330  mov     [rbp+57h+var_90], 0
0x140055338  mov     [rbx], rax
0x14005533b  lea     rcx, [rbp+57h+var_90]
0x14005533f  mov     [rbx+8], rdi
0x140055343  call    utl___FuncEmptyOnExit_utl___FuncSmall__lambda_a1aa9cf0a6a4976a2c448485f150ae8a__bool__BTH_DEVICE_FLAGS____utl___FuncEmpty_bool__BTH_DEVICE_FLAGS_________FuncEmptyOnExit_utl___FuncSmall__lambda_a1aa9cf0a6a4976a2c448485f150ae8a__bool__BTH_DEVICE_FLAGS____utl___FuncEmpty_bool__BTH_DEVICE_FLAGS_____
0x140055348  lea     rbx, [rdi+878h]
0x14005534f  mov     rax, [rbx]
0x140055352  mov     rcx, rbx
0x140055355  mov     rax, [rax]
0x140055358  call    _guard_dispatch_icall
0x14005535d  lea     rax, off_140169210
0x140055364  mov     [rbx], rax
0x140055367  lea     rcx, [rbp+57h+var_90]
0x14005536b  mov     [rbx+8], rdi
0x14005536f  xor     ebx, ebx
0x140055371  mov     [rbp+57h+var_90], rbx
0x140055375  call    utl___FuncEmptyOnExit_utl___FuncSmall__lambda_6bff374b65e49584243f75d56954e34a__bool__BTH_DEVICE_FLAGS____utl___FuncEmpty_bool__BTH_DEVICE_FLAGS_________FuncEmptyOnExit_utl___FuncSmall__lambda_6bff374b65e49584243f75d56954e34a__bool__BTH_DEVICE_FLAGS____utl___FuncEmpty_bool__BTH_DEVICE_FLAGS_____
0x14005537a  xorps   xmm0, xmm0
0x14005537d  lea     rdx, aDevice; "Device"
0x140055384  movups  [rbp+57h+var_70], xmm0
0x140055388  xor     eax, eax
0x14005538a  mov     dword ptr [rbp+57h+var_70+0Ch], esi
0x14005538d  movups  [rbp+57h+var_80], xmm0
0x140055391  mov     [rbp+57h+var_50], rax
0x140055395  lea     rax, [rbp+57h+var_60]
0x140055399  movups  [rbp+57h+var_60], xmm0
0x14005539d  mov     dword ptr [rbp+57h+var_80], 38h ; '8'
0x1400553a4  mov     ecx, 7FFFFFFEh
0x1400553a9  mov     byte ptr [rbp+57h+var_60], bl
0x1400553ac  mov     qword ptr [rbp+57h+var_70], rbx
0x1400553b0  mov     byte ptr [rbp+57h+var_70+8], bl
0x1400553b3  test    rcx, rcx
0x1400553b6  jz      short loc_1400553DA
0x1400553b8  mov     r8b, [rdx]
0x1400553bb  test    r8b, r8b
0x1400553be  jz      short loc_1400553D2
0x1400553c0  mov     [rax], r8b
0x1400553c3  inc     rdx
0x1400553c6  inc     rax
0x1400553c9  dec     rcx
0x1400553cc  sub     rsi, 1
0x1400553d0  jnz     short loc_1400553B3
0x1400553d2  test    rsi, rsi
0x1400553d5  jnz     short loc_1400553DA
0x1400553d7  dec     rax
0x1400553da  mov     [rax], bl
0x1400553dc  lea     r8, [rbp+57h+var_88]
0x1400553e0  mov     ecx, 2
0x1400553e5  mov     dword ptr [rbp+57h+var_80+4], 50485442h
0x1400553ec  mov     dword ptr [rbp+57h+var_50], ecx
0x1400553ef  lea     rdx, [rbp+57h+var_80]
0x1400553f3  mov     dword ptr [rbp+57h+var_50+4], ecx
0x1400553f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400553fd  mov     dword ptr [rbp+57h+var_80+8], 800h
0x140055404  mov     dword ptr [rbp+57h+var_80+0Ch], 100h
0x14005540b  mov     [rbp+57h+var_88], rbx
0x14005540f  call    cs:__imp_imp_WppRecorderLogCreate
0x140055416  nop     dword ptr [rax+rax+00h]
0x14005541b  test    eax, eax
0x14005541d  jz      short loc_140055438
0x14005541f  mov     rcx, cs:WPP_GLOBAL_Control
0x140055426  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14005542d  nop     dword ptr [rax+rax+00h]
0x140055432  mov     [rbp+57h+var_88], rax
0x140055436  jmp     short loc_14005543C
0x140055438  mov     rax, [rbp+57h+var_88]
0x14005543c  mov     [rdi+838h], rax
0x140055443  mov     esi, 0FFh
0x140055448  mov     [r14], rbx
0x14005544b  mov     [r14+8], rbx
0x14005544f  mov     [rdi+3B8h], r14
0x140055456  mov     rax, [r12]
0x14005545a  mov     [rdi+20h], rax
0x14005545e  test    r15, r15
0x140055461  jz      short loc_140055468
0x140055463  mov     al, [r15]
0x140055466  jmp     short loc_14005546B
0x140055468  mov     al, sil
0x14005546b  mov     [rdi+5B0h], al
0x140055471  mov     r14d, 0FFFFh
0x140055477  or      dword ptr [rdi+18h], 1
0x14005547b  mov     [rdi+3C4h], rbx
0x140055482  mov     [rdi+529h], r14w
0x14005548a  cmp     al, 1
0x14005548c  jnz     short loc_140055493
0x14005548e  bts     dword ptr [rdi+18h], 14h
0x140055493  mov     [rdi+830h], rbx
0x14005549a  lea     rcx, [rdi+670h]; SystemTime
0x1400554a1  mov     byte ptr [rdi+5B2h], 1
0x1400554a8  mov     rdx, rcx; LocalTime
0x1400554ab  mov     [rdi+5B7h], si
0x1400554b2  mov     dword ptr [rdi+5BCh], 0FFFFFFFFh
0x1400554bc  mov     rax, ds:0FFFFF78000000014h
0x1400554c6  mov     [rcx], rax
0x1400554c9  call    cs:__imp_ExSystemTimeToLocalTime
0x1400554d0  nop     dword ptr [rax+rax+00h]
0x1400554d5  lea     rbx, aOnecoreDrivers_11; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400554dc  mov     r8d, 248h
0x1400554e2  mov     r9, rbx
0x1400554e5  lea     rcx, [r13+8]
0x1400554e9  mov     rdx, rdi
0x1400554ec  call    RefObj_AddRefEx
0x1400554f1  mov     al, cs:BthLib_RefObjDebugEnabled
0x1400554f7  lea     rdx, ?HCI_DibRefDestroy@@YAXPEAU_REF_OBJ@@@Z; HCI_DibRefDestroy(_REF_OBJ *)
0x1400554fe  mov     [rsp+0E0h+var_B8], al
0x140055502  mov     r9d, 24Dh
0x140055508  mov     [rdi+378h], r13
0x14005550f  mov     r8, rdi
0x140055512  mov     rcx, rdi
0x140055515  mov     [rsp+0E0h+var_C0], rbx
0x14005551a  mov     dword ptr [rdi+370h], 1
0x140055524  call    RefObj_InitEx
0x140055529  xor     ebx, ebx
0x14005552b  mov     dword ptr [rdi+380h], 1
0x140055535  lea     rcx, [rdi+398h]; Event
0x14005553c  mov     [rdi+388h], rbx
0x140055543  xor     r8d, r8d; State
0x140055546  mov     [rdi+390h], ebx
0x14005554c  lea     edx, [rbx+1]; Type
0x14005554f  call    cs:__imp_KeInitializeEvent
0x140055556  nop     dword ptr [rax+rax+00h]
0x14005555b  mov     [rdi+3CEh], r14w
0x140055563  mov     [rdi+5C8h], esi
0x140055569  mov     eax, [r13+0D34h]
0x140055570  mov     [rdi+5CCh], eax
0x140055576  mov     [rdi+5D0h], esi
0x14005557c  mov     [rdi+840h], esi
0x140055582  mov     [rdi+844h], bl
0x140055588  mov     [rdi+8E8h], rbx
0x14005558f  mov     [rdi+8F0h], bl
0x140055595  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005559c  mov     eax, [rcx+2Ch]
0x14005559f  test    al, 20h
0x1400555a1  jz      short loc_1400555AB
0x1400555a3  cmp     byte ptr [rcx+29h], 4
0x1400555a7  mov     dl, 1
0x1400555a9  jnb     short loc_1400555AD
0x1400555ab  mov     dl, bl
0x1400555ad  mov     rax, [r12]
0x1400555b1  mov     r8b, 1
0x1400555b4  mov     r9, [rdi+838h]
0x1400555bb  mov     rcx, [rcx+18h]
0x1400555bf  mov     [rsp+0E0h+var_98], rax
0x1400555c4  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x1400555cb  mov     [rsp+0E0h+var_A0], rdi
0x1400555d0  mov     [rsp+0E0h+var_A8], rax
0x1400555d5  mov     [rsp+0E0h+var_B0], 1Ch
0x1400555dc  mov     dword ptr [rsp+0E0h+var_B8], 6
0x1400555e4  mov     byte ptr [rsp+0E0h+var_C0], 4
0x1400555e9  call    WPP_RECORDER_AND_TRACE_SF_qi
0x1400555ee  lea     rcx, [rbp+57h+var_90]
0x1400555f2  mov     [rbp+57h+var_90], rbx
0x1400555f6  call    ??1?$unique_ptr@UDEVICE_INFO_BLOCK@@U?$default_delete@UDEVICE_INFO_BLOCK@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<DEVICE_INFO_BLOCK,utl::default_delete<DEVICE_INFO_BLOCK>>::~unique_ptr<DEVICE_INFO_BLOCK,utl::default_delete<DEVICE_INFO_BLOCK>>(void)
0x1400555fb  mov     rax, rdi
0x1400555fe  jmp     short loc_140055659
0x140055600  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140055607  mov     ecx, 2
0x14005560c  mov     eax, [r10+2Ch]
0x140055610  test    cl, al
0x140055612  jz      short loc_14005561E
0x140055614  cmp     [r10+29h], cl
0x140055618  jb      short loc_14005561E
0x14005561a  mov     dl, 1
0x14005561c  jmp     short loc_140055620
0x14005561e  xor     dl, dl
0x140055620  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x140055627  mov     [rsp+0E0h+var_A8], rax
0x14005562c  mov     [rsp+0E0h+var_B0], 1Ah
0x140055633  mov     r9, [r13+10B0h]
0x14005563a  mov     r8b, 1
0x14005563d  mov     dword ptr [rsp+0E0h+var_B8], ecx
0x140055641  mov     byte ptr [rsp+0E0h+var_C0], cl
0x140055645  mov     rcx, [r10+18h]
0x140055649  call    WPP_RECORDER_AND_TRACE_SF_
0x14005564e  lea     rcx, [rbp+57h+var_90]
0x140055652  call    ??1?$unique_ptr@UDEVICE_INFO_BLOCK@@U?$default_delete@UDEVICE_INFO_BLOCK@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<DEVICE_INFO_BLOCK,utl::default_delete<DEVICE_INFO_BLOCK>>::~unique_ptr<DEVICE_INFO_BLOCK,utl::default_delete<DEVICE_INFO_BLOCK>>(void)
0x140055657  xor     eax, eax
0x140055659  mov     rcx, [rbp+57h+var_48]
0x14005565d  xor     rcx, rsp; StackCookie
0x140055660  call    __security_check_cookie
0x140055665  add     rsp, 0A8h
0x14005566c  pop     r15
0x14005566e  pop     r14
0x140055670  pop     r13
0x140055672  pop     r12
0x140055674  pop     rdi
0x140055675  pop     rsi
0x140055676  pop     rbx
0x140055677  pop     rbp
0x140055678  retn
```
