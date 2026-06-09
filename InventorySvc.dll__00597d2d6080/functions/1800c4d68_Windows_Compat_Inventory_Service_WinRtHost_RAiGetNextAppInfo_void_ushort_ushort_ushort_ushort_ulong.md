# Windows::Compat::Inventory::Service::WinRtHost::RAiGetNextAppInfo(void *,ushort *,ushort *,ushort *,ushort *,ulong)

- ea: `0x1800c4d68`
- end: `0x1800c53ce`
- name: `?RAiGetNextAppInfo@WinRtHost@Service@Inventory@Compat@Windows@@QEAAJPEAXPEAG111K@Z`
- size: `1638`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::Service::WinRtHost *this, void *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800c5b60`

## callees

- `0x180002bf0`
- `0x180002c40`
- `0x1800030e0`
- `0x1800052bc`
- `0x180005324`
- `0x180006e54`
- `0x180006e60`
- `0x1800074f0`
- `0x1800152d0`
- `0x18002d068`
- `0x1800c3c54`
- `0x1800c450c`
- `0x1800c4840`
- `0x1800c4d68`
- `0x1800c53d4`
- `0x1800c592c`
- `0x1800d1010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800c4f18`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800c4f18`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c4ead`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c50e3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c52b0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c4ead`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c50e3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c52b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c50a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c526f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c52c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c50a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c526f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c52c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800c4e16`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800c4e16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800c50ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800c528c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800c50ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800c528c`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x1800c4e8c`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x1800c4e8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c50d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c50d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c50bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c50bf`
- `ext-ms-win-appcompat-aeinv-l1-1-0!GetAppInventory` at `0x1800c4fec`
- `ext-ms-win-appcompat-aeinv-l1-1-0!GetAppInventory` at `0x1800c4fec`

## string_xrefs

