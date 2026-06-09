# CMidiClientManager::GetMidiDevice(ushort const *,MIDISRV_CLIENTCREATION_PARAMS *,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy> &)

- ea: `0x1400193c4`
- end: `0x140019aa5`
- name: `?GetMidiDevice@CMidiClientManager@@AEAAJPEBGPEAUMIDISRV_CLIENTCREATION_PARAMS@@AEAV?$com_ptr_t@VCMidiPipe@@Uerr_returncode_policy@wil@@@wil@@@Z`
- size: `1761`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400152d0`

## callees

- `0x14000179c`
- `0x140001ce8`
- `0x1400054c0`
- `0x1400058ac`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000c598`
- `0x140012de0`
- `0x140013a38`
- `0x140013b08`
- `0x140017404`
- `0x1400193c4`
- `0x14001bc60`
- `0x14001dccc`
- `0x14001f95c`
- `0x14003fd34`
- `0x14005a010`

## string_xrefs

- `0x1400196b1`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x1400197eb`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x14001983f`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x1400198f6`: `avcore\midi2\service\exe\midiclientmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CMidiClientManager::GetMidiDevice(const char *a1, CMidiDevicePipe *a2, wchar_t **a3, wchar_t ***a4)
{
  wchar_t ***v4; // r15
  _DWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned __int64 v10; // r13
  unsigned __int64 v11; // r8
  __int64 v12; // rax
  const char *v13; // rax
  _QWORD *v14; // rbx
  __int64 *v15; // rdi
  _QWORD *v16; // r12
  const wchar_t *v17; // rsi
  size_t v18; // r15
  const wchar_t *v19; // rdx
  size_t v20; // r14
  const wchar_t *v21; // rcx
  size_t v22; // r8
  int v23; // eax
  size_t v24; // rbx
  size_t v25; // r14
  const wchar_t *v26; // rcx
  size_t v27; // r8
  int v28; // eax
  __int64 v29; // rdi
  size_t v30; // rsi
  const wchar_t *v31; // rdx
  size_t v32; // r14
  const wchar_t *v33; // rcx
  size_t v34; // r8
  int v35; // eax
  wchar_t **v36; // rsi
  _DWORD *v37; // rdi
  CMidiPipe *v38; // rcx
  wchar_t **v39; // rcx
  __int64 **v40; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  unsigned int v43; // edi
  _DWORD *v44; // r10
  const wchar_t *v45; // rax
  __int64 v46; // rcx
  unsigned int v47; // ecx
  wchar_t **v48; // rdx
  int DeviceSupportedDataFormat; // eax
  CMidiDevicePipe *v50; // rax
  CMidiDevicePipe *v51; // rbx
  const unsigned __int16 *v52; // rdx
  const char *v53; // rsi
  int v54; // eax
  wchar_t **v55; // rdi
  wchar_t **v56; // rax
  _DWORD *v57; // rcx
  _DWORD *v58; // rcx
  __int64 v59; // r8
  __int64 v60; // r9
  wchar_t **v61; // rax
  int v63; // [rsp+20h] [rbp-E0h]
  wchar_t **v64; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v65; // [rsp+48h] [rbp-B8h] BYREF
  const char *v66; // [rsp+50h] [rbp-B0h] BYREF
  CMidiDevicePipe *v67; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v68; // [rsp+60h] [rbp-A0h] BYREF
  const char *v69; // [rsp+68h] [rbp-98h] BYREF
  const char *v70; // [rsp+70h] [rbp-90h]
  char v71[32]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *S2[2]; // [rsp+98h] [rbp-68h] BYREF
  size_t N; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v74; // [rsp+B0h] [rbp-50h]
  __int64 v75; // [rsp+B8h] [rbp-48h] BYREF
  int v76; // [rsp+C0h] [rbp-40h]
  __int128 v77; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v78; // [rsp+D8h] [rbp-28h]
  struct _EVENT_DATA_DESCRIPTOR v79[2]; // [rsp+F0h] [rbp-10h] BYREF
  const char *v80; // [rsp+110h] [rbp+10h]
  __int64 v81; // [rsp+118h] [rbp+18h]
  const wchar_t *v82; // [rsp+120h] [rbp+20h]
  __int64 v83; // [rsp+128h] [rbp+28h]
  const wchar_t *v84; // [rsp+130h] [rbp+30h]
  __int64 v85; // [rsp+138h] [rbp+38h]
  const wchar_t **v86; // [rsp+140h] [rbp+40h]
  __int64 v87; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v4 = a4;
  v68 = (const wchar_t *)a4;
  v64 = a3;
  v70 = a1;
  v7 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v7 > 4u )
  {
    v67 = a2;
    v65 = L"Enter";
    v69 = a1;
    v66 = "CMidiClientManager::GetMidiDevice";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v7,
      (__int64)byte_1400875CD,
      v8,
      v9,
      &v66,
      (__int64)&v69,
      &v65,
      &v67);
  }
  v77 = 0;
  v78 = 0;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)a2 + v11) );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v77, a2, v11);
  v12 = std::wstring::wstring((__int64)v71, (__int64)&v77);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(S2, v12);
  std::wstring::~wstring((char **)&v77);
  v13 = a1 + 88;
  v66 = a1 + 88;
  v14 = (_QWORD *)*((_QWORD *)a1 + 11);
  v15 = (__int64 *)v14[1];
  v16 = v14;
  if ( !*((_BYTE *)v15 + 25) )
  {
    while ( 1 )
    {
      v17 = (const wchar_t *)(v15 + 4);
      v18 = N;
      v19 = (const wchar_t *)S2;
      if ( v74 > 7 )
        v19 = S2[0];
      v20 = v15[6];
      if ( (unsigned __int64)v15[7] <= 7 )
        v21 = (const wchar_t *)(v15 + 4);
      else
        v21 = *(const wchar_t **)v17;
      v22 = v15[6];
      if ( N < v20 )
        v22 = N;
      v23 = wmemcmp(v21, v19, v22);
      if ( v23 )
      {
        if ( v23 >= 0 )
          goto LABEL_18;
      }
      else if ( v20 >= v18 )
      {
LABEL_18:
        if ( *((_BYTE *)v16 + 25) )
        {
          v24 = v15[6];
          if ( (unsigned __int64)v15[7] > 7 )
            v17 = *(const wchar_t **)v17;
          v25 = N;
          v26 = (const wchar_t *)S2;
          if ( v74 > 7 )
            v26 = S2[0];
          v27 = N;
          if ( v24 < N )
            v27 = v15[6];
          v28 = wmemcmp(v26, v17, v27);
          if ( v28 )
          {
            if ( v28 < 0 )
LABEL_29:
              v16 = v15;
          }
          else if ( v25 < v24 )
          {
            goto LABEL_29;
          }
        }
        v14 = v15;
        goto LABEL_31;
      }
      v15 += 2;
LABEL_31:
      v15 = (__int64 *)*v15;
      if ( *((_BYTE *)v15 + 25) )
      {
        v4 = (wchar_t ***)v68;
        v13 = v66;
        break;
      }
    }
  }
  if ( *((_BYTE *)v16 + 25) )
    v29 = *(_QWORD *)v13 + 8LL;
  else
    v29 = (__int64)v16;
  while ( 1 )
  {
    v29 = *(_QWORD *)v29;
    if ( *(_BYTE *)(v29 + 25) )
      break;
    v30 = *(_QWORD *)(v29 + 48);
    v31 = (const wchar_t *)(v29 + 32);
    if ( *(_QWORD *)(v29 + 56) > 7u )
      v31 = *(const wchar_t **)v31;
    v32 = N;
    v33 = (const wchar_t *)S2;
    if ( v74 > 7 )
      v33 = S2[0];
    v34 = N;
    if ( v30 < N )
      v34 = *(_QWORD *)(v29 + 48);
    v35 = wmemcmp(v33, v31, v34);
    if ( v35 )
    {
      if ( v35 >= 0 )
        goto LABEL_47;
LABEL_46:
      v16 = (_QWORD *)v29;
    }
    else
    {
      if ( v32 < v30 )
        goto LABEL_46;
LABEL_47:
      v29 += 16;
    }
  }
  v36 = v64;
  v37 = v64 + 1;
  while ( v14 != v16 )
  {
    v38 = (CMidiPipe *)v14[8];
    v37 = v36 + 1;
    if ( *((_DWORD *)v36 + 2) == *((_DWORD *)v38 + 14) && !CMidiPipe::IsInvalidated(v38) )
    {
      if ( *v4 )
      {
        v43 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1CE,
          (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
          (const char *)0x8000FFFFLL,
          v63);
        goto LABEL_103;
      }
      v39 = (wchar_t **)v14[8];
      *v4 = v39;
      if ( v39 )
        (*((void (__fastcall **)(wchar_t **))*v39 + 1))(v39);
    }
    v40 = (__int64 **)v14[2];
    if ( *((_BYTE *)v40 + 25) )
    {
      for ( i = v14[1]; !*(_BYTE *)(i + 25) && v14 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
        v14 = (_QWORD *)i;
      v14 = (_QWORD *)i;
    }
    else
    {
      v14 = (_QWORD *)v14[2];
      for ( j = *v40; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v14 = j;
    }
  }
  if ( *v4 )
  {
    v53 = v70;
  }
  else
  {
    v44 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v44 > 5u )
    {
      LODWORD(v65) = *v37;
      v45 = (const wchar_t *)S2;
      if ( v74 > 7 )
        v45 = S2[0];
      v86 = &v65;
      v87 = 4;
      if ( v45 )
      {
        v46 = -1;
        do
          ++v46;
        while ( v45[v46] );
        v47 = 2 * v46 + 2;
      }
      else
      {
        v45 = &::S2;
        v47 = 2;
      }
      v84 = v45;
      v85 = v47;
      v82 = L"No valid pipe found, creating new one";
      v83 = 76;
      v80 = "CMidiClientManager::GetMidiDevice";
      v81 = 34;
      tlgWriteTransfer_EventWriteTransfer((__int64)v44, (unsigned __int8 *)byte_140087D3F, 0, 0, 6u, v79);
    }
    v67 = 0;
    v75 = 0;
    v76 = *((_DWORD *)v36 + 3);
    LODWORD(v65) = -1;
    v48 = S2;
    if ( v74 > 7 )
      v48 = (wchar_t **)S2[0];
    v77 = 0;
    v78 = 0u;
    do
      ++v10;
    while ( *((_WORD *)v48 + v10) );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v77, v48, v10);
    DeviceSupportedDataFormat = GetDeviceSupportedDataFormat(&v77);
    if ( DeviceSupportedDataFormat < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1E9,
        (int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
        (const char *)(unsigned int)DeviceSupportedDataFormat);
    LODWORD(v75) = (_DWORD)v65;
    HIDWORD(v75) = *v37;
    v67 = 0;
    v50 = (CMidiDevicePipe *)operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
    v51 = v50;
    v64 = (wchar_t **)v50;
    v68 = (const wchar_t *)v50;
    if ( !v50 )
    {
      v43 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1EE,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
        (const char *)0x8007000ELL,
        v63);
      goto LABEL_103;
    }
    v66 = (const char *)v50;
    CMidiPipe::CMidiPipe(v50);
    *(_QWORD *)v51 = &CMidiDevicePipe::`vftable';
    *((_QWORD *)v51 + 15) = 0;
    *((_OWORD *)v51 + 8) = 0;
    *((_QWORD *)v51 + 18) = 0;
    *((_QWORD *)v51 + 19) = 0;
    *((_QWORD *)v51 + 20) = 0;
    *((_BYTE *)v51 + 168) = 1;
    v64 = 0;
    (*(void (__fastcall **)(CMidiDevicePipe *))(*(_QWORD *)v51 + 8LL))(v51);
    v67 = v51;
    (*(void (__fastcall **)(CMidiDevicePipe *))(*(_QWORD *)v51 + 16LL))(v51);
    v52 = (const unsigned __int16 *)S2;
    if ( v74 > 7 )
      v52 = S2[0];
    v53 = v70;
    v54 = CMidiDevicePipe::Initialize(v51, v52, (struct MIDISRV_DEVICECREATION_PARAMS *)&v75, (unsigned int *)v70 + 30);
    v43 = v54;
    if ( v54 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1EF,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
        (const char *)(unsigned int)v54,
        v63);
      (*(void (__fastcall **)(CMidiDevicePipe *))(*(_QWORD *)v51 + 16LL))(v51);
      goto LABEL_103;
    }
    v55 = *v4;
    *v4 = (wchar_t **)v51;
    (*(void (__fastcall **)(CMidiDevicePipe *))(*(_QWORD *)v51 + 8LL))(v51);
    if ( v55 )
      (*((void (__fastcall **)(wchar_t **))*v55 + 2))(v55);
    v56 = S2;
    if ( v74 > 7 )
      v56 = (wchar_t **)S2[0];
    v64 = v56;
    std::multimap<std::wstring,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy>>::emplace<unsigned short const *,wil::com_ptr_t<CMidiDevicePipe,wil::err_returncode_policy>>(
      (__int64 *)v53 + 11,
      &v68,
      (const void **)&v64,
      (__int64 *)&v67);
    v57 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v57 > 5u )
    {
      v64 = *v4;
      v84 = (const wchar_t *)&v64;
      v85 = 8;
      v82 = L"Inserted new device pipe into m_DevicePipes";
      v83 = 88;
      v80 = "CMidiClientManager::GetMidiDevice";
      v81 = 34;
      tlgWriteTransfer_EventWriteTransfer((__int64)v57, (unsigned __int8 *)byte_140087B95, 0, 0, 5u, v79);
    }
    if ( v67 )
      (*(void (__fastcall **)(CMidiDevicePipe *))(*(_QWORD *)v67 + 16LL))(v67);
  }
  v58 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v58 > 4u )
  {
    v61 = S2;
    if ( v74 > 7 )
      v61 = (wchar_t **)S2[0];
    v64 = v61;
    v68 = L"Exit success";
    v66 = v53;
    v69 = "CMidiClientManager::GetMidiDevice";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v58,
      (__int64)&byte_140087577,
      v59,
      v60,
      &v69,
      (__int64)&v66,
      &v68,
      &v64);
  }
  v43 = 0;
LABEL_103:
  std::wstring::~wstring((char **)S2);
  return v43;
}

```

## disassembly

```asm
0x1400193c4  push    rbp
0x1400193c6  push    rbx
0x1400193c7  push    rsi
0x1400193c8  push    rdi
0x1400193c9  push    r12
0x1400193cb  push    r13
0x1400193cd  push    r14
0x1400193cf  push    r15
0x1400193d1  lea     rbp, [rsp-68h]
0x1400193d6  sub     rsp, 168h
0x1400193dd  mov     rax, cs:__security_cookie
0x1400193e4  xor     rax, rsp
0x1400193e7  mov     [rbp+0A0h+var_50], rax
0x1400193eb  mov     r15, r9
0x1400193ee  mov     [rsp+1A0h+var_140], r9
0x1400193f3  mov     [rsp+1A0h+var_160], r8
0x1400193f8  mov     rbx, rdx
0x1400193fb  mov     rdi, rcx
0x1400193fe  mov     [rsp+1A0h+var_130], rcx
0x140019403  xor     r14d, r14d
0x140019406  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001940b  mov     rcx, [rax+8]
0x14001940f  mov     eax, [rcx]
0x140019411  lea     rdx, aCmidiclientman_7; "CMidiClientManager::GetMidiDevice"
0x140019418  cmp     eax, 4
0x14001941b  jbe     short loc_14001946C
0x14001941d  mov     [rsp+1A0h+var_148], rbx
0x140019422  lea     rax, aEnter; "Enter"
0x140019429  mov     [rsp+1A0h+var_158], rax
0x14001942e  mov     [rsp+1A0h+var_138], rdi
0x140019433  mov     [rsp+1A0h+var_150], rdx
0x140019438  lea     rax, [rsp+1A0h+var_148]
0x14001943d  mov     [rsp+1A0h+var_168], rax
0x140019442  lea     rax, [rsp+1A0h+var_158]
0x140019447  mov     [rsp+1A0h+var_170], rax
0x14001944c  lea     rax, [rsp+1A0h+var_138]
0x140019451  mov     [rsp+1A0h+var_178], rax
0x140019456  lea     rax, [rsp+1A0h+var_150]
0x14001945b  mov     qword ptr [rsp+1A0h+var_180], rax
0x140019460  lea     rdx, byte_1400875CD
0x140019467  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14001946c  xorps   xmm0, xmm0
0x14001946f  movups  [rbp+0A0h+var_D8], xmm0
0x140019473  xorps   xmm1, xmm1
0x140019476  movdqu  [rbp+0A0h+var_C8], xmm1
0x14001947b  or      r13, 0FFFFFFFFFFFFFFFFh
0x14001947f  mov     r8, r13
0x140019482  inc     r8
0x140019485  cmp     [rbx+r8*2], r14w
0x14001948a  jnz     short loc_140019482
0x14001948c  mov     rdx, rbx
0x14001948f  lea     rcx, [rbp+0A0h+var_D8]
0x140019493  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140019498  nop
0x140019499  lea     rdx, [rbp+0A0h+var_D8]
0x14001949d  lea     rcx, [rsp+1A0h+var_128]
0x1400194a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400194a7  mov     rdx, rax
0x1400194aa  lea     rcx, [rbp+0A0h+S2]
0x1400194ae  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x1400194b3  nop
0x1400194b4  lea     rcx, [rbp+0A0h+var_D8]; void *
0x1400194b8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400194bd  lea     rax, [rdi+58h]
0x1400194c1  mov     [rsp+1A0h+var_150], rax
0x1400194c6  mov     rbx, [rax]
0x1400194c9  mov     rdi, [rbx+8]
0x1400194cd  mov     r12, rbx
0x1400194d0  cmp     [rdi+19h], r14b
0x1400194d4  jnz     loc_1400195A0
0x1400194da  lea     rsi, [rdi+20h]
0x1400194de  mov     r15, [rbp+0A0h+N]
0x1400194e2  lea     rdx, [rbp+0A0h+S2]
0x1400194e6  cmp     [rbp+0A0h+var_F0], 7
0x1400194eb  cmova   rdx, [rbp+0A0h+S2]; S2
0x1400194f0  mov     r14, [rdi+30h]
0x1400194f4  cmp     qword ptr [rsi+18h], 7
0x1400194f9  jbe     short loc_140019500
0x1400194fb  mov     rcx, [rsi]
0x1400194fe  jmp     short loc_140019503
0x140019500  mov     rcx, rsi; S1
0x140019503  mov     r8, r14
0x140019506  cmp     r15, r14
0x140019509  cmovb   r8, r15; N
0x14001950d  call    wmemcmp
0x140019512  test    eax, eax
0x140019514  jz      short loc_14001951F
0x140019516  xor     r14d, r14d
0x140019519  test    eax, eax
0x14001951b  jns     short loc_140019530
0x14001951d  jmp     short loc_140019527
0x14001951f  cmp     r14, r15
0x140019522  jnb     short loc_14001952D
0x140019524  xor     r14d, r14d
0x140019527  add     rdi, 10h
0x14001952b  jmp     short loc_140019589
0x14001952d  xor     r14d, r14d
0x140019530  cmp     [r12+19h], r14b
0x140019535  jz      short loc_140019586
0x140019537  mov     rbx, [rsi+10h]
0x14001953b  cmp     qword ptr [rsi+18h], 7
0x140019540  jbe     short loc_140019545
0x140019542  mov     rsi, [rsi]
0x140019545  mov     r14, [rbp+0A0h+N]
0x140019549  lea     rcx, [rbp+0A0h+S2]
0x14001954d  cmp     [rbp+0A0h+var_F0], 7
0x140019552  cmova   rcx, [rbp+0A0h+S2]; S1
0x140019557  mov     r8, r14
0x14001955a  cmp     rbx, r14
0x14001955d  cmovb   r8, rbx; N
0x140019561  mov     rdx, rsi; S2
0x140019564  call    wmemcmp
0x140019569  test    eax, eax
0x14001956b  jz      short loc_140019576
0x14001956d  xor     r14d, r14d
0x140019570  test    eax, eax
0x140019572  jns     short loc_140019586
0x140019574  jmp     short loc_14001957E
0x140019576  cmp     r14, rbx
0x140019579  jnb     short loc_140019583
0x14001957b  xor     r14d, r14d
0x14001957e  mov     r12, rdi
0x140019581  jmp     short loc_140019586
0x140019583  xor     r14d, r14d
0x140019586  mov     rbx, rdi
0x140019589  mov     rdi, [rdi]
0x14001958c  cmp     [rdi+19h], r14b
0x140019590  jz      loc_1400194DA
0x140019596  mov     r15, [rsp+1A0h+var_140]
0x14001959b  mov     rax, [rsp+1A0h+var_150]
0x1400195a0  cmp     [r12+19h], r14b
0x1400195a5  jz      short loc_1400195B0
0x1400195a7  mov     rdi, [rax]
0x1400195aa  add     rdi, 8
0x1400195ae  jmp     short loc_140019609
0x1400195b0  mov     rdi, r12
0x1400195b3  jmp     short loc_140019609
0x1400195b5  mov     rsi, [rdi+30h]
0x1400195b9  lea     rdx, [rdi+20h]
0x1400195bd  cmp     qword ptr [rdi+38h], 7
0x1400195c2  jbe     short loc_1400195C7
0x1400195c4  mov     rdx, [rdx]; S2
0x1400195c7  mov     r14, [rbp+0A0h+N]
0x1400195cb  lea     rcx, [rbp+0A0h+S2]
0x1400195cf  cmp     [rbp+0A0h+var_F0], 7
0x1400195d4  cmova   rcx, [rbp+0A0h+S2]; S1
0x1400195d9  mov     r8, r14
0x1400195dc  cmp     rsi, r14
0x1400195df  cmovb   r8, rsi; N
0x1400195e3  call    wmemcmp
0x1400195e8  test    eax, eax
0x1400195ea  jz      short loc_1400195F5
0x1400195ec  xor     r14d, r14d
0x1400195ef  test    eax, eax
0x1400195f1  jns     short loc_140019605
0x1400195f3  jmp     short loc_1400195FD
0x1400195f5  cmp     r14, rsi
0x1400195f8  jnb     short loc_140019602
0x1400195fa  xor     r14d, r14d
0x1400195fd  mov     r12, rdi
0x140019600  jmp     short loc_140019609
0x140019602  xor     r14d, r14d
0x140019605  add     rdi, 10h
0x140019609  mov     rdi, [rdi]
0x14001960c  cmp     [rdi+19h], r14b
0x140019610  jz      short loc_1400195B5
0x140019612  mov     rsi, [rsp+1A0h+var_160]
0x140019617  lea     rdi, [rsi+8]
0x14001961b  cmp     rbx, r12
0x14001961e  jz      loc_1400196C7
0x140019624  mov     rcx, [rbx+40h]; this
0x140019628  lea     rdi, [rsi+8]
0x14001962c  mov     eax, [rcx+38h]
0x14001962f  cmp     [rdi], eax
0x140019631  jnz     short loc_14001965A
0x140019633  call    ?IsInvalidated@CMidiPipe@@QEAA_NXZ; CMidiPipe::IsInvalidated(void)
0x140019638  test    al, al
0x14001963a  jnz     short loc_14001965A
0x14001963c  cmp     [r15], r14
0x14001963f  jnz     short loc_1400196A2
0x140019641  mov     rcx, [rbx+40h]
0x140019645  mov     [r15], rcx
0x140019648  test    rcx, rcx
0x14001964b  jz      short loc_14001965A
0x14001964d  mov     rax, [rcx]
0x140019650  mov     rax, [rax+8]
0x140019654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019659  nop
0x14001965a  mov     rcx, [rbx+10h]
0x14001965e  cmp     [rcx+19h], r14b
0x140019662  jz      short loc_140019682
0x140019664  mov     rax, [rbx+8]
0x140019668  jmp     short loc_140019677
0x14001966a  cmp     rbx, [rax+10h]
0x14001966e  jnz     short loc_14001967D
0x140019670  mov     rbx, rax
0x140019673  mov     rax, [rax+8]
0x140019677  cmp     [rax+19h], r14b
0x14001967b  jz      short loc_14001966A
0x14001967d  mov     rbx, rax
0x140019680  jmp     short loc_14001961B
0x140019682  mov     rbx, rcx
0x140019685  mov     rcx, [rcx]
0x140019688  cmp     [rcx+19h], r14b
0x14001968c  jnz     short loc_14001961B
0x14001968e  mov     rbx, rcx
0x140019691  mov     rax, [rcx]
0x140019694  mov     rcx, rax
0x140019697  cmp     [rax+19h], r14b
0x14001969b  jz      short loc_14001968E
0x14001969d  jmp     loc_14001961B
0x1400196a2  mov     rcx, [rbp+0A8h]; this
0x1400196a9  mov     edi, 8000FFFFh
0x1400196ae  mov     r9d, edi; char *
0x1400196b1  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x1400196b8  mov     edx, 1CEh; void *
0x1400196bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400196c2  jmp     loc_140019A7A
0x1400196c7  cmp     [r15], r14
0x1400196ca  jnz     loc_1400199FE
0x1400196d0  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400196d5  mov     r10, [rax+8]
0x1400196d9  mov     eax, [r10]
0x1400196dc  cmp     eax, 5
0x1400196df  jbe     loc_140019788
0x1400196e5  mov     eax, [rdi]
0x1400196e7  mov     dword ptr [rsp+1A0h+var_158], eax
0x1400196eb  lea     rax, [rbp+0A0h+S2]
0x1400196ef  cmp     [rbp+0A0h+var_F0], 7
0x1400196f4  cmova   rax, [rbp+0A0h+S2]
0x1400196f9  lea     rcx, [rsp+1A0h+var_158]
0x1400196fe  mov     [rbp+0A0h+var_60], rcx
0x140019702  mov     [rbp+0A0h+var_58], 4
0x14001970a  test    rax, rax
0x14001970d  jz      short loc_140019725
0x14001970f  mov     rcx, r13
0x140019712  inc     rcx
0x140019715  cmp     [rax+rcx*2], r14w
0x14001971a  jnz     short loc_140019712
0x14001971c  lea     ecx, ds:2[rcx*2]
0x140019723  jmp     short loc_140019731
0x140019725  lea     rax, S2
0x14001972c  mov     ecx, 2
0x140019731  mov     [rbp+0A0h+var_70], rax
0x140019735  mov     dword ptr [rbp+0A0h+var_68], ecx
0x140019738  mov     dword ptr [rbp+0A0h+var_68+4], r14d
0x14001973c  lea     rax, aNoValidPipeFou; "No valid pipe found, creating new one"
0x140019743  mov     [rbp+0A0h+var_80], rax
0x140019747  mov     [rbp+0A0h+var_78], 4Ch ; 'L'
0x14001974f  lea     rax, aCmidiclientman_7; "CMidiClientManager::GetMidiDevice"
0x140019756  mov     [rbp+0A0h+var_90], rax
0x14001975a  mov     [rbp+0A0h+var_88], 22h ; '"'
0x140019762  lea     rax, [rbp+0A0h+var_B0]
0x140019766  mov     [rsp+1A0h+var_178], rax
0x14001976b  mov     [rsp+1A0h+var_180], 6; int
0x140019773  xor     r9d, r9d
0x140019776  xor     r8d, r8d
0x140019779  lea     rdx, byte_140087D3F
0x140019780  mov     rcx, r10
0x140019783  call    _tlgWriteTransfer_EventWriteTransfer
0x140019788  mov     [rsp+1A0h+var_148], r14
0x14001978d  mov     [rbp+0A0h+var_E8], r14
0x140019791  mov     eax, [rsi+0Ch]
0x140019794  mov     [rbp+0A0h+var_E0], eax
0x140019797  mov     dword ptr [rsp+1A0h+var_158], r13d
0x14001979c  lea     rdx, [rbp+0A0h+S2]
0x1400197a0  cmp     [rbp+0A0h+var_F0], 7
0x1400197a5  cmova   rdx, [rbp+0A0h+S2]
0x1400197aa  xorps   xmm0, xmm0
0x1400197ad  movups  [rbp+0A0h+var_D8], xmm0
0x1400197b1  mov     qword ptr [rbp+0A0h+var_C8], r14
0x1400197b5  mov     qword ptr [rbp+0A0h+var_C8+8], r14
0x1400197b9  inc     r13
0x1400197bc  cmp     [rdx+r13*2], r14w
0x1400197c1  jnz     short loc_1400197B9
0x1400197c3  mov     r8, r13
0x1400197c6  lea     rcx, [rbp+0A0h+var_D8]
0x1400197ca  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400197cf  lea     rdx, [rsp+1A0h+var_158]
0x1400197d4  lea     rcx, [rbp+0A0h+var_D8]; void *
0x1400197d8  call    ?GetDeviceSupportedDataFormat@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0001@@@Z; GetDeviceSupportedDataFormat(std::wstring,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0001 &)
0x1400197dd  mov     rcx, [rbp+0A8h]; this
0x1400197e4  test    eax, eax
0x1400197e6  jns     short loc_1400197FC
0x1400197e8  mov     r9d, eax; char *
0x1400197eb  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x1400197f2  mov     edx, 1E9h; void *
0x1400197f7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400197fc  mov     eax, dword ptr [rsp+1A0h+var_158]
0x140019800  mov     dword ptr [rbp+0A0h+var_E8], eax
0x140019803  mov     eax, [rdi]
0x140019805  mov     dword ptr [rbp+0A0h+var_E8+4], eax
0x140019808  mov     [rsp+1A0h+var_148], r14
0x14001980d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140019814  mov     ecx, 0B0h; unsigned __int64
0x140019819  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001981e  mov     rbx, rax
0x140019821  mov     [rsp+1A0h+var_160], rax
0x140019826  mov     [rsp+1A0h+var_140], rax
0x14001982b  test    rax, rax
  ... truncated ...
```
