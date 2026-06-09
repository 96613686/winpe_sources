# PnpUtilsSelectDriverForDevNode

- ea: `0x14002c2bc`
- end: `0x14002c76e`
- name: `PnpUtilsSelectDriverForDevNode`
- size: `1202`
- prototype: `__int64 __fastcall(int, int, int, int, struct _DRVUTILS_UPDATE_INFO *, __int64, int, __int64, __int64, unsigned __int64, unsigned __int64)`
- caller_count: `4`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001170c`
- `0x14001a9f0`
- `0x14001dc80`
- `0x14001fa98`

## callees

- `0x1400070bc`
- `0x14002405c`
- `0x1400240b8`
- `0x140029764`
- `0x1400298ec`
- `0x140029db8`
- `0x140029ed4`
- `0x14002b1c4`
- `0x14002b434`
- `0x14002b748`
- `0x14002c2bc`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002c5c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002c5c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002c710`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002c710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c4e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c520`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c56b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c4e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c520`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c56b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002c736`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002c736`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c39c`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c445`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c485`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c4fe`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c542`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c58c`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c5b3`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c6e4`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c39c`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c445`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c485`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c4fe`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c542`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c58c`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c5b3`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002c6e4`
- `drvstore!DriverStoreOpenW` at `0x14002c3f2`
- `drvstore!DriverStoreOpenW` at `0x14002c3f2`
- `drvstore!DriverStoreClose` at `0x14002c6f9`
- `drvstore!DriverStoreClose` at `0x14002c6f9`
- `drvstore!DriverStoreEnumDeviceDriversW` at `0x14002c4d2`
- `drvstore!DriverStoreEnumDeviceDriversW` at `0x14002c4d2`

## string_xrefs

- `0x14002c43e`: `Selecting drivers by excluding installed drivers.`
- `0x14002c571`: `Failed to create device descriptor. Error = 0x%08X`

## pseudocode

