# AddParentJob(_LIST_ENTRY * const,ushort const *,_FAX_PERSONAL_PROFILEW const *,_FAX_JOB_PARAM_EXW const *,_FAX_COVERPAGE_INFO_EXW const *,ushort const *,void *,_FAX_PERSONAL_PROFILEW const *,ushort const *,int)

- ea: `0x14003735c`
- end: `0x140037d36`
- name: `?AddParentJob@@YAPEAU_JOB_QUEUE@@QEAU_LIST_ENTRY@@PEBGPEBU_FAX_PERSONAL_PROFILEW@@PEBU_FAX_JOB_PARAM_EXW@@PEBU_FAX_COVERPAGE_INFO_EXW@@1PEAX21H@Z`
- size: `2522`
- prototype: `struct _JOB_QUEUE *__fastcall(struct _LIST_ENTRY *const, unsigned __int16 *, const struct _FAX_PERSONAL_PROFILEW *, const struct _FAX_JOB_PARAM_EXW *, const struct _FAX_COVERPAGE_INFO_EXW *, unsigned __int16 *, PSID pSourceSid, const struct _FAX_PERSONAL_PROFILEW *, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001dbc0`
- `0x14003e4d8`

## callees

- `0x1400023ec`
- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x14003735c`
- `0x140038d44`
- `0x140039768`
- `0x140039860`
- `0x14003a1bc`
- `0x14003a808`
- `0x14003c4ac`
- `0x14003fe88`
- `0x140040500`
- `0x140052838`
- `0x140053b44`
- `0x140054c5c`
- `0x14006af2c`
- `0x140073444`
- `0x14007972c`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400374f7`
- `KERNEL32!GetLastError` at `0x140037574`
- `KERNEL32!GetLastError` at `0x14003762b`
- `KERNEL32!GetLastError` at `0x140037656`
- `KERNEL32!GetLastError` at `0x14003768f`
- `KERNEL32!GetLastError` at `0x1400376e4`
- `KERNEL32!GetLastError` at `0x14003771d`
- `KERNEL32!GetLastError` at `0x140037746`
- `KERNEL32!GetLastError` at `0x14003777f`
- `KERNEL32!GetLastError` at `0x140037827`
- `KERNEL32!GetLastError` at `0x14003786a`
- `KERNEL32!GetLastError` at `0x1400378c9`
- `KERNEL32!GetLastError` at `0x14003794e`
- `KERNEL32!GetLastError` at `0x1400379c2`
- `KERNEL32!GetLastError` at `0x140037a21`
- `KERNEL32!GetLastError` at `0x140037ab2`
- `KERNEL32!GetLastError` at `0x140037aeb`
- `KERNEL32!GetLastError` at `0x140037b2d`
- `KERNEL32!GetLastError` at `0x140037b66`
- `KERNEL32!GetLastError` at `0x140037ba4`
- `KERNEL32!GetLastError` at `0x140037bd1`
- `KERNEL32!GetLastError` at `0x140037ca3`
- `KERNEL32!GetLastError` at `0x140037cd0`
- `KERNEL32!GetLastError` at `0x1400374f7`
- `KERNEL32!GetLastError` at `0x140037574`
- `KERNEL32!GetLastError` at `0x14003762b`
- `KERNEL32!GetLastError` at `0x140037656`
- `KERNEL32!GetLastError` at `0x14003768f`
- `KERNEL32!GetLastError` at `0x1400376e4`
- `KERNEL32!GetLastError` at `0x14003771d`
- `KERNEL32!GetLastError` at `0x140037746`
- `KERNEL32!GetLastError` at `0x14003777f`
- `KERNEL32!GetLastError` at `0x140037827`
- `KERNEL32!GetLastError` at `0x14003786a`
- `KERNEL32!GetLastError` at `0x1400378c9`
- `KERNEL32!GetLastError` at `0x14003794e`
- `KERNEL32!GetLastError` at `0x1400379c2`
- `KERNEL32!GetLastError` at `0x140037a21`
- `KERNEL32!GetLastError` at `0x140037ab2`
- `KERNEL32!GetLastError` at `0x140037aeb`
- `KERNEL32!GetLastError` at `0x140037b2d`
- `KERNEL32!GetLastError` at `0x140037b66`
- `KERNEL32!GetLastError` at `0x140037ba4`
- `KERNEL32!GetLastError` at `0x140037bd1`
- `KERNEL32!GetLastError` at `0x140037ca3`
- `KERNEL32!GetLastError` at `0x140037cd0`
- `KERNEL32!SetLastError` at `0x140037cfd`
- `KERNEL32!SetLastError` at `0x140037cfd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14003791d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14003791d`
- `KERNEL32!EnterCriticalSection` at `0x140037a82`
- `KERNEL32!EnterCriticalSection` at `0x140037a82`
- `KERNEL32!LeaveCriticalSection` at `0x140037c04`
- `KERNEL32!LeaveCriticalSection` at `0x140037c5a`
- `KERNEL32!LeaveCriticalSection` at `0x140037c04`
- `KERNEL32!LeaveCriticalSection` at `0x140037c5a`
- `KERNEL32!InitializeCriticalSection` at `0x140037483`
- `KERNEL32!InitializeCriticalSection` at `0x140037496`
- `KERNEL32!InitializeCriticalSection` at `0x140037483`
- `KERNEL32!InitializeCriticalSection` at `0x140037496`
- `KERNEL32!GetSystemTime` at `0x1400379a8`
- `KERNEL32!GetSystemTime` at `0x1400379a8`
- `KERNEL32!SystemTimeToFileTime` at `0x14003793a`
- `KERNEL32!SystemTimeToFileTime` at `0x140037a11`
- `KERNEL32!SystemTimeToFileTime` at `0x14003793a`
- `KERNEL32!SystemTimeToFileTime` at `0x140037a11`
- `FXSTIFF!TiffClose` at `0x1400377cc`
- `FXSTIFF!TiffClose` at `0x1400377cc`
- `FXSTIFF!TiffOpen` at `0x1400377ad`
- `FXSTIFF!TiffOpen` at `0x1400377ad`

