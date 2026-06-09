# CTieringEngineLib::Initialize(ushort const *,ushort const *,ushort const *)

- ea: `0x140006720`
- end: `0x140006e67`
- name: `?Initialize@CTieringEngineLib@@QEAAJPEBG00@Z`
- size: `1863`
- prototype: `__int64 __fastcall(CTieringEngineLib *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140003e38`

## callees

- `0x140002323`
- `0x140002db0`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140006720`
- `0x14000814c`
- `0x140009904`
- `0x140009a04`
- `0x140009f1c`
- `0x14003fbb0`

## import_xrefs

- `ntdll!WinSqmStartSession` at `0x140006e19`
- `ntdll!WinSqmStartSession` at `0x140006e19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000681f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006913`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400069c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006a7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006b19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006c43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006cc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006dcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000681f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006913`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400069c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006a7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006b19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006c43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006cc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006dcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006965`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006965`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006901`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006c34`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006901`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006c34`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140006e2a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140006e2a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x140006d12`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x140006d12`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x140006d05`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x140006d05`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x140006cb5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x140006cb5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1400068e9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14000696e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1400068e9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14000696e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140006dc0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140006dc0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14000680e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140006d6c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14000680e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140006d6c`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x140006a70`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x140006ad0`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x140006a70`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x140006ad0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x140006997`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x140006997`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x140006889`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x140006889`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140006ac1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140006ac1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140006bb9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140006bb9`

## string_xrefs

- `0x140006b85`: `System\CurrentControlSet\Services\TieringEngineService\Parameters`

## pseudocode

```c
__int64 __fastcall CTieringEngineLib::Initialize(
        CTieringEngineLib *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  char *v5; // rsi
  GUID si128; // xmm0
  GUID v7; // xmm1
  struct _TP_CALLBACK_ENVIRON_V3 *v8; // r8
  struct _TP_WAIT *ThreadpoolWait; // rbx
  signed int LastError; // eax
  unsigned int v11; // ebx
  HANDLE SemaphoreW; // rdi
  signed int v13; // eax
  signed int v14; // edi
  HANDLE EventW; // rax
  signed int v16; // eax
  signed int v17; // esi
  DWORD v18; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  DWORD v23; // eax
  unsigned int Key; // eax
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  unsigned int CurrentRegistrySettings; // eax
  HANDLE v28; // rax
  DWORD v29; // eax
  struct _TP_POOL *Threadpool; // rax
  DWORD v31; // eax
  DWORD v32; // eax
  PTP_WAIT v33; // rax
  DWORD v34; // eax
  PTP_WORK ThreadpoolWork; // rax
  DWORD v36; // eax
  __int64 started; // rax
  struct _TP_WORK *v38; // rcx
  _BYTE v40[8]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v41; // [rsp+58h] [rbp-A8h]
  WCHAR Buffer[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v43; // [rsp+66h] [rbp-9Ah]
  __int128 v44; // [rsp+76h] [rbp-8Ah]
  _OWORD v45[30]; // [rsp+86h] [rbp-7Ah]

  v5 = (char *)TieringEngineLibInstance;
  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieringEngineLib::Initialize";
  CHResultImp::CHResultImp((CHResultImp *)v40);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, v5);
  }
  si128 = (GUID)_mm_load_si128((const __m128i *)&_xmm);
  v7 = (GUID)_mm_load_si128((const __m128i *)&_xmm);
  v8 = TieringTpCallbackEnvironment;
  *((_QWORD *)v5 + 22) = L"Storage Tiers Optimization";
  *((_QWORD *)v5 + 23) = L"\\Microsoft\\Windows\\Storage Tiers Management";
  *((_QWORD *)v5 + 21) = a2;
  g_DiskTierTestGuid = si128;
  g_FlashTierTestGuid = v7;
  ThreadpoolWait = CreateThreadpoolWait(CTieringEngineLib::StopEventCallback, v5, v8);
  if ( !ThreadpoolWait )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( (v11 & 0x80000000) == 0 )
      v11 = -2147467259;
    v41 = v11;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, v11);
    }
    goto LABEL_106;
  }
  SemaphoreW = CreateSemaphoreW(0, 0, 1, 0);
  if ( !SemaphoreW )
  {
    v13 = GetLastError();
    v14 = v13;
    if ( v13 > 0 )
      v14 = (unsigned __int16)v13 | 0x80070000;
    if ( v14 >= 0 )
      v14 = -2147467259;
    v41 = v14;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
        (unsigned int)v14);
    }
    CloseThreadpoolWait(ThreadpoolWait);
    v11 = v14;
    goto LABEL_106;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)v5 + 27) = EventW;
  if ( EventW )
  {
    memset_0(Buffer, 0, 0x208u);
    if ( !GetSystemWindowsDirectoryW(Buffer, 0x104u) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v18 = GetLastError();
        v19 = WPP_GLOBAL_Control;
        v20 = 14;
LABEL_39:
        WPP_SF_d(v19[2], v20, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, v18);
        goto LABEL_68;
      }
      goto LABEL_68;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, Buffer);
    }
    if ( !Buffer[0] || Buffer[1] != 58 || Buffer[2] != 92 )
      goto LABEL_68;
    v44 = *(_OWORD *)L"olume Information\\Heat\\";
    v43 = *(_OWORD *)L"System Volume Information\\Heat\\";
    v45[0] = *(_OWORD *)L"formation\\Heat\\";
    *(_OWORD *)((char *)v45 + 14) = *(_OWORD *)L"on\\Heat\\";
    if ( SetCurrentDirectoryW(Buffer) )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_68;
      }
      v22 = 19;
    }
    else
    {
      v18 = GetLastError();
      if ( v18 - 2 > 1 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v20 = 18;
          goto LABEL_39;
        }
LABEL_68:
        *((_QWORD *)v5 + 25) = SemaphoreW;
        *((_QWORD *)v5 + 51) = ThreadpoolWait;
        Key = RegCreateKeyExW(
                HKEY_LOCAL_MACHINE,
                L"System\\CurrentControlSet\\Services\\TieringEngineService\\Parameters",
                0,
                0,
                0,
                0x20019u,
                0,
                (PHKEY)v5 + 16,
                0);
        if ( Key )
        {
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
          {
            goto LABEL_105;
          }
          v26 = 20;
        }
        else
        {
          CurrentRegistrySettings = CTieringEngineLib::ReadCurrentRegistrySettings((CTieringEngineLib *)v5);
          if ( CurrentRegistrySettings
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
              CurrentRegistrySettings);
          }
          v28 = CreateEventW(0, 1, 0, 0);
          *((_QWORD *)v5 + 15) = v28;
          if ( v28 )
          {
            v5[88] = 1;
            *((_DWORD *)v5 + 4) = 3;
            *((_QWORD *)v5 + 3) = 0;
            *((_QWORD *)v5 + 4) = 0;
            *((_QWORD *)v5 + 5) = 0;
            *((_QWORD *)v5 + 6) = 0;
            *((_QWORD *)v5 + 7) = 0;
            *((_QWORD *)v5 + 8) = 0;
            *((_DWORD *)v5 + 18) = 0;
            *((_DWORD *)v5 + 19) = 1;
            *((_DWORD *)v5 + 20) = 72;
            Threadpool = CreateThreadpool(0);
            *((_QWORD *)v5 + 12) = Threadpool;
            if ( Threadpool )
            {
              SetThreadpoolThreadMaximum(Threadpool, 1u);
              if ( SetThreadpoolThreadMinimum(*((PTP_POOL *)v5 + 12), 1u) )
              {
                *((_QWORD *)v5 + 3) = *((_QWORD *)v5 + 12);
                v33 = CreateThreadpoolWait(
                        CTieringEngineLib::ProcessRegistryChange,
                        v5,
                        (PTP_CALLBACK_ENVIRON)(v5 + 16));
                *((_QWORD *)v5 + 14) = v33;
                if ( v33 )
                {
                  ThreadpoolWork = CreateThreadpoolWork(
                                     CTieringEngineLib::RegistryChangeListener,
                                     v5,
                                     (PTP_CALLBACK_ENVIRON)(v5 + 16));
                  *((_QWORD *)v5 + 13) = ThreadpoolWork;
                  if ( ThreadpoolWork )
                  {
                    started = WinSqmStartSession(qword_1400440D0, 101458002, 0);
                    v38 = (struct _TP_WORK *)*((_QWORD *)v5 + 13);
                    *((_QWORD *)v5 + 52) = started;
                    SubmitThreadpoolWork(v38);
                    goto LABEL_105;
                  }
                  v36 = GetLastError();
                  Key = ATL::AtlHresultFromWin32(v36);
                  v25 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
                  {
                    goto LABEL_105;
                  }
                  v26 = 26;
                }
                else
                {
                  v34 = GetLastError();
                  Key = ATL::AtlHresultFromWin32(v34);
                  v25 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
                  {
                    goto LABEL_105;
                  }
                  v26 = 25;
                }
              }
              else
              {
                v32 = GetLastError();
                Key = ATL::AtlHresultFromWin32(v32);
                v25 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
                {
                  goto LABEL_105;
                }
                v26 = 24;
              }
            }
            else
            {
              v31 = GetLastError();
              Key = ATL::AtlHresultFromWin32(v31);
              v25 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
              {
                goto LABEL_105;
              }
              v26 = 23;
            }
          }
          else
          {
            v29 = GetLastError();
            Key = ATL::AtlHresultFromWin32(v29);
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
            {
              goto LABEL_105;
            }
            v26 = 22;
          }
        }
        WPP_SF_d(v25[2], v26, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, Key);
