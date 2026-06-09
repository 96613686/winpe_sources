# PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::EvaluateWnf(TimeValue const &,_WNF_STATE_NAME *,void * const,ulong)

- ea: `0x18000b740`
- end: `0x18000be64`
- name: `?EvaluateWnf@TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@EEAAHAEBVTimeValue@@PEAU_WNF_STATE_NAME@@QEAXK@Z`
- size: `1828`
- prototype: `__int64 __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *__hidden this, const struct TimeValue *, struct _WNF_STATE_NAME *, void *const, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000b740`
- `0x180020c30`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000b90b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000b97f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000ba23`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000bac1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000bd65`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000be03`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000b90b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000b97f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000ba23`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000bac1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000bd65`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000be03`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000bdd3`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000bdd3`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000b879`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000bca4`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000bcd7`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000b879`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000bca4`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000bcd7`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000b9c9`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000b9fb`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000bd3d`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000b9c9`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000b9fb`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000bd3d`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18000ba91`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18000ba91`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000b94f`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000b94f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000b8db`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000b8db`
- `TimeBrokerClient!TbQueryCEventTriggerTime` at `0x18000bc1f`
- `TimeBrokerClient!TbQueryCEventTriggerTime` at `0x18000bc1f`
- `TimeBrokerClient!TbUpdateCEvent` at `0x18000bbf6`
- `TimeBrokerClient!TbUpdateCEvent` at `0x18000bbf6`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::EvaluateWnf(
        PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *this,
        const struct TimeValue *a2,
        struct _WNF_STATE_NAME *a3,
        void *const a4,
        unsigned int a5)
{
  __int64 v6; // rcx
  int v7; // eax
  int v8; // edx
  FILETIME v9; // rcx
  int v10; // eax
  FILETIME v11; // rcx
  DWORD v12; // eax
  __int64 v13; // rsi
  __int64 v14; // rbx
  DWORD v15; // eax
  __int64 v16; // rcx
  __int128 v17; // xmm1
  __int128 v18; // xmm2
  __int128 v19; // xmm3
  __int128 v20; // xmm4
  __int128 v21; // xmm5
  __int128 v22; // xmm6
  __int128 v23; // xmm7
  __int128 v24; // xmm8
  __int128 v25; // xmm9
  __int128 v26; // xmm10
  __int128 v27; // xmm11
  __int128 v28; // xmm12
  __int128 v29; // xmm13
  __int128 v30; // xmm14
  __int64 v31; // rcx
  __int64 v32; // rcx
  DWORD v34; // eax
  _OWORD v35[15]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+120h] [rbp+20h]
  __int128 v37; // [rsp+130h] [rbp+30h]
  __int128 v38; // [rsp+140h] [rbp+40h]
  struct _SYSTEMTIME UniversalTime; // [rsp+230h] [rbp+130h] BYREF
  SYSTEMTIME LocalTime; // [rsp+240h] [rbp+140h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+250h] [rbp+150h] BYREF
  FILETIME FileTime; // [rsp+260h] [rbp+160h] BYREF
  FILETIME v43; // [rsp+268h] [rbp+168h]
  int v44; // [rsp+270h] [rbp+170h]
  int v45; // [rsp+274h] [rbp+174h]
  int v46; // [rsp+278h] [rbp+178h]
  struct _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+280h] [rbp+180h] BYREF
  DWORD v48; // [rsp+32Ch] [rbp+22Ch]
  SYSTEMTIME v49; // [rsp+330h] [rbp+230h] BYREF
  struct _FILETIME v50; // [rsp+340h] [rbp+240h] BYREF
  struct _FILETIME v51; // [rsp+348h] [rbp+248h]
  __int64 v52; // [rsp+350h] [rbp+250h]
  int v53; // [rsp+358h] [rbp+258h]
  SYSTEMTIME v54; // [rsp+360h] [rbp+260h] BYREF
  struct _FILETIME v55; // [rsp+370h] [rbp+270h] BYREF
  struct _FILETIME v56; // [rsp+378h] [rbp+278h]
  __int64 v57; // [rsp+380h] [rbp+280h]
  int v58; // [rsp+388h] [rbp+288h]

  v6 = *((_QWORD *)this + 51);
  if ( !v6 )
  {
    *((_DWORD *)this + 53) = 0;
    return *((unsigned int *)this + 46);
  }
  v7 = (*(__int64 (__fastcall **)(__int64, const struct TimeValue *, struct _WNF_STATE_NAME *, void *const, unsigned int))(*(_QWORD *)v6 + 40LL))(
         v6,
         a2,
         a3,
         a4,
         a5);
  v8 = v7;
  if ( *((_DWORD *)this + 53) != v7 )
  {
    *((_DWORD *)this + 53) = v7;
    v9 = (FILETIME)*((_QWORD *)this + 30);
    FileTime = (FILETIME)*((_QWORD *)this + 29);
    v44 = *((_DWORD *)this + 62);
    v10 = *((_DWORD *)this + 63);
    v43 = v9;
    v45 = v10;
    v46 = 1;
    SystemTime = *(struct _SYSTEMTIME *)((char *)this + 216);
    if ( v8 )
    {
      v11 = (FILETIME)(*(_QWORD *)&v9 - *((_QWORD *)this + 25));
    }
    else
    {
      if ( *((_DWORD *)this + 52) != 1 )
        goto LABEL_6;
      v11 = (FILETIME)(*((_QWORD *)this + 25) + *(_QWORD *)&v9);
    }
    v43 = v11;
    FileTime = v11;
    FileTimeToSystemTime(&FileTime, &SystemTime);
LABEL_6:
    v50 = 0;
    v52 = 0;
    v53 = 0;
    v49 = 0;
    v51 = 0;
    v57 = 0;
    v58 = 0;
    v54 = 0;
    v55 = 0;
    v56 = 0;
    UniversalTime = 0;
    GetSystemTime(&UniversalTime);
    v54 = UniversalTime;
    if ( SystemTimeToFileTime(&v54, &v55) )
    {
      v56 = v55;
      v57 = 0;
      v58 = 1;
    }
    LocalTime = 0;
    GetLocalTime(&LocalTime);
    v49 = LocalTime;
    if ( SystemTimeToFileTime(&v49, &v50) )
    {
      v51 = v50;
      v52 = 0;
      v53 = 1;
    }
    v12 = GetTimeZoneInformation(&TimeZoneInformation);
    v13 = *(_QWORD *)&SystemTime.wYear;
    v14 = *(_QWORD *)&SystemTime.wHour;
    v48 = v12;
    if ( (*(_BYTE *)(*((_QWORD *)this + 22) + 44LL) & 8) != 0 )
    {
      v34 = GetTimeZoneInformation(&TimeZoneInformation);
      *(_QWORD *)&v54.wYear = v13;
      v48 = v34;
      *(_QWORD *)&v54.wHour = v14;
      if ( SystemTimeToFileTime(&v54, &v55) )
      {
        v56 = v55;
        v57 = 0;
        v58 = 1;
      }
      LocalTime = v54;
      UniversalTime = 0;
      SystemTimeToTzSpecificLocalTime(&TimeZoneInformation, &LocalTime, &UniversalTime);
      v49 = UniversalTime;
      if ( SystemTimeToFileTime(&v49, &v50) )
      {
        v51 = v50;
        v52 = 0;
        v53 = 1;
      }
    }
    else
    {
      v15 = GetTimeZoneInformation(&TimeZoneInformation);
      *(_QWORD *)&v49.wYear = v13;
      v48 = v15;
      *(_QWORD *)&v49.wHour = v14;
      if ( SystemTimeToFileTime(&v49, &v50) )
      {
        v51 = v50;
        v52 = 0;
        v53 = 1;
      }
      LocalTime = v49;
      UniversalTime = 0;
      TzSpecificLocalTimeToSystemTime(&TimeZoneInformation, &LocalTime, &UniversalTime);
      v54 = UniversalTime;
      if ( SystemTimeToFileTime(&v54, &v55) )
      {
        v56 = v55;
        v57 = 0;
        v58 = 1;
      }
    }
    v16 = *((_QWORD *)this + 92);
    v17 = *((_OWORD *)this + 32);
    v18 = *((_OWORD *)this + 33);
    v19 = *((_OWORD *)this + 34);
    v20 = *((_OWORD *)this + 35);
    v21 = *((_OWORD *)this + 36);
    v22 = *((_OWORD *)this + 37);
    v23 = *((_OWORD *)this + 38);
    v24 = *((_OWORD *)this + 39);
    v25 = *((_OWORD *)this + 40);
    v26 = *((_OWORD *)this + 41);
    v27 = *((_OWORD *)this + 42);
    v28 = *((_OWORD *)this + 43);
    v29 = *((_OWORD *)this + 44);
    v30 = *((_OWORD *)this + 45);
    v37 = *((_OWORD *)this + 31);
    v38 = v17;
    if ( *((_DWORD *)this + 53) )
      HIDWORD(v38) = 1;
    *((_QWORD *)&v37 + 1) = *(_QWORD *)&v54.wYear;
    *(_QWORD *)&v38 = *(_QWORD *)&v54.wHour;
    v36 = v16;
    v31 = *((_QWORD *)this + 52);
    v35[1] = v38;
    v35[0] = v37;
    v35[2] = v18;
    v35[3] = v19;
    v35[4] = v20;
    v35[5] = v21;
    v35[6] = v22;
    v35[7] = v23;
    v35[8] = v24;
    v35[9] = v25;
    v35[10] = v26;
    v35[11] = v27;
    v35[12] = v28;
    v35[13] = v29;
    v35[14] = v30;
    TbUpdateCEvent(v31, v35);
    v32 = *((_QWORD *)this + 52);
    *(_QWORD *)&LocalTime.wYear = 0;
    *(_QWORD *)&UniversalTime.wYear = 0;
    if ( (int)TbQueryCEventTriggerTime(v32, &LocalTime, &UniversalTime) >= 0 )
    {
      *((_QWORD *)this + 41) = *(_QWORD *)&LocalTime.wYear;
      if ( FileTimeToSystemTime((const FILETIME *)this + 41, (LPSYSTEMTIME)((char *)this + 312)) )
      {
        *((_DWORD *)this + 85) = *((_DWORD *)this + 83);
        *((_DWORD *)this + 84) = *((_DWORD *)this + 82);
        *((_QWORD *)this + 43) = 0;
        *((_DWORD *)this + 88) = 1;
      }
      *((_QWORD *)this + 47) = *(_QWORD *)&UniversalTime.wYear;
      if ( FileTimeToSystemTime((const FILETIME *)this + 47, (LPSYSTEMTIME)((char *)this + 360)) )
      {
        *((_DWORD *)this + 97) = *((_DWORD *)this + 95);
        *((_DWORD *)this + 96) = *((_DWORD *)this + 94);
        *((_QWORD *)this + 49) = 0;
        *((_DWORD *)this + 100) = 1;
      }
    }
  }
  return *((unsigned int *)this + 46);
}

```

