# CMidi2LoopbackMidiBidi::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *,ulong *,IMidiCallback *,__int64,_GUID)

- ea: `0x180010b70`
- end: `0x180010ffc`
- name: `?Initialize@CMidi2LoopbackMidiBidi@@UEAAJPEBGPEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005@@PEAKPEAUIMidiCallback@@_JU_GUID@@@Z`
- size: `1164`
- prototype: `__int64 __fastcall(CMidi2LoopbackMidiBidi *__hidden this, const unsigned __int16 *, struct __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *, unsigned int *, struct IMidiCallback *, __int64, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x1800016dc`
- `0x180002fc0`
- `0x1800033d0`
- `0x180008f64`
- `0x18000add8`
- `0x18000b7fc`
- `0x18000c4c0`
- `0x180010b70`
- `0x180011190`
- `0x180013010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180010c9a`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180010d0b`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180010d7c`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180010df0`

## pseudocode

```c
__int64 __fastcall CMidi2LoopbackMidiBidi::Initialize(
        CMidi2LoopbackMidiBidi *this,
        const unsigned __int16 *a2,
        struct __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *a3,
        unsigned int *a4,
        struct IMidiCallback *a5,
        __int64 a6)
{
  _DWORD *v9; // rcx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rdx
  unsigned int v13; // ebx
  __int64 v15; // r8
  __int128 *v16; // rsi
  __int128 *v17; // rdx
  unsigned __int16 *v18; // rbx
  unsigned __int16 *v19; // r14
  __int128 *v20; // rsi
  __int128 *v21; // rdx
  unsigned __int16 *v22; // rbx
  unsigned __int16 *v23; // r14
  __int128 *v24; // rsi
  __int128 *v25; // rdx
  unsigned __int16 *v26; // rbx
  unsigned __int16 *v27; // r14
  __int128 *v28; // rcx
  __int128 *v29; // rsi
  __int128 *v30; // rdx
  unsigned __int16 *v31; // rbx
  unsigned __int16 *v32; // r14
  __int16 v33; // ax
  __int128 *v34; // r8
  unsigned __int64 v35; // r10
  __int128 *v36; // rsi
  __int128 *v37; // rdx
  unsigned __int64 v38; // r9
  unsigned __int64 v39; // rax
  char *v40; // rbx
  __int64 v41; // rax
  __int128 *v42; // r8
  __int128 *v43; // rsi
  char *v44; // rbx
  __int64 v45; // rax
  __int128 *v46; // r8
  __int128 *v47; // rsi
  char *v48; // rbx
  __int64 v49; // rax
  struct MidiDeviceTable *v50; // rax
  struct MidiDeviceTable *v51; // rax
  struct MidiDeviceTable *v52; // rax
  int v53; // [rsp+20h] [rbp-91h]
  CMidi2LoopbackMidiBidi *v54; // [rsp+30h] [rbp-81h] BYREF
  int v55[2]; // [rsp+38h] [rbp-79h] BYREF
  __int128 v56; // [rsp+40h] [rbp-71h] BYREF
  __int128 v57; // [rsp+50h] [rbp-61h]
  __int128 v58; // [rsp+60h] [rbp-51h] BYREF
  __int128 v59; // [rsp+70h] [rbp-41h]
  __int128 v60; // [rsp+80h] [rbp-31h] BYREF
  __int128 v61; // [rsp+90h] [rbp-21h]
  __int128 v62; // [rsp+A0h] [rbp-11h] BYREF
  __int128 v63; // [rsp+B0h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+47h]

  v9 = (_DWORD *)*((_QWORD *)MidiDiagnosticsTransportTelemetryProvider::Instance() + 1);
  if ( *v9 > 4u )
  {
    v54 = this;
    *(_QWORD *)v55 = "CMidi2LoopbackMidiBidi::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v9,
      (unsigned int)byte_180016E5B,
      v10,
      v11,
      (__int64)v55,
      (__int64)&v54);
  }
  if ( !a5 )
  {
    v12 = 33;
LABEL_5:
    v13 = -2147024809;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"avcore\\midi2\\transport\\diagnosticstransport\\midi2.loopbackmidibidi.cpp",
      (const char *)v13,
      v53);
    return v13;
  }
  if ( !a3 )
  {
    v12 = 34;
    goto LABEL_5;
  }
  *((_QWORD *)this + 3) = a5;
  *((_QWORD *)this + 4) = a6;
  if ( *((_DWORD *)a3 + 1) != 2 && *((_DWORD *)a3 + 1) != -1 )
  {
    v13 = -2147023266;
    v12 = 43;
    goto LABEL_6;
  }
  *((_DWORD *)a3 + 1) = 2;
  v15 = -1;
  v56 = 0;
  v57 = 0;
  do
    ++v15;
  while ( a2[v15] );
  std::wstring::_Construct<1,unsigned short const *>(&v56, a2, v15);
  if ( *((_QWORD *)&v57 + 1) > 7u )
  {
    v16 = (__int128 *)v56;
    v17 = (__int128 *)v56;
  }
  else
  {
    v16 = &v56;
    v17 = &v56;
  }
  v18 = (unsigned __int16 *)&v56;
  if ( *((_QWORD *)&v57 + 1) > 7u )
    v18 = (unsigned __int16 *)v56;
  v19 = (unsigned __int16 *)v17 + v57;
  while ( v18 != v19 )
  {
    *(_WORD *)v16 = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*v18++);
    v16 = (__int128 *)((char *)v16 + 2);
  }
  v62 = 0;
  v63 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v62, L"MIDIU_DIAG_PING", 15);
  if ( *((_QWORD *)&v63 + 1) > 7u )
  {
    v20 = (__int128 *)v62;
    v21 = (__int128 *)v62;
  }
  else
  {
    v20 = &v62;
    v21 = &v62;
  }
  v22 = (unsigned __int16 *)&v62;
  if ( *((_QWORD *)&v63 + 1) > 7u )
    v22 = (unsigned __int16 *)v62;
  v23 = (unsigned __int16 *)v21 + v63;
  while ( v22 != v23 )
  {
    *(_WORD *)v20 = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*v22++);
    v20 = (__int128 *)((char *)v20 + 2);
  }
  v60 = 0;
  v61 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v60, L"MIDIU_DIAG_LOOPBACK_A", 21);
  if ( *((_QWORD *)&v61 + 1) > 7u )
  {
    v24 = (__int128 *)v60;
    v25 = (__int128 *)v60;
  }
  else
  {
    v24 = &v60;
    v25 = &v60;
  }
  v26 = (unsigned __int16 *)&v60;
  if ( *((_QWORD *)&v61 + 1) > 7u )
    v26 = (unsigned __int16 *)v60;
  v27 = (unsigned __int16 *)v25 + v61;
  while ( v26 != v27 )
  {
    *(_WORD *)v24 = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*v26++);
    v24 = (__int128 *)((char *)v24 + 2);
  }
  v58 = 0;
  v59 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v58, L"MIDIU_DIAG_LOOPBACK_B", 21);
  v28 = (__int128 *)v58;
  if ( *((_QWORD *)&v59 + 1) > 7u )
  {
    v29 = (__int128 *)v58;
    v30 = (__int128 *)v58;
  }
  else
  {
    v29 = &v58;
    v30 = &v58;
  }
  v31 = (unsigned __int16 *)&v58;
  if ( *((_QWORD *)&v59 + 1) > 7u )
    v31 = (unsigned __int16 *)v58;
  v32 = (unsigned __int16 *)v30 + v59;
  if ( v31 != v32 )
  {
    do
    {
      v33 = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*v31++);
      *(_WORD *)v29 = v33;
      v29 = (__int128 *)((char *)v29 + 2);
    }
    while ( v31 != v32 );
    v28 = (__int128 *)v58;
  }
  v34 = &v62;
  v35 = *((_QWORD *)&v57 + 1);
  v36 = &v56;
  if ( *((_QWORD *)&v63 + 1) > 7u )
    v34 = (__int128 *)v62;
  v37 = (__int128 *)v56;
  v38 = v63;
  if ( *((_QWORD *)&v57 + 1) > 7u )
    v36 = (__int128 *)v56;
  v39 = v57;
  *((_BYTE *)this + 56) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  if ( v38 <= v39 )
  {
    if ( !v38
      || (v40 = (char *)v36 + 2 * v39, v41 = _std_search_2(v36, v40, v34), (char *)v41 != v40)
      && (v41 - (__int64)v36) >> 1 != -1 )
    {
      *((_BYTE *)this + 57) = 1;
      v51 = MidiDeviceTable::Current();
      *((_QWORD *)this + 6) = (char *)v51 + 32;
      *((_QWORD *)v51 + 4) = (char *)this + 8;
      *((_QWORD *)v51 + 5) = 0;
      goto LABEL_73;
    }
    v35 = *((_QWORD *)&v57 + 1);
    v39 = v57;
    v37 = (__int128 *)v56;
    v28 = (__int128 *)v58;
  }
  v42 = &v60;
  v43 = &v56;
  if ( *((_QWORD *)&v61 + 1) > 7u )
    v42 = (__int128 *)v60;
  if ( v35 > 7 )
    v43 = v37;
  if ( (unsigned __int64)v61 <= v39 )
  {
    if ( !(_QWORD)v61
      || (v44 = (char *)v43 + 2 * v39, v45 = _std_search_2(v43, v44, v42), (char *)v45 != v44)
      && (v45 - (__int64)v43) >> 1 != -1 )
    {
      *((_BYTE *)this + 56) = 1;
      v52 = MidiDeviceTable::Current();
      *((_QWORD *)this + 5) = v52;
      *(_QWORD *)v52 = (char *)this + 8;
      *((_QWORD *)v52 + 1) = 0;
      goto LABEL_73;
    }
    v35 = *((_QWORD *)&v57 + 1);
    v39 = v57;
    v37 = (__int128 *)v56;
    v28 = (__int128 *)v58;
  }
  v46 = &v58;
  v47 = &v56;
  if ( *((_QWORD *)&v59 + 1) > 7u )
    v46 = v28;
  if ( v35 > 7 )
    v47 = v37;
  if ( (unsigned __int64)v59 <= v39 )
  {
    if ( !(_QWORD)v59
      || (v48 = (char *)v47 + 2 * v39, v49 = _std_search_2(v47, v48, v46), (char *)v49 != v48)
      && (v49 - (__int64)v47) >> 1 != -1 )
    {
      *((_BYTE *)this + 56) = 0;
      v50 = MidiDeviceTable::Current();
      *((_QWORD *)this + 5) = v50;
      *((_QWORD *)v50 + 2) = (char *)this + 8;
      *((_QWORD *)v50 + 3) = 0;
LABEL_73:
      std::wstring::~wstring(&v58);
      std::wstring::~wstring(&v60);
      std::wstring::~wstring(&v62);
      std::wstring::~wstring(&v56);
      return 0;
    }
  }
  std::wstring::~wstring(&v58);
  std::wstring::~wstring(&v60);
  std::wstring::~wstring(&v62);
  std::wstring::~wstring(&v56);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180010b70  mov     [rsp-8+arg_18], rbx