- `0x1800c53be`: `onecore\base\appcompat\inventory\service\winrt\lib\winrthost.cpp`
- `0x1800c4f59`: `Windows::Compat::Inventory::Service::WinRtHost::RAiGetNextAppInfo`
- `0x1800c539a`: `Windows::Compat::Inventory::Service::WinRtHost::RAiGetNextAppInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Inventory::Service::WinRtHost::RAiGetNextAppInfo(
        Windows::Compat::Inventory::Service::WinRtHost *this,
        void *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned int a7)
{
  unsigned __int16 *v7; // rsi
  unsigned __int16 *v8; // r13
  void *v9; // r15
  __int64 v10; // rbx
  RTL_SRWLOCK *v11; // rbx
  char *v12; // rdx
  _QWORD *v13; // rax
  _BYTE *v14; // r8
  _QWORD *v15; // rcx
  __int64 v16; // rcx
  char *v17; // rsi
  int AppInventory; // eax
  unsigned int v19; // r15d
  volatile signed __int32 *v20; // r15
  DWORD LastError; // ebx
  __int128 *v22; // rsi
  volatile signed __int32 *v23; // rcx
  __int64 v24; // rcx
  volatile signed __int32 *v25; // rsi
  volatile signed __int32 *v26; // rsi
  Windows::Compat::Inventory::Service::WinRtHost *v27; // rcx
  __int64 v28; // rcx
  _QWORD *v30; // rax
  unsigned int v31; // eax
  int v32; // [rsp+20h] [rbp-148h]
  int NextAppInfo; // [rsp+30h] [rbp-138h]
  __int128 v35; // [rsp+40h] [rbp-128h] BYREF
  __int128 *v36; // [rsp+50h] [rbp-118h] BYREF
  unsigned __int16 *v37; // [rsp+60h] [rbp-108h]
  unsigned __int16 *v38; // [rsp+68h] [rbp-100h]
  void *v39; // [rsp+70h] [rbp-F8h] BYREF
  RTL_SRWLOCK *v40; // [rsp+78h] [rbp-F0h]
  unsigned __int16 *v41; // [rsp+80h] [rbp-E8h]
  RTL_SRWLOCK *v42; // [rsp+88h] [rbp-E0h]
  char v43[32]; // [rsp+B0h] [rbp-B8h] BYREF
  __int64 v44; // [rsp+D0h] [rbp-98h] BYREF
  int v45; // [rsp+D8h] [rbp-90h]
  int v46; // [rsp+DCh] [rbp-8Ch]
  __int64 v47; // [rsp+E0h] [rbp-88h]
  _BYTE v48[32]; // [rsp+F0h] [rbp-78h] BYREF
  int v49; // [rsp+110h] [rbp-58h]
  __int64 v50; // [rsp+118h] [rbp-50h]
  volatile signed __int32 *v51; // [rsp+120h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v7 = a4;
  v41 = a4;
  v8 = a3;
  v36 = (__int128 *)a3;
  v9 = a2;
  v39 = a2;
  v38 = a5;
  v37 = a6;
  Windows::Compat::Inventory::Service::WinRtHost::SetTimer(this);
  v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_1800FF938 > *(_DWORD *)(v10 + 4) )
  {
    Init_thread_header(&dword_1800FF938);
    if ( dword_1800FF938 == -1 )
    {
      v30 = operator new(0x60u);
      *v30 = v30;
      v30[1] = v30;
      v30[2] = v30;
      *((_WORD *)v30 + 12) = 257;
      qword_1800FF940 = v30;
      atexit(Windows::Compat::Inventory::Service::WinRtHost::RAiGetNextAppInfo_::_3_::_dynamic_atexit_destructor_for__rpcStateMap__);
      Init_thread_footer(&dword_1800FF938);
    }
  }
  if ( dword_1800FF950 > *(_DWORD *)(v10 + 4) )
  {
    Init_thread_header(&dword_1800FF950);
    if ( dword_1800FF950 == -1 )
    {
      atexit(Windows::Compat::Inventory::Service::WinRtHost::RAiGetNextAppInfo_::_4_::_dynamic_atexit_destructor_for__latestGaiResults__);
      Init_thread_footer(&dword_1800FF950);
    }
  }
  AcquireSRWLockShared(&stru_1800FF878);
  v11 = &stru_1800FF878;
  v40 = &stru_1800FF878;
  v12 = (char *)qword_1800FF940;
  v13 = (_QWORD *)*((_QWORD *)qword_1800FF940 + 1);
  v46 = 0;
  v14 = qword_1800FF940;
  v15 = v13;
  while ( !*((_BYTE *)v15 + 25) )
  {
    if ( v15[4] >= (unsigned __int64)v9 )
    {
      v14 = v15;
      v15 = (_QWORD *)*v15;
    }
    else
    {
      v15 = (_QWORD *)v15[2];
    }
  }
  if ( !v14[25] && (unsigned __int64)v9 >= *((_QWORD *)v14 + 4) && v14 != qword_1800FF940 )
  {
    while ( !*((_BYTE *)v13 + 25) )
    {
      if ( v13[4] >= (unsigned __int64)v9 )
      {
        v12 = (char *)v13;
        v13 = (_QWORD *)*v13;
      }
      else
      {
        v13 = (_QWORD *)v13[2];
      }
    }
    if ( !v12[25] && (unsigned __int64)v9 >= *((_QWORD *)v12 + 4) )
    {
      NextAppInfo = Windows::Compat::Inventory::Service::WinRtHost::GetNextAppInfo(
                      (Windows::Compat::Inventory::Service::WinRtHost *)v15,
                      (struct Windows::Compat::Inventory::Service::WinRtHost::RpcCallState *)(v12 + 40),
                      v8,
                      v7,
                      v38,
                      v37);
      goto LABEL_54;
    }
    std::_Xout_of_range("invalid map<K, T> key");
    goto LABEL_23;
  }
  LODWORD(v7) = a7;
  if ( a7 || !(_QWORD)xmmword_1800FF868 )
  {
    v11 = (RTL_SRWLOCK *)((unsigned __int64)&stru_1800FF860
                        & -(__int64)(TryAcquireSRWLockExclusive(&stru_1800FF860) != 0));
    if ( !v11 )
    {
      LODWORD(v7) = 0;
      AcquireSRWLockExclusive(&stru_1800FF860);
      v11 = &stru_1800FF860;
      goto LABEL_24;
    }
LABEL_23:
    if ( (_DWORD)v7 )
    {
      v16 = xmmword_1800FF868;
      goto LABEL_27;
    }
LABEL_24:
    v16 = xmmword_1800FF868;
    if ( (_QWORD)xmmword_1800FF868 )
    {
LABEL_39:
      if ( v11 )
        ReleaseSRWLockExclusive(v11);
      goto LABEL_41;
    }
LABEL_27:
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::Service::WinRtHost::RAiGetNextAppInfo",
      332,
      "Refreshing latest GAI results because ForceScan:%d FirstRun: %d",
      (_DWORD)v7,
      v16 == 0);
    v44 = 24;
    v45 = 0;
    v46 = (int)v7;
    v47 = 554500096;
    v17 = (char *)operator new(0x38u);
    *((_DWORD *)v17 + 2) = 1;
    *((_DWORD *)v17 + 3) = 1;
    *(_QWORD *)v17 = &std::_Ref_count_obj2<Windows::Compat::Inventory::Service::Win32AppInvReceiver>::`vftable';
    *((_QWORD *)v17 + 2) = &Windows::Compat::Inventory::Service::Win32AppInvReceiver::`vftable';
    v17[24] = 0;
    *((_QWORD *)v17 + 4) = 0;
    *((_QWORD *)v17 + 5) = 0;
    *((_QWORD *)v17 + 6) = 0;
    *(_QWORD *)&v35 = v17 + 16;
    *((_QWORD *)&v35 + 1) = v17;
    AppInventory = GetAppInventory(v17 + 16, &v44, 0);
    v19 = AppInventory;
    if ( AppInventory < 0 )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::Service::WinRtHost::RAiGetNextAppInfo",
        343,
        "failed [%#x]",
        AppInventory);
      v31 = wil::verify_hresult<long>(v19);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x157,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\winrt\\lib\\winrthost.cpp",
        (const char *)v31,
        v32);
    }
    if ( v17 )
      _InterlockedIncrement((volatile signed __int32 *)v17 + 2);
    *(_QWORD *)&xmmword_1800FF868 = v17 + 16;
    v20 = (volatile signed __int32 *)*((_QWORD *)&xmmword_1800FF868 + 1);
    *((_QWORD *)&xmmword_1800FF868 + 1) = v17;
    if ( v20 )
    {
      if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
    }
    if ( v17 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v17 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v17)(v17);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    v8 = (unsigned __int16 *)v36;
    v9 = a2;
    goto LABEL_39;
  }
LABEL_41:
  Windows::Compat::Inventory::Service::WinRtHost::GetUserSid(&v44, v9);
  LastError = GetLastError();
  ReleaseSRWLockShared(&stru_1800FF878);
  SetLastError(LastError);
  v11 = 0;
  v40 = 0;
  AcquireSRWLockExclusive(&stru_1800FF878);
  v42 = &stru_1800FF878;
  v36 = &v35;
  v35 = 0;
  if ( *((_QWORD *)&xmmword_1800FF868 + 1) )
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&xmmword_1800FF868 + 1) + 8LL));
  v35 = xmmword_1800FF868;
  v22 = (__int128 *)std::wstring::wstring(v43, &v44);
  v36 = v22;
  std::wstring::wstring(v48, v22);
  v49 = 0;
  v23 = (volatile signed __int32 *)*((_QWORD *)&v35 + 1);
  if ( *((_QWORD *)&v35 + 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v35 + 1) + 8LL));
    v23 = (volatile signed __int32 *)*((_QWORD *)&v35 + 1);
  }
  v50 = v35;
  v51 = v23;
  std::wstring::~wstring(v22);
  v25 = (volatile signed __int32 *)*((_QWORD *)&v35 + 1);
  if ( *((_QWORD *)&v35 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v35 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
      if ( !_InterlockedDecrement(v25 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
    }
  }
  std::_Tree<std::_Tmap_traits<void *,Windows::Compat::Inventory::Service::WinRtHost::RpcCallState,std::less<void *>,std::allocator<std::pair<void * const,Windows::Compat::Inventory::Service::WinRtHost::RpcCallState>>,0>>::emplace<void * &,Windows::Compat::Inventory::Service::WinRtHost::RpcCallState>(
    v24,
    &v36,
    &v39,
    v48);
  v26 = v51;
  if ( v51 )
  {
    if ( _InterlockedExchangeAdd(v51 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
      if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
    }
  }
  std::wstring::~wstring(v48);
  NextAppInfo = Windows::Compat::Inventory::Service::WinRtHost::GetNextAppInfo(
                  v27,
                  (struct Windows::Compat::Inventory::Service::WinRtHost::RpcCallState *)((char *)v36 + 40),
                  v8,
                  v41,
                  v38,
                  v37);
  ReleaseSRWLockExclusive(&stru_1800FF878);
  std::wstring::~wstring(&v44);
LABEL_54:
  if ( v11 )
    ReleaseSRWLockShared(v11);
  if ( NextAppInfo < 0 )
  {
    AcquireSRWLockExclusive(&stru_1800FF878);
    std::_Tree<std::_Tmap_traits<void *,Windows::Compat::Inventory::Service::WinRtHost::RpcCallState,std::less<void *>,std::allocator<std::pair<void * const,Windows::Compat::Inventory::Service::WinRtHost::RpcCallState>>,0>>::erase(
      v28,
      &v39);
    ReleaseSRWLockExclusive(&stru_1800FF878);
  }
  return (unsigned int)NextAppInfo;
}

```

