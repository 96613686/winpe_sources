# CMidiSessionTracker::AddClientEndpointConnection(_GUID,ulong,ushort const *,unsigned __int64)

- ea: `0x1400399d0`
- end: `0x140039d50`
- name: `?AddClientEndpointConnection@CMidiSessionTracker@@UEAAJU_GUID@@KPEBG_K@Z`
- size: `896`
- prototype: `__int64 __fastcall(const char **this, struct _GUID *, unsigned int, const unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task`

## callees

- `0x14000179c`
- `0x140003400`
- `0x1400054c0`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x1400125a0`
- `0x140013a38`
- `0x14001dccc`
- `0x14001f95c`
- `0x14002308c`
- `0x1400360c8`
- `0x1400397bc`
- `0x1400399d0`
- `0x14003a5e0`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x140039af7`
- `msvcp_win!_Xtime_get_ticks` at `0x140039af7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140039c08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140039d13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140039c08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140039d13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140039b08`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140039b08`

## string_xrefs

- `0x140039cf2`: `avcore\midi2\service\exe\midisessiontracker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CMidiSessionTracker::AddClientEndpointConnection(
        const char **this,
        struct _GUID *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned __int64 a5)
{
  _DWORD *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rsi
  unsigned __int64 v13; // r8
  __int64 v14; // rax
  struct _RTL_CRITICAL_SECTION *v15; // r14
  const char *v16; // rbx
  _QWORD *v17; // rsi
  __int64 v18; // rdi
  const wchar_t *v19; // rdx
  size_t v20; // r15
  const wchar_t *v21; // rcx
  size_t v22; // r12
  size_t v23; // r8
  int v24; // eax
  __int64 v25; // rdi
  _QWORD *v26; // rdx
  _DWORD *v28; // rcx
  int v29; // esi
  int v30; // [rsp+20h] [rbp-E0h]
  unsigned int v31; // [rsp+50h] [rbp-B0h] BYREF
  const char *v32; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v33; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID *v34; // [rsp+68h] [rbp-98h] BYREF
  char v35[32]; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v36; // [rsp+90h] [rbp-70h] BYREF
  __int128 v37; // [rsp+A0h] [rbp-60h]
  wchar_t *S1[2]; // [rsp+B0h] [rbp-50h] BYREF
  size_t v39; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v40; // [rsp+C8h] [rbp-38h]
  _OWORD v41[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 ticks; // [rsp+F0h] [rbp-10h]
  __int16 v43; // [rsp+F8h] [rbp-8h]
  const char *v44; // [rsp+120h] [rbp+20h]
  __int64 v45; // [rsp+128h] [rbp+28h]
  const char **v46; // [rsp+130h] [rbp+30h]
  __int64 v47; // [rsp+138h] [rbp+38h]
  struct _GUID *v48; // [rsp+140h] [rbp+40h]
  __int64 v49; // [rsp+148h] [rbp+48h]
  int *v50; // [rsp+150h] [rbp+50h]
  __int64 v51; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v52; // [rsp+160h] [rbp+60h]
  int v53; // [rsp+168h] [rbp+68h]
  int v54; // [rsp+16Ch] [rbp+6Ch]
  const wchar_t *v55; // [rsp+170h] [rbp+70h]
  __int64 v56; // [rsp+178h] [rbp+78h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v9 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v9 > 4u )
  {
    v32 = "CMidiSessionTracker::AddClientEndpointConnection";
    v33 = a4;
    v31 = a3;
    v34 = a2;
    *(_QWORD *)&v36.Data1 = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (__int64)v9,
      (__int64)byte_14008AF85,
      v10,
      v11,
      &v32,
      (__int64)&v36,
      (__int64)&v34,
      (__int64)&v31,
      &v33);
  }
  ticks = 0;
  v41[1] = _mm_load_si128((const __m128i *)&_xmm);
  v12 = -1;
  v41[0] = 0;
  v43 = 1;
  v13 = -1;
  LOWORD(v41[0]) = 0;
  v36 = 0;
  v37 = 0;
  do
    ++v13;
  while ( a4[v13] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v36, a4, v13);
  v14 = std::wstring::wstring((__int64)v35, (__int64)&v36);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(S1, v14);
  std::wstring::~wstring((char **)&v36);
  std::wstring::operator=(v41, S1);
  v43 = 1;
  v15 = (struct _RTL_CRITICAL_SECTION *)(this + 6);
  ticks = _Xtime_get_ticks();
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 6));
  v36 = *a2;
  CMidiSessionTracker::FindSession(this, &v32, &v36, a3);
  v16 = v32;
  if ( v32 != this[4] )
  {
    v17 = v32 + 104;
    std::_Tree<std::_Tmap_traits<std::wstring,MidiSessionConnectionEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiSessionConnectionEntry>>,0>>::_Find_lower_bound<std::wstring>(
      v32 + 104,
      &v36,
      S1);
    v18 = v37;
    if ( !*(_BYTE *)(v37 + 25) )
    {
      v19 = (const wchar_t *)(v37 + 32);
      v20 = *(_QWORD *)(v37 + 48);
      if ( *(_QWORD *)(v37 + 56) > 7u )
        v19 = *(const wchar_t **)v19;
      v21 = (const wchar_t *)S1;
      v22 = v39;
      if ( v40 > 7 )
        v21 = S1[0];
      v23 = v39;
      if ( v20 < v39 )
        v23 = *(_QWORD *)(v37 + 48);
      v24 = wmemcmp(v21, v19, v23);
      if ( v24 )
      {
        if ( v24 < 0 )
          goto LABEL_15;
      }
      else if ( v22 < v20 )
      {
        goto LABEL_15;
      }
      if ( v18 != *v17 )
      {
        ++*(_WORD *)(v18 + 104);
        goto LABEL_16;
      }
    }
LABEL_15:
    v25 = std::map<std::wstring,MidiSessionConnectionEntry>::operator[](v16 + 104, S1);
    std::wstring::operator=(v25, v41);
    *(_QWORD *)(v25 + 32) = ticks;
    *(_WORD *)(v25 + 40) = v43;
LABEL_16:
    v26 = (_QWORD *)*((_QWORD *)v16 + 16);
    if ( v26 == *((_QWORD **)v16 + 17) )
    {
      std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(v16 + 120, v26, &a5);
    }
    else
    {
      *v26 = a5;
      *((_QWORD *)v16 + 16) += 8LL;
    }
    if ( v15 )
      LeaveCriticalSection(v15);
    std::wstring::~wstring((char **)S1);
    std::wstring::~wstring((char **)v41);
    return 0;
  }
  v28 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v28 > 4u )
  {
    v31 = a3;
    v32 = (const char *)this;
    v55 = L"No valid session found. Returning E_NOTFOUND.";
    v56 = 92;
    if ( a4 )
    {
      do
        ++v12;
      while ( a4[v12] );
      v29 = 2 * v12 + 2;
    }
    else
    {
      a4 = &S2;
      v29 = 2;
    }
    v54 = 0;
    v50 = (int *)&v31;
    v52 = a4;
    v46 = &v32;
    v53 = v29;
    v44 = "CMidiSessionTracker::AddClientEndpointConnection";
    v51 = 4;
    v30 = 8;
    v48 = a2;
    v49 = 16;
    v47 = 8;
    v45 = 49;
    tlgWriteTransfer_EventWriteTransfer(v28, &dword_14008B044, 0, 0);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1F2,
    (unsigned int)"avcore\\midi2\\service\\exe\\midisessiontracker.cpp",
    (const char *)0x80070490LL,
    v30);
  if ( this != (const char **)-48LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)(this + 6));
  std::wstring::~wstring((char **)S1);
  std::wstring::~wstring((char **)v41);
  return 2147943568LL;
}

