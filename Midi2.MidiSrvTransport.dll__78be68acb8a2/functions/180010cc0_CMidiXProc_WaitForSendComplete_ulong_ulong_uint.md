# CMidiXProc::WaitForSendComplete(ulong,ulong,uint)

- ea: `0x180010cc0`
- end: `0x180011156`
- name: `?WaitForSendComplete@CMidiXProc@@AEAAJKKI@Z`
- size: `1174`
- prototype: `__int64 __fastcall(CMidiXProc *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180010260`

## callees

- `0x180001bfc`
- `0x180009014`
- `0x18000f984`
- `0x180010cc0`
- `0x18001131c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180010d27`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18001103c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180010d27`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18001103c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010e0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010ec7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010fd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010e0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010ec7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010fd9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180010ed2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180011074`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180010ed2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180011074`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010d73`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010f4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010d73`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010f4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010e1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010feb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001100a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800110cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800110e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010e1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010feb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001100a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800110cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800110e4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180010f31`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800110b6`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180010f31`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800110b6`

## string_xrefs

- `0x180010da6`: `MidiXProc Wait skipped during continued stall.`
- `0x180010db1`: `CMidiXProc::WaitForSendComplete`
- `0x180010e58`: `CMidiXProc::WaitForSendComplete`
- `0x180010f7c`: `CMidiXProc::WaitForSendComplete`
- `0x180010e4d`: `MidiXProc Detected stall resolved before WaitForSendComplete.`
- `0x180010f71`: `MidiXProc stall detected during wait.`

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

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::GetImpl'::`2'::impl);
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
              (unsigned int)byte_18001A253,
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
        (unsigned int)&unk_18001A8F8,
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
      (unsigned int)&dword_18001A424,
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
0x180010cc0  push    rbp
0x180010cc2  push    rbx
0x180010cc3  push    rsi
0x180010cc4  push    rdi
0x180010cc5  push    r12
0x180010cc7  push    r13
0x180010cc9  push    r14
0x180010ccb  push    r15
0x180010ccd  lea     rbp, [rsp-1Fh]
0x180010cd2  sub     rsp, 98h
0x180010cd9  mov     r15d, r9d
0x180010cdc  mov     r14d, r8d
0x180010cdf  mov     r12d, edx
0x180010ce2  mov     rdi, rcx
0x180010ce5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::GetImpl(void)'::`2'::impl
0x180010cec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::__private_IsEnabled(void)
0x180010cf1  mov     rcx, [rdi+70h]
0x180010cf5  test    rcx, rcx
0x180010cf8  jz      loc_1800110F2
0x180010cfe  xor     ebx, ebx
0x180010d00  test    al, al
0x180010d02  jz      loc_18001101D
0x180010d08  mov     r13, [rcx+40h]
0x180010d0c  cmp     [rcx+58h], rbx
0x180010d10  jbe     short loc_180010D37
0x180010d12  lea     r8, [rcx+48h]
0x180010d16  cmp     qword ptr [r8+18h], 7
0x180010d1b  jbe     short loc_180010D20
0x180010d1d  mov     r8, [r8]; lpName
0x180010d20  xor     edx, edx; bInheritHandle
0x180010d22  mov     ecx, 1F0003h; dwDesiredAccess
0x180010d27  call    cs:__imp_OpenEventW
0x180010d2d  test    rax, rax
0x180010d30  mov     rbx, rax
0x180010d33  cmovnz  r13, rax
0x180010d37  mov     rax, [rdi+78h]
0x180010d3b  lea     edx, [r14+r15]
0x180010d3f  mov     [rbp+57h+Handles], rax
0x180010d43  mov     [rbp+57h+var_7C], edx
0x180010d46  mov     [rbp+57h+var_48], r13
0x180010d4a  cmp     r12d, r14d
0x180010d4d  jbe     short loc_180010D59
0x180010d4f  mov     rax, [rdi+70h]
0x180010d53  add     edx, [rax+20h]
0x180010d56  mov     [rbp+57h+var_7C], edx
0x180010d59  mov     rax, [rdi+70h]
0x180010d5d  xor     edx, edx
0x180010d5f  mov     rcx, [rax+30h]
0x180010d63  xor     eax, eax
0x180010d65  lock cmpxchg [rcx], edx
0x180010d69  lea     rsi, [rdi+8]
0x180010d6d  mov     r15d, eax
0x180010d70  mov     rcx, rsi; lpCriticalSection
0x180010d73  call    cs:__imp_EnterCriticalSection
0x180010d79  cmp     byte ptr [rdi+30h], 0
0x180010d7d  jz      loc_180010EB8
0x180010d83  cmp     r15d, [rdi+34h]
0x180010d87  jnz     loc_180010E34
0x180010d8d  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x180010d92  mov     ecx, [rax]
0x180010d94  cmp     ecx, 4
0x180010d97  jbe     short loc_180010E06
0x180010d99  mov     ecx, [rdi+34h]
0x180010d9c  lea     rdx, dword_18001A424
0x180010da3  mov     [rbp+57h+var_80], ecx
0x180010da6  lea     rcx, aMidixprocWaitS; "MidiXProc Wait skipped during continued"...
0x180010dad  mov     [rbp+57h+var_70], rcx
0x180010db1  lea     rcx, aCmidixprocWait; "CMidiXProc::WaitForSendComplete"
0x180010db8  mov     [rbp+57h+var_60], rcx
0x180010dbc  lea     rcx, [rbp+57h+var_7C]
0x180010dc0  mov     [rsp+0D0h+var_88], rcx
0x180010dc5  lea     rcx, [rbp+57h+var_80]
0x180010dc9  mov     [rsp+0D0h+var_90], rcx
0x180010dce  lea     rcx, [rbp+57h+var_78]
0x180010dd2  mov     [rsp+0D0h+var_98], rcx
0x180010dd7  lea     rcx, [rbp+57h+var_70]
0x180010ddb  mov     [rsp+0D0h+var_A0], rcx
0x180010de0  lea     rcx, [rbp+57h+var_68]
0x180010de4  mov     [rsp+0D0h+var_A8], rcx
0x180010de9  lea     rcx, [rbp+57h+var_60]
0x180010ded  mov     [rsp+0D0h+var_B0], rcx
0x180010df2  mov     rcx, rax
0x180010df5  mov     [rbp+57h+var_7C], r14d
0x180010df9  mov     [rbp+57h+var_78], r15d
0x180010dfd  mov     [rbp+57h+var_68], rdi
0x180010e01  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010e06  test    rsi, rsi
0x180010e09  jz      short loc_180010E14
0x180010e0b  mov     rcx, rsi; lpCriticalSection
0x180010e0e  call    cs:__imp_LeaveCriticalSection
0x180010e14  test    rbx, rbx
0x180010e17  jz      short loc_180010E2A
0x180010e19  mov     rcx, rbx; hObject
0x180010e1c  call    cs:__imp_CloseHandle
0x180010e22  test    eax, eax
0x180010e24  jz      loc_180011147
0x180010e2a  mov     eax, 80004004h
0x180010e2f  jmp     loc_1800110F7
0x180010e34  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x180010e39  mov     ecx, [rax]
0x180010e3b  cmp     ecx, 4
0x180010e3e  jbe     short loc_180010EAD
0x180010e40  mov     ecx, [rdi+34h]
0x180010e43  lea     rdx, unk_18001A8F8
0x180010e4a  mov     [rbp+57h+var_80], ecx
0x180010e4d  lea     rcx, aMidixprocDetec; "MidiXProc Detected stall resolved befor"...
0x180010e54  mov     [rbp+57h+var_60], rcx
0x180010e58  lea     rcx, aCmidixprocWait; "CMidiXProc::WaitForSendComplete"
0x180010e5f  mov     [rbp+57h+var_58], rcx
0x180010e63  lea     rcx, [rbp+57h+var_78]
0x180010e67  mov     [rsp+0D0h+var_88], rcx
0x180010e6c  lea     rcx, [rbp+57h+var_80]
0x180010e70  mov     [rsp+0D0h+var_90], rcx
0x180010e75  lea     rcx, [rbp+57h+var_70]
0x180010e79  mov     [rsp+0D0h+var_98], rcx
0x180010e7e  lea     rcx, [rbp+57h+var_60]
0x180010e82  mov     [rsp+0D0h+var_A0], rcx
0x180010e87  lea     rcx, [rbp+57h+var_68]
0x180010e8b  mov     [rsp+0D0h+var_A8], rcx
0x180010e90  lea     rcx, [rbp+57h+var_58]
0x180010e94  mov     [rsp+0D0h+var_B0], rcx
0x180010e99  mov     rcx, rax
0x180010e9c  mov     [rbp+57h+var_78], r14d
0x180010ea0  mov     dword ptr [rbp+57h+var_70], r15d
0x180010ea4  mov     [rbp+57h+var_68], rdi
0x180010ea8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010ead  mov     byte ptr [rdi+30h], 0
0x180010eb1  mov     dword ptr [rdi+34h], 0
0x180010eb8  mov     [rbp+57h+var_80], 0
0x180010ebf  test    rsi, rsi
0x180010ec2  jz      short loc_180010F20
0x180010ec4  mov     rcx, rsi; lpCriticalSection
0x180010ec7  call    cs:__imp_LeaveCriticalSection
0x180010ecd  jmp     short loc_180010F20
0x180010ecf  mov     rcx, r13; hEvent
0x180010ed2  call    cs:__imp_ResetEvent
0x180010ed8  mov     rax, [rdi+70h]
0x180010edc  xor     edx, edx
0x180010ede  mov     rcx, [rax+30h]
0x180010ee2  xor     eax, eax
0x180010ee4  lock cmpxchg [rcx], edx
0x180010ee8  mov     r9d, [rbp+57h+var_80]
0x180010eec  mov     rcx, [rdi+70h]
0x180010ef0  mov     edx, [rcx+20h]
0x180010ef3  mov     r8d, edx
0x180010ef6  imul    r8d, r9d
0x180010efa  add     r8d, eax
0x180010efd  lea     eax, [r9+1]
0x180010f01  cmp     r8d, r12d
0x180010f04  cmovnb  eax, r9d
0x180010f08  lea     r15d, [r8+rdx]
0x180010f0c  mov     [rbp+57h+var_80], eax
0x180010f0f  cmovnb  r15d, r8d
0x180010f13  cmp     r15d, [rbp+57h+var_7C]
0x180010f17  jnb     loc_180010FFE
0x180010f1d  mov     r12d, r15d
0x180010f20  xor     r8d, r8d; bWaitAll
0x180010f23  lea     rdx, [rbp+57h+Handles]; lpHandles
0x180010f27  mov     r9d, 3E8h; dwMilliseconds
0x180010f2d  lea     ecx, [r8+2]; nCount
0x180010f31  call    cs:__imp_WaitForMultipleObjects
0x180010f37  cmp     eax, 1
0x180010f3a  jz      short loc_180010ECF
0x180010f3c  cmp     eax, 102h
0x180010f41  jnz     loc_180010FDF
0x180010f47  mov     rcx, rsi; lpCriticalSection
0x180010f4a  call    cs:__imp_EnterCriticalSection
0x180010f50  mov     byte ptr [rdi+30h], 1
0x180010f54  mov     [rdi+34h], r15d
0x180010f58  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x180010f5d  mov     ecx, [rax]
0x180010f5f  cmp     ecx, 4
0x180010f62  jbe     short loc_180010FD1
0x180010f64  mov     ecx, [rdi+34h]
0x180010f67  lea     rdx, byte_18001A253
0x180010f6e  mov     [rbp+57h+var_78], ecx
0x180010f71  lea     rcx, aMidixprocStall_2; "MidiXProc stall detected during wait."
0x180010f78  mov     [rbp+57h+var_58], rcx
0x180010f7c  lea     rcx, aCmidixprocWait; "CMidiXProc::WaitForSendComplete"
0x180010f83  mov     [rbp+57h+var_68], rcx
0x180010f87  lea     rcx, [rbp+57h+var_70]
0x180010f8b  mov     [rsp+0D0h+var_88], rcx
0x180010f90  lea     rcx, [rbp+57h+var_78]
0x180010f94  mov     [rsp+0D0h+var_90], rcx
0x180010f99  lea     rcx, [rbp+57h+var_7C]
0x180010f9d  mov     [rsp+0D0h+var_98], rcx
0x180010fa2  lea     rcx, [rbp+57h+var_58]
0x180010fa6  mov     [rsp+0D0h+var_A0], rcx
0x180010fab  lea     rcx, [rbp+57h+var_60]
0x180010faf  mov     [rsp+0D0h+var_A8], rcx
0x180010fb4  lea     rcx, [rbp+57h+var_68]
0x180010fb8  mov     [rsp+0D0h+var_B0], rcx
0x180010fbd  mov     rcx, rax
0x180010fc0  mov     dword ptr [rbp+57h+var_70], r14d
0x180010fc4  mov     [rbp+57h+var_7C], r15d
0x180010fc8  mov     [rbp+57h+var_60], rdi
0x180010fcc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010fd1  test    rsi, rsi
0x180010fd4  jz      short loc_180010FDF
0x180010fd6  mov     rcx, rsi; lpCriticalSection
0x180010fd9  call    cs:__imp_LeaveCriticalSection
0x180010fdf  test    rbx, rbx
0x180010fe2  jz      loc_180010E2A
0x180010fe8  mov     rcx, rbx; hObject
0x180010feb  call    cs:__imp_CloseHandle
0x180010ff1  test    eax, eax
0x180010ff3  jz      loc_18001111A
0x180010ff9  jmp     loc_180010E2A
0x180010ffe  test    rbx, rbx
0x180011001  jz      loc_1800110EE
0x180011007  mov     rcx, rbx; hObject
0x18001100a  call    cs:__imp_CloseHandle
0x180011010  test    eax, eax
0x180011012  jz      loc_180011129
0x180011018  jmp     loc_1800110EE
0x18001101d  mov     rsi, [rcx+40h]
0x180011021  cmp     [rcx+58h], rbx
0x180011025  jbe     short loc_18001104C
0x180011027  lea     r8, [rcx+48h]
0x18001102b  cmp     qword ptr [r8+18h], 7
0x180011030  jbe     short loc_180011035
0x180011032  mov     r8, [r8]; lpName
0x180011035  xor     edx, edx; bInheritHandle
0x180011037  mov     ecx, 1F0003h; dwDesiredAccess
0x18001103c  call    cs:__imp_OpenEventW
0x180011042  test    rax, rax
0x180011045  mov     rbx, rax
0x180011048  cmovnz  rsi, rax
0x18001104c  mov     rax, [rdi+78h]
0x180011050  add     r15d, r14d
0x180011053  mov     [rbp+57h+Handles], rax
0x180011057  mov     [rbp+57h+var_48], rsi
0x18001105b  cmp     r12d, r14d
0x18001105e  jbe     short loc_180011068
0x180011060  mov     rax, [rdi+70h]
0x180011064  add     r15d, [rax+20h]
0x180011068  xor     r13d, r13d
0x18001106b  lea     r14d, [r13+2]
0x18001106f  jmp     short loc_1800110A6
0x180011071  mov     rcx, rsi; hEvent
0x180011074  call    cs:__imp_ResetEvent
0x18001107a  mov     rax, [rdi+70h]
0x18001107e  xor     edx, edx
0x180011080  mov     rcx, [rax+30h]
0x180011084  xor     eax, eax
0x180011086  lock cmpxchg [rcx], edx
0x18001108a  cmp     eax, r12d
0x18001108d  jnb     short loc_180011092
0x18001108f  inc     r13d
0x180011092  mov     rcx, [rdi+70h]
0x180011096  mov     r12d, r13d
0x180011099  imul    r12d, [rcx+20h]
0x18001109e  add     r12d, eax
0x1800110a1  cmp     r12d, r15d
0x1800110a4  ja      short loc_1800110DC
0x1800110a6  mov     r9d, 1388h; dwMilliseconds
0x1800110ac  lea     rdx, [rbp+57h+Handles]; lpHandles
0x1800110b0  xor     r8d, r8d; bWaitAll
0x1800110b3  mov     ecx, r14d; nCount
0x1800110b6  call    cs:__imp_WaitForMultipleObjects
0x1800110bc  cmp     eax, 1
0x1800110bf  jz      short loc_180011071
0x1800110c1  test    rbx, rbx
0x1800110c4  jz      loc_180010E2A
0x1800110ca  mov     rcx, rbx; hObject
0x1800110cd  call    cs:__imp_CloseHandle
0x1800110d3  test    eax, eax
0x1800110d5  jz      short loc_180011138
0x1800110d7  jmp     loc_180010E2A
0x1800110dc  test    rbx, rbx
0x1800110df  jz      short loc_1800110EE
0x1800110e1  mov     rcx, rbx; hObject
0x1800110e4  call    cs:__imp_CloseHandle
0x1800110ea  test    eax, eax
0x1800110ec  jz      short loc_18001110B
0x1800110ee  xor     eax, eax
0x1800110f0  jmp     short loc_1800110F7
0x1800110f2  mov     eax, 1
0x1800110f7  add     rsp, 98h
0x1800110fe  pop     r15
0x180011100  pop     r14
0x180011102  pop     r13
0x180011104  pop     r12
0x180011106  pop     rdi
0x180011107  pop     rsi
0x180011108  pop     rbx
0x180011109  pop     rbp
0x18001110a  retn
0x18001110b  mov     rcx, [rbp+5Fh]; this
0x18001110f  mov     edx, 0A0Bh; void *
0x180011114  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001111a  mov     rcx, [rbp+5Fh]; this
0x18001111e  mov     edx, 0A0Bh; void *
0x180011123  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011129  mov     rcx, [rbp+5Fh]; this
0x18001112d  mov     edx, 0A0Bh; void *
0x180011132  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011138  mov     rcx, [rbp+5Fh]; this
0x18001113c  mov     edx, 0A0Bh; void *
0x180011141  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
  ... truncated ...
```
