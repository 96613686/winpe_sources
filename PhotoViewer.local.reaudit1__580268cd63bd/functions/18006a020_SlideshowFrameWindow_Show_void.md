# SlideshowFrameWindow::Show(void)

- ea: `0x18006a020`
- end: `0x18006a226`
- name: `?Show@SlideshowFrameWindow@@UEAAJXZ`
- size: `518`
- prototype: `__int64 __fastcall(SlideshowFrameWindow *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180021a90`
- `0x180021ab8`
- `0x180068028`
- `0x18006866c`
- `0x180069e40`
- `0x180069f18`
- `0x18006a020`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18006a1a4`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18006a1a4`
- `KERNEL32!SetThreadExecutionState` at `0x18006a0a1`
- `KERNEL32!SetThreadExecutionState` at `0x18006a202`
- `KERNEL32!SetThreadExecutionState` at `0x18006a0a1`
- `KERNEL32!SetThreadExecutionState` at `0x18006a202`
- `KERNEL32!GetCurrentThreadId` at `0x18006a134`
- `KERNEL32!GetCurrentThreadId` at `0x18006a134`
- `KERNEL32!LeaveCriticalSection` at `0x18006a151`
- `KERNEL32!LeaveCriticalSection` at `0x18006a151`
- `USER32!SystemParametersInfoW` at `0x18006a070`
- `USER32!SystemParametersInfoW` at `0x18006a070`
- `USER32!IsWindow` at `0x18006a0ae`
- `USER32!IsWindow` at `0x18006a0ae`
- `USER32!ShowWindow` at `0x18006a1e2`
- `USER32!ShowWindow` at `0x18006a1e2`
- `USER32!SetTimer` at `0x18006a056`
- `USER32!SetTimer` at `0x18006a096`
- `USER32!SetTimer` at `0x18006a056`
- `USER32!SetTimer` at `0x18006a096`
- `dwmapi!DwmSetWindowAttribute` at `0x18006a0d4`
- `dwmapi!DwmSetWindowAttribute` at `0x18006a0d4`

## pseudocode

```c
__int64 __fastcall SlideshowFrameWindow::Show(SlideshowFrameWindow *this)
{
  unsigned int v3; // eax
  void *v4; // rbx
  int v5; // ecx
  unsigned int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rdx
  unsigned __int64 *v9; // r8
  WTL::CAppModule *v10; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-29h] BYREF
  char v12; // [rsp+28h] [rbp-21h]
  void **v13; // [rsp+30h] [rbp-19h] BYREF
  __int64 v14; // [rsp+38h] [rbp-11h]
  __int64 v15; // [rsp+40h] [rbp-9h]
  __int64 v16; // [rsp+48h] [rbp-1h]
  __int64 v17; // [rsp+50h] [rbp+7h]
  unsigned int pvParam; // [rsp+B0h] [rbp+67h] BYREF
  DWORD pvAttribute; // [rsp+B8h] [rbp+6Fh] BYREF
  void ***v20; // [rsp+C0h] [rbp+77h] BYREF

  if ( !*((_BYTE *)this + 16) )
    return 2147500037LL;
  SetTimer(*((HWND *)this - 14), 2u, 0x64u, 0);
  pvParam = 60;
  SystemParametersInfoW(0xEu, 0, &pvParam, 0);
  v3 = pvParam;
  if ( pvParam < 0x3C )
  {
    v3 = 60;
    pvParam = 60;
  }
  SetTimer(*((HWND *)this - 14), 3u, 1000 * (v3 >> 1), 0);
  SetThreadExecutionState(0x80000001);
  if ( IsWindow(*((HWND *)this + 19)) )
  {
    pvAttribute = 1;
    DwmSetWindowAttribute(*((HWND *)this + 19), 7u, &pvAttribute, 4u);
  }
  v13 = &WTL::CMessageLoop::`vftable';
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v20 = &v13;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24);
  v12 = 0;
  if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&lpCriticalSection) >= 0 )
  {
    v4 = qword_1800A3DD8;
    pvAttribute = GetCurrentThreadId();
    ATL::CSimpleMap<unsigned long,WTL::CMessageLoop *,ATL::CSimpleMapEqualHelper<unsigned long,WTL::CMessageLoop *>>::Add(
      v4,
      &pvAttribute,
      &v20);
    LeaveCriticalSection(lpCriticalSection);
    v12 = 0;
  }
  ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&lpCriticalSection);
  v5 = v15;
  if ( (_DWORD)v15 != HIDWORD(v15) )
  {
    v8 = v14;
    goto LABEL_17;
  }
  if ( HIDWORD(v15) )
  {
    v6 = 2 * v15;
    if ( (v15 & 0x40000000) != 0 )
      goto LABEL_20;
  }
  else
  {
    v6 = 1;
  }
  if ( v6 <= 0xFFFFFFFuLL )
  {
    v7 = _o__recalloc(v14, v6, 8);
    v8 = v7;
    if ( v7 )
    {
      HIDWORD(v15) = v6;
      v14 = v7;
      v5 = v15;
LABEL_17:
      v9 = (unsigned __int64 *)(v8 + 8LL * v5);
      if ( v9 )
      {
        *v9 = ((unsigned __int64)this + 24) & -(__int64)(this != (SlideshowFrameWindow *)120);
        v5 = v15;
      }
      LODWORD(v15) = v5 + 1;
    }
  }
