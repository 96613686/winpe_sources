# CMidiXProc::WaitForSendComplete(ulong,ulong,uint)

- ea: `0x18003de34`
- end: `0x18003e2ca`
- name: `?WaitForSendComplete@CMidiXProc@@AEAAJKKI@Z`
- size: `1174`
- prototype: `__int64 __fastcall(CMidiXProc *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003d46c`

## callees

- `0x180002454`
- `0x18000bb04`
- `0x18003d1d8`
- `0x18003de34`
- `0x18003e2d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003df82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e03b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e14d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003df82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e03b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e14d`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003de9b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003e1b0`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003de9b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003e1b0`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003e046`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003e1e8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003e046`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003e1e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003dee7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e0be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003dee7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e0be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003df90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e15f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e17e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e241`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e258`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003df90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e15f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e17e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e241`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e258`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18003e0a5`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18003e22a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18003e0a5`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18003e22a`

## string_xrefs

- `0x18003df1a`: `MidiXProc Wait skipped during continued stall.`
- `0x18003df25`: `CMidiXProc::WaitForSendComplete`
- `0x18003dfcc`: `CMidiXProc::WaitForSendComplete`
- `0x18003e0f0`: `CMidiXProc::WaitForSendComplete`
- `0x18003dfc1`: `MidiXProc Detected stall resolved before WaitForSendComplete.`
- `0x18003e0e5`: `MidiXProc stall detected during wait.`

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
              (unsigned int)&byte_180068EB7,
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
        (unsigned int)&dword_18006955C,
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
      (unsigned int)&unk_180069088,
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
0x18003de34  push    rbp
0x18003de36  push    rbx
0x18003de37  push    rsi
0x18003de38  push    rdi
0x18003de39  push    r12
0x18003de3b  push    r13
0x18003de3d  push    r14
0x18003de3f  push    r15
0x18003de41  lea     rbp, [rsp-1Fh]
0x18003de46  sub     rsp, 98h
0x18003de4d  mov     r15d, r9d
0x18003de50  mov     r14d, r8d
0x18003de53  mov     r12d, edx
0x18003de56  mov     rdi, rcx
0x18003de59  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::GetImpl(void)'::`2'::impl
0x18003de60  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::__private_IsEnabled(void)
0x18003de65  mov     rcx, [rdi+70h]
0x18003de69  test    rcx, rcx
0x18003de6c  jz      loc_18003E266
0x18003de72  xor     ebx, ebx
0x18003de74  test    al, al
0x18003de76  jz      loc_18003E191
0x18003de7c  mov     r13, [rcx+40h]
0x18003de80  cmp     [rcx+58h], rbx
0x18003de84  jbe     short loc_18003DEAB
0x18003de86  lea     r8, [rcx+48h]
0x18003de8a  cmp     qword ptr [r8+18h], 7
0x18003de8f  jbe     short loc_18003DE94
0x18003de91  mov     r8, [r8]; lpName
0x18003de94  xor     edx, edx; bInheritHandle
0x18003de96  mov     ecx, 1F0003h; dwDesiredAccess
0x18003de9b  call    cs:__imp_OpenEventW
0x18003dea1  test    rax, rax
0x18003dea4  mov     rbx, rax
0x18003dea7  cmovnz  r13, rax
0x18003deab  mov     rax, [rdi+78h]
0x18003deaf  lea     edx, [r14+r15]
0x18003deb3  mov     [rbp+57h+Handles], rax
0x18003deb7  mov     [rbp+57h+var_7C], edx
0x18003deba  mov     [rbp+57h+var_48], r13
0x18003debe  cmp     r12d, r14d
0x18003dec1  jbe     short loc_18003DECD
0x18003dec3  mov     rax, [rdi+70h]
0x18003dec7  add     edx, [rax+20h]
0x18003deca  mov     [rbp+57h+var_7C], edx
0x18003decd  mov     rax, [rdi+70h]
0x18003ded1  xor     edx, edx
0x18003ded3  mov     rcx, [rax+30h]
0x18003ded7  xor     eax, eax
0x18003ded9  lock cmpxchg [rcx], edx
0x18003dedd  lea     rsi, [rdi+8]
0x18003dee1  mov     r15d, eax
0x18003dee4  mov     rcx, rsi; lpCriticalSection
0x18003dee7  call    cs:__imp_EnterCriticalSection
0x18003deed  cmp     byte ptr [rdi+30h], 0
0x18003def1  jz      loc_18003E02C
0x18003def7  cmp     r15d, [rdi+34h]
0x18003defb  jnz     loc_18003DFA8
0x18003df01  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x18003df06  mov     ecx, [rax]
0x18003df08  cmp     ecx, 4
0x18003df0b  jbe     short loc_18003DF7A
0x18003df0d  mov     ecx, [rdi+34h]
0x18003df10  lea     rdx, unk_180069088
0x18003df17  mov     [rbp+57h+var_80], ecx
0x18003df1a  lea     rcx, aMidixprocWaitS; "MidiXProc Wait skipped during continued"...
0x18003df21  mov     [rbp+57h+var_70], rcx
0x18003df25  lea     rcx, aCmidixprocWait; "CMidiXProc::WaitForSendComplete"
0x18003df2c  mov     [rbp+57h+var_60], rcx
0x18003df30  lea     rcx, [rbp+57h+var_7C]
0x18003df34  mov     [rsp+0D0h+var_88], rcx
0x18003df39  lea     rcx, [rbp+57h+var_80]
0x18003df3d  mov     [rsp+0D0h+var_90], rcx
0x18003df42  lea     rcx, [rbp+57h+var_78]
0x18003df46  mov     [rsp+0D0h+var_98], rcx
0x18003df4b  lea     rcx, [rbp+57h+var_70]
0x18003df4f  mov     [rsp+0D0h+var_A0], rcx
0x18003df54  lea     rcx, [rbp+57h+var_68]
0x18003df58  mov     [rsp+0D0h+var_A8], rcx
0x18003df5d  lea     rcx, [rbp+57h+var_60]
0x18003df61  mov     [rsp+0D0h+var_B0], rcx
0x18003df66  mov     rcx, rax
0x18003df69  mov     [rbp+57h+var_7C], r14d
0x18003df6d  mov     [rbp+57h+var_78], r15d
0x18003df71  mov     [rbp+57h+var_68], rdi
0x18003df75  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003df7a  test    rsi, rsi
0x18003df7d  jz      short loc_18003DF88
0x18003df7f  mov     rcx, rsi; lpCriticalSection
0x18003df82  call    cs:__imp_LeaveCriticalSection
0x18003df88  test    rbx, rbx
0x18003df8b  jz      short loc_18003DF9E
0x18003df8d  mov     rcx, rbx; hObject
0x18003df90  call    cs:__imp_CloseHandle
0x18003df96  test    eax, eax
0x18003df98  jz      loc_18003E2BB
0x18003df9e  mov     eax, 80004004h
0x18003dfa3  jmp     loc_18003E26B
0x18003dfa8  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x18003dfad  mov     ecx, [rax]
0x18003dfaf  cmp     ecx, 4
0x18003dfb2  jbe     short loc_18003E021
0x18003dfb4  mov     ecx, [rdi+34h]
0x18003dfb7  lea     rdx, dword_18006955C
0x18003dfbe  mov     [rbp+57h+var_80], ecx
0x18003dfc1  lea     rcx, aMidixprocDetec; "MidiXProc Detected stall resolved befor"...
0x18003dfc8  mov     [rbp+57h+var_60], rcx
0x18003dfcc  lea     rcx, aCmidixprocWait; "CMidiXProc::WaitForSendComplete"
0x18003dfd3  mov     [rbp+57h+var_58], rcx
0x18003dfd7  lea     rcx, [rbp+57h+var_78]
0x18003dfdb  mov     [rsp+0D0h+var_88], rcx
0x18003dfe0  lea     rcx, [rbp+57h+var_80]
0x18003dfe4  mov     [rsp+0D0h+var_90], rcx
0x18003dfe9  lea     rcx, [rbp+57h+var_70]
0x18003dfed  mov     [rsp+0D0h+var_98], rcx
0x18003dff2  lea     rcx, [rbp+57h+var_60]
0x18003dff6  mov     [rsp+0D0h+var_A0], rcx
0x18003dffb  lea     rcx, [rbp+57h+var_68]
0x18003dfff  mov     [rsp+0D0h+var_A8], rcx
0x18003e004  lea     rcx, [rbp+57h+var_58]
0x18003e008  mov     [rsp+0D0h+var_B0], rcx
0x18003e00d  mov     rcx, rax
0x18003e010  mov     [rbp+57h+var_78], r14d
0x18003e014  mov     dword ptr [rbp+57h+var_70], r15d
0x18003e018  mov     [rbp+57h+var_68], rdi
0x18003e01c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003e021  mov     byte ptr [rdi+30h], 0
0x18003e025  mov     dword ptr [rdi+34h], 0
0x18003e02c  mov     [rbp+57h+var_80], 0
0x18003e033  test    rsi, rsi
0x18003e036  jz      short loc_18003E094
0x18003e038  mov     rcx, rsi; lpCriticalSection
0x18003e03b  call    cs:__imp_LeaveCriticalSection
0x18003e041  jmp     short loc_18003E094
0x18003e043  mov     rcx, r13; hEvent
0x18003e046  call    cs:__imp_ResetEvent
0x18003e04c  mov     rax, [rdi+70h]
0x18003e050  xor     edx, edx
0x18003e052  mov     rcx, [rax+30h]
0x18003e056  xor     eax, eax
0x18003e058  lock cmpxchg [rcx], edx
0x18003e05c  mov     r9d, [rbp+57h+var_80]
0x18003e060  mov     rcx, [rdi+70h]
0x18003e064  mov     edx, [rcx+20h]
0x18003e067  mov     r8d, edx
0x18003e06a  imul    r8d, r9d
0x18003e06e  add     r8d, eax
0x18003e071  lea     eax, [r9+1]
0x18003e075  cmp     r8d, r12d
0x18003e078  cmovnb  eax, r9d
0x18003e07c  lea     r15d, [r8+rdx]
0x18003e080  mov     [rbp+57h+var_80], eax
0x18003e083  cmovnb  r15d, r8d
0x18003e087  cmp     r15d, [rbp+57h+var_7C]
0x18003e08b  jnb     loc_18003E172
0x18003e091  mov     r12d, r15d
0x18003e094  xor     r8d, r8d; bWaitAll
0x18003e097  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18003e09b  mov     r9d, 3E8h; dwMilliseconds
0x18003e0a1  lea     ecx, [r8+2]; nCount
0x18003e0a5  call    cs:__imp_WaitForMultipleObjects
0x18003e0ab  cmp     eax, 1
0x18003e0ae  jz      short loc_18003E043
0x18003e0b0  cmp     eax, 102h
0x18003e0b5  jnz     loc_18003E153
0x18003e0bb  mov     rcx, rsi; lpCriticalSection
0x18003e0be  call    cs:__imp_EnterCriticalSection
0x18003e0c4  mov     byte ptr [rdi+30h], 1
0x18003e0c8  mov     [rdi+34h], r15d
0x18003e0cc  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x18003e0d1  mov     ecx, [rax]
0x18003e0d3  cmp     ecx, 4
0x18003e0d6  jbe     short loc_18003E145
0x18003e0d8  mov     ecx, [rdi+34h]
0x18003e0db  lea     rdx, byte_180068EB7
0x18003e0e2  mov     [rbp+57h+var_78], ecx
0x18003e0e5  lea     rcx, aMidixprocStall_2; "MidiXProc stall detected during wait."
0x18003e0ec  mov     [rbp+57h+var_58], rcx
0x18003e0f0  lea     rcx, aCmidixprocWait; "CMidiXProc::WaitForSendComplete"
0x18003e0f7  mov     [rbp+57h+var_68], rcx
0x18003e0fb  lea     rcx, [rbp+57h+var_70]
0x18003e0ff  mov     [rsp+0D0h+var_88], rcx
0x18003e104  lea     rcx, [rbp+57h+var_78]
0x18003e108  mov     [rsp+0D0h+var_90], rcx
0x18003e10d  lea     rcx, [rbp+57h+var_7C]
0x18003e111  mov     [rsp+0D0h+var_98], rcx
0x18003e116  lea     rcx, [rbp+57h+var_58]
0x18003e11a  mov     [rsp+0D0h+var_A0], rcx
0x18003e11f  lea     rcx, [rbp+57h+var_60]
0x18003e123  mov     [rsp+0D0h+var_A8], rcx
0x18003e128  lea     rcx, [rbp+57h+var_68]
0x18003e12c  mov     [rsp+0D0h+var_B0], rcx
0x18003e131  mov     rcx, rax
0x18003e134  mov     dword ptr [rbp+57h+var_70], r14d
0x18003e138  mov     [rbp+57h+var_7C], r15d
0x18003e13c  mov     [rbp+57h+var_60], rdi
0x18003e140  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003e145  test    rsi, rsi
0x18003e148  jz      short loc_18003E153
0x18003e14a  mov     rcx, rsi; lpCriticalSection
0x18003e14d  call    cs:__imp_LeaveCriticalSection
0x18003e153  test    rbx, rbx
0x18003e156  jz      loc_18003DF9E
0x18003e15c  mov     rcx, rbx; hObject
0x18003e15f  call    cs:__imp_CloseHandle
0x18003e165  test    eax, eax
0x18003e167  jz      loc_18003E28E
0x18003e16d  jmp     loc_18003DF9E
0x18003e172  test    rbx, rbx
0x18003e175  jz      loc_18003E262
0x18003e17b  mov     rcx, rbx; hObject
0x18003e17e  call    cs:__imp_CloseHandle
0x18003e184  test    eax, eax
0x18003e186  jz      loc_18003E29D
0x18003e18c  jmp     loc_18003E262
0x18003e191  mov     rsi, [rcx+40h]
0x18003e195  cmp     [rcx+58h], rbx
0x18003e199  jbe     short loc_18003E1C0
0x18003e19b  lea     r8, [rcx+48h]
0x18003e19f  cmp     qword ptr [r8+18h], 7
0x18003e1a4  jbe     short loc_18003E1A9
0x18003e1a6  mov     r8, [r8]; lpName
0x18003e1a9  xor     edx, edx; bInheritHandle
0x18003e1ab  mov     ecx, 1F0003h; dwDesiredAccess
0x18003e1b0  call    cs:__imp_OpenEventW
0x18003e1b6  test    rax, rax
0x18003e1b9  mov     rbx, rax
0x18003e1bc  cmovnz  rsi, rax
0x18003e1c0  mov     rax, [rdi+78h]
0x18003e1c4  add     r15d, r14d
0x18003e1c7  mov     [rbp+57h+Handles], rax
0x18003e1cb  mov     [rbp+57h+var_48], rsi
0x18003e1cf  cmp     r12d, r14d
0x18003e1d2  jbe     short loc_18003E1DC
0x18003e1d4  mov     rax, [rdi+70h]
0x18003e1d8  add     r15d, [rax+20h]
0x18003e1dc  xor     r13d, r13d
0x18003e1df  lea     r14d, [r13+2]
0x18003e1e3  jmp     short loc_18003E21A
0x18003e1e5  mov     rcx, rsi; hEvent
0x18003e1e8  call    cs:__imp_ResetEvent
0x18003e1ee  mov     rax, [rdi+70h]
0x18003e1f2  xor     edx, edx
0x18003e1f4  mov     rcx, [rax+30h]
0x18003e1f8  xor     eax, eax
0x18003e1fa  lock cmpxchg [rcx], edx
0x18003e1fe  cmp     eax, r12d
0x18003e201  jnb     short loc_18003E206
0x18003e203  inc     r13d
0x18003e206  mov     rcx, [rdi+70h]
0x18003e20a  mov     r12d, r13d
0x18003e20d  imul    r12d, [rcx+20h]
0x18003e212  add     r12d, eax
0x18003e215  cmp     r12d, r15d
0x18003e218  ja      short loc_18003E250
0x18003e21a  mov     r9d, 1388h; dwMilliseconds
0x18003e220  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18003e224  xor     r8d, r8d; bWaitAll
0x18003e227  mov     ecx, r14d; nCount
0x18003e22a  call    cs:__imp_WaitForMultipleObjects
0x18003e230  cmp     eax, 1
0x18003e233  jz      short loc_18003E1E5
0x18003e235  test    rbx, rbx
0x18003e238  jz      loc_18003DF9E
0x18003e23e  mov     rcx, rbx; hObject
0x18003e241  call    cs:__imp_CloseHandle
0x18003e247  test    eax, eax
0x18003e249  jz      short loc_18003E2AC
0x18003e24b  jmp     loc_18003DF9E
0x18003e250  test    rbx, rbx
0x18003e253  jz      short loc_18003E262
0x18003e255  mov     rcx, rbx; hObject
0x18003e258  call    cs:__imp_CloseHandle
0x18003e25e  test    eax, eax
0x18003e260  jz      short loc_18003E27F
0x18003e262  xor     eax, eax
0x18003e264  jmp     short loc_18003E26B
0x18003e266  mov     eax, 1
0x18003e26b  add     rsp, 98h
0x18003e272  pop     r15
0x18003e274  pop     r14
0x18003e276  pop     r13
0x18003e278  pop     r12
0x18003e27a  pop     rdi
0x18003e27b  pop     rsi
0x18003e27c  pop     rbx
0x18003e27d  pop     rbp
0x18003e27e  retn
0x18003e27f  mov     rcx, [rbp+5Fh]; this
0x18003e283  mov     edx, 0A0Bh; void *
0x18003e288  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003e28e  mov     rcx, [rbp+5Fh]; this
0x18003e292  mov     edx, 0A0Bh; void *
0x18003e297  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003e29d  mov     rcx, [rbp+5Fh]; this
0x18003e2a1  mov     edx, 0A0Bh; void *
0x18003e2a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003e2ac  mov     rcx, [rbp+5Fh]; this
0x18003e2b0  mov     edx, 0A0Bh; void *
0x18003e2b5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
  ... truncated ...
```
