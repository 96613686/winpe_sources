# MosStorageValidateLocation(_GUID,_STORAGE_DEVICE_VALIDATION_RESULT *)

- ea: `0x180009cc0`
- end: `0x18000a273`
- name: `?MosStorageValidateLocation@@YAJU_GUID@@PEAU_STORAGE_DEVICE_VALIDATION_RESULT@@@Z`
- size: `1459`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, struct _STORAGE_DEVICE_VALIDATION_RESULT *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config`

## callees

- `0x180001c80`
- `0x180002802`
- `0x1800078d4`
- `0x180007c90`
- `0x18000824c`
- `0x180008dc0`
- `0x1800090a0`
- `0x180009220`
- `0x180009510`
- `0x180009cc0`
- `0x18000a684`
- `0x18000a750`
- `0x18000a87c`
- `0x18000a9c0`
- `0x18000bd8c`
- `0x18000d8b8`
- `0x18000e7e0`
- `0x18000e7ec`
- `0x180010010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtof_l` at `0x180009fa9`
- `api-ms-win-crt-private-l1-1-0!_o__wtof_l` at `0x18000a049`
- `api-ms-win-crt-private-l1-1-0!_o__wtof_l` at `0x180009fa9`
- `api-ms-win-crt-private-l1-1-0!_o__wtof_l` at `0x18000a049`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009d6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a209`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009d6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a209`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009d97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a23a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009d97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a23a`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180009ed9`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180009f56`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180009ff6`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180009ed9`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180009f56`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180009ff6`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180009d56`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000a07f`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180009d56`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000a07f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009f9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a03d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009f9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a03d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009ee6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009f23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009f63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009fc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a003`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a08c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a17a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009ee6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009f23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009f63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009fc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a003`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a08c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a17a`

## pseudocode

