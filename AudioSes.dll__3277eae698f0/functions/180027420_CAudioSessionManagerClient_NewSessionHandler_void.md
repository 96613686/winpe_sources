# CAudioSessionManagerClient::NewSessionHandler(void)

- ea: `0x180027420`
- end: `0x1800277e1`
- name: `?NewSessionHandler@CAudioSessionManagerClient@@AEAAXXZ`
- size: `961`
- prototype: `void __fastcall(CAudioSessionManagerClient *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006fdb0`

## callees

- `0x180007f00`
- `0x18000cf5c`
- `0x18000d11c`
- `0x18000d148`
- `0x18000d598`
- `0x1800258d0`
- `0x180025a04`
- `0x180025d88`
- `0x18002637c`
- `0x180026b18`
- `0x180027420`
- `0x180027880`
- `0x180028ab0`
- `0x180028b6c`
- `0x180028d3c`
- `0x180028db4`
- `0x1800774e8`
- `0x180087e80`
- `0x180095600`
- `0x1800b1bb0`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002748e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027504`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002759b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002748e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027504`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002759b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800274f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027608`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002769b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800276fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002779f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800274f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027608`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002769b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800276fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002779f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800274a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800274c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800274a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800274c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall CAudioSessionManagerClient::NewSessionHandler(CAudioSessionManagerClient *this)
{
  int v2; // ebx
  _QWORD *v3; // rbx
  const unsigned __int16 *v4; // rdx
  CAudioSessionManagerClient *v5; // rcx
  __int64 v6; // r12
  __int64 (__fastcall *v7)(__int64, unsigned __int16 **, struct IAudioSessionControl **); // rbx
  unsigned __int16 **v8; // rdx
  int v9; // eax
  __int64 v10; // rax
  unsigned __int16 **v11; // rdx
  const unsigned __int16 *v12; // r8
  int ExistingSession; // eax
  wil::details::in1diag3 *v14; // rcx
  __int64 v15; // rdx
  const unsigned __int16 *v16; // rdx
  struct IAudioSessionControl *v17; // [rsp+20h] [rbp-69h] BYREF
  struct IAudioSessionControl *v18; // [rsp+28h] [rbp-61h] BYREF
  void *v19; // [rsp+30h] [rbp-59h] BYREF
  __int64 v20; // [rsp+38h] [rbp-51h] BYREF
  void *v21[2]; // [rsp+40h] [rbp-49h] BYREF
  struct IAudioSessionControl *v22; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v23[8]; // [rsp+58h] [rbp-31h] BYREF
  char *v24; // [rsp+60h] [rbp-29h]
  char *v25; // [rsp+68h] [rbp-21h]
  unsigned __int16 *v26[3]; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int64 v27; // [rsp+88h] [rbp-1h]
  __int64 v28; // [rsp+90h] [rbp+7h] BYREF
  _BYTE v29[32]; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v21[0] = 0;
  wil::details::weak_query_policy::query(
    *((struct IWeakReference **)this + 20),
    &GUID_bfa971f1_4d5e_40bb_935e_967039bfbee4,
    v21);
  if ( !v21[0] )
    return;
  while ( 1 )
  {
    std::wstring::wstring(v26);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 416));
    if ( *((_DWORD *)this + 122) )
    {
      v2 = *((_DWORD *)this + 122);
      if ( v2 != GetCurrentThreadId() )
        break;
    }
    v3 = (_QWORD *)((char *)this + 456);
    if ( *((_QWORD *)this + 57) == *((_QWORD *)this + 58) )
    {
      *((_DWORD *)this + 122) = 0;
      break;
    }
    *((_DWORD *)this + 122) = GetCurrentThreadId();
    std::wstring::operator=(v26, *v3);
    std::vector<std::wstring>::erase((char *)this + 456, v23, *v3);
    if ( this != (CAudioSessionManagerClient *)-416LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 416));
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
    v24 = (char *)this + 224;
    if ( *((_BYTE *)this + 264) )
    {
      CAudioSessionManagerClient::PruneStaleAudioSessions(this);
      v18 = 0;
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v18);
      v4 = (const unsigned __int16 *)v26;
      if ( v27 > 7 )
        v4 = v26[0];
      CAudioSessionManagerClient::GetSessionForSessionId(this, v4, &v18);
      v5 = (CAudioSessionManagerClient *)v18;
      if ( !v18
        || (LODWORD(v19) = 0,
            ((int (__fastcall *)(struct IAudioSessionControl *, void **))v18->lpVtbl->GetState)(v18, &v19) < 0)
        || (_DWORD)v19 == 2 )
      {
        v17 = 0;
        if ( *((_DWORD *)this + 69) == 2 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
          v25 = (char *)this + 304;
          v6 = *((_QWORD *)this + 43);
          if ( v6 )
          {
            v7 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **, struct IAudioSessionControl **))(*(_QWORD *)v6 + 24LL);
            Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v17);
            v8 = v26;
            if ( v27 > 7 )
              v8 = (unsigned __int16 **)v26[0];
            v9 = v7(v6, v8, &v17);
            if ( v9 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x290,
                (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientsessionmgr.cpp",
                (const char *)(unsigned int)v9,
                (int)v17);
              goto LABEL_19;
            }
            v20 = 0;
            v19 = &v20;
            v10 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v19);
            if ( (int)Microsoft::WRL::AsWeak<IAudioSessionControl>(v17, v10) >= 0 )
            {
              v28 = v20;
              if ( v20 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
              v11 = v26;
              if ( v27 > 7 )
                v11 = (unsigned __int16 **)v26[0];
              std::wstring::wstring(v29, v11);
              std::vector<CAudioSessionManagerClient::SessionEntry>::emplace_back<CAudioSessionManagerClient::SessionEntry>(
                (char *)this + 280,
                &v28);
              CAudioSessionManagerClient::SessionEntry::~SessionEntry((CAudioSessionManagerClient::SessionEntry *)&v28);
            }
            Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v20);
            if ( this != (CAudioSessionManagerClient *)-304LL )
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
LABEL_29:
            v21[1] = &CAudioSessionArrived::`vftable';
            v22 = v17;
            if ( v17 )
              ((void (__fastcall *)(struct IAudioSessionControl *))v17->lpVtbl->AddRef)(v17);
            CLockedList_AllowDuplicates<IAudioSessionNotification,1>::ForEachEntry((LPCRITICAL_SECTION)((char *)this + 96));
            wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v22);
          }
          else
          {
LABEL_19:
            if ( this != (CAudioSessionManagerClient *)-304LL )
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
          }
        }
        else
        {
          v19 = 0;
          v12 = (const unsigned __int16 *)v26;
          if ( v27 > 7 )
            v12 = v26[0];
          ExistingSession = CAudioSessionManagerClient::GetExistingSession(v5, (void **)this + 21, v12, &v19);
          v14 = retaddr;
          if ( ExistingSession >= 0 )
          {
            Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v17);
            v16 = (const unsigned __int16 *)v26;
            if ( v27 > 7 )
              v16 = v26[0];
            ExistingSession = CAudioSessionManagerClient::CreateSessionControl(this, v16, v19, &v17);
            v14 = retaddr;
            if ( ExistingSession >= 0 )
              goto LABEL_29;
            v15 = 688;
          }
          else
          {
            v15 = 680;
          }
          wil::details::in1diag3::_Log_Hr(
            v14,
            (void *)v15,
            (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientsessionmgr.cpp",
            (const char *)(unsigned int)ExistingSession,
            (int)v17);
        }
        Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v17);
      }
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v18);
    }
    if ( this != (CAudioSessionManagerClient *)-224LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
    std::wstring::~wstring(v26);
  }
  if ( this != (CAudioSessionManagerClient *)-416LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 416));
  std::wstring::~wstring(v26);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(v21);
}

```

