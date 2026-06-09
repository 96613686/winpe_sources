# CMidiDeviceManager::DeactivateVirtualParentDevice(ushort const *)

- ea: `0x14002e720`
- end: `0x14002ebe3`
- name: `?DeactivateVirtualParentDevice@CMidiDeviceManager@@UEAAJPEBG@Z`
- size: `1219`
- prototype: `__int64 __fastcall(CMidiDeviceManager *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, service_task`

## callees

- `0x140001ce8`
- `0x14000298c`
- `0x1400054c0`
- `0x140005868`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000e1f8`
- `0x140013a38`
- `0x14001dccc`
- `0x14001f95c`
- `0x140027660`
- `0x140028d00`
- `0x14002e720`
- `0x14003481c`
- `0x14005a010`

## string_xrefs

- `0x14002e7cc`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002e83f`: `avcore\midi2\service\exe\mididevicemanager.cpp`

## pseudocode

```c
__int64 __fastcall CMidiDeviceManager::DeactivateVirtualParentDevice(CMidiDeviceManager *this, unsigned __int16 *a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // ebx
  unsigned __int64 v8; // r8
  __int64 v9; // rax
  __m128i si128; // xmm6
  char i; // r12
  _QWORD *v12; // rdi
  _QWORD *v13; // r14
  __int64 v14; // rax
  const wchar_t *v15; // rdx
  const wchar_t *v16; // rcx
  bool v17; // si
  _DWORD *v18; // r8
  __int64 v19; // r9
  _MIDIPARENTDEVICE *v20; // rax
  __int64 v21; // rcx
  wchar_t **v22; // rax
  _MIDIPARENTDEVICE *v23; // rax
  unsigned __int64 v24; // r8
  _WORD *v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 *v28; // r12
  __int64 *j; // rsi
  __int64 v30; // rax
  _MIDIPARENTDEVICE *v31; // r14
  __int64 v32; // rax
  void *v33; // rdi
  struct MidiSrvTelemetryProvider *v34; // rax
  __int64 v35; // r8
  __int64 v36; // r9
  const unsigned __int16 *v37; // r15
  _DWORD *v38; // rcx
  wchar_t **v39; // rax
  _DWORD *v40; // rcx
  __int64 v41; // r8
  __int64 v42; // r9
  wchar_t **v43; // rax
  int v45; // [rsp+28h] [rbp-E0h]
  const char *v46; // [rsp+58h] [rbp-B0h] BYREF
  int v47[2]; // [rsp+60h] [rbp-A8h] BYREF
  const wchar_t *v48; // [rsp+68h] [rbp-A0h] BYREF
  const unsigned __int16 *v49; // [rsp+70h] [rbp-98h] BYREF
  CMidiDeviceManager *v50; // [rsp+78h] [rbp-90h] BYREF
  const wchar_t *v51; // [rsp+80h] [rbp-88h] BYREF
  __int128 v52; // [rsp+88h] [rbp-80h] BYREF
  __int64 v53; // [rsp+98h] [rbp-70h]
  char v54[32]; // [rsp+A0h] [rbp-68h] BYREF
  wchar_t *S1[2]; // [rsp+C0h] [rbp-48h] BYREF
  __m128i v56; // [rsp+D0h] [rbp-38h]
  wchar_t *S2[2]; // [rsp+E0h] [rbp-28h] BYREF
  size_t N; // [rsp+F0h] [rbp-18h]
  unsigned __int64 v59; // [rsp+F8h] [rbp-10h]
  _OWORD v60[2]; // [rsp+100h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+170h] [rbp+68h]

  v49 = a2;
  v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    v51 = L"Exit success";
    v50 = (CMidiDeviceManager *)a2;
    v46 = (const char *)this;
    *(_QWORD *)v47 = "CMidiDeviceManager::DeactivateVirtualParentDevice";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)&byte_140089AC7,
      v5,
      v6,
      v47,
      (__int64)&v46,
      &v51,
      &v50);
  }
  if ( a2 )
  {
    *(_OWORD *)S1 = 0;
    v8 = -1;
    v56 = 0;
    do
      ++v8;
    while ( a2[v8] );
    std::wstring::_Construct<1,unsigned short const *>((char **)S1, a2, v8);
    v9 = std::wstring::wstring((__int64)v60, (__int64)S1);
    WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(S2, v9);
    std::wstring::~wstring((char **)S1);
    if ( N )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v53 = 0;
      v52 = 0;
      for ( i = 0; ; i = 1 )
      {
        v12 = (_QWORD *)*((_QWORD *)this + 21);
        v13 = (_QWORD *)*((_QWORD *)this + 22);
        while ( v12 != v13 )
        {
          v14 = std::wstring::wstring((__int64)v60, *v12 + 32LL);
          WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(S1, v14);
          v15 = (const wchar_t *)S2;
          v16 = (const wchar_t *)S1;
          if ( v59 > 7 )
            v15 = S2[0];
          if ( v56.m128i_i64[1] > 7uLL )
            v16 = S1[0];
          v17 = v56.m128i_i64[0] >= N && wmemcmp(v16, v15, N) == 0;
          std::wstring::~wstring((char **)S1);
          if ( v17 )
            break;
          ++v12;
        }
        if ( v12 == *((_QWORD **)this + 22) )
          break;
        v18 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
        if ( *v18 > 4u )
        {
          v20 = (_MIDIPARENTDEVICE *)*v12;
          v48 = (const wchar_t *)"CMidiDeviceManager::DeactivateVirtualParentDevice";
          v21 = *((_QWORD *)v20 + 3);
          v22 = S2;
          if ( v59 > 7 )
            v22 = (wchar_t **)S2[0];
          v46 = (const char *)v22;
          v51 = L"Found instance id in ports list. Erasing";
          *(_QWORD *)v47 = v21;
          v50 = this;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (__int64)v18,
            (__int64)&byte_1400894CF,
            (__int64)v18,
            v19,
            &v48,
            (__int64)&v50,
            &v51,
            &v46,
            v47);
        }
        v23 = (_MIDIPARENTDEVICE *)*v12;
        v24 = -1;
        memset(v60, 0, sizeof(v60));
        v25 = (_WORD *)*((_QWORD *)v23 + 3);
        do
          ++v24;
        while ( v25[v24] );
        std::wstring::_Construct<1,unsigned short const *>((char **)v60, v25, v24);
        v26 = std::wstring::wstring((__int64)v54, (__int64)v60);
        WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(S1, v26);
        v27 = *((_QWORD *)&v52 + 1);
        if ( *((_QWORD *)&v52 + 1) == v53 )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v52, *((_QWORD *)&v52 + 1), S1);
        }
        else
        {
          **((_OWORD **)&v52 + 1) = 0;
          *(_QWORD *)(v27 + 16) = 0;
          *(_QWORD *)(v27 + 24) = 0;
          *(_OWORD *)v27 = *(_OWORD *)S1;
          *(__m128i *)(v27 + 16) = v56;
          *((_QWORD *)&v52 + 1) += 32LL;
          v56 = si128;
          LOWORD(S1[0]) = 0;
        }
        std::wstring::~wstring((char **)S1);
        std::wstring::~wstring((char **)v60);
        v28 = (__int64 *)*((_QWORD *)this + 22);
        for ( j = v12 + 1; j != v28; ++j )
        {
          v30 = *j;
          *j = 0;
          v31 = (_MIDIPARENTDEVICE *)*v12;
          *v12 = v30;
          if ( v31 )
          {
            _MIDIPARENTDEVICE::~_MIDIPARENTDEVICE(v31);
            operator delete(v31);
          }
          ++v12;
        }
        v32 = *((_QWORD *)this + 22);
        v33 = *(void **)(v32 - 8);
        if ( v33 )
        {
          _MIDIPARENTDEVICE::~_MIDIPARENTDEVICE(*(_MIDIPARENTDEVICE **)(v32 - 8));
          operator delete(v33);
        }
        *((_QWORD *)this + 22) -= 8LL;
      }
      v34 = MidiSrvTelemetryProvider::Instance();
      v37 = v49;
      v38 = (_DWORD *)*((_QWORD *)v34 + 1);
      if ( *v38 > 4u )
      {
        v39 = S2;
        *(_QWORD *)v47 = this;
        if ( v59 > 7 )
          v39 = (wchar_t **)S2[0];
        v49 = (const unsigned __int16 *)v39;
        v48 = L"Found no more matches in list. Breaking out of loop";
        v46 = "CMidiDeviceManager::DeactivateVirtualParentDevice";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (__int64)v38,
          (__int64)byte_14008A27B,
          v35,
          v36,
          &v46,
          (__int64)v47,
          &v48,
          &v49);
      }
      if ( i )
        (*(void (__fastcall **)(CMidiDeviceManager *, const unsigned __int16 *))(*(_QWORD *)this + 64LL))(this, v37);
      v40 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v40 > 4u )
      {
        v43 = S2;
        *(_QWORD *)v47 = this;
        if ( v59 > 7 )
          v43 = (wchar_t **)S2[0];
        v49 = (const unsigned __int16 *)v43;
        v48 = L"Exit success";
        v46 = "CMidiDeviceManager::DeactivateVirtualParentDevice";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (__int64)v40,
          (__int64)&byte_14008981F,
          v41,
          v42,
          &v46,
          (__int64)v47,
          &v48,
          &v49);
      }
      std::vector<std::wstring>::~vector<std::wstring>(&v52);
      v7 = 0;
    }
    else
    {
      v7 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x238,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)0x80070057LL,
        v45);
    }
    std::wstring::~wstring((char **)S2);
  }
  else
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x235,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
      (const char *)0x80070057LL,
      v45);
  }
  return v7;
}

```

