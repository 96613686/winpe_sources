# StorageService::ScanVolume(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_SCAN_VOLUME_PARAMS *)

- ea: `0x18002901c`
- end: `0x18002948b`
- name: `?ScanVolume@StorageService@@QEAAJW4_STORAGE_DEVICE_TYPE@@KPEAU_STORAGE_SCAN_VOLUME_PARAMS@@@Z`
- size: `1135`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, service_task, installer_update`

## callers

- `0x180037950`

## callees

- `0x180001148`
- `0x180001b78`
- `0x180001c80`
- `0x18000d030`
- `0x18000d450`
- `0x18000ddb0`
- `0x18001a70c`
- `0x18001fe50`
- `0x18001feb8`
- `0x1800200e8`
- `0x180025efc`
- `0x180027080`
- `0x18002901c`
- `0x1800294ec`
- `0x18002bd7c`
- `0x180072b8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800290b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800290b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029306`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029306`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029208`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800291fb`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800291fb`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800291c1`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800291c1`
- `api-ms-win-core-realtime-l1-1-1!QueryInterruptTime` at `0x1800290a3`
- `api-ms-win-core-realtime-l1-1-1!QueryInterruptTime` at `0x180029311`
- `api-ms-win-core-realtime-l1-1-1!QueryInterruptTime` at `0x1800290a3`
- `api-ms-win-core-realtime-l1-1-1!QueryInterruptTime` at `0x180029311`

## pseudocode

```c
__int64 __fastcall StorageService::ScanVolume(__int64 a1, int a2, unsigned int a3, __int64 a4)
{
  __int64 v4; // rsi
  __int64 v5; // rdi
  char v7; // r12
  unsigned __int8 v8; // r12
  bool v9; // r14
  __int64 v10; // rcx
  int updated; // ebx
  __int64 v12; // r15
  int v13; // ebx
  int v14; // r14d
  __int64 v15; // rcx
  __int64 v16; // r9
  signed int LastError; // eax
  __int64 v18; // rax
  unsigned __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // r9
  bool v26; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[3]; // [rsp+61h] [rbp-9Fh] BYREF
  int v28; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v29; // [rsp+68h] [rbp-98h] BYREF
  int v30; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned __int64 v31; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 InterruptTime; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v33; // [rsp+80h] [rbp-80h] BYREF
  WCHAR *v34; // [rsp+88h] [rbp-78h] BYREF
  __int64 v35; // [rsp+90h] [rbp-70h] BYREF
  WCHAR szVolumeName[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR FileSystemNameBuffer[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v4 = a3;
  v5 = a2;
  memset_0(FileSystemNameBuffer, 0, 0x208u);
  v7 = ~*(_BYTE *)(a4 + 4);
  v29 = 0;
  v8 = v7 & 1;
  memset_0(szVolumeName, 0, 0x208u);
  v26 = 0;
  v9 = 0;
  InterruptTime = 0;
  v31 = 0;
  QueryInterruptTime(&InterruptTime);
  EnterCriticalSection(&stru_1800C10D0);
  updated = StorageService::CheckDeviceParameters(v10, (unsigned int)v5, v4, 1);
  if ( updated >= 0 )
  {
    if ( *(_DWORD *)a4 < 0x10u )
    {
      updated = -2147024809;
      goto LABEL_33;
    }
    if ( (unsigned int)StorageService::IsVolumeStatusSet(&g_StorageService, (unsigned int)v5, (unsigned int)v4, 8)
      || (unsigned int)StorageService::IsVolumeStatusSet(&g_StorageService, (unsigned int)v5, (unsigned int)v4, 16) )
    {
      updated = -2147024891;
    }
    else
    {
      v12 = 1112 * v4;
      v13 = 0;
      if ( !*(_WORD *)(*((_QWORD *)&g_StorageService + v5 + 5) + 1112 * v4 + 4) )
      {
        updated = -2147418113;
        goto LABEL_33;
      }
      v14 = 2;
      if ( (unsigned int)StorageService::CheckPresenceState(&g_StorageService, (unsigned int)v5, (unsigned int)v4, 2) )
      {
        v28 = 0;
        StorageService::SetDismountReason(v15, (unsigned int)v5, (unsigned int)v4);
      }
      else
      {
        updated = StorageService::UpdateDismountState(&g_StorageService, (unsigned int)v5, (unsigned int)v4, 4);
        if ( updated < 0 )
        {
LABEL_30:
          StorageService::ProcessVolumeChange((StorageService *)&g_StorageService);
          v9 = v26;
          goto LABEL_33;
        }
        v28 = 1;
        v13 = 0;
      }
      if ( GetVolumeInformationW((LPCWSTR)((char *)*(&P + 1) + v12 + 4), 0, 0, 0, 0, 0, FileSystemNameBuffer, 0x104u) )
      {
        if ( !v8 )
          v13 = *(_DWORD *)(a4 + 8);
        if ( GetVolumeNameForVolumeMountPointW((LPCWSTR)((char *)*(&P + 1) + v12 + 4), szVolumeName, 0x104u) )
        {
          v18 = -1;
          do
            ++v18;
          while ( szVolumeName[v18] );
          v19 = 2 * v18 - 2;
          if ( v19 >= 0x208 )
            _report_rangecheckfailure();
          *(WCHAR *)((char *)szVolumeName + v19) = 0;
          LOBYTE(v16) = v8;
          updated = ScanPartitionPath(((v8 ^ 1u) << 20) + 2621696, szVolumeName, FileSystemNameBuffer, v16, v13, &v29);
          if ( v29 < 6 )
            v14 = *((_DWORD *)qword_180095078 + v29);
          *(_DWORD *)(a4 + 12) = v14;
          if ( v8 )
          {
            v26 = updated >= 0 && v14 != 0;
            StorageService::ClearVolumeStatus(&g_StorageService, (unsigned int)v5, (unsigned int)v4, 1);
          }
        }
        else
        {
          LastError = GetLastError();
          updated = LastError;
          if ( LastError > 0 )
            updated = (unsigned __int16)LastError | 0x80070000;
        }
      }
      else
      {
        updated = GetLastHr();
      }
      if ( v28 )
        goto LABEL_30;
      v9 = v26;
    }
  }
LABEL_33:
  LeaveCriticalSection(&stru_1800C10D0);
  QueryInterruptTime(&v31);
  if ( (int)StorageService::CheckDeviceParameters(v20, (unsigned int)v5, v4, 1) < 0 )
  {
    if ( (unsigned int)dword_1800BF000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
    {
      v30 = v4;
      v28 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BF000,
        (__int64)&dword_1800A5FAC,
        0,
        v24,
        (__int64)&v28,
        (__int64)&v30);
    }
  }
  else if ( (unsigned int)dword_1800BF000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
  {
    v23 = *((_QWORD *)&g_StorageService + v5 + 5);
    v33 = v31 - InterruptTime;
    v34 = FileSystemNameBuffer;
    v28 = updated;
    v26 = v9;
    v27[0] = v8;
    v29 = *(_DWORD *)(v23 + 1112 * v4 + 1096);
    v30 = v5;
    v35 = v23 + 1112 * v4 + 548;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
      v21,
      (__int64)byte_1800A5D4B,
      1112 * v4,
      v22,
      &v35,
      (__int64)&v30,
      (__int64)&v29,
      (const WCHAR **)&v34,
      (__int64)&v33,
      (__int64)v27,
      (__int64)&v26,
      (__int64)&v28);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18002901c  mov     [rsp-8+arg_0], rbx
0x180029021  push    rbp
0x180029022  push    rsi
0x180029023  push    rdi
0x180029024  push    r12
0x180029026  push    r13
0x180029028  push    r14
0x18002902a  push    r15
0x18002902c  lea     rbp, [rsp-3D0h]
0x180029034  sub     rsp, 4D0h
0x18002903b  mov     rax, cs:__security_cookie
0x180029042  xor     rax, rsp
0x180029045  mov     [rbp+400h+var_40], rax
0x18002904c  mov     esi, r8d
0x18002904f  lea     rcx, [rbp+400h+FileSystemNameBuffer]; void *
0x180029056  movsxd  rdi, edx
0x180029059  mov     ebx, 208h
0x18002905e  mov     r8d, ebx; Size
0x180029061  xor     edx, edx; Val
0x180029063  mov     r13, r9
0x180029066  call    memset_0
0x18002906b  mov     r12b, [r13+4]
0x18002906f  lea     rcx, [rbp+400h+szVolumeName]; void *
0x180029073  not     r12b
0x180029076  xor     r15d, r15d
0x180029079  mov     r8d, ebx; Size
0x18002907c  mov     [rsp+500h+var_498], r15d
0x180029081  xor     edx, edx; Val
0x180029083  and     r12b, 1
0x180029087  call    memset_0
0x18002908c  lea     rcx, [rsp+500h+InterruptTime]; lpInterruptTime
0x180029091  mov     [rsp+500h+var_4A0], r15b
0x180029096  mov     r14b, r15b
0x180029099  mov     [rsp+500h+InterruptTime], r15
0x18002909e  mov     [rsp+500h+var_490], r15
0x1800290a3  call    cs:__imp_QueryInterruptTime
0x1800290a9  lea     rcx, stru_1800C10D0; lpCriticalSection
0x1800290b0  call    cs:__imp_EnterCriticalSection
0x1800290b6  lea     r9d, [r15+1]
0x1800290ba  mov     r8d, esi
0x1800290bd  mov     edx, edi
0x1800290bf  call    ?CheckDeviceParameters@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::CheckDeviceParameters(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x1800290c4  mov     ebx, eax
0x1800290c6  test    eax, eax
0x1800290c8  js      loc_1800292F8
0x1800290ce  cmp     dword ptr [r13+0], 10h
0x1800290d3  jnb     short loc_1800290DF
0x1800290d5  mov     ebx, 80070057h
0x1800290da  jmp     loc_1800292F8
0x1800290df  mov     r9d, 8
0x1800290e5  lea     rcx, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x1800290ec  mov     r8d, esi
0x1800290ef  mov     edx, edi
0x1800290f1  call    ?IsVolumeStatusSet@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::IsVolumeStatusSet(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x1800290f6  test    eax, eax
0x1800290f8  jnz     loc_1800292EC
0x1800290fe  lea     r9d, [rax+10h]
0x180029102  mov     r8d, esi
0x180029105  mov     edx, edi
0x180029107  lea     rcx, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x18002910e  call    ?IsVolumeStatusSet@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::IsVolumeStatusSet(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180029113  test    eax, eax
0x180029115  jnz     loc_1800292EC
0x18002911b  imul    r15, rsi, 458h
0x180029122  lea     rcx, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x180029129  xor     ebx, ebx
0x18002912b  mov     rax, [rcx+rdi*8+28h]
0x180029130  cmp     [rax+r15+4], bx
0x180029136  jnz     short loc_180029142
0x180029138  mov     ebx, 8000FFFFh
0x18002913d  jmp     loc_1800292F8
0x180029142  mov     r14d, 2
0x180029148  mov     r8d, esi
0x18002914b  mov     r9d, r14d
0x18002914e  mov     edx, edi
0x180029150  call    ?CheckPresenceState@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_PRESENCE_STATE@@@Z; StorageService::CheckPresenceState(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_PRESENCE_STATE)
0x180029155  mov     r8d, esi
0x180029158  mov     edx, edi
0x18002915a  test    eax, eax
0x18002915c  jnz     short loc_180029184
0x18002915e  lea     r9d, [r14+2]
0x180029162  lea     rcx, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x180029169  call    ?UpdateDismountState@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_DISMOUNT_REASON@@@Z; StorageService::UpdateDismountState(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_DISMOUNT_REASON)
0x18002916e  mov     ebx, eax
0x180029170  test    eax, eax
0x180029172  js      loc_1800292D6
0x180029178  mov     [rsp+500h+var_49C], 1
0x180029180  xor     ebx, ebx
0x180029182  jmp     short loc_18002918D
0x180029184  mov     [rsp+500h+var_49C], ebx
0x180029188  call    ?SetDismountReason@StorageService@@IEAAXW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_DISMOUNT_REASON@@@Z; StorageService::SetDismountReason(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_DISMOUNT_REASON)
0x18002918d  mov     rcx, qword ptr cs:P+8
0x180029194  lea     rax, [rbp+400h+FileSystemNameBuffer]
0x18002919b  mov     [rsp+500h+nFileSystemNameSize], 104h; nFileSystemNameSize
0x1800291a3  add     rcx, 4
0x1800291a7  mov     [rsp+500h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x1800291ac  add     rcx, r15; lpRootPathName
0x1800291af  mov     [rsp+500h+lpFileSystemFlags], rbx; lpFileSystemFlags
0x1800291b4  xor     r9d, r9d; lpVolumeSerialNumber
0x1800291b7  xor     r8d, r8d; nVolumeNameSize
0x1800291ba  mov     [rsp+500h+lpMaximumComponentLength], rbx; lpMaximumComponentLength
0x1800291bf  xor     edx, edx; lpVolumeNameBuffer
0x1800291c1  call    cs:__imp_GetVolumeInformationW
0x1800291c7  test    eax, eax
0x1800291c9  jnz     short loc_1800291DA
0x1800291cb  call    ?GetLastHr@@YAJXZ; GetLastHr(void)
0x1800291d0  mov     ebx, eax
0x1800291d2  xor     r15d, r15d
0x1800291d5  jmp     loc_1800292CF
0x1800291da  test    r12b, r12b
0x1800291dd  jnz     short loc_1800291E3
0x1800291df  mov     ebx, [r13+8]
0x1800291e3  mov     rcx, qword ptr cs:P+8
0x1800291ea  lea     rdx, [rbp+400h+szVolumeName]; lpszVolumeName
0x1800291ee  add     rcx, 4
0x1800291f2  mov     r8d, 104h; cchBufferLength
0x1800291f8  add     rcx, r15; lpszVolumeMountPoint
0x1800291fb  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180029201  xor     r15d, r15d
0x180029204  test    eax, eax
0x180029206  jnz     short loc_180029226
0x180029208  call    cs:__imp_GetLastError
0x18002920e  mov     ebx, eax
0x180029210  test    eax, eax
0x180029212  jle     loc_1800292CF
0x180029218  movzx   ebx, ax
0x18002921b  or      ebx, 80070000h
0x180029221  jmp     loc_1800292CF
0x180029226  lea     rcx, [rbp+400h+szVolumeName]
0x18002922a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002922e  inc     rax
0x180029231  cmp     [rcx+rax*2], r15w
0x180029236  jnz     short loc_18002922E
0x180029238  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180029240  cmp     rcx, 208h
0x180029247  jnb     loc_180029485
0x18002924d  mov     [rbp+rcx+400h+szVolumeName], r15w
0x180029253  lea     rax, [rsp+500h+var_498]
0x180029258  movzx   ecx, r12b
0x18002925c  lea     r8, [rbp+400h+FileSystemNameBuffer]
0x180029263  xor     ecx, 1
0x180029266  mov     [rsp+500h+lpFileSystemFlags], rax
0x18002926b  shl     ecx, 14h
0x18002926e  lea     rdx, [rbp+400h+szVolumeName]
0x180029272  add     ecx, 280100h
0x180029278  mov     dword ptr [rsp+500h+lpMaximumComponentLength], ebx
0x18002927c  mov     r9b, r12b
0x18002927f  call    ScanPartitionPath
0x180029284  cmp     [rsp+500h+var_498], 6
0x180029289  mov     ebx, eax
0x18002928b  jnb     short loc_18002929C
0x18002928d  mov     eax, [rsp+500h+var_498]
0x180029291  lea     r14, qword_180095078
0x180029298  mov     r14d, [r14+rax*4]
0x18002929c  mov     [r13+0Ch], r14d
0x1800292a0  test    r12b, r12b
0x1800292a3  jz      short loc_1800292CF
0x1800292a5  test    ebx, ebx
0x1800292a7  js      short loc_1800292B3
0x1800292a9  test    r14d, r14d
0x1800292ac  setnz   [rsp+500h+var_4A0]
0x1800292b1  jmp     short loc_1800292B8
0x1800292b3  mov     [rsp+500h+var_4A0], r15b
0x1800292b8  mov     r9d, 1
0x1800292be  lea     rcx, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x1800292c5  mov     r8d, esi
0x1800292c8  mov     edx, edi
0x1800292ca  call    ?ClearVolumeStatus@StorageService@@IEAAXW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::ClearVolumeStatus(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x1800292cf  cmp     [rsp+500h+var_49C], r15d
0x1800292d4  jz      short loc_1800292F3
0x1800292d6  lea     r13, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x1800292dd  mov     rcx, r13; this
0x1800292e0  call    ?ProcessVolumeChange@StorageService@@QEAAJXZ; StorageService::ProcessVolumeChange(void)
0x1800292e5  mov     r14b, [rsp+500h+var_4A0]
0x1800292ea  jmp     short loc_1800292FF
0x1800292ec  mov     ebx, 80070005h
0x1800292f1  jmp     short loc_1800292F8
0x1800292f3  mov     r14b, [rsp+500h+var_4A0]
0x1800292f8  lea     r13, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x1800292ff  lea     rcx, stru_1800C10D0; lpCriticalSection
0x180029306  call    cs:__imp_LeaveCriticalSection
0x18002930c  lea     rcx, [rsp+500h+var_490]; lpInterruptTime
0x180029311  call    cs:__imp_QueryInterruptTime
0x180029317  mov     r9d, 1
0x18002931d  mov     r8d, esi
0x180029320  mov     edx, edi
0x180029322  call    ?CheckDeviceParameters@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::CheckDeviceParameters(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180029327  test    eax, eax
0x180029329  mov     eax, cs:dword_1800BF000
0x18002932f  js      loc_180029408
0x180029335  cmp     eax, 5
0x180029338  jbe     loc_180029459
0x18002933e  mov     rdx, 400000000000h
0x180029348  lea     rcx, dword_1800BF000
0x18002934f  call    _tlgKeywordOn
0x180029354  test    al, al
0x180029356  jz      loc_180029459
0x18002935c  mov     rdx, [r13+rdi*8+28h]
0x180029361  mov     rax, [rsp+500h+var_490]
0x180029366  sub     rax, [rsp+500h+InterruptTime]
0x18002936b  mov     [rbp+400h+var_480], rax
0x18002936f  lea     rax, [rbp+400h+FileSystemNameBuffer]
0x180029376  mov     [rbp+400h+var_478], rax
0x18002937a  imul    r8, rsi, 458h
0x180029381  mov     [rsp+500h+var_49C], ebx
0x180029385  mov     [rsp+500h+var_4A0], r14b
0x18002938a  mov     [rsp+500h+var_49F], r12b
0x18002938f  mov     eax, [rdx+r8+448h]
0x180029397  mov     [rsp+500h+var_498], eax
0x18002939b  lea     rax, [r8+224h]
0x1800293a2  add     rax, rdx
0x1800293a5  mov     [rsp+500h+var_494], edi
0x1800293a9  mov     [rbp+400h+var_470], rax
0x1800293ad  lea     rdx, byte_1800A5D4B
0x1800293b4  lea     rax, [rsp+500h+var_49C]
0x1800293b9  mov     [rsp+500h+var_4A8], rax
0x1800293be  lea     rax, [rsp+500h+var_4A0]
0x1800293c3  mov     [rsp+500h+var_4B0], rax
0x1800293c8  lea     rax, [rsp+500h+var_49F]
0x1800293cd  mov     [rsp+500h+var_4B8], rax
0x1800293d2  lea     rax, [rbp+400h+var_480]
0x1800293d6  mov     [rsp+500h+var_4C0], rax
0x1800293db  lea     rax, [rbp+400h+var_478]
0x1800293df  mov     qword ptr [rsp+500h+nFileSystemNameSize], rax
0x1800293e4  lea     rax, [rsp+500h+var_498]
0x1800293e9  mov     [rsp+500h+lpFileSystemNameBuffer], rax
0x1800293ee  lea     rax, [rsp+500h+var_494]
0x1800293f3  mov     [rsp+500h+lpFileSystemFlags], rax
0x1800293f8  lea     rax, [rbp+400h+var_470]
0x1800293fc  mov     [rsp+500h+lpMaximumComponentLength], rax
0x180029401  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$00@@U5@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$00@@74@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x180029406  jmp     short loc_180029459
0x180029408  cmp     eax, 5
0x18002940b  jbe     short loc_180029459
0x18002940d  mov     rdx, 400000000000h
0x180029417  lea     rcx, dword_1800BF000
0x18002941e  call    _tlgKeywordOn
0x180029423  test    al, al
0x180029425  jz      short loc_180029459
0x180029427  lea     rax, [rsp+500h+var_494]
0x18002942c  mov     [rsp+500h+var_494], esi
0x180029430  mov     [rsp+500h+lpFileSystemFlags], rax
0x180029435  lea     rdx, dword_1800A5FAC
0x18002943c  lea     rax, [rsp+500h+var_49C]
0x180029441  mov     [rsp+500h+var_49C], edi
0x180029445  xor     r8d, r8d
0x180029448  mov     [rsp+500h+lpMaximumComponentLength], rax
0x18002944d  lea     rcx, dword_1800BF000
0x180029454  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180029459  mov     eax, ebx
0x18002945b  mov     rcx, [rbp+400h+var_40]
0x180029462  xor     rcx, rsp; StackCookie
0x180029465  call    __security_check_cookie
0x18002946a  mov     rbx, [rsp+500h+arg_0]
0x180029472  add     rsp, 4D0h
0x180029479  pop     r15
0x18002947b  pop     r14
0x18002947d  pop     r13
0x18002947f  pop     r12
0x180029481  pop     rdi
0x180029482  pop     rsi
0x180029483  pop     rbp
0x180029484  retn
0x180029485  call    __report_rangecheckfailure
```
