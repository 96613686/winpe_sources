# CMidiEndpointProtocolWorker::UpdateFunctionBlockNameProperty(uchar,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x140045550`
- end: `0x1400457e3`
- name: `?UpdateFunctionBlockNameProperty@CMidiEndpointProtocolWorker@@AEAAJEV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `659`
- prototype: `__int64 __fastcall(CMidiEndpointProtocolWorker *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400428c4`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x140013a38`
- `0x14001ddc4`
- `0x1400216cc`
- `0x1400417cc`
- `0x140045550`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14004560f`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14004560f`

## string_xrefs

- `0x14004578e`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x1400455c2`: `CMidiEndpointProtocolWorker::UpdateFunctionBlockNameProperty`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMidiEndpointProtocolWorker::UpdateFunctionBlockNameProperty(
        CMidiEndpointProtocolWorker *this,
        unsigned __int8 a2,
        char **a3)
{
  _DWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  char *v9; // rbx
  char *v10; // rax
  void *v11; // rax
  __int64 v12; // rax
  char **v13; // rax
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdx
  int v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20[2]; // [rsp+48h] [rbp-B8h] BYREF
  char *v21; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v22; // [rsp+58h] [rbp-A8h] BYREF
  CMidiEndpointProtocolWorker *v23; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[32]; // [rsp+68h] [rbp-98h] BYREF
  char **v25; // [rsp+88h] [rbp-78h]
  char *v26[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v28; // [rsp+A8h] [rbp-58h]
  char *Src[4]; // [rsp+B0h] [rbp-50h] BYREF
  struct _DEVPROPKEY v30; // [rsp+D0h] [rbp-30h] BYREF
  int v31; // [rsp+E4h] [rbp-1Ch]
  __int64 v32; // [rsp+E8h] [rbp-18h]
  int v33; // [rsp+F0h] [rbp-10h]
  int v34; // [rsp+F4h] [rbp-Ch]
  char **v35; // [rsp+F8h] [rbp-8h]
  __int128 v36; // [rsp+100h] [rbp+0h]
  int v37; // [rsp+110h] [rbp+10h]
  int v38; // [rsp+114h] [rbp+14h]
  __int64 v39; // [rsp+118h] [rbp+18h]
  int v40; // [rsp+120h] [rbp+20h]
  int v41; // [rsp+124h] [rbp+24h]
  __int64 *v42; // [rsp+128h] [rbp+28h]
  struct _DEVPROPKEY v43; // [rsp+130h] [rbp+30h] BYREF
  int v44; // [rsp+144h] [rbp+44h]
  __int64 v45; // [rsp+148h] [rbp+48h]
  __int64 v46; // [rsp+150h] [rbp+50h]
  __int64 v47; // [rsp+158h] [rbp+58h]
  __int128 v48; // [rsp+160h] [rbp+60h]
  int v49; // [rsp+170h] [rbp+70h]
  int v50; // [rsp+174h] [rbp+74h]
  __int64 v51; // [rsp+178h] [rbp+78h]
  int v52; // [rsp+180h] [rbp+80h]
  int v53; // [rsp+184h] [rbp+84h]
  __int64 *v54; // [rsp+188h] [rbp+88h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v25 = a3;
  v6 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  v9 = (char *)this + 56;
  if ( *v6 > 4u )
  {
    if ( *((_QWORD *)this + 10) <= 7u )
      v10 = (char *)this + 56;
    else
      v10 = *(char **)v9;
    v21 = v10;
    v22 = L"Enter";
    v23 = this;
    *(_QWORD *)v20 = "CMidiEndpointProtocolWorker::UpdateFunctionBlockNameProperty";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v6,
      (__int64)byte_14008B813,
      v7,
      v8,
      v20,
      (__int64)&v23,
      &v22,
      &v21);
  }
  v19 = 0;
  GetSystemTimePreciseAsFileTime(&v19);
  v11 = (void *)std::wstring::wstring((__int64)v24, (__int64)a3);
  v12 = WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v11);
  std::operator+<unsigned short>(v26, v12, &qword_140081AD0);
  std::wstring::~wstring(Src);
  if ( !v27 )
  {
    CMidiEndpointProtocolWorker::FunctionBlockNamePropertyKeyFromNumber(this, &v43, a2);
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v48 = PKEY_MIDI_FunctionBlocksLastUpdateTime;
    v49 = 183;
    v50 = 0;
    v51 = 0;
    v52 = 16;
    v53 = 8;
    v54 = &v19;
    if ( *((_QWORD *)this + 10) > 7u )
      v9 = *(char **)v9;
    v14 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, struct _DEVPROPKEY *))(**((_QWORD **)this + 22) + 48LL))(
            *((_QWORD *)this + 22),
            v9,
            2,
            &v43);
    v15 = v14;
    if ( v14 < 0 )
    {
      v16 = 1373;
      goto LABEL_17;
    }
LABEL_18:
    v15 = 0;
    goto LABEL_19;
  }
  CMidiEndpointProtocolWorker::FunctionBlockNamePropertyKeyFromNumber(this, &v30, a2);
  v31 = 0;
  v32 = 0;
  v33 = 18;
  v34 = 2 * v27 + 2;
  v13 = v26;
  if ( v28 > 7 )
    v13 = (char **)v26[0];
  v35 = v13;
  v36 = PKEY_MIDI_FunctionBlocksLastUpdateTime;
  v37 = 183;
  v38 = 0;
  v39 = 0;
  v40 = 16;
  v41 = 8;
  v42 = &v19;
  if ( *((_QWORD *)this + 10) > 7u )
    v9 = *(char **)v9;
  v14 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, struct _DEVPROPKEY *))(**((_QWORD **)this + 22) + 48LL))(
          *((_QWORD *)this + 22),
          v9,
          2,
          &v30);
  v15 = v14;
  if ( v14 >= 0 )
    goto LABEL_18;
  v16 = 1360;
LABEL_17:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
    (const char *)(unsigned int)v14,
    v18);
LABEL_19:
  std::wstring::~wstring(v26);
  std::wstring::~wstring(a3);
  return v15;
}

```

## disassembly

```asm
0x140045550  mov     [rsp-8+arg_18], rbx
0x140045555  push    rbp
0x140045556  push    rsi
0x140045557  push    rdi
0x140045558  push    r14
0x14004555a  push    r15
0x14004555c  lea     rbp, [rsp-0A0h]
0x140045564  sub     rsp, 1A0h
0x14004556b  mov     rax, cs:__security_cookie
0x140045572  xor     rax, rsp
0x140045575  mov     [rbp+0C0h+var_30], rax
0x14004557c  mov     rsi, r8
0x14004557f  mov     r14b, dl
0x140045582  mov     rdi, rcx
0x140045585  mov     [rbp+0C0h+var_138], r8
0x140045589  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14004558e  mov     rcx, [rax+8]
0x140045592  mov     eax, [rcx]
0x140045594  lea     rbx, [rdi+38h]
0x140045598  cmp     eax, 4
0x14004559b  jbe     short loc_140045602
0x14004559d  cmp     qword ptr [rbx+18h], 7
0x1400455a2  jbe     short loc_1400455A9
0x1400455a4  mov     rax, [rbx]
0x1400455a7  jmp     short loc_1400455AC
0x1400455a9  mov     rax, rbx
0x1400455ac  mov     [rsp+1C0h+var_170], rax
0x1400455b1  lea     rax, aEnter; "Enter"
0x1400455b8  mov     [rsp+1C0h+var_168], rax
0x1400455bd  mov     [rsp+1C0h+var_160], rdi
0x1400455c2  lea     rax, aCmidiendpointp_2; "CMidiEndpointProtocolWorker::UpdateFunc"...
0x1400455c9  mov     qword ptr [rsp+1C0h+var_178], rax
0x1400455ce  lea     rax, [rsp+1C0h+var_170]
0x1400455d3  mov     [rsp+1C0h+var_188], rax
0x1400455d8  lea     rax, [rsp+1C0h+var_168]
0x1400455dd  mov     [rsp+1C0h+var_190], rax
0x1400455e2  lea     rax, [rsp+1C0h+var_160]
0x1400455e7  mov     [rsp+1C0h+var_198], rax
0x1400455ec  lea     rax, [rsp+1C0h+var_178]
0x1400455f1  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x1400455f6  lea     rdx, byte_14008B813
0x1400455fd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140045602  xor     r15d, r15d
0x140045605  mov     [rsp+1C0h+var_180], r15
0x14004560a  lea     rcx, [rsp+1C0h+var_180]
0x14004560f  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x140045615  mov     rdx, rsi
0x140045618  lea     rcx, [rsp+1C0h+var_158]
0x14004561d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140045622  mov     rdx, rax; void *
0x140045625  lea     rcx, [rbp+0C0h+Src]; Src
0x140045629  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x14004562e  nop
0x14004562f  lea     r8, qword_140081AD0
0x140045636  mov     rdx, rax
0x140045639  lea     rcx, [rbp+0C0h+var_130]
0x14004563d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x140045642  nop
0x140045643  lea     rcx, [rbp+0C0h+Src]; void *
0x140045647  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004564c  mov     r8b, r14b; unsigned __int8
0x14004564f  mov     rcx, rdi; this
0x140045652  cmp     [rbp+0C0h+var_120], r15
0x140045656  jz      loc_140045704
0x14004565c  lea     rdx, [rbp+0C0h+var_F0]; retstr
0x140045660  call    ?FunctionBlockNamePropertyKeyFromNumber@CMidiEndpointProtocolWorker@@AEAA?AU_DEVPROPKEY@@E@Z; CMidiEndpointProtocolWorker::FunctionBlockNamePropertyKeyFromNumber(uchar)
0x140045665  mov     [rbp+0C0h+var_DC], r15d
0x140045669  mov     [rbp+0C0h+var_D8], r15
0x14004566d  mov     [rbp+0C0h+var_D0], 12h
0x140045674  mov     eax, dword ptr [rbp+0C0h+var_120]
0x140045677  lea     eax, ds:2[rax*2]
0x14004567e  mov     [rbp+0C0h+var_CC], eax
0x140045681  lea     rax, [rbp+0C0h+var_130]
0x140045685  cmp     [rbp+0C0h+var_118], 7
0x14004568a  cmova   rax, [rbp+0C0h+var_130]
0x14004568f  mov     [rbp+0C0h+var_C8], rax
0x140045693  movups  xmm0, cs:PKEY_MIDI_FunctionBlocksLastUpdateTime
0x14004569a  movaps  [rbp+0C0h+var_C0], xmm0
0x14004569e  mov     eax, cs:dword_14007A8E8
0x1400456a4  mov     [rbp+0C0h+var_B0], eax
0x1400456a7  mov     [rbp+0C0h+var_AC], r15d
0x1400456ab  mov     [rbp+0C0h+var_A8], r15
0x1400456af  mov     [rbp+0C0h+var_A0], 10h
0x1400456b6  mov     [rbp+0C0h+var_9C], 8
0x1400456bd  lea     rax, [rsp+1C0h+var_180]
0x1400456c2  mov     [rbp+0C0h+var_98], rax
0x1400456c6  mov     rcx, [rdi+0B0h]
0x1400456cd  mov     rax, [rcx]
0x1400456d0  cmp     qword ptr [rbx+18h], 7
0x1400456d5  jbe     short loc_1400456DA
0x1400456d7  mov     rbx, [rbx]
0x1400456da  lea     r9, [rbp+0C0h+var_F0]
0x1400456de  mov     r8d, 2
0x1400456e4  mov     rdx, rbx
0x1400456e7  mov     rax, [rax+30h]
0x1400456eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400456f0  mov     ebx, eax
0x1400456f2  test    eax, eax
0x1400456f4  jns     loc_1400457A6
0x1400456fa  mov     edx, 550h
0x1400456ff  jmp     loc_14004578E
0x140045704  lea     rdx, [rbp+0C0h+var_90]; retstr
0x140045708  call    ?FunctionBlockNamePropertyKeyFromNumber@CMidiEndpointProtocolWorker@@AEAA?AU_DEVPROPKEY@@E@Z; CMidiEndpointProtocolWorker::FunctionBlockNamePropertyKeyFromNumber(uchar)
0x14004570d  mov     [rbp+0C0h+var_7C], r15d
0x140045711  mov     [rbp+0C0h+var_78], r15
0x140045715  mov     [rbp+0C0h+var_70], r15
0x140045719  mov     [rbp+0C0h+var_68], r15
0x14004571d  movups  xmm0, cs:PKEY_MIDI_FunctionBlocksLastUpdateTime
0x140045724  movaps  [rbp+0C0h+var_60], xmm0
0x140045728  mov     eax, cs:dword_14007A8E8
0x14004572e  mov     [rbp+0C0h+var_50], eax
0x140045731  mov     [rbp+0C0h+var_4C], r15d
0x140045735  mov     [rbp+0C0h+var_48], r15
0x140045739  mov     [rbp+0C0h+var_40], 10h
0x140045743  mov     [rbp+0C0h+var_3C], 8
0x14004574d  lea     rax, [rsp+1C0h+var_180]
0x140045752  mov     [rbp+0C0h+var_38], rax
0x140045759  mov     rcx, [rdi+0B0h]
0x140045760  mov     rax, [rcx]
0x140045763  cmp     qword ptr [rbx+18h], 7
0x140045768  jbe     short loc_14004576D
0x14004576a  mov     rbx, [rbx]
0x14004576d  lea     r9, [rbp+0C0h+var_90]
0x140045771  mov     r8d, 2
0x140045777  mov     rdx, rbx
0x14004577a  mov     rax, [rax+30h]
0x14004577e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045783  mov     ebx, eax
0x140045785  test    eax, eax
0x140045787  jns     short loc_1400457A6
0x140045789  mov     edx, 55Dh; void *
0x14004578e  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140045795  mov     r9d, eax; char *
0x140045798  mov     rcx, [rbp+0C8h]; this
0x14004579f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400457a4  jmp     short loc_1400457A9
0x1400457a6  mov     ebx, r15d
0x1400457a9  lea     rcx, [rbp+0C0h+var_130]; void *
0x1400457ad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400457b2  nop
0x1400457b3  mov     rcx, rsi; void *
0x1400457b6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400457bb  mov     eax, ebx
0x1400457bd  mov     rcx, [rbp+0C0h+var_30]
0x1400457c4  xor     rcx, rsp; StackCookie
0x1400457c7  call    __security_check_cookie
0x1400457cc  mov     rbx, [rsp+1C0h+arg_18]
0x1400457d4  add     rsp, 1A0h
0x1400457db  pop     r15
0x1400457dd  pop     r14
0x1400457df  pop     rdi
0x1400457e0  pop     rsi
0x1400457e1  pop     rbp
0x1400457e2  retn
```