LABEL_105:
        v11 = 0;
        v41 = 0;
        goto LABEL_106;
      }
      if ( !CreateDirectoryW(Buffer, 0) || !SetCurrentDirectoryW(Buffer) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v23 = GetLastError();
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            (unsigned int)&WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
            v23,
            (__int64)Buffer);
        }
        goto LABEL_68;
      }
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_68;
      }
      v22 = 17;
    }
    WPP_SF_S(v21[2], v22, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, Buffer);
    goto LABEL_68;
  }
  v16 = GetLastError();
  v17 = v16;
  if ( v16 > 0 )
    v17 = (unsigned __int16)v16 | 0x80070000;
  if ( v17 >= 0 )
    v17 = -2147467259;
  v41 = v17;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
      (unsigned int)v17);
  }
  CloseHandle(SemaphoreW);
  CloseThreadpoolWait(ThreadpoolWait);
  v11 = v17;
LABEL_106:
  CHResultImp::~CHResultImp((CHResultImp *)v40);
  return v11;
}

```

## disassembly

```asm
0x140006720  push    rbp
0x140006722  push    rbx
0x140006723  push    rsi
0x140006724  push    rdi
0x140006725  push    r12
0x140006727  push    r13
0x140006729  push    r14
0x14000672b  push    r15
0x14000672d  lea     rbp, [rsp-188h]
0x140006735  sub     rsp, 288h
0x14000673c  mov     rax, cs:__security_cookie
0x140006743  xor     rax, rsp
0x140006746  mov     [rbp+1C0h+var_50], rax
0x14000674d  mov     rax, gs:58h
0x140006756  mov     rbx, rdx
0x140006759  mov     rsi, cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA; CTieringEngineLib * TieringEngineLibInstance
0x140006760  mov     edx, 8
0x140006765  mov     rcx, [rax]
0x140006768  lea     rax, aCtieringengine_8; "CTieringEngineLib::Initialize"
0x14000676f  mov     [rdx+rcx], rax
0x140006773  lea     rcx, [rsp+2C0h+var_270]; this
0x140006778  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14000677d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006784  lea     r12, WPP_GLOBAL_Control
0x14000678b  lea     r13, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x140006792  mov     r15d, 1
0x140006798  cmp     rcx, r12
0x14000679b  jz      short loc_1400067BC
0x14000679d  test    [rcx+1Ch], r15b
0x1400067a1  jz      short loc_1400067BC
0x1400067a3  cmp     byte ptr [rcx+19h], 4
0x1400067a7  jb      short loc_1400067BC
0x1400067a9  mov     rcx, [rcx+10h]
0x1400067ad  lea     edx, [r15+9]
0x1400067b1  mov     r9, rsi
0x1400067b4  mov     r8, r13
0x1400067b7  call    WPP_SF_q
0x1400067bc  movdqa  xmm0, cs:__xmm@11111111111111111111111111111111
0x1400067c4  lea     rax, aStorageTiersOp; "Storage Tiers Optimization"
0x1400067cb  movdqa  xmm1, cs:__xmm@22222222222222222222222222222222
0x1400067d3  lea     rcx, ?StopEventCallback@CTieringEngineLib@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1400067da  mov     r8, cs:?TieringTpCallbackEnvironment@@3PEAU_TP_CALLBACK_ENVIRON_V3@@EA; pcbe
0x1400067e1  mov     rdx, rsi; pv
0x1400067e4  mov     [rsi+0B0h], rax
0x1400067eb  lea     rax, aMicrosoftWindo; "\\Microsoft\\Windows\\Storage Tiers Man"...
0x1400067f2  mov     [rsi+0B8h], rax
0x1400067f9  mov     [rsi+0A8h], rbx
0x140006800  movups  xmmword ptr cs:?g_DiskTierTestGuid@@3U_GUID@@A.Data1, xmm0; _GUID g_DiskTierTestGuid ...
0x140006807  movups  xmmword ptr cs:?g_FlashTierTestGuid@@3U_GUID@@A.Data1, xmm1; _GUID g_FlashTierTestGuid ...
0x14000680e  call    cs:__imp_CreateThreadpoolWait
0x140006814  xor     r14d, r14d
0x140006817  mov     rbx, rax
0x14000681a  test    rax, rax
0x14000681d  jnz     short loc_14000687F
0x14000681f  call    cs:__imp_GetLastError
0x140006825  mov     ebx, eax
0x140006827  test    eax, eax
0x140006829  jle     short loc_140006834
0x14000682b  movzx   ebx, ax
0x14000682e  or      ebx, 80070000h
0x140006834  test    ebx, ebx
0x140006836  mov     eax, 80004005h
0x14000683b  cmovns  ebx, eax
0x14000683e  mov     [rsp+2C0h+var_268], ebx
0x140006842  mov     rcx, cs:WPP_GLOBAL_Control
0x140006849  cmp     rcx, r12
0x14000684c  jz      loc_140006E38
0x140006852  test    [rcx+1Ch], r15b
0x140006856  jz      loc_140006E38
0x14000685c  cmp     byte ptr [rcx+19h], 2
0x140006860  jb      loc_140006E38
0x140006866  mov     rcx, [rcx+10h]
0x14000686a  mov     edx, 0Bh
0x14000686f  mov     r9d, ebx
0x140006872  mov     r8, r13
0x140006875  call    WPP_SF_d
0x14000687a  jmp     loc_140006E38
0x14000687f  xor     r9d, r9d; lpName
0x140006882  mov     r8d, r15d; lMaximumCount
0x140006885  xor     edx, edx; lInitialCount
0x140006887  xor     ecx, ecx; lpSemaphoreAttributes
0x140006889  call    cs:__imp_CreateSemaphoreW
0x14000688f  mov     rdi, rax
0x140006892  test    rax, rax
0x140006895  jnz     short loc_1400068F6
0x140006897  call    cs:__imp_GetLastError
0x14000689d  mov     edi, eax
0x14000689f  test    eax, eax
0x1400068a1  jle     short loc_1400068AC
0x1400068a3  movzx   edi, ax
0x1400068a6  or      edi, 80070000h
0x1400068ac  test    edi, edi
0x1400068ae  mov     eax, 80004005h
0x1400068b3  cmovns  edi, eax
0x1400068b6  mov     [rsp+2C0h+var_268], edi
0x1400068ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068c1  cmp     rcx, r12
0x1400068c4  jz      short loc_1400068E6
0x1400068c6  test    [rcx+1Ch], r15b
0x1400068ca  jz      short loc_1400068E6
0x1400068cc  cmp     byte ptr [rcx+19h], 2
0x1400068d0  jb      short loc_1400068E6
0x1400068d2  mov     rcx, [rcx+10h]
0x1400068d6  mov     edx, 0Ch
0x1400068db  mov     r9d, edi
0x1400068de  mov     r8, r13
0x1400068e1  call    WPP_SF_d
0x1400068e6  mov     rcx, rbx; pwa
0x1400068e9  call    cs:__imp_CloseThreadpoolWait
0x1400068ef  mov     ebx, edi
0x1400068f1  jmp     loc_140006E38
0x1400068f6  xor     r9d, r9d; lpName
0x1400068f9  xor     r8d, r8d; bInitialState
0x1400068fc  mov     edx, r15d; bManualReset
0x1400068ff  xor     ecx, ecx; lpEventAttributes
0x140006901  call    cs:__imp_CreateEventW
0x140006907  mov     [rsi+0D8h], rax
0x14000690e  test    rax, rax
0x140006911  jnz     short loc_14000697B
0x140006913  call    cs:__imp_GetLastError
0x140006919  mov     esi, eax
0x14000691b  test    eax, eax
0x14000691d  jle     short loc_140006928
0x14000691f  movzx   esi, ax
0x140006922  or      esi, 80070000h
0x140006928  test    esi, esi
0x14000692a  mov     eax, 80004005h
0x14000692f  cmovns  esi, eax
0x140006932  mov     [rsp+2C0h+var_268], esi
0x140006936  mov     rcx, cs:WPP_GLOBAL_Control
0x14000693d  cmp     rcx, r12
0x140006940  jz      short loc_140006962
0x140006942  test    [rcx+1Ch], r15b
0x140006946  jz      short loc_140006962
0x140006948  cmp     byte ptr [rcx+19h], 2
0x14000694c  jb      short loc_140006962
0x14000694e  mov     rcx, [rcx+10h]
0x140006952  mov     edx, 0Dh
0x140006957  mov     r9d, esi
0x14000695a  mov     r8, r13
0x14000695d  call    WPP_SF_d
0x140006962  mov     rcx, rdi; hObject
0x140006965  call    cs:__imp_CloseHandle
0x14000696b  mov     rcx, rbx; pwa
0x14000696e  call    cs:__imp_CloseThreadpoolWait
0x140006974  mov     ebx, esi
0x140006976  jmp     loc_140006E38
0x14000697b  xor     edx, edx; Val
0x14000697d  lea     rcx, [rsp+2C0h+Buffer]; void *
0x140006982  mov     r8d, 208h; Size
0x140006988  call    memset_0
0x14000698d  mov     edx, 104h; uSize
0x140006992  lea     rcx, [rsp+2C0h+Buffer]; lpBuffer
0x140006997  call    cs:__imp_GetSystemWindowsDirectoryW
0x14000699d  test    eax, eax
0x14000699f  jnz     short loc_1400069EB
0x1400069a1  mov     rax, cs:WPP_GLOBAL_Control
0x1400069a8  cmp     rax, r12
0x1400069ab  jz      loc_140006B74
0x1400069b1  test    [rax+1Ch], r15b
0x1400069b5  jz      loc_140006B74
0x1400069bb  cmp     byte ptr [rax+19h], 3
0x1400069bf  jb      loc_140006B74
0x1400069c5  call    cs:__imp_GetLastError
0x1400069cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400069d2  mov     edx, 0Eh
0x1400069d7  mov     rcx, [rcx+10h]
0x1400069db  mov     r8, r13
0x1400069de  mov     r9d, eax
0x1400069e1  call    WPP_SF_d
0x1400069e6  jmp     loc_140006B74
0x1400069eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400069f2  cmp     rcx, r12
0x1400069f5  jz      short loc_140006A19
0x1400069f7  test    [rcx+1Ch], r15b
0x1400069fb  jz      short loc_140006A19
0x1400069fd  cmp     byte ptr [rcx+19h], 4
0x140006a01  jb      short loc_140006A19
0x140006a03  mov     rcx, [rcx+10h]
0x140006a07  lea     r9, [rsp+2C0h+Buffer]
0x140006a0c  mov     edx, 0Fh
0x140006a11  mov     r8, r13
0x140006a14  call    WPP_SF_S
0x140006a19  cmp     [rsp+2C0h+Buffer], r14w
0x140006a1f  jz      loc_140006B74
0x140006a25  cmp     [rsp+2C0h+var_25E], 3Ah ; ':'
0x140006a2b  jnz     loc_140006B74
0x140006a31  cmp     [rsp+2C0h+var_25C], 5Ch ; '\'
0x140006a37  jnz     loc_140006B74
0x140006a3d  movaps  xmm1, xmmword ptr cs:aSystemVolumeIn+10h; "olume Information\\Heat\\"
0x140006a44  lea     rcx, [rsp+2C0h+Buffer]; lpPathName
0x140006a49  movaps  xmm0, xmmword ptr cs:aSystemVolumeIn; "System Volume Information\\Heat\\"
0x140006a50  movups  [rsp+2C0h+var_24A], xmm1
0x140006a55  movups  xmm1, xmmword ptr cs:aSystemVolumeIn+2Eh; "on\\Heat\\"
0x140006a5c  movups  [rsp+2C0h+var_25A], xmm0
0x140006a61  movaps  xmm0, xmmword ptr cs:aSystemVolumeIn+20h; "formation\\Heat\\"
0x140006a68  movups  [rbp+1C0h+var_23A], xmm0
0x140006a6c  movups  [rbp+1C0h+var_23A+0Eh], xmm1
0x140006a70  call    cs:__imp_SetCurrentDirectoryW
0x140006a76  test    eax, eax
0x140006a78  jnz     loc_140006B46
0x140006a7e  call    cs:__imp_GetLastError
0x140006a84  lea     ecx, [rax-2]
0x140006a87  cmp     ecx, r15d
0x140006a8a  jbe     short loc_140006ABA
0x140006a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a93  cmp     rcx, r12
0x140006a96  jz      loc_140006B74
0x140006a9c  test    [rcx+1Ch], r15b
0x140006aa0  jz      loc_140006B74
0x140006aa6  cmp     byte ptr [rcx+19h], 3
0x140006aaa  jb      loc_140006B74
0x140006ab0  mov     edx, 12h
0x140006ab5  jmp     loc_1400069D7
0x140006aba  xor     edx, edx; lpSecurityAttributes
0x140006abc  lea     rcx, [rsp+2C0h+Buffer]; lpPathName
0x140006ac1  call    cs:__imp_CreateDirectoryW
0x140006ac7  test    eax, eax
0x140006ac9  jz      short loc_140006B01
0x140006acb  lea     rcx, [rsp+2C0h+Buffer]; lpPathName
0x140006ad0  call    cs:__imp_SetCurrentDirectoryW
0x140006ad6  test    eax, eax
0x140006ad8  jz      short loc_140006B01
0x140006ada  mov     rcx, cs:WPP_GLOBAL_Control
0x140006ae1  cmp     rcx, r12
0x140006ae4  jz      loc_140006B74
0x140006aea  test    [rcx+1Ch], r15b
0x140006aee  jz      loc_140006B74
0x140006af4  cmp     byte ptr [rcx+19h], 5
0x140006af8  jb      short loc_140006B74
0x140006afa  mov     edx, 11h
0x140006aff  jmp     short loc_140006B63
0x140006b01  mov     rax, cs:WPP_GLOBAL_Control
0x140006b08  cmp     rax, r12
0x140006b0b  jz      short loc_140006B74
0x140006b0d  test    [rax+1Ch], r15b
0x140006b11  jz      short loc_140006B74
0x140006b13  cmp     byte ptr [rax+19h], 3
0x140006b17  jb      short loc_140006B74
0x140006b19  call    cs:__imp_GetLastError
0x140006b1f  lea     rcx, [rsp+2C0h+Buffer]
0x140006b24  mov     edx, 10h
0x140006b29  mov     qword ptr [rsp+2C0h+dwOptions], rcx
0x140006b2e  mov     r9d, eax
0x140006b31  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b38  mov     r8, r13
0x140006b3b  mov     rcx, [rcx+10h]
0x140006b3f  call    WPP_SF_DS
0x140006b44  jmp     short loc_140006B74
0x140006b46  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b4d  cmp     rcx, r12
0x140006b50  jz      short loc_140006B74
0x140006b52  test    [rcx+1Ch], r15b
0x140006b56  jz      short loc_140006B74
0x140006b58  cmp     byte ptr [rcx+19h], 5
0x140006b5c  jb      short loc_140006B74
0x140006b5e  mov     edx, 13h
0x140006b63  mov     rcx, [rcx+10h]
0x140006b67  lea     r9, [rsp+2C0h+Buffer]
0x140006b6c  mov     r8, r13
0x140006b6f  call    WPP_SF_S
0x140006b74  mov     [rsp+2C0h+lpdwDisposition], r14; lpdwDisposition
0x140006b79  lea     rax, [rsi+80h]
0x140006b80  mov     [rsp+2C0h+phkResult], rax; phkResult
0x140006b85  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ti"...
0x140006b8c  mov     [rsp+2C0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x140006b91  xor     r9d, r9d; lpClass
0x140006b94  mov     [rsp+2C0h+samDesired], 20019h; samDesired
0x140006b9c  xor     r8d, r8d; Reserved
0x140006b9f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140006ba6  mov     [rsp+2C0h+dwOptions], r14d; dwOptions
0x140006bab  mov     [rsi+0C8h], rdi
0x140006bb2  mov     [rsi+198h], rbx
0x140006bb9  call    cs:__imp_RegCreateKeyExW
0x140006bbf  test    eax, eax
0x140006bc1  jz      short loc_140006BF1
0x140006bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x140006bca  cmp     rcx, r12
0x140006bcd  jz      loc_140006E30
0x140006bd3  test    [rcx+1Ch], r15b
0x140006bd7  jz      loc_140006E30
0x140006bdd  cmp     byte ptr [rcx+19h], 3
0x140006be1  jb      loc_140006E30
0x140006be7  mov     edx, 14h
0x140006bec  jmp     loc_140006DF9
0x140006bf1  mov     rcx, rsi; this
0x140006bf4  call    ?ReadCurrentRegistrySettings@CTieringEngineLib@@AEAAJXZ; CTieringEngineLib::ReadCurrentRegistrySettings(void)
0x140006bf9  test    eax, eax
0x140006bfb  jz      short loc_140006C29
0x140006bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140006c04  cmp     rcx, r12
0x140006c07  jz      short loc_140006C29
0x140006c09  test    [rcx+1Ch], r15b
0x140006c0d  jz      short loc_140006C29
0x140006c0f  cmp     byte ptr [rcx+19h], 3
0x140006c13  jb      short loc_140006C29
0x140006c15  mov     rcx, [rcx+10h]
0x140006c19  mov     edx, 15h
0x140006c1e  mov     r9d, eax
0x140006c21  mov     r8, r13
  ... truncated ...
```
