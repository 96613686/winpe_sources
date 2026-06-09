# FAX_SetActivityLoggingConfiguration

- ea: `0x14001ee40`
- end: `0x14001f817`
- name: `FAX_SetActivityLoggingConfiguration`
- size: `2519`
- prototype: `__int64 __fastcall(void *, int *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x140004f64`
- `0x1400154a0`
- `0x14001ee40`
- `0x140028d5c`
- `0x14002e3d4`
- `0x140047d20`
- `0x140051e70`
- `0x1400589ac`
- `0x14006998c`
- `0x140071b38`
- `0x140072490`
- `0x1400728bc`
- `0x14007a1b8`
- `0x1400840c8`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001f300`
- `KERNEL32!GetLastError` at `0x14001f41e`
- `KERNEL32!GetLastError` at `0x14001f487`
- `KERNEL32!GetLastError` at `0x14001f589`
- `KERNEL32!GetLastError` at `0x14001f640`
- `KERNEL32!GetLastError` at `0x14001f696`
- `KERNEL32!GetLastError` at `0x14001f766`
- `KERNEL32!GetLastError` at `0x14001f300`
- `KERNEL32!GetLastError` at `0x14001f41e`
- `KERNEL32!GetLastError` at `0x14001f487`
- `KERNEL32!GetLastError` at `0x14001f589`
- `KERNEL32!GetLastError` at `0x14001f640`
- `KERNEL32!GetLastError` at `0x14001f696`
- `KERNEL32!GetLastError` at `0x14001f766`
- `KERNEL32!CloseHandle` at `0x14001f3ef`
- `KERNEL32!CloseHandle` at `0x14001f45f`
- `KERNEL32!CloseHandle` at `0x14001f561`
- `KERNEL32!CloseHandle` at `0x14001f66e`
- `KERNEL32!CloseHandle` at `0x14001f3ef`
- `KERNEL32!CloseHandle` at `0x14001f45f`
- `KERNEL32!CloseHandle` at `0x14001f561`
- `KERNEL32!CloseHandle` at `0x14001f66e`
- `KERNEL32!DeleteFileW` at `0x14001f618`
- `KERNEL32!DeleteFileW` at `0x14001f72e`
- `KERNEL32!DeleteFileW` at `0x14001f618`
- `KERNEL32!DeleteFileW` at `0x14001f72e`
- `KERNEL32!EnterCriticalSection` at `0x14001f05a`
- `KERNEL32!EnterCriticalSection` at `0x14001f06d`
- `KERNEL32!EnterCriticalSection` at `0x14001f05a`
- `KERNEL32!EnterCriticalSection` at `0x14001f06d`
- `KERNEL32!LeaveCriticalSection` at `0x14001f530`
- `KERNEL32!LeaveCriticalSection` at `0x14001f543`
- `KERNEL32!LeaveCriticalSection` at `0x14001f530`
- `KERNEL32!LeaveCriticalSection` at `0x14001f543`

## pseudocode

```c
__int64 __fastcall FAX_SetActivityLoggingConfiguration(void *a1, int *a2)
{
  __int64 v2; // r12
  __int64 v3; // r13
  int v6; // esi
  CMapDeviceId *v7; // rcx
  int v8; // ebx
  __m128i v9; // xmm0
  const WCHAR *v10; // xmm1_8
  const WCHAR *v11; // rax
  __int64 v12; // r9
  __int64 v13; // r8
  unsigned int v14; // ebx
  CMapDeviceId *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned int valid; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  int v22; // r15d
  __m128i *p_Mem; // r14
  unsigned int v24; // eax
  DWORD v25; // eax
  unsigned int ConfigEvent; // eax
  CMapDeviceId *v27; // rcx
  __int64 v28; // rdx
  DWORD v29; // eax
  DWORD v30; // eax
  DWORD LastError; // eax
  int v32; // eax
  DWORD v33; // eax
  DWORD v34; // eax
  int v35; // eax
  DWORD v36; // eax
  __m128i Mem; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpPathName; // [rsp+40h] [rbp-C0h]
  int v39; // [rsp+48h] [rbp-B8h] BYREF
  int v40; // [rsp+4Ch] [rbp-B4h]
  void *v41; // [rsp+50h] [rbp-B0h] BYREF
  void *v42; // [rsp+58h] [rbp-A8h] BYREF
  __m128i *v43; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v44[4]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v45; // [rsp+78h] [rbp-88h]
  WCHAR FileName[520]; // [rsp+80h] [rbp-80h] BYREF

  v2 = -1;
  v41 = (void *)-1LL;
  v3 = -1;
  v42 = (void *)-1LL;
  v39 = 0;
  lpPathName = 0;
  v40 = 0;
  v43 = 0;
  v6 = 0;
  Mem = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 305, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( *a2 != 24 )
  {
    v8 = *a2;
    if ( (unsigned int)GetWin32StructSize(&fax_activity_logging_config_fields) != v8 )
      return 87;
    v7 = WPP_GLOBAL_Control;
  }
  v9 = *(__m128i *)a2;
  v10 = (const WCHAR *)*((_QWORD *)a2 + 2);
  lpPathName = v10;
  Mem = v9;
  if ( !v9.m128i_i32[1] && !_mm_cvtsi128_si32(_mm_srli_si128(v9, 8)) )
    goto LABEL_18;
  if ( !v10 || !*v10 )
  {
    if ( v7 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 && *((_BYTE *)v7 + 25) >= 2u )
      WPP_SF_(*((_QWORD *)v7 + 2), 306, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    return 87;
  }
  v11 = v10;
  v12 = 249;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v12;
  }
  while ( v12 );
  v13 = (249 - v12) & -(__int64)(v12 != 0);
  if ( v12 )
  {
    if ( v10[v13 - 1] == 92 )
      v10[v13 - 1] = 0;
LABEL_18:
    v14 = FaxSvcAccessCheck(0x40u, &v39, 0, 1);
    if ( v14 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_24;
      }
      v16 = 308;
      v17 = v14;
      goto LABEL_23;
    }
    if ( !v39 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 309, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
      }
      return 5;
    }
    EnterCriticalSection(&g_CsInboundActivityLogging);
    EnterCriticalSection(&g_CsOutboundActivityLogging);
    if ( *(__int64 *)((char *)Mem.m128i_i64 + 4) )
    {
      if ( !(unsigned int)PathRepresentsFullPath((wchar_t *)lpPathName) )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            310,
            &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
            lpPathName);
        }
        v14 = 87;
        goto LABEL_112;
      }
      valid = IsValidFaxFolder((unsigned __int16 *)lpPathName);
      v14 = valid;
      if ( valid )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            311,
            (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
            (_DWORD)lpPathName,
            valid);
        }
        if ( v14 == 5 && FindClientAPIVersion(a1) >= 0x10000 )
          goto LABEL_48;
