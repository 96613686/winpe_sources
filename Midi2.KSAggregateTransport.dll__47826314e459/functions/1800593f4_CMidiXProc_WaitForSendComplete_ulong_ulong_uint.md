# CMidiXProc::WaitForSendComplete(ulong,ulong,uint)

- ea: `0x1800593f4`
- end: `0x18005988a`
- name: `?WaitForSendComplete@CMidiXProc@@AEAAJKKI@Z`
- size: `1174`
- prototype: `__int64 __fastcall(CMidiXProc *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180058a2c`

## callees

- `0x180002f30`
- `0x18000c684`
- `0x180058798`
- `0x1800593f4`
- `0x180059890`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18005945b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180059770`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18005945b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180059770`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800594a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005967e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800594a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005967e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059542`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800595fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005970d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059542`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800595fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005970d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180059606`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800597a8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180059606`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800597a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005971f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005973e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059801`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059818`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005971f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005973e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059801`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059818`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180059665`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800597ea`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180059665`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800597ea`

## string_xrefs

- `0x180059581`: `MidiXProc Detected stall resolved before WaitForSendComplete.`
- `0x1800596a5`: `MidiXProc stall detected during wait.`
- `0x1800594da`: `MidiXProc Wait skipped during continued stall.`
- `0x1800594e5`: `CMidiXProc::WaitForSendComplete`
- `0x18005958c`: `CMidiXProc::WaitForSendComplete`
- `0x1800596b0`: `CMidiXProc::WaitForSendComplete`

## pseudocode

