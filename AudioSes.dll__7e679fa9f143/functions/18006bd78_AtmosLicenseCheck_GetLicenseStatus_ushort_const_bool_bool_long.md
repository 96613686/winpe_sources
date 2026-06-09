# AtmosLicenseCheck::GetLicenseStatus(ushort const *,bool *,bool *,long *)

- ea: `0x18006bd78`
- end: `0x18006bedf`
- name: `?GetLicenseStatus@AtmosLicenseCheck@@AEAAJPEBGPEA_N1PEAJ@Z`
- size: `359`
- prototype: `int(AtmosLicenseCheck *__hidden this, const unsigned __int16 *, bool *, bool *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006bd10`

## callees

- `0x18000276c`
- `0x180010a90`
- `0x18006bd78`
- `0x18007fb40`
- `0x180087e80`
- `0x18010fea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006beba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006beba`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18006be36`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18006be36`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18006be00`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18006be00`

## string_xrefs

- `0x18006be16`: `avcore\codecdsp\audio\common\atmoslicensecheck\atmoslicensecheck.cpp`
- `0x18006be80`: `avcore\codecdsp\audio\common\atmoslicensecheck\atmoslicensecheck.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AtmosLicenseCheck::GetLicenseStatus(
        AtmosLicenseCheck *this,
        const unsigned __int16 *a2,
        bool *a3,
        bool *a4,
        int *a5)
{
  HRESULT v8; // eax
  unsigned int v9; // ebx
  const unsigned __int16 *v10; // rdx
  int refreshed; // eax
  __int64 v12; // rdx
  int v13[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v14; // [rsp+30h] [rbp-D0h]
  __int128 v15; // [rsp+40h] [rbp-C0h]
  GUID pclsid; // [rsp+50h] [rbp-B0h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  *a3 = 0;
  *a4 = 0;
  if ( *((_BYTE *)this + 132) )
  {
    pclsid = GUID_00000000_0000_0000_0000_000000000000;
    v8 = CLSIDFromString(a2, &pclsid);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C1,
        (unsigned int)"avcore\\codecdsp\\audio\\common\\atmoslicensecheck\\atmoslicensecheck.cpp",
        (const char *)(unsigned int)v8,
        v13[0]);
      return v9;
    }
    InitializeCriticalSectionEx(&CriticalSection, 0, 0);
    refreshed = ExtendedSpatialAudioEncoderInfoHelper::RefreshState(&CriticalSection, v10);
    v9 = refreshed;
    if ( refreshed >= 0 )
    {
      v14 = 0;
      v15 = 0;
      refreshed = ExtendedSpatialAudioEncoderInfoHelper::GetExtendedSpatialAudioEncoderInfo(
                    &CriticalSection,
                    &pclsid,
                    (struct ExtendedSpatialAudioEncoderInfo *)v13);
      v9 = refreshed;
      if ( refreshed >= 0 )
      {
        *a3 = DWORD2(v14) != 0;
        *a4 = (_DWORD)v14 != 0;
        *a5 = DWORD2(v15);
        v9 = 0;
        goto LABEL_13;
      }
      v12 = 714;
    }
    else
    {
      v12 = 711;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"avcore\\codecdsp\\audio\\common\\atmoslicensecheck\\atmoslicensecheck.cpp",
      (const char *)(unsigned int)refreshed,
      v13[0]);
LABEL_13:
    DeleteCriticalSection(&CriticalSection);
    return v9;
  }
  if ( (unsigned int)dword_18018A668 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_18018A668,
      &unk_180172E58,
      0,
      0);
  return 0;
}

```

## disassembly