```c
_BOOL8 __fastcall PnpUtilsSelectDriverForDevNode(
        struct HDRIVERSTORE__ *a1,
        DEVINST a2,
        __int64 a3,
        char a4,
        struct _DRVUTILS_UPDATE_INFO *a5,
        _QWORD *a6,
        int a7,
        __int64 a8,
        unsigned __int16 *a9,
        unsigned __int64 a10,
        unsigned __int64 a11)
{
  struct HDRIVERSTORE__ *v14; // r12
  _OWORD *v15; // r13
  _WORD *v16; // rdi
  char v17; // al
  int v18; // r15d
  DWORD LastError; // ebx
  unsigned int v20; // ebx
  DEVINST v21; // r15d
  DWORD v22; // eax
  const char *v23; // r9
  _WORD *v24; // rax
  _WORD *i; // rdx
  __int64 v26; // rcx
  unsigned int v27; // eax
  _DWORD *v28; // r11
  int InstalledDriverCount; // eax
  int v30; // edx
  __int64 v32; // [rsp+20h] [rbp-E0h]
  unsigned int v34; // [rsp+34h] [rbp-CCh] BYREF
  int v35; // [rsp+38h] [rbp-C8h]
  _WORD *v36; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v37; // [rsp+48h] [rbp-B8h]
  struct HDRIVERSTORE__ *v38; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v39; // [rsp+58h] [rbp-A8h]
  _QWORD *v40; // [rsp+60h] [rbp-A0h]
  _OWORD v41[3]; // [rsp+68h] [rbp-98h] BYREF
  DEVINST v42; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-58h]
  unsigned int v44; // [rsp+B0h] [rbp-50h]
  size_t v45[65]; // [rsp+B4h] [rbp-4Ch] BYREF
  int v46; // [rsp+2BCh] [rbp+1BCh]
  struct _DRVUTILS_UPDATE_INFO *v47; // [rsp+2C0h] [rbp+1C0h]
  unsigned __int64 v48; // [rsp+2C8h] [rbp+1C8h]

  v38 = a1;
  v40 = a6;
  v14 = 0;
  v39 = a9;
  v37 = a8;
  memset_0(&v42, 0, 0x230u);
  v42 = a2;
  v36 = 0;
  v34 = 0;
  v43 = 0;
  v44 = 0;
  memset(v41, 0, sizeof(v41));
  v15 = 0;
  v16 = 0;
  v46 = 0;
  v47 = 0;
  v48 = a11;
  DevRtlWriteTextLog(a11, 512, 196608, "{Select Drivers - %ws}", a3);
  v17 = a4;
  v18 = a4 & 2;
  v35 = v17 & 1;
  if ( (v17 & 1) != 0 )
  {
    if ( v18 )
    {
LABEL_3:
      LastError = 87;
      goto LABEL_50;
    }
  }
  else if ( !v18 )
  {
    if ( !a5 )
      goto LABEL_9;
    goto LABEL_8;
  }
  if ( !a5 )
    goto LABEL_3;
LABEL_8:
  if ( *((_DWORD *)a5 + 17) != 2 )
    goto LABEL_3;
LABEL_9:
  if ( v38 )
  {
    v14 = v38;
  }
  else
  {
    v14 = (struct HDRIVERSTORE__ *)DriverStoreOpenW(0, 0, 0, 0);
    if ( !v14 )
    {
      LastError = GetLastError();
      goto LABEL_50;
    }
  }
  v20 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceInstall_CheckDriverIntegrity>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_DeviceInstall_CheckDriverIntegrity>::GetImpl'::`2'::impl) != 0
      ? 4109
      : 5;
  if ( v35 )
  {
    DevRtlWriteTextLog(a11, 512, 4, "Selecting drivers by excluding installed drivers.");
    v21 = a2;
    if ( !PnpUtilsCreateExclusionDeviceDescriptor(a2, a5, (struct _DRIVERSTORE_DEVICE_DESCRIPTORW *)v41) )
    {
      v22 = GetLastError();
      v23 = "Failed to select excluded device drivers. Error = 0x%08X";
LABEL_26:
      LODWORD(v32) = v22;
      LastError = v22;
      DevRtlWriteTextLog(a11, 512, 1, v23, v32);
      goto LABEL_50;
    }
    v20 |= 0x100u;
    goto LABEL_17;
  }
  if ( v18 )
  {
    DevRtlWriteTextLog(a11, 512, 4, "Selecting drivers by preferring specified drivers.");
    v21 = a2;
    if ( !PnpUtilsCreateSelectionDeviceDescriptor(v14, a2, a5, (struct _DRIVERSTORE_DEVICE_DESCRIPTORW *)v41) )
    {
      v22 = GetLastError();
      v23 = "Failed to select preferred device drivers. Error = 0x%08X";
      goto LABEL_26;
    }
    v20 |= 0x200u;
LABEL_17:
    v47 = a5;
    goto LABEL_18;
  }
  DevRtlWriteTextLog(a11, 512, 4, "Selecting drivers using default selection criteria.");
  v21 = a2;
  if ( !(unsigned int)PnpUtilsCreateDeviceDescriptor(a2) )
  {
    v22 = GetLastError();
    v23 = "Failed to create device descriptor. Error = 0x%08X";
    goto LABEL_26;
  }
LABEL_18:
  v15 = v41;
  PnpUtilsLogDeviceDescriptor((struct _DRIVERSTORE_DEVICE_DESCRIPTORW *)v41, a11);
  if ( !(unsigned int)DriverStoreEnumDeviceDriversW(v14, 0, v41, v20, EnumSelectedDriversCallback, &v42) )
  {
    v22 = GetLastError();
    v23 = "Failed to enumerate device drivers. Error = 0x%08X";
    goto LABEL_26;
  }
  if ( v44 )
  {
    LastError = pSetupStringArrayToMultiSz(v43, v44, &v36, &v34);
    if ( LastError )
    {
      v16 = 0;
      goto LABEL_50;
    }
    v16 = v36;
    for ( i = v36; *i; i += (unsigned int)(v26 + 1) )
    {
      v26 = -1;
      do
        ++v26;
      while ( i[v26] );
      i[(unsigned int)v26] = 44;
    }
    v27 = v34;
    if ( v44 > 1 )
      v27 = v34 - 2;
    v16[((unsigned __int64)v27 >> 1) - 1] = 0;
  }
  else
  {
    DevRtlWriteTextLog(a11, 512, 4, "No drivers found.");
    v24 = HeapAlloc(hHeap, 0, 2u);
    v16 = v24;
    if ( !v24 )
    {
      LastError = 8;
      goto LABEL_50;
    }
    *v24 = 0;
    LastError = 0;
    LOWORD(v45[0]) = 0;
  }
  v28 = (_DWORD *)v37;
  if ( v37 && !v46 )
  {
    InstalledDriverCount = PnpUtilsGetInstalledDriverCount(v21);
    v30 = v46;
    v28 = (_DWORD *)v37;
    if ( v44 != InstalledDriverCount )
      v30 = 1;
    v46 = v30;
  }
  if ( v39 && (int)StringCchCopyW(v39, (unsigned int)a10, v45) < 0 )
  {
    LastError = 122;
  }
  else
  {
    *v40 = v16;
    v16 = 0;
    if ( v28 )
      *v28 = v46;
  }
