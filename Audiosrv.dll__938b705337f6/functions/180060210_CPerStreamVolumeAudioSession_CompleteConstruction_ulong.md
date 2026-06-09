# CPerStreamVolumeAudioSession::CompleteConstruction(ulong)

- ea: `0x180060210`
- end: `0x1800604da`
- name: `?CompleteConstruction@CPerStreamVolumeAudioSession@@EEAAJK@Z`
- size: `714`
- prototype: `__int64 __fastcall(CPerStreamVolumeAudioSession *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000abd0`
- `0x1800126bc`
- `0x180015d34`
- `0x18001e7dc`
- `0x18001f6b0`
- `0x180060210`
- `0x180069ff0`
- `0x18007a0b0`
- `0x1800cfd9c`
- `0x1800e73ac`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060326`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060326`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800603af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006049c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800603af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006049c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800602de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060311`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800603df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800604af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800602de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060311`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800603df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800604af`

## string_xrefs

- `0x18006027a`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x1800602f0`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x18006043a`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x180060483`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPerStreamVolumeAudioSession::CompleteConstruction(CPerStreamVolumeAudioSession *this, char a2)
{
  const unsigned __int16 *Buffer; // rax
  int v5; // eax
  int MixFormat; // edi
  void *v7; // rcx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  void *v10; // rcx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rax
  void *v13; // rax
  void *v14; // rcx
  unsigned int i; // ecx
  int v16; // esi
  void *v17; // rcx
  __int64 v18; // rcx
  unsigned int v19; // eax
  int SessionConfiguration; // eax
  void *v21; // rcx
  EffectPack **v23; // [rsp+20h] [rbp-60h]
  struct _GUID v24; // [rsp+40h] [rbp-40h] BYREF
  LPVOID *p_pv; // [rsp+50h] [rbp-30h]
  struct tWAVEFORMATEX *v26; // [rsp+58h] [rbp-28h] BYREF
  char v27; // [rsp+60h] [rbp-20h]
  EffectPack *v28[2]; // [rsp+68h] [rbp-18h] BYREF
  __int64 v29; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  LPVOID pv; // [rsp+A0h] [rbp+20h] BYREF

  *(_OWORD *)v28 = 0;
  v29 = 0;
  Buffer = CAudioEndpointId::GetBuffer((CPerStreamVolumeAudioSession *)((char *)this + 584));
  v23 = v28;
  v5 = (*(__int64 (__fastcall **)(PVOID, const unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)g_pEndpointCharacteristicsCache
                                                                                  + 40LL))(
         g_pEndpointCharacteristicsCache,
         Buffer,
         0,
         0);
  MixFormat = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x616,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosession.cpp",
      (const char *)(unsigned int)v5,
      (int)v28);
    goto LABEL_36;
  }
  pv = 0;
  p_pv = &pv;
  v26 = 0;
  v27 = 1;
  v24 = GUID_00000000_0000_0000_0000_000000000000;
  MixFormat = EffectPack::GetMixFormat(v28[1], eHostProcessConnector, &v24, &v26);
  if ( v27 )
  {
    v7 = *p_pv;
    *p_pv = v26;
    if ( v7 )
      CoTaskMemFree(v7);
  }
  if ( MixFormat < 0 )
  {
    v8 = (unsigned int)MixFormat;
    v9 = 1568;
    goto LABEL_8;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 736));
  v11 = *((unsigned __int16 *)pv + 1);
  *((_DWORD *)this + 222) = v11;
  v12 = 4 * v11;
  if ( !is_mul_ok(v11, 4u) )
    v12 = -1;
  v13 = operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
  v14 = (void *)*((_QWORD *)this + 112);
  *((_QWORD *)this + 112) = v13;
  if ( v14 )
    operator delete(v14);
  if ( *((_QWORD *)this + 112) )
  {
    for ( i = 0; i < *((_DWORD *)this + 222); ++i )
      *(_DWORD *)(*((_QWORD *)this + 112) + 4LL * i) = 1065353216;
    if ( this != (CPerStreamVolumeAudioSession *)-736LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 736));
    v16 = a2 & 2;
    *((_BYTE *)this + 920) = v16 != 0;
    if ( *((_DWORD *)v28[0] + 16) == 3 )
    {
      *((_BYTE *)this + 920) = 0;
    }
    else if ( v16 )
    {
      v18 = *((_QWORD *)this + 116);
      *((_QWORD *)this + 116) = 0;
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v19 = CPerStreamVolumeAudioSession::TryOpenSessionPropertyStore(this, (struct IPropertyStore **)this + 116);
      if ( wil::details::in1diag3::Log_IfFailedWithExpected(
             retaddr,
             (void *)0x648,
             (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosession.cpp",
             (const char *)v19,
             2,
             0x80070002) >= 0 )
      {
        if ( *((_QWORD *)this + 116) )
        {
          SessionConfiguration = CPerStreamVolumeAudioSession::LoadSessionConfiguration(this);
          MixFormat = SessionConfiguration;
          if ( SessionConfiguration < 0 )
          {
            v8 = (unsigned int)SessionConfiguration;
            v9 = 1612;
LABEL_8:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v9,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosession.cpp",
              (const char *)v8,
              (int)v23);
            v10 = pv;
            pv = 0;
            if ( v10 )
              CoTaskMemFree(v10);
            goto LABEL_36;
          }
        }
      }
    }
    v17 = pv;
    pv = 0;
    if ( v17 )
      CoTaskMemFree(v17);
    MixFormat = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x628,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosession.cpp",
      (const char *)0x8007000ELL,
      (int)v28);
    if ( this != (CPerStreamVolumeAudioSession *)-736LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 736));
    v21 = pv;
    pv = 0;
    if ( v21 )
      CoTaskMemFree(v21);
    MixFormat = -2147024882;
  }