LABEL_112:
        LeaveCriticalSection(&g_CsOutboundActivityLogging);
        LeaveCriticalSection(&g_CsInboundActivityLogging);
        if ( v2 == -1 && v3 == -1 )
          goto LABEL_24;
        if ( !CloseHandle((HANDLE)v2)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            321,
            &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
            LastError);
        }
        v32 = StringCchPrintfW(FileName, 0x208u, L"%s\\%s", lpPathName, L"InboxLOG.txt");
        if ( v32 >= 0 )
        {
          if ( !DeleteFileW(FileName)
            && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v33 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 323, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v33);
          }
        }
        else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            322,
            &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
            (unsigned int)v32);
        }
        if ( !CloseHandle((HANDLE)v3)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v34 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 324, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v34);
        }
        v35 = StringCchPrintfW(FileName, 0x208u, L"%s\\%s", lpPathName, L"OutboxLOG.txt");
        if ( v35 < 0 )
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              325,
              &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
              (unsigned int)v35);
          }
          goto LABEL_24;
        }
        if ( DeleteFileW(FileName)
          || WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_24:
          if ( v14 == 8 || v14 == 14 )
            return 7001;
          return v14;
        }
        v36 = GetLastError();
        v15 = WPP_GLOBAL_Control;
        v16 = 326;
        v17 = v36;