## disassembly

```asm
0x1800c4d68  push    rbx
0x1800c4d6a  push    rsi
0x1800c4d6b  push    rdi
0x1800c4d6c  push    r12
0x1800c4d6e  push    r13
0x1800c4d70  push    r14
0x1800c4d72  push    r15
0x1800c4d74  sub     rsp, 130h
0x1800c4d7b  mov     rax, cs:__security_cookie
0x1800c4d82  xor     rax, rsp
0x1800c4d85  mov     [rsp+168h+var_40], rax
0x1800c4d8d  mov     rsi, r9
0x1800c4d90  mov     [rsp+168h+var_E8], r9
0x1800c4d98  mov     r13, r8
0x1800c4d9b  mov     [rsp+168h+var_118], r8
0x1800c4da0  mov     r15, rdx
0x1800c4da3  mov     [rsp+168h+var_130], rdx
0x1800c4da8  mov     [rsp+168h+var_F8], rdx
0x1800c4dad  mov     rax, [rsp+168h+arg_20]
0x1800c4db5  mov     [rsp+168h+var_100], rax
0x1800c4dba  mov     rax, [rsp+168h+arg_28]
0x1800c4dc2  mov     [rsp+168h+var_108], rax
0x1800c4dc7  xor     edi, edi
0x1800c4dc9  call    ?SetTimer@WinRtHost@Service@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::Service::WinRtHost::SetTimer(void)
0x1800c4dce  nop
0x1800c4dcf  mov     ecx, cs:_tls_index
0x1800c4dd5  mov     rax, gs:58h
0x1800c4dde  mov     r12d, 4
0x1800c4de4  mov     rbx, [rax+rcx*8]
0x1800c4de8  mov     eax, [rbx+r12]
0x1800c4dec  cmp     cs:dword_1800FF938, eax
0x1800c4df2  jg      loc_1800C52F5
0x1800c4df8  or      r14d, 0FFFFFFFFh
0x1800c4dfc  mov     eax, [rbx+r12]
0x1800c4e00  cmp     cs:dword_1800FF950, eax
0x1800c4e06  jg      loc_1800C5350
0x1800c4e0c  lea     r12, stru_1800FF878
0x1800c4e13  mov     rcx, r12; SRWLock
0x1800c4e16  call    cs:__imp_AcquireSRWLockShared
0x1800c4e1c  mov     rbx, r12
0x1800c4e1f  mov     [rsp+168h+var_F0], rbx
0x1800c4e24  mov     rdx, cs:qword_1800FF940
0x1800c4e2b  mov     rax, [rdx+8]
0x1800c4e2f  xor     ecx, ecx
0x1800c4e31  mov     [rsp+168h+var_8C], ecx
0x1800c4e38  mov     r8, rdx
0x1800c4e3b  mov     rcx, rax
0x1800c4e3e  cmp     [rax+19h], dil
0x1800c4e42  jnz     short loc_1800C4E5C
0x1800c4e44  cmp     [rcx+20h], r15
0x1800c4e48  jnb     short loc_1800C4E50
0x1800c4e4a  mov     rcx, [rcx+10h]
0x1800c4e4e  jmp     short loc_1800C4E56
0x1800c4e50  mov     r8, rcx
0x1800c4e53  mov     rcx, [rcx]
0x1800c4e56  cmp     [rcx+19h], dil
0x1800c4e5a  jz      short loc_1800C4E44
0x1800c4e5c  cmp     [r8+19h], dil
0x1800c4e60  jnz     short loc_1800C4E6D
0x1800c4e62  cmp     r15, [r8+20h]
0x1800c4e66  jb      short loc_1800C4E6D
0x1800c4e68  cmp     r8, rdx
0x1800c4e6b  jnz     short loc_1800C4ED3
0x1800c4e6d  mov     esi, [rsp+168h+arg_30]
0x1800c4e74  test    esi, esi
0x1800c4e76  jnz     short loc_1800C4E85
0x1800c4e78  cmp     qword ptr cs:xmmword_1800FF868, rdi
0x1800c4e7f  jnz     loc_1800C50AE
0x1800c4e85  lea     rcx, stru_1800FF860; SRWLock
0x1800c4e8c  call    cs:__imp_TryAcquireSRWLockExclusive
0x1800c4e92  neg     al
0x1800c4e94  sbb     rbx, rbx
0x1800c4e97  lea     rax, stru_1800FF860
0x1800c4e9e  and     rbx, rax
0x1800c4ea1  mov     [rsp+168h+var_138], rbx
0x1800c4ea6  jnz     short loc_1800C4F1F
0x1800c4ea8  mov     esi, edi
0x1800c4eaa  mov     rcx, rax; SRWLock
0x1800c4ead  call    cs:__imp_AcquireSRWLockExclusive
0x1800c4eb3  lea     rbx, stru_1800FF860
0x1800c4eba  mov     [rsp+168h+var_138], rbx
0x1800c4ebf  jmp     short loc_1800C4F23
0x1800c4ec1  cmp     [rax+20h], r15
0x1800c4ec5  jnb     short loc_1800C4ECD
0x1800c4ec7  mov     rax, [rax+10h]
0x1800c4ecb  jmp     short loc_1800C4ED3
0x1800c4ecd  mov     rdx, rax
0x1800c4ed0  mov     rax, [rax]
0x1800c4ed3  cmp     [rax+19h], dil
0x1800c4ed7  jz      short loc_1800C4EC1
0x1800c4ed9  cmp     [rdx+19h], dil
0x1800c4edd  jnz     short loc_1800C4F11
0x1800c4edf  cmp     r15, [rdx+20h]
0x1800c4ee3  jb      short loc_1800C4F11
0x1800c4ee5  add     rdx, 28h ; '('; struct Windows::Compat::Inventory::Service::WinRtHost::RpcCallState *
0x1800c4ee9  mov     rax, [rsp+168h+var_108]
0x1800c4eee  mov     [rsp+168h+var_140], rax; unsigned __int16 *
0x1800c4ef3  mov     rax, [rsp+168h+var_100]
0x1800c4ef8  mov     [rsp+168h+var_148], rax; unsigned __int16 *
0x1800c4efd  mov     r9, rsi; unsigned __int16 *
0x1800c4f00  mov     r8, r13; unsigned __int16 *
0x1800c4f03  call    ?GetNextAppInfo@WinRtHost@Service@Inventory@Compat@Windows@@AEAAJAEAURpcCallState@12345@PEAG111@Z; Windows::Compat::Inventory::Service::WinRtHost::GetNextAppInfo(Windows::Compat::Inventory::Service::WinRtHost::RpcCallState &,ushort *,ushort *,ushort *,ushort *)
0x1800c4f08  mov     dword ptr [rsp+168h+var_138], eax
0x1800c4f0c  jmp     loc_1800C5284
0x1800c4f11  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x1800c4f18  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1800c4f1e  nop
0x1800c4f1f  test    esi, esi
0x1800c4f21  jnz     short loc_1800C4F35
0x1800c4f23  mov     rcx, qword ptr cs:xmmword_1800FF868
0x1800c4f2a  test    rcx, rcx
0x1800c4f2d  jnz     loc_1800C50A0
0x1800c4f33  jmp     short loc_1800C4F3C
0x1800c4f35  mov     rcx, qword ptr cs:xmmword_1800FF868
0x1800c4f3c  mov     eax, edi
0x1800c4f3e  test    rcx, rcx
0x1800c4f41  setz    al
0x1800c4f44  mov     dword ptr [rsp+168h+var_140], eax
0x1800c4f48  mov     dword ptr [rsp+168h+var_148], esi
0x1800c4f4c  lea     r9, aRefreshingLate; "Refreshing latest GAI results because F"...
0x1800c4f53  mov     r8d, 14Ch
0x1800c4f59  lea     rdx, aWindowsCompatI_26; "Windows::Compat::Inventory::Service::Wi"...
0x1800c4f60  mov     ecx, 3
0x1800c4f65  call    AslLogCallPrintf
0x1800c4f6a  mov     [rsp+168h+var_98], 18h
0x1800c4f76  mov     [rsp+168h+var_90], edi
0x1800c4f7d  mov     [rsp+168h+var_8C], esi
0x1800c4f84  mov     [rsp+168h+var_88], 210D0000h
0x1800c4f90  mov     ecx, 38h ; '8'; Size
0x1800c4f95  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c4f9a  mov     rsi, rax
0x1800c4f9d  mov     dword ptr [rax+8], 1
0x1800c4fa4  mov     dword ptr [rax+0Ch], 1
0x1800c4fab  lea     rax, ??_7?$_Ref_count_obj2@VWin32AppInvReceiver@Service@Inventory@Compat@Windows@@@std@@6B@; const std::_Ref_count_obj2<Windows::Compat::Inventory::Service::Win32AppInvReceiver>::`vftable'
0x1800c4fb2  mov     [rsi], rax
0x1800c4fb5  lea     r13, [rsi+10h]
0x1800c4fb9  lea     rax, ??_7Win32AppInvReceiver@Service@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::Service::Win32AppInvReceiver::`vftable'
0x1800c4fc0  mov     [r13+0], rax
0x1800c4fc4  mov     [r13+8], dil
0x1800c4fc8  mov     [r13+10h], rdi
0x1800c4fcc  mov     [r13+18h], rdi
0x1800c4fd0  mov     [r13+20h], rdi
0x1800c4fd4  mov     qword ptr [rsp+168h+var_128], r13
0x1800c4fd9  mov     qword ptr [rsp+168h+var_128+8], rsi
0x1800c4fde  xor     r8d, r8d
0x1800c4fe1  lea     rdx, [rsp+168h+var_98]
0x1800c4fe9  mov     rcx, r13
0x1800c4fec  call    cs:__imp_GetAppInventory
0x1800c4ff2  mov     r15d, eax
0x1800c4ff5  test    eax, eax
0x1800c4ff7  js      loc_1800C5387
0x1800c4ffd  test    rsi, rsi
0x1800c5000  jz      short loc_1800C5006
0x1800c5002  lock inc dword ptr [rsi+8]
0x1800c5006  mov     qword ptr cs:xmmword_1800FF868, r13
0x1800c500d  mov     r15, qword ptr cs:xmmword_1800FF868+8
0x1800c5014  mov     qword ptr cs:xmmword_1800FF868+8, rsi
0x1800c501b  test    r15, r15
0x1800c501e  jz      short loc_1800C505A
0x1800c5020  mov     eax, r14d
0x1800c5023  lock xadd [r15+8], eax
0x1800c5029  add     eax, r14d
0x1800c502c  jnz     short loc_1800C505A
0x1800c502e  mov     rax, [r15]
0x1800c5031  mov     rcx, r15
0x1800c5034  mov     rax, [rax]
0x1800c5037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c503c  mov     eax, r14d
0x1800c503f  lock xadd [r15+0Ch], eax
0x1800c5045  add     eax, r14d
0x1800c5048  jnz     short loc_1800C505A
0x1800c504a  mov     rax, [r15]
0x1800c504d  mov     rcx, r15
0x1800c5050  mov     rax, [rax+8]
0x1800c5054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5059  nop
0x1800c505a  test    rsi, rsi
0x1800c505d  jz      short loc_1800C5096
0x1800c505f  mov     eax, r14d
0x1800c5062  lock xadd [rsi+8], eax
0x1800c5067  add     eax, r14d
0x1800c506a  jnz     short loc_1800C5096
0x1800c506c  mov     rax, [rsi]
0x1800c506f  mov     rcx, rsi
0x1800c5072  mov     rax, [rax]
0x1800c5075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c507a  mov     eax, r14d
0x1800c507d  lock xadd [rsi+0Ch], eax
0x1800c5082  add     eax, r14d
0x1800c5085  jnz     short loc_1800C5096
0x1800c5087  mov     rax, [rsi]
0x1800c508a  mov     rcx, rsi
0x1800c508d  mov     rax, [rax+8]
0x1800c5091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5096  mov     r13, [rsp+168h+var_118]
0x1800c509b  mov     r15, [rsp+168h+var_130]
0x1800c50a0  test    rbx, rbx
0x1800c50a3  jz      short loc_1800C50AE
0x1800c50a5  mov     rcx, rbx; SRWLock
0x1800c50a8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c50ae  mov     rdx, r15; BindingHandle
0x1800c50b1  lea     rcx, [rsp+168h+var_98]; void *
0x1800c50b9  call    ?GetUserSid@WinRtHost@Service@Inventory@Compat@Windows@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; Windows::Compat::Inventory::Service::WinRtHost::GetUserSid(void *)
0x1800c50be  nop
0x1800c50bf  call    cs:__imp_GetLastError
0x1800c50c5  mov     ebx, eax
0x1800c50c7  mov     rcx, r12; SRWLock
0x1800c50ca  call    cs:__imp_ReleaseSRWLockShared
0x1800c50d0  mov     ecx, ebx; dwErrCode
0x1800c50d2  call    cs:__imp_SetLastError
0x1800c50d8  mov     rbx, rdi
0x1800c50db  mov     [rsp+168h+var_F0], rbx
0x1800c50e0  mov     rcx, r12; SRWLock
0x1800c50e3  call    cs:__imp_AcquireSRWLockExclusive
0x1800c50e9  mov     [rsp+168h+var_E0], r12
0x1800c50f1  lea     rax, [rsp+168h+var_128]
0x1800c50f6  mov     [rsp+168h+var_118], rax
0x1800c50fb  xorps   xmm0, xmm0
0x1800c50fe  movdqu  [rsp+168h+var_128], xmm0
0x1800c5104  mov     rax, qword ptr cs:xmmword_1800FF868+8
0x1800c510b  test    rax, rax
0x1800c510e  jz      short loc_1800C5114
0x1800c5110  lock inc dword ptr [rax+8]
0x1800c5114  movups  xmm0, cs:xmmword_1800FF868
0x1800c511b  movdqu  [rsp+168h+var_128], xmm0
0x1800c5121  lea     rax, [rsp+168h+var_128]
0x1800c5126  mov     [rsp+168h+var_130], rax
0x1800c512b  lea     rdx, [rsp+168h+var_98]
0x1800c5133  lea     rcx, [rsp+168h+var_B8]
0x1800c513b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800c5140  mov     rsi, rax
0x1800c5143  mov     [rsp+168h+var_118], rax
0x1800c5148  mov     rdx, rax
0x1800c514b  lea     rcx, [rsp+168h+var_78]
0x1800c5153  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800c5158  mov     [rsp+168h+var_58], edi
0x1800c515f  mov     rcx, qword ptr [rsp+168h+var_128+8]
0x1800c5164  test    rcx, rcx
0x1800c5167  jz      short loc_1800C5172
0x1800c5169  lock inc dword ptr [rcx+8]
0x1800c516d  mov     rcx, qword ptr [rsp+168h+var_128+8]
0x1800c5172  mov     rax, qword ptr [rsp+168h+var_128]
0x1800c5177  mov     [rsp+168h+var_50], rax
0x1800c517f  mov     [rsp+168h+var_48], rcx
0x1800c5187  mov     rcx, rsi; void *
0x1800c518a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c518f  nop
0x1800c5190  mov     rsi, qword ptr [rsp+168h+var_128+8]
0x1800c5195  test    rsi, rsi
0x1800c5198  jz      short loc_1800C51D2
0x1800c519a  mov     eax, r14d
0x1800c519d  lock xadd [rsi+8], eax
0x1800c51a2  add     eax, r14d
0x1800c51a5  jnz     short loc_1800C51D2
0x1800c51a7  mov     rax, [rsi]
0x1800c51aa  mov     rcx, rsi
0x1800c51ad  mov     rax, [rax]
0x1800c51b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c51b5  mov     eax, r14d
0x1800c51b8  lock xadd [rsi+0Ch], eax
0x1800c51bd  add     eax, r14d
0x1800c51c0  jnz     short loc_1800C51D2
0x1800c51c2  mov     rax, [rsi]
0x1800c51c5  mov     rcx, rsi
0x1800c51c8  mov     rax, [rax+8]
0x1800c51cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c51d1  nop
0x1800c51d2  lea     r9, [rsp+168h+var_78]
0x1800c51da  lea     r8, [rsp+168h+var_F8]
0x1800c51df  lea     rdx, [rsp+168h+var_118]
0x1800c51e4  call    ??$emplace@AEAPEAXURpcCallState@WinRtHost@Service@Inventory@Compat@Windows@@@?$_Tree@V?$_Tmap_traits@PEAXURpcCallState@WinRtHost@Service@Inventory@Compat@Windows@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXURpcCallState@WinRtHost@Service@Inventory@Compat@Windows@@@std@@@8@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXURpcCallState@WinRtHost@Service@Inventory@Compat@Windows@@@std@@@std@@@std@@@std@@_N@1@AEAPEAX$$QEAURpcCallState@WinRtHost@Service@Inventory@Compat@Windows@@@Z; std::_Tree<std::_Tmap_traits<void *,Windows::Compat::Inventory::Service::WinRtHost::RpcCallState,std::less<void *>,std::allocator<std::pair<void * const,Windows::Compat::Inventory::Service::WinRtHost::RpcCallState>>,0>>::emplace<void * &,Windows::Compat::Inventory::Service::WinRtHost::RpcCallState>(void * &,Windows::Compat::Inventory::Service::WinRtHost::RpcCallState &&)
0x1800c51e9  nop
0x1800c51ea  mov     rsi, [rsp+168h+var_48]
0x1800c51f2  test    rsi, rsi
0x1800c51f5  jz      short loc_1800C522E
0x1800c51f7  mov     eax, r14d
0x1800c51fa  lock xadd [rsi+8], eax
0x1800c51ff  add     eax, r14d
0x1800c5202  jnz     short loc_1800C522E
0x1800c5204  mov     rax, [rsi]
0x1800c5207  mov     rcx, rsi
0x1800c520a  mov     rax, [rax]
0x1800c520d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5212  mov     eax, r14d
0x1800c5215  lock xadd [rsi+0Ch], eax
0x1800c521a  add     eax, r14d
0x1800c521d  jnz     short loc_1800C522E
0x1800c521f  mov     rax, [rsi]
0x1800c5222  mov     rcx, rsi
0x1800c5225  mov     rax, [rax+8]
0x1800c5229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c522e  lea     rcx, [rsp+168h+var_78]; void *
0x1800c5236  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c523b  mov     rdx, [rsp+168h+var_118]
0x1800c5240  add     rdx, 28h ; '('; struct Windows::Compat::Inventory::Service::WinRtHost::RpcCallState *
0x1800c5244  mov     rax, [rsp+168h+var_108]
0x1800c5249  mov     [rsp+168h+var_140], rax; unsigned __int16 *
0x1800c524e  mov     rax, [rsp+168h+var_100]
0x1800c5253  mov     [rsp+168h+var_148], rax; unsigned __int16 *
0x1800c5258  mov     r9, [rsp+168h+var_E8]; unsigned __int16 *
  ... truncated ...
```
