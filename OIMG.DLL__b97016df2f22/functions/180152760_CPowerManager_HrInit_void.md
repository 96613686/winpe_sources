# CPowerManager::HrInit(void)

- ea: `0x180152760`
- end: `0x180152ea3`
- name: `?HrInit@CPowerManager@@IEAAJXZ`
- size: `1859`
- prototype: `__int64 __fastcall(CPowerManager *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801521c0`

## callees

- `0x18000b7dc`
- `0x180013080`
- `0x18001373c`
- `0x18001db0c`
- `0x18002ceb0`
- `0x18009bdec`
- `0x18012fb38`
- `0x180152244`
- `0x180152760`
- `0x180152ee4`
- `0x1801532c8`
- `0x1801564f4`
- `0x1801565c4`
- `0x1801568ac`
- `0x1801572fc`
- `0x18056bd00`
- `0x18056d14c`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1801529a3`
- `KERNEL32!SetLastError` at `0x1801529a3`
- `KERNEL32!GetLastError` at `0x180152866`
- `KERNEL32!GetLastError` at `0x1801529c3`
- `KERNEL32!GetLastError` at `0x180152d8c`
- `KERNEL32!GetLastError` at `0x180152866`
- `KERNEL32!GetLastError` at `0x1801529c3`
- `KERNEL32!GetLastError` at `0x180152d8c`
- `KERNEL32!GetCurrentThreadId` at `0x180152802`
- `KERNEL32!GetCurrentThreadId` at `0x180152a51`
- `KERNEL32!GetCurrentThreadId` at `0x180152802`
- `KERNEL32!GetCurrentThreadId` at `0x180152a51`
- `KERNEL32!CloseHandle` at `0x180152b8d`
- `KERNEL32!CloseHandle` at `0x180152bbf`
- `KERNEL32!CloseHandle` at `0x180152d46`
- `KERNEL32!CloseHandle` at `0x180152d5f`
- `KERNEL32!CloseHandle` at `0x180152b8d`
- `KERNEL32!CloseHandle` at `0x180152bbf`
- `KERNEL32!CloseHandle` at `0x180152d46`
- `KERNEL32!CloseHandle` at `0x180152d5f`
- `KERNEL32!SetEvent` at `0x180152b57`
- `KERNEL32!SetEvent` at `0x180152b57`
- `KERNEL32!CreateMemoryResourceNotification` at `0x180152b71`
- `KERNEL32!CreateMemoryResourceNotification` at `0x180152ba3`
- `KERNEL32!CreateMemoryResourceNotification` at `0x180152b71`
- `KERNEL32!CreateMemoryResourceNotification` at `0x180152ba3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180152c04`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180152c04`
- `USER32!RegisterRawInputDevices` at `0x180152943`
- `USER32!RegisterRawInputDevices` at `0x180152943`
- `USER32!SetWindowLongPtrW` at `0x1801529b8`
- `USER32!SetWindowLongPtrW` at `0x1801529b8`
- `USER32!SetWindowsHookExW` at `0x180152d7a`
- `USER32!SetWindowsHookExW` at `0x180152d7a`
- `IMM32!ImmDisableIME` at `0x18015285c`
- `IMM32!ImmDisableIME` at `0x18015285c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPowerManager::HrInit(CPowerManager *this, __int64 a2, __int64 a3)
{
  unsigned int v4; // esi
  unsigned int Dw; // eax
  __int64 Window; // rax
  HWND v7; // rax
  void (*v8)(HWND, unsigned int, unsigned __int64, unsigned int); // r9
  void (*v9)(HWND, unsigned int, unsigned __int64, unsigned int); // r9
  _QWORD *v10; // r12
  HANDLE *v11; // r14
  int v12; // ebx
  int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rcx
  HANDLE MemoryResourceNotification; // rbx
  void *v17; // rcx
  HANDLE v18; // rbx
  void *v19; // rcx
  void *v20; // rcx
  _QWORD *v21; // rax
  _QWORD *v22; // rbx
  __int64 v23; // r14
  __int64 *v24; // r15
  __int64 v25; // rcx
  void (__fastcall *v26)(CPowerManager *, GUID *, _QWORD *); // r14
  __int64 v27; // rdx
  void *v28; // rcx
  HHOOK v29; // rax
  __int64 v31; // rcx
  _QWORD v32[2]; // [rsp+68h] [rbp-69h] BYREF
  WNDCLASSEXW v33; // [rsp+78h] [rbp-59h] BYREF
  RAWINPUTDEVICE pRawInputDevices; // [rsp+C8h] [rbp-9h] BYREF
  __int64 v35; // [rsp+D8h] [rbp+7h]
  __int64 v36; // [rsp+E0h] [rbp+Fh]
  int v37; // [rsp+E8h] [rbp+17h]
  int v38; // [rsp+ECh] [rbp+1Bh]
  HWND v39; // [rsp+F0h] [rbp+1Fh]

  if ( (byte_1806CFC81 & 2) != 0 )
  {
    v32[0] = this;
    v35 = (__int64)v32;
    v36 = 8;
    McGenEventWrite_EventWriteTransfer(guidProviderOfficeThreadpool_Context, PMStartup, a3, 2, &pRawInputDevices);
  }
  if ( *((_QWORD *)this + 21) )
    MsoShipAssertTagProc(4014431);
  if ( *((_BYTE *)this + 403) )
    MsoShipAssertTagProc(4014432);
  *((_BYTE *)this + 403) = 0;
  if ( *((_DWORD *)this + 24) )
    MsoShipAssertTagProc(4014433);
  *((_DWORD *)this + 24) = GetCurrentThreadId();
  memset_0(&v33, 0, sizeof(v33));
  v33.cbSize = 80;
  v33.lpfnWndProc = (WNDPROC)CPowerManager::PowerWndProc;
  v33.lpszClassName = L"OfficePowerManagerWindow";
  if ( !(unsigned __int16)IsolationAwareRegisterClassExW(&v33) )
    goto LABEL_10;
  *((_BYTE *)this + 400) = 1;
  if ( !ImmDisableIME(0) )
    GetLastError();
  Dw = MsoDwRegGetDw((const struct _msoreg *)&OrapiData::Mso::c_msoridDiscardableCacheTimerInterval);
  *((_DWORD *)this + 195) = Dw;
  if ( Dw < 0x2710 )
    *((_DWORD *)this + 195) = 10000;
  *((_DWORD *)this + 194) = MsoDwRegGetDw((const struct _msoreg *)&OrapiData::Mso::c_msoridDiscardableCacheDefaultTimeout);
  *((_DWORD *)this + 196) = MsoDwRegGetDw((const struct _msoreg *)&OrapiData::Mso::c_msoridDiscardableCacheDisableCallbacks);
  *((_DWORD *)this + 197) = MsoDwRegGetDw((const struct _msoreg *)&OrapiData::Mso::c_msoridDiscardableCacheDontQueueCallbacks);
  Window = IsolationAwareCreateWindowExW();
  *((_QWORD *)this + 21) = Window;
  if ( !Window )
    goto LABEL_10;
  *((_QWORD *)this + 61) = MsoDwRegGetDw((const struct _msoreg *)&OrapiData::Mso::c_msoridAppUserIdleTimerInterval);
  *((_QWORD *)this + 60) = MsoDwRegGetDw((const struct _msoreg *)&OrapiData::Mso::c_msoridAppUserIdleResetInterval);
  v7 = (HWND)*((_QWORD *)this + 21);
  *(_QWORD *)&pRawInputDevices.usUsagePage = 131073;
  pRawInputDevices.hwndTarget = v7;
  v35 = 393217;
  v36 = (__int64)v7;
  v37 = 13;
  v38 = 32;
  v39 = v7;
  if ( !RegisterRawInputDevices(&pRawInputDevices, 3u, 0x10u) )
    goto LABEL_10;
  if ( *((_QWORD *)this + 61) > 0xFFFFFFFF )
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  LODWORD(v32[0]) = *((_QWORD *)this + 61);
  HIDWORD(v32[0]) = 4095;
  if ( !MsoSetTimer(
          *((HWND *)this + 21),
          (-(__int64)(*((_BYTE *)this + 404) != 0) & 0x100) + 5,
          (const struct MsoTimeoutInterval *)v32,
          v8) )
    MsoShipAssertTagProc(4014469);
  SetLastError(0);
  if ( !SetWindowLongPtrW(*((HWND *)this + 21), -21, (LONG_PTR)this) )
  {
    if ( GetLastError() )
    {
LABEL_10:
      v4 = -2147467259;
      goto LABEL_75;
    }
  }
  v4 = 0;
  v32[0] = 0x271000001388LL;
  if ( !MsoSetTimer(
          *((HWND *)this + 21),
          (-(__int64)(*((_BYTE *)this + 404) != 0) & 0x100) + 7,
          (const struct MsoTimeoutInterval *)v32,
          v9) )
  {
    MsoShipAssertTagProc(4014471);
    CPowerManager::DoDelayedInit(this);
  }
  v10 = (_QWORD *)((char *)this + 160);
  CPowerFlagsChangeHelper::CPowerFlagsChangeHelper(
    (CPowerFlagsChangeHelper *)&pRawInputDevices,
    *((struct ITpThreadManager **)this + 20),
    this);
  if ( *((_QWORD *)this + 22) )
  {
    v11 = (HANDLE *)((char *)this + 184);
    if ( *((_QWORD *)this + 23) )
    {
      if ( !*((_BYTE *)this + 402) )
      {
        v12 = *((_DWORD *)this + 24);
        if ( v12 != GetCurrentThreadId() && !*((_BYTE *)this + 403) )
        {
          if ( *v10 )
          {
            if ( *((_BYTE *)this + 402) )
              goto LABEL_42;
            if ( BYTE4(v36) )
            {
              *(_DWORD *)&pRawInputDevices.usUsagePage = *(_DWORD *)&pRawInputDevices.usUsagePage & 0xFFFFFFF0
                                                       | CPowerManager::GetPowerSource(pRawInputDevices.usUsagePage & 0xF)
                                                       & 0xF;
              (*(void (__fastcall **)(__int64, RAWINPUTDEVICE *, _QWORD))(*(_QWORD *)v35 + 192LL))(
                v35,
                &pRawInputDevices,
                0);
            }
            if ( *((_BYTE *)this + 401) )
              goto LABEL_42;
            v32[0] = 0;
            if ( (unsigned __int8)Mso::ComUtil::FQueryFrom<ITpThreadManagerInternal,ITpThreadManager *>(
                                    v32,
                                    (char *)this + 160) )
            {
              if ( !v32[0] )
                CrashWithRecovery(0x1E3C3840u, 0);
              v13 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v32[0] + 224LL))(v32[0]);
              if ( v13 >= 0 )
              {
                *((_BYTE *)this + 401) = 1;
                v15 = v32[0];
                if ( v32[0] )
                {
                  v32[0] = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
                }
              }
              else
              {
                v14 = v32[0];
                if ( v32[0] )
                {
                  v32[0] = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                }
              }
              if ( v13 >= 0 )
                goto LABEL_42;
            }
            else
            {
              v31 = v32[0];
              if ( v32[0] )
              {
                v32[0] = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
              }
            }
          }
          MsoShipAssertTagProc(4014607);
        }
      }
LABEL_42:
      if ( (pRawInputDevices.usUsagePage & 0x800) != 0 )
        v11 = (HANDLE *)((char *)this + 176);
      SetEvent(*v11);
    }
  }
  *(_WORD *)((char *)this + 401) = 257;
  CPowerFlagsChangeHelper::~CPowerFlagsChangeHelper((CPowerFlagsChangeHelper *)&pRawInputDevices);
  MemoryResourceNotification = CreateMemoryResourceNotification(LowMemoryResourceNotification);
  v17 = (void *)*((_QWORD *)this + 62);
  if ( v17 )
  {
    *((_QWORD *)this + 62) = 0;
    CloseHandle(v17);
  }
  *((_QWORD *)this + 62) = MemoryResourceNotification;
  v18 = CreateMemoryResourceNotification(HighMemoryResourceNotification);
  v19 = (void *)*((_QWORD *)this + 63);
  if ( v19 )
  {
    *((_QWORD *)this + 63) = 0;
    CloseHandle(v19);
  }
  *((_QWORD *)this + 63) = v18;
  if ( !*((_QWORD *)this + 62) || !v18 )
    MsoShipAssertTagProc(4014472);
  v20 = (void *)*((_QWORD *)this + 62);
  if ( !v20 )
    goto LABEL_70;
  if ( !*((_QWORD *)this + 63) )
  {
    *((_QWORD *)this + 62) = 0;
    CloseHandle(v20);
LABEL_70:
    v28 = (void *)*((_QWORD *)this + 63);
    if ( v28 )
    {
      *((_QWORD *)this + 63) = 0;
      CloseHandle(v28);
    }
    goto LABEL_72;
  }
  v21 = malloc(0x28u);
  v22 = v21;
  if ( v21 )
  {
    v23 = *v10;
    *v21 = &IMsoDebugMessage::`vftable';
    *((_DWORD *)v21 + 2) = 1;
    *v21 = &CMemoryCallBack::`vftable'{for `CTpBase'};
    v21[2] = &CMemoryCallBack::`vftable'{for `ITpWaitCallback'};
    v21[3] = 0;
    v24 = v21 + 4;
    v21[4] = 0;
    if ( v23 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
      v25 = v22[3];
      if ( v25 )
      {
        v22[3] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      v22[3] = v23;
    }
    v26 = **(void (__fastcall ***)(CPowerManager *, GUID *, _QWORD *))this;
    v27 = *v24;
    if ( *v24 )
    {
      *v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v26(this, &GUID_b5e344c4_1b82_4498_921a_e9a5a6230b8f, v22 + 4);
  }
  else
  {
    v22 = 0;
  }
  if ( !v22 )
  {
    MsoShipAssertTagProc(4014473);
LABEL_65:
    if ( !(*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 88LL))(*v10) )
      MsoShipAssertTagProc(4014474);
    goto LABEL_67;
  }
  if ( (*(int (__fastcall **)(_QWORD, __int64, _QWORD *, char *))(*(_QWORD *)*v10 + 40LL))(
         *v10,
         8449,
         v22 + 2,
         (char *)this + 512) < 0 )
    goto LABEL_65;
  (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 64) + 216LL))(
    *((_QWORD *)this + 64),
    *((_QWORD *)this + 62),
    0xFFFFFFFFLL);
