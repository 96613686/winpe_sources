# PeriodicUpdateManager::TimerFired(_GUID const *)

- ea: `0x18008e370`
- end: `0x18008e79c`
- name: `?TimerFired@PeriodicUpdateManager@@UEAAJPEBU_GUID@@@Z`
- size: `1068`
- prototype: `__int64 __fastcall(PeriodicUpdateManager *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002efc`
- `0x180004e38`
- `0x180011618`
- `0x18001ade8`
- `0x1800299c0`
- `0x18002ee38`
- `0x180032ed4`
- `0x180034624`
- `0x18003fe5c`
- `0x180049a54`
- `0x180078688`
- `0x18007b918`
- `0x18007ed64`
- `0x18008a97c`
- `0x18008e370`
- `0x1800a0b2c`
- `0x1800af0a4`
- `0x1800b9a20`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008e458`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008e458`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e445`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e767`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e445`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e767`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008e775`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008e775`

## string_xrefs

- `0x18008e3e3`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18008e474`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18008e4ff`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18008e568`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18008e5c0`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18008e625`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18008e69f`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PeriodicUpdateManager::TimerFired(PeriodicUpdateManager *this, const struct _GUID *a2, __int64 a3)
{
  unsigned __int16 *v5; // rsi
  __int64 v6; // rbx
  __int64 v7; // rdx
  unsigned int v8; // edi
  __int64 v9; // r8
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  HANDLE ProcessHeap; // rax
  __int64 v14; // rbx
  unsigned __int16 *v15; // rax
  InitialPollUrlWork *v16; // rax
  InitialPollUrlWork *v17; // rbx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  HANDLE v25; // rax
  int v27; // [rsp+20h] [rbp-50h]
  int v28; // [rsp+20h] [rbp-50h]
  char *v29; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int16 *v30; // [rsp+58h] [rbp-18h] BYREF
  struct _GUID v31; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  LPVOID lpMem; // [rsp+A0h] [rbp+30h] BYREF
  InitialPollUrlWork *v34; // [rsp+A8h] [rbp+38h] BYREF
  ThreadPool *v35; // [rsp+B0h] [rbp+40h] BYREF
  InitialPollUrlWork *v36; // [rsp+B8h] [rbp+48h] BYREF

  v5 = 0;
  lpMem = 0;
  v36 = 0;
  v35 = 0;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, 0, a3);
  v6 = *((_QWORD *)this + 3);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  Microsoft::WRL::ComPtr<IGlobalInterfaceTable>::InternalAddRef(v6 + 48, v7);
  v35 = *(ThreadPool **)(v6 + 48);
  if ( v35 )
  {
    v31 = *a2;
    v8 = PeriodicUpdateManager::UnpackPersistedEvent(&v31, 0, (struct _PERSISTED_PERIODIC_UPDATE **)&lpMem, 0);
    if ( (v8 & 0x80000000) == 0 )
    {
      v16 = (InitialPollUrlWork *)operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
      v34 = v16;
      if ( v16 )
        v16 = InitialPollUrlWork::InitialPollUrlWork(v16);
      v34 = v16;
      std::unique_ptr<InitialPollUrlWork>::operator=<std::default_delete<InitialPollUrlWork>,0>(
        (__int64 *)&v36,
        (__int64 *)&v34);
      std::unique_ptr<CacheMetadataStorage>::~unique_ptr<CacheMetadataStorage>(&v34);
      v17 = v36;
      if ( !v36 )
      {
        v8 = -2147024882;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x452,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
          (const char *)0x8007000ELL,
          v27);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            43,
            WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids,
            2147942414LL);
        v5 = (unsigned __int16 *)lpMem;
        goto LABEL_38;
      }
      v5 = (unsigned __int16 *)lpMem;
      v18 = InitialPollUrlWork::SetAppUserModelId(v36, (const unsigned __int16 *)lpMem + 40);
      v8 = v18;
      if ( v18 >= 0 )
      {
        v19 = InitialPollUrlWork::SetPackageFullName(v17, v5 + 170);
        v8 = v19;
        if ( v19 >= 0 )
        {
          lpMem = v5 + 300;
          v20 = InitialPollUrlWork::SetUrls(v17, 1u, (const unsigned __int16 **)&lpMem);
          v8 = v20;
          if ( v20 >= 0 )
          {
            *((_QWORD *)v17 + 17) = *((_QWORD *)this + 3);
            *((_DWORD *)v17 + 29) = *((_DWORD *)v5 + 149);
            *(_OWORD *)((char *)v17 + 120) = *(_OWORD *)v5;
            v36 = 0;
            v21 = ThreadPool::Submit(v35, v17);
            v8 = v21;
            if ( v21 >= 0 )
              goto LABEL_41;
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x463,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
              (const char *)(unsigned int)v21,
              v27);
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
              goto LABEL_38;
            v11 = 47;
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x45C,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
              (const char *)(unsigned int)v20,
              v27);
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
              goto LABEL_38;
            v11 = 46;
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x458,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
            (const char *)(unsigned int)v19,
            v27);
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
            goto LABEL_38;
          v11 = 45;
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x455,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
          (const char *)(unsigned int)v18,
          v27);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_38;
        v11 = 44;
      }
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v14 = 4772;
      v15 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x12A4u);
      v5 = v15;
      do
      {
        *(_BYTE *)v15 = 0;
        v15 = (unsigned __int16 *)((char *)v15 + 1);
        --v14;
      }
      while ( v14 );
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x44C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)v8,
        v27);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_38;
      v11 = 42;
    }
    v12 = v8;
    goto LABEL_37;
  }
  v8 = -2143420155;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x400,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
    (const char *)0x803E0105LL,
    v27);
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x43F,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
    (const char *)0x803E0105LL,
    v28);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v11 = 41;
    v12 = 2151547141LL;
