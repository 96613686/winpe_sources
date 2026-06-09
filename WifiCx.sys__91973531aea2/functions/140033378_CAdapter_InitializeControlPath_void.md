# CAdapter::InitializeControlPath(void)

- ea: `0x140033378`
- end: `0x1400338ea`
- name: `?InitializeControlPath@CAdapter@@QEAAJXZ`
- size: `1394`
- prototype: `__int64 __fastcall(CAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x1400cee44`

## callees

- `0x140004d48`
- `0x1400069dc`
- `0x140009420`
- `0x14000c778`
- `0x14000c940`
- `0x14000d054`
- `0x140016d00`
- `0x14002aaec`
- `0x140032580`
- `0x140033378`
- `0x1400338f0`
- `0x140036aac`
- `0x140054804`
- `0x140054f60`
- `0x140055e18`
- `0x140055ea0`
- `0x1400587e0`
- `0x140067478`
- `0x14006e5ec`
- `0x140095e14`
- `0x1400d8b94`
- `0x1400dc4c8`
- `0x1400dfd00`
- `0x1400dfd40`
- `0x1400e0100`

## string_xrefs

- `0x1400334af`: `System\CurrentControlSet\Services\WlanSvc`
- `0x1400334c9`: `SecondaryStaConfig`

## pseudocode