LABEL_67:
  if ( v22 )
    (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
LABEL_72:
  v29 = SetWindowsHookExW(5, PowerManagerWindowHook, 0, Mso::Threadpool::details::vdwTidMain);
  *((_QWORD *)this + 99) = v29;
  if ( !v29 && !GetLastError() )
    MsoShipAssertTagProc(4014475);
LABEL_75:
  if ( !*((_BYTE *)this + 402) )
    CPowerManager::UnInit(this);
  return v4;
}

```

## disassembly

```asm
0x180152760  mov     rax, rsp
0x180152763  mov     [rax+10h], rbx
0x180152767  mov     [rax+18h], rsi
0x18015276b  mov     [rax+20h], rdi
0x18015276f  push    rbp
0x180152770  push    r12
0x180152772  push    r13
0x180152774  push    r14
0x180152776  push    r15
0x180152778  lea     rbp, [rax-5Fh]
0x18015277c  sub     rsp, 100h
0x180152783  mov     rax, cs:__security_cookie
0x18015278a  xor     rax, rsp
0x18015278d  mov     [rbp+57h+var_30], rax
0x180152791  mov     rdi, rcx
0x180152794  xor     r13d, r13d
0x180152797  lea     esi, [r13+2]
0x18015279b  test    cs:byte_1806CFC81, sil
0x1801527a2  jz      short loc_1801527D7
0x1801527a4  mov     [rbp+57h+var_C0], rcx
0x1801527a8  lea     rax, [rbp+57h+var_C0]
0x1801527ac  mov     [rbp+57h+var_50], rax
0x1801527b0  mov     [rbp+57h+var_48], 8
0x1801527b8  lea     rax, [rbp+57h+pRawInputDevices]
0x1801527bc  mov     [rsp+120h+var_100], rax
0x1801527c1  mov     r9d, esi
0x1801527c4  lea     rdx, PMStartup
0x1801527cb  lea     rcx, guidProviderOfficeThreadpool_Context
0x1801527d2  call    McGenEventWrite_EventWriteTransfer
0x1801527d7  cmp     [rdi+0A8h], r13
0x1801527de  jnz     loc_180152E11
0x1801527e4  cmp     [rdi+193h], r13b
0x1801527eb  jnz     loc_180152E20
0x1801527f1  mov     [rdi+193h], r13b
0x1801527f8  cmp     [rdi+60h], r13d
0x1801527fc  jnz     loc_180152E2F
0x180152802  call    cs:__imp_GetCurrentThreadId
0x180152808  mov     [rdi+60h], eax
0x18015280b  mov     ebx, 50h ; 'P'
0x180152810  mov     r8d, ebx; Size
0x180152813  xor     edx, edx; Val
0x180152815  lea     rcx, [rbp+57h+var_B0]; void *
0x180152819  call    memset_0
0x18015281e  mov     [rbp+57h+var_B0.cbSize], ebx
0x180152821  lea     rax, ?PowerWndProc@CPowerManager@@KA_JPEAUHWND__@@I_K_J@Z; CPowerManager::PowerWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180152828  mov     [rbp+57h+var_B0.lpfnWndProc], rax
0x18015282c  lea     rax, ?c_szPowerManagerWindowClassName@@3QB_WB; "OfficePowerManagerWindow"
0x180152833  mov     [rbp+57h+var_B0.lpszClassName], rax
0x180152837  lea     rcx, [rbp+57h+var_B0]; WNDCLASSEXW *
0x18015283b  call    IsolationAwareRegisterClassExW
0x180152840  test    ax, ax
0x180152843  jnz     short loc_18015284F
0x180152845  mov     esi, 80004005h
0x18015284a  jmp     loc_180152D96
0x18015284f  mov     ebx, 1
0x180152854  mov     [rdi+190h], bl
0x18015285a  xor     ecx, ecx; DWORD
0x18015285c  call    cs:__imp_ImmDisableIME
0x180152862  test    eax, eax
0x180152864  jnz     short loc_18015286C
0x180152866  call    cs:__imp_GetLastError
0x18015286c  lea     rcx, ?c_msoridDiscardableCacheTimerInterval@Mso@OrapiData@@3U_msoreg@@B; struct _msoreg *
0x180152873  call    ?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x180152878  mov     [rdi+30Ch], eax
0x18015287e  mov     r14d, 2710h
0x180152884  cmp     eax, r14d
0x180152887  jnb     short loc_180152890
0x180152889  mov     [rdi+30Ch], r14d
0x180152890  lea     rcx, ?c_msoridDiscardableCacheDefaultTimeout@Mso@OrapiData@@3U_msoreg@@B; struct _msoreg *
0x180152897  call    ?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x18015289c  mov     [rdi+308h], eax
0x1801528a2  lea     rcx, ?c_msoridDiscardableCacheDisableCallbacks@Mso@OrapiData@@3U_msoreg@@B; struct _msoreg *
0x1801528a9  call    ?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x1801528ae  mov     [rdi+310h], eax
0x1801528b4  lea     rcx, ?c_msoridDiscardableCacheDontQueueCallbacks@Mso@OrapiData@@3U_msoreg@@B; struct _msoreg *
0x1801528bb  call    ?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x1801528c0  mov     [rdi+314h], eax
0x1801528c6  call    IsolationAwareCreateWindowExW
0x1801528cb  mov     [rdi+0A8h], rax
0x1801528d2  test    rax, rax
0x1801528d5  jz      loc_180152845
0x1801528db  lea     rcx, ?c_msoridAppUserIdleTimerInterval@Mso@OrapiData@@3U_msoreg@@B; struct _msoreg *
0x1801528e2  call    ?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x1801528e7  mov     eax, eax
0x1801528e9  mov     [rdi+1E8h], rax
0x1801528f0  lea     rcx, ?c_msoridAppUserIdleResetInterval@Mso@OrapiData@@3U_msoreg@@B; struct _msoreg *
0x1801528f7  call    ?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x1801528fc  mov     eax, eax
0x1801528fe  mov     [rdi+1E0h], rax
0x180152905  mov     rax, [rdi+0A8h]
0x18015290c  mov     qword ptr [rbp+57h+pRawInputDevices.usUsagePage], 20001h
0x180152914  mov     [rbp+57h+pRawInputDevices.hwndTarget], rax
0x180152918  mov     [rbp+57h+var_50], 60001h
0x180152920  mov     [rbp+57h+var_48], rax
0x180152924  mov     [rbp+57h+var_40], 0Dh
0x18015292b  mov     [rbp+57h+var_3C], 20h ; ' '
0x180152932  mov     [rbp+57h+var_38], rax
0x180152936  mov     edx, 3; uiNumDevices
0x18015293b  lea     r8d, [rdx+0Dh]; cbSize
0x18015293f  lea     rcx, [rbp+57h+pRawInputDevices]; pRawInputDevices
0x180152943  call    cs:__imp_RegisterRawInputDevices
0x180152949  test    eax, eax
0x18015294b  jz      loc_180152845
0x180152951  mov     rax, [rdi+1E8h]
0x180152958  mov     ecx, 0FFFFFFFFh
0x18015295d  cmp     rax, rcx
0x180152960  ja      loc_180152E0B
0x180152966  mov     dword ptr [rbp+57h+var_C0], eax
0x180152969  mov     dword ptr [rbp+57h+var_C0+4], 0FFFh
0x180152970  mov     al, [rdi+194h]
0x180152976  neg     al
0x180152978  sbb     rdx, rdx
0x18015297b  mov     r15d, 100h
0x180152981  and     rdx, r15
0x180152984  add     rdx, 5; unsigned __int64
0x180152988  lea     r8, [rbp+57h+var_C0]; struct MsoTimeoutInterval *
0x18015298c  mov     rcx, [rdi+0A8h]; HWND
0x180152993  call    ?MsoSetTimer@@YA_KPEAUHWND__@@_KAEBUMsoTimeoutInterval@@P6AX0I1K@Z@Z; MsoSetTimer(HWND__ *,unsigned __int64,MsoTimeoutInterval const &,void (*)(HWND__ *,uint,unsigned __int64,ulong))
0x180152998  test    rax, rax
0x18015299b  jz      loc_180152E3E
0x1801529a1  xor     ecx, ecx; dwErrCode
0x1801529a3  call    cs:__imp_SetLastError
0x1801529a9  mov     r8, rdi; dwNewLong
0x1801529ac  mov     edx, 0FFFFFFEBh; nIndex
0x1801529b1  mov     rcx, [rdi+0A8h]; hWnd
0x1801529b8  call    cs:__imp_SetWindowLongPtrW
0x1801529be  test    rax, rax
0x1801529c1  jnz     short loc_1801529D1
0x1801529c3  call    cs:__imp_GetLastError
0x1801529c9  test    eax, eax
0x1801529cb  jnz     loc_180152845
0x1801529d1  mov     esi, r13d
0x1801529d4  mov     dword ptr [rbp+57h+var_C0], 1388h
0x1801529db  mov     dword ptr [rbp+57h+var_C0+4], r14d
0x1801529df  mov     al, [rdi+194h]
0x1801529e5  neg     al
0x1801529e7  sbb     rdx, rdx
0x1801529ea  and     rdx, r15
0x1801529ed  add     rdx, 7; unsigned __int64
0x1801529f1  lea     r8, [rbp+57h+var_C0]; struct MsoTimeoutInterval *
0x1801529f5  mov     rcx, [rdi+0A8h]; HWND
0x1801529fc  call    ?MsoSetTimer@@YA_KPEAUHWND__@@_KAEBUMsoTimeoutInterval@@P6AX0I1K@Z@Z; MsoSetTimer(HWND__ *,unsigned __int64,MsoTimeoutInterval const &,void (*)(HWND__ *,uint,unsigned __int64,ulong))
0x180152a01  test    rax, rax
0x180152a04  jz      loc_180152E4D
0x180152a0a  lea     r12, [rdi+0A0h]
0x180152a11  mov     r8, rdi; struct ITpPowerManagerInternal *
0x180152a14  mov     rdx, [r12]; struct ITpThreadManager *
0x180152a18  lea     rcx, [rbp+57h+pRawInputDevices]; this
0x180152a1c  call    ??0CPowerFlagsChangeHelper@@QEAA@PEAUITpThreadManager@@PEAUITpPowerManagerInternal@@@Z; CPowerFlagsChangeHelper::CPowerFlagsChangeHelper(ITpThreadManager *,ITpPowerManagerInternal *)
0x180152a21  lea     r15, [rdi+0B0h]
0x180152a28  cmp     [r15], r13
0x180152a2b  jz      loc_180152B5D
0x180152a31  lea     r14, [rdi+0B8h]
0x180152a38  cmp     [r14], r13
0x180152a3b  jz      loc_180152B5D
0x180152a41  cmp     [rdi+192h], r13b
0x180152a48  jnz     loc_180152B48
0x180152a4e  mov     ebx, [rdi+60h]
0x180152a51  call    cs:__imp_GetCurrentThreadId
0x180152a57  cmp     ebx, eax
0x180152a59  jz      loc_180152B43
0x180152a5f  cmp     [rdi+193h], r13b
0x180152a66  jnz     loc_180152B43
0x180152a6c  cmp     [r12], r13
0x180152a70  jz      loc_180152DFC
0x180152a76  cmp     [rdi+192h], r13b
0x180152a7d  jnz     loc_180152B43
0x180152a83  cmp     byte ptr [rbp+57h+var_48+4], r13b
0x180152a87  jz      short loc_180152ABD
0x180152a89  mov     ecx, dword ptr [rbp+57h+pRawInputDevices.usUsagePage]
0x180152a8c  and     ecx, 0Fh
0x180152a8f  call    ?GetPowerSource@CPowerManager@@KA?AW4ePowerSource@@W42@@Z; CPowerManager::GetPowerSource(ePowerSource)
0x180152a94  and     eax, 0Fh
0x180152a97  mov     ecx, dword ptr [rbp+57h+pRawInputDevices.usUsagePage]
0x180152a9a  and     ecx, 0FFFFFFF0h
0x180152a9d  or      eax, ecx
0x180152a9f  mov     dword ptr [rbp+57h+pRawInputDevices.usUsagePage], eax
0x180152aa2  mov     rcx, [rbp+57h+var_50]
0x180152aa6  mov     rax, [rcx]
0x180152aa9  xor     r8d, r8d
0x180152aac  lea     rdx, [rbp+57h+pRawInputDevices]
0x180152ab0  mov     rax, [rax+0C0h]
0x180152ab7  call    cs:__guard_dispatch_icall_fptr
0x180152abd  cmp     [rdi+191h], r13b
0x180152ac4  jnz     short loc_180152B43
0x180152ac6  mov     [rbp+57h+var_C0], r13
0x180152aca  mov     rdx, r12
0x180152acd  lea     rcx, [rbp+57h+var_C0]
0x180152ad1  call    ??$FQueryFrom@UITpThreadManagerInternal@@PEAUITpThreadManager@@@ComUtil@Mso@@YA_NAEAV?$TCntPtr@UITpThreadManagerInternal@@@1@AEBQEAUITpThreadManager@@AEBU_GUID@@@Z; Mso::ComUtil::FQueryFrom<ITpThreadManagerInternal,ITpThreadManager *>(Mso::TCntPtr<ITpThreadManagerInternal> &,ITpThreadManager * const &,_GUID const &)
0x180152ad6  test    al, al
0x180152ad8  jz      loc_180152DE2
0x180152ade  mov     rcx, [rbp+57h+var_C0]
0x180152ae2  test    rcx, rcx
0x180152ae5  jz      loc_180152E64
0x180152aeb  mov     rax, [rcx]
0x180152aee  mov     rax, [rax+0E0h]
0x180152af5  call    cs:__guard_dispatch_icall_fptr
0x180152afb  mov     ebx, eax
0x180152afd  test    eax, eax
0x180152aff  jns     short loc_180152B1A
0x180152b01  mov     rdx, [rbp+57h+var_C0]
0x180152b05  test    rdx, rdx
0x180152b08  jz      short loc_180152B3B
0x180152b0a  mov     [rbp+57h+var_C0], r13
0x180152b0e  mov     rcx, [rdx]
0x180152b11  mov     rax, [rcx+10h]
0x180152b15  mov     rcx, rdx
0x180152b18  jmp     short loc_180152B35
0x180152b1a  mov     byte ptr [rdi+191h], 1
0x180152b21  mov     rcx, [rbp+57h+var_C0]
0x180152b25  test    rcx, rcx
0x180152b28  jz      short loc_180152B3B
0x180152b2a  mov     [rbp+57h+var_C0], r13
0x180152b2e  mov     rax, [rcx]
0x180152b31  mov     rax, [rax+10h]
0x180152b35  call    cs:__guard_dispatch_icall_fptr
0x180152b3b  test    ebx, ebx
0x180152b3d  js      loc_180152DFC
0x180152b43  mov     ebx, 1
0x180152b48  mov     eax, dword ptr [rbp+57h+pRawInputDevices.usUsagePage]
0x180152b4b  shr     eax, 0Bh
0x180152b4e  test    bl, al
0x180152b50  cmovnz  r14, r15
0x180152b54  mov     rcx, [r14]; hEvent
0x180152b57  call    cs:__imp_SetEvent
0x180152b5d  mov     word ptr [rdi+191h], 101h
0x180152b66  lea     rcx, [rbp+57h+pRawInputDevices]; this
0x180152b6a  call    ??1CPowerFlagsChangeHelper@@QEAA@XZ; CPowerFlagsChangeHelper::~CPowerFlagsChangeHelper(void)
0x180152b6f  xor     ecx, ecx; NotificationType
0x180152b71  call    cs:__imp_CreateMemoryResourceNotification
0x180152b77  mov     rbx, rax
0x180152b7a  mov     rcx, [rdi+1F0h]; hObject
0x180152b81  test    rcx, rcx
0x180152b84  jz      short loc_180152B93
0x180152b86  mov     [rdi+1F0h], r13
0x180152b8d  call    cs:__imp_CloseHandle
0x180152b93  mov     [rdi+1F0h], rbx
0x180152b9a  mov     r15d, 1
0x180152ba0  mov     ecx, r15d; NotificationType
0x180152ba3  call    cs:__imp_CreateMemoryResourceNotification
0x180152ba9  mov     rbx, rax
0x180152bac  mov     rcx, [rdi+1F8h]; hObject
0x180152bb3  test    rcx, rcx
0x180152bb6  jz      short loc_180152BC5
0x180152bb8  mov     [rdi+1F8h], r13
0x180152bbf  call    cs:__imp_CloseHandle
0x180152bc5  mov     [rdi+1F8h], rbx
0x180152bcc  cmp     [rdi+1F0h], r13
0x180152bd3  jz      loc_180152E75
0x180152bd9  test    rbx, rbx
0x180152bdc  jz      loc_180152E75
0x180152be2  mov     rcx, [rdi+1F0h]; hObject
0x180152be9  test    rcx, rcx
0x180152bec  jz      loc_180152D4C
0x180152bf2  cmp     [rdi+1F8h], r13
0x180152bf9  jz      loc_180152D3A
0x180152bff  mov     ecx, 28h ; '('; Size
0x180152c04  call    cs:__imp_malloc
0x180152c0a  mov     rbx, rax
0x180152c0d  test    rax, rax
0x180152c10  jz      loc_180152CB4
0x180152c16  mov     r14, [r12]
0x180152c1a  lea     rax, ??_7IMsoDebugMessage@@6B@; const IMsoDebugMessage::`vftable'
0x180152c21  mov     [rbx], rax
0x180152c24  mov     [rbx+8], r15d
0x180152c28  lea     rax, ??_7CMemoryCallBack@@6BCTpBase@@@; const CMemoryCallBack::`vftable'{for `CTpBase'}
0x180152c2f  mov     [rbx], rax
0x180152c32  lea     rax, ??_7CMemoryCallBack@@6BITpWaitCallback@@@; const CMemoryCallBack::`vftable'{for `ITpWaitCallback'}
0x180152c39  mov     [rbx+10h], rax
0x180152c3d  mov     [rbx+18h], r13
0x180152c41  lea     r15, [rbx+20h]
0x180152c45  mov     [r15], r13
0x180152c48  test    r14, r14
0x180152c4b  jz      short loc_180152C7B
0x180152c4d  mov     rax, [r14]
0x180152c50  mov     rcx, r14
0x180152c53  mov     rax, [rax+8]
0x180152c57  call    cs:__guard_dispatch_icall_fptr
0x180152c5d  mov     rcx, [rbx+18h]
0x180152c61  test    rcx, rcx
0x180152c64  jz      short loc_180152C77
0x180152c66  mov     [rbx+18h], r13
0x180152c6a  mov     rax, [rcx]
0x180152c6d  mov     rax, [rax+10h]
0x180152c71  call    cs:__guard_dispatch_icall_fptr
0x180152c77  mov     [rbx+18h], r14
0x180152c7b  mov     rax, [rdi]
0x180152c7e  mov     r14, [rax]
0x180152c81  mov     rdx, [r15]
0x180152c84  test    rdx, rdx
0x180152c87  jz      short loc_180152C9C
0x180152c89  mov     [r15], r13
0x180152c8c  mov     rcx, [rdx]
0x180152c8f  mov     rax, [rcx+10h]
0x180152c93  mov     rcx, rdx
0x180152c96  call    cs:__guard_dispatch_icall_fptr
0x180152c9c  mov     r8, r15
0x180152c9f  lea     rdx, _GUID_b5e344c4_1b82_4498_921a_e9a5a6230b8f
0x180152ca6  mov     rcx, rdi
0x180152ca9  mov     rax, r14
  ... truncated ...
```