```asm
0x18006bd78  push    rbp
0x18006bd7a  push    rbx
0x18006bd7b  push    rsi
0x18006bd7c  push    rdi
0x18006bd7d  push    r14
0x18006bd7f  lea     rbp, [rsp-0F0h]
0x18006bd87  sub     rsp, 1F0h
0x18006bd8e  mov     rax, cs:__security_cookie
0x18006bd95  xor     rax, rsp
0x18006bd98  mov     [rbp+110h+var_30], rax
0x18006bd9f  mov     rsi, r9
0x18006bda2  mov     rdi, r8
0x18006bda5  mov     rax, rdx
0x18006bda8  mov     r14, [rbp+110h+arg_20]
0x18006bdaf  mov     byte ptr [r8], 0
0x18006bdb3  mov     byte ptr [r9], 0
0x18006bdb7  cmp     byte ptr [rcx+84h], 0
0x18006bdbe  jnz     short loc_18006BDEB
0x18006bdc0  mov     eax, cs:dword_18018A668
0x18006bdc6  cmp     eax, 5
0x18006bdc9  jbe     short loc_18006BDE4
0x18006bdcb  xor     r9d, r9d
0x18006bdce  xor     r8d, r8d
0x18006bdd1  lea     rdx, unk_180172E58
0x18006bdd8  lea     rcx, dword_18018A668
0x18006bddf  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18006bde4  xor     eax, eax
0x18006bde6  jmp     loc_18006BEC2
0x18006bdeb  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18006bdf2  movdqu  xmmword ptr [rsp+210h+pclsid.Data1], xmm0
0x18006bdf8  lea     rdx, [rsp+210h+pclsid]; pclsid
0x18006bdfd  mov     rcx, rax; lpsz
0x18006be00  call    cs:__imp_CLSIDFromString
0x18006be06  mov     ebx, eax
0x18006be08  test    eax, eax
0x18006be0a  jns     short loc_18006BE2C
0x18006be0c  mov     rcx, [rbp+118h]; this
0x18006be13  mov     r9d, eax; char *
0x18006be16  lea     r8, aAvcoreCodecdsp; "avcore\\codecdsp\\audio\\common\\atmosl"...
0x18006be1d  mov     edx, 2C1h; void *
0x18006be22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006be27  jmp     loc_18006BEC0
0x18006be2c  xor     r8d, r8d; Flags
0x18006be2f  xor     edx, edx; dwSpinCount
0x18006be31  lea     rcx, [rsp+210h+CriticalSection]; lpCriticalSection
0x18006be36  call    cs:__imp_InitializeCriticalSectionEx
0x18006be3c  nop
0x18006be3d  lea     rcx, [rsp+210h+CriticalSection]; lpCriticalSection
0x18006be42  call    ?RefreshState@ExtendedSpatialAudioEncoderInfoHelper@@QEAAJPEBG@Z; ExtendedSpatialAudioEncoderInfoHelper::RefreshState(ushort const *)
0x18006be47  mov     ebx, eax
0x18006be49  test    eax, eax
0x18006be4b  jns     short loc_18006BE54
0x18006be4d  mov     edx, 2C7h
0x18006be52  jmp     short loc_18006BE80
0x18006be54  xorps   xmm0, xmm0
0x18006be57  movups  [rsp+210h+var_1E0], xmm0
0x18006be5c  movups  [rsp+210h+var_1D0], xmm0
0x18006be61  lea     r8, [rsp+210h+var_1F0]; struct ExtendedSpatialAudioEncoderInfo *
0x18006be66  lea     rdx, [rsp+210h+pclsid]; struct _GUID *
0x18006be6b  lea     rcx, [rsp+210h+CriticalSection]; lpCriticalSection
0x18006be70  call    ?GetExtendedSpatialAudioEncoderInfo@ExtendedSpatialAudioEncoderInfoHelper@@QEAAJAEBU_GUID@@PEAUExtendedSpatialAudioEncoderInfo@@@Z; ExtendedSpatialAudioEncoderInfoHelper::GetExtendedSpatialAudioEncoderInfo(_GUID const &,ExtendedSpatialAudioEncoderInfo *)
0x18006be75  mov     ebx, eax
0x18006be77  test    eax, eax
0x18006be79  jns     short loc_18006BE98
0x18006be7b  mov     edx, 2CAh; void *
0x18006be80  lea     r8, aAvcoreCodecdsp; "avcore\\codecdsp\\audio\\common\\atmosl"...
0x18006be87  mov     r9d, eax; char *
0x18006be8a  mov     rcx, [rbp+118h]; this
0x18006be91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006be96  jmp     short loc_18006BEB5
0x18006be98  cmp     dword ptr [rsp+210h+var_1E0+8], 0
0x18006be9d  setnz   al
0x18006bea0  mov     [rdi], al
0x18006bea2  cmp     dword ptr [rsp+210h+var_1E0], 0
0x18006bea7  setnz   al
0x18006beaa  mov     [rsi], al
0x18006beac  mov     eax, dword ptr [rsp+210h+var_1D0+8]
0x18006beb0  mov     [r14], eax
0x18006beb3  xor     ebx, ebx
0x18006beb5  lea     rcx, [rsp+210h+CriticalSection]; lpCriticalSection
0x18006beba  call    cs:__imp_DeleteCriticalSection
0x18006bec0  mov     eax, ebx
0x18006bec2  mov     rcx, [rbp+110h+var_30]
0x18006bec9  xor     rcx, rsp; StackCookie
0x18006becc  call    __security_check_cookie
0x18006bed1  add     rsp, 1F0h
0x18006bed8  pop     r14
0x18006beda  pop     rdi
0x18006bedb  pop     rsi
0x18006bedc  pop     rbx
0x18006bedd  pop     rbp
0x18006bede  retn
```
