# CDeviceInitializeJob::StartSetFirmwareConfiguration(void)

- ea: `0x14006b040`
- end: `0x14006b409`
- name: `?StartSetFirmwareConfiguration@CDeviceInitializeJob@@AEAAHXZ`
- size: `969`
- prototype: `__int64 __fastcall(CDeviceInitializeJob *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400699d0`

## callees

- `0x14000688c`
- `0x14000c940`
- `0x140016d00`
- `0x14001d4c0`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002eeb8`
- `0x1400317ac`
- `0x140032580`
- `0x14003fefc`
- `0x140063a48`
- `0x1400683ac`
- `0x1400688c0`
- `0x1400689a8`
- `0x14006b040`
- `0x1400dc4c8`
- `0x1400dfd00`
- `0x1400e0100`

## pseudocode

```c
__int64 __fastcall CDeviceInitializeJob::StartSetFirmwareConfiguration(CDeviceInitializeJob *this)
{
  int v2; // edx
  int v3; // r8d
  CPropertyCache *AdapterPropertyCache; // rax
  __int64 v5; // rdx
  CAdapter *v6; // rcx
  CPropertyCache *v7; // rax
  __int64 v8; // r8
  int v9; // eax
  int v10; // edx
  int v11; // r8d
  int v12; // edi
  CPropertyCache *v13; // rax
  unsigned int WdiSetAdapterConfigurationToIhv; // eax
  int v15; // edx
  int v16; // r8d
  unsigned int v17; // edi
  unsigned int v18; // eax
  int v19; // r9d
  __int64 v21; // [rsp+38h] [rbp-C8h]
  unsigned int v22; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v23; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int8 *v24; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v25[10]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SourceString[264]; // [rsp+A0h] [rbp-60h] BYREF

  v25[0] = v25[0] & 0xFFFFFFE0;
  v24 = 0;
  v23 = 0;
  *(_QWORD *)((char *)&v25[1] + 4) = 0;
  LODWORD(v25[3]) = 0;
  v25[4] = 0;
  LOBYTE(v25[5]) = 0;
  LODWORD(v25[6]) = 0;
  v25[7] = 0;
  LOBYTE(v25[8]) = 0;
  LODWORD(v25[9]) = 0;
  BYTE4(v25[9]) = 0;
  LOWORD(v25[1]) = 0;
  v22 = 0;
  memset(SourceString, 0, 0x208u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v2,
      v3,
      14,
      (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  memset(v25, 0, sizeof(v25));
  if ( CDeviceInitializeJob::CheckForNetworkAddressChange(
         (CAdapter **)this,
         (struct _WDI_MAC_ADDRESS *)((char *)v25 + 4)) )
  {
    LODWORD(v25[0]) &= ~1u;
  }
  else
  {
    LODWORD(v25[0]) |= 1u;
  }
  AdapterPropertyCache = CJobBase::get_AdapterPropertyCache(this);
  CPropertyCache::GetPropertyULong(AdapterPropertyCache, 0x18u, (unsigned int *)&v25[1] + 1);
  LODWORD(v25[0]) |= 2u;
  ArrayOfElements<_WDI_LINK_QUALITY_BAR_MAP_PARAMETERS>::AllocateElements(&v25[6], 2, 0);
  *(_BYTE *)(v25[7] + 2LL) = 0;
  *(_BYTE *)v25[7] = 0;
  *(_BYTE *)(v25[7] + 1LL) = 49;
  *(_BYTE *)(v25[7] + 5LL) = 1;
  *(_BYTE *)(v25[7] + 3LL) = 50;
  *(_BYTE *)(v25[7] + 4LL) = 100;
  LODWORD(v25[0]) |= 0x10u;
  LODWORD(v25[9]) = 3;
  KmWlanStateSeparation_GetMutableRegistryKey(
    SourceString,
    v5,
    L"Software\\Microsoft\\Wlansvc",
    L"Parameters\\CustomScanParameters");
  if ( !(unsigned int)CAdapter::ReadRegDword(v6, SourceString, L"WlanScanMode", &v22) && v22 == 500 )
  {
    v7 = CJobBase::get_AdapterPropertyCache(this);
    LOBYTE(v8) = 1;
    v9 = CPropertyCache::SetPropertyBoolean(v7, 114, v8);
    if ( v9 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v11,
        15,
        (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v9);
    }
    LODWORD(v25[9]) = 2;
  }
  v12 = *(_DWORD *)(*((_QWORD *)this + 68) + 5372LL);
  v13 = CJobBase::get_AdapterPropertyCache(this);
  if ( CPropertyCache::GetPropertyBooleanOrDefault(v13, 0x15u, 0) || (BYTE4(v25[9]) = 1, !v12) )
    BYTE4(v25[9]) = 0;
  WdiSetAdapterConfigurationToIhv = GenerateWdiSetAdapterConfigurationToIhv(
                                      (unsigned int)v25,
                                      48,
                                      (unsigned int)*((_QWORD *)this + 68) + 5384,
                                      (unsigned int)&v23,
                                      (__int64)&v24);
  v17 = WdiSetAdapterConfigurationToIhv;
  if ( WdiSetAdapterConfigurationToIhv )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v21) = WdiSetAdapterConfigurationToIhv;
      LOBYTE(v15) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v15,
        v16,
        16,
        (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v21);
    }
  }
  else
  {
    v18 = DeviceCommand::Initialize((CDeviceInitializeJob *)((char *)this + 1088), 0xFFFF, 85, v23, v24);
    v17 = v18;
    if ( v18 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_29;
      v19 = 17;
    }
    else
    {
      LODWORD(v25[0]) |= 4u;
      LODWORD(v25[2]) = 1;
      *((_DWORD *)this + 134) = 1;
      v18 = CJobBase::QueueDeviceCommand(this, (CDeviceInitializeJob *)((char *)this + 1088), v16);
      v17 = v18;
      if ( !v18 )
      {
        *((_QWORD *)this + 159) = v24;
        v24 = 0;
        goto LABEL_29;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_29;
      v19 = 18;
    }
    LODWORD(v21) = v18;
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      v16,
      v19,
      (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v21);
  }
LABEL_29:
  if ( v24 )
    operator delete(v24);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v15) = 5;
    LODWORD(v21) = v17;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      v16,
      19,
      (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v21);
  }
  _WDI_SET_FIRMWARE_CONFIGURATION_PARAMETERS::~_WDI_SET_FIRMWARE_CONFIGURATION_PARAMETERS((_WDI_SET_FIRMWARE_CONFIGURATION_PARAMETERS *)v25);
  return v17;
}