```c
__int64 __fastcall CAdapter::InitializeControlPath(CAdapter *this)
{
  int v2; // edx
  int v3; // ebx
  struct _WFC_REG_ENTRY *v4; // r8
  unsigned int v5; // r9d
  CRegistryHelper *v6; // r14
  char v7; // bp
  int PropertiesFromRegistry; // eax
  int v9; // edx
  int v10; // r9d
  __int64 v11; // rdx
  CAdapter *v12; // rcx
  int v13; // edx
  unsigned int v14; // ebx
  _DWORD *v15; // rax
  int v16; // edx
  _DWORD *v17; // rbx
  __int64 v18; // rax
  int v19; // edx
  unsigned int v20; // ebx
  __int64 i; // rcx
  unsigned int v22; // edx
  __int64 v23; // rcx
  int v25; // [rsp+20h] [rbp-298h]
  __int64 v26; // [rsp+28h] [rbp-290h]
  unsigned int v27[4]; // [rsp+40h] [rbp-278h] BYREF
  WCHAR SourceString[264]; // [rsp+50h] [rbp-268h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      116,
      (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids);
  }
  *((_QWORD *)this + 91) = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  v3 = CAdapterPropertyCache::Initialize((CAdapter *)((char *)this + 56));
  if ( v3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        1,
        117,
        (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids);
    goto LABEL_60;
  }
  v6 = (CRegistryHelper *)operator new(0x10u);
  if ( v6 )
  {
    *(_QWORD *)v6 = *((_QWORD *)this + 10);
    v7 = 0;
    *((_QWORD *)v6 + 1) = 0;
    PropertiesFromRegistry = CRegistryHelper::LoadPropertiesFromRegistry(v6, (CAdapter *)((char *)this + 56), v4, v5);
    v3 = PropertiesFromRegistry;
    if ( PropertiesFromRegistry )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v10 = 119;
LABEL_12:
        LODWORD(v26) = PropertiesFromRegistry;
        LOBYTE(v9) = 2;
LABEL_50:
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          1,
          v10,
          (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids,
          v26);
      }
    }
    else
    {
      v27[0] = 0;
      memset(SourceString, 0, 0x208u);
      if ( !(unsigned int)KmWlanStateSeparation_GetMutableRegistryKey(
                            SourceString,
                            v11,
                            L"System\\CurrentControlSet\\Services\\WlanSvc",
                            L"Parameters\\SecondarySta")
        && !(unsigned int)CAdapter::ReadRegDword(v12, SourceString, L"SecondaryStaConfig", v27) )
      {
        v14 = v27[0];
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            1,
            120,
            (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids,
            v27[0]);
        }
        *((_DWORD *)this + 1344) = v14;
      }
      if ( (unsigned int)Feature_55721363__private_IsEnabledDeviceUsageNoInline(v12) )
      {
        CAdapter::QueryPLDRCapability(this);
      }
      else
      {
        v15 = operator new(0x50u);
        v17 = v15;
        if ( v15 )
        {
          memset(v15, 0, 0x50u);
          *v17 = 65616;
          v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01031 + 1616))(
                  WdfDriverGlobals,
                  *((_QWORD *)this + 10),
                  off_14010E308);
          LOWORD(v26) = 1;
          LOWORD(v25) = 80;
          if ( !(*(unsigned int (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, GUID *, _DWORD *, int, _DWORD, _QWORD))(WdfFunctions_01031 + 1048))(
                  WdfDriverGlobals,
                  *(_QWORD *)(v18 + 8),
                  &GUID_DEVICE_RESET_INTERFACE_STANDARD,
                  v17,
                  v25,
                  v26,
                  0)
            && (v17[10] & 2) != 0 )
          {
            *((_DWORD *)this + 1343) = 1;
          }
          operator delete(v17);
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = 4;
          WPP_RECORDER_SF_DD(
            WPP_GLOBAL_Control->DeviceExtension,
            v16,
            1,
            121,
            (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids,
            *((_DWORD *)this + 1343),
            0);
        }
      }
      v27[0] = 0;
      if ( !(unsigned int)CPropertyCache::GetPropertyULong((CAdapter *)((char *)this + 56), 0x42u, v27) )
      {
        v20 = v27[0];
        if ( v27[0] != -1 && (v27[0] != 0) != (*((_DWORD *)this + 1343) != 0) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v26) = v27[0];
            LOBYTE(v19) = 2;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v19,
              1,
              122,
              (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids,
              v26);
          }
          *((_DWORD *)this + 1343) = v20;
        }
      }
      CPropertyCache::GetPropertyULong((CAdapter *)((char *)this + 56), 0x30u, &g_Test_FeatureMask);
      for ( i = 0; i != 6; ++i )
      {
        *((_QWORD *)this + 12 * i + 609) = this;
        _InterlockedAdd((volatile signed __int32 *)this + 24 * i + 1196, 1u);
      }
      CPropertyCache::SetPropertyULong((CAdapter *)((char *)this + 56), 0x2Cu, 0xFFFFFFFF);
      PropertiesFromRegistry = CAdapter::InitializeControlPathFoundation(this);
      v3 = PropertiesFromRegistry;
      if ( PropertiesFromRegistry )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v10 = 123;
          goto LABEL_12;
        }
      }
      else
      {
        v7 = 1;
        CPropertyCache::GetPropertyULong((CAdapter *)((char *)this + 56), 0x41u, (unsigned int *)this + 188);
        if ( *((_DWORD *)this + 188) )
        {
          CAdapter::SimulateFirmwareHang(this, v22);
        }
        else
        {
          v3 = CAdapter::ControlResetRecovery(this);
          if ( v3 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_(
                WPP_GLOBAL_Control->DeviceExtension,
                2,
                1,
                124,
                (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids);
            goto LABEL_51;
          }
        }
        CBSSListManager::Initialize((char *)this + 1336, this, (char *)this + 56, 1);
        CBSSListManager::Initialize((char *)this + 1736, this, (char *)this + 56, 4);
        CServicesManager::Initialize((CAdapter *)((char *)this + 3360), this, (CAdapter *)((char *)this + 56));
        PropertiesFromRegistry = CAdapter::RegisterForAdapterNotifications(this);
        v3 = PropertiesFromRegistry;
        if ( !PropertiesFromRegistry )
        {
          if ( !(unsigned int)Feature_55721363__private_IsEnabledDeviceUsageNoInline(v23) )
            CAdapter::RegisterForPDCStandbyNotifications(this);
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_51;
          v10 = 126;
          LODWORD(v26) = 0;
          LOBYTE(v9) = 4;
          goto LABEL_50;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v10 = 125;
          goto LABEL_12;
        }
      }
    }
LABEL_51:
    if ( *((_QWORD *)v6 + 1) )
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01031 + 1848))(WdfDriverGlobals);
    operator delete(v6);
    if ( v3 && v7 )
      CAdapter::DeInitializeControlPathFoundation(this, 0);
    goto LABEL_60;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      1,
      118,
      (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids);
  v3 = -1073741670;
LABEL_60:
  *((_BYTE *)this + 4657) = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v26) = v3;
    LOBYTE(v2) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v2,
      1,
      127,
      (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids,
      v26);
  }
  return v3 != 0 ? 0xC0000001 : 0;
}

```

