# SystemSettings::StorageSenseHandlers::CStorageCleanupItem::Cleanup(CORRELATION_VECTOR,std::vector<SystemSettings::StorageSenseHandlers::PluginCleanupStart,std::allocator<SystemSettings::StorageSenseHandlers::PluginCleanupStart>> *,std::vector<SystemSettings::StorageSenseHandlers::PluginCleanupStop,std::allocator<SystemSettings::StorageSenseHandlers::PluginCleanupStop>> *,unsigned __int64 *)

- ea: `0x1800884d0`
- end: `0x180088de4`
- name: `?Cleanup@CStorageCleanupItem@StorageSenseHandlers@SystemSettings@@QEAAJUCORRELATION_VECTOR@@PEAV?$vector@UPluginCleanupStart@StorageSenseHandlers@SystemSettings@@V?$allocator@UPluginCleanupStart@StorageSenseHandlers@SystemSettings@@@std@@@std@@PEAV?$vector@UPluginCleanupStop@StorageSenseHandlers@SystemSettings@@V?$allocator@UPluginCleanupStop@StorageSenseHandlers@SystemSettings@@@std@@@6@PEA_K@Z`
- size: `2324`
- prototype: `__int64 __usercall@<rax>(SystemSettings::DataModel::CSettingBase *this@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008e1d0`
- `0x18008f150`

## callees