LABEL_36:
  EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v28);
  return (unsigned int)MixFormat;
}

```

## disassembly

```asm
0x180060210  mov     [rsp-18h+arg_8], rbx
0x180060215  mov     [rsp-18h+arg_10], rsi
0x18006021a  push    rbp
0x18006021b  push    rdi
0x18006021c  push    r14
0x18006021e  mov     rbp, rsp
0x180060221  sub     rsp, 80h
0x180060228  mov     esi, edx
0x18006022a  mov     rbx, rcx
0x18006022d  xorps   xmm0, xmm0
0x180060230  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180060235  xor     r14d, r14d
0x180060238  mov     [rbp+var_8], r14
0x18006023c  add     rcx, 248h; this
0x180060243  call    ?GetBuffer@CAudioEndpointId@@QEAAPEBGXZ; CAudioEndpointId::GetBuffer(void)
0x180060248  mov     rdx, rax
0x18006024b  mov     rcx, cs:?g_pEndpointCharacteristicsCache@@3PEAUIEndpointCharacteristicsCache@@EA; IEndpointCharacteristicsCache * g_pEndpointCharacteristicsCache
0x180060252  mov     r8, [rcx]
0x180060255  mov     rax, [r8+28h]
0x180060259  lea     r8, [rbp+var_18]
0x18006025d  mov     qword ptr [rsp+80h+var_60], r8; int
0x180060262  xor     r9d, r9d
0x180060265  xor     r8d, r8d
0x180060268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006026d  mov     edi, eax
0x18006026f  test    eax, eax
0x180060271  jns     short loc_180060290
0x180060273  mov     rcx, [rbp+18h]; this
0x180060277  mov     r9d, eax; char *
0x18006027a  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180060281  mov     edx, 616h; void *
0x180060286  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006028b  jmp     loc_1800604B7
0x180060290  mov     [rbp+pv], r14
0x180060294  lea     rax, [rbp+pv]
0x180060298  mov     [rbp+var_30], rax
0x18006029c  mov     [rbp+var_28], r14
0x1800602a0  mov     [rbp+var_20], 1
0x1800602a4  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800602ab  movdqu  xmmword ptr [rbp+var_40.Data1], xmm0
0x1800602b0  lea     r9, [rbp+var_28]; struct tWAVEFORMATEX **
0x1800602b4  lea     r8, [rbp+var_40]; struct _GUID
0x1800602b8  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800602ba  mov     rcx, [rbp+var_18+8]; this
0x1800602be  call    ?GetMixFormat@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetMixFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x1800602c3  mov     edi, eax
0x1800602c5  cmp     [rbp+var_20], r14b
0x1800602c9  jz      short loc_1800602E4
0x1800602cb  mov     r8, [rbp+var_30]
0x1800602cf  mov     rcx, [r8]; pv
0x1800602d2  mov     rdx, [rbp+var_28]
0x1800602d6  mov     [r8], rdx
0x1800602d9  test    rcx, rcx
0x1800602dc  jz      short loc_1800602E4
0x1800602de  call    cs:__imp_CoTaskMemFree
0x1800602e4  test    edi, edi
0x1800602e6  jns     short loc_18006031C
0x1800602e8  mov     r9d, edi; char *
0x1800602eb  mov     edx, 620h; void *
0x1800602f0  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800602f7  mov     rcx, [rbp+18h]; this
0x1800602fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060300  mov     rcx, [rbp+pv]; pv
0x180060304  mov     [rbp+pv], r14
0x180060308  test    rcx, rcx
0x18006030b  jz      loc_1800604B7
0x180060311  call    cs:__imp_CoTaskMemFree
0x180060317  jmp     loc_1800604B7
0x18006031c  lea     rdi, [rbx+2E0h]
0x180060323  mov     rcx, rdi; lpCriticalSection
0x180060326  call    cs:__imp_EnterCriticalSection
0x18006032c  mov     rax, [rbp+pv]
0x180060330  movzx   ecx, word ptr [rax+2]
0x180060334  mov     [rbx+378h], ecx
0x18006033a  mov     eax, 4
0x18006033f  mul     rcx
0x180060342  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180060349  cmovb   rax, rcx
0x18006034d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180060354  mov     rcx, rax; unsigned __int64
0x180060357  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006035c  mov     rcx, [rbx+380h]; void *
0x180060363  mov     [rbx+380h], rax
0x18006036a  test    rcx, rcx
0x18006036d  jz      short loc_180060374
0x18006036f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180060374  cmp     [rbx+380h], r14
0x18006037b  jz      loc_180060477
0x180060381  mov     ecx, r14d
0x180060384  cmp     [rbx+378h], r14d
0x18006038b  jbe     short loc_1800603A7
0x18006038d  mov     edx, ecx
0x18006038f  mov     rax, [rbx+380h]
0x180060396  mov     dword ptr [rax+rdx*4], 3F800000h
0x18006039d  inc     ecx
0x18006039f  cmp     ecx, [rbx+378h]
0x1800603a5  jb      short loc_18006038D
0x1800603a7  test    rdi, rdi
0x1800603aa  jz      short loc_1800603B5
0x1800603ac  mov     rcx, rdi; lpCriticalSection
0x1800603af  call    cs:__imp_LeaveCriticalSection
0x1800603b5  and     esi, 2
0x1800603b8  setnz   al
0x1800603bb  mov     [rbx+398h], al
0x1800603c1  mov     rax, [rbp+var_18]
0x1800603c5  cmp     dword ptr [rax+40h], 3
0x1800603c9  jnz     short loc_1800603ED
0x1800603cb  mov     [rbx+398h], r14b
0x1800603d2  mov     rcx, [rbp+pv]; pv
0x1800603d6  mov     [rbp+pv], r14
0x1800603da  test    rcx, rcx
0x1800603dd  jz      short loc_1800603E5
0x1800603df  call    cs:__imp_CoTaskMemFree
0x1800603e5  mov     edi, r14d
0x1800603e8  jmp     loc_1800604B7
0x1800603ed  test    esi, esi
0x1800603ef  jz      short loc_1800603D2
0x1800603f1  lea     rdi, [rbx+3A0h]
0x1800603f8  mov     rcx, [rdi]
0x1800603fb  mov     [rdi], r14
0x1800603fe  test    rcx, rcx
0x180060401  jz      short loc_180060410
0x180060403  mov     rax, [rcx]
0x180060406  mov     rax, [rax+10h]
0x18006040a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006040f  nop
0x180060410  mov     rdx, rdi; struct IPropertyStore **
0x180060413  mov     rcx, rbx; this
0x180060416  call    ?TryOpenSessionPropertyStore@CPerStreamVolumeAudioSession@@AEAAJPEAPEAUIPropertyStore@@@Z; CPerStreamVolumeAudioSession::TryOpenSessionPropertyStore(IPropertyStore * *)
0x18006041b  mov     rcx, [rbp+18h]; this
0x18006041f  mov     [rsp+80h+var_50], 80070005h
0x180060427  mov     [rsp+80h+var_58], 80070002h; unsigned int
0x18006042f  mov     [rsp+80h+var_60], 2; int
0x180060437  mov     r9d, eax; char *
0x18006043a  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180060441  mov     edx, 648h; void *
0x180060446  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x18006044b  test    eax, eax
0x18006044d  js      short loc_1800603D2
0x18006044f  cmp     [rdi], r14
0x180060452  jz      loc_1800603D2
0x180060458  mov     rcx, rbx; this
0x18006045b  call    ?LoadSessionConfiguration@CPerStreamVolumeAudioSession@@AEAAJXZ; CPerStreamVolumeAudioSession::LoadSessionConfiguration(void)
0x180060460  mov     edi, eax
0x180060462  test    eax, eax
0x180060464  jns     loc_1800603D2
0x18006046a  mov     r9d, eax
0x18006046d  mov     edx, 64Ch
0x180060472  jmp     loc_1800602F0
0x180060477  mov     rcx, [rbp+18h]; this
0x18006047b  mov     ebx, 8007000Eh
0x180060480  mov     r9d, ebx; char *
0x180060483  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18006048a  mov     edx, 628h; void *
0x18006048f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060494  test    rdi, rdi
0x180060497  jz      short loc_1800604A2
0x180060499  mov     rcx, rdi; lpCriticalSection
0x18006049c  call    cs:__imp_LeaveCriticalSection
0x1800604a2  mov     rcx, [rbp+pv]; pv
0x1800604a6  mov     [rbp+pv], r14
0x1800604aa  test    rcx, rcx
0x1800604ad  jz      short loc_1800604B5
0x1800604af  call    cs:__imp_CoTaskMemFree
0x1800604b5  mov     edi, ebx
0x1800604b7  lea     rcx, [rbp+var_18]; this
0x1800604bb  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x1800604c0  mov     eax, edi
0x1800604c2  lea     r11, [rsp+80h+var_s0]
0x1800604ca  mov     rbx, [r11+28h]
0x1800604ce  mov     rsi, [r11+30h]
0x1800604d2  mov     rsp, r11
0x1800604d5  pop     r14
0x1800604d7  pop     rdi
0x1800604d8  pop     rbp
0x1800604d9  retn
```
