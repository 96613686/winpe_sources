# CMidiXProc::WaitForSendComplete(ulong,ulong,uint)

- ea: `0x140047c20`
- end: `0x1400480b6`
- name: `?WaitForSendComplete@CMidiXProc@@AEAAJKKI@Z`
- size: `1174`
- prototype: `__int64 __fastcall(CMidiXProc *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140047258`

## callees

- `0x140003640`
- `0x14000c55c`
- `0x140046fc4`
- `0x140047c20`
- `0x1400480bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140047c87`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140047f9c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140047c87`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140047f9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140047d6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140047e27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140047f39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140047d6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140047e27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140047f39`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140047e32`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140047fd4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140047e32`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140047fd4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140047cd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140047eaa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140047cd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140047eaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047d7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047f4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047f6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004802d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140048044`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047d7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047f4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047f6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004802d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140048044`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140047e91`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140048016`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140047e91`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140048016`

## string_xrefs

- `0x140047dad`: `MidiXProc Detected stall resolved before WaitForSendComplete.`
- `0x140047ed1`: `MidiXProc stall detected during wait.`
- `0x140047d06`: `MidiXProc Wait skipped during continued stall.`
- `0x140047d11`: `CMidiXProc::WaitForSendComplete`
- `0x140047db8`: `CMidiXProc::WaitForSendComplete`
- `0x140047edc`: `CMidiXProc::WaitForSendComplete`

## pseudocode