- `0x180006e50`
- `0x180007a00`
- `0x180084f50`
- `0x180085c98`
- `0x180085cc4`
- `0x180085df8`
- `0x180085fc0`
- `0x1800877c8`
- `0x180087854`
- `0x180087ffc`
- `0x1800884d0`
- `0x18008dff8`
- `0x180090a3c`
- `0x180091b18`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180088777`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180088777`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008862b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088671`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088d6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088d78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088d87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088da1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008862b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088671`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088d6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088d78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088d87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088da1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800886c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800886e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180088766`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800887c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180088ae4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180088b03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180088b16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180088cb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800886c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800886e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180088766`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800887c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180088ae4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180088b03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180088b16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180088cb1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180088940`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180088981`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180088a84`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180088aa9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180088940`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180088981`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180088a84`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180088aa9`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x1800888b0`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x1800888b0`
- `ext-ms-win-storage-sense-l1-2-2!GetStorageDeviceSize` at `0x1800888d7`
- `ext-ms-win-storage-sense-l1-2-2!GetStorageDeviceSize` at `0x1800889dc`
- `ext-ms-win-storage-sense-l1-2-2!GetStorageDeviceSize` at `0x1800888d7`
- `ext-ms-win-storage-sense-l1-2-2!GetStorageDeviceSize` at `0x1800889dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::StorageSenseHandlers::CStorageCleanupItem::Cleanup(
        SystemSettings::DataModel::CSettingBase *this,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4,
        _QWORD *a5)
{
  SystemSettings::DataModel::CSettingBase *v6; // r15
  __int64 v7; // rdi
  void (__fastcall *v8)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v9; // rdi
  void (__fastcall *v10)(__int64, _QWORD, HSTRING *); // rbx
  int v11; // edx
  unsigned int v12; // r14d
  unsigned int v13; // r12d
  const OLECHAR *v14; // rax
  __int64 v15; // r13
  unsigned int v16; // ebx
  int v17; // edi
  GUID v18; // xmm6
  const unsigned __int16 *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  unsigned int *v22; // rax
  int StorageDeviceInfo; // r14d
  enum _STORAGE_RESERVE_ID i; // ebx
  ULONGLONG TickCount64; // rbx
  _QWORD *v26; // rdi
  __int64 *v27; // r13
  __int64 v28; // rcx
  double v29; // xmm8_8
  double v30; // xmm8_8
  enum _STORAGE_RESERVE_ID j; // ebx
  unsigned __int64 v32; // r14
  unsigned __int64 v33; // r15
  unsigned __int64 v34; // r12
  __int64 v35; // r13
  PCWSTR v36; // rsi
  bool v37; // di
  PCWSTR v38; // rbx
  PCWSTR v39; // rax
  __int64 v40; // r9
  __int64 v41; // rcx
  unsigned __int64 v42; // r13
  unsigned __int64 v43; // rcx
  double v44; // xmm7_8
  double v45; // xmm7_8
  unsigned int v46; // ebx
  int v47; // edi
  unsigned __int64 v48; // rsi
  unsigned __int64 v49; // r14
  unsigned __int64 v50; // r15
  unsigned __int64 v51; // r12
  GUID v52; // xmm6
  const unsigned __int16 *v53; // rax
  __int64 v54; // rax
  __int64 v55; // rdx
  unsigned int v57; // [rsp+80h] [rbp-948h]
  _BYTE v58[4]; // [rsp+90h] [rbp-938h] BYREF
  int v59; // [rsp+94h] [rbp-934h] BYREF
  unsigned int v60[2]; // [rsp+98h] [rbp-930h] BYREF
  _QWORD *v61; // [rsp+A0h] [rbp-928h]
  HSTRING string; // [rsp+A8h] [rbp-920h] BYREF
  unsigned __int64 v63; // [rsp+B0h] [rbp-918h] BYREF
  HSTRING v64; // [rsp+B8h] [rbp-910h] BYREF
  unsigned __int64 v65; // [rsp+C0h] [rbp-908h]
  PCWSTR StringRawBuffer; // [rsp+C8h] [rbp-900h] BYREF
  unsigned __int64 v67; // [rsp+D0h] [rbp-8F8h] BYREF
  unsigned __int64 v68; // [rsp+D8h] [rbp-8F0h]
  unsigned __int64 v69; // [rsp+E0h] [rbp-8E8h]
  unsigned __int64 v70; // [rsp+E8h] [rbp-8E0h]
  unsigned __int64 v71; // [rsp+F0h] [rbp-8D8h] BYREF
  SystemSettings::DataModel::CSettingBase *v72; // [rsp+F8h] [rbp-8D0h]
  __int64 v73; // [rsp+100h] [rbp-8C8h]
  unsigned __int64 v74; // [rsp+108h] [rbp-8C0h]
  _QWORD *v75; // [rsp+110h] [rbp-8B8h]
  unsigned __int64 v76; // [rsp+118h] [rbp-8B0h] BYREF
  unsigned __int64 v77; // [rsp+120h] [rbp-8A8h] BYREF
  _QWORD *v78; // [rsp+128h] [rbp-8A0h]
  SystemSettings::DataModel::CSettingBase *v79; // [rsp+138h] [rbp-890h]
  __int64 *v80; // [rsp+148h] [rbp-880h]
  struct _GUID v81; // [rsp+160h] [rbp-868h] BYREF
  struct _GUID v82; // [rsp+170h] [rbp-858h] BYREF
  __m128i si128; // [rsp+180h] [rbp-848h]
  __m128i v84; // [rsp+190h] [rbp-838h]
  __int64 v85; // [rsp+1A0h] [rbp-828h]
  __int64 v86; // [rsp+1A8h] [rbp-820h]
  __int64 v87; // [rsp+1B0h] [rbp-818h]
  GUID pclsid; // [rsp+1C0h] [rbp-808h] BYREF
  _OWORD v89[8]; // [rsp+1D0h] [rbp-7F8h] BYREF
  __int16 v90; // [rsp+250h] [rbp-778h]
  _BYTE v91[336]; // [rsp+2E0h] [rbp-6E8h] BYREF
  int v92; // [rsp+430h] [rbp-598h] BYREF
  _BYTE v93[1116]; // [rsp+434h] [rbp-594h] BYREF
  _BYTE v94[96]; // [rsp+890h] [rbp-138h] BYREF
  _BYTE v95[96]; // [rsp+8F0h] [rbp-D8h] BYREF

  v74 = a4;
  *(_QWORD *)&v82.Data1 = a3;
  v73 = a2;
  v6 = this;
  v72 = this;
  v79 = this;
  v87 = a2;
  v63 = a4;
  v61 = a5;
  v80 = (__int64 *)((char *)this + 272);
  v65 = *((_QWORD *)this + 34);
  v71 = v65;
  v64 = 0;
  string = 0;
  v85 = 0;
  v86 = 0;
  v59 = 0;
  v77 = 0;
  v76 = 0;
  v67 = 0;
  v70 = 0;
  v69 = 0;
  v68 = 0;
  memset_0(v95, -1, sizeof(v95));
  memset_0(v94, -1, sizeof(v94));
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v84 = si128;
  v78 = (_QWORD *)((char *)v6 + 320);
  *(_QWORD *)&v81.Data1 = (char *)v6 + 320;
  v7 = *((_QWORD *)v6 + 40);
  v8 = *(void (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v7 + 56LL);
  WindowsDeleteString(0);
  v64 = 0;
  v75 = (_QWORD *)((char *)v6 + 312);
  v8(v7, *((_QWORD *)v6 + 39), &v64);
  v9 = *((_QWORD *)v6 + 40);
  v10 = *(void (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v9 + 40LL);
  WindowsDeleteString(0);
  string = 0;
  v10(v9, *((_QWORD *)v6 + 39), &string);
  (*(void (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)v6 + 40) + 72LL))(
    *((_QWORD *)v6 + 40),
    *((_QWORD *)v6 + 39),
    &v59);
  v58[0] = v59;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  *(_QWORD *)v60 = WindowsGetStringRawBuffer(v64, 0);
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanMgrCleanup::StorageSenseCleanMgrCleanup(
    (unsigned int)v91,
    v11,
    (unsigned int)v60,
    (unsigned int)&StringRawBuffer,
    (__int64)v58,
    (__int64)&v71,
    a2);
  v12 = 0;
  v13 = 0;
  memset_0(v93, 0, 0x454u);
  v92 = 1112;
  pclsid = 0;
  v14 = WindowsGetStringRawBuffer(string, 0);
  CLSIDFromString(v14, &pclsid);
  v15 = *(_QWORD *)&v82.Data1;
  if ( *(_QWORD *)&v82.Data1 && !*v61 )
  {
    v16 = *(_DWORD *)v75;
    v17 = v59;
    v18 = pclsid;
    v19 = WindowsGetStringRawBuffer(v64, 0);
    v82 = v18;
    v20 = SystemSettings::StorageSenseHandlers::PluginCleanupStart::PluginCleanupStart(
            (SystemSettings::StorageSenseHandlers::PluginCleanupStart *)v89,
            v19,
            &v82,
            v65,
            v17,
            v16);
    v21 = *(_QWORD *)(v15 + 8);
    if ( v21 == *(_QWORD *)(v15 + 16) )
    {
      try
      {
        std::vector<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInitializeStopData>::_Emplace_reallocate<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInitializeStopData>(
          v15,
          v21,
          v20);
      }
      catch ( std::bad_alloc )
      {
        *v61 = 1;
        v65 = v71;
        goto LABEL_5;
      }
      catch ( ... )
      {
        *v61 = 2;
        v65 = v71;
LABEL_5:
        v6 = v79;
        v74 = v63;
        v73 = v87;
        v72 = v79;
        v13 = 0;
        v12 = 0;
        v68 = 0;
        v69 = 0;
        v70 = 0;
      }
    }
    else
    {
      std::vector<SystemSettings::StorageSenseHandlers::PluginCleanupStart>::_Emplace_back_with_unused_capacity<SystemSettings::StorageSenseHandlers::PluginCleanupStart>(
        v15,
        v20);
    }
  }
  v22 = (unsigned int *)*((_QWORD *)v6 + 32);
  if ( v22 )
  {
    v12 = *v22;
    v13 = v22[1];
  }
  StorageDeviceInfo = GetStorageDeviceInfo(v12, v13, &v92);
  if ( StorageDeviceInfo >= 0 )
  {
    GetStorageDeviceSize(v93, 0, &v67, &v77);
    (*(void (__fastcall **)(_QWORD, __int64, _BYTE *))(*(_QWORD *)*v78 + 104LL))(*v78, 12, v95);
  }
  for ( i = StorageReserveIdHard; (unsigned int)i < 4; ++i )
  {
    v63 = 0;
    if ( (int)SystemSettings::StorageSenseHandlers::CStorageCleanupItem::GetReserveSize(v6, i, &v63) >= 0 )
      si128.m128i_i64[i] = v63;
  }
  TickCount64 = GetTickCount64();
  v26 = *(_QWORD **)&v81.Data1;
  v27 = v80;
  v60[0] = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(***(_QWORD ***)&v81.Data1 + 88LL))(
             **(_QWORD **)&v81.Data1,
             *v75,
             *v80);
  v28 = GetTickCount64() - TickCount64;
  if ( v28 < 0 )
    v29 = (double)(int)(v28 & 1 | ((unsigned __int64)v28 >> 1)) + (double)(int)(v28 & 1 | ((unsigned __int64)v28 >> 1));
  else
    v29 = (double)(int)v28;
  v30 = v29 / 1000.0;
  if ( StorageDeviceInfo >= 0 )
  {
    GetStorageDeviceSize(v93, 0, &v67, &v76);
    (*(void (__fastcall **)(_QWORD, __int64, _BYTE *))(*(_QWORD *)*v26 + 104LL))(*v26, 12, v94);
  }
  for ( j = StorageReserveIdHard; ; ++j )
  {
    while ( 1 )
    {
      v63 = 0;
      if ( (int)SystemSettings::StorageSenseHandlers::CStorageCleanupItem::GetReserveSize(v6, j, &v63) >= 0 )
        break;
LABEL_24:
      if ( (unsigned int)++j >= 4 )
        goto LABEL_30;
    }
    if ( j != StorageReserveIdHard )
      break;
    v70 = si128.m128i_i64[1] - v63;
LABEL_27:
    ;
  }
  if ( j == StorageReserveIdSoft )
  {
    v69 = v84.m128i_i64[0] - v63;
    goto LABEL_27;
  }
  if ( j != StorageReserveIdMax )
    goto LABEL_24;
  v68 = v84.m128i_i64[1] - v63;
LABEL_30:
  v78 = (_QWORD *)GetTickCount64();
  SystemSettings::StorageSenseHandlers::CStorageCleanupItem::RefreshSize(v6, 0);
  *(_QWORD *)&v81.Data1 = GetTickCount64();
  v32 = v76;
  v33 = v77;
  v34 = v67;
  v35 = *v27;
  v36 = WindowsGetStringRawBuffer(*((HSTRING *)v72 + 30), 0);
  v37 = (_BYTE)v59 != 0;
  v38 = WindowsGetStringRawBuffer(string, 0);
  v39 = WindowsGetStringRawBuffer(v64, 0);
  v89[0] = *(_OWORD *)v73;
  v89[1] = *(_OWORD *)(v73 + 16);
  v89[2] = *(_OWORD *)(v73 + 32);
  v89[3] = *(_OWORD *)(v73 + 48);
  v89[4] = *(_OWORD *)(v73 + 64);
  v89[5] = *(_OWORD *)(v73 + 80);
  v89[6] = *(_OWORD *)(v73 + 96);
  v89[7] = *(_OWORD *)(v73 + 112);
  v90 = *(_WORD *)(v73 + 128);
  v57 = v60[0];
  LOBYTE(v40) = v37;
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanMgrCleanup::Stop(
    v41,
    v39,
    v38,
    v40,
    v36,
    v65,
    v35,
    *(_QWORD *)&v30,
    v34,
    v33,
    v32,
    v95,
    v94);
  v42 = v74;
  if ( v74 )
  {
    v43 = *(_QWORD *)&v81.Data1 - (_QWORD)v78;
    v44 = (__int64)(*(_QWORD *)&v81.Data1 - (_QWORD)v78) < 0
        ? (double)(int)(v43 & 1 | (v43 >> 1)) + (double)(int)(v43 & 1 | (v43 >> 1))
        : (double)(int)v43;
    v45 = v44 / 1000.0;
    if ( !*v61 )
    {
      try
      {
        v46 = *(_DWORD *)v75;
        v47 = v59;
        v48 = v76;
        v49 = v77;
        v50 = v67;
        v51 = *v80;
        v52 = pclsid;
        v53 = WindowsGetStringRawBuffer(v64, 0);
        v81 = v52;
        v54 = SystemSettings::StorageSenseHandlers::PluginCleanupStop::PluginCleanupStop(
                (SystemSettings::StorageSenseHandlers::PluginCleanupStop *)v89,
                v53,
                &v81,
                v65,
                v51,
                v50,
                v49,
                v48,
                v70,
                v69,
                v68,
                v30,
                v45,
                v60[0],
                v47,
                v46,
                v57);
        v55 = *(_QWORD *)(v42 + 8);
        if ( v55 == *(_QWORD *)(v42 + 16) )
          std::vector<SystemSettings::StorageSenseHandlers::PluginCleanupStop>::_Emplace_reallocate<SystemSettings::StorageSenseHandlers::PluginCleanupStop>(
            v42,
            v55,
            v54);
        else
          std::vector<SystemSettings::StorageSenseHandlers::PluginCleanupStop>::_Emplace_back_with_unused_capacity<SystemSettings::StorageSenseHandlers::PluginCleanupStop>(
            v42,
            v54);
      }
      catch ( std::bad_alloc )
      {
        *v61 = 1;
      }
      catch ( ... )
      {
        *v61 = 2;
      }
    }
  }
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanMgrCleanup::~StorageSenseCleanMgrCleanup((SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanMgrCleanup *)v91);
  WindowsDeleteString(0);
  WindowsDeleteString(0);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v64);
  return v60[0];
}

