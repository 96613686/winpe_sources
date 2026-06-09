# CFbrProcessor::CreateGlobalObjects(void *,ulong,ulong,ushort * *,ushort * *,ushort * *)

- ea: `0x180078cd0`
- end: `0x18007971e`
- name: `?CreateGlobalObjects@CFbrProcessor@@IEAAJPEAXKKPEAPEAG11@Z`
- size: `2638`
- prototype: `__int64 __fastcall(CFbrProcessor *this, void *, unsigned int, int, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800cb1d4`

## callees

- `0x180023384`
- `0x180076090`
- `0x180078360`
- `0x180078800`
- `0x180078cd0`
- `0x180079724`
- `0x180079770`
- `0x18007f6a4`
- `0x1800cafa4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180078ea6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180078ea6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079055`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007908e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007945c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079683`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079055`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007908e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007945c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079683`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18007921a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18007921a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180079022`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180079022`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800793ec`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800793ec`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180079522`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180079641`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180079522`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180079641`

## string_xrefs

- `0x180079100`: `AddSidToObjectsSecurityDescriptor failed!`
- `0x1800794d7`: `AddSidToObjectsSecurityDescriptor failed!`

## pseudocode

```c
__int64 __fastcall CFbrProcessor::CreateGlobalObjects(
        CFbrProcessor *this,
        void *a2,
        unsigned int a3,
        int a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7)
{
  unsigned __int16 *v9; // r14
  void *v10; // r15
  WCHAR *v11; // r12
  unsigned __int16 *v12; // rsi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v14; // rdx
  signed int ObjectNameSuffix; // ebx
  unsigned int v16; // eax
  void *v17; // rdi
  unsigned int v18; // eax
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v22; // ebx
  unsigned int v23; // eax
  __int64 v24; // rdx
  signed int v25; // eax
  CFbrProcessor *v26; // rcx
  unsigned int v27; // eax
  int v28; // edx
  unsigned int v29; // eax
  unsigned int v30; // eax
  HANDLE MutexW; // rax
  signed int v32; // eax
  CFbrProcessor *v33; // rcx
  unsigned int v34; // eax
  unsigned __int16 *v35; // rsi
  unsigned int v36; // eax
  unsigned int v37; // r15d
  HANDLE FileMappingW; // rax
  signed int v39; // eax
  unsigned int v40; // ebx
  unsigned int v41; // eax
  __int64 v42; // rdx
  signed int v43; // eax
  unsigned int v44; // eax
  unsigned __int8 *v45; // rax
  signed int v46; // eax
  unsigned int v47; // eax
  _DWORD *v48; // rax
  signed int v49; // eax
  unsigned int v50; // ecx
  __int64 v51; // rcx
  int v52; // eax
  unsigned __int16 **v53; // rax
  unsigned __int16 *v54; // [rsp+68h] [rbp-A0h]
  void *Block; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v56[2]; // [rsp+78h] [rbp-90h]
  unsigned __int16 *v57; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int16 *v58; // [rsp+88h] [rbp-80h] BYREF
  LPCWSTR lpName; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int16 *v60; // [rsp+98h] [rbp-70h] BYREF
  LPCWSTR v61; // [rsp+A0h] [rbp-68h] BYREF
  int v62; // [rsp+A8h] [rbp-60h]
  void *v63; // [rsp+B0h] [rbp-58h]
  DWORD dwFileOffsetLow[2]; // [rsp+B8h] [rbp-50h]
  unsigned __int16 **v65; // [rsp+C0h] [rbp-48h]
  unsigned __int16 **v66; // [rsp+C8h] [rbp-40h]
  unsigned __int16 **v67; // [rsp+D0h] [rbp-38h]
  struct _SYSTEM_INFO SystemInfo; // [rsp+D8h] [rbp-30h] BYREF

  v67 = a5;
  v66 = a6;
  v65 = a7;
  v9 = 0;
  v56[0] = a3;
  v10 = 0;
  v63 = a2;
  v11 = 0;
  v60 = 0;
  v12 = 0;
  v58 = 0;
  Block = 0;
  v61 = 0;
  lpName = 0;
  v57 = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  if ( *((_QWORD *)this + 14) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147418113;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 37;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids,
      CurrentThreadActivityIdPrefix,
      -2147418113);
    return (unsigned int)-2147418113;
  }
  if ( *((_QWORD *)this + 15) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147418113;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 38;
    goto LABEL_6;
  }
  if ( *((_QWORD *)this + 13) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147418113;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 39;
    goto LABEL_6;
  }
  if ( *((_QWORD *)this + 16) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147418113;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 40;
    goto LABEL_6;
  }
  if ( *((_QWORD *)this + 21) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147418113;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 41;
    goto LABEL_6;
  }
  v62 = -a3;
  GetSystemInfo(&SystemInfo);
  *(_QWORD *)dwFileOffsetLow = SystemInfo.dwAllocationGranularity * (0x38 / SystemInfo.dwAllocationGranularity + 1);
  ObjectNameSuffix = CFbrProcessor::GenerateObjectNameSuffix(
                       (CFbrProcessor *)SystemInfo.dwAllocationGranularity,
                       (unsigned __int16 **)&Block);
  if ( ObjectNameSuffix < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids,
        v16,
        (__int64)"GenerateObjectNameSuffix failed!",
        ObjectNameSuffix);
    }
    v17 = Block;
    goto LABEL_41;
  }
  v54 = (unsigned __int16 *)Block;
  ObjectNameSuffix = CFbrProcessor::GenerateObjectName(this, (const unsigned __int16 *)Block, &v57);
  if ( ObjectNameSuffix < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        (unsigned int)WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids,
        v18,
        (__int64)"GenerateObjectName failed!",
        ObjectNameSuffix);
    }
    v12 = v57;
    goto LABEL_40;
  }
  v12 = v57;
  EventW = CreateEventW(0, 0, 0, v57);
  *((_QWORD *)this + 14) = EventW;
  if ( !EventW )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v22 = LastError;
      if ( LastError > 0 )
        v22 = (unsigned __int16)LastError | 0x80070000;
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      v24 = 44;
LABEL_59:
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids, v23, v22);
      goto LABEL_60;
    }
    goto LABEL_60;
  }
  ObjectNameSuffix = CFbrProcessor::AddSidToObjectsSecurityDescriptor(this, EventW, SE_KERNEL_OBJECT, v63, 0x100000u);
  if ( ObjectNameSuffix >= 0 )
  {
    ObjectNameSuffix = CFbrProcessor::GenerateObjectNameSuffix(v26, &v58);
    if ( ObjectNameSuffix < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v29 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          (unsigned int)WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids,
          v29,
          (__int64)"GenerateObjectNameSuffix failed!",
          ObjectNameSuffix);
      }
      v9 = v58;
      goto LABEL_40;
    }
    v9 = v58;
    ObjectNameSuffix = CFbrProcessor::GenerateObjectName(this, v58, (unsigned __int16 **)&lpName);
    if ( ObjectNameSuffix < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v30 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          47,
          (unsigned int)WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids,
          v30,
          (__int64)"GenerateObjectName failed!",
          ObjectNameSuffix);
      }
      v11 = (WCHAR *)lpName;
      goto LABEL_40;
    }
    v11 = (WCHAR *)lpName;
    MutexW = CreateMutexW(0, 0, lpName);
    *((_QWORD *)this + 15) = MutexW;
    if ( !MutexW )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v32 = GetLastError();
        v22 = v32;
        if ( v32 > 0 )
          v22 = (unsigned __int16)v32 | 0x80070000;
        v23 = RdpWppGetCurrentThreadActivityIdPrefix();
        v24 = 48;
        goto LABEL_59;
      }