## pseudocode

```c
struct _JOB_QUEUE *__fastcall AddParentJob(
        struct _LIST_ENTRY *const a1,
        unsigned __int16 *a2,
        const struct _FAX_PERSONAL_PROFILEW *a3,
        const struct _FAX_JOB_PARAM_EXW *a4,
        const struct _FAX_COVERPAGE_INFO_EXW *a5,
        unsigned __int16 *a6,
        PSID pSourceSid,
        const struct _FAX_PERSONAL_PROFILEW *a8,
        unsigned __int16 *a9,
        int a10)
{
  _DWORD *v11; // rax
  _DWORD *v12; // rdi
  DWORD LastError; // ebx
  __int64 v14; // rax
  CMapDeviceId **v15; // rdx
  DWORD v16; // eax
  __int64 v17; // rdx
  CMapDeviceId *v18; // rcx
  __int64 v19; // rax
  DWORD v20; // eax
  __int64 v21; // rax
  DWORD v22; // eax
  __int64 v23; // rdx
  CMapDeviceId *v24; // rcx
  __int64 v25; // rax
  unsigned int v26; // eax
  unsigned int *v27; // rdx
  unsigned int FileSize; // eax
  unsigned int MergedFileSize; // eax
  _QWORD *v30; // rbx
  unsigned int v31; // r8d
  unsigned __int64 UniqueQueueFile; // rax
  DWORD v33; // eax
  __int64 v34; // rax
  DWORD v35; // eax
  char v36; // al
  struct _LIST_ENTRY *Blink; // rax
  CFaxConfiguration *v38; // rcx
  DWORD v40; // eax
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v44[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v45[264]; // [rsp+80h] [rbp-80h] BYREF

  memset(v44, 0, sizeof(v44));
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 207, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  v11 = operator new(0x738u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)&SystemTime.wYear = v11;
  v12 = v11;
  if ( !v11 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v40 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 208, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v40);
    }
    goto LABEL_117;
  }
  v11[461] = 0;
  LastError = 0;
  memset_0(v11, 0, 0x738u);
  *((_QWORD *)v12 + 213) = v12 + 424;
  *((_QWORD *)v12 + 212) = v12 + 424;
  *((_QWORD *)v12 + 221) = v12 + 440;
  *((_QWORD *)v12 + 220) = v12 + 440;
  *((_QWORD *)v12 + 28) = v12 + 54;
  *((_QWORD *)v12 + 27) = v12 + 54;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v12 + 444));
  InitializeCriticalSection((LPCRITICAL_SECTION)v12 + 43);
  v12[8] = _InterlockedIncrement((volatile signed __int32 *)g_pFaxConfig + 27);
  v14 = StringDup(a2);
  *((_QWORD *)v12 + 9) = v14;
  if ( a2 && !v14 )
  {
    v15 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_107;
    }
    v16 = GetLastError();
    v17 = 209;
    goto LABEL_12;
  }
  v12[9] = 32;
  v19 = StringDup(a6);
  *((_QWORD *)v12 + 50) = v19;
  if ( a6 && !v19 )
  {
    v15 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_107;
    }
    v16 = GetLastError();
    v17 = 210;
    goto LABEL_12;
  }
  v20 = AllocateAndCopySid(pSourceSid);
  LastError = v20;
  if ( v20 )
  {
    v15 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 211, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v20);
    }
    goto LABEL_107;
  }
  v21 = StringDup(a9);
  *((_QWORD *)v12 + 55) = v21;
  if ( a9 && !v21 )
  {
    v15 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_107;
    }
    v16 = GetLastError();
    v17 = 212;
LABEL_12:
    v18 = WPP_GLOBAL_Control;
    LastError = v16;
LABEL_13:
    WPP_SF_d(*((_QWORD *)v18 + 2), v17, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v16);
LABEL_107:
    FreeParentQueueEntry((struct _JOB_QUEUE *)v12, (int)v15);
LABEL_117:
    SetLastError(LastError);
    return 0;
  }
  if ( !(unsigned int)CopyJobParamEx((struct _FAX_JOB_PARAM_EXW *)(v12 + 20), a4) )
  {
    LastError = GetLastError();
    v15 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_107;
    }
    v22 = GetLastError();
    v23 = 213;
    goto LABEL_36;
  }
  _JOB_QUEUE::PutStatus((_JOB_QUEUE *)v12, 1u);
  if ( !(unsigned int)CopyPersonalProfile(v12 + 60, a3) )
  {
    LastError = GetLastError();
    v15 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_107;
    }
    v22 = GetLastError();
    v23 = 214;
    goto LABEL_36;
  }
  if ( !(unsigned int)CopyCoverPageInfoEx((struct _FAX_COVERPAGE_INFO_EXW *)(v12 + 44), a5) )
  {
    LastError = GetLastError();
    v15 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_107;
    }
    v22 = GetLastError();
    v23 = 215;
LABEL_36:
    v24 = WPP_GLOBAL_Control;
LABEL_37:
    WPP_SF_d(*((_QWORD *)v24 + 2), v23, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v22);
    goto LABEL_107;
  }
  if ( a2 )
  {
    v25 = TiffOpen(a2, v44, 1, 1);
    if ( !v25 )
    {
      v22 = GetLastError();
      LastError = v22;
      v24 = WPP_GLOBAL_Control;
      v15 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_107;
      }
      v23 = 216;
      goto LABEL_37;
    }
    v12[16] = DWORD2(v44[0]);
    TiffClose(v25);
  }
  v26 = v12[42];
  v27 = v12 + 16;
  if ( v26 )
    *v27 = v26;
  if ( a5 && *((_QWORD *)a5 + 1) )
  {
    v27 = v12 + 16;
    ++v12[16];
  }
  if ( a8 )
  {
    if ( *((_QWORD *)a5 + 1) )
    {
      MergedFileSize = GetMergedFileSize(a2, *v27, a5, a3, a8);
      v12[97] = MergedFileSize;
      if ( !MergedFileSize )
      {
        v16 = GetLastError();
        LastError = v16;
        v18 = WPP_GLOBAL_Control;
        v15 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_107;
        }
        v17 = 218;
        goto LABEL_13;
      }
    }
    else
    {
      FileSize = MyGetFileSize(a2);
      v12[97] = FileSize;
      if ( !FileSize )
      {
        v16 = GetLastError();
        LastError = v16;
        v18 = WPP_GLOBAL_Control;
        v15 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_107;
        }
        v17 = 217;
        goto LABEL_13;
      }
    }
  }
  *((_QWORD *)v12 + 49) = 0;
  GetSystemTimeAsFileTime((LPFILETIME)v12 + 53);
  if ( *((_DWORD *)a4 + 1) == 1 )
  {
    v30 = v12 + 6;
    if ( !SystemTimeToFileTime((const SYSTEMTIME *)(v12 + 22), (LPFILETIME)v12 + 3) )
    {
      v16 = GetLastError();
      LastError = v16;
      v18 = WPP_GLOBAL_Control;
      v15 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_107;
      }
      v17 = 219;
      goto LABEL_13;
    }
  }
  else if ( *((_DWORD *)a4 + 1) == 2 )
  {
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    if ( !(unsigned int)SetDiscountTime(&SystemTime) )
    {
      v16 = GetLastError();
      LastError = v16;
      v18 = WPP_GLOBAL_Control;
      v15 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_107;
      }
      v17 = 220;
      goto LABEL_13;
    }
    v30 = v12 + 6;
    if ( !SystemTimeToFileTime(&SystemTime, (LPFILETIME)v12 + 3) )
    {
      v16 = GetLastError();
      LastError = v16;
      v18 = WPP_GLOBAL_Control;
      v15 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_107;
      }
      v17 = 221;
      goto LABEL_13;
    }
  }
  else
  {
    v30 = v12 + 6;
    *((_QWORD *)v12 + 3) = *((_QWORD *)v12 + 53);
  }
  *((_QWORD *)v12 + 52) = *v30;
  EnterCriticalSection(&g_CsQueue);
  if ( a10 )
  {
    UniqueQueueFile = GenerateUniqueQueueFile(0x20u, v45, v31);
    *((_QWORD *)v12 + 2) = UniqueQueueFile;
    if ( !UniqueQueueFile )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v33 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v33);
      }
LABEL_106:
      LeaveCriticalSection(&g_CsQueue);
      goto LABEL_107;
    }
    v34 = StringDup(v45);
    *((_QWORD *)v12 + 7) = v34;
    if ( !v34 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v35 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v35);
      }
      goto LABEL_106;
    }
    if ( !(unsigned int)CommitQueueEntry((struct _JOB_QUEUE *)v12, 1) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v36 = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          224,
          (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
          (unsigned int)v45,
          v36);
      }
      goto LABEL_106;
    }
  }
  Blink = g_QueueListHead.Blink;
  *(_QWORD *)v12 = &g_QueueListHead;
  *((_QWORD *)v12 + 1) = Blink;
  Blink->Flink = (struct _LIST_ENTRY *)v12;
  g_QueueListHead.Blink = (struct _LIST_ENTRY *)v12;
  SafeIncIdleCounter(&g_dwQueueCount);
  CFaxConfiguration::StoreNextJobId(v38, *((_DWORD *)g_pFaxConfig + 27));
  LeaveCriticalSection(&g_CsQueue);
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      225,
      &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
      (unsigned int)v12[8]);
  }
  return (struct _JOB_QUEUE *)v12;
}

```

