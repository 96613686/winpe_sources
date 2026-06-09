# UbpmMaintenanceGetUrgencyLevel

- ea: `0x180016b50`
- end: `0x180016e63`
- name: `UbpmMaintenanceGetUrgencyLevel`
- size: `787`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180015e20`

## callees

- `0x180015c7c`
- `0x180016b50`
- `0x1800182a0`
- `0x180018970`
- `0x1800189e8`
- `0x180036d44`
- `0x180040260`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180016d29`
- `ntdll!RtlReleaseSRWLockShared` at `0x180016d29`
- `ntdll!RtlAcquireSRWLockShared` at `0x180016d0b`
- `ntdll!RtlAcquireSRWLockShared` at `0x180016d0b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180016d4a`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180016d4a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180016c9a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180016cc5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180016cf0`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180016c9a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180016cc5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180016cf0`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016d68`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016d68`

## pseudocode

```c
FILETIME __fastcall UbpmMaintenanceGetUrgencyLevel(__int64 a1, _BYTE *a2, FILETIME *a3)
{
  __int64 v6; // r14
  unsigned __int16 *v7; // r8
  __int64 v8; // r15
  __int64 v9; // r12
  FILETIME v10; // rax
  __int64 v11; // rcx
  char IsCritical; // al
  FILETIME result; // rax
  __int64 v14; // [rsp+30h] [rbp-99h]
  char v15[8]; // [rsp+50h] [rbp-79h] BYREF
  FILETIME v16; // [rsp+58h] [rbp-71h] BYREF
  FILETIME FileTime; // [rsp+60h] [rbp-69h] BYREF
  struct _FILETIME v18; // [rsp+68h] [rbp-61h] BYREF
  FILETIME v19; // [rsp+70h] [rbp-59h] BYREF
  FILETIME v20; // [rsp+78h] [rbp-51h] BYREF
  FILETIME v21; // [rsp+80h] [rbp-49h] BYREF
  FILETIME v22; // [rsp+88h] [rbp-41h] BYREF
  FILETIME v23; // [rsp+90h] [rbp-39h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+98h] [rbp-31h] BYREF
  _BYTE v25[36]; // [rsp+A8h] [rbp-21h] BYREF
  __int128 Source2; // [rsp+D0h] [rbp+7h] BYREF

  v15[0] = 0;
  v20 = 0;
  v18 = 0;
  memset(v25, 0, sizeof(v25));
  FileTime = 0;
  v19 = 0;
  Source2 = 0;
  v16 = 0;
  v6 = *(_QWORD *)DateTime::NowUTC(&SystemTime);
  v7 = *(unsigned __int16 **)(*(_QWORD *)(a1 + 24) + 48LL);
  v8 = 10000000 * (v7[6] + 60 * (v7[5] + 60 * (v7[4] + 24 * (v7[3] + 365LL * *v7 + 7LL * v7[2] + 30LL * v7[1]))));
  v9 = 10000000 * (v7[13] + 60 * (v7[12] + 60 * (v7[11] + 24 * (365LL * v7[7] + v7[10] + 7LL * v7[9] + 30LL * v7[8]))));
  if ( (unsigned int)UbpmStatsOperation(a1, 0, v25) )
  {
    v10 = 0;
    *(_DWORD *)v25 = 3;
    memset(&v25[4], 0, 32);
  }
  else
  {
    v10 = *(FILETIME *)&v25[4];
  }
  FileTime = v10;
  SystemTime = 0;
  if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
    FileTime = 0;
  v19 = *(FILETIME *)&v25[12];
  SystemTime = 0;
  if ( !FileTimeToSystemTime(&v19, &SystemTime) )
    v19 = 0;
  v16 = *(FILETIME *)&v25[28];
  SystemTime = 0;
  if ( !FileTimeToSystemTime(&v16, &SystemTime) )
    v16 = 0;
  RtlAcquireSRWLockShared(&g_SystemSetup);
  Source2 = xmmword_18004FB52;
  RtlReleaseSRWLockShared(&g_SystemSetup);
  SystemTime = 0;
  if ( RtlCompareMemory(&SystemTime, &Source2, 0x10u) == 16 )
  {
    v18 = 0;
  }
  else if ( !SystemTimeToFileTime((const SYSTEMTIME *)&Source2, &v18) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v11);
    v18 = 0;
  }
  IsCritical = UbpmpMaintenanceTaskIsCritical(a1);
  v21 = v16;
  v22 = FileTime;
  v23 = v18;
  *(_QWORD *)&SystemTime.wYear = v6;
  UbpmpMaintenanceGetLevelForTime(v8, v9, (const FILETIME *)&SystemTime, &v23, &v22, &v21, v14, IsCritical, v15, &v20);
  *a2 = v15[0];
  result = v20;
  *a3 = v20;
  return result;
}

```

