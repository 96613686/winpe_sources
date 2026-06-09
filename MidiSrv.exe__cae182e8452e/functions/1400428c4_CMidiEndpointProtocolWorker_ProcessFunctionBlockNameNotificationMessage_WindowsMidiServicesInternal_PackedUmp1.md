# CMidiEndpointProtocolWorker::ProcessFunctionBlockNameNotificationMessage(WindowsMidiServicesInternal::PackedUmp128 &)

- ea: `0x1400428c4`
- end: `0x140042d02`
- name: `?ProcessFunctionBlockNameNotificationMessage@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z`
- size: `1086`
- prototype: `__int64 __fastcall(CMidiEndpointProtocolWorker *__hidden this, struct WindowsMidiServicesInternal::PackedUmp128 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400412c0`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x140013a38`
- `0x14001440c`
- `0x14001ddc4`
- `0x14002698c`
- `0x140029568`
- `0x140040ff8`
- `0x140041c98`
- `0x1400428c4`
- `0x140045550`

## string_xrefs

- `0x140042aae`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x140042cb0`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x140042927`: `CMidiEndpointProtocolWorker::ProcessFunctionBlockNameNotificationMessage`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMidiEndpointProtocolWorker::ProcessFunctionBlockNameNotificationMessage(
        CMidiEndpointProtocolWorker *this,
        struct WindowsMidiServicesInternal::PackedUmp128 *a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  _QWORD *v7; // rax
  unsigned int v8; // ecx
  int v9; // edi
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  __int64 *v13; // r8
  __int64 *v14; // rcx
  __int64 *v15; // r9
  __int64 *v16; // rdx
  char v17; // r10
  __int64 *v18; // rax
  __int64 *v19; // rbx
  char v20; // dl
  __int64 *v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  void *v24; // rax
  __int64 v25; // rax
  int v26; // eax
  unsigned int v27; // ebx
  __int64 *v28; // r8
  __int64 *v29; // rcx
  __int64 *v30; // r9
  __int64 *v31; // rdx
  char v32; // r10
  __int64 *v33; // rax
  __int64 *v34; // rbx
  char v35; // dl
  __int64 *v36; // rax
  __int64 v37; // rax
  char **v38; // rcx
  void *v39; // rax
  __int64 v40; // rax
  int updated; // eax
  int v43; // [rsp+20h] [rbp-99h]
  char v44[8]; // [rsp+40h] [rbp-79h] BYREF
  int v45[2]; // [rsp+48h] [rbp-71h] BYREF
  int v46; // [rsp+54h] [rbp-65h]
  _QWORD *v47; // [rsp+60h] [rbp-59h] BYREF
  const wchar_t *v48; // [rsp+68h] [rbp-51h] BYREF
  CMidiEndpointProtocolWorker *v49; // [rsp+70h] [rbp-49h] BYREF
  _OWORD v50[2]; // [rsp+78h] [rbp-41h] BYREF
  char v51; // [rsp+98h] [rbp-21h]
  int v52; // [rsp+99h] [rbp-20h]
  __int16 v53; // [rsp+9Dh] [rbp-1Ch]
  char v54; // [rsp+9Fh] [rbp-1Ah]
  _OWORD Src[2]; // [rsp+A0h] [rbp-19h] BYREF
  char v56; // [rsp+C0h] [rbp+7h]
  int v57; // [rsp+C1h] [rbp+8h]
  __int16 v58; // [rsp+C5h] [rbp+Ch]
  char v59; // [rsp+C7h] [rbp+Eh]
  char *v60[4]; // [rsp+C8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    v7 = (_QWORD *)((char *)this + 56);
    if ( *((_QWORD *)this + 10) > 7u )
      v7 = (_QWORD *)*v7;
    v47 = v7;
    v48 = L"Received Function Block Name Notification";
    v49 = this;
    *(_QWORD *)v45 = "CMidiEndpointProtocolWorker::ProcessFunctionBlockNameNotificationMessage";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)byte_14008BA71,
      v5,
      v6,
      v45,
      (__int64)&v49,
      &v48,
      &v47);
  }
  v8 = *(_DWORD *)a2;
  v9 = *(_DWORD *)a2 >> 8;
  v44[0] = BYTE1(*(_DWORD *)a2);
  v10 = (v8 >> 26) & 3;
  if ( !v10 )
  {
    v50[0] = 0;
    v50[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v50[0]) = 0;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    v39 = (void *)CMidiEndpointProtocolWorker::ParseStreamTextMessage(this, v60, a2);
    v40 = WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v39);
    std::wstring::operator=((char **)v50, v40);
    std::wstring::~wstring((char **)Src);
    v51 = 1;
    std::map<unsigned char,MidiFunctionBlockName>::insert_or_assign<MidiFunctionBlockName &>(
      (char *)this + 280,
      v45,
      v44,
      v50);
    std::wstring::wstring((__int64)v60, (__int64)v50);
    updated = CMidiEndpointProtocolWorker::UpdateFunctionBlockNameProperty(this);
    v27 = updated;
    if ( updated < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33A,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
        (const char *)(unsigned int)updated,
        v43);
      std::wstring::~wstring((char **)v50);
      return v27;
    }
    v38 = (char **)v50;
    goto LABEL_59;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    Src[0] = 0;
    Src[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Src[0]) = 0;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    v59 = 0;
    v37 = CMidiEndpointProtocolWorker::ParseStreamTextMessage(this, v60, a2);
    std::wstring::operator=((char **)Src, v37);
    std::wstring::~wstring(v60);
    v56 = 0;
    std::map<unsigned char,MidiFunctionBlockName>::insert_or_assign<MidiFunctionBlockName &>(
      (char *)this + 280,
      v45,
      v44,
      Src);
    v38 = (char **)Src;
LABEL_59:
    std::wstring::~wstring(v38);
    return 0;
  }
  v12 = v11 - 1;
  if ( v12 )
  {
    if ( v12 == 1 )
    {
      v13 = (__int64 *)*((_QWORD *)this + 35);
      v14 = (__int64 *)v13[1];
      v46 = 0;
      v15 = v13;
      v16 = v14;
      if ( !*((_BYTE *)v14 + 25) )
      {
        do
        {
          if ( *((_BYTE *)v16 + 32) >= (unsigned __int8)v9 )
          {
            v17 = 0;
            v15 = v16;
          }
          else
          {
            v17 = 1;
          }
          v18 = v16 + 2;
          if ( !v17 )
            v18 = v16;
          v16 = (__int64 *)*v18;
        }
        while ( !*(_BYTE *)(*v18 + 25) );
      }
      if ( !*((_BYTE *)v15 + 25) && (unsigned __int8)v9 >= *((_BYTE *)v15 + 32) && v15 != v13 )
      {
        v46 = 0;
        v19 = v13;
        while ( !*((_BYTE *)v14 + 25) )
        {
          if ( *((_BYTE *)v14 + 32) >= (unsigned __int8)v9 )
          {
            v20 = 0;
            v19 = v14;
          }
          else
          {
            v20 = 1;
          }
          v21 = v14 + 2;
          if ( !v20 )
            v21 = v14;
          v14 = (__int64 *)*v21;
        }
        if ( *((_BYTE *)v19 + 25) || (unsigned __int8)v9 < *((_BYTE *)v19 + 32) )
          v19 = v13;
        v22 = (__int64)(v19 + 5);
        v23 = CMidiEndpointProtocolWorker::ParseStreamTextMessage(this, v60, a2);
        v24 = (void *)std::operator+<unsigned short>(v50, v22, v23);
        v25 = WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v24);
        std::wstring::operator=((char **)v22, v25);
        std::wstring::~wstring((char **)Src);
        std::wstring::~wstring(v60);
        *(_BYTE *)(v22 + 32) = 1;
        std::wstring::wstring((__int64)v60, v22);
        v26 = CMidiEndpointProtocolWorker::UpdateFunctionBlockNameProperty(this);
        v27 = v26;
        if ( v26 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x35F,
            (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
            (const char *)(unsigned int)v26,
            v43);
          return v27;
        }
      }
    }
  }
  else
  {
    v28 = (__int64 *)*((_QWORD *)this + 35);
    v29 = (__int64 *)v28[1];
    v46 = 0;
    v30 = v28;
    v31 = v29;
    if ( !*((_BYTE *)v29 + 25) )
    {
      do
      {
        if ( *((_BYTE *)v31 + 32) >= (unsigned __int8)v9 )
        {
          v32 = 0;
          v30 = v31;
        }
        else
        {
          v32 = 1;
        }
        v33 = v31 + 2;
        if ( !v32 )
          v33 = v31;
        v31 = (__int64 *)*v33;
      }
      while ( !*(_BYTE *)(*v33 + 25) );
    }
    if ( !*((_BYTE *)v30 + 25) && (unsigned __int8)v9 >= *((_BYTE *)v30 + 32) && v30 != v28 )
    {
      v46 = 0;
      v34 = v28;
      while ( !*((_BYTE *)v29 + 25) )
      {
        if ( *((_BYTE *)v29 + 32) >= (unsigned __int8)v9 )
        {
          v35 = 0;
          v34 = v29;
        }
        else
        {
          v35 = 1;
        }
        v36 = v29 + 2;
        if ( !v35 )
          v36 = v29;
        v29 = (__int64 *)*v36;
      }
      if ( *((_BYTE *)v34 + 25) || (unsigned __int8)v9 < *((_BYTE *)v34 + 32) )
        v34 = v28;
      CMidiEndpointProtocolWorker::ParseStreamTextMessage(this, v60, a2);
      std::wstring::operator+=(v34 + 5);
      std::wstring::~wstring(v60);
      std::map<unsigned char,MidiFunctionBlockName>::insert_or_assign<MidiFunctionBlockName &>(
        (char *)this + 280,
        v45,
        v44,
        v34 + 5);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400428c4  mov     [rsp-8+arg_10], rbx
0x1400428c9  mov     [rsp-8+arg_18], rsi
0x1400428ce  push    rbp
0x1400428cf  push    rdi
0x1400428d0  push    r12
0x1400428d2  push    r14
0x1400428d4  push    r15
0x1400428d6  lea     rbp, [rsp-37h]
0x1400428db  sub     rsp, 0F0h
0x1400428e2  mov     rax, cs:__security_cookie
0x1400428e9  xor     rax, rsp
0x1400428ec  mov     [rbp+57h+var_28], rax
0x1400428f0  mov     r14, rdx
0x1400428f3  mov     rsi, rcx
0x1400428f6  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400428fb  mov     rcx, [rax+8]
0x1400428ff  mov     eax, [rcx]
0x140042901  cmp     eax, 4
0x140042904  jbe     short loc_140042962
0x140042906  lea     rax, [rsi+38h]
0x14004290a  cmp     qword ptr [rax+18h], 7
0x14004290f  jbe     short loc_140042914
0x140042911  mov     rax, [rax]
0x140042914  mov     [rbp+57h+var_B0], rax
0x140042918  lea     rax, aReceivedFuncti; "Received Function Block Name Notificati"...
0x14004291f  mov     [rbp+57h+var_A8], rax
0x140042923  mov     [rbp+57h+var_A0], rsi
0x140042927  lea     rax, aCmidiendpointp_22; "CMidiEndpointProtocolWorker::ProcessFun"...
0x14004292e  mov     qword ptr [rbp+57h+var_C8], rax
0x140042932  lea     rax, [rbp+57h+var_B0]
0x140042936  mov     [rsp+110h+var_D8], rax
0x14004293b  lea     rax, [rbp+57h+var_A8]
0x14004293f  mov     [rsp+110h+var_E0], rax
0x140042944  lea     rax, [rbp+57h+var_A0]
0x140042948  mov     [rsp+110h+var_E8], rax
0x14004294d  lea     rax, [rbp+57h+var_C8]
0x140042951  mov     qword ptr [rsp+110h+var_F0], rax; int
0x140042956  lea     rdx, byte_14008BA71
0x14004295d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140042962  mov     ecx, [r14]
0x140042965  mov     edi, ecx
0x140042967  shr     edi, 8
0x14004296a  mov     [rbp+57h+var_D0], dil
0x14004296e  shr     ecx, 1Ah
0x140042971  xor     r12d, r12d
0x140042974  and     ecx, 3
0x140042977  jz      loc_140042C13
0x14004297d  sub     ecx, 1
0x140042980  jz      loc_140042BA0
0x140042986  sub     ecx, 1
0x140042989  jz      loc_140042AC4
0x14004298f  cmp     ecx, 1
0x140042992  jnz     loc_140042CD8
0x140042998  mov     r8, [rsi+118h]
0x14004299f  mov     rcx, [r8+8]
0x1400429a3  xor     eax, eax
0x1400429a5  mov     [rbp+57h+var_BC], eax
0x1400429a8  mov     r9, r8
0x1400429ab  mov     rdx, rcx
0x1400429ae  cmp     [rcx+19h], r12b
0x1400429b2  jnz     short loc_1400429D9
0x1400429b4  cmp     [rdx+20h], dil
0x1400429b8  jnb     short loc_1400429BF
0x1400429ba  mov     r10b, 1
0x1400429bd  jmp     short loc_1400429C5
0x1400429bf  mov     r10b, r12b
0x1400429c2  mov     r9, rdx
0x1400429c5  lea     rax, [rdx+10h]
0x1400429c9  test    r10b, r10b
0x1400429cc  cmovz   rax, rdx
0x1400429d0  mov     rdx, [rax]
0x1400429d3  cmp     [rdx+19h], r12b
0x1400429d7  jz      short loc_1400429B4
0x1400429d9  cmp     [r9+19h], r12b
0x1400429dd  jnz     loc_140042CD8
0x1400429e3  cmp     dil, [r9+20h]
0x1400429e7  jb      loc_140042CD8
0x1400429ed  cmp     r9, r8
0x1400429f0  jz      loc_140042CD8
0x1400429f6  xor     eax, eax
0x1400429f8  mov     [rbp+57h+var_BC], eax
0x1400429fb  mov     rbx, r8
0x1400429fe  jmp     short loc_140042A1D
0x140042a00  cmp     [rcx+20h], dil
0x140042a04  jnb     short loc_140042A0A
0x140042a06  mov     dl, 1
0x140042a08  jmp     short loc_140042A10
0x140042a0a  mov     dl, r12b
0x140042a0d  mov     rbx, rcx
0x140042a10  lea     rax, [rcx+10h]
0x140042a14  test    dl, dl
0x140042a16  cmovz   rax, rcx
0x140042a1a  mov     rcx, [rax]
0x140042a1d  cmp     [rcx+19h], r12b
0x140042a21  jz      short loc_140042A00
0x140042a23  cmp     [rbx+19h], r12b
0x140042a27  jnz     short loc_140042A2F
0x140042a29  cmp     dil, [rbx+20h]
0x140042a2d  jnb     short loc_140042A32
0x140042a2f  mov     rbx, r8
0x140042a32  add     rbx, 28h ; '('
0x140042a36  mov     r8, r14
0x140042a39  lea     rdx, [rbp+57h+var_48]
0x140042a3d  mov     rcx, rsi
0x140042a40  call    ?ParseStreamTextMessage@CMidiEndpointProtocolWorker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ParseStreamTextMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x140042a45  nop
0x140042a46  mov     r8, rax
0x140042a49  mov     rdx, rbx
0x140042a4c  lea     rcx, [rbp+57h+var_98]
0x140042a50  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x140042a55  mov     rdx, rax; void *
0x140042a58  lea     rcx, [rbp+57h+Src]; Src
0x140042a5c  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x140042a61  mov     rdx, rax
0x140042a64  mov     rcx, rbx
0x140042a67  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140042a6c  lea     rcx, [rbp+57h+Src]; void *
0x140042a70  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140042a75  nop
0x140042a76  lea     rcx, [rbp+57h+var_48]; void *
0x140042a7a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140042a7f  mov     byte ptr [rbx+20h], 1
0x140042a83  mov     rdx, rbx
0x140042a86  lea     rcx, [rbp+57h+var_48]
0x140042a8a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140042a8f  mov     r8, rax
0x140042a92  mov     dl, dil
0x140042a95  mov     rcx, rsi; this
0x140042a98  call    ?UpdateFunctionBlockNameProperty@CMidiEndpointProtocolWorker@@AEAAJEV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CMidiEndpointProtocolWorker::UpdateFunctionBlockNameProperty(uchar,std::wstring)
0x140042a9d  mov     ebx, eax
0x140042a9f  test    eax, eax
0x140042aa1  jns     loc_140042CD8
0x140042aa7  mov     rcx, [rbp+5Fh]; this
0x140042aab  mov     r9d, eax; char *
0x140042aae  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140042ab5  mov     edx, 35Fh; void *
0x140042aba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140042abf  jmp     loc_140042CCB
0x140042ac4  lea     r15, [rsi+118h]
0x140042acb  mov     r8, [r15]
0x140042ace  mov     rcx, [r8+8]
0x140042ad2  xor     eax, eax
0x140042ad4  mov     [rbp+57h+var_BC], eax
0x140042ad7  mov     r9, r8
0x140042ada  mov     rdx, rcx
0x140042add  cmp     [rcx+19h], r12b
0x140042ae1  jnz     short loc_140042B08
0x140042ae3  cmp     [rdx+20h], dil
0x140042ae7  jnb     short loc_140042AEE
0x140042ae9  mov     r10b, 1
0x140042aec  jmp     short loc_140042AF4
0x140042aee  mov     r10b, r12b
0x140042af1  mov     r9, rdx
0x140042af4  lea     rax, [rdx+10h]
0x140042af8  test    r10b, r10b
0x140042afb  cmovz   rax, rdx
0x140042aff  mov     rdx, [rax]
0x140042b02  cmp     [rdx+19h], r12b
0x140042b06  jz      short loc_140042AE3
0x140042b08  cmp     [r9+19h], r12b
0x140042b0c  jnz     loc_140042CD8
0x140042b12  cmp     dil, [r9+20h]
0x140042b16  jb      loc_140042CD8
0x140042b1c  cmp     r9, r8
0x140042b1f  jz      loc_140042CD8
0x140042b25  xor     eax, eax
0x140042b27  mov     [rbp+57h+var_BC], eax
0x140042b2a  mov     rbx, r8
0x140042b2d  jmp     short loc_140042B4C
0x140042b2f  cmp     [rcx+20h], dil
0x140042b33  jnb     short loc_140042B39
0x140042b35  mov     dl, 1
0x140042b37  jmp     short loc_140042B3F
0x140042b39  mov     dl, r12b
0x140042b3c  mov     rbx, rcx
0x140042b3f  lea     rax, [rcx+10h]
0x140042b43  test    dl, dl
0x140042b45  cmovz   rax, rcx
0x140042b49  mov     rcx, [rax]
0x140042b4c  cmp     [rcx+19h], r12b
0x140042b50  jz      short loc_140042B2F
0x140042b52  cmp     [rbx+19h], r12b
0x140042b56  jnz     short loc_140042B5E
0x140042b58  cmp     dil, [rbx+20h]
0x140042b5c  jnb     short loc_140042B61
0x140042b5e  mov     rbx, r8
0x140042b61  mov     r8, r14
0x140042b64  lea     rdx, [rbp+57h+var_48]
0x140042b68  mov     rcx, rsi
0x140042b6b  call    ?ParseStreamTextMessage@CMidiEndpointProtocolWorker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ParseStreamTextMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x140042b70  nop
0x140042b71  mov     rdx, rax
0x140042b74  lea     rcx, [rbx+28h]; Src
0x140042b78  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x140042b7d  nop
0x140042b7e  lea     rcx, [rbp+57h+var_48]; void *
0x140042b82  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140042b87  lea     r9, [rbx+28h]
0x140042b8b  lea     r8, [rbp+57h+var_D0]
0x140042b8f  lea     rdx, [rbp+57h+var_C8]
0x140042b93  mov     rcx, r15
0x140042b96  call    ??$insert_or_assign@AEAUMidiFunctionBlockName@@@?$map@EUMidiFunctionBlockName@@U?$less@E@std@@V?$allocator@U?$pair@$$CBEUMidiFunctionBlockName@@@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEUMidiFunctionBlockName@@@std@@@std@@@std@@@std@@_N@1@AEBEAEAUMidiFunctionBlockName@@@Z; std::map<uchar,MidiFunctionBlockName>::insert_or_assign<MidiFunctionBlockName &>(uchar const &,MidiFunctionBlockName &)
0x140042b9b  jmp     loc_140042CD8
0x140042ba0  xorps   xmm0, xmm0
0x140042ba3  movups  [rbp+57h+Src], xmm0
0x140042ba7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140042baf  movdqu  [rbp+57h+var_60], xmm1
0x140042bb4  mov     word ptr [rbp+57h+Src], r12w
0x140042bb9  mov     [rbp+57h+var_50], r12b
0x140042bbd  xor     eax, eax
0x140042bbf  mov     [rbp+57h+var_4F], eax
0x140042bc2  mov     [rbp+57h+var_4B], ax
0x140042bc6  mov     [rbp+57h+var_49], al
0x140042bc9  mov     r8, r14
0x140042bcc  lea     rdx, [rbp+57h+var_48]
0x140042bd0  mov     rcx, rsi
0x140042bd3  call    ?ParseStreamTextMessage@CMidiEndpointProtocolWorker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ParseStreamTextMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x140042bd8  mov     rdx, rax
0x140042bdb  lea     rcx, [rbp+57h+Src]
0x140042bdf  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140042be4  lea     rcx, [rbp+57h+var_48]; void *
0x140042be8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140042bed  mov     [rbp+57h+var_50], r12b
0x140042bf1  lea     rcx, [rsi+118h]
0x140042bf8  lea     r9, [rbp+57h+Src]
0x140042bfc  lea     r8, [rbp+57h+var_D0]
0x140042c00  lea     rdx, [rbp+57h+var_C8]
0x140042c04  call    ??$insert_or_assign@AEAUMidiFunctionBlockName@@@?$map@EUMidiFunctionBlockName@@U?$less@E@std@@V?$allocator@U?$pair@$$CBEUMidiFunctionBlockName@@@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEUMidiFunctionBlockName@@@std@@@std@@@std@@@std@@_N@1@AEBEAEAUMidiFunctionBlockName@@@Z; std::map<uchar,MidiFunctionBlockName>::insert_or_assign<MidiFunctionBlockName &>(uchar const &,MidiFunctionBlockName &)
0x140042c09  nop
0x140042c0a  lea     rcx, [rbp+57h+Src]
0x140042c0e  jmp     loc_140042CD3
0x140042c13  xorps   xmm0, xmm0
0x140042c16  movups  [rbp+57h+var_98], xmm0
0x140042c1a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140042c22  movdqu  [rbp+57h+var_88], xmm1
0x140042c27  mov     word ptr [rbp+57h+var_98], r12w
0x140042c2c  mov     [rbp+57h+var_78], r12b
0x140042c30  xor     eax, eax
0x140042c32  mov     [rbp+57h+var_77], eax
0x140042c35  mov     [rbp+57h+var_73], ax
0x140042c39  mov     [rbp+57h+var_71], al
0x140042c3c  mov     r8, r14
0x140042c3f  lea     rdx, [rbp+57h+var_48]
0x140042c43  mov     rcx, rsi
0x140042c46  call    ?ParseStreamTextMessage@CMidiEndpointProtocolWorker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ParseStreamTextMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x140042c4b  mov     rdx, rax; void *
0x140042c4e  lea     rcx, [rbp+57h+Src]; Src
0x140042c52  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x140042c57  mov     rdx, rax
0x140042c5a  lea     rcx, [rbp+57h+var_98]
0x140042c5e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140042c63  lea     rcx, [rbp+57h+Src]; void *
0x140042c67  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140042c6c  mov     [rbp+57h+var_78], 1
0x140042c70  lea     rcx, [rsi+118h]
0x140042c77  lea     r9, [rbp+57h+var_98]
0x140042c7b  lea     r8, [rbp+57h+var_D0]
0x140042c7f  lea     rdx, [rbp+57h+var_C8]
0x140042c83  call    ??$insert_or_assign@AEAUMidiFunctionBlockName@@@?$map@EUMidiFunctionBlockName@@U?$less@E@std@@V?$allocator@U?$pair@$$CBEUMidiFunctionBlockName@@@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEUMidiFunctionBlockName@@@std@@@std@@@std@@@std@@_N@1@AEBEAEAUMidiFunctionBlockName@@@Z; std::map<uchar,MidiFunctionBlockName>::insert_or_assign<MidiFunctionBlockName &>(uchar const &,MidiFunctionBlockName &)
0x140042c88  lea     rdx, [rbp+57h+var_98]
0x140042c8c  lea     rcx, [rbp+57h+var_48]
0x140042c90  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140042c95  mov     r8, rax
0x140042c98  mov     dl, dil
0x140042c9b  mov     rcx, rsi; this
0x140042c9e  call    ?UpdateFunctionBlockNameProperty@CMidiEndpointProtocolWorker@@AEAAJEV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CMidiEndpointProtocolWorker::UpdateFunctionBlockNameProperty(uchar,std::wstring)
0x140042ca3  mov     ebx, eax
0x140042ca5  test    eax, eax
0x140042ca7  jns     short loc_140042CCF
0x140042ca9  mov     rcx, [rbp+5Fh]; this
0x140042cad  mov     r9d, eax; char *
0x140042cb0  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140042cb7  mov     edx, 33Ah; void *
0x140042cbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140042cc1  nop
0x140042cc2  lea     rcx, [rbp+57h+var_98]; void *
0x140042cc6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140042ccb  mov     eax, ebx
0x140042ccd  jmp     short loc_140042CDA
0x140042ccf  lea     rcx, [rbp+57h+var_98]; void *
0x140042cd3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140042cd8  xor     eax, eax
0x140042cda  mov     rcx, [rbp+57h+var_28]
0x140042cde  xor     rcx, rsp; StackCookie
0x140042ce1  call    __security_check_cookie
0x140042ce6  lea     r11, [rsp+110h+var_20]
0x140042cee  mov     rbx, [r11+40h]
0x140042cf2  mov     rsi, [r11+48h]
0x140042cf6  mov     rsp, r11
0x140042cf9  pop     r15
0x140042cfb  pop     r14
0x140042cfd  pop     r12
0x140042cff  pop     rdi
0x140042d00  pop     rbp
0x140042d01  retn
```