LABEL_23:
        WPP_SF_d(*((_QWORD *)v15 + 2), v16, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v17);
        goto LABEL_24;
      }
      v20 = CheckToSeeIfSameDir(lpPathName, *(wchar_t **)&fDesiredAccess);
      v14 = v20;
      if ( v20 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 312, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v20);
        }
        goto LABEL_61;
      }
      v6 = v40;
      if ( !v40 )
      {
        v21 = CreateLogDB(lpPathName, &v41, &v42);
        v14 = v21;
        if ( v21 )
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 313, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v21);
          }
          v3 = (__int64)v42;
          v2 = (__int64)v41;
LABEL_61:
          if ( v14 != 5 && v14 != 32 )
            goto LABEL_112;
LABEL_48:
          v14 = 7008;
          goto LABEL_112;
        }
        v2 = (__int64)v41;
        v3 = (__int64)v42;
      }
    }
    v22 = ContractConfigurationFolder(&Mem, &v43);
    if ( v22 )
    {
      p_Mem = v43;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 314, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
      }
      p_Mem = &Mem;
    }
    v24 = StoreActivityLoggingSettings(p_Mem);
    v14 = v24;
    if ( v24 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 315, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v24);
      }
      v14 = 1015;
      goto LABEL_110;
    }
    if ( *(__int64 *)((char *)Mem.m128i_i64 + 4) )
    {
      if ( !ReplaceStringWithCopy((unsigned __int16 **)&fDesiredAccess, lpPathName) )
      {
        v25 = GetLastError();
        v14 = v25;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 316, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v25);
        }
        v44[1] = *(&g_ActivityLoggingConfig + 1);
        v44[2] = *(&g_ActivityLoggingConfig + 2);
        v45 = *(_QWORD *)&fDesiredAccess;
        v44[3] = 0;
        v44[0] = 24;
        ConfigEvent = StoreActivityLoggingSettings(v44);
        if ( !ConfigEvent )
          goto LABEL_110;
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_110;
        }
        v28 = 317;
        goto LABEL_89;
      }
      if ( *(__int64 *)((char *)Mem.m128i_i64 + 4) && !v6 )
      {
        if ( g_hInboxActivityLogFile != (HANDLE)-1LL
          && !CloseHandle(g_hInboxActivityLogFile)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v29 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 318, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v29);
        }
        if ( g_hOutboxActivityLogFile != (HANDLE)-1LL
          && !CloseHandle(g_hOutboxActivityLogFile)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v30 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 319, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v30);
        }
        g_hInboxActivityLogFile = (HANDLE)v2;
        g_hOutboxActivityLogFile = (HANDLE)v3;
        v2 = -1;
        v3 = -1;
      }
    }
    *(_QWORD *)((char *)&g_ActivityLoggingConfig + 4) = *(__int64 *)((char *)Mem.m128i_i64 + 4);
    ConfigEvent = CreateConfigEvent(1);
    if ( !ConfigEvent
      || (v27 = WPP_GLOBAL_Control, WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control)
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_110:
      if ( v22 )
        pMemFree(p_Mem);
      goto LABEL_112;
    }
    v28 = 320;
LABEL_89:
    WPP_SF_d(*((_QWORD *)v27 + 2), v28, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, ConfigEvent);
    goto LABEL_110;
  }
  if ( v7 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 && *((_BYTE *)v7 + 25) >= 2u )
    WPP_SF_(*((_QWORD *)v7 + 2), 307, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  return 111;
}