## disassembly

```asm
0x18000b740  push    rbp
0x18000b742  push    rdi
0x18000b743  push    r14
0x18000b745  lea     rbp, [rsp-350h]
0x18000b74d  sub     rsp, 450h
0x18000b754  mov     rax, cs:__security_cookie
0x18000b75b  xor     rax, rsp
0x18000b75e  mov     [rbp+360h+var_D0], rax
0x18000b765  mov     rdi, rcx
0x18000b768  mov     rcx, [rcx+198h]
0x18000b76f  test    rcx, rcx
0x18000b772  jz      loc_18000BD31
0x18000b778  mov     rax, [rcx]
0x18000b77b  mov     r10d, [rbp+360h+arg_20]
0x18000b782  mov     [rsp+460h+var_440], r10d
0x18000b787  mov     rax, [rax+28h]
0x18000b78b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b790  mov     edx, eax
0x18000b792  cmp     [rdi+0D4h], eax
0x18000b798  jz      loc_18000BD10
0x18000b79e  movaps  [rsp+460h+var_40], xmm6
0x18000b7a6  movaps  [rsp+460h+var_50], xmm7
0x18000b7ae  movaps  [rsp+460h+var_60], xmm8
0x18000b7b7  mov     [rdi+0D4h], eax
0x18000b7bd  mov     rax, [rdi+0E8h]
0x18000b7c4  mov     rcx, [rdi+0F0h]
0x18000b7cb  movaps  [rsp+460h+var_70], xmm9
0x18000b7d4  movaps  [rsp+460h+var_80], xmm10
0x18000b7dd  movaps  [rsp+460h+var_90], xmm11
0x18000b7e6  mov     qword ptr [rbp+360h+FileTime.dwLowDateTime], rax
0x18000b7ed  mov     eax, [rdi+0F8h]
0x18000b7f3  movaps  [rsp+460h+var_A0], xmm12
0x18000b7fc  mov     [rbp+360h+var_1F0], eax
0x18000b802  mov     eax, [rdi+0FCh]
0x18000b808  movaps  [rsp+460h+var_B0], xmm13
0x18000b811  movaps  [rsp+460h+var_C0], xmm14
0x18000b81a  mov     [rbp+360h+var_1F8], rcx
0x18000b821  mov     [rbp+360h+var_1EC], eax
0x18000b827  mov     [rbp+360h+var_1E8], 1
0x18000b831  movups  xmm0, xmmword ptr [rdi+0D8h]
0x18000b838  movups  xmmword ptr [rbp+360h+SystemTime.wYear], xmm0
0x18000b83f  test    edx, edx
0x18000b841  jz      loc_18000BE3F
0x18000b847  sub     rcx, [rdi+0C8h]
0x18000b84e  mov     [rbp+360h+var_1F8], rcx
0x18000b855  lea     rdx, [rbp+360h+SystemTime]; lpSystemTime
0x18000b85c  mov     eax, dword ptr [rbp+360h+var_1F8]
0x18000b862  shr     rcx, 20h
0x18000b866  mov     [rbp+360h+FileTime.dwHighDateTime], ecx
0x18000b86c  lea     rcx, [rbp+360h+FileTime]; lpFileTime
0x18000b873  mov     [rbp+360h+FileTime.dwLowDateTime], eax
0x18000b879  call    cs:__imp_FileTimeToSystemTime
0x18000b87f  xor     eax, eax
0x18000b881  lea     rcx, [rbp+360h+UniversalTime]; lpSystemTime
0x18000b888  xor     r14d, r14d
0x18000b88b  mov     qword ptr [rbp+360h+var_120.dwLowDateTime], rax
0x18000b892  xorps   xmm0, xmm0
0x18000b895  mov     [rbp+360h+var_110], r14
0x18000b89c  mov     [rbp+360h+var_108], r14d
0x18000b8a3  movups  xmmword ptr [rbp+360h+var_130.wYear], xmm0
0x18000b8aa  mov     [rbp+360h+var_118], rax
0x18000b8b1  mov     [rbp+360h+var_E0], r14
0x18000b8b8  mov     [rbp+360h+var_D8], r14d
0x18000b8bf  movups  xmmword ptr [rbp+360h+var_100.wYear], xmm0
0x18000b8c6  mov     qword ptr [rbp+360h+var_F0.dwLowDateTime], rax
0x18000b8cd  mov     [rbp+360h+var_E8], rax
0x18000b8d4  movups  xmmword ptr [rbp+360h+UniversalTime.wYear], xmm0
0x18000b8db  call    cs:__imp_GetSystemTime
0x18000b8e1  mov     rax, qword ptr [rbp+360h+UniversalTime.wYear]
0x18000b8e8  lea     rdx, [rbp+360h+var_F0]; lpFileTime
0x18000b8ef  mov     qword ptr [rbp+360h+var_100.wYear], rax
0x18000b8f6  lea     rcx, [rbp+360h+var_100]; lpSystemTime
0x18000b8fd  mov     rax, qword ptr [rbp+360h+UniversalTime.wHour]
0x18000b904  mov     qword ptr [rbp+360h+var_100.wHour], rax
0x18000b90b  call    cs:__imp_SystemTimeToFileTime
0x18000b911  test    eax, eax
0x18000b913  jz      short loc_18000B93E
0x18000b915  mov     eax, [rbp+360h+var_F0.dwHighDateTime]
0x18000b91b  mov     dword ptr [rbp+360h+var_E8+4], eax
0x18000b921  mov     eax, [rbp+360h+var_F0.dwLowDateTime]
0x18000b927  mov     dword ptr [rbp+360h+var_E8], eax
0x18000b92d  mov     [rbp+360h+var_E0], r14
0x18000b934  mov     [rbp+360h+var_D8], 1
0x18000b93e  xorps   xmm0, xmm0
0x18000b941  lea     rcx, [rbp+360h+LocalTime]; lpSystemTime
0x18000b948  movups  xmmword ptr [rbp+360h+LocalTime.wYear], xmm0
0x18000b94f  call    cs:__imp_GetLocalTime
0x18000b955  mov     rax, qword ptr [rbp+360h+LocalTime.wYear]
0x18000b95c  lea     rdx, [rbp+360h+var_120]; lpFileTime
0x18000b963  mov     qword ptr [rbp+360h+var_130.wYear], rax
0x18000b96a  lea     rcx, [rbp+360h+var_130]; lpSystemTime
0x18000b971  mov     rax, qword ptr [rbp+360h+LocalTime.wHour]
0x18000b978  mov     qword ptr [rbp+360h+var_130.wHour], rax
0x18000b97f  call    cs:__imp_SystemTimeToFileTime
0x18000b985  test    eax, eax
0x18000b987  jz      short loc_18000B9B2
0x18000b989  mov     eax, [rbp+360h+var_120.dwHighDateTime]
0x18000b98f  mov     dword ptr [rbp+360h+var_118+4], eax
0x18000b995  mov     eax, [rbp+360h+var_120.dwLowDateTime]
0x18000b99b  mov     dword ptr [rbp+360h+var_118], eax
0x18000b9a1  mov     [rbp+360h+var_110], r14
0x18000b9a8  mov     [rbp+360h+var_108], 1
0x18000b9b2  mov     [rsp+460h+var_18], rbx
0x18000b9ba  lea     rcx, [rbp+360h+TimeZoneInformation]; lpTimeZoneInformation
0x18000b9c1  mov     [rsp+460h+var_20], rsi
0x18000b9c9  call    cs:__imp_GetTimeZoneInformation
0x18000b9cf  mov     rsi, qword ptr [rbp+360h+SystemTime.wYear]
0x18000b9d6  lea     rcx, [rbp+360h+TimeZoneInformation]; lpTimeZoneInformation
0x18000b9dd  mov     rbx, qword ptr [rbp+360h+SystemTime.wHour]
0x18000b9e4  mov     [rbp+360h+var_134], eax
0x18000b9ea  mov     rax, [rdi+0B0h]
0x18000b9f1  test    byte ptr [rax+2Ch], 8
0x18000b9f5  jnz     loc_18000BD3D
0x18000b9fb  call    cs:__imp_GetTimeZoneInformation
0x18000ba01  lea     rdx, [rbp+360h+var_120]; lpFileTime
0x18000ba08  mov     qword ptr [rbp+360h+var_130.wYear], rsi
0x18000ba0f  lea     rcx, [rbp+360h+var_130]; lpSystemTime
0x18000ba16  mov     [rbp+360h+var_134], eax
0x18000ba1c  mov     qword ptr [rbp+360h+var_130.wHour], rbx
0x18000ba23  call    cs:__imp_SystemTimeToFileTime
0x18000ba29  test    eax, eax
0x18000ba2b  jz      short loc_18000BA56
0x18000ba2d  mov     eax, [rbp+360h+var_120.dwHighDateTime]
0x18000ba33  mov     dword ptr [rbp+360h+var_118+4], eax
0x18000ba39  mov     eax, [rbp+360h+var_120.dwLowDateTime]
0x18000ba3f  mov     dword ptr [rbp+360h+var_118], eax
0x18000ba45  mov     [rbp+360h+var_110], r14
0x18000ba4c  mov     [rbp+360h+var_108], 1
0x18000ba56  mov     rax, qword ptr [rbp+360h+var_130.wYear]
0x18000ba5d  lea     r8, [rbp+360h+UniversalTime]; lpUniversalTime
0x18000ba64  mov     qword ptr [rbp+360h+LocalTime.wYear], rax
0x18000ba6b  lea     rdx, [rbp+360h+LocalTime]; lpLocalTime
0x18000ba72  mov     rax, qword ptr [rbp+360h+var_130.wHour]
0x18000ba79  lea     rcx, [rbp+360h+TimeZoneInformation]; lpTimeZoneInformation
0x18000ba80  xorps   xmm0, xmm0
0x18000ba83  mov     qword ptr [rbp+360h+LocalTime.wHour], rax
0x18000ba8a  movups  xmmword ptr [rbp+360h+UniversalTime.wYear], xmm0
0x18000ba91  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x18000ba97  mov     rax, qword ptr [rbp+360h+UniversalTime.wYear]
0x18000ba9e  lea     rdx, [rbp+360h+var_F0]; lpFileTime
0x18000baa5  mov     qword ptr [rbp+360h+var_100.wYear], rax
0x18000baac  lea     rcx, [rbp+360h+var_100]; lpSystemTime
0x18000bab3  mov     rax, qword ptr [rbp+360h+UniversalTime.wHour]
0x18000baba  mov     qword ptr [rbp+360h+var_100.wHour], rax
0x18000bac1  call    cs:__imp_SystemTimeToFileTime
0x18000bac7  test    eax, eax
0x18000bac9  jz      short loc_18000BAF4
0x18000bacb  mov     eax, [rbp+360h+var_F0.dwHighDateTime]
0x18000bad1  mov     dword ptr [rbp+360h+var_E8+4], eax
0x18000bad7  mov     eax, [rbp+360h+var_F0.dwLowDateTime]
0x18000badd  mov     dword ptr [rbp+360h+var_E8], eax
0x18000bae3  mov     [rbp+360h+var_E0], r14
0x18000baea  mov     [rbp+360h+var_D8], 1
0x18000baf4  movups  xmm0, xmmword ptr [rdi+1F0h]
0x18000bafb  mov     rcx, [rdi+2E0h]
0x18000bb02  movups  xmm1, xmmword ptr [rdi+200h]
0x18000bb09  movups  xmm2, xmmword ptr [rdi+210h]
0x18000bb10  movups  xmm3, xmmword ptr [rdi+220h]
0x18000bb17  movups  xmm4, xmmword ptr [rdi+230h]
0x18000bb1e  movups  xmm5, xmmword ptr [rdi+240h]
0x18000bb25  movups  xmm6, xmmword ptr [rdi+250h]
0x18000bb2c  movups  xmm7, xmmword ptr [rdi+260h]
0x18000bb33  movups  xmm8, xmmword ptr [rdi+270h]
0x18000bb3b  movups  xmm9, xmmword ptr [rdi+280h]
0x18000bb43  movups  xmm10, xmmword ptr [rdi+290h]
0x18000bb4b  movups  xmm11, xmmword ptr [rdi+2A0h]
0x18000bb53  movups  xmm12, xmmword ptr [rdi+2B0h]
0x18000bb5b  movups  xmm13, xmmword ptr [rdi+2C0h]
0x18000bb63  movups  xmm14, xmmword ptr [rdi+2D0h]
0x18000bb6b  movups  [rbp+360h+var_330], xmm0
0x18000bb6f  movups  [rbp+360h+var_320], xmm1
0x18000bb73  cmp     [rdi+0D4h], r14d
0x18000bb7a  jnz     loc_18000BE58
0x18000bb80  mov     rax, qword ptr [rbp+360h+var_100.wYear]
0x18000bb87  lea     rdx, [rsp+460h+var_430]
0x18000bb8c  mov     qword ptr [rbp+360h+var_330+8], rax
0x18000bb90  mov     rax, qword ptr [rbp+360h+var_100.wHour]
0x18000bb97  movaps  xmm0, [rbp+360h+var_330]
0x18000bb9b  mov     qword ptr [rbp+360h+var_320], rax
0x18000bb9f  movaps  xmm1, [rbp+360h+var_320]
0x18000bba3  mov     [rbp+360h+var_340], rcx
0x18000bba7  mov     rcx, [rdi+1A0h]
0x18000bbae  movups  [rsp+460h+var_420], xmm1
0x18000bbb3  movups  [rsp+460h+var_430], xmm0
0x18000bbb8  movups  [rsp+460h+var_410], xmm2
0x18000bbbd  movups  [rsp+460h+var_400], xmm3
0x18000bbc2  movups  [rsp+460h+var_3F0], xmm4
0x18000bbc7  movups  [rbp+360h+var_3E0], xmm5
0x18000bbcb  movups  [rbp+360h+var_3D0], xmm6
0x18000bbcf  movups  [rbp+360h+var_3C0], xmm7
0x18000bbd3  movups  [rbp+360h+var_3B0], xmm8
0x18000bbd8  movups  [rbp+360h+var_3A0], xmm9
0x18000bbdd  movups  [rbp+360h+var_390], xmm10
0x18000bbe2  movups  [rbp+360h+var_380], xmm11
0x18000bbe7  movups  [rbp+360h+var_370], xmm12
0x18000bbec  movups  [rbp+360h+var_360], xmm13
0x18000bbf1  movups  [rbp+360h+var_350], xmm14
0x18000bbf6  call    cs:__imp_TbUpdateCEvent
0x18000bbfc  mov     rcx, [rdi+1A0h]
0x18000bc03  lea     r8, [rbp+360h+UniversalTime]
0x18000bc0a  lea     rdx, [rbp+360h+LocalTime]
0x18000bc11  mov     qword ptr [rbp+360h+LocalTime.wYear], r14
0x18000bc18  mov     qword ptr [rbp+360h+UniversalTime.wYear], r14
0x18000bc1f  call    cs:__imp_TbQueryCEventTriggerTime
0x18000bc25  movaps  xmm14, [rsp+460h+var_C0]
0x18000bc2e  movaps  xmm13, [rsp+460h+var_B0]
0x18000bc37  movaps  xmm12, [rsp+460h+var_A0]
0x18000bc40  movaps  xmm11, [rsp+460h+var_90]
0x18000bc49  movaps  xmm10, [rsp+460h+var_80]
0x18000bc52  movaps  xmm9, [rsp+460h+var_70]
0x18000bc5b  movaps  xmm8, [rsp+460h+var_60]
0x18000bc64  movaps  xmm7, [rsp+460h+var_50]
0x18000bc6c  movaps  xmm6, [rsp+460h+var_40]
0x18000bc74  test    eax, eax
0x18000bc76  js      loc_18000BD00
0x18000bc7c  mov     rax, qword ptr [rbp+360h+LocalTime.wYear]
0x18000bc83  lea     rsi, [rdi+138h]
0x18000bc8a  mov     rdx, rsi; lpSystemTime
0x18000bc8d  mov     [rsp+460h+var_28], r15
0x18000bc95  lea     rcx, [rsi+10h]; lpFileTime
0x18000bc99  mov     [rsi+10h], rax
0x18000bc9d  lea     rbx, [rdi+168h]
0x18000bca4  call    cs:__imp_FileTimeToSystemTime
0x18000bcaa  test    eax, eax
0x18000bcac  jz      short loc_18000BCC5
0x18000bcae  mov     eax, [rsi+14h]
0x18000bcb1  mov     [rsi+1Ch], eax
0x18000bcb4  mov     eax, [rsi+10h]
0x18000bcb7  mov     [rsi+18h], eax
0x18000bcba  mov     [rsi+20h], r14
0x18000bcbe  mov     dword ptr [rsi+28h], 1
0x18000bcc5  mov     rax, qword ptr [rbp+360h+UniversalTime.wYear]
0x18000bccc  lea     rcx, [rbx+10h]; lpFileTime
0x18000bcd0  mov     rdx, rbx; lpSystemTime
0x18000bcd3  mov     [rbx+10h], rax
0x18000bcd7  call    cs:__imp_FileTimeToSystemTime
0x18000bcdd  mov     r15, [rsp+460h+var_28]
0x18000bce5  test    eax, eax
0x18000bce7  jz      short loc_18000BD00
0x18000bce9  mov     eax, [rbx+14h]
0x18000bcec  mov     [rbx+1Ch], eax
0x18000bcef  mov     eax, [rbx+10h]
0x18000bcf2  mov     [rbx+18h], eax
0x18000bcf5  mov     [rbx+20h], r14
0x18000bcf9  mov     dword ptr [rbx+28h], 1
0x18000bd00  mov     rsi, [rsp+460h+var_20]
0x18000bd08  mov     rbx, [rsp+460h+var_18]
0x18000bd10  mov     eax, [rdi+0B8h]
0x18000bd16  mov     rcx, [rbp+360h+var_D0]
0x18000bd1d  xor     rcx, rsp; StackCookie
0x18000bd20  call    __security_check_cookie
0x18000bd25  add     rsp, 450h
0x18000bd2c  pop     r14
0x18000bd2e  pop     rdi
0x18000bd2f  pop     rbp
0x18000bd30  retn
0x18000bd31  xor     r14d, r14d
0x18000bd34  mov     [rdi+0D4h], r14d
0x18000bd3b  jmp     short loc_18000BD10
0x18000bd3d  call    cs:__imp_GetTimeZoneInformation
0x18000bd43  lea     rdx, [rbp+360h+var_F0]; lpFileTime
0x18000bd4a  mov     qword ptr [rbp+360h+var_100.wYear], rsi
0x18000bd51  lea     rcx, [rbp+360h+var_100]; lpSystemTime
0x18000bd58  mov     [rbp+360h+var_134], eax
0x18000bd5e  mov     qword ptr [rbp+360h+var_100.wHour], rbx
0x18000bd65  call    cs:__imp_SystemTimeToFileTime
0x18000bd6b  test    eax, eax
0x18000bd6d  jz      short loc_18000BD98
0x18000bd6f  mov     eax, [rbp+360h+var_F0.dwHighDateTime]
0x18000bd75  mov     dword ptr [rbp+360h+var_E8+4], eax
0x18000bd7b  mov     eax, [rbp+360h+var_F0.dwLowDateTime]
0x18000bd81  mov     dword ptr [rbp+360h+var_E8], eax
0x18000bd87  mov     [rbp+360h+var_E0], r14
0x18000bd8e  mov     [rbp+360h+var_D8], 1
0x18000bd98  mov     rax, qword ptr [rbp+360h+var_100.wYear]
0x18000bd9f  lea     r8, [rbp+360h+UniversalTime]; lpLocalTime
0x18000bda6  mov     qword ptr [rbp+360h+LocalTime.wYear], rax
0x18000bdad  lea     rdx, [rbp+360h+LocalTime]; lpUniversalTime
0x18000bdb4  mov     rax, qword ptr [rbp+360h+var_100.wHour]
0x18000bdbb  lea     rcx, [rbp+360h+TimeZoneInformation]; lpTimeZoneInformation
0x18000bdc2  xorps   xmm0, xmm0
0x18000bdc5  mov     qword ptr [rbp+360h+LocalTime.wHour], rax
0x18000bdcc  movups  xmmword ptr [rbp+360h+UniversalTime.wYear], xmm0
0x18000bdd3  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x18000bdd9  mov     rax, qword ptr [rbp+360h+UniversalTime.wYear]
0x18000bde0  lea     rdx, [rbp+360h+var_120]; lpFileTime
0x18000bde7  mov     qword ptr [rbp+360h+var_130.wYear], rax
0x18000bdee  lea     rcx, [rbp+360h+var_130]; lpSystemTime
0x18000bdf5  mov     rax, qword ptr [rbp+360h+UniversalTime.wHour]
0x18000bdfc  mov     qword ptr [rbp+360h+var_130.wHour], rax
0x18000be03  call    cs:__imp_SystemTimeToFileTime
0x18000be09  test    eax, eax
0x18000be0b  jz      loc_18000BAF4
0x18000be11  mov     eax, [rbp+360h+var_120.dwHighDateTime]
0x18000be17  mov     dword ptr [rbp+360h+var_118+4], eax
0x18000be1d  mov     eax, [rbp+360h+var_120.dwLowDateTime]
0x18000be23  mov     dword ptr [rbp+360h+var_118], eax
0x18000be29  mov     [rbp+360h+var_110], r14
0x18000be30  mov     [rbp+360h+var_108], 1
0x18000be3a  jmp     loc_18000BAF4
  ... truncated ...
```
