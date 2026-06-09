# CPerStreamVolumeAudioSession::CompleteConstruction(ulong)

- ea: `0x18005fd80`
- end: `0x18006004a`
- name: `?CompleteConstruction@CPerStreamVolumeAudioSession@@EEAAJK@Z`
- size: `714`
- prototype: `__int64 __fastcall(CPerStreamVolumeAudioSession *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ad20`
- `0x18001280c`
- `0x180015e84`
- `0x18001e92c`
- `0x18001f800`
- `0x18005fd80`
- `0x180069b60`
- `0x180079bb0`
- `0x1800cddac`
- `0x1800e6c2c`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005fe96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005fe96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ff1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006000c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ff1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006000c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005fe4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005fe81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ff4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006001f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005fe4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005fe81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ff4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006001f`

## string_xrefs

- `0x18005fdea`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x18005fe60`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x18005ffaa`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x18005fff3`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`

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
0x18005fd80  mov     [rsp-18h+arg_8], rbx
0x18005fd85  mov     [rsp-18h+arg_10], rsi
0x18005fd8a  push    rbp
0x18005fd8b  push    rdi
0x18005fd8c  push    r14
0x18005fd8e  mov     rbp, rsp
0x18005fd91  sub     rsp, 80h
0x18005fd98  mov     esi, edx
0x18005fd9a  mov     rbx, rcx
0x18005fd9d  xorps   xmm0, xmm0
0x18005fda0  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18005fda5  xor     r14d, r14d
0x18005fda8  mov     [rbp+var_8], r14
0x18005fdac  add     rcx, 248h; this
0x18005fdb3  call    ?GetBuffer@CAudioEndpointId@@QEAAPEBGXZ; CAudioEndpointId::GetBuffer(void)
0x18005fdb8  mov     rdx, rax
0x18005fdbb  mov     rcx, cs:?g_pEndpointCharacteristicsCache@@3PEAUIEndpointCharacteristicsCache@@EA; IEndpointCharacteristicsCache * g_pEndpointCharacteristicsCache
0x18005fdc2  mov     r8, [rcx]
0x18005fdc5  mov     rax, [r8+28h]
0x18005fdc9  lea     r8, [rbp+var_18]
0x18005fdcd  mov     qword ptr [rsp+80h+var_60], r8; int
0x18005fdd2  xor     r9d, r9d
0x18005fdd5  xor     r8d, r8d
0x18005fdd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fddd  mov     edi, eax
0x18005fddf  test    eax, eax
0x18005fde1  jns     short loc_18005FE00
0x18005fde3  mov     rcx, [rbp+18h]; this
0x18005fde7  mov     r9d, eax; char *
0x18005fdea  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18005fdf1  mov     edx, 616h; void *
0x18005fdf6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005fdfb  jmp     loc_180060027
0x18005fe00  mov     [rbp+pv], r14
0x18005fe04  lea     rax, [rbp+pv]
0x18005fe08  mov     [rbp+var_30], rax
0x18005fe0c  mov     [rbp+var_28], r14
0x18005fe10  mov     [rbp+var_20], 1
0x18005fe14  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18005fe1b  movdqu  xmmword ptr [rbp+var_40.Data1], xmm0
0x18005fe20  lea     r9, [rbp+var_28]; struct tWAVEFORMATEX **
0x18005fe24  lea     r8, [rbp+var_40]; struct _GUID
0x18005fe28  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18005fe2a  mov     rcx, [rbp+var_18+8]; this
0x18005fe2e  call    ?GetMixFormat@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetMixFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x18005fe33  mov     edi, eax
0x18005fe35  cmp     [rbp+var_20], r14b
0x18005fe39  jz      short loc_18005FE54
0x18005fe3b  mov     r8, [rbp+var_30]
0x18005fe3f  mov     rcx, [r8]; pv
0x18005fe42  mov     rdx, [rbp+var_28]
0x18005fe46  mov     [r8], rdx
0x18005fe49  test    rcx, rcx
0x18005fe4c  jz      short loc_18005FE54
0x18005fe4e  call    cs:__imp_CoTaskMemFree
0x18005fe54  test    edi, edi
0x18005fe56  jns     short loc_18005FE8C
0x18005fe58  mov     r9d, edi; char *
0x18005fe5b  mov     edx, 620h; void *
0x18005fe60  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18005fe67  mov     rcx, [rbp+18h]; this
0x18005fe6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005fe70  mov     rcx, [rbp+pv]; pv
0x18005fe74  mov     [rbp+pv], r14
0x18005fe78  test    rcx, rcx
0x18005fe7b  jz      loc_180060027
0x18005fe81  call    cs:__imp_CoTaskMemFree
0x18005fe87  jmp     loc_180060027
0x18005fe8c  lea     rdi, [rbx+2E0h]
0x18005fe93  mov     rcx, rdi; lpCriticalSection
0x18005fe96  call    cs:__imp_EnterCriticalSection
0x18005fe9c  mov     rax, [rbp+pv]
0x18005fea0  movzx   ecx, word ptr [rax+2]
0x18005fea4  mov     [rbx+378h], ecx
0x18005feaa  mov     eax, 4
0x18005feaf  mul     rcx
0x18005feb2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005feb9  cmovb   rax, rcx
0x18005febd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005fec4  mov     rcx, rax; unsigned __int64
0x18005fec7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005fecc  mov     rcx, [rbx+380h]; void *
0x18005fed3  mov     [rbx+380h], rax
0x18005feda  test    rcx, rcx
0x18005fedd  jz      short loc_18005FEE4
0x18005fedf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005fee4  cmp     [rbx+380h], r14
0x18005feeb  jz      loc_18005FFE7
0x18005fef1  mov     ecx, r14d
0x18005fef4  cmp     [rbx+378h], r14d
0x18005fefb  jbe     short loc_18005FF17
0x18005fefd  mov     edx, ecx
0x18005feff  mov     rax, [rbx+380h]
0x18005ff06  mov     dword ptr [rax+rdx*4], 3F800000h
0x18005ff0d  inc     ecx
0x18005ff0f  cmp     ecx, [rbx+378h]
0x18005ff15  jb      short loc_18005FEFD
0x18005ff17  test    rdi, rdi
0x18005ff1a  jz      short loc_18005FF25
0x18005ff1c  mov     rcx, rdi; lpCriticalSection
0x18005ff1f  call    cs:__imp_LeaveCriticalSection
0x18005ff25  and     esi, 2
0x18005ff28  setnz   al
0x18005ff2b  mov     [rbx+398h], al
0x18005ff31  mov     rax, [rbp+var_18]
0x18005ff35  cmp     dword ptr [rax+40h], 3
0x18005ff39  jnz     short loc_18005FF5D
0x18005ff3b  mov     [rbx+398h], r14b
0x18005ff42  mov     rcx, [rbp+pv]; pv
0x18005ff46  mov     [rbp+pv], r14
0x18005ff4a  test    rcx, rcx
0x18005ff4d  jz      short loc_18005FF55
0x18005ff4f  call    cs:__imp_CoTaskMemFree
0x18005ff55  mov     edi, r14d
0x18005ff58  jmp     loc_180060027
0x18005ff5d  test    esi, esi
0x18005ff5f  jz      short loc_18005FF42
0x18005ff61  lea     rdi, [rbx+3A0h]
0x18005ff68  mov     rcx, [rdi]
0x18005ff6b  mov     [rdi], r14
0x18005ff6e  test    rcx, rcx
0x18005ff71  jz      short loc_18005FF80
0x18005ff73  mov     rax, [rcx]
0x18005ff76  mov     rax, [rax+10h]
0x18005ff7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ff7f  nop
0x18005ff80  mov     rdx, rdi; struct IPropertyStore **
0x18005ff83  mov     rcx, rbx; this
0x18005ff86  call    ?TryOpenSessionPropertyStore@CPerStreamVolumeAudioSession@@AEAAJPEAPEAUIPropertyStore@@@Z; CPerStreamVolumeAudioSession::TryOpenSessionPropertyStore(IPropertyStore * *)
0x18005ff8b  mov     rcx, [rbp+18h]; this
0x18005ff8f  mov     [rsp+80h+var_50], 80070005h
0x18005ff97  mov     [rsp+80h+var_58], 80070002h; unsigned int
0x18005ff9f  mov     [rsp+80h+var_60], 2; int
0x18005ffa7  mov     r9d, eax; char *
0x18005ffaa  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18005ffb1  mov     edx, 648h; void *
0x18005ffb6  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x18005ffbb  test    eax, eax
0x18005ffbd  js      short loc_18005FF42
0x18005ffbf  cmp     [rdi], r14
0x18005ffc2  jz      loc_18005FF42
0x18005ffc8  mov     rcx, rbx; this
0x18005ffcb  call    ?LoadSessionConfiguration@CPerStreamVolumeAudioSession@@AEAAJXZ; CPerStreamVolumeAudioSession::LoadSessionConfiguration(void)
0x18005ffd0  mov     edi, eax
0x18005ffd2  test    eax, eax
0x18005ffd4  jns     loc_18005FF42
0x18005ffda  mov     r9d, eax
0x18005ffdd  mov     edx, 64Ch
0x18005ffe2  jmp     loc_18005FE60
0x18005ffe7  mov     rcx, [rbp+18h]; this
0x18005ffeb  mov     ebx, 8007000Eh
0x18005fff0  mov     r9d, ebx; char *
0x18005fff3  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18005fffa  mov     edx, 628h; void *
0x18005ffff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060004  test    rdi, rdi
0x180060007  jz      short loc_180060012
0x180060009  mov     rcx, rdi; lpCriticalSection
0x18006000c  call    cs:__imp_LeaveCriticalSection
0x180060012  mov     rcx, [rbp+pv]; pv
0x180060016  mov     [rbp+pv], r14
0x18006001a  test    rcx, rcx
0x18006001d  jz      short loc_180060025
0x18006001f  call    cs:__imp_CoTaskMemFree
0x180060025  mov     edi, ebx
0x180060027  lea     rcx, [rbp+var_18]; this
0x18006002b  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x180060030  mov     eax, edi
0x180060032  lea     r11, [rsp+80h+var_s0]
0x18006003a  mov     rbx, [r11+28h]
0x18006003e  mov     rsi, [r11+30h]
0x180060042  mov     rsp, r11
0x180060045  pop     r14
0x180060047  pop     rdi
0x180060048  pop     rbp
0x180060049  retn
```