LABEL_60:
      v25 = GetLastError();
      ObjectNameSuffix = v25;
      if ( v25 > 0 )
        ObjectNameSuffix = (unsigned __int16)v25 | 0x80070000;
      goto LABEL_40;
    }
    ObjectNameSuffix = CFbrProcessor::AddSidToObjectsSecurityDescriptor(this, MutexW, SE_KERNEL_OBJECT, v63, 0x100000u);
    if ( ObjectNameSuffix < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      v27 = RdpWppGetCurrentThreadActivityIdPrefix();
      v28 = 49;
      goto LABEL_67;
    }
    ObjectNameSuffix = CFbrProcessor::GenerateObjectNameSuffix(v33, &v60);
    if ( ObjectNameSuffix < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v34 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          (unsigned int)WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids,
          v34,
          (__int64)"GenerateObjectNameSuffix failed!",
          ObjectNameSuffix);
      }
      v35 = v60;
      goto LABEL_115;
    }
    v35 = v60;
    ObjectNameSuffix = CFbrProcessor::GenerateObjectName(this, v60, (unsigned __int16 **)&v61);
    if ( ObjectNameSuffix < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v36 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          (unsigned int)WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids,
          v36,
          (__int64)"GenerateObjectName failed!",
          ObjectNameSuffix);
      }
      v10 = (void *)v61;
      goto LABEL_115;
    }
    Block = (void *)v61;
    v37 = 4 * v56[0] * a4;
    FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, v37 + dwFileOffsetLow[0], v61);
    *((_QWORD *)this + 13) = FileMappingW;
    if ( !FileMappingW )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v39 = GetLastError();
        v40 = v39;
        if ( v39 > 0 )
          v40 = (unsigned __int16)v39 | 0x80070000;
        v41 = RdpWppGetCurrentThreadActivityIdPrefix();
        v42 = 52;
