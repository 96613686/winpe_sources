# CMidi2DiagnosticsEndpointManager::CreateParentDevice(void)

- ea: `0x18000d0b4`
- end: `0x18000d314`
- name: `?CreateParentDevice@CMidi2DiagnosticsEndpointManager@@AEAAJXZ`
- size: `608`
- prototype: `__int64 __fastcall(CMidi2DiagnosticsEndpointManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18000f4f0`

## callees

- `0x1800016dc`
- `0x1800033d0`
- `0x1800033f4`
- `0x180004170`
- `0x180008f64`
- `0x18000add8`
- `0x18000b7fc`
- `0x18000c4c0`
- `0x18000d0b4`
- `0x180010078`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d210`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d2e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d210`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d2e0`

## string_xrefs

- `0x18000d0eb`: `CMidi2DiagnosticsEndpointManager::CreateParentDevice`
- `0x18000d12c`: `MIDI 2.0 Service Tests`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMidi2DiagnosticsEndpointManager::CreateParentDevice(CMidi2DiagnosticsEndpointManager *this)
{
  _DWORD *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  __int128 *v5; // rax
  __int128 *v6; // rax
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  unsigned int v10; // edi
  __int64 v12; // r8
  char *v13; // rbx
  unsigned __int64 v14; // rdx
  __int64 v15; // rax
  void *v16; // rcx
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  CMidi2DiagnosticsEndpointManager *v18; // [rsp+38h] [rbp-C8h] BYREF
  const char *v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  __int128 *v21; // [rsp+58h] [rbp-A8h]
  char *v22; // [rsp+70h] [rbp-90h]
  int v23; // [rsp+78h] [rbp-88h]
  __int128 *v24; // [rsp+80h] [rbp-80h]
  __int128 v25; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v26; // [rsp+B0h] [rbp-50h]
  __int128 v27; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v28; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v29; // [rsp+D8h] [rbp-28h]
  __int128 v30; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v31; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v32; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v2 = (_DWORD *)*((_QWORD *)MidiDiagnosticsTransportTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v18 = this;
    v19 = "CMidi2DiagnosticsEndpointManager::CreateParentDevice";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v2,
      (unsigned int)&byte_180016DB7,
      v3,
      v4,
      (__int64)&v19,
      (__int64)&v18);
  }
  v30 = 0;
  v31 = 0;
  v32 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v30, L"MIDI 2.0 Service Tests", 22);
  v27 = 0;
  v28 = 0;
  v29 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v27, L"MIDIU_DIAG_TRANSPORT", 20);
  memset_0(&v20, 0, 0x48u);
  v20 = 72;
  v5 = &v27;
  if ( v29 > 7 )
    v5 = (__int128 *)v27;
  v21 = v5;
  v23 = 0;
  v6 = &v30;
  if ( v32 > 7 )
    v6 = (__int128 *)v30;
  v24 = v6;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl'::`2'::impl) )
    v22 = (char *)this + 16;
  pv = 0;
  v7 = (__int64 *)*((_QWORD *)this + 6);
  v8 = *v7;
  pv = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, int *))(v8 + 24))(v7, 0, 0, &v20);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v25 = 0;
    v26 = 0u;
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)pv + v12) );
    std::wstring::_Construct<1,unsigned short const *>(&v25, pv, v12);
    v13 = (char *)this + 56;
    if ( v13 != (char *)&v25 )
    {
      v14 = *((_QWORD *)v13 + 3);
      if ( v14 > 7 )
      {
        v15 = *(_QWORD *)v13;
        if ( 2 * v14 + 2 < 0x1000 )
        {
          v16 = *(void **)v13;
        }
        else
        {
          v16 = *(void **)(v15 - 8);
          if ( (unsigned __int64)(v15 - (_QWORD)v16 - 8) > 0x1F )
            __fastfail(5u);
        }
        operator delete(v16);
      }
      *(_OWORD *)v13 = v25;
      *((_OWORD *)v13 + 1) = v26;
      *(_QWORD *)&v26 = 0;
      *((_QWORD *)&v26 + 1) = 7;
      LOWORD(v25) = 0;
    }
    std::wstring::~wstring(&v25);
    if ( pv )
      CoTaskMemFree(pv);
    std::wstring::~wstring(&v27);
    std::wstring::~wstring(&v30);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"avcore\\midi2\\transport\\diagnosticstransport\\midi2.diagnosticsendpointmanager.cpp",
      (const char *)(unsigned int)v9,
      (int)&pv);
    if ( pv )
      CoTaskMemFree(pv);
    std::wstring::~wstring(&v27);
    std::wstring::~wstring(&v30);
    return v10;
  }
}