## disassembly

```asm
0x180027420  mov     [rsp-8+arg_8], rbx
0x180027425  mov     [rsp-8+arg_10], rsi
0x18002742a  push    rbp
0x18002742b  push    rdi
0x18002742c  push    r12
0x18002742e  push    r14
0x180027430  push    r15
0x180027432  lea     rbp, [rsp-37h]
0x180027437  sub     rsp, 0C0h
0x18002743e  mov     rax, cs:__security_cookie
0x180027445  xor     rax, rsp
0x180027448  mov     [rbp+57h+var_28], rax
0x18002744c  mov     rdi, rcx
0x18002744f  mov     [rbp+57h+var_A0], 0
0x180027457  lea     r8, [rbp+57h+var_A0]; void **
0x18002745b  lea     rdx, _GUID_bfa971f1_4d5e_40bb_935e_967039bfbee4; struct _GUID *
0x180027462  mov     rcx, [rcx+0A0h]; struct IWeakReference *
0x180027469  call    ?query@weak_query_policy@details@wil@@SAJPEAUIWeakReference@@AEBU_GUID@@PEAPEAX@Z; wil::details::weak_query_policy::query(IWeakReference *,_GUID const &,void * *)
0x18002746e  cmp     [rbp+57h+var_A0], 0
0x180027473  jnz     short loc_18002747A
0x180027475  jmp     loc_1800277B9
0x18002747a  lea     r14, [rdi+1A0h]
0x180027481  lea     rcx, [rbp+57h+var_70]
0x180027485  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002748a  nop
0x18002748b  mov     rcx, r14; lpCriticalSection
0x18002748e  call    cs:__imp_EnterCriticalSection
0x180027494  cmp     dword ptr [rdi+1E8h], 0
0x18002749b  jz      short loc_1800274B1
0x18002749d  mov     ebx, [rdi+1E8h]
0x1800274a3  call    cs:__imp_GetCurrentThreadId
0x1800274a9  cmp     ebx, eax
0x1800274ab  jnz     loc_180027797
0x1800274b1  lea     rbx, [rdi+1C8h]
0x1800274b8  mov     rax, [rbx+8]
0x1800274bc  cmp     [rbx], rax
0x1800274bf  jz      loc_18002778D
0x1800274c5  call    cs:__imp_GetCurrentThreadId
0x1800274cb  mov     [rdi+1E8h], eax
0x1800274d1  mov     rdx, [rbx]
0x1800274d4  lea     rcx, [rbp+57h+var_70]
0x1800274d8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800274dd  mov     r8, [rbx]
0x1800274e0  lea     rdx, [rbp+57h+var_88]
0x1800274e4  mov     rcx, rbx
0x1800274e7  call    ?erase@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@@Z; std::vector<std::wstring>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>)
0x1800274ec  test    r14, r14
0x1800274ef  jz      short loc_1800274FA
0x1800274f1  mov     rcx, r14; lpCriticalSection
0x1800274f4  call    cs:__imp_LeaveCriticalSection
0x1800274fa  lea     rsi, [rdi+0E0h]
0x180027501  mov     rcx, rsi; lpCriticalSection
0x180027504  call    cs:__imp_EnterCriticalSection
0x18002750a  mov     [rbp+57h+var_80], rsi
0x18002750e  cmp     byte ptr [rdi+108h], 0
0x180027515  jz      loc_1800276F2
0x18002751b  mov     rcx, rdi; this
0x18002751e  call    ?PruneStaleAudioSessions@CAudioSessionManagerClient@@IEAAXXZ; CAudioSessionManagerClient::PruneStaleAudioSessions(void)
0x180027523  mov     [rbp+57h+var_B8], 0
0x18002752b  lea     rcx, [rbp+57h+var_B8]
0x18002752f  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180027534  lea     rdx, [rbp+57h+var_70]
0x180027538  cmp     [rbp+57h+var_58], 7
0x18002753d  cmova   rdx, [rbp+57h+var_70]; unsigned __int16 *
0x180027542  lea     r8, [rbp+57h+var_B8]; struct IAudioSessionControl **
0x180027546  mov     rcx, rdi; this
0x180027549  call    ?GetSessionForSessionId@CAudioSessionManagerClient@@IEAAXPEBGPEAPEAUIAudioSessionControl@@@Z; CAudioSessionManagerClient::GetSessionForSessionId(ushort const *,IAudioSessionControl * *)
0x18002754e  mov     rcx, [rbp+57h+var_B8]
0x180027552  test    rcx, rcx
0x180027555  jz      short loc_18002757C
0x180027557  mov     dword ptr [rbp+57h+var_B0], 0
0x18002755e  mov     rax, [rcx]
0x180027561  lea     rdx, [rbp+57h+var_B0]
0x180027565  mov     rax, [rax+18h]
0x180027569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002756e  test    eax, eax
0x180027570  js      short loc_18002757C
0x180027572  cmp     dword ptr [rbp+57h+var_B0], 2
0x180027576  jnz     loc_1800276E8
0x18002757c  mov     [rbp+57h+var_C0], 0
0x180027584  cmp     dword ptr [rdi+114h], 2
0x18002758b  jnz     loc_18002770F
0x180027591  lea     r15, [rdi+130h]
0x180027598  mov     rcx, r15; lpCriticalSection
0x18002759b  call    cs:__imp_EnterCriticalSection
0x1800275a1  mov     [rbp+57h+var_78], r15
0x1800275a5  mov     r12, [rdi+158h]
0x1800275ac  test    r12, r12
0x1800275af  jz      short loc_1800275FC
0x1800275b1  mov     rax, [r12]
0x1800275b5  mov     rbx, [rax+18h]
0x1800275b9  lea     rcx, [rbp+57h+var_C0]
0x1800275bd  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800275c2  lea     rdx, [rbp+57h+var_70]
0x1800275c6  cmp     [rbp+57h+var_58], 7
0x1800275cb  cmova   rdx, [rbp+57h+var_70]
0x1800275d0  lea     r8, [rbp+57h+var_C0]
0x1800275d4  mov     rcx, r12
0x1800275d7  mov     rax, rbx
0x1800275da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275df  mov     rcx, [rbp+5Fh]; this
0x1800275e3  test    eax, eax
0x1800275e5  jns     short loc_180027613
0x1800275e7  mov     r9d, eax; char *
0x1800275ea  lea     r8, aAvcoreAudiocor_21; "avcore\\audiocore\\client\\audioclient"...
0x1800275f1  mov     edx, 290h; void *
0x1800275f6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800275fb  nop
0x1800275fc  test    r15, r15
0x1800275ff  jz      loc_1800276DE
0x180027605  mov     rcx, r15; lpCriticalSection
0x180027608  call    cs:__imp_LeaveCriticalSection
0x18002760e  jmp     loc_1800276DE
0x180027613  mov     [rbp+57h+var_A8], 0
0x18002761b  lea     rax, [rbp+57h+var_A8]
0x18002761f  mov     [rbp+57h+var_B0], rax
0x180027623  lea     rcx, [rbp+57h+var_B0]
0x180027627  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18002762c  mov     rdx, rax
0x18002762f  mov     rcx, [rbp+57h+var_C0]
0x180027633  call    ??$AsWeak@UIAudioSessionControl@@@WRL@Microsoft@@YAJPEAUIAudioSessionControl@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<IAudioSessionControl>(IAudioSessionControl *,Microsoft::WRL::WeakRef *)
0x180027638  test    eax, eax
0x18002763a  js      short loc_180027689
0x18002763c  mov     rcx, [rbp+57h+var_A8]
0x180027640  mov     [rbp+57h+var_50], rcx
0x180027644  test    rcx, rcx
0x180027647  jz      short loc_180027656
0x180027649  mov     rax, [rcx]
0x18002764c  mov     rax, [rax+8]
0x180027650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027655  nop
0x180027656  lea     rdx, [rbp+57h+var_70]
0x18002765a  cmp     [rbp+57h+var_58], 7
0x18002765f  cmova   rdx, [rbp+57h+var_70]
0x180027664  lea     rcx, [rbp+57h+var_48]
0x180027668  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002766d  nop
0x18002766e  lea     rdx, [rbp+57h+var_50]
0x180027672  lea     rcx, [rdi+118h]
0x180027679  call    ??$emplace_back@USessionEntry@CAudioSessionManagerClient@@@?$vector@USessionEntry@CAudioSessionManagerClient@@V?$allocator@USessionEntry@CAudioSessionManagerClient@@@std@@@std@@QEAAAEAUSessionEntry@CAudioSessionManagerClient@@$$QEAU23@@Z; std::vector<CAudioSessionManagerClient::SessionEntry>::emplace_back<CAudioSessionManagerClient::SessionEntry>(CAudioSessionManagerClient::SessionEntry &&)
0x18002767e  nop
0x18002767f  lea     rcx, [rbp+57h+var_50]; this
0x180027683  call    ??1SessionEntry@CAudioSessionManagerClient@@QEAA@XZ; CAudioSessionManagerClient::SessionEntry::~SessionEntry(void)
0x180027688  nop
0x180027689  lea     rcx, [rbp+57h+var_A8]
0x18002768d  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180027692  nop
0x180027693  test    r15, r15
0x180027696  jz      short loc_1800276A1
0x180027698  mov     rcx, r15; lpCriticalSection
0x18002769b  call    cs:__imp_LeaveCriticalSection
0x1800276a1  mov     rcx, [rbp+57h+var_C0]
0x1800276a5  lea     rax, ??_7CAudioSessionArrived@@6B@; const CAudioSessionArrived::`vftable'
0x1800276ac  mov     [rbp+57h+var_98], rax
0x1800276b0  mov     [rbp+57h+var_90], rcx
0x1800276b4  test    rcx, rcx
0x1800276b7  jz      short loc_1800276C6
0x1800276b9  mov     rax, [rcx]
0x1800276bc  mov     rax, [rax+8]
0x1800276c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276c5  nop
0x1800276c6  lea     rdx, [rbp+57h+var_98]
0x1800276ca  lea     rcx, [rdi+60h]; lpCriticalSection
0x1800276ce  call    ?ForEachEntry@?$CLockedList_AllowDuplicates@UIAudioSessionNotification@@$00@@QEAAJ$$QEAVCListWorker@1@@Z; CLockedList_AllowDuplicates<IAudioSessionNotification,1>::ForEachEntry(CLockedList_AllowDuplicates<IAudioSessionNotification,1>::CListWorker &&)
0x1800276d3  nop
0x1800276d4  lea     rcx, [rbp+57h+var_90]; void *
0x1800276d8  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800276dd  nop
0x1800276de  lea     rcx, [rbp+57h+var_C0]
0x1800276e2  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800276e7  nop
0x1800276e8  lea     rcx, [rbp+57h+var_B8]
0x1800276ec  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800276f1  nop
0x1800276f2  test    rsi, rsi
0x1800276f5  jz      short loc_180027701
0x1800276f7  mov     rcx, rsi; lpCriticalSection
0x1800276fa  call    cs:__imp_LeaveCriticalSection
0x180027700  nop
0x180027701  lea     rcx, [rbp+57h+var_70]
0x180027705  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002770a  jmp     loc_180027481
0x18002770f  mov     [rbp+57h+var_B0], 0
0x180027717  lea     r8, [rbp+57h+var_70]
0x18002771b  cmp     [rbp+57h+var_58], 7
0x180027720  cmova   r8, [rbp+57h+var_70]; unsigned __int16 *
0x180027725  lea     rdx, [rdi+0A8h]; void **
0x18002772c  lea     r9, [rbp+57h+var_B0]; void **
0x180027730  call    ?GetExistingSession@CAudioSessionManagerClient@@IEAAJPEAPEAXPEBG0@Z; CAudioSessionManagerClient::GetExistingSession(void * *,ushort const *,void * *)
0x180027735  mov     rcx, [rbp+5Fh]; this
0x180027739  test    eax, eax
0x18002773b  jns     short loc_180027753
0x18002773d  mov     edx, 2A8h; void *
0x180027742  lea     r8, aAvcoreAudiocor_21; "avcore\\audiocore\\client\\audioclient"...
0x180027749  mov     r9d, eax; char *
0x18002774c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027751  jmp     short loc_1800276DE
0x180027753  lea     rcx, [rbp+57h+var_C0]
0x180027757  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18002775c  lea     rdx, [rbp+57h+var_70]
0x180027760  cmp     [rbp+57h+var_58], 7
0x180027765  cmova   rdx, [rbp+57h+var_70]; unsigned __int16 *
0x18002776a  lea     r9, [rbp+57h+var_C0]; struct IAudioSessionControl **
0x18002776e  mov     r8, [rbp+57h+var_B0]; void *
0x180027772  mov     rcx, rdi; this
0x180027775  call    ?CreateSessionControl@CAudioSessionManagerClient@@IEAAJPEBGPEAXPEAPEAUIAudioSessionControl@@@Z; CAudioSessionManagerClient::CreateSessionControl(ushort const *,void *,IAudioSessionControl * *)
0x18002777a  mov     rcx, [rbp+5Fh]
0x18002777e  test    eax, eax
0x180027780  jns     loc_1800276A1
0x180027786  mov     edx, 2B0h
0x18002778b  jmp     short loc_180027742
0x18002778d  mov     dword ptr [rdi+1E8h], 0
0x180027797  test    r14, r14
0x18002779a  jz      short loc_1800277A6
0x18002779c  mov     rcx, r14; lpCriticalSection
0x18002779f  call    cs:__imp_LeaveCriticalSection
0x1800277a5  nop
0x1800277a6  lea     rcx, [rbp+57h+var_70]
0x1800277aa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800277af  nop
0x1800277b0  lea     rcx, [rbp+57h+var_A0]; void *
0x1800277b4  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800277b9  mov     rcx, [rbp+57h+var_28]
0x1800277bd  xor     rcx, rsp; StackCookie
0x1800277c0  call    __security_check_cookie
0x1800277c5  lea     r11, [rsp+0E0h+var_20]
0x1800277cd  mov     rbx, [r11+38h]
0x1800277d1  mov     rsi, [r11+40h]
0x1800277d5  mov     rsp, r11
0x1800277d8  pop     r15
0x1800277da  pop     r14
0x1800277dc  pop     r12
0x1800277de  pop     rdi
0x1800277df  pop     rbp
0x1800277e0  retn
```
