# CDsmDeviceTask::RemoveDevice(TASK_COMPLETION_STATUS *)

- ea: `0x1800191b0`
- end: `0x180019511`
- name: `?RemoveDevice@CDsmDeviceTask@@QEAAJPEAW4TASK_COMPLETION_STATUS@@@Z`
- size: `865`
- prototype: `__int64 __fastcall(CDsmDeviceTask *__hidden this, enum TASK_COMPLETION_STATUS *)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180034060`

## callees

- `0x180002c90`
- `0x1800042ec`
- `0x1800080f0`
- `0x1800088e0`
- `0x18000af5c`
- `0x18000e63c`
- `0x180017a34`
- `0x1800191b0`
- `0x180019518`
- `0x180022070`
- `0x180025294`
- `0x180027ba8`
- `0x18002f1b4`
- `0x1800360dc`
- `0x180036680`
- `0x180036a18`
- `0x180036ad4`
- `0x180036c20`
- `0x180036c34`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180019332`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800193fb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180019406`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180019332`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800193fb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180019406`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800194f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800194f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDsmDeviceTask::RemoveDevice(CDsmDeviceTask *this, enum TASK_COMPLETION_STATUS *a2)
{
  const OLECHAR *v4; // r15
  int LevelSortedList; // ebx
  CDsmDeviceTask *v6; // rcx
  __int64 i; // rdi
  int v8; // eax
  PVOID v9; // rcx
  const WCHAR *v10; // r8
  PVOID v11; // rcx
  const WCHAR *v12; // r8
  LPVOID *p_pv; // [rsp+20h] [rbp-E0h]
  struct tagPROPVARIANT pvar; // [rsp+30h] [rbp-D0h] BYREF
  void **v16; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h]
  __int128 v18; // [rsp+60h] [rbp-A0h] BYREF
  int v19; // [rsp+70h] [rbp-90h]
  int v20; // [rsp+74h] [rbp-8Ch]
  int v21; // [rsp+78h] [rbp-88h]
  int v22; // [rsp+7Ch] [rbp-84h]
  __m128i si128; // [rsp+80h] [rbp-80h]
  int v24; // [rsp+90h] [rbp-70h]
  int v25; // [rsp+94h] [rbp-6Ch]
  __int64 v26; // [rsp+98h] [rbp-68h]
  __int64 v27; // [rsp+A0h] [rbp-60h]
  struct tagPROPVARIANT v28; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v29[208]; // [rsp+D0h] [rbp-30h] BYREF
  bool v30; // [rsp+1B0h] [rbp+B0h] BYREF
  LPVOID pv; // [rsp+1B8h] [rbp+B8h] BYREF

  *(_DWORD *)a2 = 3;
  pv = 0;
  v4 = (const OLECHAR *)((char *)this + 16);
  p_pv = &pv;
  GetDeviceObjectStringProperty(2, (char *)this + 16, &DEVPKEY_NAME);
  v16 = &CDsmDeviceTree::`vftable';
  v17 = 0;
  v18 = 0;
  v19 = 17;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v24 = 0;
  v25 = 10;
  v26 = 0;
  v27 = 0;
  v20 = 1061158912;
  v21 = 1048576000;
  v22 = 1074790400;
  ATL::CAtlMap<_GUID,unsigned int,ATL::CElementTraits<_GUID>,ATL::CElementTraits<unsigned int>>::UpdateRehashThresholds(&v18);
  LevelSortedList = CDsmDeviceTree::PopulateDeviceTree((CDsmDeviceTree *)&v16, v4);
  if ( LevelSortedList >= 0 )
  {
    if ( CDsmDeviceTree::GetDeviceCount((CDsmDeviceTree *)&v16) )
    {
      memset(&pvar, 0, sizeof(pvar));
      LevelSortedList = CDsmDeviceTree::GetLevelSortedList(&v16, 3, &pvar);
      v6 = (CDsmDeviceTask *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LODWORD(p_pv) = pvar.lVal;
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_33771ca157e2352e8c67aa8b8aaebcd9_Traceguids,
          (unsigned int)LevelSortedList,
          p_pv);
      }
      if ( LevelSortedList >= 0 )
      {
        for ( i = 0; (unsigned int)i < pvar.lVal; i = (unsigned int)(i + 1) )
        {
          v8 = CDsmDeviceTask::_EjectDevnode(v6, *(const unsigned __int16 **)&pvar.bstrblobVal.pData[8 * i]);
          LevelSortedList = v8;
          if ( v8 < 0 )
          {
            if ( v8 == -2147022492 )
              *(_DWORD *)a2 = 10;
            break;
          }
        }
      }
      PropVariantClear((PROPVARIANT *)&pvar);
      if ( LevelSortedList >= 0 )
      {
        memset(&v28, 0, sizeof(v28));
        LevelSortedList = CDsmDeviceTree::GetLevelSortedList(&v16, 1, &v28);
        if ( LevelSortedList >= 0 )
        {
          memset(&pvar, 0, sizeof(pvar));
          LevelSortedList = CDsmDeviceTree::GetLevelSortedList(&v16, 2, &pvar);
          if ( LevelSortedList >= 0 )
          {
            CDsmDeviceScan::CDsmDeviceScan((CDsmDeviceScan *)v29);
            LevelSortedList = CDsmDeviceScan::InitializeRemovalWatcher((CDsmDeviceScan *)v29, v4);
            if ( LevelSortedList >= 0 )
            {
              if ( (int)CDsmDeviceTask::_RemovePairedDevnodes(this, &v28, &v30) >= 0 )
                CDsmDeviceTask::_RemovePnPDevnodes(this, &pvar, &v30);
              LevelSortedList = CDsmDeviceScan::WaitForDeviceRemove((CDsmDeviceScan *)v29);
              CDsmDeviceTree::RemoveDrivers((CDsmDeviceTree *)&v16);
            }
            CDsmDeviceScan::~CDsmDeviceScan((CDsmDeviceScan *)v29);
          }
          PropVariantClear((PROPVARIANT *)&pvar);
        }
        PropVariantClear((PROPVARIANT *)&v28);
        if ( LevelSortedList >= 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_33771ca157e2352e8c67aa8b8aaebcd9_Traceguids, v4);
          if ( (Microsoft_Windows_DeviceSetupManagerEnableBits & 1) != 0 )
          {
            v10 = &pwszLanguagesBuffer;
            if ( pv )
              v10 = (const WCHAR *)pv;
            McTemplateU0zj_EventWriteTransfer(v9, DeviceRemovalSucceeded, v10, this);
          }
          *(_DWORD *)a2 = 1;
          goto LABEL_39;
        }
      }
    }
    else
    {
      LevelSortedList = -2147467259;
    }
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_33771ca157e2352e8c67aa8b8aaebcd9_Traceguids,
      (unsigned int)LevelSortedList);
  if ( (Microsoft_Windows_DeviceSetupManagerEnableBits & 2) != 0 )
  {
    v12 = &pwszLanguagesBuffer;
    if ( pv )
      v12 = (const WCHAR *)pv;
    McTemplateU0zj_EventWriteTransfer(v11, DeviceRemovalTimeout, v12, this);
  }
LABEL_39:
  CDsmDeviceTree::~CDsmDeviceTree((CDsmDeviceTree *)&v16);
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)LevelSortedList;
}

```

