# CMidi2LoopbackMidiEndpointManager::CreateParentDevice(void)

- ea: `0x18001d188`
- end: `0x18001d44c`
- name: `?CreateParentDevice@CMidi2LoopbackMidiEndpointManager@@AEAAJXZ`
- size: `708`
- prototype: `__int64 __fastcall(CMidi2LoopbackMidiEndpointManager *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180020170`

## callees

- `0x1800016dc`
- `0x180001a38`
- `0x180004180`
- `0x18000500c`
- `0x18000a024`
- `0x18000b740`
- `0x18000ccd8`
- `0x18000e178`
- `0x18000f0a4`
- `0x18000feb0`
- `0x18001338c`
- `0x18001d188`
- `0x180021328`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d342`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d40b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d342`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d40b`

## string_xrefs

- `0x18001d1c0`: `CMidi2LoopbackMidiEndpointManager::CreateParentDevice`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMidi2LoopbackMidiEndpointManager::CreateParentDevice(CMidi2LoopbackMidiEndpointManager *this)
{
  _DWORD *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  __int64 v6; // rax
  _QWORD *v7; // rax
  __int128 *v8; // rax
  __int64 *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // edi
  __int64 v13; // r8
  __int64 v14; // rax
  _DWORD *v15; // rcx
  int v16; // r8d
  int v17; // r9d
  int v18; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  CMidi2LoopbackMidiEndpointManager *v20; // [rsp+48h] [rbp-B8h] BYREF
  int v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  const char *v22; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v24; // [rsp+68h] [rbp-98h]
  char *v25; // [rsp+80h] [rbp-80h]
  int v26; // [rsp+88h] [rbp-78h]
  __int128 *v27; // [rsp+90h] [rbp-70h]
  _BYTE v28[32]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v29; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v30; // [rsp+E0h] [rbp-20h]
  __int128 v31; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v32; // [rsp+100h] [rbp+0h]
  _QWORD v33[4]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v34[32]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v2 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v20 = this;
    *(_QWORD *)v21 = "CMidi2LoopbackMidiEndpointManager::CreateParentDevice";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v2,
      (unsigned int)byte_1800587A9,
      v3,
      v4,
      (__int64)v21,
      (__int64)&v20);
  }
  if ( *((_QWORD *)this + 11) )
  {
    v31 = 0;
    v32 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v31, L"MIDI 2.0 Loop Devices");
    v29 = 0;
    v30 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v29, L"MIDIU_LOOP_TRANSPORT");
    v6 = std::wstring::wstring(v34, &v29);
    WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(v33, v6);
    std::wstring::~wstring(&v29);
    memset_0(&v23, 0, 0x48u);
    v23 = 72;
    v7 = v33;
    if ( v33[3] > 7u )
      v7 = (_QWORD *)v33[0];
    v24 = v7;
    v26 = 0;
    v8 = &v31;
    if ( *((_QWORD *)&v32 + 1) > 7u )
      v8 = (__int128 *)v31;
    v27 = v8;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl'::`2'::impl) )
      v25 = (char *)this + 20;
    pv = 0;
    v9 = (__int64 *)*((_QWORD *)this + 11);
    v10 = *v9;
    pv = 0;
    v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, int *))(v10 + 24))(v9, 0, 0, &v23);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v29 = 0;
      v30 = 0;
      v13 = -1;
      do
        ++v13;
      while ( *((_WORD *)pv + v13) );
      std::wstring::_Construct<1,unsigned short const *>(&v29, pv);
      v14 = std::wstring::wstring(v28, &v29);
      WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(v34, v14);
      std::wstring::operator=((char *)this + 56, v34);
      std::wstring::~wstring(v34);
      std::wstring::~wstring(&v29);
      v15 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
      if ( *v15 > 4u )
      {
        *(_QWORD *)v21 = pv;
        v20 = this;
        v22 = "CMidi2LoopbackMidiEndpointManager::CreateParentDevice";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v15,
          (unsigned int)byte_180058761,
          v16,
          v17,
          (__int64)&v22,
          (__int64)&v20,
          (__int64)v21);
      }
      v12 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidiendpointmanager.cpp",
        (const char *)(unsigned int)v11,
        (int)&pv);
      if ( pv )
        CoTaskMemFree(pv);
    }
    std::wstring::~wstring(v33);
    std::wstring::~wstring(&v31);
    return v12;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidiendpointmanager.cpp",
      (const char *)0x80004003LL,
      v18);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18001d188  mov     [rsp-8+arg_8], rbx