LABEL_50:
  DevRtlWriteTextLog(a11, 512, 327680, "{Select Drivers - exit(0x%08X}", LastError);
  if ( v14 && !v38 )
    DriverStoreClose(v14);
  if ( v16 )
    HeapFree(hHeap, 0, v16);
  if ( v43 )
    pSetupFreeStringArray(v43);
  if ( v15 )
    PnpUtilsDestroyDeviceDescriptor(v15);
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x14002c2bc  mov     [rsp-8+arg_18], rbx
0x14002c2c1  push    rbp
0x14002c2c2  push    rsi
0x14002c2c3  push    rdi
0x14002c2c4  push    r12
0x14002c2c6  push    r13
0x14002c2c8  push    r14
0x14002c2ca  push    r15
0x14002c2cc  lea     rbp, [rsp-1E0h]
0x14002c2d4  sub     rsp, 2E0h
0x14002c2db  mov     rax, cs:__security_cookie
0x14002c2e2  xor     rax, rsp
0x14002c2e5  mov     [rbp+210h+var_40], rax
0x14002c2ec  mov     rax, [rbp+210h+arg_28]
0x14002c2f3  mov     rbx, r8
0x14002c2f6  mov     r14, [rbp+210h+arg_20]
0x14002c2fd  mov     esi, edx
0x14002c2ff  mov     [rsp+310h+var_2C0], rcx
0x14002c304  mov     r8d, 230h; Size
0x14002c30a  mov     rcx, [rbp+210h+arg_40]
0x14002c311  mov     r15d, r9d
0x14002c314  mov     [rsp+310h+var_2B0], rax
0x14002c319  xor     r12d, r12d
0x14002c31c  mov     rax, [rbp+210h+arg_38]
0x14002c323  mov     [rsp+310h+var_2B8], rcx
0x14002c328  lea     rcx, [rbp+210h+var_270]; void *
0x14002c32c  mov     [rsp+310h+dnDevInst], edx
0x14002c330  xor     edx, edx; Val
0x14002c332  mov     [rsp+310h+var_2C8], rax
0x14002c337  call    memset_0
0x14002c33c  xor     eax, eax
0x14002c33e  mov     [rbp+210h+var_270], esi
0x14002c341  mov     rsi, [rbp+210h+arg_50]
0x14002c348  lea     r9, aSelectDriversW; "{Select Drivers - %ws}"
0x14002c34f  xorps   xmm0, xmm0
0x14002c352  mov     [rsp+310h+var_2D0], rax
0x14002c357  mov     rcx, rsi
0x14002c35a  mov     [rsp+310h+var_2DC], eax
0x14002c35e  mov     edx, 200h
0x14002c363  mov     [rbp+210h+var_268], rax
0x14002c367  mov     r8d, 30000h
0x14002c36d  mov     [rbp+210h+var_260], eax
0x14002c370  movups  [rsp+310h+var_2A8], xmm0
0x14002c375  mov     r13d, eax
0x14002c378  mov     edi, eax
0x14002c37a  movups  [rsp+310h+var_298], xmm0
0x14002c37f  mov     [rbp+210h+var_54], eax
0x14002c385  movups  [rbp+210h+var_288], xmm0
0x14002c389  mov     [rbp+210h+var_50], rax
0x14002c390  mov     [rbp+210h+var_48], rsi
0x14002c397  mov     [rsp+310h+var_2F0], rbx
0x14002c39c  call    cs:__imp_DevRtlWriteTextLog
0x14002c3a2  mov     eax, r15d
0x14002c3a5  and     r15d, 2
0x14002c3a9  and     eax, 1
0x14002c3ac  mov     [rsp+310h+var_2D8], eax
0x14002c3b0  test    eax, eax
0x14002c3b2  jz      short loc_14002C3C6
0x14002c3b4  test    r15d, r15d
0x14002c3b7  jz      short loc_14002C3CB
0x14002c3b9  mov     ebx, 57h ; 'W'
0x14002c3be  xor     r14d, r14d
0x14002c3c1  jmp     loc_14002C6CB
0x14002c3c6  test    r15d, r15d
0x14002c3c9  jz      short loc_14002C3D2
0x14002c3cb  test    r14, r14
0x14002c3ce  jnz     short loc_14002C3D7
0x14002c3d0  jmp     short loc_14002C3B9
0x14002c3d2  test    r14, r14
0x14002c3d5  jz      short loc_14002C3DE
0x14002c3d7  cmp     dword ptr [r14+44h], 2
0x14002c3dc  jnz     short loc_14002C3B9
0x14002c3de  mov     rax, [rsp+310h+var_2C0]
0x14002c3e3  test    rax, rax
0x14002c3e6  jnz     short loc_14002C40A
0x14002c3e8  xor     r9d, r9d
0x14002c3eb  xor     r8d, r8d
0x14002c3ee  xor     edx, edx
0x14002c3f0  xor     ecx, ecx
0x14002c3f2  call    cs:__imp_DriverStoreOpenW
0x14002c3f8  mov     r12, rax
0x14002c3fb  test    rax, rax
0x14002c3fe  jnz     short loc_14002C40D
0x14002c400  call    cs:__imp_GetLastError
0x14002c406  mov     ebx, eax
0x14002c408  jmp     short loc_14002C3BE
0x14002c40a  mov     r12, rax
0x14002c40d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeviceInstall_CheckDriverIntegrity@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceInstall_CheckDriverIntegrity@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceInstall_CheckDriverIntegrity> `wil::Feature<__WilFeatureTraits_Feature_DeviceInstall_CheckDriverIntegrity>::GetImpl(void)'::`2'::impl
0x14002c414  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceInstall_CheckDriverIntegrity@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceInstall_CheckDriverIntegrity>::__private_IsEnabled(void)
0x14002c419  neg     al
0x14002c41b  mov     edx, 200h
0x14002c420  mov     r8d, 4
0x14002c426  mov     rcx, rsi
0x14002c429  sbb     ebx, ebx
0x14002c42b  and     ebx, 1008h
0x14002c431  add     ebx, 5
0x14002c434  cmp     [rsp+310h+var_2D8], edi
0x14002c438  jz      loc_14002C4F2
0x14002c43e  lea     r9, aSelectingDrive_1; "Selecting drivers by excluding installe"...
0x14002c445  call    cs:__imp_DevRtlWriteTextLog
0x14002c44b  mov     r15d, [rsp+310h+dnDevInst]
0x14002c450  lea     r8, [rsp+310h+var_2A8]; struct _DRIVERSTORE_DEVICE_DESCRIPTORW *
0x14002c455  mov     rdx, r14; struct _DRVUTILS_UPDATE_INFO *
0x14002c458  mov     ecx, r15d; dnDevInst
0x14002c45b  call    ?PnpUtilsCreateExclusionDeviceDescriptor@@YAHKPEAU_DRVUTILS_UPDATE_INFO@@PEAU_DRIVERSTORE_DEVICE_DESCRIPTORW@@@Z; PnpUtilsCreateExclusionDeviceDescriptor(ulong,_DRVUTILS_UPDATE_INFO *,_DRIVERSTORE_DEVICE_DESCRIPTORW *)
0x14002c460  test    eax, eax
0x14002c462  jnz     short loc_14002C490
0x14002c464  call    cs:__imp_GetLastError
0x14002c46a  lea     r9, aFailedToSelect_2; "Failed to select excluded device driver"...
0x14002c471  mov     edx, 200h
0x14002c476  mov     dword ptr [rsp+310h+var_2F0], eax
0x14002c47a  mov     r8d, 1
0x14002c480  mov     rcx, rsi
0x14002c483  mov     ebx, eax
0x14002c485  call    cs:__imp_DevRtlWriteTextLog
0x14002c48b  jmp     loc_14002C3BE
0x14002c490  bts     ebx, 8
0x14002c494  mov     [rbp+210h+var_50], r14
0x14002c49b  xor     r14d, r14d
0x14002c49e  mov     rdx, rsi; unsigned __int64
0x14002c4a1  lea     rcx, [rsp+310h+var_2A8]; struct _DRIVERSTORE_DEVICE_DESCRIPTORW *
0x14002c4a6  lea     r13, [rsp+310h+var_2A8]
0x14002c4ab  call    ?PnpUtilsLogDeviceDescriptor@@YAXPEAU_DRIVERSTORE_DEVICE_DESCRIPTORW@@_K@Z; PnpUtilsLogDeviceDescriptor(_DRIVERSTORE_DEVICE_DESCRIPTORW *,unsigned __int64)
0x14002c4b0  lea     rax, [rbp+210h+var_270]
0x14002c4b4  mov     r9d, ebx
0x14002c4b7  mov     [rsp+310h+var_2E8], rax
0x14002c4bc  lea     r8, [rsp+310h+var_2A8]
0x14002c4c1  lea     rax, ?EnumSelectedDriversCallback@@YAHPEAUHDRIVERSTORE__@@PEBGPEAU_DRIVERSTORE_DEVICE_DESCRIPTORW@@PEAU_DRIVERSTORE_DEVICE_DRIVER_INFOW@@_J@Z; EnumSelectedDriversCallback(HDRIVERSTORE__ *,ushort const *,_DRIVERSTORE_DEVICE_DESCRIPTORW *,_DRIVERSTORE_DEVICE_DRIVER_INFOW *,__int64)
0x14002c4c8  xor     edx, edx
0x14002c4ca  mov     rcx, r12
0x14002c4cd  mov     [rsp+310h+var_2F0], rax
0x14002c4d2  call    cs:__imp_DriverStoreEnumDeviceDriversW
0x14002c4d8  test    eax, eax
0x14002c4da  jnz     loc_14002C597
0x14002c4e0  call    cs:__imp_GetLastError
0x14002c4e6  lea     r9, aFailedToEnumer; "Failed to enumerate device drivers. Err"...
0x14002c4ed  jmp     loc_14002C578
0x14002c4f2  test    r15d, r15d
0x14002c4f5  jz      short loc_14002C53B
0x14002c4f7  lea     r9, aSelectingDrive; "Selecting drivers by preferring specifi"...
0x14002c4fe  call    cs:__imp_DevRtlWriteTextLog
0x14002c504  mov     r15d, [rsp+310h+dnDevInst]
0x14002c509  lea     r9, [rsp+310h+var_2A8]; struct _DRIVERSTORE_DEVICE_DESCRIPTORW *
0x14002c50e  mov     r8, r14; struct _DRVUTILS_UPDATE_INFO *
0x14002c511  mov     edx, r15d; unsigned int
0x14002c514  mov     rcx, r12; struct HDRIVERSTORE__ *
0x14002c517  call    ?PnpUtilsCreateSelectionDeviceDescriptor@@YAHPEAUHDRIVERSTORE__@@KPEAU_DRVUTILS_UPDATE_INFO@@PEAU_DRIVERSTORE_DEVICE_DESCRIPTORW@@@Z; PnpUtilsCreateSelectionDeviceDescriptor(HDRIVERSTORE__ *,ulong,_DRVUTILS_UPDATE_INFO *,_DRIVERSTORE_DEVICE_DESCRIPTORW *)
0x14002c51c  test    eax, eax
0x14002c51e  jnz     short loc_14002C532
0x14002c520  call    cs:__imp_GetLastError
0x14002c526  lea     r9, aFailedToSelect_1; "Failed to select preferred device drive"...
0x14002c52d  jmp     loc_14002C471
0x14002c532  bts     ebx, 9
0x14002c536  jmp     loc_14002C494
0x14002c53b  lea     r9, aSelectingDrive_0; "Selecting drivers using default selecti"...
0x14002c542  call    cs:__imp_DevRtlWriteTextLog
0x14002c548  mov     r15d, [rsp+310h+dnDevInst]
0x14002c54d  lea     rdx, [rsp+310h+var_2A8]
0x14002c552  mov     r8d, 1
0x14002c558  mov     ecx, r15d; dnDevInst
0x14002c55b  call    PnpUtilsCreateDeviceDescriptor
0x14002c560  xor     r14d, r14d
0x14002c563  test    eax, eax
0x14002c565  jnz     loc_14002C49E
0x14002c56b  call    cs:__imp_GetLastError
0x14002c571  lea     r9, aFailedToCreate; "Failed to create device descriptor. Err"...
0x14002c578  mov     edx, 200h
0x14002c57d  mov     dword ptr [rsp+310h+var_2F0], eax
0x14002c581  mov     r8d, 1
0x14002c587  mov     rcx, rsi
0x14002c58a  mov     ebx, eax
0x14002c58c  call    cs:__imp_DevRtlWriteTextLog
0x14002c592  jmp     loc_14002C6CB
0x14002c597  mov     edx, [rbp+210h+var_260]
0x14002c59a  test    edx, edx
0x14002c59c  jnz     short loc_14002C5EA
0x14002c59e  lea     r9, aNoDriversFound; "No drivers found."
0x14002c5a5  mov     edx, 200h
0x14002c5aa  mov     r8d, 4
0x14002c5b0  mov     rcx, rsi
0x14002c5b3  call    cs:__imp_DevRtlWriteTextLog
0x14002c5b9  mov     rcx, cs:hHeap; hHeap
0x14002c5c0  xor     edx, edx; dwFlags
0x14002c5c2  lea     r8d, [rdx+2]; dwBytes
0x14002c5c6  call    cs:__imp_HeapAlloc
0x14002c5cc  mov     rdi, rax
0x14002c5cf  test    rax, rax
0x14002c5d2  jnz     short loc_14002C5DC
0x14002c5d4  lea     ebx, [rax+8]
0x14002c5d7  jmp     loc_14002C6CB
0x14002c5dc  mov     [rax], r14w
0x14002c5e0  mov     ebx, r14d
0x14002c5e3  mov     word ptr [rbp+210h+var_25C], r14w
0x14002c5e8  jmp     short loc_14002C654
0x14002c5ea  mov     rcx, [rbp+210h+var_268]
0x14002c5ee  lea     r9, [rsp+310h+var_2DC]
0x14002c5f3  lea     r8, [rsp+310h+var_2D0]
0x14002c5f8  call    pSetupStringArrayToMultiSz
0x14002c5fd  mov     ebx, eax
0x14002c5ff  test    eax, eax
0x14002c601  jz      short loc_14002C60B
0x14002c603  mov     rdi, r14
0x14002c606  jmp     loc_14002C6CB
0x14002c60b  mov     rdi, [rsp+310h+var_2D0]
0x14002c610  mov     rdx, rdi
0x14002c613  cmp     [rdi], r14w
0x14002c617  jz      short loc_14002C63C
0x14002c619  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14002c61d  inc     rcx
0x14002c620  cmp     [rdx+rcx*2], r14w
0x14002c625  jnz     short loc_14002C61D
0x14002c627  mov     eax, ecx
0x14002c629  mov     word ptr [rdx+rax*2], 2Ch ; ','
0x14002c62f  lea     eax, [rcx+1]
0x14002c632  lea     rdx, [rdx+rax*2]
0x14002c636  cmp     [rdx], r14w
0x14002c63a  jnz     short loc_14002C619
0x14002c63c  cmp     [rbp+210h+var_260], 1
0x14002c640  mov     eax, [rsp+310h+var_2DC]
0x14002c644  jbe     short loc_14002C649
0x14002c646  add     eax, 0FFFFFFFEh
0x14002c649  mov     edx, eax
0x14002c64b  shr     rdx, 1
0x14002c64e  mov     [rdi+rdx*2-2], r14w
0x14002c654  mov     r11, [rsp+310h+var_2C8]
0x14002c659  test    r11, r11
0x14002c65c  jz      short loc_14002C68B
0x14002c65e  cmp     [rbp+210h+var_54], r14d
0x14002c665  jnz     short loc_14002C68B
0x14002c667  mov     ecx, r15d; dnDevInst
0x14002c66a  call    ?PnpUtilsGetInstalledDriverCount@@YAKK@Z; PnpUtilsGetInstalledDriverCount(ulong)
0x14002c66f  cmp     [rbp+210h+var_260], eax
0x14002c672  mov     eax, 1
0x14002c677  mov     edx, [rbp+210h+var_54]
0x14002c67d  mov     r11, [rsp+310h+var_2C8]
0x14002c682  cmovnz  edx, eax
0x14002c685  mov     [rbp+210h+var_54], edx
0x14002c68b  mov     rax, [rsp+310h+var_2B8]
0x14002c690  test    rax, rax
0x14002c693  jz      short loc_14002C6B2
0x14002c695  mov     edx, dword ptr [rbp+210h+arg_48]; unsigned __int64
0x14002c69b  lea     r8, [rbp+210h+var_25C]; unsigned __int16 *
0x14002c69f  mov     rcx, rax; unsigned __int16 *
0x14002c6a2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002c6a7  test    eax, eax
0x14002c6a9  jns     short loc_14002C6B2
0x14002c6ab  mov     ebx, 7Ah ; 'z'
0x14002c6b0  jmp     short loc_14002C6CB
0x14002c6b2  mov     rax, [rsp+310h+var_2B0]
0x14002c6b7  mov     [rax], rdi
0x14002c6ba  mov     rdi, r14
0x14002c6bd  test    r11, r11
0x14002c6c0  jz      short loc_14002C6CB
0x14002c6c2  mov     eax, [rbp+210h+var_54]
0x14002c6c8  mov     [r11], eax
0x14002c6cb  lea     r9, aSelectDriversE; "{Select Drivers - exit(0x%08X}"
0x14002c6d2  mov     dword ptr [rsp+310h+var_2F0], ebx
0x14002c6d6  mov     edx, 200h
0x14002c6db  mov     r8d, 50000h
0x14002c6e1  mov     rcx, rsi
0x14002c6e4  call    cs:__imp_DevRtlWriteTextLog
0x14002c6ea  test    r12, r12
0x14002c6ed  jz      short loc_14002C6FF
0x14002c6ef  cmp     [rsp+310h+var_2C0], r14
0x14002c6f4  jnz     short loc_14002C6FF
0x14002c6f6  mov     rcx, r12
0x14002c6f9  call    cs:__imp_DriverStoreClose
0x14002c6ff  test    rdi, rdi
0x14002c702  jz      short loc_14002C716
0x14002c704  mov     rcx, cs:hHeap; hHeap
0x14002c70b  mov     r8, rdi; lpMem
0x14002c70e  xor     edx, edx; dwFlags
0x14002c710  call    cs:__imp_HeapFree
0x14002c716  mov     rcx, [rbp+210h+var_268]
0x14002c71a  test    rcx, rcx
0x14002c71d  jz      short loc_14002C727
0x14002c71f  mov     edx, [rbp+210h+var_260]
0x14002c722  call    pSetupFreeStringArray
0x14002c727  test    r13, r13
0x14002c72a  jz      short loc_14002C734
0x14002c72c  mov     rcx, r13
0x14002c72f  call    PnpUtilsDestroyDeviceDescriptor
0x14002c734  mov     ecx, ebx; dwErrCode
0x14002c736  call    cs:__imp_SetLastError
0x14002c73c  test    ebx, ebx
0x14002c73e  mov     eax, r14d
0x14002c741  setz    al
0x14002c744  mov     rcx, [rbp+210h+var_40]
0x14002c74b  xor     rcx, rsp; StackCookie
0x14002c74e  call    __security_check_cookie
0x14002c753  mov     rbx, [rsp+310h+arg_18]
0x14002c75b  add     rsp, 2E0h
0x14002c762  pop     r15
0x14002c764  pop     r14
0x14002c766  pop     r13
0x14002c768  pop     r12
0x14002c76a  pop     rdi
0x14002c76b  pop     rsi
0x14002c76c  pop     rbp
0x14002c76d  retn
  ... truncated ...
```