```c
__int64 __fastcall CMidiXProc::WaitForSendComplete(CMidiXProc *this, unsigned __int32 a2, unsigned int a3, int a4)
{
  char IsEnabled; // al
  _QWORD *v9; // rcx
  void *v10; // rbx
  void *v11; // r13
  const WCHAR *v12; // r8
  HANDLE v13; // rax
  unsigned __int32 v14; // r15d
  const struct _tlgProvider_t *v15; // rax
  int v16; // r8d
  int v17; // r9d
  unsigned int v18; // r8d
  const char *v19; // r9
  const struct _tlgProvider_t *v21; // rax
  int v22; // r8d
  int v23; // r9d
  signed __int32 v24; // eax
  __int64 v25; // rcx
  unsigned __int32 v26; // r8d
  int v27; // eax
  DWORD v28; // eax
  const struct _tlgProvider_t *v29; // rax
  int v30; // r8d
  int v31; // r9d
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  void *v36; // rsi
  const WCHAR *v37; // r8
  HANDLE v38; // rax
  unsigned __int32 v39; // r15d
  int v40; // r13d
  unsigned __int32 v41; // eax
  unsigned int v42; // r8d
  const char *v43; // r9
  unsigned int v44; // r8d
  const char *v45; // r9
  int v46; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v47; // [rsp+54h] [rbp-25h] BYREF
  unsigned __int32 v48; // [rsp+58h] [rbp-21h] BYREF
  const wchar_t *v49; // [rsp+60h] [rbp-19h] BYREF
  const char *v50; // [rsp+68h] [rbp-11h] BYREF
  const char *v51; // [rsp+70h] [rbp-9h] BYREF
  const char *v52; // [rsp+78h] [rbp-1h] BYREF
  HANDLE Handles; // [rsp+80h] [rbp+7h] BYREF
  void *v54; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::GetImpl'::`2'::impl);
  v9 = (_QWORD *)*((_QWORD *)this + 14);
  if ( !v9 )
    return 1;
  v10 = 0;
  if ( !IsEnabled )
  {
    v36 = (void *)v9[8];
    if ( v9[11] )
    {
      v37 = (const WCHAR *)(v9 + 9);
      if ( v9[12] > 7u )
        v37 = *(const WCHAR **)v37;
      v38 = OpenEventW(0x1F0003u, 0, v37);
      v10 = v38;
      if ( v38 )
        v36 = v38;
    }
    v39 = a3 + a4;
    Handles = (HANDLE)*((_QWORD *)this + 15);
    v54 = v36;
    if ( a2 > a3 )
      v39 += *(_DWORD *)(*((_QWORD *)this + 14) + 32LL);
    v40 = 0;
    do
    {
      if ( WaitForMultipleObjects(2u, &Handles, 0, 0x1388u) != 1 )
      {
        if ( v10 && !CloseHandle(v10) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
        return 2147500036LL;
      }
      ResetEvent(v36);
      v41 = _InterlockedCompareExchange(*(volatile signed __int32 **)(*((_QWORD *)this + 14) + 48LL), 0, 0);
      if ( v41 < a2 )
        ++v40;
      a2 = v41 + *(_DWORD *)(*((_QWORD *)this + 14) + 32LL) * v40;
    }
    while ( a2 <= v39 );
    if ( v10 && !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v44, v45);
    return 0;
  }
  v11 = (void *)v9[8];
  if ( v9[11] )
  {
    v12 = (const WCHAR *)(v9 + 9);
    if ( v9[12] > 7u )
      v12 = *(const WCHAR **)v12;
    v13 = OpenEventW(0x1F0003u, 0, v12);
    v10 = v13;
    if ( v13 )
      v11 = v13;
  }
  Handles = (HANDLE)*((_QWORD *)this + 15);
  v47 = a3 + a4;
  v54 = v11;
  if ( a2 > a3 )
    v47 = *(_DWORD *)(*((_QWORD *)this + 14) + 32LL) + a3 + a4;
  v14 = _InterlockedCompareExchange(*(volatile signed __int32 **)(*((_QWORD *)this + 14) + 48LL), 0, 0);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( !*((_BYTE *)this + 48) )
  {
LABEL_22:
    v46 = 0;
    if ( this != (CMidiXProc *)-8LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    while ( 1 )
    {
      v28 = WaitForMultipleObjects(2u, &Handles, 0, 0x3E8u);
      if ( v28 != 1 )
      {
        if ( v28 == 258 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
          *((_BYTE *)this + 48) = 1;
          *((_DWORD *)this + 13) = v14;
          v29 = MidiXProcTelemetryProvider::Provider();
          if ( *(_DWORD *)v29 > 4u )
          {
            v48 = *((_DWORD *)this + 13);
            v52 = (const char *)L"MidiXProc stall detected during wait.";
            v50 = "CMidiXProc::WaitForSendComplete";
            LODWORD(v49) = a3;
            v47 = v14;
            v51 = (const char *)this;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (_DWORD)v29,
              (unsigned int)byte_18008B4B1,
              v30,
              v31,
              (__int64)&v50,
              (__int64)&v51,
              (__int64)&v52,
              (__int64)&v47,
              (__int64)&v48,
              (__int64)&v49);
          }
          if ( this != (CMidiXProc *)-8LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
        }
        if ( v10 && !CloseHandle(v10) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
        return 2147500036LL;
      }
      ResetEvent(v11);
      v24 = _InterlockedCompareExchange(*(volatile signed __int32 **)(*((_QWORD *)this + 14) + 48LL), 0, 0);
      v25 = *((_QWORD *)this + 14);
      v26 = v24 + v46 * *(_DWORD *)(v25 + 32);
      v27 = v46 + 1;
      if ( v26 >= a2 )
        v27 = v46;
      v14 = v26 + *(_DWORD *)(v25 + 32);
      v46 = v27;
      if ( v26 >= a2 )
        v14 = v26;
      if ( v14 >= v47 )
        break;
      a2 = v14;
    }
    if ( v10 && !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
    return 0;
  }
  if ( v14 != *((_DWORD *)this + 13) )
  {
    v21 = MidiXProcTelemetryProvider::Provider();
    if ( *(_DWORD *)v21 > 4u )
    {
      v46 = *((_DWORD *)this + 13);
      v51 = (const char *)L"MidiXProc Detected stall resolved before WaitForSendComplete.";
      v52 = "CMidiXProc::WaitForSendComplete";
      v48 = a3;
      LODWORD(v49) = v14;
      v50 = (const char *)this;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v21,
        (unsigned int)&word_18008BB56,
        v22,
        v23,
        (__int64)&v52,
        (__int64)&v50,
        (__int64)&v51,
        (__int64)&v49,
        (__int64)&v46,
        (__int64)&v48);
    }
    *((_BYTE *)this + 48) = 0;
    *((_DWORD *)this + 13) = 0;
    goto LABEL_22;
  }
  v15 = MidiXProcTelemetryProvider::Provider();
  if ( *(_DWORD *)v15 > 4u )
  {
    v46 = *((_DWORD *)this + 13);
    v49 = L"MidiXProc Wait skipped during continued stall.";
    v51 = "CMidiXProc::WaitForSendComplete";
    v47 = a3;
    v48 = v14;
    v50 = (const char *)this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v15,
      (unsigned int)word_18008B682,
      v16,
      v17,
      (__int64)&v51,
      (__int64)&v50,
      (__int64)&v49,
      (__int64)&v48,
      (__int64)&v46,
      (__int64)&v47);
  }
  if ( this != (CMidiXProc *)-8LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( v10 )
  {
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
  }
  return 2147500036LL;
}

```

## disassembly

```asm
0x1800593f4  push    rbp
0x1800593f6  push    rbx
0x1800593f7  push    rsi
0x1800593f8  push    rdi
0x1800593f9  push    r12
0x1800593fb  push    r13
0x1800593fd  push    r14
0x1800593ff  push    r15
0x180059401  lea     rbp, [rsp-1Fh]
0x180059406  sub     rsp, 98h
0x18005940d  mov     r15d, r9d
0x180059410  mov     r14d, r8d
0x180059413  mov     r12d, edx
0x180059416  mov     rdi, rcx
0x180059419  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::GetImpl(void)'::`2'::impl
0x180059420  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::__private_IsEnabled(void)
0x180059425  mov     rcx, [rdi+70h]
0x180059429  test    rcx, rcx
0x18005942c  jz      loc_180059826
0x180059432  xor     ebx, ebx
0x180059434  test    al, al
0x180059436  jz      loc_180059751
0x18005943c  mov     r13, [rcx+40h]
0x180059440  cmp     [rcx+58h], rbx
0x180059444  jbe     short loc_18005946B
0x180059446  lea     r8, [rcx+48h]
0x18005944a  cmp     qword ptr [r8+18h], 7
0x18005944f  jbe     short loc_180059454
0x180059451  mov     r8, [r8]; lpName
0x180059454  xor     edx, edx; bInheritHandle
0x180059456  mov     ecx, 1F0003h; dwDesiredAccess
0x18005945b  call    cs:__imp_OpenEventW
0x180059461  test    rax, rax
0x180059464  mov     rbx, rax
0x180059467  cmovnz  r13, rax
0x18005946b  mov     rax, [rdi+78h]
0x18005946f  lea     edx, [r14+r15]
0x180059473  mov     [rbp+57h+Handles], rax
0x180059477  mov     [rbp+57h+var_7C], edx
0x18005947a  mov     [rbp+57h+var_48], r13
0x18005947e  cmp     r12d, r14d
0x180059481  jbe     short loc_18005948D
0x180059483  mov     rax, [rdi+70h]
0x180059487  add     edx, [rax+20h]
0x18005948a  mov     [rbp+57h+var_7C], edx
0x18005948d  mov     rax, [rdi+70h]
0x180059491  xor     edx, edx
0x180059493  mov     rcx, [rax+30h]
0x180059497  xor     eax, eax
0x180059499  lock cmpxchg [rcx], edx
0x18005949d  lea     rsi, [rdi+8]
0x1800594a1  mov     r15d, eax
0x1800594a4  mov     rcx, rsi; lpCriticalSection
0x1800594a7  call    cs:__imp_EnterCriticalSection
0x1800594ad  cmp     byte ptr [rdi+30h], 0
0x1800594b1  jz      loc_1800595EC
0x1800594b7  cmp     r15d, [rdi+34h]
0x1800594bb  jnz     loc_180059568
0x1800594c1  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x1800594c6  mov     ecx, [rax]
0x1800594c8  cmp     ecx, 4
0x1800594cb  jbe     short loc_18005953A
0x1800594cd  mov     ecx, [rdi+34h]
0x1800594d0  lea     rdx, word_18008B682
0x1800594d7  mov     [rbp+57h+var_80], ecx
0x1800594da  lea     rcx, aMidixprocWaitS; "MidiXProc Wait skipped during continued"...
0x1800594e1  mov     [rbp+57h+var_70], rcx
0x1800594e5  lea     rcx, aCmidixprocWait; "CMidiXProc::WaitForSendComplete"
0x1800594ec  mov     [rbp+57h+var_60], rcx
0x1800594f0  lea     rcx, [rbp+57h+var_7C]
0x1800594f4  mov     [rsp+0D0h+var_88], rcx
0x1800594f9  lea     rcx, [rbp+57h+var_80]
0x1800594fd  mov     [rsp+0D0h+var_90], rcx
0x180059502  lea     rcx, [rbp+57h+var_78]
0x180059506  mov     [rsp+0D0h+var_98], rcx
0x18005950b  lea     rcx, [rbp+57h+var_70]
0x18005950f  mov     [rsp+0D0h+var_A0], rcx
0x180059514  lea     rcx, [rbp+57h+var_68]
0x180059518  mov     [rsp+0D0h+var_A8], rcx
0x18005951d  lea     rcx, [rbp+57h+var_60]
0x180059521  mov     [rsp+0D0h+var_B0], rcx
0x180059526  mov     rcx, rax
0x180059529  mov     [rbp+57h+var_7C], r14d
0x18005952d  mov     [rbp+57h+var_78], r15d
0x180059531  mov     [rbp+57h+var_68], rdi
0x180059535  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005953a  test    rsi, rsi
0x18005953d  jz      short loc_180059548
0x18005953f  mov     rcx, rsi; lpCriticalSection
0x180059542  call    cs:__imp_LeaveCriticalSection
0x180059548  test    rbx, rbx
0x18005954b  jz      short loc_18005955E
0x18005954d  mov     rcx, rbx; hObject
0x180059550  call    cs:__imp_CloseHandle
0x180059556  test    eax, eax
0x180059558  jz      loc_18005987B
0x18005955e  mov     eax, 80004004h
0x180059563  jmp     loc_18005982B
0x180059568  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x18005956d  mov     ecx, [rax]
0x18005956f  cmp     ecx, 4
0x180059572  jbe     short loc_1800595E1
0x180059574  mov     ecx, [rdi+34h]
0x180059577  lea     rdx, word_18008BB56
0x18005957e  mov     [rbp+57h+var_80], ecx
0x180059581  lea     rcx, aMidixprocDetec; "MidiXProc Detected stall resolved befor"...
0x180059588  mov     [rbp+57h+var_60], rcx
0x18005958c  lea     rcx, aCmidixprocWait; "CMidiXProc::WaitForSendComplete"
0x180059593  mov     [rbp+57h+var_58], rcx
0x180059597  lea     rcx, [rbp+57h+var_78]
0x18005959b  mov     [rsp+0D0h+var_88], rcx
0x1800595a0  lea     rcx, [rbp+57h+var_80]
0x1800595a4  mov     [rsp+0D0h+var_90], rcx
0x1800595a9  lea     rcx, [rbp+57h+var_70]
0x1800595ad  mov     [rsp+0D0h+var_98], rcx
0x1800595b2  lea     rcx, [rbp+57h+var_60]
0x1800595b6  mov     [rsp+0D0h+var_A0], rcx
0x1800595bb  lea     rcx, [rbp+57h+var_68]
0x1800595bf  mov     [rsp+0D0h+var_A8], rcx
0x1800595c4  lea     rcx, [rbp+57h+var_58]
0x1800595c8  mov     [rsp+0D0h+var_B0], rcx
0x1800595cd  mov     rcx, rax
0x1800595d0  mov     [rbp+57h+var_78], r14d
0x1800595d4  mov     dword ptr [rbp+57h+var_70], r15d
0x1800595d8  mov     [rbp+57h+var_68], rdi
0x1800595dc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800595e1  mov     byte ptr [rdi+30h], 0
0x1800595e5  mov     dword ptr [rdi+34h], 0
0x1800595ec  mov     [rbp+57h+var_80], 0
0x1800595f3  test    rsi, rsi
0x1800595f6  jz      short loc_180059654
0x1800595f8  mov     rcx, rsi; lpCriticalSection
0x1800595fb  call    cs:__imp_LeaveCriticalSection
0x180059601  jmp     short loc_180059654
0x180059603  mov     rcx, r13; hEvent
0x180059606  call    cs:__imp_ResetEvent
0x18005960c  mov     rax, [rdi+70h]
0x180059610  xor     edx, edx
0x180059612  mov     rcx, [rax+30h]
0x180059616  xor     eax, eax
0x180059618  lock cmpxchg [rcx], edx
0x18005961c  mov     r9d, [rbp+57h+var_80]
0x180059620  mov     rcx, [rdi+70h]
0x180059624  mov     edx, [rcx+20h]
0x180059627  mov     r8d, edx
0x18005962a  imul    r8d, r9d
0x18005962e  add     r8d, eax
0x180059631  lea     eax, [r9+1]
0x180059635  cmp     r8d, r12d
0x180059638  cmovnb  eax, r9d
0x18005963c  lea     r15d, [r8+rdx]
0x180059640  mov     [rbp+57h+var_80], eax
0x180059643  cmovnb  r15d, r8d
0x180059647  cmp     r15d, [rbp+57h+var_7C]
0x18005964b  jnb     loc_180059732
0x180059651  mov     r12d, r15d
0x180059654  xor     r8d, r8d; bWaitAll
0x180059657  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18005965b  mov     r9d, 3E8h; dwMilliseconds
0x180059661  lea     ecx, [r8+2]; nCount
0x180059665  call    cs:__imp_WaitForMultipleObjects
0x18005966b  cmp     eax, 1
0x18005966e  jz      short loc_180059603
0x180059670  cmp     eax, 102h
0x180059675  jnz     loc_180059713
0x18005967b  mov     rcx, rsi; lpCriticalSection
0x18005967e  call    cs:__imp_EnterCriticalSection
0x180059684  mov     byte ptr [rdi+30h], 1
0x180059688  mov     [rdi+34h], r15d
0x18005968c  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x180059691  mov     ecx, [rax]
0x180059693  cmp     ecx, 4
0x180059696  jbe     short loc_180059705
0x180059698  mov     ecx, [rdi+34h]
0x18005969b  lea     rdx, byte_18008B4B1
0x1800596a2  mov     [rbp+57h+var_78], ecx
0x1800596a5  lea     rcx, aMidixprocStall_2; "MidiXProc stall detected during wait."
0x1800596ac  mov     [rbp+57h+var_58], rcx
0x1800596b0  lea     rcx, aCmidixprocWait; "CMidiXProc::WaitForSendComplete"
0x1800596b7  mov     [rbp+57h+var_68], rcx
0x1800596bb  lea     rcx, [rbp+57h+var_70]
0x1800596bf  mov     [rsp+0D0h+var_88], rcx
0x1800596c4  lea     rcx, [rbp+57h+var_78]
0x1800596c8  mov     [rsp+0D0h+var_90], rcx
0x1800596cd  lea     rcx, [rbp+57h+var_7C]
0x1800596d1  mov     [rsp+0D0h+var_98], rcx
0x1800596d6  lea     rcx, [rbp+57h+var_58]
0x1800596da  mov     [rsp+0D0h+var_A0], rcx
0x1800596df  lea     rcx, [rbp+57h+var_60]
0x1800596e3  mov     [rsp+0D0h+var_A8], rcx
0x1800596e8  lea     rcx, [rbp+57h+var_68]
0x1800596ec  mov     [rsp+0D0h+var_B0], rcx
0x1800596f1  mov     rcx, rax
0x1800596f4  mov     dword ptr [rbp+57h+var_70], r14d
0x1800596f8  mov     [rbp+57h+var_7C], r15d
0x1800596fc  mov     [rbp+57h+var_60], rdi
0x180059700  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180059705  test    rsi, rsi
0x180059708  jz      short loc_180059713
0x18005970a  mov     rcx, rsi; lpCriticalSection
0x18005970d  call    cs:__imp_LeaveCriticalSection
0x180059713  test    rbx, rbx
0x180059716  jz      loc_18005955E
0x18005971c  mov     rcx, rbx; hObject
0x18005971f  call    cs:__imp_CloseHandle
0x180059725  test    eax, eax
0x180059727  jz      loc_18005984E
0x18005972d  jmp     loc_18005955E
0x180059732  test    rbx, rbx
0x180059735  jz      loc_180059822
0x18005973b  mov     rcx, rbx; hObject
0x18005973e  call    cs:__imp_CloseHandle
0x180059744  test    eax, eax
0x180059746  jz      loc_18005985D
0x18005974c  jmp     loc_180059822
0x180059751  mov     rsi, [rcx+40h]
0x180059755  cmp     [rcx+58h], rbx
0x180059759  jbe     short loc_180059780
0x18005975b  lea     r8, [rcx+48h]
0x18005975f  cmp     qword ptr [r8+18h], 7
0x180059764  jbe     short loc_180059769
0x180059766  mov     r8, [r8]; lpName
0x180059769  xor     edx, edx; bInheritHandle
0x18005976b  mov     ecx, 1F0003h; dwDesiredAccess
0x180059770  call    cs:__imp_OpenEventW
0x180059776  test    rax, rax
0x180059779  mov     rbx, rax
0x18005977c  cmovnz  rsi, rax
0x180059780  mov     rax, [rdi+78h]
0x180059784  add     r15d, r14d
0x180059787  mov     [rbp+57h+Handles], rax
0x18005978b  mov     [rbp+57h+var_48], rsi
0x18005978f  cmp     r12d, r14d
0x180059792  jbe     short loc_18005979C
0x180059794  mov     rax, [rdi+70h]
0x180059798  add     r15d, [rax+20h]
0x18005979c  xor     r13d, r13d
0x18005979f  lea     r14d, [r13+2]
0x1800597a3  jmp     short loc_1800597DA
0x1800597a5  mov     rcx, rsi; hEvent
0x1800597a8  call    cs:__imp_ResetEvent
0x1800597ae  mov     rax, [rdi+70h]
0x1800597b2  xor     edx, edx
0x1800597b4  mov     rcx, [rax+30h]
0x1800597b8  xor     eax, eax
0x1800597ba  lock cmpxchg [rcx], edx
0x1800597be  cmp     eax, r12d
0x1800597c1  jnb     short loc_1800597C6
0x1800597c3  inc     r13d
0x1800597c6  mov     rcx, [rdi+70h]
0x1800597ca  mov     r12d, r13d
0x1800597cd  imul    r12d, [rcx+20h]
0x1800597d2  add     r12d, eax
0x1800597d5  cmp     r12d, r15d
0x1800597d8  ja      short loc_180059810
0x1800597da  mov     r9d, 1388h; dwMilliseconds
0x1800597e0  lea     rdx, [rbp+57h+Handles]; lpHandles
0x1800597e4  xor     r8d, r8d; bWaitAll
0x1800597e7  mov     ecx, r14d; nCount
0x1800597ea  call    cs:__imp_WaitForMultipleObjects
0x1800597f0  cmp     eax, 1
0x1800597f3  jz      short loc_1800597A5
0x1800597f5  test    rbx, rbx
0x1800597f8  jz      loc_18005955E
0x1800597fe  mov     rcx, rbx; hObject
0x180059801  call    cs:__imp_CloseHandle
0x180059807  test    eax, eax
0x180059809  jz      short loc_18005986C
0x18005980b  jmp     loc_18005955E
0x180059810  test    rbx, rbx
0x180059813  jz      short loc_180059822
0x180059815  mov     rcx, rbx; hObject
0x180059818  call    cs:__imp_CloseHandle
0x18005981e  test    eax, eax
0x180059820  jz      short loc_18005983F
0x180059822  xor     eax, eax
0x180059824  jmp     short loc_18005982B
0x180059826  mov     eax, 1
0x18005982b  add     rsp, 98h
0x180059832  pop     r15
0x180059834  pop     r14
0x180059836  pop     r13
0x180059838  pop     r12
0x18005983a  pop     rdi
0x18005983b  pop     rsi
0x18005983c  pop     rbx
0x18005983d  pop     rbp
0x18005983e  retn
0x18005983f  mov     rcx, [rbp+5Fh]; this
0x180059843  mov     edx, 0A0Bh; void *
0x180059848  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18005984e  mov     rcx, [rbp+5Fh]; this
0x180059852  mov     edx, 0A0Bh; void *
0x180059857  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18005985d  mov     rcx, [rbp+5Fh]; this
0x180059861  mov     edx, 0A0Bh; void *
0x180059866  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18005986c  mov     rcx, [rbp+5Fh]; this
0x180059870  mov     edx, 0A0Bh; void *
0x180059875  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
  ... truncated ...
```