0x180010b75  push    rbp
0x180010b76  push    rsi
0x180010b77  push    rdi
0x180010b78  push    r14
0x180010b7a  push    r15
0x180010b7c  lea     rbp, [rsp-1Fh]
0x180010b81  sub     rsp, 0D0h
0x180010b88  mov     rax, cs:__security_cookie
0x180010b8f  xor     rax, rsp
0x180010b92  mov     [rbp+3Fh+var_30], rax
0x180010b96  mov     rbx, r8
0x180010b99  mov     rsi, rdx
0x180010b9c  mov     rdi, rcx
0x180010b9f  call    ?Instance@MidiDiagnosticsTransportTelemetryProvider@@KAPEAV1@XZ; MidiDiagnosticsTransportTelemetryProvider::Instance(void)
0x180010ba4  mov     rcx, [rax+8]
0x180010ba8  mov     eax, [rcx]
0x180010baa  cmp     eax, 4
0x180010bad  jbe     short loc_180010BDE
0x180010baf  lea     rax, aCmidi2loopback_0; "CMidi2LoopbackMidiBidi::Initialize"
0x180010bb6  mov     [rsp+0F0h+var_C0], rdi
0x180010bbb  mov     qword ptr [rbp+3Fh+var_B8], rax
0x180010bbf  lea     rdx, byte_180016E5B
0x180010bc6  lea     rax, [rsp+0F0h+var_C0]
0x180010bcb  mov     [rsp+0F0h+var_C8], rax
0x180010bd0  lea     rax, [rbp+3Fh+var_B8]
0x180010bd4  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180010bd9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180010bde  mov     rax, [rbp+3Fh+arg_20]
0x180010be2  xor     r15d, r15d
0x180010be5  test    rax, rax
0x180010be8  jnz     short loc_180010C0C
0x180010bea  lea     edx, [rax+21h]; void *
0x180010bed  mov     ebx, 80070057h
0x180010bf2  mov     rcx, [rbp+47h]; this
0x180010bf6  lea     r8, aAvcoreMidi2Tra_1; "avcore\\midi2\\transport\\diagnosticstr"...
0x180010bfd  mov     r9d, ebx; char *
0x180010c00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c05  mov     eax, ebx
0x180010c07  jmp     loc_180010FD9
0x180010c0c  test    rbx, rbx
0x180010c0f  jnz     short loc_180010C16
0x180010c11  lea     edx, [rbx+22h]
0x180010c14  jmp     short loc_180010BED
0x180010c16  mov     [rdi+18h], rax
0x180010c1a  mov     rax, [rbp+3Fh+arg_28]
0x180010c1e  mov     [rdi+20h], rax
0x180010c22  cmp     dword ptr [rbx+4], 2
0x180010c26  jz      short loc_180010C3A
0x180010c28  cmp     dword ptr [rbx+4], 0FFFFFFFFh
0x180010c2c  jz      short loc_180010C3A
0x180010c2e  mov     ebx, 8007065Eh
0x180010c33  mov     edx, 2Bh ; '+'
0x180010c38  jmp     short loc_180010BF2
0x180010c3a  xorps   xmm0, xmm0
0x180010c3d  mov     dword ptr [rbx+4], 2
0x180010c44  xorps   xmm1, xmm1
0x180010c47  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010c4b  movups  [rbp+3Fh+var_B0], xmm0
0x180010c4f  movdqu  [rbp+3Fh+var_A0], xmm1
0x180010c54  inc     r8
0x180010c57  cmp     [rsi+r8*2], r15w
0x180010c5c  jnz     short loc_180010C54
0x180010c5e  mov     rdx, rsi
0x180010c61  lea     rcx, [rbp+3Fh+var_B0]
0x180010c65  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180010c6a  cmp     qword ptr [rbp+3Fh+var_A0+8], 7
0x180010c6f  mov     rcx, qword ptr [rbp+3Fh+var_B0]
0x180010c73  ja      short loc_180010C7F
0x180010c75  lea     rsi, [rbp+3Fh+var_B0]
0x180010c79  lea     rdx, [rbp+3Fh+var_B0]
0x180010c7d  jmp     short loc_180010C85
0x180010c7f  mov     rsi, rcx
0x180010c82  mov     rdx, rcx
0x180010c85  mov     rax, qword ptr [rbp+3Fh+var_A0]
0x180010c89  lea     rbx, [rbp+3Fh+var_B0]
0x180010c8d  cmova   rbx, rcx
0x180010c91  lea     r14, [rdx+rax*2]
0x180010c95  jmp     short loc_180010CB1
0x180010c97  movzx   ecx, word ptr [rbx]
0x180010c9a  mov     rax, cs:__imp__o_towlower
0x180010ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ca6  mov     [rsi], ax
0x180010ca9  add     rbx, 2
0x180010cad  lea     rsi, [rsi+2]
0x180010cb1  cmp     rbx, r14
0x180010cb4  jnz     short loc_180010C97
0x180010cb6  xorps   xmm0, xmm0
0x180010cb9  lea     rdx, aMidiuDiagPing; "MIDIU_DIAG_PING"
0x180010cc0  xorps   xmm1, xmm1
0x180010cc3  lea     rcx, [rbp+3Fh+var_50]
0x180010cc7  mov     r8d, 0Fh
0x180010ccd  movups  [rbp+3Fh+var_50], xmm0
0x180010cd1  movdqu  [rbp+3Fh+var_40], xmm1
0x180010cd6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180010cdb  cmp     qword ptr [rbp+3Fh+var_40+8], 7
0x180010ce0  mov     rcx, qword ptr [rbp+3Fh+var_50]
0x180010ce4  ja      short loc_180010CF0
0x180010ce6  lea     rsi, [rbp+3Fh+var_50]
0x180010cea  lea     rdx, [rbp+3Fh+var_50]
0x180010cee  jmp     short loc_180010CF6
0x180010cf0  mov     rsi, rcx
0x180010cf3  mov     rdx, rcx
0x180010cf6  mov     rax, qword ptr [rbp+3Fh+var_40]
0x180010cfa  lea     rbx, [rbp+3Fh+var_50]
0x180010cfe  cmova   rbx, rcx
0x180010d02  lea     r14, [rdx+rax*2]
0x180010d06  jmp     short loc_180010D22
0x180010d08  movzx   ecx, word ptr [rbx]
0x180010d0b  mov     rax, cs:__imp__o_towlower
0x180010d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d17  mov     [rsi], ax
0x180010d1a  add     rbx, 2
0x180010d1e  lea     rsi, [rsi+2]
0x180010d22  cmp     rbx, r14
0x180010d25  jnz     short loc_180010D08
0x180010d27  xorps   xmm0, xmm0
0x180010d2a  lea     rdx, aMidiuDiagLoopb_0; "MIDIU_DIAG_LOOPBACK_A"
0x180010d31  xorps   xmm1, xmm1
0x180010d34  lea     rcx, [rbp+3Fh+var_70]
0x180010d38  mov     r8d, 15h
0x180010d3e  movups  [rbp+3Fh+var_70], xmm0
0x180010d42  movdqu  [rbp+3Fh+var_60], xmm1
0x180010d47  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180010d4c  cmp     qword ptr [rbp+3Fh+var_60+8], 7
0x180010d51  mov     rcx, qword ptr [rbp+3Fh+var_70]
0x180010d55  ja      short loc_180010D61
0x180010d57  lea     rsi, [rbp+3Fh+var_70]
0x180010d5b  lea     rdx, [rbp+3Fh+var_70]
0x180010d5f  jmp     short loc_180010D67
0x180010d61  mov     rsi, rcx
0x180010d64  mov     rdx, rcx
0x180010d67  mov     rax, qword ptr [rbp+3Fh+var_60]
0x180010d6b  lea     rbx, [rbp+3Fh+var_70]
0x180010d6f  cmova   rbx, rcx
0x180010d73  lea     r14, [rdx+rax*2]
0x180010d77  jmp     short loc_180010D93
0x180010d79  movzx   ecx, word ptr [rbx]
0x180010d7c  mov     rax, cs:__imp__o_towlower
0x180010d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d88  mov     [rsi], ax
0x180010d8b  add     rbx, 2
0x180010d8f  lea     rsi, [rsi+2]
0x180010d93  cmp     rbx, r14
0x180010d96  jnz     short loc_180010D79
0x180010d98  xorps   xmm0, xmm0
0x180010d9b  lea     rdx, aMidiuDiagLoopb; "MIDIU_DIAG_LOOPBACK_B"
0x180010da2  xorps   xmm1, xmm1
0x180010da5  lea     rcx, [rbp+3Fh+var_90]
0x180010da9  mov     r8d, 15h
0x180010daf  movups  [rbp+3Fh+var_90], xmm0
0x180010db3  movdqu  [rbp+3Fh+var_80], xmm1
0x180010db8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180010dbd  cmp     qword ptr [rbp+3Fh+var_80+8], 7
0x180010dc2  mov     rcx, qword ptr [rbp+3Fh+var_90]
0x180010dc6  ja      short loc_180010DD2
0x180010dc8  lea     rsi, [rbp+3Fh+var_90]
0x180010dcc  lea     rdx, [rbp+3Fh+var_90]
0x180010dd0  jmp     short loc_180010DD8
0x180010dd2  mov     rsi, rcx
0x180010dd5  mov     rdx, rcx
0x180010dd8  mov     rax, qword ptr [rbp+3Fh+var_80]
0x180010ddc  lea     rbx, [rbp+3Fh+var_90]
0x180010de0  cmova   rbx, rcx
0x180010de4  lea     r14, [rdx+rax*2]
0x180010de8  cmp     rbx, r14
0x180010deb  jz      short loc_180010E10
0x180010ded  movzx   ecx, word ptr [rbx]
0x180010df0  mov     rax, cs:__imp__o_towlower
0x180010df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dfc  add     rbx, 2
0x180010e00  mov     [rsi], ax
0x180010e03  lea     rsi, [rsi+2]
0x180010e07  cmp     rbx, r14
0x180010e0a  jnz     short loc_180010DED
0x180010e0c  mov     rcx, qword ptr [rbp+3Fh+var_90]
0x180010e10  cmp     qword ptr [rbp+3Fh+var_40+8], 7
0x180010e15  lea     r8, [rbp+3Fh+var_50]
0x180010e19  mov     r10, qword ptr [rbp+3Fh+var_A0+8]
0x180010e1d  lea     rsi, [rbp+3Fh+var_B0]
0x180010e21  cmova   r8, qword ptr [rbp+3Fh+var_50]
0x180010e26  cmp     r10, 7
0x180010e2a  mov     rdx, qword ptr [rbp+3Fh+var_B0]
0x180010e2e  mov     r9, qword ptr [rbp+3Fh+var_40]
0x180010e32  cmova   rsi, rdx
0x180010e36  mov     rax, qword ptr [rbp+3Fh+var_A0]
0x180010e3a  mov     [rdi+38h], r15b
0x180010e3e  mov     [rdi+28h], r15
0x180010e42  mov     [rdi+30h], r15
0x180010e46  cmp     r9, rax
0x180010e49  ja      short loc_180010E88
0x180010e4b  test    r9, r9
0x180010e4e  jz      loc_180010F78
0x180010e54  lea     rbx, [rsi+rax*2]
0x180010e58  mov     rcx, rsi
0x180010e5b  mov     rdx, rbx
0x180010e5e  call    __std_search_2
0x180010e63  cmp     rax, rbx
0x180010e66  jz      short loc_180010E78
0x180010e68  sub     rax, rsi
0x180010e6b  sar     rax, 1
0x180010e6e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010e72  jnz     loc_180010F78
0x180010e78  mov     r10, qword ptr [rbp+3Fh+var_A0+8]
0x180010e7c  mov     rax, qword ptr [rbp+3Fh+var_A0]
0x180010e80  mov     rdx, qword ptr [rbp+3Fh+var_B0]
0x180010e84  mov     rcx, qword ptr [rbp+3Fh+var_90]
0x180010e88  cmp     qword ptr [rbp+3Fh+var_60+8], 7
0x180010e8d  lea     r8, [rbp+3Fh+var_70]
0x180010e91  mov     r9, qword ptr [rbp+3Fh+var_60]
0x180010e95  lea     rsi, [rbp+3Fh+var_B0]
0x180010e99  cmova   r8, qword ptr [rbp+3Fh+var_70]
0x180010e9e  cmp     r10, 7
0x180010ea2  cmova   rsi, rdx
0x180010ea6  cmp     r9, rax
0x180010ea9  ja      short loc_180010EE8
0x180010eab  test    r9, r9
0x180010eae  jz      loc_180010F96
0x180010eb4  lea     rbx, [rsi+rax*2]
0x180010eb8  mov     rcx, rsi
0x180010ebb  mov     rdx, rbx
0x180010ebe  call    __std_search_2
0x180010ec3  cmp     rax, rbx
0x180010ec6  jz      short loc_180010ED8
0x180010ec8  sub     rax, rsi
0x180010ecb  sar     rax, 1
0x180010ece  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010ed2  jnz     loc_180010F96
0x180010ed8  mov     r10, qword ptr [rbp+3Fh+var_A0+8]
0x180010edc  mov     rax, qword ptr [rbp+3Fh+var_A0]
0x180010ee0  mov     rdx, qword ptr [rbp+3Fh+var_B0]
0x180010ee4  mov     rcx, qword ptr [rbp+3Fh+var_90]
0x180010ee8  cmp     qword ptr [rbp+3Fh+var_80+8], 7
0x180010eed  lea     r8, [rbp+3Fh+var_90]
0x180010ef1  mov     r9, qword ptr [rbp+3Fh+var_80]
0x180010ef5  lea     rsi, [rbp+3Fh+var_B0]
0x180010ef9  cmova   r8, rcx
0x180010efd  cmp     r10, 7
0x180010f01  cmova   rsi, rdx
0x180010f05  cmp     r9, rax
0x180010f08  ja      loc_180010FB0
0x180010f0e  test    r9, r9
0x180010f11  jz      short loc_180010F37
0x180010f13  lea     rbx, [rsi+rax*2]
0x180010f17  mov     rcx, rsi
0x180010f1a  mov     rdx, rbx
0x180010f1d  call    __std_search_2
0x180010f22  cmp     rax, rbx
0x180010f25  jz      loc_180010FB0
0x180010f2b  sub     rax, rsi
0x180010f2e  sar     rax, 1
0x180010f31  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010f35  jz      short loc_180010FB0
0x180010f37  mov     [rdi+38h], r15b
0x180010f3b  call    ?Current@MidiDeviceTable@@SAAEAV1@XZ; MidiDeviceTable::Current(void)
0x180010f40  mov     [rdi+28h], rax
0x180010f44  lea     rcx, [rdi+8]
0x180010f48  mov     [rax+10h], rcx
0x180010f4c  mov     [rax+18h], r15
0x180010f50  lea     rcx, [rbp+3Fh+var_90]
0x180010f54  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010f59  lea     rcx, [rbp+3Fh+var_70]
0x180010f5d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010f62  lea     rcx, [rbp+3Fh+var_50]
0x180010f66  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010f6b  lea     rcx, [rbp+3Fh+var_B0]
0x180010f6f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010f74  xor     eax, eax
0x180010f76  jmp     short loc_180010FD9
0x180010f78  mov     byte ptr [rdi+39h], 1
0x180010f7c  call    ?Current@MidiDeviceTable@@SAAEAV1@XZ; MidiDeviceTable::Current(void)
0x180010f81  lea     rcx, [rax+20h]
0x180010f85  mov     [rdi+30h], rcx
0x180010f89  lea     rax, [rdi+8]
0x180010f8d  mov     [rcx], rax
0x180010f90  mov     [rcx+8], r15
0x180010f94  jmp     short loc_180010F50
0x180010f96  mov     byte ptr [rdi+38h], 1
0x180010f9a  call    ?Current@MidiDeviceTable@@SAAEAV1@XZ; MidiDeviceTable::Current(void)
0x180010f9f  mov     [rdi+28h], rax
0x180010fa3  lea     rcx, [rdi+8]
0x180010fa7  mov     [rax], rcx
0x180010faa  mov     [rax+8], r15
0x180010fae  jmp     short loc_180010F50
0x180010fb0  lea     rcx, [rbp+3Fh+var_90]
0x180010fb4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010fb9  lea     rcx, [rbp+3Fh+var_70]
0x180010fbd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010fc2  lea     rcx, [rbp+3Fh+var_50]
0x180010fc6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010fcb  lea     rcx, [rbp+3Fh+var_B0]
0x180010fcf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010fd4  mov     eax, 80004005h
0x180010fd9  mov     rcx, [rbp+3Fh+var_30]
0x180010fdd  xor     rcx, rsp; StackCookie
0x180010fe0  call    __security_check_cookie
0x180010fe5  mov     rbx, [rsp+0F0h+arg_18]
0x180010fed  add     rsp, 0D0h
0x180010ff4  pop     r15
0x180010ff6  pop     r14
  ... truncated ...
```