```

## disassembly

```asm
0x14001ee40  mov     [rsp-8+arg_10], rbx
0x14001ee45  push    rbp
0x14001ee46  push    rsi
0x14001ee47  push    rdi
0x14001ee48  push    r12
0x14001ee4a  push    r13
0x14001ee4c  push    r14
0x14001ee4e  push    r15
0x14001ee50  lea     rbp, [rsp-3A0h]
0x14001ee58  sub     rsp, 4A0h
0x14001ee5f  mov     rax, cs:__security_cookie
0x14001ee66  xor     rax, rsp
0x14001ee69  mov     [rbp+3D0h+var_40], rax
0x14001ee70  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001ee74  xor     r15d, r15d
0x14001ee77  mov     r12, rax
0x14001ee7a  mov     [rsp+4D0h+var_480], rax
0x14001ee7f  mov     r13, rax
0x14001ee82  mov     [rsp+4D0h+var_478], rax
0x14001ee87  xor     eax, eax
0x14001ee89  mov     [rsp+4D0h+var_488], r15d
0x14001ee8e  xorps   xmm0, xmm0
0x14001ee91  mov     [rsp+4D0h+lpPathName], rax
0x14001ee96  mov     rdi, rdx
0x14001ee99  mov     [rsp+4D0h+var_484], r15d
0x14001ee9e  mov     r14, rcx
0x14001eea1  mov     [rsp+4D0h+var_470], r15
0x14001eea6  mov     esi, r15d
0x14001eea9  movups  [rsp+4D0h+Mem], xmm0
0x14001eeae  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eeb5  lea     rax, WPP_GLOBAL_Control
0x14001eebc  cmp     rcx, rax
0x14001eebf  jz      short loc_14001EEE9
0x14001eec1  test    byte ptr [rcx+1Ch], 4
0x14001eec5  jz      short loc_14001EEE9
0x14001eec7  cmp     byte ptr [rcx+19h], 5
0x14001eecb  jb      short loc_14001EEE9
0x14001eecd  mov     rcx, [rcx+10h]
0x14001eed1  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001eed8  mov     edx, 131h
0x14001eedd  call    WPP_SF_
0x14001eee2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eee9  mov     ebx, [rdi]
0x14001eeeb  cmp     ebx, 18h
0x14001eeee  jz      short loc_14001EF0B
0x14001eef0  lea     rcx, ?fax_activity_logging_config_fields@@3PAU_FieldInfo@@A; _FieldInfo near * fax_activity_logging_config_fields
0x14001eef7  call    GetWin32StructSize
0x14001eefc  cmp     eax, ebx
0x14001eefe  jnz     loc_14001F7E7
0x14001ef04  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ef0b  movups  xmm0, xmmword ptr [rdi]
0x14001ef0e  movsd   xmm1, qword ptr [rdi+10h]
0x14001ef13  mov     edi, 2
0x14001ef18  movq    rax, xmm0
0x14001ef1d  movsd   [rsp+4D0h+lpPathName], xmm1
0x14001ef23  shr     rax, 20h
0x14001ef27  movups  [rsp+4D0h+Mem], xmm0
0x14001ef2c  test    eax, eax
0x14001ef2e  jnz     short loc_14001EF3D
0x14001ef30  psrldq  xmm0, 8
0x14001ef35  movd    eax, xmm0
0x14001ef39  test    eax, eax
0x14001ef3b  jz      short loc_14001EFA4
0x14001ef3d  movq    rdx, xmm1
0x14001ef42  test    rdx, rdx
0x14001ef45  jz      loc_14001F7BA
0x14001ef4b  cmp     [rdx], r15w
0x14001ef4f  jz      loc_14001F7BA
0x14001ef55  test    rdx, rdx
0x14001ef58  jz      loc_14001F786
0x14001ef5e  mov     r10d, 0F9h
0x14001ef64  mov     rax, rdx
0x14001ef67  mov     r9d, r10d
0x14001ef6a  cmp     [rax], r15w
0x14001ef6e  jz      short loc_14001EF79
0x14001ef70  add     rax, rdi
0x14001ef73  sub     r9, 1
0x14001ef77  jnz     short loc_14001EF6A
0x14001ef79  sub     r10, r9
0x14001ef7c  mov     rax, r9
0x14001ef7f  neg     rax
0x14001ef82  sbb     r8, r8
0x14001ef85  and     r8, r10
0x14001ef88  test    r9, r9
0x14001ef8b  jz      loc_14001F786
0x14001ef91  mov     eax, 5Ch ; '\'
0x14001ef96  cmp     ax, [rdx+r8*2-2]
0x14001ef9c  jnz     short loc_14001EFA4
0x14001ef9e  mov     [rdx+r8*2-2], r15w
0x14001efa4  mov     r9d, 1; int
0x14001efaa  lea     rdx, [rsp+4D0h+var_488]; int *
0x14001efaf  xor     r8d, r8d; unsigned int *
0x14001efb2  lea     ecx, [r9+3Fh]; unsigned int
0x14001efb6  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14001efbb  mov     ebx, eax
0x14001efbd  test    eax, eax
0x14001efbf  jz      short loc_14001F00E
0x14001efc1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001efc8  lea     rax, WPP_GLOBAL_Control
0x14001efcf  cmp     rcx, rax
0x14001efd2  jz      short loc_14001EFF8
0x14001efd4  test    byte ptr [rcx+1Ch], 4
0x14001efd8  jz      short loc_14001EFF8
0x14001efda  cmp     [rcx+19h], dil
0x14001efde  jb      short loc_14001EFF8
0x14001efe0  mov     edx, 134h
0x14001efe5  mov     r9d, ebx
0x14001efe8  mov     rcx, [rcx+10h]
0x14001efec  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001eff3  call    WPP_SF_d
0x14001eff8  cmp     ebx, 8
0x14001effb  jz      short loc_14001F002
0x14001effd  cmp     ebx, 0Eh
0x14001f000  jnz     short loc_14001F007
0x14001f002  mov     ebx, 1B59h
0x14001f007  mov     eax, ebx
0x14001f009  jmp     loc_14001F7EC
0x14001f00e  cmp     [rsp+4D0h+var_488], r15d
0x14001f013  jnz     short loc_14001F053
0x14001f015  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f01c  lea     rax, WPP_GLOBAL_Control
0x14001f023  cmp     rcx, rax
0x14001f026  jz      short loc_14001F049
0x14001f028  test    byte ptr [rcx+1Ch], 4
0x14001f02c  jz      short loc_14001F049
0x14001f02e  cmp     [rcx+19h], dil
0x14001f032  jb      short loc_14001F049
0x14001f034  mov     rcx, [rcx+10h]
0x14001f038  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001f03f  mov     edx, 135h
0x14001f044  call    WPP_SF_
0x14001f049  mov     eax, 5
0x14001f04e  jmp     loc_14001F7EC
0x14001f053  lea     rcx, ?g_CsInboundActivityLogging@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001f05a  call    cs:__imp_EnterCriticalSection
0x14001f061  nop     dword ptr [rax+rax+00h]
0x14001f066  lea     rcx, ?g_CsOutboundActivityLogging@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001f06d  call    cs:__imp_EnterCriticalSection
0x14001f074  nop     dword ptr [rax+rax+00h]
0x14001f079  cmp     dword ptr [rsp+4D0h+Mem+4], r15d
0x14001f07e  jnz     short loc_14001F08B
0x14001f080  cmp     dword ptr [rsp+4D0h+Mem+8], r15d
0x14001f085  jz      loc_14001F230
0x14001f08b  mov     rcx, [rsp+4D0h+lpPathName]; String1
0x14001f090  call    PathRepresentsFullPath
0x14001f095  test    eax, eax
0x14001f097  jnz     short loc_14001F0DC
0x14001f099  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f0a0  lea     rsi, WPP_GLOBAL_Control
0x14001f0a7  cmp     rcx, rsi
0x14001f0aa  jz      short loc_14001F0D2
0x14001f0ac  test    byte ptr [rcx+1Ch], 4
0x14001f0b0  jz      short loc_14001F0D2
0x14001f0b2  cmp     [rcx+19h], dil
0x14001f0b6  jb      short loc_14001F0D2
0x14001f0b8  mov     r9, [rsp+4D0h+lpPathName]
0x14001f0bd  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001f0c4  mov     rcx, [rcx+10h]
0x14001f0c8  mov     edx, 136h
0x14001f0cd  call    WPP_SF_S
0x14001f0d2  mov     ebx, 57h ; 'W'
0x14001f0d7  jmp     loc_14001F529
0x14001f0dc  mov     rcx, [rsp+4D0h+lpPathName]; unsigned __int16 *
0x14001f0e1  call    IsValidFaxFolder
0x14001f0e6  mov     ebx, eax
0x14001f0e8  test    eax, eax
0x14001f0ea  jz      short loc_14001F14F
0x14001f0ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f0f3  lea     rsi, WPP_GLOBAL_Control
0x14001f0fa  cmp     rcx, rsi
0x14001f0fd  jz      short loc_14001F129
0x14001f0ff  test    byte ptr [rcx+1Ch], 4
0x14001f103  jz      short loc_14001F129
0x14001f105  cmp     [rcx+19h], dil
0x14001f109  jb      short loc_14001F129
0x14001f10b  mov     r9, [rsp+4D0h+lpPathName]
0x14001f110  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001f117  mov     rcx, [rcx+10h]
0x14001f11b  mov     edx, 137h
0x14001f120  mov     dword ptr [rsp+4D0h+var_4B0], eax
0x14001f124  call    WPP_SF_Sd
0x14001f129  cmp     ebx, 5
0x14001f12c  jnz     loc_14001F529
0x14001f132  mov     rcx, r14; void *
0x14001f135  call    ?FindClientAPIVersion@@YAKPEAX@Z; FindClientAPIVersion(void *)
0x14001f13a  cmp     eax, 10000h
0x14001f13f  jb      loc_14001F529
0x14001f145  mov     ebx, 1B60h
0x14001f14a  jmp     loc_14001F529
0x14001f14f  mov     rdx, qword ptr cs:fDesiredAccess; String2
0x14001f156  lea     r8, [rsp+4D0h+var_484]
0x14001f15b  mov     rcx, [rsp+4D0h+lpPathName]; lpPathName
0x14001f160  call    CheckToSeeIfSameDir
0x14001f165  mov     ebx, eax
0x14001f167  test    eax, eax
0x14001f169  jz      short loc_14001F1AC
0x14001f16b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f172  lea     rsi, WPP_GLOBAL_Control
0x14001f179  cmp     rcx, rsi
0x14001f17c  jz      loc_14001F20F
0x14001f182  test    byte ptr [rcx+1Ch], 4
0x14001f186  jz      loc_14001F20F
0x14001f18c  cmp     [rcx+19h], dil
0x14001f190  jb      short loc_14001F20F
0x14001f192  mov     rcx, [rcx+10h]
0x14001f196  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001f19d  mov     edx, 138h
0x14001f1a2  mov     r9d, eax
0x14001f1a5  call    WPP_SF_d
0x14001f1aa  jmp     short loc_14001F20F
0x14001f1ac  mov     esi, [rsp+4D0h+var_484]
0x14001f1b0  test    esi, esi
0x14001f1b2  jnz     short loc_14001F230
0x14001f1b4  mov     rcx, [rsp+4D0h+lpPathName]; unsigned __int16 *
0x14001f1b9  lea     r8, [rsp+4D0h+var_478]; void **
0x14001f1be  lea     rdx, [rsp+4D0h+var_480]; void **
0x14001f1c3  call    ?CreateLogDB@@YAKPEBGPEAPEAX1@Z; CreateLogDB(ushort const *,void * *,void * *)
0x14001f1c8  mov     ebx, eax
0x14001f1ca  test    eax, eax
0x14001f1cc  jz      short loc_14001F226
0x14001f1ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f1d5  lea     rsi, WPP_GLOBAL_Control
0x14001f1dc  cmp     rcx, rsi
0x14001f1df  jz      short loc_14001F205
0x14001f1e1  test    byte ptr [rcx+1Ch], 4
0x14001f1e5  jz      short loc_14001F205
0x14001f1e7  cmp     [rcx+19h], dil
0x14001f1eb  jb      short loc_14001F205
0x14001f1ed  mov     rcx, [rcx+10h]
0x14001f1f1  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001f1f8  mov     edx, 139h
0x14001f1fd  mov     r9d, eax
0x14001f200  call    WPP_SF_d
0x14001f205  mov     r13, [rsp+4D0h+var_478]
0x14001f20a  mov     r12, [rsp+4D0h+var_480]
0x14001f20f  cmp     ebx, 5
0x14001f212  jz      loc_14001F145
0x14001f218  cmp     ebx, 20h ; ' '
0x14001f21b  jnz     loc_14001F529
0x14001f221  jmp     loc_14001F145
0x14001f226  mov     r12, [rsp+4D0h+var_480]
0x14001f22b  mov     r13, [rsp+4D0h+var_478]
0x14001f230  lea     rdx, [rsp+4D0h+var_470]
0x14001f235  lea     rcx, [rsp+4D0h+Mem]
0x14001f23a  call    ?ContractConfigurationFolder@@YAHQEAXPEAPEAXW4FAX_ENUM_CONFIGURATION_TYPES@@@Z; ContractConfigurationFolder(void * const,void * *,FAX_ENUM_CONFIGURATION_TYPES)
0x14001f23f  mov     r15d, eax
0x14001f242  test    eax, eax
0x14001f244  jnz     short loc_14001F281
0x14001f246  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f24d  lea     rax, WPP_GLOBAL_Control
0x14001f254  cmp     rcx, rax
0x14001f257  jz      short loc_14001F27A
0x14001f259  test    byte ptr [rcx+1Ch], 4
0x14001f25d  jz      short loc_14001F27A
0x14001f25f  cmp     [rcx+19h], dil
0x14001f263  jb      short loc_14001F27A
0x14001f265  mov     rcx, [rcx+10h]
0x14001f269  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001f270  mov     edx, 13Ah
0x14001f275  call    WPP_SF_
0x14001f27a  lea     r14, [rsp+4D0h+Mem]
0x14001f27f  jmp     short loc_14001F286
0x14001f281  mov     r14, [rsp+4D0h+var_470]
0x14001f286  mov     rcx, r14
0x14001f289  call    StoreActivityLoggingSettings
0x14001f28e  mov     ebx, eax
0x14001f290  test    eax, eax
0x14001f292  jz      short loc_14001F2D5
0x14001f294  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f29b  lea     rsi, WPP_GLOBAL_Control
0x14001f2a2  cmp     rcx, rsi
0x14001f2a5  jz      short loc_14001F2CB
0x14001f2a7  test    byte ptr [rcx+1Ch], 4
0x14001f2ab  jz      short loc_14001F2CB
0x14001f2ad  cmp     [rcx+19h], dil
0x14001f2b1  jb      short loc_14001F2CB
0x14001f2b3  mov     rcx, [rcx+10h]
0x14001f2b7  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001f2be  mov     edx, 13Bh
0x14001f2c3  mov     r9d, eax
0x14001f2c6  call    WPP_SF_d
0x14001f2cb  mov     ebx, 3F7h
0x14001f2d0  jmp     loc_14001F51C
0x14001f2d5  cmp     dword ptr [rsp+4D0h+Mem+4], 0
0x14001f2da  jnz     short loc_14001F2E7
0x14001f2dc  cmp     dword ptr [rsp+4D0h+Mem+8], 0
0x14001f2e1  jz      loc_14001F4CA
0x14001f2e7  mov     rdx, [rsp+4D0h+lpPathName]; unsigned __int16 *
0x14001f2ec  lea     rcx, fDesiredAccess; unsigned __int16 **
0x14001f2f3  call    ?ReplaceStringWithCopy@@YAHPEAPEAGPEBG@Z; ReplaceStringWithCopy(ushort * *,ushort const *)
0x14001f2f8  test    eax, eax
0x14001f2fa  jnz     loc_14001F3C8
0x14001f300  call    cs:__imp_GetLastError
0x14001f307  nop     dword ptr [rax+rax+00h]
0x14001f30c  mov     ebx, eax
0x14001f30e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f315  lea     rsi, WPP_GLOBAL_Control
0x14001f31c  cmp     rcx, rsi
0x14001f31f  jz      short loc_14001F345
0x14001f321  test    byte ptr [rcx+1Ch], 4
  ... truncated ...
```