## disassembly

```asm
0x1800191b0  mov     [rsp-8+arg_10], rbx
0x1800191b5  push    rbp
0x1800191b6  push    rsi
0x1800191b7  push    rdi
0x1800191b8  push    r14
0x1800191ba  push    r15
0x1800191bc  lea     rbp, [rsp-80h]
0x1800191c1  sub     rsp, 180h
0x1800191c8  mov     r14, rdx
0x1800191cb  mov     rsi, rcx
0x1800191ce  mov     dword ptr [rdx], 3
0x1800191d4  mov     [rbp+0A0h+pv], 0
0x1800191df  lea     r15, [rcx+10h]
0x1800191e3  lea     rax, [rbp+0A0h+pv]
0x1800191ea  mov     [rsp+1A0h+var_180], rax
0x1800191ef  xor     r9d, r9d
0x1800191f2  lea     r8, DEVPKEY_NAME
0x1800191f9  mov     rdx, r15
0x1800191fc  lea     ecx, [r9+2]
0x180019200  call    ?GetDeviceObjectStringProperty@@YAJW4_DEV_OBJECT_TYPE@@PEBGAEBU_DEVPROPKEY@@_NPEAPEAG@Z; GetDeviceObjectStringProperty(_DEV_OBJECT_TYPE,ushort const *,_DEVPROPKEY const &,bool,ushort * *)
0x180019205  lea     rax, ??_7CDsmDeviceTree@@6B@; const CDsmDeviceTree::`vftable'
0x18001920c  mov     [rsp+1A0h+var_150], rax
0x180019211  mov     [rsp+1A0h+var_148], 0
0x180019219  xorps   xmm0, xmm0
0x18001921c  movdqa  [rsp+1A0h+var_140], xmm0
0x180019222  mov     [rsp+1A0h+var_130], 11h
0x18001922a  movdqa  xmm1, cs:__xmm@000000000000000000000000ffffffff
0x180019232  movdqa  [rbp+0A0h+var_120], xmm1
0x180019237  mov     [rbp+0A0h+var_110], 0
0x18001923e  mov     edi, 0Ah
0x180019243  mov     [rbp+0A0h+var_10C], edi
0x180019246  mov     [rbp+0A0h+var_108], 0
0x18001924e  mov     [rbp+0A0h+var_100], 0
0x180019256  mov     [rsp+1A0h+var_12C], 3F400000h
0x18001925e  mov     [rsp+1A0h+var_128], 3E800000h
0x180019266  mov     [rsp+1A0h+var_124], 40100000h
0x18001926e  lea     rcx, [rsp+1A0h+var_140]
0x180019273  call    ?UpdateRehashThresholds@?$CAtlMap@U_GUID@@IV?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@I@3@@ATL@@AEAAXXZ; ATL::CAtlMap<_GUID,uint,ATL::CElementTraits<_GUID>,ATL::CElementTraits<uint>>::UpdateRehashThresholds(void)
0x180019278  nop
0x180019279  mov     rdx, r15; lpsz
0x18001927c  lea     rcx, [rsp+1A0h+var_150]; this
0x180019281  call    ?PopulateDeviceTree@CDsmDeviceTree@@QEAAJPEBG@Z; CDsmDeviceTree::PopulateDeviceTree(ushort const *)
0x180019286  mov     ebx, eax
0x180019288  test    eax, eax
0x18001928a  js      loc_18001947C
0x180019290  lea     rcx, [rsp+1A0h+var_150]; this
0x180019295  call    ?GetDeviceCount@CDsmDeviceTree@@QEAAIXZ; CDsmDeviceTree::GetDeviceCount(void)
0x18001929a  test    eax, eax
0x18001929c  jz      loc_180019477
0x1800192a2  xorps   xmm0, xmm0
0x1800192a5  xor     eax, eax
0x1800192a7  movups  xmmword ptr [rsp+1A0h+pvar], xmm0
0x1800192ac  mov     [rsp+1A0h+var_160], rax
0x1800192b1  lea     r8, [rsp+1A0h+pvar]
0x1800192b6  lea     edx, [rdi-7]
0x1800192b9  lea     rcx, [rsp+1A0h+var_150]
0x1800192be  call    ?GetLevelSortedList@CDsmDeviceTree@@QEAAJW4DDT_LIST_FILTER@@PEAUtagPROPVARIANT@@@Z; CDsmDeviceTree::GetLevelSortedList(DDT_LIST_FILTER,tagPROPVARIANT *)
0x1800192c3  mov     ebx, eax
0x1800192c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192cc  lea     rax, WPP_GLOBAL_Control
0x1800192d3  cmp     rcx, rax
0x1800192d6  jz      short loc_1800192FB
0x1800192d8  test    byte ptr [rcx+1Ch], 1
0x1800192dc  jz      short loc_1800192FB
0x1800192de  mov     edx, edi
0x1800192e0  mov     eax, dword ptr [rsp+1A0h+pvar+8]
0x1800192e4  mov     dword ptr [rsp+1A0h+var_180], eax
0x1800192e8  mov     r9d, ebx
0x1800192eb  lea     r8, WPP_33771ca157e2352e8c67aa8b8aaebcd9_Traceguids
0x1800192f2  mov     rcx, [rcx+10h]
0x1800192f6  call    WPP_SF_Dd
0x1800192fb  test    ebx, ebx
0x1800192fd  js      short loc_18001932D
0x1800192ff  xor     edi, edi
0x180019301  cmp     edi, dword ptr [rsp+1A0h+pvar+8]
0x180019305  jnb     short loc_18001932D
0x180019307  mov     rdx, [rsp+1A0h+var_160]
0x18001930c  mov     rdx, [rdx+rdi*8]; unsigned __int16 *
0x180019310  call    ?_EjectDevnode@CDsmDeviceTask@@AEAAJPEBG@Z; CDsmDeviceTask::_EjectDevnode(ushort const *)
0x180019315  mov     ebx, eax
0x180019317  test    eax, eax
0x180019319  js      short loc_18001931F
0x18001931b  inc     edi
0x18001931d  jmp     short loc_180019301
0x18001931f  cmp     eax, 80070964h
0x180019324  jnz     short loc_18001932D
0x180019326  mov     dword ptr [r14], 0Ah
0x18001932d  lea     rcx, [rsp+1A0h+pvar]; pvar
0x180019332  call    cs:__imp_PropVariantClear
0x180019338  test    ebx, ebx
0x18001933a  js      loc_18001947C
0x180019340  xorps   xmm0, xmm0
0x180019343  xor     eax, eax
0x180019345  movups  xmmword ptr [rbp+0A0h+var_F0], xmm0
0x180019349  mov     [rbp+0A0h+var_E0], rax
0x18001934d  lea     r8, [rbp+0A0h+var_F0]
0x180019351  lea     edx, [rax+1]
0x180019354  lea     rcx, [rsp+1A0h+var_150]
0x180019359  call    ?GetLevelSortedList@CDsmDeviceTree@@QEAAJW4DDT_LIST_FILTER@@PEAUtagPROPVARIANT@@@Z; CDsmDeviceTree::GetLevelSortedList(DDT_LIST_FILTER,tagPROPVARIANT *)
0x18001935e  mov     ebx, eax
0x180019360  test    eax, eax
0x180019362  js      loc_180019402
0x180019368  xorps   xmm0, xmm0
0x18001936b  xor     eax, eax
0x18001936d  movups  xmmword ptr [rsp+1A0h+pvar], xmm0
0x180019372  mov     [rsp+1A0h+var_160], rax
0x180019377  lea     r8, [rsp+1A0h+pvar]
0x18001937c  lea     edx, [rax+2]
0x18001937f  lea     rcx, [rsp+1A0h+var_150]
0x180019384  call    ?GetLevelSortedList@CDsmDeviceTree@@QEAAJW4DDT_LIST_FILTER@@PEAUtagPROPVARIANT@@@Z; CDsmDeviceTree::GetLevelSortedList(DDT_LIST_FILTER,tagPROPVARIANT *)
0x180019389  mov     ebx, eax
0x18001938b  test    eax, eax
0x18001938d  js      short loc_1800193F6
0x18001938f  lea     rcx, [rbp+0A0h+var_D0]; this
0x180019393  call    ??0CDsmDeviceScan@@QEAA@XZ; CDsmDeviceScan::CDsmDeviceScan(void)
0x180019398  nop
0x180019399  mov     rdx, r15; unsigned __int16 *
0x18001939c  lea     rcx, [rbp+0A0h+var_D0]; this
0x1800193a0  call    ?InitializeRemovalWatcher@CDsmDeviceScan@@QEAAJPEBG@Z; CDsmDeviceScan::InitializeRemovalWatcher(ushort const *)
0x1800193a5  mov     ebx, eax
0x1800193a7  test    eax, eax
0x1800193a9  js      short loc_1800193EC
0x1800193ab  lea     r8, [rbp+0A0h+arg_0]; bool *
0x1800193b2  lea     rdx, [rbp+0A0h+var_F0]; struct tagPROPVARIANT *
0x1800193b6  mov     rcx, rsi; this
0x1800193b9  call    ?_RemovePairedDevnodes@CDsmDeviceTask@@AEAAJAEBUtagPROPVARIANT@@PEA_N@Z; CDsmDeviceTask::_RemovePairedDevnodes(tagPROPVARIANT const &,bool *)
0x1800193be  test    eax, eax
0x1800193c0  js      short loc_1800193D6
0x1800193c2  lea     r8, [rbp+0A0h+arg_0]; bool *
0x1800193c9  lea     rdx, [rsp+1A0h+pvar]; struct tagPROPVARIANT *
0x1800193ce  mov     rcx, rsi; this
0x1800193d1  call    ?_RemovePnPDevnodes@CDsmDeviceTask@@AEAAXAEBUtagPROPVARIANT@@PEA_N@Z; CDsmDeviceTask::_RemovePnPDevnodes(tagPROPVARIANT const &,bool *)
0x1800193d6  lea     rcx, [rbp+0A0h+var_D0]; this
0x1800193da  call    ?WaitForDeviceRemove@CDsmDeviceScan@@QEAAJXZ; CDsmDeviceScan::WaitForDeviceRemove(void)
0x1800193df  mov     ebx, eax
0x1800193e1  lea     rcx, [rsp+1A0h+var_150]; this
0x1800193e6  call    ?RemoveDrivers@CDsmDeviceTree@@QEAAJXZ; CDsmDeviceTree::RemoveDrivers(void)
0x1800193eb  nop
0x1800193ec  lea     rcx, [rbp+0A0h+var_D0]; this
0x1800193f0  call    ??1CDsmDeviceScan@@UEAA@XZ; CDsmDeviceScan::~CDsmDeviceScan(void)
0x1800193f5  nop
0x1800193f6  lea     rcx, [rsp+1A0h+pvar]; pvar
0x1800193fb  call    cs:__imp_PropVariantClear
0x180019401  nop
0x180019402  lea     rcx, [rbp+0A0h+var_F0]; pvar
0x180019406  call    cs:__imp_PropVariantClear
0x18001940c  test    ebx, ebx
0x18001940e  js      short loc_18001947C
0x180019410  mov     rcx, cs:WPP_GLOBAL_Control
0x180019417  lea     rax, WPP_GLOBAL_Control
0x18001941e  cmp     rcx, rax
0x180019421  jz      short loc_180019441
0x180019423  test    byte ptr [rcx+1Ch], 1
0x180019427  jz      short loc_180019441
0x180019429  mov     edx, 0Bh
0x18001942e  mov     r9, r15
0x180019431  lea     r8, WPP_33771ca157e2352e8c67aa8b8aaebcd9_Traceguids
0x180019438  mov     rcx, [rcx+10h]
0x18001943c  call    WPP_SF_S
0x180019441  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, 1
0x180019448  jz      short loc_18001946E
0x18001944a  lea     r8, pwszLanguagesBuffer
0x180019451  mov     rax, [rbp+0A0h+pv]
0x180019458  test    rax, rax
0x18001945b  cmovnz  r8, rax
0x18001945f  mov     r9, rsi
0x180019462  lea     rdx, DeviceRemovalSucceeded
0x180019469  call    McTemplateU0zj_EventWriteTransfer
0x18001946e  mov     dword ptr [r14], 1
0x180019475  jmp     short loc_1800194DB
0x180019477  mov     ebx, 80004005h
0x18001947c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019483  lea     rax, WPP_GLOBAL_Control
0x18001948a  cmp     rcx, rax
0x18001948d  jz      short loc_1800194AD
0x18001948f  test    byte ptr [rcx+1Ch], 4
0x180019493  jz      short loc_1800194AD
0x180019495  mov     edx, 0Ch
0x18001949a  mov     r9d, ebx
0x18001949d  lea     r8, WPP_33771ca157e2352e8c67aa8b8aaebcd9_Traceguids
0x1800194a4  mov     rcx, [rcx+10h]
0x1800194a8  call    WPP_SF_d
0x1800194ad  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, 2
0x1800194b4  jz      short loc_1800194DB
0x1800194b6  lea     r8, pwszLanguagesBuffer
0x1800194bd  mov     rax, [rbp+0A0h+pv]
0x1800194c4  test    rax, rax
0x1800194c7  cmovnz  r8, rax
0x1800194cb  mov     r9, rsi
0x1800194ce  lea     rdx, DeviceRemovalTimeout
0x1800194d5  call    McTemplateU0zj_EventWriteTransfer
0x1800194da  nop
0x1800194db  lea     rcx, [rsp+1A0h+var_150]; this
0x1800194e0  call    ??1CDsmDeviceTree@@UEAA@XZ; CDsmDeviceTree::~CDsmDeviceTree(void)
0x1800194e5  nop
0x1800194e6  mov     rcx, [rbp+0A0h+pv]; pv
0x1800194ed  test    rcx, rcx
0x1800194f0  jz      short loc_1800194F8
0x1800194f2  call    cs:__imp_CoTaskMemFree
0x1800194f8  mov     eax, ebx
0x1800194fa  mov     rbx, [rsp+1A0h+arg_10]
0x180019502  add     rsp, 180h
0x180019509  pop     r15
0x18001950b  pop     r14
0x18001950d  pop     rdi
0x18001950e  pop     rsi
0x18001950f  pop     rbp
0x180019510  retn
```