## disassembly

```asm
0x180016b50  push    rbp
0x180016b52  push    rbx
0x180016b53  push    rsi
0x180016b54  push    rdi
0x180016b55  push    r12
0x180016b57  push    r14
0x180016b59  push    r15
0x180016b5b  lea     rbp, [rsp-27h]
0x180016b60  sub     rsp, 0F0h
0x180016b67  mov     rax, cs:__security_cookie
0x180016b6e  xor     rax, rsp
0x180016b71  mov     [rbp+57h+var_40], rax
0x180016b75  xor     eax, eax
0x180016b77  mov     [rbp+57h+var_D0], 0
0x180016b7b  xorps   xmm0, xmm0
0x180016b7e  mov     [rbp+57h+var_A8], rax
0x180016b82  mov     rbx, rcx
0x180016b85  mov     dword ptr [rbp+57h+var_68+10h], eax
0x180016b88  lea     rcx, [rbp+57h+SystemTime]
0x180016b8c  mov     qword ptr [rbp+57h+var_B8.dwLowDateTime], rax
0x180016b90  movups  [rbp+57h+var_78], xmm0
0x180016b94  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rax
0x180016b98  mov     rsi, r8
0x180016b9b  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x180016b9f  mov     qword ptr [rbp+57h+var_B0.dwLowDateTime], rax
0x180016ba3  mov     rdi, rdx
0x180016ba6  movups  [rbp+57h+Source2], xmm0
0x180016baa  mov     qword ptr [rbp+57h+var_C8.dwLowDateTime], rax
0x180016bae  call    ?NowUTC@DateTime@@SA?AV1@XZ; DateTime::NowUTC(void)
0x180016bb3  mov     r14, [rax]
0x180016bb6  mov     rax, [rbx+18h]
0x180016bba  mov     r8, [rax+30h]
0x180016bbe  movzx   eax, word ptr [r8+2]
0x180016bc3  imul    rdx, rax, 1Eh
0x180016bc7  movzx   eax, word ptr [r8+4]
0x180016bcc  imul    rcx, rax, 7
0x180016bd0  movzx   eax, word ptr [r8]
0x180016bd4  add     rdx, rcx
0x180016bd7  imul    rcx, rax, 16Dh
0x180016bde  movzx   eax, word ptr [r8+6]
0x180016be3  add     rdx, rcx
0x180016be6  add     rdx, rax
0x180016be9  movzx   eax, word ptr [r8+8]
0x180016bee  lea     rcx, [rdx+rdx*2]
0x180016bf2  lea     rcx, [rax+rcx*8]
0x180016bf6  movzx   eax, word ptr [r8+0Ah]
0x180016bfb  imul    rdx, rcx, 3Ch ; '<'
0x180016bff  add     rdx, rax
0x180016c02  movzx   eax, word ptr [r8+0Ch]
0x180016c07  imul    rcx, rdx, 3Ch ; '<'
0x180016c0b  add     rcx, rax
0x180016c0e  movzx   eax, word ptr [r8+10h]
0x180016c13  imul    rdx, rax, 1Eh
0x180016c17  imul    r15, rcx, 989680h
0x180016c1e  movzx   eax, word ptr [r8+12h]
0x180016c23  imul    rcx, rax, 7
0x180016c27  movzx   eax, word ptr [r8+14h]
0x180016c2c  add     rdx, rcx
0x180016c2f  add     rdx, rax
0x180016c32  movzx   eax, word ptr [r8+0Eh]
0x180016c37  imul    rcx, rax, 16Dh
0x180016c3e  movzx   eax, word ptr [r8+16h]
0x180016c43  add     rdx, rcx
0x180016c46  lea     rcx, [rdx+rdx*2]
0x180016c4a  lea     rcx, [rax+rcx*8]
0x180016c4e  movzx   eax, word ptr [r8+18h]
0x180016c53  imul    rdx, rcx, 3Ch ; '<'
0x180016c57  add     rdx, rax
0x180016c5a  movzx   eax, word ptr [r8+1Ah]
0x180016c5f  imul    rcx, rdx, 3Ch ; '<'
0x180016c63  lea     r8, [rbp+57h+var_78]
0x180016c67  xor     edx, edx
0x180016c69  add     rcx, rax
0x180016c6c  imul    r12, rcx, 989680h
0x180016c73  mov     rcx, rbx
0x180016c76  call    UbpmStatsOperation
0x180016c7b  test    eax, eax
0x180016c7d  jnz     loc_180016E14
0x180016c83  mov     rax, qword ptr [rbp+57h+var_78+4]
0x180016c87  xorps   xmm0, xmm0
0x180016c8a  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rax
0x180016c8e  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x180016c92  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x180016c96  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180016c9a  call    cs:__imp_FileTimeToSystemTime
0x180016ca1  nop     dword ptr [rax+rax+00h]
0x180016ca6  test    eax, eax
0x180016ca8  jz      loc_180016E32
0x180016cae  mov     rax, qword ptr [rbp+57h+var_78+0Ch]
0x180016cb2  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x180016cb6  xorps   xmm0, xmm0
0x180016cb9  mov     qword ptr [rbp+57h+var_B0.dwLowDateTime], rax
0x180016cbd  lea     rcx, [rbp+57h+var_B0]; lpFileTime
0x180016cc1  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180016cc5  call    cs:__imp_FileTimeToSystemTime
0x180016ccc  nop     dword ptr [rax+rax+00h]
0x180016cd1  test    eax, eax
0x180016cd3  jz      loc_180016E3D
0x180016cd9  mov     rax, qword ptr [rbp+57h+var_68+0Ch]
0x180016cdd  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x180016ce1  xorps   xmm0, xmm0
0x180016ce4  mov     qword ptr [rbp+57h+var_C8.dwLowDateTime], rax
0x180016ce8  lea     rcx, [rbp+57h+var_C8]; lpFileTime
0x180016cec  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180016cf0  call    cs:__imp_FileTimeToSystemTime
0x180016cf7  nop     dword ptr [rax+rax+00h]
0x180016cfc  test    eax, eax
0x180016cfe  jz      loc_180016E48
0x180016d04  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; _UBPM_UTILS_SETUP_PARAMS g_SystemSetup
0x180016d0b  call    cs:__imp_RtlAcquireSRWLockShared
0x180016d12  nop     dword ptr [rax+rax+00h]
0x180016d17  movups  xmm0, cs:xmmword_18004FB52
0x180016d1e  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; _UBPM_UTILS_SETUP_PARAMS g_SystemSetup
0x180016d25  movups  [rbp+57h+Source2], xmm0
0x180016d29  call    cs:__imp_RtlReleaseSRWLockShared
0x180016d30  nop     dword ptr [rax+rax+00h]
0x180016d35  xorps   xmm0, xmm0
0x180016d38  lea     rdx, [rbp+57h+Source2]; Source2
0x180016d3c  mov     r8d, 10h; Length
0x180016d42  lea     rcx, [rbp+57h+SystemTime]; Source1
0x180016d46  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180016d4a  call    cs:__imp_RtlCompareMemory
0x180016d51  nop     dword ptr [rax+rax+00h]
0x180016d56  cmp     rax, 10h
0x180016d5a  jz      loc_180016E07
0x180016d60  lea     rdx, [rbp+57h+var_B8]; lpFileTime
0x180016d64  lea     rcx, [rbp+57h+Source2]; lpSystemTime
0x180016d68  call    cs:__imp_SystemTimeToFileTime
0x180016d6f  nop     dword ptr [rax+rax+00h]
0x180016d74  test    eax, eax
0x180016d76  jz      loc_180016E53
0x180016d7c  mov     rcx, rbx
0x180016d7f  call    UbpmpMaintenanceTaskIsCritical
0x180016d84  mov     rcx, qword ptr [rbp+57h+var_C8.dwLowDateTime]
0x180016d88  lea     rdx, [rbp+57h+var_A8]
0x180016d8c  mov     r8, qword ptr [rbp+57h+var_B8.dwLowDateTime]
0x180016d90  lea     r9, [rbp+57h+var_90]
0x180016d94  mov     [rsp+120h+var_D8], rdx
0x180016d99  lea     rdx, [rbp+57h+var_D0]
0x180016d9d  mov     [rsp+120h+var_E0], rdx
0x180016da2  mov     rdx, r12
0x180016da5  mov     [rsp+120h+var_E8], al
0x180016da9  lea     rax, [rbp+57h+var_A0]
0x180016dad  mov     [rbp+57h+var_A0], rcx
0x180016db1  mov     rcx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180016db5  mov     [rsp+120h+var_F8], rax
0x180016dba  lea     rax, [rbp+57h+var_98]
0x180016dbe  mov     [rbp+57h+var_98], rcx
0x180016dc2  mov     rcx, r15
0x180016dc5  mov     [rbp+57h+var_90], r8
0x180016dc9  lea     r8, [rbp+57h+SystemTime]
0x180016dcd  mov     [rsp+120h+var_100], rax
0x180016dd2  mov     qword ptr [rbp+57h+SystemTime.wYear], r14
0x180016dd6  call    UbpmpMaintenanceGetLevelForTime
0x180016ddb  movzx   eax, [rbp+57h+var_D0]
0x180016ddf  mov     [rdi], al
0x180016de1  mov     rax, [rbp+57h+var_A8]
0x180016de5  mov     [rsi], rax
0x180016de8  mov     rcx, [rbp+57h+var_40]
0x180016dec  xor     rcx, rsp; StackCookie
0x180016def  call    __security_check_cookie
0x180016df4  add     rsp, 0F0h
0x180016dfb  pop     r15
0x180016dfd  pop     r14
0x180016dff  pop     r12
0x180016e01  pop     rdi
0x180016e02  pop     rsi
0x180016e03  pop     rbx
0x180016e04  pop     rbp
0x180016e05  retn
0x180016e07  mov     qword ptr [rbp+57h+var_B8.dwLowDateTime], 0
0x180016e0f  jmp     loc_180016D7C
0x180016e14  xor     eax, eax
0x180016e16  mov     dword ptr [rbp+57h+var_78], 3
0x180016e1d  mov     qword ptr [rbp+57h+var_78+4], rax
0x180016e21  mov     qword ptr [rbp+57h+var_78+0Ch], rax
0x180016e25  mov     qword ptr [rbp+57h+var_68+4], rax
0x180016e29  mov     qword ptr [rbp+57h+var_68+0Ch], rax
0x180016e2d  jmp     loc_180016C87
0x180016e32  xor     eax, eax
0x180016e34  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rax
0x180016e38  jmp     loc_180016CAE
0x180016e3d  xor     eax, eax
0x180016e3f  mov     qword ptr [rbp+57h+var_B0.dwLowDateTime], rax
0x180016e43  jmp     loc_180016CD9
0x180016e48  xor     eax, eax
0x180016e4a  mov     qword ptr [rbp+57h+var_C8.dwLowDateTime], rax
0x180016e4e  jmp     loc_180016D04
0x180016e53  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180016e58  xor     eax, eax
0x180016e5a  mov     qword ptr [rbp+57h+var_B8.dwLowDateTime], rax
0x180016e5e  jmp     loc_180016D7C
```