## disassembly

```asm
0x14003735c  mov     [rsp-8+arg_0], rbx
0x140037361  push    rbp
0x140037362  push    rsi
0x140037363  push    rdi
0x140037364  push    r12
0x140037366  push    r13
0x140037368  push    r14
0x14003736a  push    r15
0x14003736c  lea     rbp, [rsp-1A0h]
0x140037374  sub     rsp, 2A0h
0x14003737b  mov     rax, cs:__security_cookie
0x140037382  xor     rax, rsp
0x140037385  mov     [rbp+1D0h+var_40], rax
0x14003738c  mov     rax, [rbp+1D0h+arg_38]
0x140037393  xorps   xmm0, xmm0
0x140037396  mov     rsi, [rbp+1D0h+arg_20]
0x14003739d  mov     r14, rdx
0x1400373a0  mov     r15, [rbp+1D0h+arg_28]
0x1400373a7  mov     r13, [rbp+1D0h+pSourceSid]
0x1400373ae  mov     r12, [rbp+1D0h+arg_40]
0x1400373b5  mov     [rsp+2D0h+var_290], rax
0x1400373ba  movups  [rsp+2D0h+var_278], xmm0
0x1400373bf  mov     [rsp+2D0h+var_2A0], r9
0x1400373c4  movups  [rsp+2D0h+var_268], xmm0
0x1400373c9  mov     [rsp+2D0h+var_298], r8
0x1400373ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400373d5  lea     rax, WPP_GLOBAL_Control
0x1400373dc  cmp     rcx, rax
0x1400373df  jz      short loc_140037402
0x1400373e1  test    byte ptr [rcx+1Ch], 4
0x1400373e5  jz      short loc_140037402
0x1400373e7  cmp     byte ptr [rcx+19h], 5
0x1400373eb  jb      short loc_140037402
0x1400373ed  mov     rcx, [rcx+10h]
0x1400373f1  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x1400373f8  mov     edx, 0CFh
0x1400373fd  call    WPP_SF_
0x140037402  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140037409  mov     ecx, 738h; unsigned __int64
0x14003740e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140037413  mov     qword ptr [rsp+2D0h+SystemTime.wYear], rax
0x140037418  mov     rdi, rax
0x14003741b  test    rax, rax
0x14003741e  jz      loc_140037CA3
0x140037424  mov     dword ptr [rax+734h], 0
0x14003742e  test    rax, rax
0x140037431  jz      loc_140037CA3
0x140037437  xor     edx, edx; Val
0x140037439  mov     r8d, 738h; Size
0x14003743f  mov     rcx, rax; void *
0x140037442  xor     ebx, ebx
0x140037444  call    memset_0
0x140037449  lea     rax, [rdi+6A0h]
0x140037450  mov     [rdi+6A8h], rax
0x140037457  lea     rcx, [rdi+6F0h]; lpCriticalSection
0x14003745e  mov     [rax], rax
0x140037461  lea     rax, [rdi+6E0h]
0x140037468  mov     [rdi+6E8h], rax
0x14003746f  mov     [rax], rax
0x140037472  lea     rax, [rdi+0D8h]
0x140037479  mov     [rdi+0E0h], rax
0x140037480  mov     [rax], rax
0x140037483  call    cs:__imp_InitializeCriticalSection
0x14003748a  nop     dword ptr [rax+rax+00h]
0x14003748f  lea     rcx, [rdi+6B8h]; lpCriticalSection
0x140037496  call    cs:__imp_InitializeCriticalSection
0x14003749d  nop     dword ptr [rax+rax+00h]
0x1400374a2  mov     rcx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x1400374a9  lea     eax, [rbx+1]
0x1400374ac  lock xadd [rcx+6Ch], eax
0x1400374b1  inc     eax
0x1400374b3  mov     rcx, r14; unsigned __int16 *
0x1400374b6  mov     [rdi+20h], eax
0x1400374b9  call    StringDup
0x1400374be  mov     [rdi+48h], rax
0x1400374c2  test    r14, r14
0x1400374c5  jz      short loc_140037529
0x1400374c7  test    rax, rax
0x1400374ca  jnz     short loc_140037529
0x1400374cc  mov     rax, cs:WPP_GLOBAL_Control
0x1400374d3  lea     rdx, WPP_GLOBAL_Control
0x1400374da  cmp     rax, rdx
0x1400374dd  jz      loc_140037C10
0x1400374e3  test    byte ptr [rax+1Ch], 4
0x1400374e7  jz      loc_140037C10
0x1400374ed  cmp     byte ptr [rax+19h], 2
0x1400374f1  jb      loc_140037C10
0x1400374f7  call    cs:__imp_GetLastError
0x1400374fe  nop     dword ptr [rax+rax+00h]
0x140037503  mov     edx, 0D1h
0x140037508  mov     rcx, cs:WPP_GLOBAL_Control
0x14003750f  mov     ebx, eax
0x140037511  mov     rcx, [rcx+10h]
0x140037515  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003751c  mov     r9d, eax
0x14003751f  call    WPP_SF_d
0x140037524  jmp     loc_140037C10
0x140037529  mov     rcx, r15; unsigned __int16 *
0x14003752c  mov     dword ptr [rdi+24h], 20h ; ' '
0x140037533  call    StringDup
0x140037538  mov     [rdi+190h], rax
0x14003753f  test    r15, r15
0x140037542  jz      short loc_140037587
0x140037544  test    rax, rax
0x140037547  jnz     short loc_140037587
0x140037549  mov     rax, cs:WPP_GLOBAL_Control
0x140037550  lea     rdx, WPP_GLOBAL_Control
0x140037557  cmp     rax, rdx
0x14003755a  jz      loc_140037C10
0x140037560  test    byte ptr [rax+1Ch], 4
0x140037564  jz      loc_140037C10
0x14003756a  cmp     byte ptr [rax+19h], 2
0x14003756e  jb      loc_140037C10
0x140037574  call    cs:__imp_GetLastError
0x14003757b  nop     dword ptr [rax+rax+00h]
0x140037580  mov     edx, 0D2h
0x140037585  jmp     short loc_140037508
0x140037587  lea     rdx, [rdi+198h]
0x14003758e  mov     rcx, r13; pSourceSid
0x140037591  call    AllocateAndCopySid
0x140037596  xor     r13d, r13d
0x140037599  mov     ebx, eax
0x14003759b  test    eax, eax
0x14003759d  jz      short loc_1400375E7
0x14003759f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400375a6  lea     rdx, WPP_GLOBAL_Control
0x1400375ad  cmp     rcx, rdx
0x1400375b0  jz      loc_140037C10
0x1400375b6  test    byte ptr [rcx+1Ch], 4
0x1400375ba  jz      loc_140037C10
0x1400375c0  cmp     byte ptr [rcx+19h], 2
0x1400375c4  jb      loc_140037C10
0x1400375ca  mov     rcx, [rcx+10h]
0x1400375ce  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x1400375d5  mov     edx, 0D3h
0x1400375da  mov     r9d, eax
0x1400375dd  call    WPP_SF_d
0x1400375e2  jmp     loc_140037C10
0x1400375e7  mov     rcx, r12; unsigned __int16 *
0x1400375ea  call    StringDup
0x1400375ef  mov     [rdi+1B8h], rax
0x1400375f6  test    r12, r12
0x1400375f9  jz      short loc_140037641
0x1400375fb  test    rax, rax
0x1400375fe  jnz     short loc_140037641
0x140037600  mov     rax, cs:WPP_GLOBAL_Control
0x140037607  lea     rdx, WPP_GLOBAL_Control
0x14003760e  cmp     rax, rdx
0x140037611  jz      loc_140037C10
0x140037617  test    byte ptr [rax+1Ch], 4
0x14003761b  jz      loc_140037C10
0x140037621  cmp     byte ptr [rax+19h], 2
0x140037625  jb      loc_140037C10
0x14003762b  call    cs:__imp_GetLastError
0x140037632  nop     dword ptr [rax+rax+00h]
0x140037637  mov     edx, 0D4h
0x14003763c  jmp     loc_140037508
0x140037641  mov     rbx, [rsp+2D0h+var_2A0]
0x140037646  lea     rcx, [rdi+50h]; struct _FAX_JOB_PARAM_EXW *
0x14003764a  mov     rdx, rbx; struct _FAX_JOB_PARAM_EXW *
0x14003764d  call    ?CopyJobParamEx@@YAHPEAU_FAX_JOB_PARAM_EXW@@PEBU1@@Z; CopyJobParamEx(_FAX_JOB_PARAM_EXW *,_FAX_JOB_PARAM_EXW const *)
0x140037652  test    eax, eax
0x140037654  jnz     short loc_1400376BF
0x140037656  call    cs:__imp_GetLastError
0x14003765d  nop     dword ptr [rax+rax+00h]
0x140037662  mov     ebx, eax
0x140037664  mov     rax, cs:WPP_GLOBAL_Control
0x14003766b  lea     rdx, WPP_GLOBAL_Control
0x140037672  cmp     rax, rdx
0x140037675  jz      loc_140037C10
0x14003767b  test    byte ptr [rax+1Ch], 4
0x14003767f  jz      loc_140037C10
0x140037685  cmp     byte ptr [rax+19h], 2
0x140037689  jb      loc_140037C10
0x14003768f  call    cs:__imp_GetLastError
0x140037696  nop     dword ptr [rax+rax+00h]
0x14003769b  mov     edx, 0D5h
0x1400376a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400376a7  mov     rcx, [rcx+10h]
0x1400376ab  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x1400376b2  mov     r9d, eax
0x1400376b5  call    WPP_SF_d
0x1400376ba  jmp     loc_140037C10
0x1400376bf  mov     edx, 1; unsigned int
0x1400376c4  mov     rcx, rdi; this
0x1400376c7  call    ?PutStatus@_JOB_QUEUE@@QEAAXK@Z; _JOB_QUEUE::PutStatus(ulong)
0x1400376cc  mov     r12, [rsp+2D0h+var_298]
0x1400376d1  lea     rcx, [rdi+0F0h]
0x1400376d8  mov     rdx, r12
0x1400376db  call    CopyPersonalProfile
0x1400376e0  test    eax, eax
0x1400376e2  jnz     short loc_140037733
0x1400376e4  call    cs:__imp_GetLastError
0x1400376eb  nop     dword ptr [rax+rax+00h]
0x1400376f0  mov     ebx, eax
0x1400376f2  mov     rax, cs:WPP_GLOBAL_Control
0x1400376f9  lea     rdx, WPP_GLOBAL_Control
0x140037700  cmp     rax, rdx
0x140037703  jz      loc_140037C10
0x140037709  test    byte ptr [rax+1Ch], 4
0x14003770d  jz      loc_140037C10
0x140037713  cmp     byte ptr [rax+19h], 2
0x140037717  jb      loc_140037C10
0x14003771d  call    cs:__imp_GetLastError
0x140037724  nop     dword ptr [rax+rax+00h]
0x140037729  mov     edx, 0D6h
0x14003772e  jmp     loc_1400376A0
0x140037733  lea     rcx, [rdi+0B0h]; struct _FAX_COVERPAGE_INFO_EXW *
0x14003773a  mov     rdx, rsi; struct _FAX_COVERPAGE_INFO_EXW *
0x14003773d  call    ?CopyCoverPageInfoEx@@YAHPEAU_FAX_COVERPAGE_INFO_EXW@@PEBU1@@Z; CopyCoverPageInfoEx(_FAX_COVERPAGE_INFO_EXW *,_FAX_COVERPAGE_INFO_EXW const *)
0x140037742  test    eax, eax
0x140037744  jnz     short loc_140037795
0x140037746  call    cs:__imp_GetLastError
0x14003774d  nop     dword ptr [rax+rax+00h]
0x140037752  mov     ebx, eax
0x140037754  mov     rax, cs:WPP_GLOBAL_Control
0x14003775b  lea     rdx, WPP_GLOBAL_Control
0x140037762  cmp     rax, rdx
0x140037765  jz      loc_140037C10
0x14003776b  test    byte ptr [rax+1Ch], 4
0x14003776f  jz      loc_140037C10
0x140037775  cmp     byte ptr [rax+19h], 2
0x140037779  jb      loc_140037C10
0x14003777f  call    cs:__imp_GetLastError
0x140037786  nop     dword ptr [rax+rax+00h]
0x14003778b  mov     edx, 0D7h
0x140037790  jmp     loc_1400376A0
0x140037795  test    r14, r14
0x140037798  jz      short loc_1400377D8
0x14003779a  mov     eax, 1
0x14003779f  lea     rdx, [rsp+2D0h+var_278]
0x1400377a4  mov     r9d, eax
0x1400377a7  mov     r8d, eax
0x1400377aa  mov     rcx, r14
0x1400377ad  call    cs:__imp_TiffOpen
0x1400377b4  nop     dword ptr [rax+rax+00h]
0x1400377b9  test    rax, rax
0x1400377bc  jz      loc_14003786A
0x1400377c2  mov     ecx, dword ptr [rsp+2D0h+var_278+8]
0x1400377c6  mov     [rdi+40h], ecx
0x1400377c9  mov     rcx, rax
0x1400377cc  call    cs:__imp_TiffClose
0x1400377d3  nop     dword ptr [rax+rax+00h]
0x1400377d8  mov     eax, [rdi+0A8h]
0x1400377de  lea     rdx, [rdi+40h]
0x1400377e2  test    eax, eax
0x1400377e4  jz      short loc_1400377E8
0x1400377e6  mov     [rdx], eax
0x1400377e8  test    rsi, rsi
0x1400377eb  jz      short loc_1400377F9
0x1400377ed  cmp     [rsi+8], r13
0x1400377f1  jz      short loc_1400377F9
0x1400377f3  lea     rdx, [rdi+40h]
0x1400377f7  inc     dword ptr [rdx]
0x1400377f9  mov     rax, [rsp+2D0h+var_290]
0x1400377fe  test    rax, rax
0x140037801  jz      loc_14003790C
0x140037807  mov     rcx, r14; unsigned __int16 *
0x14003780a  cmp     [rsi+8], r13
0x14003780e  jnz     loc_1400378AD
0x140037814  call    ?MyGetFileSize@@YAKPEBG@Z; MyGetFileSize(ushort const *)
0x140037819  mov     [rdi+184h], eax
0x14003781f  test    eax, eax
0x140037821  jnz     loc_14003790C
0x140037827  call    cs:__imp_GetLastError
0x14003782e  nop     dword ptr [rax+rax+00h]
0x140037833  mov     ebx, eax
0x140037835  mov     rcx, cs:WPP_GLOBAL_Control
0x14003783c  lea     rdx, WPP_GLOBAL_Control
0x140037843  cmp     rcx, rdx
0x140037846  jz      loc_140037C10
0x14003784c  test    byte ptr [rcx+1Ch], 4
0x140037850  jz      loc_140037C10
0x140037856  cmp     byte ptr [rcx+19h], 2
0x14003785a  jb      loc_140037C10
0x140037860  mov     edx, 0D9h
0x140037865  jmp     loc_140037511
0x14003786a  call    cs:__imp_GetLastError
0x140037871  nop     dword ptr [rax+rax+00h]
0x140037876  mov     ebx, eax
0x140037878  mov     rcx, cs:WPP_GLOBAL_Control
0x14003787f  lea     rdx, WPP_GLOBAL_Control
0x140037886  cmp     rcx, rdx
0x140037889  jz      loc_140037C10
0x14003788f  test    byte ptr [rcx+1Ch], 4
0x140037893  jz      loc_140037C10
0x140037899  cmp     byte ptr [rcx+19h], 2
0x14003789d  jb      loc_140037C10
0x1400378a3  mov     edx, 0D8h
0x1400378a8  jmp     loc_1400376A7
0x1400378ad  mov     edx, [rdx]; unsigned int
0x1400378af  mov     r9, r12; struct _FAX_PERSONAL_PROFILEW *
0x1400378b2  mov     r8, rsi; struct _FAX_COVERPAGE_INFO_EXW *
0x1400378b5  mov     [rsp+2D0h+var_2B0], rax; struct _FAX_PERSONAL_PROFILEW *
0x1400378ba  call    ?GetMergedFileSize@@YAKPEBGKPEBU_FAX_COVERPAGE_INFO_EXW@@PEBU_FAX_PERSONAL_PROFILEW@@2@Z; GetMergedFileSize(ushort const *,ulong,_FAX_COVERPAGE_INFO_EXW const *,_FAX_PERSONAL_PROFILEW const *,_FAX_PERSONAL_PROFILEW const *)
0x1400378bf  mov     [rdi+184h], eax
0x1400378c5  test    eax, eax
0x1400378c7  jnz     short loc_14003790C
0x1400378c9  call    cs:__imp_GetLastError
0x1400378d0  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