## disassembly

```asm
0x14002e720  mov     rax, rsp
0x14002e723  mov     [rax+18h], rbx
0x14002e727  push    rbp
0x14002e728  push    rsi
0x14002e729  push    rdi
0x14002e72a  push    r12
0x14002e72c  push    r13
0x14002e72e  push    r14
0x14002e730  push    r15
0x14002e732  lea     rbp, [rax-68h]
0x14002e736  sub     rsp, 130h
0x14002e73d  movaps  xmmword ptr [rax-48h], xmm6
0x14002e741  mov     rax, cs:__security_cookie
0x14002e748  xor     rax, rsp
0x14002e74b  mov     [rbp+60h+var_48], rax
0x14002e74f  mov     r15, rdx
0x14002e752  mov     [rsp+160h+var_F8], rdx
0x14002e757  mov     rbx, rcx
0x14002e75a  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14002e75f  lea     rdx, aExitSuccess_0; "Exit success"
0x14002e766  lea     rdi, aCmidideviceman_6; "CMidiDeviceManager::DeactivateVirtualPa"...
0x14002e76d  mov     rcx, [rax+8]
0x14002e771  mov     eax, [rcx]
0x14002e773  cmp     eax, 4
0x14002e776  jbe     short loc_14002E7C0
0x14002e778  lea     rax, [rsp+160h+var_F0]
0x14002e77d  mov     [rsp+160h+var_E8], rdx
0x14002e782  mov     [rsp+160h+var_128], rax
0x14002e787  lea     rdx, byte_140089AC7
0x14002e78e  lea     rax, [rsp+160h+var_E8]
0x14002e793  mov     [rsp+160h+var_F0], r15
0x14002e798  mov     [rsp+160h+var_130], rax
0x14002e79d  lea     rax, [rsp+160h+var_110]
0x14002e7a2  mov     [rsp+160h+var_138], rax
0x14002e7a7  lea     rax, [rsp+160h+var_108]
0x14002e7ac  mov     qword ptr [rsp+160h+var_140], rax; int
0x14002e7b1  mov     [rsp+160h+var_110], rbx
0x14002e7b6  mov     qword ptr [rsp+160h+var_108], rdi
0x14002e7bb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14002e7c0  xor     r13d, r13d
0x14002e7c3  test    r15, r15
0x14002e7c6  jnz     short loc_14002E7EA
0x14002e7c8  mov     rcx, [rbp+68h]; this
0x14002e7cc  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x14002e7d3  mov     ebx, 80070057h
0x14002e7d8  mov     edx, 235h; void *
0x14002e7dd  mov     r9d, ebx; char *
0x14002e7e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002e7e5  jmp     loc_14002EBB5
0x14002e7ea  xorps   xmm0, xmm0
0x14002e7ed  xorps   xmm1, xmm1
0x14002e7f0  movups  xmmword ptr [rbp+60h+S1], xmm0
0x14002e7f4  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002e7f8  movdqu  [rbp+60h+var_98], xmm1
0x14002e7fd  inc     r8
0x14002e800  cmp     [r15+r8*2], r13w
0x14002e805  jnz     short loc_14002E7FD
0x14002e807  mov     rdx, r15
0x14002e80a  lea     rcx, [rbp+60h+S1]
0x14002e80e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002e813  lea     rdx, [rbp+60h+S1]
0x14002e817  lea     rcx, [rbp+60h+var_68]
0x14002e81b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002e820  mov     rdx, rax
0x14002e823  lea     rcx, [rbp+60h+S2]
0x14002e827  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x14002e82c  lea     rcx, [rbp+60h+S1]; void *
0x14002e830  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002e835  cmp     [rbp+60h+N], r13
0x14002e839  jnz     short loc_14002E85D
0x14002e83b  mov     rcx, [rbp+68h]; this
0x14002e83f  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x14002e846  mov     ebx, 80070057h
0x14002e84b  mov     edx, 238h; void *
0x14002e850  mov     r9d, ebx; char *
0x14002e853  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002e858  jmp     loc_14002EBAC
0x14002e85d  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14002e865  lea     r15, aCmidideviceman_6; "CMidiDeviceManager::DeactivateVirtualPa"...
0x14002e86c  xorps   xmm0, xmm0
0x14002e86f  mov     [rbp+60h+var_D0], r13
0x14002e873  movdqu  [rbp+60h+var_E0], xmm0
0x14002e878  mov     r12b, r13b
0x14002e87b  mov     rdi, [rbx+0A8h]
0x14002e882  mov     r14, [rbx+0B0h]
0x14002e889  jmp     short loc_14002E8EF
0x14002e88b  mov     rdx, [rdi]
0x14002e88e  lea     rcx, [rbp+60h+var_68]
0x14002e892  add     rdx, 20h ; ' '
0x14002e896  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002e89b  mov     rdx, rax
0x14002e89e  lea     rcx, [rbp+60h+S1]
0x14002e8a2  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x14002e8a7  cmp     [rbp+60h+var_70], 7
0x14002e8ac  lea     rdx, [rbp+60h+S2]
0x14002e8b0  mov     r8, [rbp+60h+N]; N
0x14002e8b4  lea     rcx, [rbp+60h+S1]
0x14002e8b8  cmova   rdx, [rbp+60h+S2]; S2
0x14002e8bd  cmp     qword ptr [rbp+60h+var_98+8], 7
0x14002e8c2  cmova   rcx, [rbp+60h+S1]; S1
0x14002e8c7  cmp     qword ptr [rbp+60h+var_98], r8
0x14002e8cb  jnb     short loc_14002E8D2
0x14002e8cd  mov     sil, r13b
0x14002e8d0  jmp     short loc_14002E8DD
0x14002e8d2  call    wmemcmp
0x14002e8d7  test    eax, eax
0x14002e8d9  setz    sil
0x14002e8dd  lea     rcx, [rbp+60h+S1]; void *
0x14002e8e1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002e8e6  test    sil, sil
0x14002e8e9  jnz     short loc_14002E8F4
0x14002e8eb  add     rdi, 8
0x14002e8ef  cmp     rdi, r14
0x14002e8f2  jnz     short loc_14002E88B
0x14002e8f4  cmp     rdi, [rbx+0B0h]
0x14002e8fb  jz      loc_14002EA9A
0x14002e901  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14002e906  mov     r8, [rax+8]
0x14002e90a  mov     eax, [r8]
0x14002e90d  cmp     eax, 4
0x14002e910  jbe     short loc_14002E988
0x14002e912  mov     rax, [rdi]
0x14002e915  lea     rdx, byte_1400894CF
0x14002e91c  cmp     [rbp+60h+var_70], 7
0x14002e921  mov     [rsp+160h+var_100], r15
0x14002e926  mov     rcx, [rax+18h]
0x14002e92a  lea     rax, [rbp+60h+S2]
0x14002e92e  cmova   rax, [rbp+60h+S2]
0x14002e933  mov     [rsp+160h+var_110], rax
0x14002e938  lea     rax, aFoundInstanceI; "Found instance id in ports list. Erasin"...
0x14002e93f  mov     [rsp+160h+var_E8], rax
0x14002e944  lea     rax, [rsp+160h+var_108]
0x14002e949  mov     [rsp+160h+var_120], rax
0x14002e94e  lea     rax, [rsp+160h+var_110]
0x14002e953  mov     [rsp+160h+var_128], rax
0x14002e958  lea     rax, [rsp+160h+var_E8]
0x14002e95d  mov     [rsp+160h+var_130], rax
0x14002e962  lea     rax, [rsp+160h+var_F0]
0x14002e967  mov     [rsp+160h+var_138], rax
0x14002e96c  lea     rax, [rsp+160h+var_100]
0x14002e971  mov     qword ptr [rsp+160h+var_108], rcx
0x14002e976  mov     rcx, r8
0x14002e979  mov     qword ptr [rsp+160h+var_140], rax
0x14002e97e  mov     [rsp+160h+var_F0], rbx
0x14002e983  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14002e988  mov     rax, [rdi]
0x14002e98b  xorps   xmm0, xmm0
0x14002e98e  xorps   xmm1, xmm1
0x14002e991  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002e995  movups  [rbp+60h+var_68], xmm0
0x14002e999  mov     rdx, [rax+18h]
0x14002e99d  movdqu  [rbp+60h+var_58], xmm1
0x14002e9a2  inc     r8
0x14002e9a5  cmp     [rdx+r8*2], r13w
0x14002e9aa  jnz     short loc_14002E9A2
0x14002e9ac  lea     rcx, [rbp+60h+var_68]
0x14002e9b0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002e9b5  lea     rdx, [rbp+60h+var_68]
0x14002e9b9  lea     rcx, [rbp+60h+var_C8]
0x14002e9bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002e9c2  mov     rdx, rax
0x14002e9c5  lea     rcx, [rbp+60h+S1]
0x14002e9c9  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x14002e9ce  mov     rdx, qword ptr [rbp+60h+var_E0+8]
0x14002e9d2  cmp     rdx, [rbp+60h+var_D0]
0x14002e9d6  jz      short loc_14002EA06
0x14002e9d8  xorps   xmm0, xmm0
0x14002e9db  movups  xmmword ptr [rdx], xmm0
0x14002e9de  mov     [rdx+10h], r13
0x14002e9e2  mov     [rdx+18h], r13
0x14002e9e6  movups  xmm0, xmmword ptr [rbp+60h+S1]
0x14002e9ea  movups  xmmword ptr [rdx], xmm0
0x14002e9ed  movups  xmm1, [rbp+60h+var_98]
0x14002e9f1  movups  xmmword ptr [rdx+10h], xmm1
0x14002e9f5  add     qword ptr [rbp+60h+var_E0+8], 20h ; ' '
0x14002e9fa  movdqu  [rbp+60h+var_98], xmm6
0x14002e9ff  mov     word ptr [rbp+60h+S1], r13w
0x14002ea04  jmp     short loc_14002EA13
0x14002ea06  lea     r8, [rbp+60h+S1]
0x14002ea0a  lea     rcx, [rbp+60h+var_E0]
0x14002ea0e  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x14002ea13  lea     rcx, [rbp+60h+S1]; void *
0x14002ea17  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002ea1c  lea     rcx, [rbp+60h+var_68]; void *
0x14002ea20  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002ea25  mov     r12, [rbx+0B0h]
0x14002ea2c  lea     rsi, [rdi+8]
0x14002ea30  jmp     short loc_14002EA60
0x14002ea32  mov     rax, [rsi]
0x14002ea35  mov     [rsi], r13
0x14002ea38  mov     r14, [rdi]
0x14002ea3b  mov     [rdi], rax
0x14002ea3e  test    r14, r14
0x14002ea41  jz      short loc_14002EA58
0x14002ea43  mov     rcx, r14; this
0x14002ea46  call    ??1_MIDIPARENTDEVICE@@QEAA@XZ; _MIDIPARENTDEVICE::~_MIDIPARENTDEVICE(void)
0x14002ea4b  mov     edx, 48h ; 'H'
0x14002ea50  mov     rcx, r14; Block
0x14002ea53  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002ea58  add     rdi, 8
0x14002ea5c  add     rsi, 8
0x14002ea60  cmp     rsi, r12
0x14002ea63  jnz     short loc_14002EA32
0x14002ea65  mov     rax, [rbx+0B0h]
0x14002ea6c  mov     rdi, [rax-8]
0x14002ea70  test    rdi, rdi
0x14002ea73  jz      short loc_14002EA8A
0x14002ea75  mov     rcx, rdi; this
0x14002ea78  call    ??1_MIDIPARENTDEVICE@@QEAA@XZ; _MIDIPARENTDEVICE::~_MIDIPARENTDEVICE(void)
0x14002ea7d  mov     edx, 48h ; 'H'
0x14002ea82  mov     rcx, rdi; Block
0x14002ea85  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002ea8a  add     qword ptr [rbx+0B0h], 0FFFFFFFFFFFFFFF8h
0x14002ea92  mov     r12b, 1
0x14002ea95  jmp     loc_14002E87B
0x14002ea9a  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14002ea9f  mov     r15, [rsp+160h+var_F8]
0x14002eaa4  mov     rcx, [rax+8]
0x14002eaa8  mov     eax, [rcx]
0x14002eaaa  cmp     eax, 4
0x14002eaad  jbe     short loc_14002EB15
0x14002eaaf  cmp     [rbp+60h+var_70], 7
0x14002eab4  lea     rax, [rbp+60h+S2]
0x14002eab8  lea     rdi, aCmidideviceman_6; "CMidiDeviceManager::DeactivateVirtualPa"...
0x14002eabf  mov     qword ptr [rsp+160h+var_108], rbx
0x14002eac4  cmova   rax, [rbp+60h+S2]
0x14002eac9  lea     rdx, byte_14008A27B
0x14002ead0  mov     [rsp+160h+var_F8], rax
0x14002ead5  lea     rax, aFoundNoMoreMat; "Found no more matches in list. Breaking"...
0x14002eadc  mov     [rsp+160h+var_100], rax
0x14002eae1  lea     rax, [rsp+160h+var_F8]
0x14002eae6  mov     [rsp+160h+var_128], rax
0x14002eaeb  lea     rax, [rsp+160h+var_100]
0x14002eaf0  mov     [rsp+160h+var_130], rax
0x14002eaf5  lea     rax, [rsp+160h+var_108]
0x14002eafa  mov     [rsp+160h+var_138], rax
0x14002eaff  lea     rax, [rsp+160h+var_110]
0x14002eb04  mov     qword ptr [rsp+160h+var_140], rax
0x14002eb09  mov     [rsp+160h+var_110], rdi
0x14002eb0e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14002eb13  jmp     short loc_14002EB1C
0x14002eb15  lea     rdi, aCmidideviceman_6; "CMidiDeviceManager::DeactivateVirtualPa"...
0x14002eb1c  test    r12b, r12b
0x14002eb1f  jz      short loc_14002EB33
0x14002eb21  mov     rax, [rbx]
0x14002eb24  mov     rdx, r15
0x14002eb27  mov     rcx, rbx
0x14002eb2a  mov     rax, [rax+40h]
0x14002eb2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002eb33  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14002eb38  mov     rcx, [rax+8]
0x14002eb3c  mov     eax, [rcx]
0x14002eb3e  cmp     eax, 4
0x14002eb41  jbe     short loc_14002EBA0
0x14002eb43  cmp     [rbp+60h+var_70], 7
0x14002eb48  lea     rax, [rbp+60h+S2]
0x14002eb4c  lea     rdx, byte_14008981F
0x14002eb53  mov     qword ptr [rsp+160h+var_108], rbx
0x14002eb58  cmova   rax, [rbp+60h+S2]
0x14002eb5d  mov     [rsp+160h+var_F8], rax
0x14002eb62  lea     rax, aExitSuccess_0; "Exit success"
0x14002eb69  mov     [rsp+160h+var_100], rax
0x14002eb6e  lea     rax, [rsp+160h+var_F8]
0x14002eb73  mov     [rsp+160h+var_128], rax
0x14002eb78  lea     rax, [rsp+160h+var_100]
0x14002eb7d  mov     [rsp+160h+var_130], rax
0x14002eb82  lea     rax, [rsp+160h+var_108]
0x14002eb87  mov     [rsp+160h+var_138], rax
0x14002eb8c  lea     rax, [rsp+160h+var_110]
0x14002eb91  mov     qword ptr [rsp+160h+var_140], rax
0x14002eb96  mov     [rsp+160h+var_110], rdi
0x14002eb9b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14002eba0  lea     rcx, [rbp+60h+var_E0]
0x14002eba4  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x14002eba9  mov     ebx, r13d
0x14002ebac  lea     rcx, [rbp+60h+S2]; void *
0x14002ebb0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002ebb5  mov     eax, ebx
0x14002ebb7  mov     rcx, [rbp+60h+var_48]
0x14002ebbb  xor     rcx, rsp; StackCookie
0x14002ebbe  call    __security_check_cookie
0x14002ebc3  lea     r11, [rsp+160h+var_30]
0x14002ebcb  mov     rbx, [r11+50h]
0x14002ebcf  movaps  xmm6, xmmword ptr [r11-10h]
0x14002ebd4  mov     rsp, r11
0x14002ebd7  pop     r15
0x14002ebd9  pop     r14
0x14002ebdb  pop     r13
0x14002ebdd  pop     r12
0x14002ebdf  pop     rdi
0x14002ebe0  pop     rsi
0x14002ebe1  pop     rbp
0x14002ebe2  retn
```
