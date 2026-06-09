# CMidiSessionTracker::UpdateClientSessionName(_GUID,ushort const *,ulong)

- ea: `0x14003bfb0`
- end: `0x14003c249`
- name: `?UpdateClientSessionName@CMidiSessionTracker@@UEAAJU_GUID@@PEBGK@Z`
- size: `665`
- prototype: `__int64 __fastcall(CMidiSessionTracker *__hidden this, struct _GUID *__struct_ptr, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update`

## callees

- `0x14000204c`
- `0x140003400`
- `0x1400054c0`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x14001b33c`
- `0x14002308c`
- `0x14003a5e0`
- `0x14003bfb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003c0ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003c17a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003c0ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003c17a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003c08d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003c08d`

## string_xrefs

- `0x14003c159`: `avcore\midi2\service\exe\midisessiontracker.cpp`
- `0x14003c205`: `avcore\midi2\service\exe\midisessiontracker.cpp`
- `0x14003bfe8`: `CMidiSessionTracker::UpdateClientSessionName`

## pseudocode

```c
__int64 __fastcall CMidiSessionTracker::UpdateClientSessionName(
        CMidiSessionTracker *this,
        const wchar_t *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  _DWORD *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned __int64 v11; // r8
  _DWORD *v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  _DWORD *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // [rsp+20h] [rbp-89h]
  unsigned int v20; // [rsp+50h] [rbp-59h] BYREF
  const char *v21; // [rsp+58h] [rbp-51h] BYREF
  int v22[2]; // [rsp+60h] [rbp-49h] BYREF
  const wchar_t *v23; // [rsp+68h] [rbp-41h] BYREF
  _QWORD v24[2]; // [rsp+70h] [rbp-39h] BYREF
  int v25[4]; // [rsp+80h] [rbp-29h] BYREF
  __int128 Src; // [rsp+90h] [rbp-19h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-9h]
  __int64 v28; // [rsp+A8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v8 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v8 > 4u )
  {
    *(_QWORD *)v22 = a3;
    v20 = a4;
    v23 = a2;
    v24[0] = this;
    v21 = "CMidiSessionTracker::UpdateClientSessionName";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (__int64)v8,
      (__int64)qword_14008AE38,
      v9,
      v10,
      &v21,
      (__int64)v24,
      (__int64)&v23,
      (__int64)&v20,
      v22);
  }
  Src = 0;
  v27 = 0;
  v11 = -1;
  v28 = 0;
  do
    ++v11;
  while ( a3[v11] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&Src, a3, v11);
  WindowsMidiServicesInternal::InPlaceTrim(&Src);
  if ( v27 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    *(_OWORD *)v25 = *(_OWORD *)a2;
    CMidiSessionTracker::FindSession(this, &v21, v25, a4);
    if ( v21 == *((const char **)this + 4) )
    {
      v13 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v13 > 2u )
      {
        v21 = (const char *)a3;
        v23 = L"E_NOTFOUND. No matching session";
        v20 = a4;
        v24[0] = a2;
        *(_QWORD *)v22 = this;
        *(_QWORD *)v25 = "CMidiSessionTracker::UpdateClientSessionName";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          (__int64)v13,
          (__int64)byte_14008AB99,
          v14,
          v15,
          v25,
          (__int64)v22,
          &v23,
          (__int64)v24,
          (__int64)&v20,
          &v21);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11B,
        (unsigned int)"avcore\\midi2\\service\\exe\\midisessiontracker.cpp",
        (const char *)0x80070490LL,
        v19);
      if ( this != (CMidiSessionTracker *)-48LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
      std::wstring::~wstring((char **)&Src);
      return 2147943568LL;
    }
    else
    {
      std::wstring::operator=(v21 + 72, &Src);
      if ( this != (CMidiSessionTracker *)-48LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
      std::wstring::~wstring((char **)&Src);
      return 0;
    }
  }
  else
  {
    v16 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v16 > 2u )
    {
      *(_QWORD *)v25 = a3;
      v24[0] = L"E_INVALIDARG. Trimmed session name is empty";
      v20 = a4;
      v21 = (const char *)a2;
      v23 = (const wchar_t *)this;
      *(_QWORD *)v22 = "CMidiSessionTracker::UpdateClientSessionName";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        (__int64)v16,
        (__int64)&word_14008AA6E,
        v17,
        v18,
        v22,
        (__int64)&v23,
        v24,
        (__int64)&v21,
        (__int64)&v20,
        v25);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12C,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisessiontracker.cpp",
      (const char *)0x80070057LL,
      v19);
    std::wstring::~wstring((char **)&Src);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x14003bfb0  push    rbp