```

## disassembly

```asm
0x14006b040  mov     [rsp-8+arg_8], rbx
0x14006b045  mov     [rsp-8+arg_10], rsi
0x14006b04a  push    rbp
0x14006b04b  push    rdi
0x14006b04c  push    r13
0x14006b04e  push    r14
0x14006b050  push    r15
0x14006b052  lea     rbp, [rsp-1C0h]
0x14006b05a  sub     rsp, 2C0h
0x14006b061  mov     rax, cs:__security_cookie
0x14006b068  xor     rax, rsp
0x14006b06b  mov     [rbp+1E0h+var_30], rax
0x14006b072  and     [rsp+2E0h+var_290], 0FFFFFFE0h
0x14006b077  xor     r14d, r14d
0x14006b07a  xor     eax, eax
0x14006b07c  mov     [rsp+2E0h+var_298], r14
0x14006b081  mov     rbx, rcx
0x14006b084  mov     [rsp+2E0h+var_29C], r14d
0x14006b089  lea     rcx, [rbp+1E0h+SourceString]; void *
0x14006b08d  mov     qword ptr [rsp+2E0h+var_284], r14
0x14006b092  xor     edx, edx; Val
0x14006b094  mov     [rsp+2E0h+var_278], r14d
0x14006b099  mov     r8d, 208h; Size
0x14006b09f  mov     [rsp+2E0h+var_270], r14
0x14006b0a4  mov     [rsp+2E0h+var_268], r14b
0x14006b0a9  mov     [rbp+1E0h+var_260], r14d
0x14006b0ad  mov     [rbp+1E0h+var_258], r14
0x14006b0b1  mov     [rbp+1E0h+var_250], r14b
0x14006b0b5  mov     [rbp+1E0h+var_248], r14d
0x14006b0b9  mov     [rbp+1E0h+var_244], r14b
0x14006b0bd  mov     dword ptr [rsp+2E0h+var_28C.Address], eax
0x14006b0c1  mov     word ptr [rsp+2E0h+var_28C.Address+4], ax
0x14006b0c6  mov     [rsp+2E0h+var_2A0], r14d
0x14006b0cb  call    memset
0x14006b0d0  lea     r15, WPP_RECORDER_INITIALIZED
0x14006b0d7  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006b0de  lea     r13, WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids
0x14006b0e5  jz      short loc_14006B11D
0x14006b0e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b0ee  cmp     byte ptr [rcx+29h], 5
0x14006b0f2  jnb     short loc_14006B0FB
0x14006b0f4  cmp     [rcx+48h], r14w
0x14006b0f9  jz      short loc_14006B11D
0x14006b0fb  mov     eax, [rbx+10h]
0x14006b0fe  mov     r9d, 0Eh
0x14006b104  mov     rcx, [rcx+40h]
0x14006b108  mov     dl, 5
0x14006b10a  mov     [rsp+2E0h+var_2B0], eax
0x14006b10e  mov     [rsp+2E0h+var_2B8], rbx
0x14006b113  mov     [rsp+2E0h+var_2C0], r13
0x14006b118  call    WPP_RECORDER_SF_qD
0x14006b11d  xor     edx, edx; Val
0x14006b11f  lea     rcx, [rsp+2E0h+var_290]; void *
0x14006b124  lea     r8d, [rdx+50h]; Size
0x14006b128  call    memset
0x14006b12d  lea     rdx, [rsp+2E0h+var_28C]; struct _WDI_MAC_ADDRESS *
0x14006b132  mov     rcx, rbx; this
0x14006b135  call    ?CheckForNetworkAddressChange@CDeviceInitializeJob@@AEAAHPEAU_WDI_MAC_ADDRESS@@@Z; CDeviceInitializeJob::CheckForNetworkAddressChange(_WDI_MAC_ADDRESS *)
0x14006b13a  test    eax, eax
0x14006b13c  jnz     short loc_14006B145
0x14006b13e  or      [rsp+2E0h+var_290], 1
0x14006b143  jmp     short loc_14006B14A
0x14006b145  and     [rsp+2E0h+var_290], 0FFFFFFFEh
0x14006b14a  mov     rcx, rbx; this
0x14006b14d  call    ?get_AdapterPropertyCache@CJobBase@@IEAAPEAVCAdapterPropertyCache@@XZ; CJobBase::get_AdapterPropertyCache(void)
0x14006b152  lea     r8, [rsp+2E0h+var_284]; unsigned int *
0x14006b157  mov     edx, 18h; unsigned int
0x14006b15c  mov     rcx, rax; this
0x14006b15f  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x14006b164  mov     esi, 2
0x14006b169  lea     rcx, [rbp+1E0h+var_260]
0x14006b16d  or      [rsp+2E0h+var_290], esi
0x14006b171  mov     edx, esi
0x14006b173  xor     r8d, r8d
0x14006b176  call    ?AllocateElements@?$ArrayOfElements@U_WDI_LINK_QUALITY_BAR_MAP_PARAMETERS@@@@QEAAHI_K@Z; ArrayOfElements<_WDI_LINK_QUALITY_BAR_MAP_PARAMETERS>::AllocateElements(uint,unsigned __int64)
0x14006b17b  mov     rax, [rbp+1E0h+var_258]
0x14006b17f  lea     r9, aParametersCust; "Parameters\\CustomScanParameters"
0x14006b186  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Wlansvc"
0x14006b18d  lea     rcx, [rbp+1E0h+SourceString]; SourceString
0x14006b191  mov     [rax+2], r14b
0x14006b195  mov     rax, [rbp+1E0h+var_258]
0x14006b199  mov     [rax], r14b
0x14006b19c  mov     rax, [rbp+1E0h+var_258]
0x14006b1a0  mov     byte ptr [rax+1], 31h ; '1'
0x14006b1a4  mov     rax, [rbp+1E0h+var_258]
0x14006b1a8  mov     byte ptr [rax+5], 1
0x14006b1ac  mov     rax, [rbp+1E0h+var_258]
0x14006b1b0  mov     byte ptr [rax+3], 32h ; '2'
0x14006b1b4  mov     rax, [rbp+1E0h+var_258]
0x14006b1b8  mov     byte ptr [rax+4], 64h ; 'd'
0x14006b1bc  or      [rsp+2E0h+var_290], 10h
0x14006b1c1  mov     [rbp+1E0h+var_248], 3
0x14006b1c8  call    KmWlanStateSeparation_GetMutableRegistryKey
0x14006b1cd  lea     r9, [rsp+2E0h+var_2A0]; unsigned int *
0x14006b1d2  lea     r8, aWlanscanmode; "WlanScanMode"
0x14006b1d9  lea     rdx, [rbp+1E0h+SourceString]; unsigned __int16 *
0x14006b1dd  call    ?ReadRegDword@CAdapter@@QEAAHPEAG0PEAK@Z; CAdapter::ReadRegDword(ushort *,ushort *,ulong *)
0x14006b1e2  test    eax, eax
0x14006b1e4  jnz     short loc_14006B242
0x14006b1e6  cmp     [rsp+2E0h+var_2A0], 1F4h
0x14006b1ee  jnz     short loc_14006B242
0x14006b1f0  mov     rcx, rbx; this
0x14006b1f3  call    ?get_AdapterPropertyCache@CJobBase@@IEAAPEAVCAdapterPropertyCache@@XZ; CJobBase::get_AdapterPropertyCache(void)
0x14006b1f8  mov     r8b, 1; unsigned __int8
0x14006b1fb  lea     edx, [rsi+70h]; unsigned int
0x14006b1fe  mov     rcx, rax; this
0x14006b201  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x14006b206  test    eax, eax
0x14006b208  jz      short loc_14006B23F
0x14006b20a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006b211  jz      short loc_14006B23F
0x14006b213  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b21a  lea     r9d, [rsi+0Dh]
0x14006b21e  mov     dword ptr [rsp+2E0h+var_2A8], eax
0x14006b222  mov     dl, sil
0x14006b225  mov     eax, [rbx+10h]
0x14006b228  mov     [rsp+2E0h+var_2B0], eax
0x14006b22c  mov     rcx, [rcx+40h]
0x14006b230  mov     [rsp+2E0h+var_2B8], rbx
0x14006b235  mov     [rsp+2E0h+var_2C0], r13
0x14006b23a  call    WPP_RECORDER_SF_qDD
0x14006b23f  mov     [rbp+1E0h+var_248], esi
0x14006b242  mov     rax, [rbx+220h]
0x14006b249  mov     rcx, rbx; this
0x14006b24c  mov     edi, [rax+14FCh]
0x14006b252  call    ?get_AdapterPropertyCache@CJobBase@@IEAAPEAVCAdapterPropertyCache@@XZ; CJobBase::get_AdapterPropertyCache(void)
0x14006b257  xor     r8d, r8d; unsigned __int8
0x14006b25a  mov     rcx, rax; this
0x14006b25d  lea     edx, [r8+15h]; unsigned int
0x14006b261  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x14006b266  test    al, al
0x14006b268  jnz     short loc_14006B272
0x14006b26a  mov     [rbp+1E0h+var_244], 1
0x14006b26e  test    edi, edi
0x14006b270  jnz     short loc_14006B276
0x14006b272  mov     [rbp+1E0h+var_244], r14b
0x14006b276  mov     r8, [rbx+220h]
0x14006b27d  lea     rax, [rsp+2E0h+var_298]
0x14006b282  add     r8, 1508h
0x14006b289  mov     [rsp+2E0h+var_2C0], rax
0x14006b28e  lea     r9, [rsp+2E0h+var_29C]
0x14006b293  mov     edx, 30h ; '0'
0x14006b298  lea     rcx, [rsp+2E0h+var_290]
0x14006b29d  call    GenerateWdiSetAdapterConfigurationToIhv
0x14006b2a2  mov     edi, eax
0x14006b2a4  test    eax, eax
0x14006b2a6  jz      short loc_14006B2CE
0x14006b2a8  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006b2af  jz      loc_14006B37F
0x14006b2b5  mov     ecx, [rbx+10h]
0x14006b2b8  mov     r9d, 10h
0x14006b2be  mov     dword ptr [rsp+2E0h+var_2A8], eax
0x14006b2c2  mov     dl, sil
0x14006b2c5  mov     [rsp+2E0h+var_2B0], ecx
0x14006b2c9  jmp     loc_14006B352
0x14006b2ce  mov     rax, [rsp+2E0h+var_298]
0x14006b2d3  lea     rsi, [rbx+440h]
0x14006b2da  mov     r9d, [rsp+2E0h+var_29C]; unsigned int
0x14006b2df  mov     rcx, rsi; this
0x14006b2e2  mov     edx, 0FFFFh; unsigned __int16
0x14006b2e7  mov     [rsp+2E0h+var_2C0], rax; unsigned __int8 *
0x14006b2ec  mov     r8d, 55h ; 'U'; unsigned int
0x14006b2f2  call    ?Initialize@DeviceCommand@@QEAAHGKKPEAE@Z; DeviceCommand::Initialize(ushort,ulong,ulong,uchar *)
0x14006b2f7  mov     edi, eax
0x14006b2f9  test    eax, eax
0x14006b2fb  jz      short loc_14006B30E
0x14006b2fd  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006b304  jz      short loc_14006B37F
0x14006b306  mov     r9d, 11h
0x14006b30c  jmp     short loc_14006B345
0x14006b30e  or      [rsp+2E0h+var_290], 4
0x14006b313  mov     rdx, rsi; struct DeviceCommand *
0x14006b316  mov     rcx, rbx; this
0x14006b319  mov     [rsp+2E0h+var_284+4], 1
0x14006b321  mov     dword ptr [rbx+218h], 1
0x14006b32b  call    ?QueueDeviceCommand@CJobBase@@IEAAHPEAVDeviceCommand@@@Z; CJobBase::QueueDeviceCommand(DeviceCommand *)
0x14006b330  mov     edi, eax
0x14006b332  test    eax, eax
0x14006b334  jz      short loc_14006B36E
0x14006b336  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006b33d  jz      short loc_14006B37F
0x14006b33f  mov     r9d, 12h
0x14006b345  mov     dword ptr [rsp+2E0h+var_2A8], eax
0x14006b349  mov     dl, 2
0x14006b34b  mov     eax, [rbx+10h]
0x14006b34e  mov     [rsp+2E0h+var_2B0], eax
0x14006b352  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b359  mov     [rsp+2E0h+var_2B8], rbx
0x14006b35e  mov     [rsp+2E0h+var_2C0], r13
0x14006b363  mov     rcx, [rcx+40h]
0x14006b367  call    WPP_RECORDER_SF_qDD
0x14006b36c  jmp     short loc_14006B37F
0x14006b36e  mov     rax, [rsp+2E0h+var_298]
0x14006b373  mov     [rbx+4F8h], rax
0x14006b37a  mov     [rsp+2E0h+var_298], r14
0x14006b37f  mov     rcx, [rsp+2E0h+var_298]; void *
0x14006b384  test    rcx, rcx
0x14006b387  jz      short loc_14006B38E
0x14006b389  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14006b38e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006b395  jz      short loc_14006B3D1
0x14006b397  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b39e  cmp     byte ptr [rcx+29h], 5
0x14006b3a2  jnb     short loc_14006B3AB
0x14006b3a4  cmp     [rcx+48h], r14w
0x14006b3a9  jz      short loc_14006B3D1
0x14006b3ab  mov     eax, [rbx+10h]
0x14006b3ae  mov     r9d, 13h
0x14006b3b4  mov     rcx, [rcx+40h]
0x14006b3b8  mov     dl, 5
0x14006b3ba  mov     dword ptr [rsp+2E0h+var_2A8], edi
0x14006b3be  mov     [rsp+2E0h+var_2B0], eax
0x14006b3c2  mov     [rsp+2E0h+var_2B8], rbx
0x14006b3c7  mov     [rsp+2E0h+var_2C0], r13
0x14006b3cc  call    WPP_RECORDER_SF_qDD
0x14006b3d1  lea     rcx, [rsp+2E0h+var_290]; this
0x14006b3d6  call    ??1_WDI_SET_FIRMWARE_CONFIGURATION_PARAMETERS@@QEAA@XZ; _WDI_SET_FIRMWARE_CONFIGURATION_PARAMETERS::~_WDI_SET_FIRMWARE_CONFIGURATION_PARAMETERS(void)
0x14006b3db  mov     eax, edi
0x14006b3dd  mov     rcx, [rbp+1E0h+var_30]
0x14006b3e4  xor     rcx, rsp; StackCookie
0x14006b3e7  call    __security_check_cookie
0x14006b3ec  lea     r11, [rsp+2E0h+var_20]
0x14006b3f4  mov     rbx, [r11+38h]
0x14006b3f8  mov     rsi, [r11+40h]
0x14006b3fc  mov     rsp, r11
0x14006b3ff  pop     r15
0x14006b401  pop     r14
0x14006b403  pop     r13
0x14006b405  pop     rdi
0x14006b406  pop     rbp
0x14006b407  retn
```