LABEL_111:
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v42, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids, v41, v40);
        goto LABEL_112;
      }
      goto LABEL_112;
    }
    ObjectNameSuffix = CFbrProcessor::AddSidToObjectsSecurityDescriptor(this, FileMappingW, SE_KERNEL_OBJECT, v63, 6u);
    if ( ObjectNameSuffix >= 0 )
    {
      v45 = (unsigned __int8 *)MapViewOfFile(*((HANDLE *)this + 13), 2u, 0, dwFileOffsetLow[0], v37);
      *((_QWORD *)this + 21) = v45;
      if ( !v45 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v46 = GetLastError();
          v40 = v46;
          if ( v46 > 0 )
            v40 = (unsigned __int16)v46 | 0x80070000;
          v41 = RdpWppGetCurrentThreadActivityIdPrefix();
          v42 = 54;
          goto LABEL_111;
        }
LABEL_112:
        v43 = GetLastError();
        ObjectNameSuffix = v43;
        if ( v43 > 0 )
          ObjectNameSuffix = (unsigned __int16)v43 | 0x80070000;
        goto LABEL_114;
      }
      if ( !PixelMap::Attach((CFbrProcessor *)((char *)this + 136), v45, v37, a4, v56[0], 4 * a4, 32, 0, 0, a4, v56[0]) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v47 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            55,
            WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids,
            v47,
            -2147418113);
        }
        ObjectNameSuffix = -2147418113;
        goto LABEL_114;
      }
      v48 = MapViewOfFile(*((HANDLE *)this + 13), 2u, 0, 0, 0x10u);
      *((_QWORD *)this + 16) = v48;
      if ( !v48 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v49 = GetLastError();
          v40 = v49;
          if ( v49 > 0 )
            v40 = (unsigned __int16)v49 | 0x80070000;
          v41 = RdpWppGetCurrentThreadActivityIdPrefix();
          v42 = 56;
          goto LABEL_111;
        }
        goto LABEL_112;
      }
      v50 = v56[0];
      *(_QWORD *)v48 = 0;
      v48[2] = a4;
      v48[3] = v50;
      v51 = *((_QWORD *)this + 16);
      v52 = v62;
      *(_DWORD *)(v51 + 16) = 40;
      *(_DWORD *)(v51 + 20) = a4;
      *(_DWORD *)(v51 + 24) = v52;
      *(_QWORD *)(v51 + 28) = 2097153;
      *(_OWORD *)(v51 + 36) = 0;
      *(_DWORD *)(v51 + 52) = 0;
      v53 = v65;
      *((_DWORD *)this + 44) = 1;
      *((_DWORD *)this + 23) = 1;
      *v53 = v54;
      v17 = 0;
      *v66 = v9;
      v9 = 0;
      *v67 = v35;
      v35 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_114;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v44 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          53,
          (unsigned int)WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids,
          v44,
          (__int64)"AddSidToObjectsSecurityDescriptor failed!",
          ObjectNameSuffix);
LABEL_114:
        v10 = Block;
LABEL_115:
        v17 = v54;
LABEL_116:
        if ( v35 )
          operator delete(v35);
        v12 = v57;
        goto LABEL_41;
      }
      v17 = v54;
    }
    v10 = Block;
    goto LABEL_116;
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_40;
  }
  v27 = RdpWppGetCurrentThreadActivityIdPrefix();
  v28 = 45;
LABEL_67:
  WPP_SF_DsD(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v28,
    (unsigned int)WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids,
    v27,
    (__int64)"AddSidToObjectsSecurityDescriptor failed!",
    ObjectNameSuffix);