0x14003bfb2  push    rbx
0x14003bfb3  push    rsi
0x14003bfb4  push    rdi
0x14003bfb5  push    r12
0x14003bfb7  push    r13
0x14003bfb9  push    r14
0x14003bfbb  push    r15
0x14003bfbd  lea     rbp, [rsp-1Fh]
0x14003bfc2  sub     rsp, 0C8h
0x14003bfc9  mov     rax, cs:__security_cookie
0x14003bfd0  xor     rax, rsp
0x14003bfd3  mov     [rbp+57h+var_50], rax
0x14003bfd7  mov     r15d, r9d
0x14003bfda  mov     rsi, r8
0x14003bfdd  mov     r14, rdx
0x14003bfe0  mov     rdi, rcx
0x14003bfe3  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003bfe8  lea     r13, aCmidisessiontr_2; "CMidiSessionTracker::UpdateClientSessio"...
0x14003bfef  mov     rcx, [rax+8]
0x14003bff3  mov     eax, [rcx]
0x14003bff5  cmp     eax, 4
0x14003bff8  jbe     short loc_14003C047
0x14003bffa  lea     rax, [rbp+57h+var_A0]
0x14003bffe  mov     qword ptr [rbp+57h+var_A0], rsi
0x14003c002  mov     [rsp+100h+var_C0], rax
0x14003c007  lea     rdx, qword_14008AE38
0x14003c00e  lea     rax, [rbp+57h+var_B0]
0x14003c012  mov     [rbp+57h+var_B0], r15d
0x14003c016  mov     [rsp+100h+var_C8], rax
0x14003c01b  lea     rax, [rbp+57h+var_98]
0x14003c01f  mov     [rsp+100h+var_D0], rax
0x14003c024  lea     rax, [rbp+57h+var_90]
0x14003c028  mov     [rsp+100h+var_D8], rax
0x14003c02d  lea     rax, [rbp+57h+var_A8]
0x14003c031  mov     qword ptr [rsp+100h+var_E0], rax
0x14003c036  mov     [rbp+57h+var_98], r14
0x14003c03a  mov     [rbp+57h+var_90], rdi
0x14003c03e  mov     [rbp+57h+var_A8], r13
0x14003c042  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x14003c047  xor     r12d, r12d
0x14003c04a  xorps   xmm0, xmm0
0x14003c04d  movups  [rbp+57h+Src], xmm0
0x14003c051  mov     [rbp+57h+var_60], r12
0x14003c055  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003c059  mov     [rbp+57h+var_58], r12
0x14003c05d  inc     r8
0x14003c060  cmp     [rsi+r8*2], r12w
0x14003c065  jnz     short loc_14003C05D
0x14003c067  mov     rdx, rsi
0x14003c06a  lea     rcx, [rbp+57h+Src]
0x14003c06e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003c073  lea     rcx, [rbp+57h+Src]; Src
0x14003c077  call    ?InPlaceTrim@WindowsMidiServicesInternal@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WindowsMidiServicesInternal::InPlaceTrim(std::wstring &)
0x14003c07c  cmp     [rbp+57h+var_60], r12
0x14003c080  jz      loc_14003C190
0x14003c086  lea     rbx, [rdi+30h]
0x14003c08a  mov     rcx, rbx; lpCriticalSection
0x14003c08d  call    cs:__imp_EnterCriticalSection
0x14003c093  movups  xmm0, xmmword ptr [r14]
0x14003c097  mov     r9d, r15d
0x14003c09a  lea     r8, [rbp+57h+var_80]
0x14003c09e  lea     rdx, [rbp+57h+var_A8]
0x14003c0a2  mov     rcx, rdi
0x14003c0a5  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x14003c0aa  call    ?FindSession@CMidiSessionTracker@@AEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UMidiSessionEntry@@@std@@@std@@@std@@U_GUID@@K@Z; CMidiSessionTracker::FindSession(_GUID,ulong)
0x14003c0af  mov     rcx, [rbp+57h+var_A8]
0x14003c0b3  cmp     rcx, [rdi+20h]
0x14003c0b7  jz      short loc_14003C0E4
0x14003c0b9  add     rcx, 48h ; 'H'
0x14003c0bd  lea     rdx, [rbp+57h+Src]
0x14003c0c1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14003c0c6  test    rbx, rbx
0x14003c0c9  jz      short loc_14003C0D4
0x14003c0cb  mov     rcx, rbx; lpCriticalSection
0x14003c0ce  call    cs:__imp_LeaveCriticalSection
0x14003c0d4  lea     rcx, [rbp+57h+Src]; void *
0x14003c0d8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003c0dd  xor     eax, eax
0x14003c0df  jmp     loc_14003C229
0x14003c0e4  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003c0e9  mov     rcx, [rax+8]
0x14003c0ed  mov     eax, [rcx]
0x14003c0ef  cmp     eax, 2
0x14003c0f2  jbe     short loc_14003C155
0x14003c0f4  lea     rax, aENotfoundNoMat; "E_NOTFOUND. No matching session"
0x14003c0fb  mov     [rbp+57h+var_A8], rsi
0x14003c0ff  mov     [rbp+57h+var_98], rax
0x14003c103  lea     rdx, byte_14008AB99
0x14003c10a  lea     rax, [rbp+57h+var_A8]
0x14003c10e  mov     [rbp+57h+var_B0], r15d
0x14003c112  mov     [rsp+100h+var_B8], rax
0x14003c117  lea     rax, [rbp+57h+var_B0]
0x14003c11b  mov     [rsp+100h+var_C0], rax
0x14003c120  lea     rax, [rbp+57h+var_90]
0x14003c124  mov     [rsp+100h+var_C8], rax
0x14003c129  lea     rax, [rbp+57h+var_98]
0x14003c12d  mov     [rsp+100h+var_D0], rax
0x14003c132  lea     rax, [rbp+57h+var_A0]
0x14003c136  mov     [rsp+100h+var_D8], rax
0x14003c13b  lea     rax, [rbp+57h+var_80]
0x14003c13f  mov     qword ptr [rsp+100h+var_E0], rax; int
0x14003c144  mov     [rbp+57h+var_90], r14
0x14003c148  mov     qword ptr [rbp+57h+var_A0], rdi
0x14003c14c  mov     qword ptr [rbp+57h+var_80], r13
0x14003c150  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x14003c155  mov     rcx, [rbp+5Fh]; this
0x14003c159  lea     r8, aAvcoreMidi2Ser_5; "avcore\\midi2\\service\\exe\\midisessio"...
0x14003c160  mov     edi, 80070490h
0x14003c165  mov     edx, 11Bh; void *
0x14003c16a  mov     r9d, edi; char *
0x14003c16d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003c172  test    rbx, rbx
0x14003c175  jz      short loc_14003C180
0x14003c177  mov     rcx, rbx; lpCriticalSection
0x14003c17a  call    cs:__imp_LeaveCriticalSection
0x14003c180  lea     rcx, [rbp+57h+Src]; void *
0x14003c184  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003c189  mov     eax, edi
0x14003c18b  jmp     loc_14003C229
0x14003c190  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003c195  mov     rcx, [rax+8]
0x14003c199  mov     eax, [rcx]
0x14003c19b  cmp     eax, 2
0x14003c19e  jbe     short loc_14003C201
0x14003c1a0  lea     rax, aEInvalidargTri; "E_INVALIDARG. Trimmed session name is e"...
0x14003c1a7  mov     qword ptr [rbp+57h+var_80], rsi
0x14003c1ab  mov     [rbp+57h+var_90], rax
0x14003c1af  lea     rdx, word_14008AA6E
0x14003c1b6  lea     rax, [rbp+57h+var_80]
0x14003c1ba  mov     [rbp+57h+var_B0], r15d
0x14003c1be  mov     [rsp+100h+var_B8], rax
0x14003c1c3  lea     rax, [rbp+57h+var_B0]
0x14003c1c7  mov     [rsp+100h+var_C0], rax
0x14003c1cc  lea     rax, [rbp+57h+var_A8]
0x14003c1d0  mov     [rsp+100h+var_C8], rax
0x14003c1d5  lea     rax, [rbp+57h+var_90]
0x14003c1d9  mov     [rsp+100h+var_D0], rax
0x14003c1de  lea     rax, [rbp+57h+var_98]
0x14003c1e2  mov     [rsp+100h+var_D8], rax
0x14003c1e7  lea     rax, [rbp+57h+var_A0]
0x14003c1eb  mov     qword ptr [rsp+100h+var_E0], rax; int
0x14003c1f0  mov     [rbp+57h+var_A8], r14
0x14003c1f4  mov     [rbp+57h+var_98], rdi
0x14003c1f8  mov     qword ptr [rbp+57h+var_A0], r13
0x14003c1fc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x14003c201  mov     rcx, [rbp+5Fh]; this
0x14003c205  lea     r8, aAvcoreMidi2Ser_5; "avcore\\midi2\\service\\exe\\midisessio"...
0x14003c20c  mov     ebx, 80070057h
0x14003c211  mov     edx, 12Ch; void *
0x14003c216  mov     r9d, ebx; char *
0x14003c219  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003c21e  lea     rcx, [rbp+57h+Src]; void *
0x14003c222  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003c227  mov     eax, ebx
0x14003c229  mov     rcx, [rbp+57h+var_50]
0x14003c22d  xor     rcx, rsp; StackCookie
0x14003c230  call    __security_check_cookie
0x14003c235  add     rsp, 0C8h
0x14003c23c  pop     r15
0x14003c23e  pop     r14
0x14003c240  pop     r13
0x14003c242  pop     r12
0x14003c244  pop     rdi
0x14003c245  pop     rsi
0x14003c246  pop     rbx
0x14003c247  pop     rbp
0x14003c248  retn
```