```c
__int64 __fastcall CMidiXProc::WaitForSendComplete(CMidiXProc *this, unsigned __int32 a2, unsigned __int32 a3, int a4)
{
  char IsEnabled; // al
  _QWORD *v9; // rcx
  void *v10; // rbx
  void *v11; // r13
  const WCHAR *v12; // r8
  HANDLE v13; // rax
  unsigned __int32 v14; // r15d
  const struct _tlgProvider_t *v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  const struct _tlgProvider_t *v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  signed __int32 v24; // eax
  int v25; // edx
  unsigned __int32 v26; // r8d
  int v27; // eax
  DWORD v28; // eax
  const struct _tlgProvider_t *v29; // rax
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  void *v36; // rsi
  const WCHAR *v37; // r8
  HANDLE v38; // rax
  unsigned __int32 v39; // r15d
  int v40; // r13d
  unsigned __int32 v41; // eax
  __int64 v42; // r8
  const char *v43; // r9
  __int64 v44; // r8
  const char *v45; // r9
  int v46; // [rsp+50h] [rbp-29h]
  unsigned int v47; // [rsp+54h] [rbp-25h]
  const wchar_t *v48; // [rsp+60h] [rbp-19h] BYREF
  const char *v49; // [rsp+68h] [rbp-11h] BYREF
  const char *v50; // [rsp+70h] [rbp-9h] BYREF
  const char *v51; // [rsp+78h] [rbp-1h] BYREF
  HANDLE Handles; // [rsp+80h] [rbp+7h] BYREF
  void *v53; // [rsp+88h] [rbp+Fh]
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
    v53 = v36;
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
  v53 = v11;
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
            v51 = (const char *)L"MidiXProc stall detected during wait.";
            v49 = "CMidiXProc::WaitForSendComplete";
            LODWORD(v48) = a3;
            v50 = (const char *)this;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (__int64)v29,
              (__int64)&byte_14008C627,
              v30,
              v31,
              &v49,
              (__int64)&v50,
              &v51);
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
      v25 = *(_DWORD *)(*((_QWORD *)this + 14) + 32LL);
      v26 = v24 + v46 * v25;
      v27 = v46 + 1;
      if ( v26 >= a2 )
        v27 = v46;
      v14 = v26 + v25;
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
      v50 = (const char *)L"MidiXProc Detected stall resolved before WaitForSendComplete.";
      v51 = "CMidiXProc::WaitForSendComplete";
      LODWORD(v48) = v14;
      v49 = (const char *)this;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v21,
        (__int64)&dword_14008CCCC,
        v22,
        v23,
        &v51,
        (__int64)&v49,
        &v50);
    }
    *((_BYTE *)this + 48) = 0;
    *((_DWORD *)this + 13) = 0;
    goto LABEL_22;
  }
  v15 = MidiXProcTelemetryProvider::Provider();
  if ( *(_DWORD *)v15 > 4u )
  {
    v48 = L"MidiXProc Wait skipped during continued stall.";
    v50 = "CMidiXProc::WaitForSendComplete";
    v49 = (const char *)this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)v15,
      (__int64)&unk_14008C7F8,
      v16,
      v17,
      &v50,
      (__int64)&v49,
      &v48);
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
0x140047c20  push    rbp
0x140047c22  push    rbx
0x140047c23  push    rsi
0x140047c24  push    rdi
0x140047c25  push    r12
0x140047c27  push    r13
0x140047c29  push    r14
0x140047c2b  push    r15
0x140047c2d  lea     rbp, [rsp-1Fh]
0x140047c32  sub     rsp, 98h
0x140047c39  mov     r15d, r9d
0x140047c3c  mov     r14d, r8d
0x140047c3f  mov     r12d, edx
0x140047c42  mov     rdi, rcx
0x140047c45  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::GetImpl(void)'::`2'::impl
0x140047c4c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::__private_IsEnabled(void)
0x140047c51  mov     rcx, [rdi+70h]
0x140047c55  test    rcx, rcx
0x140047c58  jz      loc_140048052
0x140047c5e  xor     ebx, ebx
0x140047c60  test    al, al
0x140047c62  jz      loc_140047F7D
0x140047c68  mov     r13, [rcx+40h]
0x140047c6c  cmp     [rcx+58h], rbx
0x140047c70  jbe     short loc_140047C97
0x140047c72  lea     r8, [rcx+48h]
0x140047c76  cmp     qword ptr [r8+18h], 7
0x140047c7b  jbe     short loc_140047C80
0x140047c7d  mov     r8, [r8]; lpName
0x140047c80  xor     edx, edx; bInheritHandle
0x140047c82  mov     ecx, 1F0003h; dwDesiredAccess
0x140047c87  call    cs:__imp_OpenEventW
0x140047c8d  test    rax, rax
0x140047c90  mov     rbx, rax
0x140047c93  cmovnz  r13, rax
0x140047c97  mov     rax, [rdi+78h]
0x140047c9b  lea     edx, [r14+r15]
0x140047c9f  mov     [rbp+57h+Handles], rax
0x140047ca3  mov     [rbp+57h+var_7C], edx
0x140047ca6  mov     [rbp+57h+var_48], r13
0x140047caa  cmp     r12d, r14d
0x140047cad  jbe     short loc_140047CB9
0x140047caf  mov     rax, [rdi+70h]
0x140047cb3  add     edx, [rax+20h]
0x140047cb6  mov     [rbp+57h+var_7C], edx
0x140047cb9  mov     rax, [rdi+70h]
0x140047cbd  xor     edx, edx
0x140047cbf  mov     rcx, [rax+30h]
0x140047cc3  xor     eax, eax
0x140047cc5  lock cmpxchg [rcx], edx
0x140047cc9  lea     rsi, [rdi+8]
0x140047ccd  mov     r15d, eax
0x140047cd0  mov     rcx, rsi; lpCriticalSection
0x140047cd3  call    cs:__imp_EnterCriticalSection
0x140047cd9  cmp     byte ptr [rdi+30h], 0
0x140047cdd  jz      loc_140047E18
0x140047ce3  cmp     r15d, [rdi+34h]
0x140047ce7  jnz     loc_140047D94
0x140047ced  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x140047cf2  mov     ecx, [rax]
0x140047cf4  cmp     ecx, 4
0x140047cf7  jbe     short loc_140047D66
0x140047cf9  mov     ecx, [rdi+34h]
0x140047cfc  lea     rdx, unk_14008C7F8
0x140047d03  mov     [rbp+57h+var_80], ecx
0x140047d06  lea     rcx, aMidixprocWaitS; "MidiXProc Wait skipped during continued"...
0x140047d0d  mov     [rbp+57h+var_70], rcx
0x140047d11  lea     rcx, aCmidixprocWait; "CMidiXProc::WaitForSendComplete"
0x140047d18  mov     [rbp+57h+var_60], rcx
0x140047d1c  lea     rcx, [rbp+57h+var_7C]
0x140047d20  mov     [rsp+0D0h+var_88], rcx
0x140047d25  lea     rcx, [rbp+57h+var_80]
0x140047d29  mov     [rsp+0D0h+var_90], rcx
0x140047d2e  lea     rcx, [rbp+57h+var_78]
0x140047d32  mov     [rsp+0D0h+var_98], rcx
0x140047d37  lea     rcx, [rbp+57h+var_70]
0x140047d3b  mov     [rsp+0D0h+var_A0], rcx
0x140047d40  lea     rcx, [rbp+57h+var_68]
0x140047d44  mov     [rsp+0D0h+var_A8], rcx
0x140047d49  lea     rcx, [rbp+57h+var_60]
0x140047d4d  mov     [rsp+0D0h+var_B0], rcx
0x140047d52  mov     rcx, rax
0x140047d55  mov     [rbp+57h+var_7C], r14d
0x140047d59  mov     [rbp+57h+var_78], r15d
0x140047d5d  mov     [rbp+57h+var_68], rdi
0x140047d61  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140047d66  test    rsi, rsi
0x140047d69  jz      short loc_140047D74
0x140047d6b  mov     rcx, rsi; lpCriticalSection
0x140047d6e  call    cs:__imp_LeaveCriticalSection
0x140047d74  test    rbx, rbx
0x140047d77  jz      short loc_140047D8A
0x140047d79  mov     rcx, rbx; hObject
0x140047d7c  call    cs:__imp_CloseHandle
0x140047d82  test    eax, eax
0x140047d84  jz      loc_1400480A7
0x140047d8a  mov     eax, 80004004h
0x140047d8f  jmp     loc_140048057
0x140047d94  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x140047d99  mov     ecx, [rax]
0x140047d9b  cmp     ecx, 4
0x140047d9e  jbe     short loc_140047E0D
0x140047da0  mov     ecx, [rdi+34h]
0x140047da3  lea     rdx, dword_14008CCCC
0x140047daa  mov     [rbp+57h+var_80], ecx
0x140047dad  lea     rcx, aMidixprocDetec; "MidiXProc Detected stall resolved befor"...
0x140047db4  mov     [rbp+57h+var_60], rcx
0x140047db8  lea     rcx, aCmidixprocWait; "CMidiXProc::WaitForSendComplete"
0x140047dbf  mov     [rbp+57h+var_58], rcx
0x140047dc3  lea     rcx, [rbp+57h+var_78]
0x140047dc7  mov     [rsp+0D0h+var_88], rcx
0x140047dcc  lea     rcx, [rbp+57h+var_80]
0x140047dd0  mov     [rsp+0D0h+var_90], rcx
0x140047dd5  lea     rcx, [rbp+57h+var_70]
0x140047dd9  mov     [rsp+0D0h+var_98], rcx
0x140047dde  lea     rcx, [rbp+57h+var_60]
0x140047de2  mov     [rsp+0D0h+var_A0], rcx
0x140047de7  lea     rcx, [rbp+57h+var_68]
0x140047deb  mov     [rsp+0D0h+var_A8], rcx
0x140047df0  lea     rcx, [rbp+57h+var_58]
0x140047df4  mov     [rsp+0D0h+var_B0], rcx
0x140047df9  mov     rcx, rax
0x140047dfc  mov     [rbp+57h+var_78], r14d
0x140047e00  mov     dword ptr [rbp+57h+var_70], r15d
0x140047e04  mov     [rbp+57h+var_68], rdi
0x140047e08  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140047e0d  mov     byte ptr [rdi+30h], 0
0x140047e11  mov     dword ptr [rdi+34h], 0
0x140047e18  mov     [rbp+57h+var_80], 0
0x140047e1f  test    rsi, rsi
0x140047e22  jz      short loc_140047E80
0x140047e24  mov     rcx, rsi; lpCriticalSection
0x140047e27  call    cs:__imp_LeaveCriticalSection
0x140047e2d  jmp     short loc_140047E80
0x140047e2f  mov     rcx, r13; hEvent
0x140047e32  call    cs:__imp_ResetEvent
0x140047e38  mov     rax, [rdi+70h]
0x140047e3c  xor     edx, edx
0x140047e3e  mov     rcx, [rax+30h]
0x140047e42  xor     eax, eax
0x140047e44  lock cmpxchg [rcx], edx
0x140047e48  mov     r9d, [rbp+57h+var_80]
0x140047e4c  mov     rcx, [rdi+70h]
0x140047e50  mov     edx, [rcx+20h]
0x140047e53  mov     r8d, edx
0x140047e56  imul    r8d, r9d
0x140047e5a  add     r8d, eax
0x140047e5d  lea     eax, [r9+1]
0x140047e61  cmp     r8d, r12d
0x140047e64  cmovnb  eax, r9d
0x140047e68  lea     r15d, [r8+rdx]
0x140047e6c  mov     [rbp+57h+var_80], eax
0x140047e6f  cmovnb  r15d, r8d
0x140047e73  cmp     r15d, [rbp+57h+var_7C]
0x140047e77  jnb     loc_140047F5E
0x140047e7d  mov     r12d, r15d
0x140047e80  xor     r8d, r8d; bWaitAll
0x140047e83  lea     rdx, [rbp+57h+Handles]; lpHandles
0x140047e87  mov     r9d, 3E8h; dwMilliseconds
0x140047e8d  lea     ecx, [r8+2]; nCount
0x140047e91  call    cs:__imp_WaitForMultipleObjects
0x140047e97  cmp     eax, 1
0x140047e9a  jz      short loc_140047E2F
0x140047e9c  cmp     eax, 102h
0x140047ea1  jnz     loc_140047F3F
0x140047ea7  mov     rcx, rsi; lpCriticalSection
0x140047eaa  call    cs:__imp_EnterCriticalSection
0x140047eb0  mov     byte ptr [rdi+30h], 1
0x140047eb4  mov     [rdi+34h], r15d
0x140047eb8  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x140047ebd  mov     ecx, [rax]
0x140047ebf  cmp     ecx, 4
0x140047ec2  jbe     short loc_140047F31
0x140047ec4  mov     ecx, [rdi+34h]
0x140047ec7  lea     rdx, byte_14008C627
0x140047ece  mov     [rbp+57h+var_78], ecx
0x140047ed1  lea     rcx, aMidixprocStall_2; "MidiXProc stall detected during wait."
0x140047ed8  mov     [rbp+57h+var_58], rcx
0x140047edc  lea     rcx, aCmidixprocWait; "CMidiXProc::WaitForSendComplete"
0x140047ee3  mov     [rbp+57h+var_68], rcx
0x140047ee7  lea     rcx, [rbp+57h+var_70]
0x140047eeb  mov     [rsp+0D0h+var_88], rcx
0x140047ef0  lea     rcx, [rbp+57h+var_78]
0x140047ef4  mov     [rsp+0D0h+var_90], rcx
0x140047ef9  lea     rcx, [rbp+57h+var_7C]
0x140047efd  mov     [rsp+0D0h+var_98], rcx
0x140047f02  lea     rcx, [rbp+57h+var_58]
0x140047f06  mov     [rsp+0D0h+var_A0], rcx
0x140047f0b  lea     rcx, [rbp+57h+var_60]
0x140047f0f  mov     [rsp+0D0h+var_A8], rcx
0x140047f14  lea     rcx, [rbp+57h+var_68]
0x140047f18  mov     [rsp+0D0h+var_B0], rcx
0x140047f1d  mov     rcx, rax
0x140047f20  mov     dword ptr [rbp+57h+var_70], r14d
0x140047f24  mov     [rbp+57h+var_7C], r15d
0x140047f28  mov     [rbp+57h+var_60], rdi
0x140047f2c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140047f31  test    rsi, rsi
0x140047f34  jz      short loc_140047F3F
0x140047f36  mov     rcx, rsi; lpCriticalSection
0x140047f39  call    cs:__imp_LeaveCriticalSection
0x140047f3f  test    rbx, rbx
0x140047f42  jz      loc_140047D8A
0x140047f48  mov     rcx, rbx; hObject
0x140047f4b  call    cs:__imp_CloseHandle
0x140047f51  test    eax, eax
0x140047f53  jz      loc_14004807A
0x140047f59  jmp     loc_140047D8A
0x140047f5e  test    rbx, rbx
0x140047f61  jz      loc_14004804E
0x140047f67  mov     rcx, rbx; hObject
0x140047f6a  call    cs:__imp_CloseHandle
0x140047f70  test    eax, eax
0x140047f72  jz      loc_140048089
0x140047f78  jmp     loc_14004804E
0x140047f7d  mov     rsi, [rcx+40h]
0x140047f81  cmp     [rcx+58h], rbx
0x140047f85  jbe     short loc_140047FAC
0x140047f87  lea     r8, [rcx+48h]
0x140047f8b  cmp     qword ptr [r8+18h], 7
0x140047f90  jbe     short loc_140047F95
0x140047f92  mov     r8, [r8]; lpName
0x140047f95  xor     edx, edx; bInheritHandle
0x140047f97  mov     ecx, 1F0003h; dwDesiredAccess
0x140047f9c  call    cs:__imp_OpenEventW
0x140047fa2  test    rax, rax
0x140047fa5  mov     rbx, rax
0x140047fa8  cmovnz  rsi, rax
0x140047fac  mov     rax, [rdi+78h]
0x140047fb0  add     r15d, r14d
0x140047fb3  mov     [rbp+57h+Handles], rax
0x140047fb7  mov     [rbp+57h+var_48], rsi
0x140047fbb  cmp     r12d, r14d
0x140047fbe  jbe     short loc_140047FC8
0x140047fc0  mov     rax, [rdi+70h]
0x140047fc4  add     r15d, [rax+20h]
0x140047fc8  xor     r13d, r13d
0x140047fcb  lea     r14d, [r13+2]
0x140047fcf  jmp     short loc_140048006
0x140047fd1  mov     rcx, rsi; hEvent
0x140047fd4  call    cs:__imp_ResetEvent
0x140047fda  mov     rax, [rdi+70h]
0x140047fde  xor     edx, edx
0x140047fe0  mov     rcx, [rax+30h]
0x140047fe4  xor     eax, eax
0x140047fe6  lock cmpxchg [rcx], edx
0x140047fea  cmp     eax, r12d
0x140047fed  jnb     short loc_140047FF2
0x140047fef  inc     r13d
0x140047ff2  mov     rcx, [rdi+70h]
0x140047ff6  mov     r12d, r13d
0x140047ff9  imul    r12d, [rcx+20h]
0x140047ffe  add     r12d, eax
0x140048001  cmp     r12d, r15d
0x140048004  ja      short loc_14004803C
0x140048006  mov     r9d, 1388h; dwMilliseconds
0x14004800c  lea     rdx, [rbp+57h+Handles]; lpHandles
0x140048010  xor     r8d, r8d; bWaitAll
0x140048013  mov     ecx, r14d; nCount
0x140048016  call    cs:__imp_WaitForMultipleObjects
0x14004801c  cmp     eax, 1
0x14004801f  jz      short loc_140047FD1
0x140048021  test    rbx, rbx
0x140048024  jz      loc_140047D8A
0x14004802a  mov     rcx, rbx; hObject
0x14004802d  call    cs:__imp_CloseHandle
0x140048033  test    eax, eax
0x140048035  jz      short loc_140048098
0x140048037  jmp     loc_140047D8A
0x14004803c  test    rbx, rbx
0x14004803f  jz      short loc_14004804E
0x140048041  mov     rcx, rbx; hObject
0x140048044  call    cs:__imp_CloseHandle
0x14004804a  test    eax, eax
0x14004804c  jz      short loc_14004806B
0x14004804e  xor     eax, eax
0x140048050  jmp     short loc_140048057
0x140048052  mov     eax, 1
0x140048057  add     rsp, 98h
0x14004805e  pop     r15
0x140048060  pop     r14
0x140048062  pop     r13
0x140048064  pop     r12
0x140048066  pop     rdi
0x140048067  pop     rsi
0x140048068  pop     rbx
0x140048069  pop     rbp
0x14004806a  retn
0x14004806b  mov     rcx, [rbp+5Fh]; this
0x14004806f  mov     edx, 0A0Bh; void *
0x140048074  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14004807a  mov     rcx, [rbp+5Fh]; this
0x14004807e  mov     edx, 0A0Bh; void *
0x140048083  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140048089  mov     rcx, [rbp+5Fh]; this
0x14004808d  mov     edx, 0A0Bh; void *
0x140048092  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140048098  mov     rcx, [rbp+5Fh]; this
0x14004809c  mov     edx, 0A0Bh; void *
0x1400480a1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
  ... truncated ...
```