LABEL_20:
  ShowWindow(*((HWND *)this - 14), 1);
  *((_BYTE *)this + 281) = 1;
  WTL::CMessageLoop::Run((WTL::CMessageLoop *)&v13);
  WTL::CAppModule::RemoveMessageLoop(v10);
  SetThreadExecutionState(0x80000000);
  WTL::CMessageLoop::~CMessageLoop((WTL::CMessageLoop *)&v13);
  return 0;
}

```

## disassembly

```asm
0x18006a020  mov     [rsp-8+arg_18], rbx
0x18006a025  push    rbp
0x18006a026  push    rsi
0x18006a027  push    rdi
0x18006a028  lea     rbp, [rsp-47h]
0x18006a02d  sub     rsp, 90h
0x18006a034  mov     rdi, rcx
0x18006a037  cmp     byte ptr [rcx+10h], 0
0x18006a03b  jnz     short loc_18006A047
0x18006a03d  mov     eax, 80004005h
0x18006a042  jmp     loc_18006A213
0x18006a047  xor     r9d, r9d; lpTimerFunc
0x18006a04a  lea     edx, [r9+2]; nIDEvent
0x18006a04e  lea     r8d, [r9+64h]; uElapse
0x18006a052  mov     rcx, [rcx-70h]; hWnd
0x18006a056  call    cs:__imp_SetTimer
0x18006a05c  mov     ebx, 3Ch ; '<'
0x18006a061  mov     [rbp+57h+pvParam], ebx
0x18006a064  xor     r9d, r9d; fWinIni
0x18006a067  lea     r8, [rbp+57h+pvParam]; pvParam
0x18006a06b  xor     edx, edx; uiParam
0x18006a06d  lea     ecx, [rbx-2Eh]; uiAction
0x18006a070  call    cs:__imp_SystemParametersInfoW
0x18006a076  mov     eax, [rbp+57h+pvParam]
0x18006a079  cmp     eax, ebx
0x18006a07b  jnb     short loc_18006A082
0x18006a07d  mov     eax, ebx
0x18006a07f  mov     [rbp+57h+pvParam], ebx
0x18006a082  shr     eax, 1
0x18006a084  imul    r8d, eax, 3E8h; uElapse
0x18006a08b  xor     r9d, r9d; lpTimerFunc
0x18006a08e  lea     edx, [r9+3]; nIDEvent
0x18006a092  mov     rcx, [rdi-70h]; hWnd
0x18006a096  call    cs:__imp_SetTimer
0x18006a09c  mov     ecx, 80000001h; esFlags
0x18006a0a1  call    cs:__imp_SetThreadExecutionState
0x18006a0a7  mov     rcx, [rdi+98h]; hWnd
0x18006a0ae  call    cs:__imp_IsWindow
0x18006a0b4  test    eax, eax
0x18006a0b6  jz      short loc_18006A0DA
0x18006a0b8  mov     [rbp+57h+pvAttribute], 1
0x18006a0bf  mov     r9d, 4; cbAttribute
0x18006a0c5  lea     r8, [rbp+57h+pvAttribute]; pvAttribute
0x18006a0c9  lea     edx, [r9+3]; dwAttribute
0x18006a0cd  mov     rcx, [rdi+98h]; hwnd
0x18006a0d4  call    cs:__imp_DwmSetWindowAttribute
0x18006a0da  lea     rax, ??_7CMessageLoop@WTL@@6B@; const WTL::CMessageLoop::`vftable'
0x18006a0e1  mov     [rbp+57h+var_70], rax
0x18006a0e5  mov     [rbp+57h+var_68], 0
0x18006a0ed  mov     [rbp+57h+var_60], 0
0x18006a0f5  mov     [rbp+57h+var_58], 0
0x18006a0fd  mov     [rbp+57h+var_50], 0
0x18006a105  lea     rax, [rbp+57h+var_70]
0x18006a109  mov     [rbp+57h+arg_10], rax
0x18006a10d  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18006a114  add     rax, 18h
0x18006a118  mov     [rbp+57h+lpCriticalSection], rax
0x18006a11c  mov     [rbp+57h+var_78], 0
0x18006a120  lea     rcx, [rbp+57h+lpCriticalSection]
0x18006a124  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18006a129  test    eax, eax
0x18006a12b  js      short loc_18006A15B
0x18006a12d  mov     rbx, cs:qword_1800A3DD8
0x18006a134  call    cs:__imp_GetCurrentThreadId
0x18006a13a  mov     [rbp+57h+pvAttribute], eax
0x18006a13d  lea     r8, [rbp+57h+arg_10]
0x18006a141  lea     rdx, [rbp+57h+pvAttribute]
0x18006a145  mov     rcx, rbx
0x18006a148  call    ?Add@?$CSimpleMap@KPEAVCMessageLoop@WTL@@V?$CSimpleMapEqualHelper@KPEAVCMessageLoop@WTL@@@ATL@@@ATL@@QEAAHAEBKAEBQEAVCMessageLoop@WTL@@@Z; ATL::CSimpleMap<ulong,WTL::CMessageLoop *,ATL::CSimpleMapEqualHelper<ulong,WTL::CMessageLoop *>>::Add(ulong const &,WTL::CMessageLoop * const &)
0x18006a14d  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18006a151  call    cs:__imp_LeaveCriticalSection
0x18006a157  mov     [rbp+57h+var_78], 0
0x18006a15b  lea     rcx, [rbp+57h+lpCriticalSection]; this
0x18006a15f  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x18006a164  lea     rax, [rdi-78h]
0x18006a168  lea     rcx, [rdi+18h]
0x18006a16c  neg     rax
0x18006a16f  sbb     rsi, rsi
0x18006a172  and     rsi, rcx
0x18006a175  mov     eax, dword ptr [rbp+57h+var_60+4]
0x18006a178  mov     ecx, dword ptr [rbp+57h+var_60]
0x18006a17b  cmp     ecx, eax
0x18006a17d  jnz     short loc_18006A1BE
0x18006a17f  test    eax, eax
0x18006a181  jnz     short loc_18006A188
0x18006a183  lea     ebx, [rax+1]
0x18006a186  jmp     short loc_18006A18F
0x18006a188  lea     ebx, [rcx+rcx]
0x18006a18b  test    ebx, ebx
0x18006a18d  js      short loc_18006A1D9
0x18006a18f  mov     edx, ebx
0x18006a191  cmp     rdx, 0FFFFFFFh
0x18006a198  ja      short loc_18006A1D9
0x18006a19a  mov     r8d, 8
0x18006a1a0  mov     rcx, [rbp+57h+var_68]
0x18006a1a4  call    cs:__imp__o__recalloc
0x18006a1aa  mov     rdx, rax
0x18006a1ad  test    rax, rax
0x18006a1b0  jz      short loc_18006A1D9
0x18006a1b2  mov     dword ptr [rbp+57h+var_60+4], ebx
0x18006a1b5  mov     [rbp+57h+var_68], rax
0x18006a1b9  mov     ecx, dword ptr [rbp+57h+var_60]
0x18006a1bc  jmp     short loc_18006A1C2
0x18006a1be  mov     rdx, [rbp+57h+var_68]
0x18006a1c2  movsxd  rax, ecx
0x18006a1c5  lea     r8, [rdx+rax*8]
0x18006a1c9  test    r8, r8
0x18006a1cc  jz      short loc_18006A1D4
0x18006a1ce  mov     [r8], rsi
0x18006a1d1  mov     ecx, dword ptr [rbp+57h+var_60]
0x18006a1d4  inc     ecx
0x18006a1d6  mov     dword ptr [rbp+57h+var_60], ecx
0x18006a1d9  mov     edx, 1; nCmdShow
0x18006a1de  mov     rcx, [rdi-70h]; hWnd
0x18006a1e2  call    cs:__imp_ShowWindow
0x18006a1e8  mov     byte ptr [rdi+119h], 1
0x18006a1ef  lea     rcx, [rbp+57h+var_70]; this
0x18006a1f3  call    ?Run@CMessageLoop@WTL@@QEAAHXZ; WTL::CMessageLoop::Run(void)
0x18006a1f8  call    ?RemoveMessageLoop@CAppModule@WTL@@QEAAHXZ; WTL::CAppModule::RemoveMessageLoop(void)
0x18006a1fd  mov     ecx, 80000000h; esFlags
0x18006a202  call    cs:__imp_SetThreadExecutionState
0x18006a208  lea     rcx, [rbp+57h+var_70]; this
0x18006a20c  call    ??1CMessageLoop@WTL@@QEAA@XZ; WTL::CMessageLoop::~CMessageLoop(void)
0x18006a211  xor     eax, eax
0x18006a213  mov     rbx, [rsp+0A0h+arg_18]
0x18006a21b  add     rsp, 90h
0x18006a222  pop     rdi
0x18006a223  pop     rsi
0x18006a224  pop     rbp
0x18006a225  retn
```