0x18001d18d  mov     [rsp-8+arg_10], rsi
0x18001d192  push    rbp
0x18001d193  push    rdi
0x18001d194  push    r14
0x18001d196  lea     rbp, [rsp-60h]
0x18001d19b  sub     rsp, 160h
0x18001d1a2  mov     rax, cs:__security_cookie
0x18001d1a9  xor     rax, rsp
0x18001d1ac  mov     [rbp+70h+var_20], rax
0x18001d1b0  mov     rbx, rcx
0x18001d1b3  xor     esi, esi
0x18001d1b5  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x18001d1ba  mov     rcx, [rax+8]
0x18001d1be  mov     eax, [rcx]
0x18001d1c0  lea     r14, aCmidi2loopback_7; "CMidi2LoopbackMidiEndpointManager::Crea"...
0x18001d1c7  cmp     eax, 4
0x18001d1ca  jbe     short loc_18001D1F6
0x18001d1cc  mov     [rsp+170h+var_128], rbx
0x18001d1d1  mov     qword ptr [rsp+170h+var_120], r14
0x18001d1d6  lea     rax, [rsp+170h+var_128]
0x18001d1db  mov     [rsp+170h+var_148], rax
0x18001d1e0  lea     rax, [rsp+170h+var_120]
0x18001d1e5  mov     qword ptr [rsp+170h+var_150], rax; int
0x18001d1ea  lea     rdx, byte_1800587A9
0x18001d1f1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18001d1f6  cmp     [rbx+58h], rsi
0x18001d1fa  jnz     short loc_18001D220
0x18001d1fc  mov     rcx, [rbp+78h]; this
0x18001d200  mov     ebx, 80004003h
0x18001d205  mov     r9d, ebx; char *
0x18001d208  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\loopbackmidit"...
0x18001d20f  mov     edx, 7Dh ; '}'; void *
0x18001d214  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d219  mov     eax, ebx
0x18001d21b  jmp     loc_18001D428
0x18001d220  xorps   xmm0, xmm0
0x18001d223  movups  [rbp+70h+var_80], xmm0
0x18001d227  xorps   xmm1, xmm1
0x18001d22a  movdqu  [rbp+70h+var_70], xmm1
0x18001d22f  mov     r8d, 15h
0x18001d235  lea     rdx, aMidi20LoopDevi; "MIDI 2.0 Loop Devices"
0x18001d23c  lea     rcx, [rbp+70h+var_80]
0x18001d240  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d245  nop
0x18001d246  xorps   xmm0, xmm0
0x18001d249  movups  [rbp+70h+var_A0], xmm0
0x18001d24d  xorps   xmm1, xmm1
0x18001d250  movdqu  [rbp+70h+var_90], xmm1
0x18001d255  mov     r8d, 14h
0x18001d25b  lea     rdx, aMidiuLoopTrans; "MIDIU_LOOP_TRANSPORT"
0x18001d262  lea     rcx, [rbp+70h+var_A0]
0x18001d266  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d26b  nop
0x18001d26c  lea     rdx, [rbp+70h+var_A0]
0x18001d270  lea     rcx, [rbp+70h+var_40]
0x18001d274  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d279  mov     rdx, rax
0x18001d27c  lea     rcx, [rbp+70h+var_60]
0x18001d280  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x18001d285  nop
0x18001d286  lea     rcx, [rbp+70h+var_A0]; void *
0x18001d28a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d28f  mov     edi, 48h ; 'H'
0x18001d294  mov     r8d, edi; Size
0x18001d297  xor     edx, edx; Val
0x18001d299  lea     rcx, [rsp+170h+var_110]; void *
0x18001d29e  call    memset_0
0x18001d2a3  mov     [rsp+170h+var_110], edi
0x18001d2a7  lea     rax, [rbp+70h+var_60]
0x18001d2ab  cmp     [rbp+70h+var_48], 7
0x18001d2b0  cmova   rax, [rbp+70h+var_60]
0x18001d2b5  mov     [rsp+170h+var_108], rax
0x18001d2ba  mov     [rbp+70h+var_E8], esi
0x18001d2bd  lea     rax, [rbp+70h+var_80]
0x18001d2c1  cmp     qword ptr [rbp+70h+var_70+8], 7
0x18001d2c6  cmova   rax, qword ptr [rbp+70h+var_80]
0x18001d2cb  mov     [rbp+70h+var_E0], rax
0x18001d2cf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl(void)'::`2'::impl
0x18001d2d6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(void)
0x18001d2db  test    al, al
0x18001d2dd  jnz     short loc_18001D2E7
0x18001d2df  lea     rax, [rbx+14h]
0x18001d2e3  mov     [rbp+70h+var_F0], rax
0x18001d2e7  mov     [rsp+170h+pv], rsi
0x18001d2ec  mov     rcx, [rbx+58h]
0x18001d2f0  mov     rax, [rcx]
0x18001d2f3  mov     [rsp+170h+pv], rsi
0x18001d2f8  lea     rdx, [rsp+170h+pv]
0x18001d2fd  mov     qword ptr [rsp+170h+var_150], rdx; int
0x18001d302  lea     r9, [rsp+170h+var_110]
0x18001d307  xor     r8d, r8d
0x18001d30a  xor     edx, edx
0x18001d30c  mov     rax, [rax+18h]
0x18001d310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d315  mov     edi, eax
0x18001d317  test    eax, eax
0x18001d319  jns     short loc_18001D34D
0x18001d31b  mov     rcx, [rbp+78h]; this
0x18001d31f  mov     r9d, eax; char *
0x18001d322  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\loopbackmidit"...
0x18001d329  mov     edx, 97h; void *
0x18001d32e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d333  nop
0x18001d334  mov     rcx, [rsp+170h+pv]; pv
0x18001d339  test    rcx, rcx
0x18001d33c  jz      loc_18001D413
0x18001d342  call    cs:__imp_CoTaskMemFree
0x18001d348  jmp     loc_18001D413
0x18001d34d  mov     rdx, [rsp+170h+pv]
0x18001d352  xorps   xmm0, xmm0
0x18001d355  movups  [rbp+70h+var_A0], xmm0
0x18001d359  xorps   xmm1, xmm1
0x18001d35c  movdqu  [rbp+70h+var_90], xmm1
0x18001d361  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001d365  inc     r8
0x18001d368  cmp     [rdx+r8*2], si
0x18001d36d  jnz     short loc_18001D365
0x18001d36f  lea     rcx, [rbp+70h+var_A0]
0x18001d373  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d378  nop
0x18001d379  lea     rdx, [rbp+70h+var_A0]
0x18001d37d  lea     rcx, [rbp+70h+var_C0]
0x18001d381  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d386  mov     rdx, rax
0x18001d389  lea     rcx, [rbp+70h+var_40]
0x18001d38d  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x18001d392  lea     rcx, [rbx+38h]
0x18001d396  lea     rdx, [rbp+70h+var_40]
0x18001d39a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001d39f  lea     rcx, [rbp+70h+var_40]; void *
0x18001d3a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d3a8  nop
0x18001d3a9  lea     rcx, [rbp+70h+var_A0]; void *
0x18001d3ad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d3b2  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x18001d3b7  mov     rcx, [rax+8]
0x18001d3bb  mov     eax, [rcx]
0x18001d3bd  cmp     eax, 4
0x18001d3c0  jbe     short loc_18001D401
0x18001d3c2  mov     rax, [rsp+170h+pv]
0x18001d3c7  mov     qword ptr [rsp+170h+var_120], rax
0x18001d3cc  mov     [rsp+170h+var_128], rbx
0x18001d3d1  mov     [rsp+170h+var_118], r14
0x18001d3d6  lea     rax, [rsp+170h+var_120]
0x18001d3db  mov     [rsp+170h+var_140], rax
0x18001d3e0  lea     rax, [rsp+170h+var_128]
0x18001d3e5  mov     [rsp+170h+var_148], rax
0x18001d3ea  lea     rax, [rsp+170h+var_118]
0x18001d3ef  mov     qword ptr [rsp+170h+var_150], rax
0x18001d3f4  lea     rdx, byte_180058761
0x18001d3fb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18001d400  nop
0x18001d401  mov     rcx, [rsp+170h+pv]; pv
0x18001d406  test    rcx, rcx
0x18001d409  jz      short loc_18001D411
0x18001d40b  call    cs:__imp_CoTaskMemFree
0x18001d411  mov     edi, esi
0x18001d413  lea     rcx, [rbp+70h+var_60]; void *
0x18001d417  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d41c  nop
0x18001d41d  lea     rcx, [rbp+70h+var_80]; void *
0x18001d421  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d426  mov     eax, edi
0x18001d428  mov     rcx, [rbp+70h+var_20]
0x18001d42c  xor     rcx, rsp; StackCookie
0x18001d42f  call    __security_check_cookie
0x18001d434  lea     r11, [rsp+170h+var_10]
0x18001d43c  mov     rbx, [r11+28h]
0x18001d440  mov     rsi, [r11+30h]
0x18001d444  mov     rsp, r11
0x18001d447  pop     r14
0x18001d449  pop     rdi
0x18001d44a  pop     rbp
0x18001d44b  retn
```