LABEL_37:
    WPP_SF_d(v10[2], v11, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids, v12);
  }
LABEL_38:
  if ( (unsigned int)dword_18015C038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18015C038, 0x400000000000LL, v9) )
  {
    LODWORD(lpMem) = *((_DWORD *)v5 + 149);
    v29 = (char *)(v5 + 300);
    v30 = v5;
    *(_QWORD *)&v31.Data1 = v5 + 40;
    LODWORD(v34) = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v22,
      (unsigned int)byte_180138C8D,
      v23,
      v24,
      (__int64)&v34,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&lpMem);
  }
LABEL_41:
  if ( v5 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v5);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  std::unique_ptr<CacheMetadataStorage>::~unique_ptr<CacheMetadataStorage>(&v36);
  return v8;
}

```

## disassembly

```asm
0x18008e370  push    rbp
0x18008e372  push    rbx
0x18008e373  push    rsi
0x18008e374  push    rdi
0x18008e375  push    r14
0x18008e377  mov     rbp, rsp
0x18008e37a  sub     rsp, 70h
0x18008e37e  mov     rdi, rdx
0x18008e381  mov     r14, rcx
0x18008e384  xor     esi, esi
0x18008e386  mov     [rbp+lpMem], rsi
0x18008e38a  mov     [rbp+arg_18], rsi
0x18008e38e  mov     [rbp+arg_10], rsi
0x18008e392  test    rdx, rdx
0x18008e395  jnz     short loc_18008E39C
0x18008e397  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "TimerPersistenceId != nullptr")
0x18008e39c  mov     rbx, [r14+18h]
0x18008e3a0  lea     rcx, [rbp+arg_10]
0x18008e3a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008e3a9  lea     rcx, [rbx+30h]
0x18008e3ad  call    ?InternalAddRef@?$ComPtr@UIGlobalInterfaceTable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IGlobalInterfaceTable>::InternalAddRef(void)
0x18008e3b2  mov     rax, [rbx+30h]
0x18008e3b6  mov     [rbp+arg_10], rax
0x18008e3ba  test    rax, rax
0x18008e3bd  jnz     short loc_18008E425
0x18008e3bf  mov     rcx, [rbp+28h]; this
0x18008e3c3  mov     edi, 803E0105h
0x18008e3c8  mov     r9d, edi; char *
0x18008e3cb  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008e3d2  mov     edx, 400h; void *
0x18008e3d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e3dc  mov     rcx, [rbp+28h]; this
0x18008e3e0  mov     r9d, edi; char *
0x18008e3e3  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008e3ea  mov     edx, 43Fh; void *
0x18008e3ef  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e3f4  lea     rax, WPP_GLOBAL_Control
0x18008e3fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e402  cmp     rcx, rax
0x18008e405  jz      loc_18008E6E1
0x18008e40b  test    byte ptr [rcx+1Ch], 80h
0x18008e40f  jz      loc_18008E6E1
0x18008e415  mov     edx, 29h ; ')'
0x18008e41a  mov     r9d, 803E0105h
0x18008e420  jmp     loc_18008E6D1
0x18008e425  movups  xmm0, xmmword ptr [rdi]
0x18008e428  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x18008e42d  xor     r9d, r9d; int *
0x18008e430  lea     r8, [rbp+lpMem]; struct _PERSISTED_PERIODIC_UPDATE **
0x18008e434  xor     edx, edx; void *
0x18008e436  lea     rcx, [rbp+var_10]; struct _GUID
0x18008e43a  call    ?UnpackPersistedEvent@PeriodicUpdateManager@@CAJU_GUID@@PEAXPEAPEAU_PERSISTED_PERIODIC_UPDATE@@PEAH@Z; PeriodicUpdateManager::UnpackPersistedEvent(_GUID,void *,_PERSISTED_PERIODIC_UPDATE * *,int *)
0x18008e43f  mov     edi, eax
0x18008e441  test    eax, eax
0x18008e443  jns     short loc_18008E4AE
0x18008e445  call    cs:__imp_GetProcessHeap
0x18008e44b  mov     rcx, rax; hHeap
0x18008e44e  mov     ebx, 12A4h
0x18008e453  mov     r8d, ebx; dwBytes
0x18008e456  xor     edx, edx; dwFlags
0x18008e458  call    cs:__imp_HeapAlloc
0x18008e45e  mov     rsi, rax
0x18008e461  mov     byte ptr [rax], 0
0x18008e464  inc     rax
0x18008e467  sub     rbx, 1
0x18008e46b  jnz     short loc_18008E461
0x18008e46d  mov     rcx, [rbp+28h]; this
0x18008e471  mov     r9d, edi; char *
0x18008e474  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008e47b  mov     edx, 44Ch; void *
0x18008e480  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e485  lea     rax, WPP_GLOBAL_Control
0x18008e48c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e493  cmp     rcx, rax
0x18008e496  jz      loc_18008E6E1
0x18008e49c  test    byte ptr [rcx+1Ch], 80h
0x18008e4a0  jz      loc_18008E6E1
0x18008e4a6  lea     edx, [rbx+2Ah]
0x18008e4a9  jmp     loc_18008E6CE
0x18008e4ae  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008e4b5  mov     ecx, 90h; unsigned __int64
0x18008e4ba  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008e4bf  mov     [rbp+arg_8], rax
0x18008e4c3  test    rax, rax
0x18008e4c6  jz      short loc_18008E4D0
0x18008e4c8  mov     rcx, rax; this
0x18008e4cb  call    ??0InitialPollUrlWork@@QEAA@XZ; InitialPollUrlWork::InitialPollUrlWork(void)
0x18008e4d0  mov     [rbp+arg_8], rax
0x18008e4d4  lea     rdx, [rbp+arg_8]
0x18008e4d8  lea     rcx, [rbp+arg_18]
0x18008e4dc  call    ??$?4U?$default_delete@VInitialPollUrlWork@@@std@@$0A@@?$unique_ptr@VInitialPollUrlWork@@U?$default_delete@VInitialPollUrlWork@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<InitialPollUrlWork>::operator=<std::default_delete<InitialPollUrlWork>,0>(std::unique_ptr<InitialPollUrlWork> &&)
0x18008e4e1  lea     rcx, [rbp+arg_8]
0x18008e4e5  call    ??1?$unique_ptr@VCacheMetadataStorage@@U?$default_delete@VCacheMetadataStorage@@@std@@@std@@QEAA@XZ; std::unique_ptr<CacheMetadataStorage>::~unique_ptr<CacheMetadataStorage>(void)
0x18008e4ea  mov     rbx, [rbp+arg_18]
0x18008e4ee  test    rbx, rbx
0x18008e4f1  jnz     short loc_18008E54B
0x18008e4f3  mov     edi, 8007000Eh
0x18008e4f8  mov     rcx, [rbp+28h]; this
0x18008e4fc  mov     r9d, edi; char *
0x18008e4ff  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008e506  mov     edx, 452h; void *
0x18008e50b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e510  lea     rax, WPP_GLOBAL_Control
0x18008e517  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e51e  cmp     rcx, rax
0x18008e521  jz      short loc_18008E542
0x18008e523  test    byte ptr [rcx+1Ch], 80h
0x18008e527  jz      short loc_18008E542
0x18008e529  lea     edx, [rbx+2Bh]
0x18008e52c  mov     r9d, 8007000Eh
0x18008e532  lea     r8, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids
0x18008e539  mov     rcx, [rcx+10h]
0x18008e53d  call    WPP_SF_d
0x18008e542  mov     rsi, [rbp+lpMem]
0x18008e546  jmp     loc_18008E6E1
0x18008e54b  mov     rsi, [rbp+lpMem]
0x18008e54f  lea     rdx, [rsi+50h]; unsigned __int16 *
0x18008e553  mov     rcx, rbx; this
0x18008e556  call    ?SetAppUserModelId@InitialPollUrlWork@@QEAAJPEBG@Z; InitialPollUrlWork::SetAppUserModelId(ushort const *)
0x18008e55b  mov     edi, eax
0x18008e55d  test    eax, eax
0x18008e55f  jns     short loc_18008E5A4
0x18008e561  mov     rcx, [rbp+28h]; this
0x18008e565  mov     r9d, eax; char *
0x18008e568  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008e56f  mov     edx, 455h; void *
0x18008e574  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e579  lea     rax, WPP_GLOBAL_Control
0x18008e580  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e587  cmp     rcx, rax
0x18008e58a  jz      loc_18008E6E1
0x18008e590  test    byte ptr [rcx+1Ch], 80h
0x18008e594  jz      loc_18008E6E1
0x18008e59a  mov     edx, 2Ch ; ','
0x18008e59f  jmp     loc_18008E6CE
0x18008e5a4  lea     rdx, [rsi+154h]; unsigned __int16 *
0x18008e5ab  mov     rcx, rbx; this
0x18008e5ae  call    ?SetPackageFullName@InitialPollUrlWork@@QEAAJPEBG@Z; InitialPollUrlWork::SetPackageFullName(ushort const *)
0x18008e5b3  mov     edi, eax
0x18008e5b5  test    eax, eax
0x18008e5b7  jns     short loc_18008E5FC
0x18008e5b9  mov     rcx, [rbp+28h]; this
0x18008e5bd  mov     r9d, eax; char *
0x18008e5c0  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008e5c7  mov     edx, 458h; void *
0x18008e5cc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e5d1  lea     rax, WPP_GLOBAL_Control
0x18008e5d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e5df  cmp     rcx, rax
0x18008e5e2  jz      loc_18008E6E1
0x18008e5e8  test    byte ptr [rcx+1Ch], 80h
0x18008e5ec  jz      loc_18008E6E1
0x18008e5f2  mov     edx, 2Dh ; '-'
0x18008e5f7  jmp     loc_18008E6CE
0x18008e5fc  lea     rax, [rsi+258h]
0x18008e603  mov     [rbp+lpMem], rax
0x18008e607  lea     r8, [rbp+lpMem]; unsigned __int16 **
0x18008e60b  mov     edx, 1; unsigned int
0x18008e610  mov     rcx, rbx; this
0x18008e613  call    ?SetUrls@InitialPollUrlWork@@QEAAJIPEAPEBG@Z; InitialPollUrlWork::SetUrls(uint,ushort const * *)
0x18008e618  mov     edi, eax
0x18008e61a  test    eax, eax
0x18008e61c  jns     short loc_18008E65E
0x18008e61e  mov     rcx, [rbp+28h]; this
0x18008e622  mov     r9d, eax; char *
0x18008e625  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008e62c  mov     edx, 45Ch; void *
0x18008e631  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e636  lea     rax, WPP_GLOBAL_Control
0x18008e63d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e644  cmp     rcx, rax
0x18008e647  jz      loc_18008E6E1
0x18008e64d  test    byte ptr [rcx+1Ch], 80h
0x18008e651  jz      loc_18008E6E1
0x18008e657  mov     edx, 2Eh ; '.'
0x18008e65c  jmp     short loc_18008E6CE
0x18008e65e  mov     rax, [r14+18h]
0x18008e662  mov     [rbx+88h], rax
0x18008e669  mov     eax, [rsi+254h]
0x18008e66f  mov     [rbx+74h], eax
0x18008e672  movups  xmm0, xmmword ptr [rsi]
0x18008e675  movdqu  xmmword ptr [rbx+78h], xmm0
0x18008e67a  mov     [rbp+arg_18], 0
0x18008e682  mov     rdx, rbx; struct WorkItem *
0x18008e685  mov     rcx, [rbp+arg_10]; this
0x18008e689  call    ?Submit@ThreadPool@@QEAAJPEAVWorkItem@@@Z; ThreadPool::Submit(WorkItem *)
0x18008e68e  mov     edi, eax
0x18008e690  test    eax, eax
0x18008e692  jns     loc_18008E762
0x18008e698  mov     rcx, [rbp+28h]; this
0x18008e69c  mov     r9d, eax; char *
0x18008e69f  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008e6a6  mov     edx, 463h; void *
0x18008e6ab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e6b0  lea     rax, WPP_GLOBAL_Control
0x18008e6b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e6be  cmp     rcx, rax
0x18008e6c1  jz      short loc_18008E6E1
0x18008e6c3  test    byte ptr [rcx+1Ch], 80h
0x18008e6c7  jz      short loc_18008E6E1
0x18008e6c9  mov     edx, 2Fh ; '/'
0x18008e6ce  mov     r9d, edi
0x18008e6d1  lea     r8, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids
0x18008e6d8  mov     rcx, [rcx+10h]
0x18008e6dc  call    WPP_SF_d
0x18008e6e1  mov     eax, cs:dword_18015C038
0x18008e6e7  cmp     eax, 5
0x18008e6ea  jbe     short loc_18008E762
0x18008e6ec  mov     rdx, 400000000000h
0x18008e6f6  lea     rcx, dword_18015C038
0x18008e6fd  call    _tlgKeywordOn
0x18008e702  test    al, al
0x18008e704  jz      short loc_18008E762
0x18008e706  mov     eax, [rsi+254h]
0x18008e70c  mov     dword ptr [rbp+lpMem], eax
0x18008e70f  lea     rax, [rsi+258h]
0x18008e716  mov     [rbp+var_20], rax
0x18008e71a  mov     [rbp+var_18], rsi
0x18008e71e  lea     rax, [rsi+50h]
0x18008e722  mov     qword ptr [rbp+var_10.Data1], rax
0x18008e726  mov     dword ptr [rbp+arg_8], edi
0x18008e729  lea     rax, [rbp+lpMem]
0x18008e72d  mov     [rsp+70h+var_30], rax
0x18008e732  lea     rax, [rbp+var_20]
0x18008e736  mov     [rsp+70h+var_38], rax
0x18008e73b  lea     rax, [rbp+var_18]
0x18008e73f  mov     [rsp+70h+var_40], rax
0x18008e744  lea     rax, [rbp+var_10]
0x18008e748  mov     [rsp+70h+var_48], rax
0x18008e74d  lea     rax, [rbp+arg_8]
0x18008e751  mov     [rsp+70h+var_50], rax
0x18008e756  lea     rdx, byte_180138C8D
0x18008e75d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18008e762  test    rsi, rsi
0x18008e765  jz      short loc_18008E77C
0x18008e767  call    cs:__imp_GetProcessHeap
0x18008e76d  mov     r8, rsi; lpMem
0x18008e770  xor     edx, edx; dwFlags
0x18008e772  mov     rcx, rax; hHeap
0x18008e775  call    cs:__imp_HeapFree
0x18008e77b  nop
0x18008e77c  lea     rcx, [rbp+arg_10]
0x18008e780  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008e785  nop
0x18008e786  lea     rcx, [rbp+arg_18]
0x18008e78a  call    ??1?$unique_ptr@VCacheMetadataStorage@@U?$default_delete@VCacheMetadataStorage@@@std@@@std@@QEAA@XZ; std::unique_ptr<CacheMetadataStorage>::~unique_ptr<CacheMetadataStorage>(void)
0x18008e78f  mov     eax, edi
0x18008e791  add     rsp, 70h
0x18008e795  pop     r14
0x18008e797  pop     rdi
0x18008e798  pop     rsi
0x18008e799  pop     rbx
0x18008e79a  pop     rbp
0x18008e79b  retn
```
