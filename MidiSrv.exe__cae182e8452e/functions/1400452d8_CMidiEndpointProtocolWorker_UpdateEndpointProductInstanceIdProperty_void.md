# CMidiEndpointProtocolWorker::UpdateEndpointProductInstanceIdProperty(void)

- ea: `0x1400452d8`
- end: `0x140045547`
- name: `?UpdateEndpointProductInstanceIdProperty@CMidiEndpointProtocolWorker@@AEAAJXZ`
- size: `623`
- prototype: `__int64 __fastcall(CMidiEndpointProtocolWorker *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140042d08`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x140013a38`
- `0x14001ddc4`
- `0x1400216cc`
- `0x1400452d8`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140045385`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140045385`

## string_xrefs

- `0x14004550a`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x140045339`: `CMidiEndpointProtocolWorker::UpdateEndpointProductInstanceIdProperty`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMidiEndpointProtocolWorker::UpdateEndpointProductInstanceIdProperty(
        CMidiEndpointProtocolWorker *this)
{
  _DWORD *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  char *v5; // rbx
  char *v6; // rax
  void *v7; // rax
  __int64 v8; // rax
  char **v9; // rax
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  int v14; // [rsp+20h] [rbp-E0h]
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16[2]; // [rsp+48h] [rbp-B8h] BYREF
  char *v17; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v18; // [rsp+58h] [rbp-A8h] BYREF
  CMidiEndpointProtocolWorker *v19; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[32]; // [rsp+68h] [rbp-98h] BYREF
  char *v21[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v22; // [rsp+98h] [rbp-68h]
  unsigned __int64 v23; // [rsp+A0h] [rbp-60h]
  char *Src[5]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v25; // [rsp+D0h] [rbp-30h] BYREF
  int v26; // [rsp+E0h] [rbp-20h]
  int v27; // [rsp+E4h] [rbp-1Ch]
  __int64 v28; // [rsp+E8h] [rbp-18h]
  int v29; // [rsp+F0h] [rbp-10h]
  int v30; // [rsp+F4h] [rbp-Ch]
  char **v31; // [rsp+F8h] [rbp-8h]
  __int128 v32; // [rsp+100h] [rbp+0h]
  int v33; // [rsp+110h] [rbp+10h]
  int v34; // [rsp+114h] [rbp+14h]
  __int64 v35; // [rsp+118h] [rbp+18h]
  int v36; // [rsp+120h] [rbp+20h]
  int v37; // [rsp+124h] [rbp+24h]
  __int64 *v38; // [rsp+128h] [rbp+28h]
  __int128 v39; // [rsp+130h] [rbp+30h] BYREF
  int v40; // [rsp+140h] [rbp+40h]
  int v41; // [rsp+144h] [rbp+44h]
  __int64 v42; // [rsp+148h] [rbp+48h]
  __int64 v43; // [rsp+150h] [rbp+50h]
  __int64 v44; // [rsp+158h] [rbp+58h]
  __int128 v45; // [rsp+160h] [rbp+60h]
  int v46; // [rsp+170h] [rbp+70h]
  int v47; // [rsp+174h] [rbp+74h]
  __int64 v48; // [rsp+178h] [rbp+78h]
  int v49; // [rsp+180h] [rbp+80h]
  int v50; // [rsp+184h] [rbp+84h]
  __int64 *v51; // [rsp+188h] [rbp+88h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v2 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  v5 = (char *)this + 56;
  if ( *v2 > 4u )
  {
    if ( *((_QWORD *)this + 10) <= 7u )
      v6 = (char *)this + 56;
    else
      v6 = *(char **)v5;
    v17 = v6;
    v18 = L"Enter";
    v19 = this;
    *(_QWORD *)v16 = "CMidiEndpointProtocolWorker::UpdateEndpointProductInstanceIdProperty";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)&byte_14008BC1F,
      v3,
      v4,
      v16,
      (__int64)&v19,
      &v18,
      &v17);
  }
  v15 = 0;
  GetSystemTimePreciseAsFileTime(&v15);
  v7 = (void *)std::wstring::wstring((__int64)v20, (__int64)this + 248);
  v8 = WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v7);
  std::operator+<unsigned short>(v21, v8, &qword_140081AD0);
  std::wstring::~wstring(Src);
  if ( !v22 )
  {
    v39 = PKEY_MIDI_EndpointProvidedProductInstanceId;
    v40 = 171;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = PKEY_MIDI_EndpointProvidedProductInstanceIdLastUpdateTime;
    v46 = 173;
    v47 = 0;
    v48 = 0;
    v49 = 16;
    v50 = 8;
    v51 = &v15;
    if ( *((_QWORD *)this + 10) > 7u )
      v5 = *(char **)v5;
    v10 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, __int128 *))(**((_QWORD **)this + 22) + 48LL))(
            *((_QWORD *)this + 22),
            v5,
            2,
            &v39);
    v11 = v10;
    if ( v10 < 0 )
    {
      v12 = 1324;
      goto LABEL_17;
    }