```c
__int64 __fastcall MosStorageValidateLocation(struct _GUID *a1, struct _STORAGE_DEVICE_VALIDATION_RESULT *a2)
{
  int StorageDeviceDataFromDeviceGuid; // eax
  int v5; // r8d
  signed int v6; // ebx
  bool v7; // bl
  _DWORD *v8; // rax
  OfflineMapsTelemetry *v9; // rax
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // rbx
  struct ILocaleMapConfiguration *v12; // r12
  int v13; // r15d
  int LocaleMapConfiguration; // eax
  struct ILocaleMapConfiguration *v15; // rcx
  struct ILocaleMapConfiguration *v16; // rdi
  __int64 (__fastcall *v17)(struct ILocaleMapConfiguration *, __int64, _QWORD *); // rbx
  int v18; // eax
  struct ILocaleMapConfiguration *v19; // rcx
  __int64 v20; // rbx
  PCWSTR StringRawBuffer; // rax
  double v22; // xmm7_8
  struct ILocaleMapConfiguration *v23; // rdi
  __int64 (__fastcall *v24)(struct ILocaleMapConfiguration *, __int64, _QWORD *); // rbx
  int v25; // eax
  struct ILocaleMapConfiguration *v26; // rcx
  __int64 v27; // rbx
  PCWSTR v28; // rax
  double v29; // xmm0_8
  int AverageSpeed; // eax
  struct ILocaleMapConfiguration *v31; // rcx
  bool v32; // di
  _DWORD *v33; // rax
  OfflineMapsTelemetry *v34; // rax
  bool v35; // bl
  _DWORD *v36; // rax
  OfflineMapsTelemetry *v37; // rax
  struct ILocaleMapConfiguration *v38; // rcx
  bool v39; // di
  _DWORD *v40; // rax
  OfflineMapsTelemetry *v41; // rax
  struct ILocaleMapConfiguration *v43; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD string[3]; // [rsp+50h] [rbp-B8h] BYREF
  double v45; // [rsp+68h] [rbp-A0h] BYREF
  double v46; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v47[1084]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE Buf1[564]; // [rsp+4B4h] [rbp+3ACh] BYREF
  _BYTE Src[4]; // [rsp+6E8h] [rbp+5E0h] BYREF
  int v50; // [rsp+6ECh] [rbp+5E4h]
  unsigned int v51; // [rsp+8FCh] [rbp+7F4h]
  _BYTE Buf2[548]; // [rsp+B24h] [rbp+A1Ch] BYREF
  unsigned int v53; // [rsp+D48h] [rbp+C40h]

  v45 = 0.0;
  v46 = 0.0;
  v43 = 0;
  memset_0(Src, 0, 0x670u);
  MosStorageResetMigrationStateCacheValues();
  *(struct _GUID *)&string[1] = *a1;
  StorageDeviceDataFromDeviceGuid = GetStorageDeviceDataFromDeviceGuid(&string[1], Src);
  if ( StorageDeviceDataFromDeviceGuid >= 0 )
  {
    EnterCriticalSection(&CriticalSection);
    LODWORD(xmmword_1800184B0) = 1;
    memcpy_0(qword_1800184D8, Src, sizeof(qword_1800184D8));
    LeaveCriticalSection(&CriticalSection);
    v7 = v50 != 0;
    v8 = (_DWORD *)*((_QWORD *)OfflineMapsTelemetry::Instance() + 1);
    if ( v8 && *v8 )
    {
      v9 = OfflineMapsTelemetry::Instance();
      OfflineMapsTelemetry::StorageMigrationValidationStartMosHost_(v9, v7, v51, v53);
    }
    StorageDeviceDataFromDeviceGuid = MosStorageGetMapDataMaxBrowseCacheSizeInBytes((unsigned __int64 *)&v43);
    if ( StorageDeviceDataFromDeviceGuid >= 0 )
    {
      StorageDeviceDataFromDeviceGuid = MosStorageGetTotalMapDataInBytes((unsigned __int64 *)&v46);
      if ( StorageDeviceDataFromDeviceGuid >= 0 )
      {
        StorageDeviceDataFromDeviceGuid = MosStorageGetStorageSizesInBytes(
                                            (const struct _STORAGE_DEVICE_DATA *)Src,
                                            &string[1],
                                            (unsigned __int64 *)&v45);
        if ( StorageDeviceDataFromDeviceGuid >= 0 )
        {
          v10 = *(_QWORD *)&v46 + 10000000LL;
          v11 = *(_QWORD *)&v45;
          v12 = v43;
          if ( *(_QWORD *)&v45 < (unsigned __int64)v43 || v10 > *(_QWORD *)&v45 )
          {
            v13 = 2;
            v39 = v50 != 0;
            v40 = (_DWORD *)*((_QWORD *)OfflineMapsTelemetry::Instance() + 1);
            if ( v40 && *v40 )
            {
              v41 = OfflineMapsTelemetry::Instance();
              OfflineMapsTelemetry::StorageMigrationNoSpaceMosHost_(v41, v39, v51, v53);
            }
            if ( v10 <= v11 )
              v10 = (unsigned __int64)v12;
            v10 -= v11;
          }
          else
          {
            memset_0(v47, 0, 0x670u);
            StorageDeviceDataFromDeviceGuid = GetDefaultStorageLocation(v47);
            if ( StorageDeviceDataFromDeviceGuid < 0 )
            {
              v5 = 748;
              goto LABEL_3;
            }
            v13 = 0;
            if ( memcmp_0(Buf1, Buf2, 0x10u) )
            {
              v46 = 0.0;
              v45 = 0.0;
              v43 = 0;
              string[1] = 0;
              LocaleMapConfiguration = MapPlatformConfig::GetLocaleMapConfiguration(&v43);
              if ( LocaleMapConfiguration < 0 )
              {
                v6 = ZTraceReportOriginationNoThis(LocaleMapConfiguration, "MosStorageValidateLocation", 761);
                WindowsDeleteString((HSTRING)string[1]);
                string[1] = 0;
                v15 = v43;
                if ( v43 )
                {
                  v43 = 0;
                  (*(void (__fastcall **)(struct ILocaleMapConfiguration *))(*(_QWORD *)v15 + 16LL))(v15);
                }
                goto LABEL_33;
              }
              v16 = v43;
              v17 = *(__int64 (__fastcall **)(struct ILocaleMapConfiguration *, __int64, _QWORD *))(*(_QWORD *)v43 + 48LL);
              WindowsDeleteString((HSTRING)string[1]);
              string[1] = 0;
              v18 = v17(v16, 306, &string[1]);
              if ( v18 < 0 )
              {
                v6 = ZTraceReportOriginationNoThis(v18, "MosStorageValidateLocation", 765);
                WindowsDeleteString((HSTRING)string[1]);
                string[1] = 0;
                v19 = v43;
                if ( v43 )
                {
                  v43 = 0;
                  (*(void (__fastcall **)(struct ILocaleMapConfiguration *))(*(_QWORD *)v19 + 16LL))(v19);
                }
                goto LABEL_33;
              }
              v20 = qword_180018E10;
              StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)string[1], 0);
              v22 = _o__wtof_l(StringRawBuffer, v20);
              v23 = v43;
              v24 = *(__int64 (__fastcall **)(struct ILocaleMapConfiguration *, __int64, _QWORD *))(*(_QWORD *)v43 + 48LL);
              WindowsDeleteString((HSTRING)string[1]);
              string[1] = 0;
              v25 = v24(v23, 307, &string[1]);
              if ( v25 < 0 )
              {
                v6 = ZTraceReportOriginationNoThis(v25, "MosStorageValidateLocation", 773);
                WindowsDeleteString((HSTRING)string[1]);
                string[1] = 0;
                v26 = v43;
                if ( v43 )
                {
                  v43 = 0;
                  (*(void (__fastcall **)(struct ILocaleMapConfiguration *))(*(_QWORD *)v26 + 16LL))(v26);
                }
                goto LABEL_33;
              }
              v27 = qword_180018E10;
              v28 = WindowsGetStringRawBuffer((HSTRING)string[1], 0);
              v29 = _o__wtof_l(v28, v27);
              AverageSpeed = StoragePerfGetAverageSpeed((const struct _STORAGE_DEVICE_DATA *)Src, &v46, &v45);
              if ( AverageSpeed < 0 )
              {
                v6 = ZTraceReportPropagationNoThis(AverageSpeed, "MosStorageValidateLocation", 779);
                WindowsDeleteString((HSTRING)string[1]);
                string[1] = 0;
                v31 = v43;
                if ( v43 )
                {
                  v43 = 0;
                  (*(void (__fastcall **)(struct ILocaleMapConfiguration *))(*(_QWORD *)v31 + 16LL))(v31);
                }
                goto LABEL_33;
              }
              if ( v22 > v46 || v29 > v45 )
                v13 = 1;
              v35 = v50 != 0;
              v36 = (_DWORD *)*((_QWORD *)OfflineMapsTelemetry::Instance() + 1);
              if ( v36 && *v36 )
              {
                v37 = OfflineMapsTelemetry::Instance();
                OfflineMapsTelemetry::StorageMigrationPerfResultMosHost_(
                  v37,
                  (unsigned __int8)v13 != 1,
                  v46,
                  v45,
                  v35,
                  v51,
                  v53);
              }
              WindowsDeleteString((HSTRING)string[1]);
              string[1] = 0;
              v38 = v43;
              if ( v43 )
              {
                v43 = 0;
                (*(void (__fastcall **)(struct ILocaleMapConfiguration *))(*(_QWORD *)v38 + 16LL))(v38);
              }
            }
          }
          v6 = 0;
          *((_QWORD *)a2 + 1) = v10;
          *(_DWORD *)a2 = v13;
          *((_QWORD *)a2 + 2) = v12;
          goto LABEL_53;
        }
        v5 = 722;
      }
      else
      {
        v5 = 721;
      }
    }
    else
    {
      v5 = 720;
    }
  }
  else
  {
    v5 = 706;
  }
LABEL_3:
  v6 = ZTraceReportPropagationNoThis(StorageDeviceDataFromDeviceGuid, "MosStorageValidateLocation", v5);
LABEL_33:
  if ( v6 < 0 )
  {
    v32 = v50 != 0;
    v33 = (_DWORD *)*((_QWORD *)OfflineMapsTelemetry::Instance() + 1);
    if ( v33 )
    {
      if ( *v33 )
      {
        v34 = OfflineMapsTelemetry::Instance();
        OfflineMapsTelemetry::StorageMigrationPerfResultFailedMosHost_(v34, v32, v51, v53, v6);
      }
    }
  }
LABEL_53:
  EnterCriticalSection(&CriticalSection);
  LODWORD(xmmword_1800184B0) = 2;
  DWORD2(xmmword_1800184B0) = v6;
  DWORD1(xmmword_1800184B0) = *(_DWORD *)a2;
  qword_1800184C0 = *((_QWORD *)a2 + 2);
  LeaveCriticalSection(&CriticalSection);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009cc0  mov     rax, rsp
0x180009cc3  push    rbp
0x180009cc4  push    rbx
0x180009cc5  push    rsi
0x180009cc6  push    rdi
0x180009cc7  push    r12
0x180009cc9  push    r13
0x180009ccb  push    r14
0x180009ccd  push    r15
0x180009ccf  lea     rbp, [rax-0CC8h]
0x180009cd6  sub     rsp, 0D88h
0x180009cdd  movaps  xmmword ptr [rax-58h], xmm6
0x180009ce1  movaps  xmmword ptr [rax-68h], xmm7
0x180009ce5  mov     rax, cs:__security_cookie
0x180009cec  xor     rax, rsp
0x180009cef  mov     [rbp+0CC0h+var_70], rax
0x180009cf6  mov     r14, rdx
0x180009cf9  mov     rbx, rcx
0x180009cfc  xor     r13d, r13d
0x180009cff  mov     [rsp+0DC0h+var_D60], r13
0x180009d04  mov     [rsp+0DC0h+var_D58], r13
0x180009d09  mov     [rsp+0DC0h+var_D80], r13
0x180009d0e  mov     edi, 670h
0x180009d13  mov     r8d, edi; Size
0x180009d16  xor     edx, edx; Val
0x180009d18  lea     rcx, [rbp+0CC0h+Src]; void *
0x180009d1f  call    memset_0
0x180009d24  call    ?MosStorageResetMigrationStateCacheValues@@YAXXZ; MosStorageResetMigrationStateCacheValues(void)
0x180009d29  movups  xmm0, xmmword ptr [rbx]
0x180009d2c  movdqu  xmmword ptr [rsp+0DC0h+string+8], xmm0
0x180009d32  lea     rdx, [rbp+0CC0h+Src]
0x180009d39  lea     rcx, [rsp+0DC0h+string+8]
0x180009d3e  call    GetStorageDeviceDataFromDeviceGuid
0x180009d43  test    eax, eax
0x180009d45  jns     short loc_180009D63
0x180009d47  mov     r8d, 2C2h
0x180009d4d  lea     rdx, aMosstoragevali_0; "MosStorageValidateLocation"
0x180009d54  mov     ecx, eax
0x180009d56  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180009d5c  mov     ebx, eax
0x180009d5e  jmp     loc_18000A0B3
0x180009d63  lea     rcx, CriticalSection; lpCriticalSection
0x180009d6a  call    cs:__imp_EnterCriticalSection
0x180009d70  mov     dword ptr cs:xmmword_1800184B0, 1
0x180009d7a  lea     rcx, qword_1800184D8; void *
0x180009d81  lea     rdx, [rbp+0CC0h+Src]; Src
0x180009d88  mov     r8, rdi; Size
0x180009d8b  call    memcpy_0
0x180009d90  lea     rcx, CriticalSection; lpCriticalSection
0x180009d97  call    cs:__imp_LeaveCriticalSection
0x180009d9d  cmp     [rbp+0CC0h+var_6DC], r13d
0x180009da4  setnz   bl
0x180009da7  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180009dac  mov     rax, [rax+8]
0x180009db0  test    rax, rax
0x180009db3  jz      short loc_180009DD8
0x180009db5  mov     eax, [rax]
0x180009db7  test    eax, eax
0x180009db9  jz      short loc_180009DD8
0x180009dbb  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180009dc0  mov     r9d, [rbp+0CC0h+var_80]; unsigned int
0x180009dc7  mov     r8d, [rbp+0CC0h+var_4CC]; unsigned int
0x180009dce  mov     dl, bl; bool
0x180009dd0  mov     rcx, rax; this
0x180009dd3  call    ?StorageMigrationValidationStartMosHost_@OfflineMapsTelemetry@@QEAAX_NII@Z; OfflineMapsTelemetry::StorageMigrationValidationStartMosHost_(bool,uint,uint)
0x180009dd8  lea     rcx, [rsp+0DC0h+var_D80]; unsigned __int64 *
0x180009ddd  call    ?MosStorageGetMapDataMaxBrowseCacheSizeInBytes@@YAJPEA_K@Z; MosStorageGetMapDataMaxBrowseCacheSizeInBytes(unsigned __int64 *)
0x180009de2  test    eax, eax
0x180009de4  jns     short loc_180009DF1
0x180009de6  mov     r8d, 2D0h
0x180009dec  jmp     loc_180009D4D
0x180009df1  lea     rcx, [rsp+0DC0h+var_D58]; unsigned __int64 *
0x180009df6  call    ?MosStorageGetTotalMapDataInBytes@@YAJPEA_K@Z; MosStorageGetTotalMapDataInBytes(unsigned __int64 *)
0x180009dfb  test    eax, eax
0x180009dfd  jns     short loc_180009E0A
0x180009dff  mov     r8d, 2D1h
0x180009e05  jmp     loc_180009D4D
0x180009e0a  lea     r8, [rsp+0DC0h+var_D60]; unsigned __int64 *
0x180009e0f  lea     rdx, [rsp+0DC0h+string+8]; unsigned __int64 *
0x180009e14  lea     rcx, [rbp+0CC0h+Src]; struct _STORAGE_DEVICE_DATA *
0x180009e1b  call    ?MosStorageGetStorageSizesInBytes@@YAJAEBU_STORAGE_DEVICE_DATA@@PEA_K1@Z; MosStorageGetStorageSizesInBytes(_STORAGE_DEVICE_DATA const &,unsigned __int64 *,unsigned __int64 *)
0x180009e20  test    eax, eax
0x180009e22  jns     short loc_180009E2F
0x180009e24  mov     r8d, 2D2h
0x180009e2a  jmp     loc_180009D4D
0x180009e2f  mov     rsi, [rsp+0DC0h+var_D58]
0x180009e34  add     rsi, 989680h
0x180009e3b  mov     rbx, [rsp+0DC0h+var_D60]
0x180009e40  mov     r12, [rsp+0DC0h+var_D80]
0x180009e45  cmp     rbx, r12
0x180009e48  jb      loc_18000A1A3
0x180009e4e  cmp     rsi, rbx
0x180009e51  ja      loc_18000A1A3
0x180009e57  mov     r8, rdi; Size
0x180009e5a  xor     edx, edx; Val
0x180009e5c  lea     rcx, [rsp+0DC0h+var_D50]; void *
0x180009e61  call    memset_0
0x180009e66  lea     rcx, [rsp+0DC0h+var_D50]; void *
0x180009e6b  call    GetDefaultStorageLocation
0x180009e70  test    eax, eax
0x180009e72  jns     short loc_180009E7F
0x180009e74  mov     r8d, 2ECh
0x180009e7a  jmp     loc_180009D4D
0x180009e7f  mov     r15d, r13d
0x180009e82  mov     r8d, 10h; Size
0x180009e88  lea     rdx, [rbp+0CC0h+Buf2]; Buf2
0x180009e8f  lea     rcx, [rbp+0CC0h+Buf1]; Buf1
0x180009e96  call    memcmp_0
0x180009e9b  test    eax, eax
0x180009e9d  jz      loc_18000A1F1
0x180009ea3  xorps   xmm0, xmm0
0x180009ea6  movsd   [rsp+0DC0h+var_D58], xmm0
0x180009eac  movsd   [rsp+0DC0h+var_D60], xmm0
0x180009eb2  mov     [rsp+0DC0h+var_D80], r13
0x180009eb7  mov     qword ptr [rsp+0DC0h+string+8], r13
0x180009ebc  lea     rcx, [rsp+0DC0h+var_D80]; struct ILocaleMapConfiguration **
0x180009ec1  call    ?GetLocaleMapConfiguration@MapPlatformConfig@@SAJPEAPEAUILocaleMapConfiguration@@@Z; MapPlatformConfig::GetLocaleMapConfiguration(ILocaleMapConfiguration * *)
0x180009ec6  test    eax, eax
0x180009ec8  jns     short loc_180009F12
0x180009eca  mov     r8d, 2F9h
0x180009ed0  lea     rdx, aMosstoragevali_0; "MosStorageValidateLocation"
0x180009ed7  mov     ecx, eax
0x180009ed9  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180009edf  mov     ebx, eax
0x180009ee1  mov     rcx, qword ptr [rsp+0DC0h+string+8]; string
0x180009ee6  call    cs:__imp_WindowsDeleteString
0x180009eec  mov     qword ptr [rsp+0DC0h+string+8], r13
0x180009ef1  mov     rcx, [rsp+0DC0h+var_D80]
0x180009ef6  test    rcx, rcx
0x180009ef9  jz      short loc_180009F0D
0x180009efb  mov     [rsp+0DC0h+var_D80], r13
0x180009f00  mov     rax, [rcx]
0x180009f03  mov     rax, [rax+10h]
0x180009f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f0c  nop
0x180009f0d  jmp     loc_18000A0B3
0x180009f12  mov     rdi, [rsp+0DC0h+var_D80]
0x180009f17  mov     rax, [rdi]
0x180009f1a  mov     rbx, [rax+30h]
0x180009f1e  mov     rcx, qword ptr [rsp+0DC0h+string+8]; string
0x180009f23  call    cs:__imp_WindowsDeleteString
0x180009f29  mov     qword ptr [rsp+0DC0h+string+8], r13
0x180009f2e  lea     r8, [rsp+0DC0h+string+8]
0x180009f33  mov     edx, 132h
0x180009f38  mov     rcx, rdi
0x180009f3b  mov     rax, rbx
0x180009f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f43  test    eax, eax
0x180009f45  jns     short loc_180009F8F
0x180009f47  mov     r8d, 2FDh
0x180009f4d  lea     rdx, aMosstoragevali_0; "MosStorageValidateLocation"
0x180009f54  mov     ecx, eax
0x180009f56  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180009f5c  mov     ebx, eax
0x180009f5e  mov     rcx, qword ptr [rsp+0DC0h+string+8]; string
0x180009f63  call    cs:__imp_WindowsDeleteString
0x180009f69  mov     qword ptr [rsp+0DC0h+string+8], r13
0x180009f6e  mov     rcx, [rsp+0DC0h+var_D80]
0x180009f73  test    rcx, rcx
0x180009f76  jz      short loc_180009F8A
0x180009f78  mov     [rsp+0DC0h+var_D80], r13
0x180009f7d  mov     rax, [rcx]
0x180009f80  mov     rax, [rax+10h]
0x180009f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f89  nop
0x180009f8a  jmp     loc_18000A0B3
0x180009f8f  mov     rbx, cs:qword_180018E10
0x180009f96  xor     edx, edx; length
0x180009f98  mov     rcx, qword ptr [rsp+0DC0h+string+8]; string
0x180009f9d  call    cs:__imp_WindowsGetStringRawBuffer
0x180009fa3  mov     rdx, rbx
0x180009fa6  mov     rcx, rax
0x180009fa9  call    cs:__imp__o__wtof_l
0x180009faf  movaps  xmm7, xmm0
0x180009fb2  mov     rdi, [rsp+0DC0h+var_D80]
0x180009fb7  mov     rax, [rdi]
0x180009fba  mov     rbx, [rax+30h]
0x180009fbe  mov     rcx, qword ptr [rsp+0DC0h+string+8]; string
0x180009fc3  call    cs:__imp_WindowsDeleteString
0x180009fc9  mov     qword ptr [rsp+0DC0h+string+8], r13
0x180009fce  lea     r8, [rsp+0DC0h+string+8]
0x180009fd3  mov     edx, 133h
0x180009fd8  mov     rcx, rdi
0x180009fdb  mov     rax, rbx
0x180009fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fe3  test    eax, eax
0x180009fe5  jns     short loc_18000A02F
0x180009fe7  mov     r8d, 305h
0x180009fed  lea     rdx, aMosstoragevali_0; "MosStorageValidateLocation"
0x180009ff4  mov     ecx, eax
0x180009ff6  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180009ffc  mov     ebx, eax
0x180009ffe  mov     rcx, qword ptr [rsp+0DC0h+string+8]; string
0x18000a003  call    cs:__imp_WindowsDeleteString
0x18000a009  mov     qword ptr [rsp+0DC0h+string+8], r13
0x18000a00e  mov     rcx, [rsp+0DC0h+var_D80]
0x18000a013  test    rcx, rcx
0x18000a016  jz      short loc_18000A02A
0x18000a018  mov     [rsp+0DC0h+var_D80], r13
0x18000a01d  mov     rax, [rcx]
0x18000a020  mov     rax, [rax+10h]
0x18000a024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a029  nop
0x18000a02a  jmp     loc_18000A0B3
0x18000a02f  mov     rbx, cs:qword_180018E10
0x18000a036  xor     edx, edx; length
0x18000a038  mov     rcx, qword ptr [rsp+0DC0h+string+8]; string
0x18000a03d  call    cs:__imp_WindowsGetStringRawBuffer
0x18000a043  mov     rdx, rbx
0x18000a046  mov     rcx, rax
0x18000a049  call    cs:__imp__o__wtof_l
0x18000a04f  movaps  xmm6, xmm0
0x18000a052  lea     r8, [rsp+0DC0h+var_D60]; double *
0x18000a057  lea     rdx, [rsp+0DC0h+var_D58]; double *
0x18000a05c  lea     rcx, [rbp+0CC0h+Src]; struct _STORAGE_DEVICE_DATA *
0x18000a063  call    ?StoragePerfGetAverageSpeed@@YAJAEBU_STORAGE_DEVICE_DATA@@PEAN1@Z; StoragePerfGetAverageSpeed(_STORAGE_DEVICE_DATA const &,double *,double *)
0x18000a068  test    eax, eax
0x18000a06a  jns     loc_18000A109
0x18000a070  mov     r8d, 30Bh
0x18000a076  lea     rdx, aMosstoragevali_0; "MosStorageValidateLocation"
0x18000a07d  mov     ecx, eax
0x18000a07f  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000a085  mov     ebx, eax
0x18000a087  mov     rcx, qword ptr [rsp+0DC0h+string+8]; string
0x18000a08c  call    cs:__imp_WindowsDeleteString
0x18000a092  mov     qword ptr [rsp+0DC0h+string+8], r13
0x18000a097  mov     rcx, [rsp+0DC0h+var_D80]
0x18000a09c  test    rcx, rcx
0x18000a09f  jz      short loc_18000A0B3
0x18000a0a1  mov     [rsp+0DC0h+var_D80], r13
0x18000a0a6  mov     rax, [rcx]
0x18000a0a9  mov     rax, [rax+10h]
0x18000a0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0b2  nop
0x18000a0b3  test    ebx, ebx
0x18000a0b5  jns     loc_18000A202
0x18000a0bb  cmp     [rbp+0CC0h+var_6DC], r13d
0x18000a0c2  setnz   dil
0x18000a0c6  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18000a0cb  mov     rax, [rax+8]
0x18000a0cf  test    rax, rax
0x18000a0d2  jz      loc_18000A202
0x18000a0d8  mov     eax, [rax]
0x18000a0da  test    eax, eax
0x18000a0dc  jz      loc_18000A202
0x18000a0e2  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18000a0e7  mov     dword ptr [rsp+0DC0h+var_DA0], ebx; unsigned int
0x18000a0eb  mov     r9d, [rbp+0CC0h+var_80]; int
0x18000a0f2  mov     r8d, [rbp+0CC0h+var_4CC]; unsigned int
0x18000a0f9  mov     dl, dil; bool
0x18000a0fc  mov     rcx, rax; this
0x18000a0ff  call    ?StorageMigrationPerfResultFailedMosHost_@OfflineMapsTelemetry@@QEAAX_NIJI@Z; OfflineMapsTelemetry::StorageMigrationPerfResultFailedMosHost_(bool,uint,long,uint)
0x18000a104  jmp     loc_18000A202
0x18000a109  comisd  xmm7, [rsp+0DC0h+var_D58]
0x18000a10f  ja      short loc_18000A119
0x18000a111  comisd  xmm6, [rsp+0DC0h+var_D60]
0x18000a117  jbe     short loc_18000A11F
0x18000a119  mov     r15d, 1
0x18000a11f  cmp     [rbp+0CC0h+var_6DC], r13d
0x18000a126  setnz   bl
0x18000a129  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18000a12e  mov     rax, [rax+8]
0x18000a132  test    rax, rax
0x18000a135  jz      short loc_18000A175
0x18000a137  mov     eax, [rax]
0x18000a139  test    eax, eax
0x18000a13b  jz      short loc_18000A175
0x18000a13d  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18000a142  mov     dl, r15b
0x18000a145  xor     dl, 1; bool
0x18000a148  mov     ecx, [rbp+0CC0h+var_80]
0x18000a14e  mov     [rsp+0DC0h+var_D90], ecx; unsigned int
0x18000a152  mov     ecx, [rbp+0CC0h+var_4CC]
0x18000a158  mov     [rsp+0DC0h+var_D98], ecx; unsigned int
0x18000a15c  mov     [rsp+0DC0h+var_DA0], bl; bool
0x18000a160  movsd   xmm3, [rsp+0DC0h+var_D60]; double
0x18000a166  movsd   xmm2, [rsp+0DC0h+var_D58]; double
0x18000a16c  mov     rcx, rax; this
0x18000a16f  call    ?StorageMigrationPerfResultMosHost_@OfflineMapsTelemetry@@QEAAX_NNN0II@Z; OfflineMapsTelemetry::StorageMigrationPerfResultMosHost_(bool,double,double,bool,uint,uint)
0x18000a174  nop
0x18000a175  mov     rcx, qword ptr [rsp+0DC0h+string+8]; string
0x18000a17a  call    cs:__imp_WindowsDeleteString
0x18000a180  mov     qword ptr [rsp+0DC0h+string+8], r13
0x18000a185  mov     rcx, [rsp+0DC0h+var_D80]
0x18000a18a  test    rcx, rcx
0x18000a18d  jz      short loc_18000A1A1
0x18000a18f  mov     [rsp+0DC0h+var_D80], r13
0x18000a194  mov     rax, [rcx]
0x18000a197  mov     rax, [rax+10h]
0x18000a19b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1a0  nop
0x18000a1a1  jmp     short loc_18000A1F1
0x18000a1a3  mov     r15d, 2
0x18000a1a9  cmp     [rbp+0CC0h+var_6DC], r13d
0x18000a1b0  setnz   dil
0x18000a1b4  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18000a1b9  mov     rax, [rax+8]
0x18000a1bd  test    rax, rax
0x18000a1c0  jz      short loc_18000A1E6
0x18000a1c2  mov     eax, [rax]
  ... truncated ...
```