```

## disassembly

```asm
0x18000d0b4  push    rbp
0x18000d0b6  push    rbx
0x18000d0b7  push    rsi
0x18000d0b8  push    rdi
0x18000d0b9  lea     rbp, [rsp-18h]
0x18000d0be  sub     rsp, 118h
0x18000d0c5  mov     rax, cs:__security_cookie
0x18000d0cc  xor     rax, rsp
0x18000d0cf  mov     [rbp+30h+var_30], rax
0x18000d0d3  mov     rbx, rcx
0x18000d0d6  call    ?Instance@MidiDiagnosticsTransportTelemetryProvider@@KAPEAV1@XZ; MidiDiagnosticsTransportTelemetryProvider::Instance(void)
0x18000d0db  mov     rcx, [rax+8]
0x18000d0df  mov     eax, [rcx]
0x18000d0e1  cmp     eax, 4
0x18000d0e4  jbe     short loc_18000D117
0x18000d0e6  mov     [rsp+130h+var_F8], rbx
0x18000d0eb  lea     rax, aCmidi2diagnost_3; "CMidi2DiagnosticsEndpointManager::Creat"...
0x18000d0f2  mov     [rsp+130h+var_F0], rax
0x18000d0f7  lea     rax, [rsp+130h+var_F8]
0x18000d0fc  mov     [rsp+130h+var_108], rax
0x18000d101  lea     rax, [rsp+130h+var_F0]
0x18000d106  mov     qword ptr [rsp+130h+var_110], rax
0x18000d10b  lea     rdx, byte_180016DB7
0x18000d112  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000d117  xorps   xmm0, xmm0
0x18000d11a  movups  [rbp+30h+var_50], xmm0
0x18000d11e  xor     esi, esi
0x18000d120  mov     [rbp+30h+var_40], rsi
0x18000d124  mov     [rbp+30h+var_38], rsi
0x18000d128  lea     r8d, [rsi+16h]
0x18000d12c  lea     rdx, aMidi20ServiceT; "MIDI 2.0 Service Tests"
0x18000d133  lea     rcx, [rbp+30h+var_50]
0x18000d137  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000d13c  nop
0x18000d13d  xorps   xmm0, xmm0
0x18000d140  movups  [rbp+30h+var_70], xmm0
0x18000d144  mov     [rbp+30h+var_60], rsi
0x18000d148  mov     [rbp+30h+var_58], rsi
0x18000d14c  lea     r8d, [rsi+14h]
0x18000d150  lea     rdx, aMidiuDiagTrans; "MIDIU_DIAG_TRANSPORT"
0x18000d157  lea     rcx, [rbp+30h+var_70]
0x18000d15b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000d160  nop
0x18000d161  lea     edi, [rsi+48h]
0x18000d164  mov     r8d, edi; Size
0x18000d167  xor     edx, edx; Val
0x18000d169  lea     rcx, [rsp+130h+var_E0]; void *
0x18000d16e  call    memset_0
0x18000d173  mov     [rsp+130h+var_E0], edi
0x18000d177  lea     rax, [rbp+30h+var_70]
0x18000d17b  cmp     [rbp+30h+var_58], 7
0x18000d180  cmova   rax, qword ptr [rbp+30h+var_70]
0x18000d185  mov     [rsp+130h+var_D8], rax
0x18000d18a  mov     [rsp+130h+var_B8], esi
0x18000d18e  lea     rax, [rbp+30h+var_50]
0x18000d192  cmp     [rbp+30h+var_38], 7
0x18000d197  cmova   rax, qword ptr [rbp+30h+var_50]
0x18000d19c  mov     [rbp+30h+var_B0], rax
0x18000d1a0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl(void)'::`2'::impl
0x18000d1a7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(void)
0x18000d1ac  test    al, al
0x18000d1ae  jnz     short loc_18000D1B9
0x18000d1b0  lea     rax, [rbx+10h]
0x18000d1b4  mov     [rsp+130h+var_C0], rax
0x18000d1b9  mov     [rsp+130h+pv], rsi
0x18000d1be  mov     rcx, [rbx+30h]
0x18000d1c2  mov     rax, [rcx]
0x18000d1c5  mov     [rsp+130h+pv], rsi
0x18000d1ca  lea     rdx, [rsp+130h+pv]
0x18000d1cf  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18000d1d4  lea     r9, [rsp+130h+var_E0]
0x18000d1d9  xor     r8d, r8d
0x18000d1dc  xor     edx, edx
0x18000d1de  mov     rax, [rax+18h]
0x18000d1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1e7  mov     edi, eax
0x18000d1e9  test    eax, eax
0x18000d1eb  jns     short loc_18000D231
0x18000d1ed  mov     rcx, [rbp+38h]; this
0x18000d1f1  mov     r9d, eax; char *
0x18000d1f4  lea     r8, aAvcoreMidi2Tra_3; "avcore\\midi2\\transport\\diagnosticstr"...
0x18000d1fb  mov     edx, 64h ; 'd'; void *
0x18000d200  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d205  nop
0x18000d206  mov     rcx, [rsp+130h+pv]; pv
0x18000d20b  test    rcx, rcx
0x18000d20e  jz      short loc_18000D217
0x18000d210  call    cs:__imp_CoTaskMemFree
0x18000d216  nop
0x18000d217  lea     rcx, [rbp+30h+var_70]
0x18000d21b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d220  nop
0x18000d221  lea     rcx, [rbp+30h+var_50]
0x18000d225  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d22a  mov     eax, edi
0x18000d22c  jmp     loc_18000D2FC
0x18000d231  mov     rdx, [rsp+130h+pv]
0x18000d236  xorps   xmm0, xmm0
0x18000d239  movups  [rbp+30h+var_90], xmm0
0x18000d23d  mov     qword ptr [rbp+30h+var_80], rsi
0x18000d241  mov     qword ptr [rbp+30h+var_80+8], rsi
0x18000d245  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000d249  inc     r8
0x18000d24c  cmp     [rdx+r8*2], si
0x18000d251  jnz     short loc_18000D249
0x18000d253  lea     rcx, [rbp+30h+var_90]
0x18000d257  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000d25c  add     rbx, 38h ; '8'
0x18000d260  lea     rax, [rbp+30h+var_90]
0x18000d264  cmp     rbx, rax
0x18000d267  jz      short loc_18000D2CC
0x18000d269  mov     rdx, [rbx+18h]
0x18000d26d  cmp     rdx, 7
0x18000d271  jbe     short loc_18000D2AD
0x18000d273  mov     rax, [rbx]
0x18000d276  lea     rdx, ds:2[rdx*2]
0x18000d27e  cmp     rdx, 1000h
0x18000d285  jb      short loc_18000D2A5
0x18000d287  mov     rcx, [rax-8]
0x18000d28b  sub     rax, rcx
0x18000d28e  sub     rax, 8
0x18000d292  cmp     rax, 1Fh
0x18000d296  ja      short loc_18000D29E
0x18000d298  add     rdx, 27h ; '''
0x18000d29c  jmp     short loc_18000D2A8
0x18000d29e  mov     ecx, 5
0x18000d2a3  int     29h; Win8: RtlFailFast(ecx)
0x18000d2a5  mov     rcx, rax; Block
0x18000d2a8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d2ad  movups  xmm0, [rbp+30h+var_90]
0x18000d2b1  movups  xmmword ptr [rbx], xmm0
0x18000d2b4  movups  xmm1, [rbp+30h+var_80]
0x18000d2b8  movups  xmmword ptr [rbx+10h], xmm1
0x18000d2bc  mov     qword ptr [rbp+30h+var_80], rsi
0x18000d2c0  mov     qword ptr [rbp+30h+var_80+8], 7
0x18000d2c8  mov     word ptr [rbp+30h+var_90], si
0x18000d2cc  lea     rcx, [rbp+30h+var_90]
0x18000d2d0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d2d5  nop
0x18000d2d6  mov     rcx, [rsp+130h+pv]; pv
0x18000d2db  test    rcx, rcx
0x18000d2de  jz      short loc_18000D2E7
0x18000d2e0  call    cs:__imp_CoTaskMemFree
0x18000d2e6  nop
0x18000d2e7  lea     rcx, [rbp+30h+var_70]
0x18000d2eb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d2f0  nop
0x18000d2f1  lea     rcx, [rbp+30h+var_50]
0x18000d2f5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d2fa  xor     eax, eax
0x18000d2fc  mov     rcx, [rbp+30h+var_30]
0x18000d300  xor     rcx, rsp; StackCookie
0x18000d303  call    __security_check_cookie
0x18000d308  add     rsp, 118h
0x18000d30f  pop     rdi
0x18000d310  pop     rsi
0x18000d311  pop     rbx
0x18000d312  pop     rbp
0x18000d313  retn
```