LABEL_40:
  v17 = v54;
LABEL_41:
  if ( v17 )
    operator delete(v17);
  if ( v9 )
    operator delete(v9);
  if ( v10 )
    operator delete(v10);
  if ( v12 )
    operator delete(v12);
  if ( v11 )
    operator delete(v11);
  return (unsigned int)ObjectNameSuffix;
}

```

## disassembly

```asm
0x180078cd0  mov     rax, rsp
0x180078cd3  push    rbp
0x180078cd4  push    rbx
0x180078cd5  push    rsi
0x180078cd6  push    rdi
0x180078cd7  push    r12
0x180078cd9  push    r13
0x180078cdb  push    r14
0x180078cdd  push    r15
0x180078cdf  lea     rbp, [rax-58h]
0x180078ce3  sub     rsp, 118h
0x180078cea  mov     rdi, rcx
0x180078ced  movaps  xmmword ptr [rax-58h], xmm6
0x180078cf1  mov     rcx, [rbp+50h+arg_20]
0x180078cf8  xorps   xmm0, xmm0
0x180078cfb  mov     [rbp+50h+var_88], rcx
0x180078cff  mov     eax, r8d
0x180078d02  mov     rcx, [rbp+50h+arg_28]
0x180078d09  mov     r13d, r9d
0x180078d0c  mov     [rbp+50h+var_90], rcx
0x180078d10  mov     rcx, [rbp+50h+arg_30]
0x180078d17  mov     [rbp+50h+var_98], rcx
0x180078d1b  xor     ecx, ecx
0x180078d1d  mov     r14d, ecx
0x180078d20  mov     [rsp+150h+var_E0], eax
0x180078d24  mov     r15d, ecx
0x180078d27  mov     [rbp+50h+var_A8], rdx
0x180078d2b  mov     r12d, ecx
0x180078d2e  mov     [rbp+50h+var_C0], rcx
0x180078d32  mov     esi, ecx
0x180078d34  mov     [rbp+50h+var_D0], rcx
0x180078d38  mov     [rsp+150h+Block], rcx
0x180078d3d  mov     [rbp+50h+var_B8], rcx
0x180078d41  mov     [rbp+50h+lpName], rcx
0x180078d45  mov     [rsp+150h+var_D8], rcx
0x180078d4a  movups  xmmword ptr [rbp+50h+SystemInfo], xmm0
0x180078d4e  movups  xmmword ptr [rbp+50h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180078d52  movups  xmmword ptr [rbp-10h], xmm0
0x180078d56  cmp     [rdi+70h], rcx
0x180078d5a  jz      short loc_180078DAF
0x180078d5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180078d63  lea     rax, WPP_GLOBAL_Control
0x180078d6a  cmp     rcx, rax
0x180078d6d  jz      short loc_180078DA5
0x180078d6f  test    byte ptr [rcx+1Ch], 8
0x180078d73  jz      short loc_180078DA5
0x180078d75  cmp     byte ptr [rcx+19h], 2
0x180078d79  jb      short loc_180078DA5
0x180078d7b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078d80  lea     edx, [rsi+25h]
0x180078d83  mov     rcx, cs:WPP_GLOBAL_Control
0x180078d8a  lea     r8, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids
0x180078d91  mov     r9d, eax
0x180078d94  mov     [rsp+150h+dwMaximumSizeLow], 8000FFFFh
0x180078d9c  mov     rcx, [rcx+10h]
0x180078da0  call    WPP_SF_Dd
0x180078da5  mov     ebx, 8000FFFFh
0x180078daa  jmp     loc_180078FF0
0x180078daf  cmp     [rdi+78h], rcx
0x180078db3  jz      short loc_180078DE0
0x180078db5  mov     rcx, cs:WPP_GLOBAL_Control
0x180078dbc  lea     rax, WPP_GLOBAL_Control
0x180078dc3  cmp     rcx, rax
0x180078dc6  jz      short loc_180078DA5
0x180078dc8  test    byte ptr [rcx+1Ch], 8
0x180078dcc  jz      short loc_180078DA5
0x180078dce  cmp     byte ptr [rcx+19h], 2
0x180078dd2  jb      short loc_180078DA5
0x180078dd4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078dd9  mov     edx, 26h ; '&'
0x180078dde  jmp     short loc_180078D83
0x180078de0  cmp     [rdi+68h], rcx
0x180078de4  jz      short loc_180078E14
0x180078de6  mov     rcx, cs:WPP_GLOBAL_Control
0x180078ded  lea     rax, WPP_GLOBAL_Control
0x180078df4  cmp     rcx, rax
0x180078df7  jz      short loc_180078DA5
0x180078df9  test    byte ptr [rcx+1Ch], 8
0x180078dfd  jz      short loc_180078DA5
0x180078dff  cmp     byte ptr [rcx+19h], 2
0x180078e03  jb      short loc_180078DA5
0x180078e05  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078e0a  mov     edx, 27h ; '''
0x180078e0f  jmp     loc_180078D83
0x180078e14  cmp     [rdi+80h], rcx
0x180078e1b  jz      short loc_180078E57
0x180078e1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180078e24  lea     rax, WPP_GLOBAL_Control
0x180078e2b  cmp     rcx, rax
0x180078e2e  jz      loc_180078DA5
0x180078e34  test    byte ptr [rcx+1Ch], 8
0x180078e38  jz      loc_180078DA5
0x180078e3e  cmp     byte ptr [rcx+19h], 2
0x180078e42  jb      loc_180078DA5
0x180078e48  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078e4d  mov     edx, 28h ; '('
0x180078e52  jmp     loc_180078D83
0x180078e57  cmp     [rdi+0A8h], rcx
0x180078e5e  jz      short loc_180078E9A
0x180078e60  mov     rcx, cs:WPP_GLOBAL_Control
0x180078e67  lea     rax, WPP_GLOBAL_Control
0x180078e6e  cmp     rcx, rax
0x180078e71  jz      loc_180078DA5
0x180078e77  test    byte ptr [rcx+1Ch], 8
0x180078e7b  jz      loc_180078DA5
0x180078e81  cmp     byte ptr [rcx+19h], 2
0x180078e85  jb      loc_180078DA5
0x180078e8b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078e90  mov     edx, 29h ; ')'
0x180078e95  jmp     loc_180078D83
0x180078e9a  neg     eax
0x180078e9c  lea     rcx, [rbp+50h+SystemInfo]; lpSystemInfo
0x180078ea0  mov     [rbp+50h+var_B0], eax
0x180078ea3  xorps   xmm6, xmm6
0x180078ea6  call    cs:__imp_GetSystemInfo
0x180078eac  mov     ecx, [rbp+50h+SystemInfo.dwAllocationGranularity]; this
0x180078eaf  xor     edx, edx
0x180078eb1  lea     eax, [rdx+38h]
0x180078eb4  div     rcx
0x180078eb7  lea     rdx, [rsp+150h+Block]; unsigned __int16 **
0x180078ebc  inc     eax
0x180078ebe  imul    eax, [rbp+50h+SystemInfo.dwAllocationGranularity]
0x180078ec2  mov     qword ptr [rbp+50h+dwFileOffsetLow], rax
0x180078ec6  call    ?GenerateObjectNameSuffix@CFbrProcessor@@IEAAJPEAPEAG@Z; CFbrProcessor::GenerateObjectNameSuffix(ushort * *)
0x180078ecb  mov     ebx, eax
0x180078ecd  test    eax, eax
0x180078ecf  jns     short loc_180078F2E
0x180078ed1  mov     rcx, cs:WPP_GLOBAL_Control
0x180078ed8  lea     rax, WPP_GLOBAL_Control
0x180078edf  cmp     rcx, rax
0x180078ee2  jz      short loc_180078F24
0x180078ee4  test    byte ptr [rcx+1Ch], 8
0x180078ee8  jz      short loc_180078F24
0x180078eea  cmp     byte ptr [rcx+19h], 2
0x180078eee  jb      short loc_180078F24
0x180078ef0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078ef5  lea     rcx, aGenerateobject; "GenerateObjectNameSuffix failed!"
0x180078efc  mov     dword ptr [rsp+150h+var_128], ebx
0x180078f00  mov     qword ptr [rsp+150h+dwMaximumSizeLow], rcx
0x180078f05  lea     r8, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids
0x180078f0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180078f13  mov     edx, 2Ah ; '*'
0x180078f18  mov     r9d, eax
0x180078f1b  mov     rcx, [rcx+10h]
0x180078f1f  call    WPP_SF_DsD
0x180078f24  mov     rdi, [rsp+150h+Block]
0x180078f29  jmp     loc_180078FAF
0x180078f2e  mov     rax, [rsp+150h+Block]
0x180078f33  lea     r8, [rsp+150h+var_D8]; unsigned __int16 **
0x180078f38  mov     rdx, rax; unsigned __int16 *
0x180078f3b  mov     [rsp+150h+var_F0], rax
0x180078f40  mov     rcx, rdi; this
0x180078f43  call    ?GenerateObjectName@CFbrProcessor@@IEAAJPEBGPEAPEAG@Z; CFbrProcessor::GenerateObjectName(ushort const *,ushort * *)
0x180078f48  mov     ebx, eax
0x180078f4a  test    eax, eax
0x180078f4c  jns     loc_18007900E
0x180078f52  mov     rcx, cs:WPP_GLOBAL_Control
0x180078f59  lea     rax, WPP_GLOBAL_Control
0x180078f60  cmp     rcx, rax
0x180078f63  jz      short loc_180078FA5
0x180078f65  test    byte ptr [rcx+1Ch], 8
0x180078f69  jz      short loc_180078FA5
0x180078f6b  cmp     byte ptr [rcx+19h], 2
0x180078f6f  jb      short loc_180078FA5
0x180078f71  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078f76  lea     rcx, aGenerateobject_0; "GenerateObjectName failed!"
0x180078f7d  mov     dword ptr [rsp+150h+var_128], ebx
0x180078f81  mov     qword ptr [rsp+150h+dwMaximumSizeLow], rcx
0x180078f86  lea     r8, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids
0x180078f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180078f94  mov     edx, 2Bh ; '+'
0x180078f99  mov     r9d, eax
0x180078f9c  mov     rcx, [rcx+10h]
0x180078fa0  call    WPP_SF_DsD
0x180078fa5  mov     rsi, [rsp+150h+var_D8]
0x180078faa  mov     rdi, [rsp+150h+var_F0]
0x180078faf  test    rdi, rdi
0x180078fb2  jz      short loc_180078FBC
0x180078fb4  mov     rcx, rdi; Block
0x180078fb7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180078fbc  test    r14, r14
0x180078fbf  jz      short loc_180078FC9
0x180078fc1  mov     rcx, r14; Block
0x180078fc4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180078fc9  test    r15, r15
0x180078fcc  jz      short loc_180078FD6
0x180078fce  mov     rcx, r15; Block
0x180078fd1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180078fd6  test    rsi, rsi
0x180078fd9  jz      short loc_180078FE3
0x180078fdb  mov     rcx, rsi; Block
0x180078fde  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180078fe3  test    r12, r12
0x180078fe6  jz      short loc_180078FF0
0x180078fe8  mov     rcx, r12; Block
0x180078feb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180078ff0  movaps  xmm6, xmmword ptr [rsp+100h]
0x180078ff8  mov     eax, ebx
0x180078ffa  add     rsp, 118h
0x180079001  pop     r15
0x180079003  pop     r14
0x180079005  pop     r13
0x180079007  pop     r12
0x180079009  pop     rdi
0x18007900a  pop     rsi
0x18007900b  pop     rbx
0x18007900c  pop     rbp
0x18007900d  retn
0x18007900e  mov     rsi, [rsp+150h+var_D8]
0x180079013  xor     r8d, r8d; bInitialState
0x180079016  mov     r9, rsi; lpName
0x180079019  mov     [rsp+150h+var_D8], rsi
0x18007901e  xor     edx, edx; bManualReset
0x180079020  xor     ecx, ecx; lpEventAttributes
0x180079022  call    cs:__imp_CreateEventW
0x180079028  mov     [rdi+70h], rax
0x18007902c  test    rax, rax
0x18007902f  jnz     short loc_1800790A8
0x180079031  mov     rcx, cs:WPP_GLOBAL_Control
0x180079038  lea     rax, WPP_GLOBAL_Control
0x18007903f  mov     edi, 80070000h
0x180079044  cmp     rcx, rax
0x180079047  jz      short loc_18007908E
0x180079049  test    byte ptr [rcx+1Ch], 8
0x18007904d  jz      short loc_18007908E
0x18007904f  cmp     byte ptr [rcx+19h], 2
0x180079053  jb      short loc_18007908E
0x180079055  call    cs:__imp_GetLastError
0x18007905b  mov     ebx, eax
0x18007905d  test    eax, eax
0x18007905f  jle     short loc_180079066
0x180079061  movzx   ebx, ax
0x180079064  or      ebx, edi
0x180079066  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007906b  mov     edx, 2Ch ; ','
0x180079070  mov     rcx, cs:WPP_GLOBAL_Control
0x180079077  lea     r8, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids
0x18007907e  mov     r9d, eax
0x180079081  mov     [rsp+150h+dwMaximumSizeLow], ebx
0x180079085  mov     rcx, [rcx+10h]
0x180079089  call    WPP_SF_Dd
0x18007908e  call    cs:__imp_GetLastError
0x180079094  mov     ebx, eax
0x180079096  test    eax, eax
0x180079098  jle     loc_180078FAA
0x18007909e  movzx   ebx, ax
0x1800790a1  or      ebx, edi
0x1800790a3  jmp     loc_180078FAA
0x1800790a8  mov     r9, [rbp+50h+var_A8]; void *
0x1800790ac  mov     r8d, 6; enum _SE_OBJECT_TYPE
0x1800790b2  mov     rdx, rax; void *
0x1800790b5  mov     [rsp+150h+dwMaximumSizeLow], 100000h; unsigned int
0x1800790bd  mov     rcx, rdi; this
0x1800790c0  call    ?AddSidToObjectsSecurityDescriptor@CFbrProcessor@@IEAAJPEAXW4_SE_OBJECT_TYPE@@0K@Z; CFbrProcessor::AddSidToObjectsSecurityDescriptor(void *,_SE_OBJECT_TYPE,void *,ulong)
0x1800790c5  mov     ebx, eax
0x1800790c7  test    eax, eax
0x1800790c9  jns     short loc_18007912F
0x1800790cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800790d2  lea     rax, WPP_GLOBAL_Control
0x1800790d9  cmp     rcx, rax
0x1800790dc  jz      loc_180078FAA
0x1800790e2  test    byte ptr [rcx+1Ch], 8
0x1800790e6  jz      loc_180078FAA
0x1800790ec  cmp     byte ptr [rcx+19h], 2
0x1800790f0  jb      loc_180078FAA
0x1800790f6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800790fb  mov     edx, 2Dh ; '-'
0x180079100  lea     rcx, aAddsidtoobject; "AddSidToObjectsSecurityDescriptor faile"...
0x180079107  mov     dword ptr [rsp+150h+var_128], ebx
0x18007910b  mov     qword ptr [rsp+150h+dwMaximumSizeLow], rcx
0x180079110  lea     r8, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids
0x180079117  mov     rcx, cs:WPP_GLOBAL_Control
0x18007911e  mov     r9d, eax
0x180079121  mov     rcx, [rcx+10h]
0x180079125  call    WPP_SF_DsD
0x18007912a  jmp     loc_180078FAA
0x18007912f  lea     rdx, [rbp+50h+var_D0]; unsigned __int16 **
0x180079133  call    ?GenerateObjectNameSuffix@CFbrProcessor@@IEAAJPEAPEAG@Z; CFbrProcessor::GenerateObjectNameSuffix(ushort * *)
0x180079138  mov     ebx, eax
0x18007913a  test    eax, eax
0x18007913c  jns     short loc_18007919A
0x18007913e  mov     rcx, cs:WPP_GLOBAL_Control
0x180079145  lea     rax, WPP_GLOBAL_Control
0x18007914c  cmp     rcx, rax
0x18007914f  jz      short loc_180079191
0x180079151  test    byte ptr [rcx+1Ch], 8
0x180079155  jz      short loc_180079191
0x180079157  cmp     byte ptr [rcx+19h], 2
0x18007915b  jb      short loc_180079191
0x18007915d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079162  lea     rcx, aGenerateobject; "GenerateObjectNameSuffix failed!"
0x180079169  mov     dword ptr [rsp+150h+var_128], ebx
0x18007916d  mov     qword ptr [rsp+150h+dwMaximumSizeLow], rcx
0x180079172  lea     r8, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids
0x180079179  mov     rcx, cs:WPP_GLOBAL_Control
0x180079180  mov     edx, 2Eh ; '.'
0x180079185  mov     r9d, eax
0x180079188  mov     rcx, [rcx+10h]
0x18007918c  call    WPP_SF_DsD
0x180079191  mov     r14, [rbp+50h+var_D0]
  ... truncated ...
```