LABEL_18:
    v11 = 0;
    goto LABEL_19;
  }
  v25 = PKEY_MIDI_EndpointProvidedProductInstanceId;
  v26 = 171;
  v27 = 0;
  v28 = 0;
  v29 = 18;
  v30 = 2 * v22 + 2;
  v9 = v21;
  if ( v23 > 7 )
    v9 = (char **)v21[0];
  v31 = v9;
  v32 = PKEY_MIDI_EndpointProvidedProductInstanceIdLastUpdateTime;
  v33 = 173;
  v34 = 0;
  v35 = 0;
  v36 = 16;
  v37 = 8;
  v38 = &v15;
  if ( *((_QWORD *)this + 10) > 7u )
    v5 = *(char **)v5;
  v10 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, __int128 *))(**((_QWORD **)this + 22) + 48LL))(
          *((_QWORD *)this + 22),
          v5,
          2,
          &v25);
  v11 = v10;
  if ( v10 >= 0 )
    goto LABEL_18;
  v12 = 1306;
LABEL_17:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
    (const char *)(unsigned int)v10,
    v14);
LABEL_19:
  std::wstring::~wstring(v21);
  return v11;
}

```

## disassembly

```asm
0x1400452d8  push    rbp
0x1400452da  push    rbx
0x1400452db  push    rsi
0x1400452dc  push    rdi
0x1400452dd  lea     rbp, [rsp-0A8h]
0x1400452e5  sub     rsp, 1A8h
0x1400452ec  mov     rax, cs:__security_cookie
0x1400452f3  xor     rax, rsp
0x1400452f6  mov     [rbp+0C0h+var_30], rax
0x1400452fd  mov     rdi, rcx
0x140045300  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140045305  mov     rcx, [rax+8]
0x140045309  mov     eax, [rcx]
0x14004530b  lea     rbx, [rdi+38h]
0x14004530f  cmp     eax, 4
0x140045312  jbe     short loc_140045379
0x140045314  cmp     qword ptr [rbx+18h], 7
0x140045319  jbe     short loc_140045320
0x14004531b  mov     rax, [rbx]
0x14004531e  jmp     short loc_140045323
0x140045320  mov     rax, rbx
0x140045323  mov     [rsp+1C0h+var_170], rax
0x140045328  lea     rax, aEnter; "Enter"
0x14004532f  mov     [rsp+1C0h+var_168], rax
0x140045334  mov     [rsp+1C0h+var_160], rdi
0x140045339  lea     rax, aCmidiendpointp_19; "CMidiEndpointProtocolWorker::UpdateEndp"...
0x140045340  mov     qword ptr [rsp+1C0h+var_178], rax
0x140045345  lea     rax, [rsp+1C0h+var_170]
0x14004534a  mov     [rsp+1C0h+var_188], rax
0x14004534f  lea     rax, [rsp+1C0h+var_168]
0x140045354  mov     [rsp+1C0h+var_190], rax
0x140045359  lea     rax, [rsp+1C0h+var_160]
0x14004535e  mov     [rsp+1C0h+var_198], rax
0x140045363  lea     rax, [rsp+1C0h+var_178]
0x140045368  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x14004536d  lea     rdx, byte_14008BC1F
0x140045374  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140045379  xor     esi, esi
0x14004537b  mov     [rsp+1C0h+var_180], rsi
0x140045380  lea     rcx, [rsp+1C0h+var_180]
0x140045385  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x14004538b  lea     rdx, [rdi+0F8h]
0x140045392  lea     rcx, [rsp+1C0h+var_158]
0x140045397  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14004539c  mov     rdx, rax; void *
0x14004539f  lea     rcx, [rbp+0C0h+Src]; Src
0x1400453a3  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x1400453a8  nop
0x1400453a9  lea     r8, qword_140081AD0
0x1400453b0  mov     rdx, rax
0x1400453b3  lea     rcx, [rbp+0C0h+var_138]
0x1400453b7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1400453bc  nop
0x1400453bd  lea     rcx, [rbp+0C0h+Src]; void *
0x1400453c1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400453c6  mov     rcx, [rbp+0C0h+var_128]
0x1400453ca  movups  xmm0, cs:PKEY_MIDI_EndpointProvidedProductInstanceId
0x1400453d1  mov     eax, cs:dword_14007A390
0x1400453d7  test    rcx, rcx
0x1400453da  jz      loc_140045481
0x1400453e0  movaps  [rbp+0C0h+var_F0], xmm0
0x1400453e4  mov     [rbp+0C0h+var_E0], eax
0x1400453e7  mov     [rbp+0C0h+var_DC], esi
0x1400453ea  mov     [rbp+0C0h+var_D8], rsi
0x1400453ee  mov     [rbp+0C0h+var_D0], 12h
0x1400453f5  lea     eax, ds:2[rcx*2]
0x1400453fc  mov     [rbp+0C0h+var_CC], eax
0x1400453ff  lea     rax, [rbp+0C0h+var_138]
0x140045403  cmp     [rbp+0C0h+var_120], 7
0x140045408  cmova   rax, [rbp+0C0h+var_138]
0x14004540d  mov     [rbp+0C0h+var_C8], rax
0x140045411  movups  xmm0, cs:PKEY_MIDI_EndpointProvidedProductInstanceIdLastUpdateTime
0x140045418  movaps  [rbp+0C0h+var_C0], xmm0
0x14004541c  mov     eax, cs:dword_14007A870
0x140045422  mov     [rbp+0C0h+var_B0], eax
0x140045425  mov     [rbp+0C0h+var_AC], esi
0x140045428  mov     [rbp+0C0h+var_A8], rsi
0x14004542c  mov     [rbp+0C0h+var_A0], 10h
0x140045433  mov     [rbp+0C0h+var_9C], 8
0x14004543a  lea     rax, [rsp+1C0h+var_180]
0x14004543f  mov     [rbp+0C0h+var_98], rax
0x140045443  mov     rcx, [rdi+0B0h]
0x14004544a  mov     rax, [rcx]
0x14004544d  cmp     qword ptr [rbx+18h], 7
0x140045452  jbe     short loc_140045457
0x140045454  mov     rbx, [rbx]
0x140045457  lea     r9, [rbp+0C0h+var_F0]
0x14004545b  mov     r8d, 2
0x140045461  mov     rdx, rbx
0x140045464  mov     rax, [rax+30h]
0x140045468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004546d  mov     ebx, eax
0x14004546f  test    eax, eax
0x140045471  jns     loc_14004551F
0x140045477  mov     edx, 51Ah
0x14004547c  jmp     loc_140045507
0x140045481  movaps  [rbp+0C0h+var_90], xmm0
0x140045485  mov     [rbp+0C0h+var_80], eax
0x140045488  mov     [rbp+0C0h+var_7C], esi
0x14004548b  mov     [rbp+0C0h+var_78], rsi
0x14004548f  mov     [rbp+0C0h+var_70], rsi
0x140045493  mov     [rbp+0C0h+var_68], rsi
0x140045497  movups  xmm0, cs:PKEY_MIDI_EndpointProvidedProductInstanceIdLastUpdateTime
0x14004549e  movaps  [rbp+0C0h+var_60], xmm0
0x1400454a2  mov     eax, cs:dword_14007A870
0x1400454a8  mov     [rbp+0C0h+var_50], eax
0x1400454ab  mov     [rbp+0C0h+var_4C], esi
0x1400454ae  mov     [rbp+0C0h+var_48], rsi
0x1400454b2  mov     [rbp+0C0h+var_40], 10h
0x1400454bc  mov     [rbp+0C0h+var_3C], 8
0x1400454c6  lea     rax, [rsp+1C0h+var_180]
0x1400454cb  mov     [rbp+0C0h+var_38], rax
0x1400454d2  mov     rcx, [rdi+0B0h]
0x1400454d9  mov     rax, [rcx]
0x1400454dc  cmp     qword ptr [rbx+18h], 7
0x1400454e1  jbe     short loc_1400454E6
0x1400454e3  mov     rbx, [rbx]
0x1400454e6  lea     r9, [rbp+0C0h+var_90]
0x1400454ea  mov     r8d, 2
0x1400454f0  mov     rdx, rbx
0x1400454f3  mov     rax, [rax+30h]
0x1400454f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400454fc  mov     ebx, eax
0x1400454fe  test    eax, eax
0x140045500  jns     short loc_14004551F
0x140045502  mov     edx, 52Ch; void *
0x140045507  mov     r9d, eax; char *
0x14004550a  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140045511  mov     rcx, [rbp+0C8h]; this
0x140045518  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004551d  jmp     short loc_140045521
0x14004551f  mov     ebx, esi
0x140045521  lea     rcx, [rbp+0C0h+var_138]; void *
0x140045525  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004552a  mov     eax, ebx
0x14004552c  mov     rcx, [rbp+0C0h+var_30]
0x140045533  xor     rcx, rsp; StackCookie
0x140045536  call    __security_check_cookie
0x14004553b  add     rsp, 1A8h
0x140045542  pop     rdi
0x140045543  pop     rsi
0x140045544  pop     rbx
0x140045545  pop     rbp
0x140045546  retn
```