## disassembly

```asm
0x140033378  push    rbx
0x14003337a  push    rbp
0x14003337b  push    rsi
0x14003337c  push    rdi
0x14003337d  push    r12
0x14003337f  push    r13
0x140033381  push    r14
0x140033383  push    r15
0x140033385  sub     rsp, 278h
0x14003338c  mov     rax, cs:__security_cookie
0x140033393  xor     rax, rsp
0x140033396  mov     [rsp+2B8h+var_58], rax
0x14003339e  mov     rdi, rcx
0x1400333a1  xor     r15d, r15d
0x1400333a4  lea     r13, WPP_RECORDER_INITIALIZED
0x1400333ab  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400333b2  lea     rbp, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x1400333b9  lea     r12d, [r15+1]
0x1400333bd  jz      short loc_1400333EC
0x1400333bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400333c6  cmp     byte ptr [rcx+29h], 5
0x1400333ca  jnb     short loc_1400333D3
0x1400333cc  cmp     [rcx+48h], r15w
0x1400333d1  jz      short loc_1400333EC
0x1400333d3  mov     rcx, [rcx+40h]
0x1400333d7  mov     r9d, 74h ; 't'
0x1400333dd  mov     r8d, r12d
0x1400333e0  mov     [rsp+2B8h+var_298], rbp
0x1400333e5  mov     dl, 5
0x1400333e7  call    WPP_RECORDER_SF_
0x1400333ec  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400333f3  lea     rsi, [rdi+38h]
0x1400333f7  mov     rcx, rsi; this
0x1400333fa  mov     [rdi+2D8h], rax
0x140033401  call    ?Initialize@CAdapterPropertyCache@@QEAAHXZ; CAdapterPropertyCache::Initialize(void)
0x140033406  mov     ebx, eax
0x140033408  test    eax, eax
0x14003340a  jz      short loc_14003343E
0x14003340c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140033413  jz      loc_14003387B
0x140033419  mov     rcx, cs:WPP_GLOBAL_Control
0x140033420  mov     r9d, 75h ; 'u'
0x140033426  mov     r8d, r12d
0x140033429  mov     [rsp+2B8h+var_298], rbp
0x14003342e  mov     dl, 2
0x140033430  mov     rcx, [rcx+40h]
0x140033434  call    WPP_RECORDER_SF_
0x140033439  jmp     loc_14003387B
0x14003343e  mov     ecx, 10h; unsigned __int64
0x140033443  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140033448  mov     r14, rax
0x14003344b  test    rax, rax
0x14003344e  jz      loc_14003384D
0x140033454  mov     rax, [rdi+50h]
0x140033458  mov     rdx, rsi; struct CPropertyCache *
0x14003345b  mov     rcx, r14; this
0x14003345e  mov     [r14], rax
0x140033461  mov     bpl, r15b
0x140033464  mov     [r14+8], r15
0x140033468  call    ?LoadPropertiesFromRegistry@CRegistryHelper@@QEAAHPEAVCPropertyCache@@PEAU_WFC_REG_ENTRY@@K@Z; CRegistryHelper::LoadPropertiesFromRegistry(CPropertyCache *,_WFC_REG_ENTRY *,ulong)
0x14003346d  mov     ebx, eax
0x14003346f  test    eax, eax
0x140033471  jz      short loc_140033491
0x140033473  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003347a  jz      loc_140033806
0x140033480  mov     r9d, 77h ; 'w'
0x140033486  mov     dword ptr [rsp+2B8h+var_290], eax
0x14003348a  mov     dl, 2
0x14003348c  jmp     loc_1400337E7
0x140033491  xor     edx, edx; Val
0x140033493  mov     [rsp+2B8h+var_278], r15d
0x140033498  mov     r8d, 208h; Size
0x14003349e  lea     rcx, [rsp+2B8h+SourceString]; void *
0x1400334a3  call    memset
0x1400334a8  lea     r9, aParametersSeco; "Parameters\\SecondarySta"
0x1400334af  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Wl"...
0x1400334b6  lea     rcx, [rsp+2B8h+SourceString]; SourceString
0x1400334bb  call    KmWlanStateSeparation_GetMutableRegistryKey
0x1400334c0  test    eax, eax
0x1400334c2  jnz     short loc_14003351A
0x1400334c4  lea     r9, [rsp+2B8h+var_278]; unsigned int *
0x1400334c9  lea     r8, aSecondarystaco; "SecondaryStaConfig"
0x1400334d0  lea     rdx, [rsp+2B8h+SourceString]; unsigned __int16 *
0x1400334d5  call    ?ReadRegDword@CAdapter@@QEAAHPEAG0PEAK@Z; CAdapter::ReadRegDword(ushort *,ushort *,ulong *)
0x1400334da  test    eax, eax
0x1400334dc  jnz     short loc_14003351A
0x1400334de  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400334e5  mov     ebx, [rsp+2B8h+var_278]
0x1400334e9  jz      short loc_140033514
0x1400334eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400334f2  lea     r9d, [rax+78h]
0x1400334f6  lea     rax, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x1400334fd  mov     dword ptr [rsp+2B8h+var_290], ebx
0x140033501  mov     r8d, r12d
0x140033504  mov     [rsp+2B8h+var_298], rax
0x140033509  mov     dl, 2
0x14003350b  mov     rcx, [rcx+40h]
0x14003350f  call    WPP_RECORDER_SF_d
0x140033514  mov     [rdi+1500h], ebx
0x14003351a  call    Feature_55721363__private_IsEnabledDeviceUsageNoInline
0x14003351f  test    eax, eax
0x140033521  jz      short loc_140033530
0x140033523  mov     rcx, rdi; this
0x140033526  call    ?QueryPLDRCapability@CAdapter@@AEAAXXZ; CAdapter::QueryPLDRCapability(void)
0x14003352b  jmp     loc_140033612
0x140033530  mov     ecx, 50h ; 'P'; unsigned __int64
0x140033535  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003353a  mov     rbx, rax
0x14003353d  test    rax, rax
0x140033540  jz      loc_1400335D3
0x140033546  xor     edx, edx; Val
0x140033548  mov     rcx, rax; void *
0x14003354b  lea     r8d, [rdx+50h]; Size
0x14003354f  call    memset
0x140033554  mov     dword ptr [rbx], 10050h
0x14003355a  mov     rcx, cs:WdfFunctions_01031
0x140033561  mov     r8, cs:off_14010E308
0x140033568  mov     rdx, [rdi+50h]
0x14003356c  mov     rax, [rcx+650h]
0x140033573  mov     rcx, cs:WdfDriverGlobals
0x14003357a  call    _guard_dispatch_icall
0x14003357f  mov     rcx, cs:WdfFunctions_01031
0x140033586  lea     r8, GUID_DEVICE_RESET_INTERFACE_STANDARD
0x14003358d  mov     [rsp+2B8h+var_288], r15
0x140033592  mov     r9, rbx
0x140033595  mov     word ptr [rsp+2B8h+var_290], r12w
0x14003359b  mov     rdx, [rax+8]
0x14003359f  mov     rax, [rcx+418h]
0x1400335a6  mov     rcx, cs:WdfDriverGlobals
0x1400335ad  mov     word ptr [rsp+2B8h+var_298], 50h ; 'P'
0x1400335b4  call    _guard_dispatch_icall
0x1400335b9  test    eax, eax
0x1400335bb  jnz     short loc_1400335CB
0x1400335bd  mov     eax, [rbx+28h]
0x1400335c0  test    al, 2
0x1400335c2  jz      short loc_1400335CB
0x1400335c4  mov     [rdi+14FCh], r12d
0x1400335cb  mov     rcx, rbx; void *
0x1400335ce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400335d3  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400335da  jz      short loc_140033612
0x1400335dc  mov     eax, [rdi+14FCh]
0x1400335e2  mov     r9d, 79h ; 'y'
0x1400335e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400335ef  mov     r8d, r12d
0x1400335f2  mov     dword ptr [rsp+2B8h+var_288], r15d
0x1400335f7  mov     dl, 4
0x1400335f9  mov     dword ptr [rsp+2B8h+var_290], eax
0x1400335fd  lea     rax, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x140033604  mov     [rsp+2B8h+var_298], rax
0x140033609  mov     rcx, [rcx+40h]
0x14003360d  call    WPP_RECORDER_SF_DD
0x140033612  lea     r8, [rsp+2B8h+var_278]; unsigned int *
0x140033617  mov     [rsp+2B8h+var_278], r15d
0x14003361c  mov     edx, 42h ; 'B'; unsigned int
0x140033621  mov     rcx, rsi; this
0x140033624  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x140033629  test    eax, eax
0x14003362b  jnz     short loc_140033689
0x14003362d  mov     ebx, [rsp+2B8h+var_278]
0x140033631  cmp     ebx, 0FFFFFFFFh
0x140033634  jz      short loc_140033689
0x140033636  test    ebx, ebx
0x140033638  mov     ecx, r15d
0x14003363b  mov     eax, r15d
0x14003363e  setnz   cl
0x140033641  cmp     [rdi+14FCh], r15d
0x140033648  setnz   al
0x14003364b  cmp     ecx, eax
0x14003364d  jz      short loc_140033689
0x14003364f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140033656  jz      short loc_140033683
0x140033658  mov     rcx, cs:WPP_GLOBAL_Control
0x14003365f  lea     rax, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x140033666  mov     r9d, 7Ah ; 'z'
0x14003366c  mov     dword ptr [rsp+2B8h+var_290], ebx
0x140033670  mov     r8d, r12d
0x140033673  mov     [rsp+2B8h+var_298], rax
0x140033678  mov     dl, 2
0x14003367a  mov     rcx, [rcx+40h]
0x14003367e  call    WPP_RECORDER_SF_d
0x140033683  mov     [rdi+14FCh], ebx
0x140033689  lea     r8, ?g_Test_FeatureMask@@3KA; unsigned int *
0x140033690  mov     edx, 30h ; '0'; unsigned int
0x140033695  mov     rcx, rsi; this
0x140033698  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x14003369d  mov     rcx, r15
0x1400336a0  lea     rax, [rcx+rcx*2]
0x1400336a4  shl     rax, 5
0x1400336a8  mov     [rax+rdi+1308h], rdi
0x1400336b0  lock add [rax+rdi+12B0h], r12d
0x1400336b9  add     rcx, r12
0x1400336bc  cmp     rcx, 6
0x1400336c0  jnz     short loc_1400336A0
0x1400336c2  lea     edx, [rcx+26h]; unsigned int
0x1400336c5  or      r8d, 0FFFFFFFFh; unsigned int
0x1400336c9  mov     rcx, rsi; this
0x1400336cc  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x1400336d1  mov     rcx, rdi; this
0x1400336d4  call    ?InitializeControlPathFoundation@CAdapter@@AEAAHXZ; CAdapter::InitializeControlPathFoundation(void)
0x1400336d9  mov     ebx, eax
0x1400336db  test    eax, eax
0x1400336dd  jz      short loc_1400336F7
0x1400336df  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400336e6  jz      loc_140033806
0x1400336ec  mov     r9d, 7Bh ; '{'
0x1400336f2  jmp     loc_140033486
0x1400336f7  lea     rbx, [rdi+2F0h]
0x1400336fe  mov     edx, 41h ; 'A'; unsigned int
0x140033703  mov     r8, rbx; unsigned int *
0x140033706  mov     rcx, rsi; this
0x140033709  mov     bpl, r12b
0x14003370c  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x140033711  mov     rcx, rdi; this
0x140033714  cmp     [rbx], r15d
0x140033717  jz      short loc_140033783
0x140033719  call    ?SimulateFirmwareHang@CAdapter@@QEAAHK@Z; CAdapter::SimulateFirmwareHang(ulong)
0x14003371e  lea     rcx, [rdi+538h]
0x140033725  mov     r9d, r12d
0x140033728  mov     r8, rsi
0x14003372b  mov     rdx, rdi
0x14003372e  call    ?Initialize@CBSSListManager@@QEAAHPEAVCAdapter@@PEAVCAdapterPropertyCache@@W4_WFC_PORT_TYPE@@@Z; CBSSListManager::Initialize(CAdapter *,CAdapterPropertyCache *,_WFC_PORT_TYPE)
0x140033733  lea     rcx, [rdi+6C8h]
0x14003373a  mov     r9d, 4
0x140033740  mov     r8, rsi
0x140033743  mov     rdx, rdi
0x140033746  call    ?Initialize@CBSSListManager@@QEAAHPEAVCAdapter@@PEAVCAdapterPropertyCache@@W4_WFC_PORT_TYPE@@@Z; CBSSListManager::Initialize(CAdapter *,CAdapterPropertyCache *,_WFC_PORT_TYPE)
0x14003374b  lea     rcx, [rdi+0D20h]; this
0x140033752  mov     r8, rsi; struct CAdapterPropertyCache *
0x140033755  mov     rdx, rdi; struct CAdapter *
0x140033758  call    ?Initialize@CServicesManager@@QEAAHPEAVCAdapter@@PEAVCAdapterPropertyCache@@@Z; CServicesManager::Initialize(CAdapter *,CAdapterPropertyCache *)
0x14003375d  mov     rcx, rdi; this
0x140033760  call    ?RegisterForAdapterNotifications@CAdapter@@QEAAHXZ; CAdapter::RegisterForAdapterNotifications(void)
0x140033765  mov     ebx, eax
0x140033767  test    eax, eax
0x140033769  jz      short loc_1400337C0
0x14003376b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140033772  jz      loc_140033806
0x140033778  mov     r9d, 7Dh ; '}'
0x14003377e  jmp     loc_140033486
0x140033783  call    ?ControlResetRecovery@CAdapter@@QEAAHXZ; CAdapter::ControlResetRecovery(void)
0x140033788  mov     ebx, eax
0x14003378a  test    eax, eax
0x14003378c  jz      short loc_14003371E
0x14003378e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140033795  jz      short loc_140033806
0x140033797  mov     rcx, cs:WPP_GLOBAL_Control
0x14003379e  lea     rax, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x1400337a5  mov     r9d, 7Ch ; '|'
0x1400337ab  mov     [rsp+2B8h+var_298], rax
0x1400337b0  mov     r8d, r12d
0x1400337b3  mov     dl, 2
0x1400337b5  mov     rcx, [rcx+40h]
0x1400337b9  call    WPP_RECORDER_SF_
0x1400337be  jmp     short loc_140033806
0x1400337c0  call    Feature_55721363__private_IsEnabledDeviceUsageNoInline
0x1400337c5  test    eax, eax
0x1400337c7  jnz     short loc_1400337D1
0x1400337c9  mov     rcx, rdi; Context
0x1400337cc  call    ?RegisterForPDCStandbyNotifications@CAdapter@@QEAAXXZ; CAdapter::RegisterForPDCStandbyNotifications(void)
0x1400337d1  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400337d8  jz      short loc_140033806
0x1400337da  mov     r9d, 7Eh ; '~'
0x1400337e0  mov     dword ptr [rsp+2B8h+var_290], r15d
0x1400337e5  mov     dl, 4
0x1400337e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400337ee  lea     rax, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x1400337f5  mov     r8d, r12d
0x1400337f8  mov     [rsp+2B8h+var_298], rax
0x1400337fd  mov     rcx, [rcx+40h]
0x140033801  call    WPP_RECORDER_SF_d
0x140033806  mov     rdx, [r14+8]
0x14003380a  test    rdx, rdx
0x14003380d  jz      short loc_140033829
0x14003380f  mov     rax, cs:WdfFunctions_01031
0x140033816  mov     rcx, cs:WdfDriverGlobals
0x14003381d  mov     rax, [rax+738h]
0x140033824  call    _guard_dispatch_icall
0x140033829  mov     rcx, r14; void *
0x14003382c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140033831  test    ebx, ebx
0x140033833  jz      short loc_140033844
0x140033835  test    bpl, bpl
0x140033838  jz      short loc_140033844
0x14003383a  xor     edx, edx; bool
0x14003383c  mov     rcx, rdi; this
0x14003383f  call    ?DeInitializeControlPathFoundation@CAdapter@@AEAAX_N@Z; CAdapter::DeInitializeControlPathFoundation(bool)
0x140033844  lea     rbp, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x14003384b  jmp     short loc_14003387B
0x14003384d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140033854  jz      short loc_140033876
0x140033856  mov     rcx, cs:WPP_GLOBAL_Control
0x14003385d  mov     r9d, 76h ; 'v'
0x140033863  mov     r8d, r12d
0x140033866  mov     [rsp+2B8h+var_298], rbp
0x14003386b  mov     dl, 2
0x14003386d  mov     rcx, [rcx+40h]
0x140033871  call    WPP_RECORDER_SF_
0x140033876  mov     ebx, 0C000009Ah
0x14003387b  mov     [rdi+1231h], r12b
  ... truncated ...
```
