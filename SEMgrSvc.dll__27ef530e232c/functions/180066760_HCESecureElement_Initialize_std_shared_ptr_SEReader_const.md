# HCESecureElement::Initialize(std::shared_ptr<SEReader> const &)

- ea: `0x180066760`
- end: `0x180066b3f`
- name: `?Initialize@HCESecureElement@@UEAAJAEBV?$shared_ptr@VSEReader@@@std@@@Z`
- size: `991`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001194`
- `0x180004e9c`
- `0x180004ec0`
- `0x180010aa8`
- `0x180011a3c`
- `0x180066760`
- `0x180069004`
- `0x18006c28c`
- `0x18007ce94`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006697c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006697c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800668fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800668fe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180066926`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180066926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006693e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006693e`

## string_xrefs

- `0x1800667b0`: `Test hook for HCE background tasks found. Allowing connections without a corresponding background task.`
- `0x18006678e`: `HCERequireBackgroundTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall HCESecureElement::Initialize(__int64 a1, _QWORD *a2)
{
  bool v4; // r15
  unsigned int v5; // edi
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  char *v9; // rax
  char *v10; // rsi
  int v11; // eax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  __int64 v15; // r13
  HANDLE EventW; // rax
  signed int LastError; // eax
  char *v18; // rax
  _OWORD *v19; // rbx
  __int64 v20; // rsi
  __int64 v21; // r12
  int v22; // eax
  char *v23; // rbx
  char *v24; // rax
  volatile signed __int32 *v25; // rbx
  const char *v26; // [rsp+30h] [rbp-10h] BYREF
  char v27; // [rsp+38h] [rbp-8h]
  unsigned int v29; // [rsp+90h] [rbp+50h] BYREF
  const char *v30; // [rsp+98h] [rbp+58h] BYREF

  v4 = 1;
  v5 = 0;
  v29 = 0;
  if ( NfcRegUtils::GetDword((const struct NfcRegistryLocation *)&qword_1800A1E08, L"HCERequireBackgroundTask", &v29) >= 0 )
  {
    if ( (unsigned int)dword_18012F048 > 5 )
    {
      v30 = "Test hook for HCE background tasks found. Allowing connections without a corresponding background task.";
      v26 = "HCESecureElement::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v6,
        (unsigned int)word_18011CF9A,
        v7,
        v8,
        (__int64)&v26,
        (__int64)&v30);
    }
    v4 = v29 != 0;
  }
  v9 = (char *)operator new(0x98u, (const struct std::nothrow_t *)std::nothrow);
  v10 = v9;
  v30 = v9;
  if ( v9 )
  {
    *(_QWORD *)v9 = &HCEConnectionMgr::`vftable';
    *((_QWORD *)v9 + 1) = 0;
    *((_QWORD *)v9 + 2) = 0;
    v9[24] = !v4;
    *(_DWORD *)(v9 + 26) = 196633;
    *((_QWORD *)v9 + 4) = 0;
    *((_QWORD *)v9 + 5) = 0;
    *((_OWORD *)v9 + 3) = 0;
    *((_OWORD *)v9 + 4) = 0;
    *((_QWORD *)v9 + 10) = 0;
    v11 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 48));
    if ( v11 < 0 )
      ATL::AtlThrowImpl(v11);
    v10[88] = 0;
    *((_QWORD *)v10 + 14) = 0;
    *((_QWORD *)v10 + 15) = 0;
    v12 = operator new(0x108u);
    *v12 = v12;
    v12[1] = v12;
    *((_QWORD *)v10 + 14) = v12;
    v10[128] = 0;
    *((_QWORD *)v10 + 17) = 0;
    *((_QWORD *)v10 + 18) = 0;
    v13 = operator new(0x28u);
    *v13 = v13;
    v13[1] = v13;
    *((_QWORD *)v10 + 17) = v13;
  }
  else
  {
    v10 = 0;
  }
  *(_QWORD *)(a1 + 104) = v10;
  if ( v10 )
  {
    v15 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
    v26 = v10 + 48;
    EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
    v27 = 1;
    if ( v10[128] )
    {
      v5 = -2147019873;
    }
    else
    {
      EventW = CreateEventW(0, 1, 1, 0);
      tlx::shared_any<tlx::file_handle_traits>::assign(v10 + 32, EventW);
      if ( *((_QWORD *)v10 + 4) )
      {
        (*(void (__fastcall **)(char *, char *))(*(_QWORD *)v10 + 8LL))(v10, v10 + 16);
        *((_QWORD *)v10 + 1) = v15;
        v10[128] = 1;
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
    if ( (v5 & 0x80000000) != 0 )
      goto LABEL_11;
    v18 = (char *)operator new(0xD0u, (const struct std::nothrow_t *)std::nothrow);
    v19 = v18;
    v30 = v18;
    if ( v18 )
    {
      v20 = *(_QWORD *)(a1 + 104);
      v21 = *(_QWORD *)(*a2 + 128LL);
      *(_QWORD *)v18 = &HCEEventHandler::`vftable';
      *(_OWORD *)(v18 + 8) = 0;
      *(_OWORD *)(v18 + 24) = 0;
      *((_QWORD *)v18 + 5) = 0;
      v22 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v18 + 8));
      if ( v22 < 0 )
        ATL::AtlThrowImpl(v22);
      v19[3] = *(_OWORD *)(a1 + 12);
      *((_QWORD *)v19 + 8) = a1;
      *((_QWORD *)v19 + 9) = &SEEventMgr::s_Instance;
      *((_QWORD *)v19 + 10) = 0;
      *((_BYTE *)v19 + 88) = v4;
      *((_QWORD *)v19 + 12) = 0;
      *((_QWORD *)v19 + 13) = v21;
      *((_QWORD *)v19 + 14) = v20;
      *((_QWORD *)v19 + 15) = 0;
      *((_QWORD *)v19 + 16) = 0;
      *((_QWORD *)v19 + 17) = 0;
      *((_QWORD *)v19 + 18) = 0;
      *((_QWORD *)v19 + 19) = 0;
      *((_QWORD *)v19 + 20) = 0;
      *((_QWORD *)v19 + 22) = 0;
      *((_QWORD *)v19 + 23) = 0;
      *((_QWORD *)v19 + 24) = 0;
      *((_BYTE *)v19 + 200) = 0;
      HCEEventHandler::ClearPendingApdu((HCEEventHandler *)v19);
    }
    else
    {
      v19 = 0;
    }
    *(_QWORD *)(a1 + 40) = v19;
    if ( v19 )
    {
      v23 = (char *)operator new(8u, (const struct std::nothrow_t *)std::nothrow);
      if ( v23 )
        *(_QWORD *)v23 = &TrivialSECardManager::`vftable';
      else
        v23 = 0;
      v30 = v23;
      v24 = (char *)operator new(0x18u);
      v30 = v24;
      *(_OWORD *)v24 = 0;
      *((_DWORD *)v24 + 2) = 1;
      *((_DWORD *)v24 + 3) = 1;
      *(_QWORD *)v24 = &std::_Ref_count<DeviceCastle::Library::Internal::CryptogramMaterialPackageManager>::`vftable';
      *((_QWORD *)v24 + 2) = v23;
      *(_QWORD *)(a1 + 120) = v23;
      v25 = *(volatile signed __int32 **)(a1 + 128);
      *(_QWORD *)(a1 + 128) = v24;
      if ( v25 )
      {
        if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
          if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
        }
      }
      if ( *(_QWORD *)(a1 + 120) )
      {
        *(_BYTE *)(a1 + 112) = 1;
        return v5;
      }
    }
  }
  v5 = -2147024882;