```

## disassembly

```asm
0x1400399d0  push    rbp
0x1400399d2  push    rbx
0x1400399d3  push    rsi
0x1400399d4  push    rdi
0x1400399d5  push    r12
0x1400399d7  push    r13
0x1400399d9  push    r14
0x1400399db  push    r15
0x1400399dd  lea     rbp, [rsp-98h]
0x1400399e5  sub     rsp, 198h
0x1400399ec  mov     rax, cs:__security_cookie
0x1400399f3  xor     rax, rsp
0x1400399f6  mov     [rbp+0D0h+var_50], rax
0x1400399fd  mov     rdi, r9
0x140039a00  mov     r12d, r8d
0x140039a03  mov     r13, rdx
0x140039a06  mov     r15, rcx
0x140039a09  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140039a0e  lea     rdx, aCmidisessiontr_6; "CMidiSessionTracker::AddClientEndpointC"...
0x140039a15  mov     rcx, [rax+8]
0x140039a19  mov     eax, [rcx]
0x140039a1b  cmp     eax, 4
0x140039a1e  jbe     short loc_140039A75
0x140039a20  lea     rax, [rsp+1D0h+var_170]
0x140039a25  mov     [rsp+1D0h+var_178], rdx
0x140039a2a  mov     [rsp+1D0h+var_190], rax
0x140039a2f  lea     rdx, byte_14008AF85
0x140039a36  lea     rax, [rsp+1D0h+var_180]
0x140039a3b  mov     [rsp+1D0h+var_170], rdi
0x140039a40  mov     [rsp+1D0h+var_198], rax
0x140039a45  lea     rax, [rsp+1D0h+var_168]
0x140039a4a  mov     [rsp+1D0h+var_1A0], rax
0x140039a4f  lea     rax, [rbp+0D0h+var_140]
0x140039a53  mov     [rsp+1D0h+var_1A8], rax
0x140039a58  lea     rax, [rsp+1D0h+var_178]
0x140039a5d  mov     qword ptr [rsp+1D0h+var_1B0], rax
0x140039a62  mov     [rsp+1D0h+var_180], r12d
0x140039a67  mov     [rsp+1D0h+var_168], r13
0x140039a6c  mov     qword ptr [rbp+0D0h+var_140], r15
0x140039a70  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x140039a75  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140039a7d  xor     ecx, ecx
0x140039a7f  xorps   xmm0, xmm0
0x140039a82  mov     [rbp+0D0h+var_E0], rcx
0x140039a86  movdqu  [rbp+0D0h+var_F0], xmm1
0x140039a8b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140039a8f  lea     ebx, [rcx+1]
0x140039a92  xorps   xmm1, xmm1
0x140039a95  movups  [rbp+0D0h+var_100], xmm0
0x140039a99  mov     [rbp+0D0h+var_D8], bx
0x140039a9d  mov     r8, rsi
0x140039aa0  mov     word ptr [rbp+0D0h+var_100], cx
0x140039aa4  movups  [rbp+0D0h+var_140], xmm0
0x140039aa8  movdqu  [rbp+0D0h+var_130], xmm1
0x140039aad  inc     r8
0x140039ab0  cmp     [rdi+r8*2], cx
0x140039ab5  jnz     short loc_140039AAD
0x140039ab7  mov     rdx, rdi
0x140039aba  lea     rcx, [rbp+0D0h+var_140]
0x140039abe  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140039ac3  lea     rdx, [rbp+0D0h+var_140]
0x140039ac7  lea     rcx, [rsp+1D0h+var_160]
0x140039acc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140039ad1  mov     rdx, rax
0x140039ad4  lea     rcx, [rbp+0D0h+S1]
0x140039ad8  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x140039add  lea     rcx, [rbp+0D0h+var_140]; void *
0x140039ae1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140039ae6  lea     rdx, [rbp+0D0h+S1]
0x140039aea  lea     rcx, [rbp+0D0h+var_100]
0x140039aee  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140039af3  mov     [rbp+0D0h+var_D8], bx
0x140039af7  call    cs:__imp__Xtime_get_ticks
0x140039afd  lea     r14, [r15+30h]
0x140039b01  mov     [rbp+0D0h+var_E0], rax
0x140039b05  mov     rcx, r14; lpCriticalSection
0x140039b08  call    cs:__imp_EnterCriticalSection
0x140039b0e  movups  xmm0, xmmword ptr [r13+0]
0x140039b13  mov     r9d, r12d
0x140039b16  lea     r8, [rbp+0D0h+var_140]
0x140039b1a  lea     rdx, [rsp+1D0h+var_178]
0x140039b1f  mov     rcx, r15
0x140039b22  movdqu  [rbp+0D0h+var_140], xmm0
0x140039b27  call    ?FindSession@CMidiSessionTracker@@AEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UMidiSessionEntry@@@std@@@std@@@std@@U_GUID@@K@Z; CMidiSessionTracker::FindSession(_GUID,ulong)
0x140039b2c  mov     rbx, [rsp+1D0h+var_178]
0x140039b31  cmp     rbx, [r15+20h]
0x140039b35  jz      loc_140039C27
0x140039b3b  lea     rsi, [rbx+68h]
0x140039b3f  mov     rcx, rsi
0x140039b42  lea     r8, [rbp+0D0h+S1]
0x140039b46  lea     rdx, [rbp+0D0h+var_140]
0x140039b4a  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,MidiSessionConnectionEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiSessionConnectionEntry>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x140039b4f  mov     rdi, qword ptr [rbp+0D0h+var_130]
0x140039b53  xor     r13d, r13d
0x140039b56  cmp     [rdi+19h], r13b
0x140039b5a  jnz     short loc_140039B98
0x140039b5c  lea     rdx, [rdi+20h]
0x140039b60  cmp     qword ptr [rdx+18h], 7
0x140039b65  mov     r15, [rdx+10h]
0x140039b69  jbe     short loc_140039B6E
0x140039b6b  mov     rdx, [rdx]; S2
0x140039b6e  cmp     [rbp+0D0h+var_108], 7
0x140039b73  lea     rcx, [rbp+0D0h+S1]
0x140039b77  mov     r12, [rbp+0D0h+var_110]
0x140039b7b  cmova   rcx, [rbp+0D0h+S1]; S1
0x140039b80  mov     r8, r12
0x140039b83  cmp     r15, r12
0x140039b86  cmovb   r8, r15; N
0x140039b8a  call    wmemcmp
0x140039b8f  test    eax, eax
0x140039b91  jnz     short loc_140039BE2
0x140039b93  cmp     r12, r15
0x140039b96  jnb     short loc_140039BE4
0x140039b98  lea     rdx, [rbp+0D0h+S1]
0x140039b9c  mov     rcx, rsi
0x140039b9f  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@@std@@@2@@std@@QEAAAEAUMidiSessionConnectionEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,MidiSessionConnectionEntry>::operator[](std::wstring const &)
0x140039ba4  lea     rdx, [rbp+0D0h+var_100]
0x140039ba8  mov     rcx, rax
0x140039bab  mov     rdi, rax
0x140039bae  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140039bb3  mov     rcx, [rbp+0D0h+var_E0]
0x140039bb7  mov     [rdi+20h], rcx
0x140039bbb  movzx   ecx, [rbp+0D0h+var_D8]
0x140039bbf  mov     [rdi+28h], cx
0x140039bc3  lea     rcx, [rbx+78h]
0x140039bc7  mov     rdx, [rcx+8]
0x140039bcb  cmp     rdx, [rcx+10h]
0x140039bcf  jz      short loc_140039BF4
0x140039bd1  mov     rax, [rbp+0D0h+arg_20]
0x140039bd8  mov     [rdx], rax
0x140039bdb  add     qword ptr [rcx+8], 8
0x140039be0  jmp     short loc_140039C00
0x140039be2  js      short loc_140039B98
0x140039be4  cmp     rdi, [rsi]
0x140039be7  jz      short loc_140039B98
0x140039be9  mov     eax, 1
0x140039bee  add     [rdi+68h], ax
0x140039bf2  jmp     short loc_140039BC3
0x140039bf4  lea     r8, [rbp+0D0h+arg_20]
0x140039bfb  call    ??$_Emplace_reallocate@AEB_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAPEA_KQEA_KAEB_K@Z; std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(unsigned __int64 * const,unsigned __int64 const &)
0x140039c00  test    r14, r14
0x140039c03  jz      short loc_140039C0E
0x140039c05  mov     rcx, r14; lpCriticalSection
0x140039c08  call    cs:__imp_LeaveCriticalSection
0x140039c0e  lea     rcx, [rbp+0D0h+S1]; void *
0x140039c12  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140039c17  lea     rcx, [rbp+0D0h+var_100]; void *
0x140039c1b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140039c20  xor     eax, eax
0x140039c22  jmp     loc_140039D2D
0x140039c27  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140039c2c  mov     rcx, [rax+8]
0x140039c30  mov     eax, [rcx]
0x140039c32  cmp     eax, 4
0x140039c35  jbe     loc_140039CEB
0x140039c3b  xor     edx, edx
0x140039c3d  mov     [rsp+1D0h+var_180], r12d
0x140039c42  mov     [rsp+1D0h+var_178], r15
0x140039c47  lea     rax, aNoValidSession; "No valid session found. Returning E_NOT"...
0x140039c4e  mov     [rbp+0D0h+var_60], rax
0x140039c52  mov     [rbp+0D0h+var_58], 5Ch ; '\'
0x140039c5a  test    rdi, rdi
0x140039c5d  jz      short loc_140039C71
0x140039c5f  inc     rsi
0x140039c62  cmp     [rdi+rsi*2], dx
0x140039c66  jnz     short loc_140039C5F
0x140039c68  lea     esi, ds:2[rsi*2]
0x140039c6f  jmp     short loc_140039C7D
0x140039c71  lea     rdi, S2
0x140039c78  mov     esi, 2
0x140039c7d  lea     rax, [rsp+1D0h+var_180]
0x140039c82  mov     [rbp+0D0h+var_64], edx
0x140039c85  mov     [rbp+0D0h+var_80], rax
0x140039c89  lea     rdx, dword_14008B044
0x140039c90  lea     rax, [rsp+1D0h+var_178]
0x140039c95  mov     [rbp+0D0h+var_70], rdi
0x140039c99  mov     [rbp+0D0h+var_A0], rax
0x140039c9d  xor     r9d, r9d
0x140039ca0  lea     rax, aCmidisessiontr_6; "CMidiSessionTracker::AddClientEndpointC"...
0x140039ca7  mov     [rbp+0D0h+var_68], esi
0x140039caa  mov     [rbp+0D0h+var_B0], rax
0x140039cae  xor     r8d, r8d
0x140039cb1  lea     rax, [rbp+0D0h+var_D0]
0x140039cb5  mov     [rbp+0D0h+var_78], 4
0x140039cbd  mov     [rsp+1D0h+var_1A8], rax
0x140039cc2  mov     [rsp+1D0h+var_1B0], 8; int
0x140039cca  mov     [rbp+0D0h+var_90], r13
0x140039cce  mov     [rbp+0D0h+var_88], 10h
0x140039cd6  mov     [rbp+0D0h+var_98], 8
0x140039cde  mov     [rbp+0D0h+var_A8], 31h ; '1'
0x140039ce6  call    _tlgWriteTransfer_EventWriteTransfer
0x140039ceb  mov     rcx, [rbp+0D8h]; this
0x140039cf2  lea     r8, aAvcoreMidi2Ser_5; "avcore\\midi2\\service\\exe\\midisessio"...
0x140039cf9  mov     ebx, 80070490h
0x140039cfe  mov     edx, 1F2h; void *
0x140039d03  mov     r9d, ebx; char *
0x140039d06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140039d0b  test    r14, r14
0x140039d0e  jz      short loc_140039D19
0x140039d10  mov     rcx, r14; lpCriticalSection
0x140039d13  call    cs:__imp_LeaveCriticalSection
0x140039d19  lea     rcx, [rbp+0D0h+S1]; void *
0x140039d1d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140039d22  lea     rcx, [rbp+0D0h+var_100]; void *
0x140039d26  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140039d2b  mov     eax, ebx
0x140039d2d  mov     rcx, [rbp+0D0h+var_50]
0x140039d34  xor     rcx, rsp; StackCookie
0x140039d37  call    __security_check_cookie
0x140039d3c  add     rsp, 198h
0x140039d43  pop     r15
0x140039d45  pop     r14
0x140039d47  pop     r13
0x140039d49  pop     r12
0x140039d4b  pop     rdi
0x140039d4c  pop     rsi
0x140039d4d  pop     rbx
0x140039d4e  pop     rbp
0x140039d4f  retn
```