```

## disassembly

```asm
0x1800884d0  mov     r11, rsp
0x1800884d3  push    rbx
0x1800884d4  push    rsi
0x1800884d5  push    rdi
0x1800884d6  push    r12
0x1800884d8  push    r13
0x1800884da  push    r14
0x1800884dc  push    r15
0x1800884de  sub     rsp, 990h
0x1800884e5  movaps  xmmword ptr [r11-48h], xmm6
0x1800884ea  movaps  xmmword ptr [r11-58h], xmm7
0x1800884ef  movaps  xmmword ptr [r11-68h], xmm8
0x1800884f4  mov     rax, cs:__security_cookie
0x1800884fb  xor     rax, rsp
0x1800884fe  mov     [rsp+9C8h+var_78], rax
0x180088506  mov     [rsp+9C8h+var_8C0], r9
0x18008850e  mov     qword ptr [rsp+9C8h+var_858.Data1], r8
0x180088516  mov     r13, rdx
0x180088519  mov     [rsp+9C8h+var_8C8], rdx
0x180088521  mov     r15, rcx
0x180088524  mov     [rsp+9C8h+var_8D0], rcx
0x18008852c  mov     [rsp+9C8h+var_890], rcx
0x180088534  mov     [rsp+9C8h+var_818], rdx
0x18008853c  mov     [rsp+9C8h+var_918], r9
0x180088544  mov     rax, [rsp+9C8h+arg_20]
0x18008854c  mov     [rsp+9C8h+var_928], rax
0x180088554  lea     rax, [rcx+110h]
0x18008855b  mov     [rsp+9C8h+var_880], rax
0x180088563  mov     rax, [rax]
0x180088566  mov     [r11-908h], rax
0x18008856d  mov     [r11-8D8h], rax
0x180088574  xor     esi, esi
0x180088576  mov     [r11-910h], rsi
0x18008857d  mov     [r11-920h], rsi
0x180088584  mov     [r11-828h], rsi
0x18008858b  mov     [r11-820h], rsi
0x180088592  mov     [rsp+9C8h+var_934], esi
0x180088599  mov     [r11-8A8h], rsi
0x1800885a0  mov     [r11-8B0h], rsi
0x1800885a7  mov     [r11-8F8h], rsi
0x1800885ae  mov     [rsp+9C8h+var_8E0], rsi
0x1800885b6  mov     [rsp+9C8h+var_8E8], rsi
0x1800885be  mov     [rsp+9C8h+var_8F0], rsi
0x1800885c6  lea     edi, [rsi+60h]
0x1800885c9  mov     r8d, edi; Size
0x1800885cc  or      ebx, 0FFFFFFFFh
0x1800885cf  mov     edx, ebx; Val
0x1800885d1  lea     rcx, [r11-0D8h]; void *
0x1800885d8  call    memset_0
0x1800885dd  mov     r8d, edi; Size
0x1800885e0  mov     edx, ebx; Val
0x1800885e2  lea     rcx, [rsp+9C8h+var_138]; void *
0x1800885ea  call    memset_0
0x1800885ef  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800885f7  movups  [rsp+9C8h+var_848], xmm0
0x1800885ff  movups  [rsp+9C8h+var_838], xmm0
0x180088607  lea     r12, [r15+140h]
0x18008860e  mov     [rsp+9C8h+var_8A0], r12
0x180088616  mov     qword ptr [rsp+9C8h+var_868.Data1], r12
0x18008861e  mov     rdi, [r12]
0x180088622  mov     rax, [rdi]
0x180088625  mov     rbx, [rax+38h]
0x180088629  xor     ecx, ecx; string
0x18008862b  call    cs:__imp_WindowsDeleteString
0x180088631  mov     [rsp+9C8h+var_910], rsi
0x180088639  lea     r14, [r15+138h]
0x180088640  mov     [rsp+9C8h+var_8B8], r14
0x180088648  lea     r8, [rsp+9C8h+var_910]
0x180088650  mov     rdx, [r14]
0x180088653  mov     rcx, rdi
0x180088656  mov     rax, rbx
0x180088659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008865e  mov     rdi, [r12]
0x180088662  mov     rax, [rdi]
0x180088665  mov     rbx, [rax+28h]
0x180088669  mov     rcx, [rsp+9C8h+string]; string
0x180088671  call    cs:__imp_WindowsDeleteString
0x180088677  mov     [rsp+9C8h+string], rsi
0x18008867f  lea     r8, [rsp+9C8h+string]
0x180088687  mov     rdx, [r14]
0x18008868a  mov     rcx, rdi
0x18008868d  mov     rax, rbx
0x180088690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088695  mov     rcx, [r12]
0x180088699  mov     rax, [rcx]
0x18008869c  lea     r8, [rsp+9C8h+var_934]
0x1800886a4  mov     rdx, [r14]
0x1800886a7  mov     rax, [rax+48h]
0x1800886ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800886b0  mov     al, byte ptr [rsp+9C8h+var_934]
0x1800886b7  mov     [rsp+9C8h+var_938], al
0x1800886be  xor     edx, edx; length
0x1800886c0  mov     rcx, [rsp+9C8h+string]; string
0x1800886c8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800886ce  mov     [rsp+9C8h+var_900], rax
0x1800886d6  xor     edx, edx; length
0x1800886d8  mov     rcx, [rsp+9C8h+var_910]; string
0x1800886e0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800886e6  mov     qword ptr [rsp+9C8h+var_930], rax
0x1800886ee  mov     [rsp+9C8h+var_998], r13
0x1800886f3  lea     rax, [rsp+9C8h+var_8D8]
0x1800886fb  mov     qword ptr [rsp+9C8h+var_9A0], rax
0x180088700  lea     rax, [rsp+9C8h+var_938]
0x180088708  mov     [rsp+9C8h+var_9A8], rax
0x18008870d  lea     r9, [rsp+9C8h+var_900]
0x180088715  lea     r8, [rsp+9C8h+var_930]
0x18008871d  lea     rcx, [rsp+9C8h+var_6E8]
0x180088725  call    ??$?0PEBGPEBGEAEA_KAEAUCORRELATION_VECTOR@@@StorageSenseCleanMgrCleanup@SSTelemetry@Internal@StorageSenseHandlers@SystemSettings@@AEAA@U?$integral_constant@D$0A@@wistd@@$$QEAPEBG1$$QEAEAEA_KAEAUCORRELATION_VECTOR@@@Z; SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanMgrCleanup::StorageSenseCleanMgrCleanup(wistd::integral_constant<char,0>,ushort const * &&,ushort const * &&,uchar &&,unsigned __int64 &,CORRELATION_VECTOR &)
0x18008872a  nop
0x18008872b  mov     r14d, esi
0x18008872e  mov     r12d, esi
0x180088731  xor     edx, edx; Val
0x180088733  mov     r8d, 454h; Size
0x180088739  lea     rcx, [rsp+9C8h+var_594]; void *
0x180088741  call    memset_0
0x180088746  mov     [rsp+9C8h+var_598], 458h
0x180088751  xorps   xmm0, xmm0
0x180088754  movups  xmmword ptr [rsp+9C8h+pclsid.Data1], xmm0
0x18008875c  xor     edx, edx; length
0x18008875e  mov     rcx, [rsp+9C8h+string]; string
0x180088766  call    cs:__imp_WindowsGetStringRawBuffer
0x18008876c  lea     rdx, [rsp+9C8h+pclsid]; pclsid
0x180088774  mov     rcx, rax; lpsz
0x180088777  call    cs:__imp_CLSIDFromString
0x18008877d  mov     r13, qword ptr [rsp+9C8h+var_858.Data1]
0x180088785  test    r13, r13
0x180088788  jz      loc_18008888F
0x18008878e  mov     rcx, [rsp+9C8h+var_928]
0x180088796  cmp     [rcx], rsi
0x180088799  jnz     loc_18008888F
0x18008879f  mov     rax, [rsp+9C8h+var_8B8]
0x1800887a7  mov     ebx, [rax]
0x1800887a9  mov     edi, [rsp+9C8h+var_934]
0x1800887b0  movups  xmm6, xmmword ptr [rsp+9C8h+pclsid.Data1]
0x1800887b8  xor     edx, edx; length
0x1800887ba  mov     rcx, [rsp+9C8h+var_910]; string
0x1800887c2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800887c8  movdqu  xmmword ptr [rsp+9C8h+var_858.Data1], xmm6
0x1800887d1  mov     [rsp+9C8h+var_9A0], ebx; unsigned int
0x1800887d5  mov     dword ptr [rsp+9C8h+var_9A8], edi; int
0x1800887d9  mov     r9, [rsp+9C8h+var_908]; unsigned __int64
0x1800887e1  lea     r8, [rsp+9C8h+var_858]; struct _GUID
0x1800887e9  mov     rdx, rax; unsigned __int16 *
0x1800887ec  lea     rcx, [rsp+9C8h+var_7F8]; this
0x1800887f4  call    ??0PluginCleanupStart@StorageSenseHandlers@SystemSettings@@QEAA@PEBGU_GUID@@_KHI@Z; SystemSettings::StorageSenseHandlers::PluginCleanupStart::PluginCleanupStart(ushort const *,_GUID,unsigned __int64,int,uint)
0x1800887f9  mov     rdx, [r13+8]
0x1800887fd  mov     rcx, r13
0x180088800  cmp     rdx, [r13+10h]
0x180088804  jz      short loc_180088810
0x180088806  mov     rdx, rax
0x180088809  call    ??$_Emplace_back_with_unused_capacity@UPluginCleanupStart@StorageSenseHandlers@SystemSettings@@@?$vector@UPluginCleanupStart@StorageSenseHandlers@SystemSettings@@V?$allocator@UPluginCleanupStart@StorageSenseHandlers@SystemSettings@@@std@@@std@@AEAAAEAUPluginCleanupStart@StorageSenseHandlers@SystemSettings@@$$QEAU234@@Z; std::vector<SystemSettings::StorageSenseHandlers::PluginCleanupStart>::_Emplace_back_with_unused_capacity<SystemSettings::StorageSenseHandlers::PluginCleanupStart>(SystemSettings::StorageSenseHandlers::PluginCleanupStart &&)
0x18008880e  jmp     short loc_180088819
0x180088810  mov     r8, rax
0x180088813  call    ??$_Emplace_reallocate@UPluginInitializeStopData@CleanmgrHelper@StorageSenseHandlers@SystemSettings@@@?$vector@UPluginInitializeStopData@CleanmgrHelper@StorageSenseHandlers@SystemSettings@@V?$allocator@UPluginInitializeStopData@CleanmgrHelper@StorageSenseHandlers@SystemSettings@@@std@@@std@@AEAAPEAUPluginInitializeStopData@CleanmgrHelper@StorageSenseHandlers@SystemSettings@@QEAU2345@$$QEAU2345@@Z; std::vector<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInitializeStopData>::_Emplace_reallocate<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInitializeStopData>(SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInitializeStopData * const,SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInitializeStopData &&)
0x180088818  nop
0x180088819  jmp     short loc_18008888F
0x18008881b  mov     rdx, [rsp+9C8h+var_8D8]
0x180088823  mov     [rsp+9C8h+var_908], rdx
0x18008882b  jmp     short loc_18008883D
0x18008882d  mov     rax, [rsp+9C8h+var_8D8]
0x180088835  mov     [rsp+9C8h+var_908], rax
0x18008883d  xor     esi, esi
0x18008883f  mov     rax, [rsp+9C8h+var_918]
0x180088847  mov     r13, [rsp+9C8h+var_818]
0x18008884f  mov     r15, [rsp+9C8h+var_890]
0x180088857  mov     ecx, esi
0x180088859  mov     [rsp+9C8h+var_8C0], rax
0x180088861  mov     [rsp+9C8h+var_8C8], r13
0x180088869  mov     [rsp+9C8h+var_8D0], r15
0x180088871  mov     r12d, esi
0x180088874  mov     r14d, esi
0x180088877  mov     [rsp+9C8h+var_8F0], rcx
0x18008887f  mov     [rsp+9C8h+var_8E8], rcx
0x180088887  mov     [rsp+9C8h+var_8E0], rcx
0x18008888f  mov     rax, [r15+100h]
0x180088896  test    rax, rax
0x180088899  jz      short loc_1800888A2
0x18008889b  mov     r14d, [rax]
0x18008889e  mov     r12d, [rax+4]
0x1800888a2  lea     r8, [rsp+9C8h+var_598]
0x1800888aa  mov     edx, r12d
0x1800888ad  mov     ecx, r14d
0x1800888b0  call    cs:__imp_GetStorageDeviceInfo
0x1800888b6  mov     r14d, eax
0x1800888b9  test    eax, eax
0x1800888bb  js      short loc_180088904
0x1800888bd  lea     r9, [rsp+9C8h+var_8A8]
0x1800888c5  lea     r8, [rsp+9C8h+var_8F8]
0x1800888cd  xor     edx, edx
0x1800888cf  lea     rcx, [rsp+9C8h+var_594]
0x1800888d7  call    cs:__imp_GetStorageDeviceSize
0x1800888dd  mov     rcx, [rsp+9C8h+var_8A0]
0x1800888e5  mov     r9, [rcx]
0x1800888e8  mov     rcx, [r9]
0x1800888eb  mov     rax, [rcx+68h]
0x1800888ef  lea     r8, [rsp+9C8h+var_D8]
0x1800888f7  mov     edx, 0Ch
0x1800888fc  mov     rcx, r9
0x1800888ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088904  mov     ebx, 1
0x180088909  mov     [rsp+9C8h+var_918], rsi
0x180088911  lea     r8, [rsp+9C8h+var_918]; unsigned __int64 *
0x180088919  mov     edx, ebx; enum _STORAGE_RESERVE_ID
0x18008891b  mov     rcx, r15; this
0x18008891e  call    ?GetReserveSize@CStorageCleanupItem@StorageSenseHandlers@SystemSettings@@QEAAJW4_STORAGE_RESERVE_ID@@PEA_K@Z; SystemSettings::StorageSenseHandlers::CStorageCleanupItem::GetReserveSize(_STORAGE_RESERVE_ID,unsigned __int64 *)
0x180088923  test    eax, eax
0x180088925  js      short loc_180088939
0x180088927  mov     ecx, ebx
0x180088929  mov     rax, [rsp+9C8h+var_918]
0x180088931  mov     qword ptr [rsp+rcx*8+9C8h+var_848], rax
0x180088939  inc     ebx
0x18008893b  cmp     ebx, 4
0x18008893e  jb      short loc_180088909
0x180088940  call    cs:__imp_GetTickCount64
0x180088946  mov     rbx, rax
0x180088949  mov     rdi, qword ptr [rsp+9C8h+var_868.Data1]
0x180088951  mov     r9, [rdi]
0x180088954  mov     rcx, [r9]
0x180088957  mov     rax, [rcx+58h]
0x18008895b  mov     r13, [rsp+9C8h+var_880]
0x180088963  mov     r8, [r13+0]
0x180088967  mov     rdx, [rsp+9C8h+var_8B8]
0x18008896f  mov     rdx, [rdx]
0x180088972  mov     rcx, r9
0x180088975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008897a  mov     [rsp+9C8h+var_930], eax
0x180088981  call    cs:__imp_GetTickCount64
0x180088987  mov     rcx, rax
0x18008898a  sub     rcx, rbx
0x18008898d  xorps   xmm8, xmm8
0x180088991  js      short loc_18008899A
0x180088993  cvtsi2sd xmm8, rcx
0x180088998  jmp     short loc_1800889B0
0x18008899a  mov     rax, rcx
0x18008899d  shr     rax, 1
0x1800889a0  and     ecx, 1
0x1800889a3  or      rax, rcx
0x1800889a6  cvtsi2sd xmm8, rax
0x1800889ab  addsd   xmm8, xmm8
0x1800889b0  movsd   xmm6, cs:__real@408f400000000000
0x1800889b8  divsd   xmm8, xmm6
0x1800889bd  test    r14d, r14d
0x1800889c0  js      short loc_1800889FE
0x1800889c2  lea     r9, [rsp+9C8h+var_8B0]
0x1800889ca  lea     r8, [rsp+9C8h+var_8F8]
0x1800889d2  xor     edx, edx
0x1800889d4  lea     rcx, [rsp+9C8h+var_594]
0x1800889dc  call    cs:__imp_GetStorageDeviceSize
0x1800889e2  mov     rcx, [rdi]
0x1800889e5  mov     rax, [rcx]
0x1800889e8  lea     r8, [rsp+9C8h+var_138]
0x1800889f0  mov     edx, 0Ch
0x1800889f5  mov     rax, [rax+68h]
0x1800889f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800889fe  mov     ebx, 1
0x180088a03  mov     [rsp+9C8h+var_918], rsi
0x180088a0b  lea     r8, [rsp+9C8h+var_918]; unsigned __int64 *
0x180088a13  mov     edx, ebx; enum _STORAGE_RESERVE_ID
0x180088a15  mov     rcx, r15; this
0x180088a18  call    ?GetReserveSize@CStorageCleanupItem@StorageSenseHandlers@SystemSettings@@QEAAJW4_STORAGE_RESERVE_ID@@PEA_K@Z; SystemSettings::StorageSenseHandlers::CStorageCleanupItem::GetReserveSize(_STORAGE_RESERVE_ID,unsigned __int64 *)
0x180088a1d  test    eax, eax
0x180088a1f  js      short loc_180088A3C
0x180088a21  mov     rcx, [rsp+9C8h+var_918]
0x180088a29  mov     edx, ebx
0x180088a2b  mov     eax, ebx
0x180088a2d  sub     eax, 1
0x180088a30  jz      short loc_180088A5C
0x180088a32  sub     eax, 1
0x180088a35  jz      short loc_180088A45
0x180088a37  cmp     eax, 1
0x180088a3a  jz      short loc_180088A71
0x180088a3c  inc     ebx
0x180088a3e  cmp     ebx, 4
0x180088a41  jb      short loc_180088A03
0x180088a43  jmp     short loc_180088A84
0x180088a45  mov     r12, qword ptr [rsp+rdx*8+9C8h+var_848]
0x180088a4d  sub     r12, rcx
0x180088a50  mov     [rsp+9C8h+var_8E8], r12
0x180088a58  inc     ebx
0x180088a5a  jmp     short loc_180088A03
0x180088a5c  mov     r12, qword ptr [rsp+rdx*8+9C8h+var_848]
0x180088a64  sub     r12, rcx
0x180088a67  mov     [rsp+9C8h+var_8E0], r12
0x180088a6f  jmp     short loc_180088A58
0x180088a71  mov     rax, qword ptr [rsp+rdx*8+9C8h+var_848]
0x180088a79  sub     rax, rcx
0x180088a7c  mov     [rsp+9C8h+var_8F0], rax
0x180088a84  call    cs:__imp_GetTickCount64
0x180088a8a  mov     [rsp+9C8h+var_8A0], rax
0x180088a92  mov     [rsp+9C8h+var_9A8], rsi; __int64
0x180088a97  xor     r9d, r9d
0x180088a9a  xor     r8d, r8d
0x180088a9d  lea     edx, [r9+1]
0x180088aa1  mov     rcx, r15; this
0x180088aa4  call    ?RefreshSize@CStorageCleanupItem@StorageSenseHandlers@SystemSettings@@QEAAJW4CleanupItemSizeRefreshOperationKind@23@PEAV?$vector@UPluginScanStart@StorageSenseHandlers@SystemSettings@@V?$allocator@UPluginScanStart@StorageSenseHandlers@SystemSettings@@@std@@@std@@PEAV?$vector@UPluginScanStop@StorageSenseHandlers@SystemSettings@@V?$allocator@UPluginScanStop@StorageSenseHandlers@SystemSettings@@@std@@@6@PEA_K@Z; SystemSettings::StorageSenseHandlers::CStorageCleanupItem::RefreshSize(SystemSettings::StorageSenseHandlers::CleanupItemSizeRefreshOperationKind,std::vector<SystemSettings::StorageSenseHandlers::PluginScanStart> *,std::vector<SystemSettings::StorageSenseHandlers::PluginScanStop> *,unsigned __int64 *)
0x180088aa9  call    cs:__imp_GetTickCount64
0x180088aaf  mov     qword ptr [rsp+9C8h+var_868.Data1], rax
0x180088ab7  mov     r14, [rsp+9C8h+var_8B0]
0x180088abf  mov     r15, [rsp+9C8h+var_8A8]
0x180088ac7  mov     r12, [rsp+9C8h+var_8F8]
  ... truncated ...
```