LABEL_11:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return v5;
}

```

## disassembly

```asm
0x180066760  mov     [rsp-38h+arg_0], rbx
0x180066765  mov     [rsp-38h+arg_8], rdx
0x18006676a  push    rbp
0x18006676b  push    rsi
0x18006676c  push    rdi
0x18006676d  push    r12
0x18006676f  push    r13
0x180066771  push    r14
0x180066773  push    r15
0x180066775  mov     rbp, rsp
0x180066778  sub     rsp, 40h
0x18006677c  mov     rbx, rdx
0x18006677f  mov     r14, rcx
0x180066782  mov     r15b, 1
0x180066785  xor     edi, edi
0x180066787  mov     [rbp+arg_10], edi
0x18006678a  lea     r8, [rbp+arg_10]; unsigned int *
0x18006678e  lea     rdx, aHcerequireback; "HCERequireBackgroundTask"
0x180066795  lea     rcx, qword_1800A1E08; struct NfcRegistryLocation *
0x18006679c  call    ?GetDword@NfcRegUtils@@SAJAEBUNfcRegistryLocation@@PEBGPEAK@Z; NfcRegUtils::GetDword(NfcRegistryLocation const &,ushort const *,ulong *)
0x1800667a1  test    eax, eax
0x1800667a3  js      short loc_1800667EB
0x1800667a5  mov     eax, cs:dword_18012F048
0x1800667ab  cmp     eax, 5
0x1800667ae  jbe     short loc_1800667E4
0x1800667b0  lea     rax, aTestHookForHce; "Test hook for HCE background tasks foun"...
0x1800667b7  mov     [rbp+arg_18], rax
0x1800667bb  lea     rax, aHcesecureeleme_24; "HCESecureElement::Initialize"
0x1800667c2  mov     [rbp+var_10], rax
0x1800667c6  lea     rax, [rbp+arg_18]
0x1800667ca  mov     [rsp+40h+var_18], rax
0x1800667cf  lea     rax, [rbp+var_10]
0x1800667d3  mov     [rsp+40h+var_20], rax
0x1800667d8  lea     rdx, word_18011CF9A
0x1800667df  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800667e4  cmp     [rbp+arg_10], edi
0x1800667e7  setnz   r15b
0x1800667eb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800667f2  mov     ecx, 98h; unsigned __int64
0x1800667f7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800667fc  mov     rsi, rax
0x1800667ff  mov     [rbp+arg_18], rax
0x180066803  test    rax, rax
0x180066806  jz      loc_1800668A7
0x18006680c  lea     rax, ??_7HCEConnectionMgr@@6B@; const HCEConnectionMgr::`vftable'
0x180066813  mov     [rsi], rax
0x180066816  mov     [rsi+8], rdi
0x18006681a  mov     [rsi+10h], rdi
0x18006681e  mov     cl, r15b
0x180066821  xor     cl, 1
0x180066824  mov     [rsi+18h], cl
0x180066827  mov     dword ptr [rsi+1Ah], 30019h
0x18006682e  mov     [rsi+20h], rdi
0x180066832  mov     [rsi+28h], rdi
0x180066836  lea     rcx, [rsi+30h]; this
0x18006683a  xorps   xmm0, xmm0
0x18006683d  xor     eax, eax
0x18006683f  movups  xmmword ptr [rcx], xmm0
0x180066842  movups  xmmword ptr [rcx+10h], xmm0
0x180066846  mov     [rcx+20h], rax
0x18006684a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18006684f  test    eax, eax
0x180066851  js      loc_180066B37
0x180066857  mov     [rsi+58h], dil
0x18006685b  mov     [rsi+70h], rdi
0x18006685f  mov     [rsi+78h], rdi
0x180066863  mov     ecx, 108h; Size
0x180066868  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006686d  mov     [rax], rax
0x180066870  mov     [rax+8], rax
0x180066874  mov     [rsi+70h], rax
0x180066878  mov     [rsi+80h], dil
0x18006687f  mov     [rsi+88h], rdi
0x180066886  mov     [rsi+90h], rdi
0x18006688d  mov     ecx, 28h ; '('; Size
0x180066892  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180066897  mov     [rax], rax
0x18006689a  mov     [rax+8], rax
0x18006689e  mov     [rsi+88h], rax
0x1800668a5  jmp     short loc_1800668AA
0x1800668a7  mov     rsi, rdi
0x1800668aa  mov     [r14+68h], rsi
0x1800668ae  test    rsi, rsi
0x1800668b1  jnz     short loc_1800668E1
0x1800668b3  mov     edi, 8007000Eh
0x1800668b8  mov     rcx, [r14]
0x1800668bb  mov     rax, [rcx+10h]
0x1800668bf  mov     rcx, r14
0x1800668c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800668c7  mov     eax, edi
0x1800668c9  mov     rbx, [rsp+40h+arg_0]
0x1800668d1  add     rsp, 40h
0x1800668d5  pop     r15
0x1800668d7  pop     r14
0x1800668d9  pop     r13
0x1800668db  pop     r12
0x1800668dd  pop     rdi
0x1800668de  pop     rsi
0x1800668df  pop     rbp
0x1800668e0  retn
0x1800668e1  mov     rcx, [rbx]
0x1800668e4  mov     rax, [rcx]
0x1800668e7  mov     rax, [rax+10h]
0x1800668eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800668f0  mov     r13, rax
0x1800668f3  lea     r12, [rsi+30h]
0x1800668f7  mov     [rbp+var_10], r12
0x1800668fb  mov     rcx, r12; lpCriticalSection
0x1800668fe  call    cs:__imp_EnterCriticalSection
0x180066904  mov     eax, 1
0x180066909  mov     [rbp+var_8], al
0x18006690c  cmp     [rsi+80h], dil
0x180066913  jz      short loc_18006691C
0x180066915  mov     edi, 8007139Fh
0x18006691a  jmp     short loc_180066976
0x18006691c  xor     r9d, r9d; lpName
0x18006691f  mov     r8d, eax; bInitialState
0x180066922  mov     edx, eax; bManualReset
0x180066924  xor     ecx, ecx; lpEventAttributes
0x180066926  call    cs:__imp_CreateEventW
0x18006692c  mov     rdx, rax
0x18006692f  lea     rcx, [rsi+20h]
0x180066933  call    ?assign@?$shared_any@Ufile_handle_traits@tlx@@@tlx@@QEAA_NPEAX@Z; tlx::shared_any<tlx::file_handle_traits>::assign(void *)
0x180066938  cmp     [rsi+20h], rdi
0x18006693c  jnz     short loc_180066958
0x18006693e  call    cs:__imp_GetLastError
0x180066944  mov     edi, eax
0x180066946  xor     r13d, r13d
0x180066949  test    eax, eax
0x18006694b  jle     short loc_180066979
0x18006694d  movzx   edi, ax
0x180066950  or      edi, 80070000h
0x180066956  jmp     short loc_180066979
0x180066958  mov     rax, [rsi]
0x18006695b  lea     rdx, [rsi+10h]
0x18006695f  mov     rcx, rsi
0x180066962  mov     rax, [rax+8]
0x180066966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006696b  mov     [rsi+8], r13
0x18006696f  mov     byte ptr [rsi+80h], 1
0x180066976  xor     r13d, r13d
0x180066979  mov     rcx, r12; lpCriticalSection
0x18006697c  call    cs:__imp_LeaveCriticalSection
0x180066982  test    edi, edi
0x180066984  js      loc_1800668B8
0x18006698a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180066991  mov     ecx, 0D0h; unsigned __int64
0x180066996  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006699b  mov     rbx, rax
0x18006699e  mov     [rbp+arg_18], rax
0x1800669a2  test    rax, rax
0x1800669a5  jz      loc_180066A62
0x1800669ab  mov     rsi, [r14+68h]
0x1800669af  mov     rcx, [rbp+arg_8]
0x1800669b3  mov     rcx, [rcx]
0x1800669b6  mov     r12, [rcx+80h]
0x1800669bd  lea     rax, ??_7HCEEventHandler@@6B@; const HCEEventHandler::`vftable'
0x1800669c4  mov     [rbx], rax
0x1800669c7  lea     rcx, [rbx+8]; this
0x1800669cb  xorps   xmm0, xmm0
0x1800669ce  xor     eax, eax
0x1800669d0  movups  xmmword ptr [rcx], xmm0
0x1800669d3  movups  xmmword ptr [rcx+10h], xmm0
0x1800669d7  mov     [rcx+20h], rax
0x1800669db  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800669e0  test    eax, eax
0x1800669e2  js      loc_180066B2F
0x1800669e8  movups  xmm0, xmmword ptr [r14+0Ch]
0x1800669ed  movdqu  xmmword ptr [rbx+30h], xmm0
0x1800669f2  mov     [rbx+40h], r14
0x1800669f6  lea     rax, ?s_Instance@SEEventMgr@@0V1@A; SEEventMgr SEEventMgr::s_Instance
0x1800669fd  mov     [rbx+48h], rax
0x180066a01  mov     [rbx+50h], r13
0x180066a05  mov     [rbx+58h], r15b
0x180066a09  mov     [rbx+60h], r13
0x180066a0d  mov     [rbx+68h], r12
0x180066a11  mov     [rbx+70h], rsi
0x180066a15  mov     [rbx+78h], r13
0x180066a19  mov     [rbx+80h], r13
0x180066a20  mov     [rbx+88h], r13
0x180066a27  mov     [rbx+90h], r13
0x180066a2e  mov     [rbx+98h], r13
0x180066a35  mov     [rbx+0A0h], r13
0x180066a3c  mov     [rbx+0B0h], r13
0x180066a43  mov     [rbx+0B8h], r13
0x180066a4a  mov     [rbx+0C0h], r13
0x180066a51  mov     [rbx+0C8h], r13b
0x180066a58  mov     rcx, rbx; this
0x180066a5b  call    ?ClearPendingApdu@HCEEventHandler@@AEAAXXZ; HCEEventHandler::ClearPendingApdu(void)
0x180066a60  jmp     short loc_180066A65
0x180066a62  mov     rbx, r13
0x180066a65  mov     [r14+28h], rbx
0x180066a69  test    rbx, rbx
0x180066a6c  jz      loc_1800668B3
0x180066a72  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180066a79  mov     ecx, 8; unsigned __int64
0x180066a7e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180066a83  mov     rbx, rax
0x180066a86  test    rax, rax
0x180066a89  jz      short loc_180066A97
0x180066a8b  lea     rax, ??_7TrivialSECardManager@@6B@; const TrivialSECardManager::`vftable'
0x180066a92  mov     [rbx], rax
0x180066a95  jmp     short loc_180066A9A
0x180066a97  mov     rbx, r13
0x180066a9a  mov     [rbp+arg_18], rbx
0x180066a9e  mov     ecx, 18h; Size
0x180066aa3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180066aa8  mov     [rbp+arg_18], rax
0x180066aac  xorps   xmm0, xmm0
0x180066aaf  movups  xmmword ptr [rax], xmm0
0x180066ab2  mov     dword ptr [rax+8], 1
0x180066ab9  mov     dword ptr [rax+0Ch], 1
0x180066ac0  lea     rcx, ??_7?$_Ref_count@VCryptogramMaterialPackageManager@Internal@Library@DeviceCastle@@@std@@6B@; const std::_Ref_count<DeviceCastle::Library::Internal::CryptogramMaterialPackageManager>::`vftable'
0x180066ac7  mov     [rax], rcx
0x180066aca  mov     [rax+10h], rbx
0x180066ace  mov     [r14+78h], rbx
0x180066ad2  mov     rbx, [r14+80h]
0x180066ad9  mov     [r14+80h], rax
0x180066ae0  test    rbx, rbx
0x180066ae3  jz      short loc_180066B1B
0x180066ae5  or      esi, 0FFFFFFFFh
0x180066ae8  mov     eax, esi
0x180066aea  lock xadd [rbx+8], eax
0x180066aef  add     eax, esi
0x180066af1  jnz     short loc_180066B1B
0x180066af3  mov     rax, [rbx]
0x180066af6  mov     rcx, rbx
0x180066af9  mov     rax, [rax]
0x180066afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b01  mov     eax, esi
0x180066b03  lock xadd [rbx+0Ch], eax
0x180066b08  add     eax, esi
0x180066b0a  jnz     short loc_180066B1B
0x180066b0c  mov     rax, [rbx]
0x180066b0f  mov     rcx, rbx
0x180066b12  mov     rax, [rax+8]
0x180066b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b1b  cmp     [r14+78h], r13
0x180066b1f  jz      loc_1800668B3
0x180066b25  mov     byte ptr [r14+70h], 1
0x180066b2a  jmp     loc_1800668C7
0x180066b2f  mov     ecx, eax; int
0x180066b31  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180066b37  mov     ecx, eax; int
0x180066b39  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
