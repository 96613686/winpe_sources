# CMidiDeviceManager::RebuildMidi1PortsForEndpoint(ushort const *)

- ea: `0x1400324c0`
- end: `0x1400327bf`
- name: `?RebuildMidi1PortsForEndpoint@CMidiDeviceManager@@UEAAJPEBG@Z`
- size: `767`
- prototype: `__int64 __fastcall(CMidiDeviceManager *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update`

## callees

- `0x1400054c0`
- `0x1400072d4`
- `0x140007c20`
- `0x14000a6b4`
- `0x140013a38`
- `0x14001440c`
- `0x14001dccc`
- `0x14001e990`
- `0x14001f95c`
- `0x1400324c0`
- `0x140032ff4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003261e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140032696`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400326af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003261e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140032696`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400326af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140032558`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140032558`

## string_xrefs

- `0x140032671`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14003278f`: `avcore\midi2\service\exe\mididevicemanager.cpp`

## pseudocode

```c
__int64 __fastcall CMidiDeviceManager::RebuildMidi1PortsForEndpoint(
        CMidiDeviceManager *this,
        const unsigned __int16 *a2)
{
  unsigned __int64 v2; // r8
  __int64 v4; // rax
  __int64 v5; // rdx
  struct _MIDIPORT **v6; // rbx
  struct _MIDIPORT **v7; // r14
  struct _MIDIPORT *v8; // rax
  unsigned __int64 v9; // r8
  _WORD *v10; // rdx
  __int64 v11; // rax
  const wchar_t *v12; // rdx
  const wchar_t *v13; // rcx
  unsigned int v14; // ebx
  int v16; // eax
  struct _MIDIPORT **v17; // rbx
  struct _MIDIPORT **v18; // rdi
  struct _MIDIPORT *v19; // rax
  unsigned __int64 v20; // r8
  _WORD *v21; // rdx
  __int64 v22; // rax
  const wchar_t *v23; // rdx
  const wchar_t *v24; // rcx
  int v25; // eax
  int v26[8]; // [rsp+20h] [rbp-59h] BYREF
  wchar_t *S1[2]; // [rsp+40h] [rbp-39h] BYREF
  size_t N[2]; // [rsp+50h] [rbp-29h]
  wchar_t *S2[2]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v30; // [rsp+70h] [rbp-9h]
  unsigned __int64 v31; // [rsp+78h] [rbp-1h]
  char *v32[4]; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = -1;
  *(_OWORD *)S1 = 0;
  *(_OWORD *)N = 0;
  do
    ++v2;
  while ( a2[v2] );
  std::wstring::_Construct<1,unsigned short const *>((char **)S1, a2, v2);
  v4 = std::wstring::wstring((__int64)v32, (__int64)S1);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(S2, v4);
  std::wstring::~wstring((char **)S1);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(
                           `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl,
                           v5) )
  {
    v17 = (struct _MIDIPORT **)*((_QWORD *)this + 17);
    v18 = (struct _MIDIPORT **)*((_QWORD *)this + 18);
    while ( 1 )
    {
      if ( v17 == v18 )
      {
LABEL_18:
        v14 = -2147023728;
        goto LABEL_19;
      }
      v19 = *v17;
      *(_OWORD *)S1 = 0;
      N[0] = 0;
      v20 = -1;
      N[1] = 0;
      v21 = (_WORD *)*((_QWORD *)v19 + 5);
      do
        ++v20;
      while ( v21[v20] );
      std::wstring::_Construct<1,unsigned short const *>((char **)S1, v21, v20);
      v22 = std::wstring::wstring((__int64)v26, (__int64)S1);
      WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v32, v22);
      std::wstring::operator=((char **)S1, (__int64)v32);
      std::wstring::~wstring(v32);
      v23 = (const wchar_t *)S2;
      v24 = (const wchar_t *)S1;
      if ( v31 > 7 )
        v23 = S2[0];
      if ( N[1] > 7 )
        v24 = S1[0];
      if ( N[0] == v30 && (!N[0] || !wmemcmp(v24, v23, N[0])) )
        break;
      std::wstring::~wstring((char **)S1);
      ++v17;
    }
    v25 = CMidiDeviceManager::SyncMidi1Ports(this, *v17);
    v14 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAF4,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)(unsigned int)v25,
        v26[0]);
      std::wstring::~wstring((char **)S1);
      goto LABEL_19;
    }
    std::wstring::~wstring((char **)S1);
    goto LABEL_25;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v6 = (struct _MIDIPORT **)*((_QWORD *)this + 17);
  v7 = (struct _MIDIPORT **)*((_QWORD *)this + 18);
  while ( 1 )
  {
    if ( v6 == v7 )
    {
      if ( this != (CMidiDeviceManager *)-96LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
      goto LABEL_18;
    }
    v8 = *v6;
    *(_OWORD *)S1 = 0;
    N[0] = 0;
    v9 = -1;
    N[1] = 0;
    v10 = (_WORD *)*((_QWORD *)v8 + 5);
    do
      ++v9;
    while ( v10[v9] );
    std::wstring::_Construct<1,unsigned short const *>((char **)S1, v10, v9);
    v11 = std::wstring::wstring((__int64)v26, (__int64)S1);
    WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v32, v11);
    std::wstring::operator=((char **)S1, (__int64)v32);
    std::wstring::~wstring(v32);
    v12 = (const wchar_t *)S2;
    v13 = (const wchar_t *)S1;
    if ( v31 > 7 )
      v12 = S2[0];
    if ( N[1] > 7 )
      v13 = S1[0];
    if ( N[0] == v30 && (!N[0] || !wmemcmp(v13, v12, N[0])) )
      break;
    std::wstring::~wstring((char **)S1);
    ++v6;
  }
  v16 = CMidiDeviceManager::SyncMidi1Ports(this, *v6);
  v14 = v16;
  if ( v16 >= 0 )
  {
    std::wstring::~wstring((char **)S1);
    if ( this != (CMidiDeviceManager *)-96LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
LABEL_25:
    v14 = 0;
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xAE5,
    (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
    (const char *)(unsigned int)v16,
    v26[0]);
  std::wstring::~wstring((char **)S1);
  if ( this != (CMidiDeviceManager *)-96LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
LABEL_19:
  std::wstring::~wstring((char **)S2);
  return v14;
}

```

## disassembly

```asm
0x1400324c0  mov     [rsp-8+arg_10], rbx
0x1400324c5  mov     [rsp-8+arg_18], rsi
0x1400324ca  push    rbp
0x1400324cb  push    rdi
0x1400324cc  push    r12
0x1400324ce  push    r14
0x1400324d0  push    r15
0x1400324d2  lea     rbp, [rsp-37h]
0x1400324d7  sub     rsp, 0B0h
0x1400324de  mov     rax, cs:__security_cookie
0x1400324e5  xor     rax, rsp
0x1400324e8  mov     [rbp+57h+var_30], rax
0x1400324ec  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400324f0  xorps   xmm0, xmm0
0x1400324f3  xorps   xmm1, xmm1
0x1400324f6  mov     r8, r12
0x1400324f9  movups  xmmword ptr [rbp+57h+S1], xmm0
0x1400324fd  xor     r15d, r15d
0x140032500  mov     rsi, rcx
0x140032503  movdqu  xmmword ptr [rbp+57h+N], xmm1
0x140032508  inc     r8
0x14003250b  cmp     [rdx+r8*2], r15w
0x140032510  jnz     short loc_140032508
0x140032512  lea     rcx, [rbp+57h+S1]
0x140032516  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003251b  lea     rdx, [rbp+57h+S1]
0x14003251f  lea     rcx, [rbp+57h+var_50]
0x140032523  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140032528  mov     rdx, rax
0x14003252b  lea     rcx, [rbp+57h+S2]
0x14003252f  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x140032534  lea     rcx, [rbp+57h+S1]; void *
0x140032538  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003253d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x140032544  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x140032549  test    al, al
0x14003254b  jz      loc_1400326BD
0x140032551  lea     rdi, [rsi+60h]
0x140032555  mov     rcx, rdi; lpCriticalSection
0x140032558  call    cs:__imp_EnterCriticalSection
0x14003255e  mov     rbx, [rsi+88h]
0x140032565  mov     r14, [rsi+90h]
0x14003256c  jmp     loc_14003260D
0x140032571  mov     rax, [rbx]
0x140032574  xorps   xmm0, xmm0
0x140032577  movups  xmmword ptr [rbp+57h+S1], xmm0
0x14003257b  mov     [rbp+57h+N], r15
0x14003257f  mov     r8, r12
0x140032582  mov     [rbp+57h+N+8], r15
0x140032586  mov     rdx, [rax+28h]
0x14003258a  inc     r8
0x14003258d  cmp     [rdx+r8*2], r15w
0x140032592  jnz     short loc_14003258A
0x140032594  lea     rcx, [rbp+57h+S1]
0x140032598  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003259d  lea     rdx, [rbp+57h+S1]
0x1400325a1  lea     rcx, [rbp+57h+var_B0]
0x1400325a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400325aa  mov     rdx, rax
0x1400325ad  lea     rcx, [rbp+57h+var_50]
0x1400325b1  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x1400325b6  lea     rdx, [rbp+57h+var_50]
0x1400325ba  lea     rcx, [rbp+57h+S1]
0x1400325be  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400325c3  lea     rcx, [rbp+57h+var_50]; void *
0x1400325c7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400325cc  cmp     [rbp+57h+var_58], 7
0x1400325d1  lea     rdx, [rbp+57h+S2]
0x1400325d5  mov     r8, [rbp+57h+N]; N
0x1400325d9  lea     rcx, [rbp+57h+S1]
0x1400325dd  cmova   rdx, [rbp+57h+S2]; S2
0x1400325e2  cmp     [rbp+57h+N+8], 7
0x1400325e7  cmova   rcx, [rbp+57h+S1]; S1
0x1400325ec  cmp     r8, [rbp+57h+var_60]
0x1400325f0  jnz     short loc_140032600
0x1400325f2  test    r8, r8
0x1400325f5  jz      short loc_14003265C
0x1400325f7  call    wmemcmp
0x1400325fc  test    eax, eax
0x1400325fe  jz      short loc_14003265C
0x140032600  lea     rcx, [rbp+57h+S1]; void *
0x140032604  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140032609  add     rbx, 8
0x14003260d  cmp     rbx, r14
0x140032610  jnz     loc_140032571
0x140032616  test    rdi, rdi
0x140032619  jz      short loc_140032624
0x14003261b  mov     rcx, rdi; lpCriticalSection
0x14003261e  call    cs:__imp_LeaveCriticalSection
0x140032624  mov     ebx, 80070490h
0x140032629  lea     rcx, [rbp+57h+S2]; void *
0x14003262d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140032632  mov     eax, ebx
0x140032634  mov     rcx, [rbp+57h+var_30]
0x140032638  xor     rcx, rsp; StackCookie
0x14003263b  call    __security_check_cookie
0x140032640  lea     r11, [rsp+0D0h+var_20]
0x140032648  mov     rbx, [r11+40h]
0x14003264c  mov     rsi, [r11+48h]
0x140032650  mov     rsp, r11
0x140032653  pop     r15
0x140032655  pop     r14
0x140032657  pop     r12
0x140032659  pop     rdi
0x14003265a  pop     rbp
0x14003265b  retn
0x14003265c  mov     rdx, [rbx]; struct _MIDIPORT *
0x14003265f  mov     rcx, rsi; this
0x140032662  call    ?SyncMidi1Ports@CMidiDeviceManager@@AEAAJPEAU_MIDIPORT@@@Z; CMidiDeviceManager::SyncMidi1Ports(_MIDIPORT *)
0x140032667  mov     ebx, eax
0x140032669  test    eax, eax
0x14003266b  jns     short loc_14003269E
0x14003266d  mov     rcx, [rbp+5Fh]; this
0x140032671  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x140032678  mov     r9d, eax; char *
0x14003267b  mov     edx, 0AE5h; void *
0x140032680  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140032685  lea     rcx, [rbp+57h+S1]; void *
0x140032689  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003268e  test    rdi, rdi
0x140032691  jz      short loc_140032629
0x140032693  mov     rcx, rdi; lpCriticalSection
0x140032696  call    cs:__imp_LeaveCriticalSection
0x14003269c  jmp     short loc_140032629
0x14003269e  lea     rcx, [rbp+57h+S1]; void *
0x1400326a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400326a7  test    rdi, rdi
0x1400326aa  jz      short loc_1400326B5
0x1400326ac  mov     rcx, rdi; lpCriticalSection
0x1400326af  call    cs:__imp_LeaveCriticalSection
0x1400326b5  mov     ebx, r15d
0x1400326b8  jmp     loc_140032629
0x1400326bd  mov     rbx, [rsi+88h]
0x1400326c4  mov     rdi, [rsi+90h]
0x1400326cb  jmp     loc_14003276C
0x1400326d0  mov     rax, [rbx]
0x1400326d3  xorps   xmm0, xmm0
0x1400326d6  movups  xmmword ptr [rbp+57h+S1], xmm0
0x1400326da  mov     [rbp+57h+N], r15
0x1400326de  mov     r8, r12
0x1400326e1  mov     [rbp+57h+N+8], r15
0x1400326e5  mov     rdx, [rax+28h]
0x1400326e9  inc     r8
0x1400326ec  cmp     [rdx+r8*2], r15w
0x1400326f1  jnz     short loc_1400326E9
0x1400326f3  lea     rcx, [rbp+57h+S1]
0x1400326f7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400326fc  lea     rdx, [rbp+57h+S1]
0x140032700  lea     rcx, [rbp+57h+var_B0]
0x140032704  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140032709  mov     rdx, rax
0x14003270c  lea     rcx, [rbp+57h+var_50]
0x140032710  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x140032715  lea     rdx, [rbp+57h+var_50]
0x140032719  lea     rcx, [rbp+57h+S1]
0x14003271d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140032722  lea     rcx, [rbp+57h+var_50]; void *
0x140032726  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003272b  cmp     [rbp+57h+var_58], 7
0x140032730  lea     rdx, [rbp+57h+S2]
0x140032734  mov     r8, [rbp+57h+N]; N
0x140032738  lea     rcx, [rbp+57h+S1]
0x14003273c  cmova   rdx, [rbp+57h+S2]; S2
0x140032741  cmp     [rbp+57h+N+8], 7
0x140032746  cmova   rcx, [rbp+57h+S1]; S1
0x14003274b  cmp     r8, [rbp+57h+var_60]
0x14003274f  jnz     short loc_14003275F
0x140032751  test    r8, r8
0x140032754  jz      short loc_14003277A
0x140032756  call    wmemcmp
0x14003275b  test    eax, eax
0x14003275d  jz      short loc_14003277A
0x14003275f  lea     rcx, [rbp+57h+S1]; void *
0x140032763  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140032768  add     rbx, 8
0x14003276c  cmp     rbx, rdi
0x14003276f  jnz     loc_1400326D0
0x140032775  jmp     loc_140032624
0x14003277a  mov     rdx, [rbx]; struct _MIDIPORT *
0x14003277d  mov     rcx, rsi; this
0x140032780  call    ?SyncMidi1Ports@CMidiDeviceManager@@AEAAJPEAU_MIDIPORT@@@Z; CMidiDeviceManager::SyncMidi1Ports(_MIDIPORT *)
0x140032785  mov     ebx, eax
0x140032787  test    eax, eax
0x140032789  jns     short loc_1400327B1
0x14003278b  mov     rcx, [rbp+5Fh]; this
0x14003278f  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x140032796  mov     r9d, eax; char *
0x140032799  mov     edx, 0AF4h; void *
0x14003279e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400327a3  lea     rcx, [rbp+57h+S1]; void *
0x1400327a7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400327ac  jmp     loc_140032629
0x1400327b1  lea     rcx, [rbp+57h+S1]; void *
0x1400327b5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400327ba  jmp     loc_1400326B5
```
