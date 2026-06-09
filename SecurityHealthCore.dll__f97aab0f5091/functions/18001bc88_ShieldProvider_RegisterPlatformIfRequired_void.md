# ShieldProvider::RegisterPlatformIfRequired(void)

- ea: `0x18001bc88`
- end: `0x18001c049`
- name: `?RegisterPlatformIfRequired@ShieldProvider@@YAJXZ`
- size: `961`
- prototype: `__int64 __fastcall(ShieldProvider *this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000fad8`

## callees

- `0x180001a1c`
- `0x180001d04`
- `0x180004710`
- `0x180004ae0`
- `0x18000d7fc`
- `0x18000e3ec`
- `0x18000e5f4`
- `0x18000e9bc`
- `0x18000ecb8`
- `0x18000eda4`
- `0x180010ff0`
- `0x180019f1c`
- `0x18001b4a8`
- `0x18001b594`
- `0x18001b76c`
- `0x18001b800`
- `0x18001bc88`
- `0x18001c75c`
- `0x18001c9f8`
- `0x18001cca4`
- `0x1800cebd8`
- `0x1800dadb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001bd8e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001bd8e`
- `ole32!CoCreateGuid` at `0x18001bfa1`
- `ole32!CoCreateGuid` at `0x18001bfa1`

## string_xrefs

- `0x18001bd28`: `SOFTWARE\Microsoft\Windows Security Health\Platform`
- `0x18001bd6a`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\service\utils.cpp`
- `0x18001bffd`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\service\utils.cpp`

## pseudocode

```c
__int64 __fastcall ShieldProvider::RegisterPlatformIfRequired(ShieldProvider *this, unsigned __int16 **a2)
{
  int InstallLocation; // eax
  const struct std::nothrow_t *v3; // rdx
  unsigned int v4; // ebx
  wchar_t *v6; // rbx
  unsigned int v7; // r9d
  unsigned int ConfigDword; // r13d
  ShieldProvider *v9; // rcx
  unsigned __int8 v10; // r15
  bool v11; // si
  int v12; // eax
  int v13; // r12d
  wchar_t *v14; // rax
  const unsigned __int16 *v15; // rdx
  unsigned __int16 **v16; // r9
  const OLECHAR *v17; // r14
  ShieldProvider *v18; // rcx
  int v19; // eax
  const struct std::nothrow_t *v20; // rdx
  const unsigned __int16 *v21; // r9
  ShieldProvider *v22; // rcx
  int v23; // esi
  int v24; // r8d
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  ShieldProvider *v27; // rcx
  unsigned __int64 v28; // r9
  const struct std::nothrow_t *v29; // rdx
  int v30; // eax
  const struct std::nothrow_t *v31; // rdx
  const struct _GUID *v32; // r8
  const unsigned __int16 *v33; // r9
  __int64 v34; // rdx
  ShieldProvider *v35; // rcx
  const unsigned __int16 *v36; // r9
  unsigned __int16 *v37; // [rsp+20h] [rbp-59h]
  char v38; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int8 IsBinaryDifferentFromLastKnownGood; // [rsp+51h] [rbp-28h]
  wchar_t *Str; // [rsp+58h] [rbp-21h] BYREF
  int v41; // [rsp+60h] [rbp-19h] BYREF
  int v42; // [rsp+64h] [rbp-15h] BYREF
  int v43; // [rsp+68h] [rbp-11h] BYREF
  BOOL v44; // [rsp+6Ch] [rbp-Dh] BYREF
  GUID pguid; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  Str = 0;
  InstallLocation = ShieldProvider::GetInstallLocation((ShieldProvider *)&Str, a2);
  v4 = InstallLocation;
  if ( InstallLocation < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        &WPP_000ecca967ad310820d6b0106919f4ce_Traceguids,
        (unsigned int)InstallLocation);
    if ( Str )
      operator delete(Str, v3);
    return v4;
  }
  v6 = Str;
  IsBinaryDifferentFromLastKnownGood = ShieldProvider::IsBinaryDifferentFromLastKnownGood(Str);
  ConfigDword = ShieldProvider::GetConfigDword(
                  (ShieldProvider *)L"SOFTWARE\\Microsoft\\Windows Security Health\\Platform",
                  (const unsigned __int16 *)&stru_1800F5338,
                  0,
                  v7);
  v10 = !ShieldProvider::SanityCheckPlatformDCOMEntriesRegistered(v9);
  v11 = IsBinaryDifferentFromLastKnownGood || !ConfigDword || v10;
  v12 = ShieldProvider::RegisterMamProtocolIfRequired(v6);
  if ( v12 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xE6,
      (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\service\\utils.cpp",
      (const char *)(unsigned int)v12,
      (int)v37);
  v13 = (unsigned __int8)g_fDefaultBits;
  v14 = wcsrchr(v6, 0x5Cu);
  if ( v14 )
    v17 = v14 + 1;
  else
    v17 = &word_1800F4E78;
  v18 = (ShieldProvider *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_dddddS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v15,
      ConfigDword == 0,
      v11,
      IsBinaryDifferentFromLastKnownGood,
      ConfigDword == 0,
      v10,
      v13,
      (__int64)v17);
  if ( !(_BYTE)v13 && !ShieldProvider::GetMiscFlagIfApplicable((ShieldProvider *)L"IgnoreDowngrade", v15) )
  {
    v38 = 0;
    if ( (int)ShieldProvider::GetIsRunningDowngradedBits(&v38) >= 0 )
    {
      if ( v38 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_000ecca967ad310820d6b0106919f4ce_Traceguids);
        ShieldProvider::StopPlatform((ShieldProvider *)2, (unsigned int)v15);
      }
    }
  }
  if ( v11 )
  {
    v19 = ShieldProvider::RegisterPlatform((ShieldProvider *)v6, v15);
    v22 = (ShieldProvider *)(unsigned int)dword_18012F2B8;
    v23 = v19;
    if ( (unsigned int)dword_18012F2B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18012F2B8, 0x800000000000LL) )
    {
      v43 = v10;
      v41 = v23;
      *(_QWORD *)&pguid.Data1 = v17;
      v42 = v13;
      v44 = ConfigDword == 0;
      LODWORD(Str) = IsBinaryDifferentFromLastKnownGood;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v22,
        (unsigned int)&word_18012146E,
        v24,
        (_DWORD)v21,
        (__int64)&Str,
        (__int64)&v44,
        (__int64)&v43,
        (__int64)&v42,
        (__int64)&pguid,
        (__int64)&v41);
    }
    if ( v23 < 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_38;
      v26 = 25;
LABEL_37:
      WPP_SF_d(v25[2], v26, &WPP_000ecca967ad310820d6b0106919f4ce_Traceguids, (unsigned int)v23);
LABEL_38:
      if ( v6 )
        operator delete(v6, v20);
      return (unsigned int)v23;
    }
    v23 = ShieldProvider::SetConfigString(v22, L"CoreLocation", v6, v21);
    if ( v23 < 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_38;
      v26 = 26;
      goto LABEL_37;
    }
    ShieldProvider::SetConfigQword(v27, L"Features", ShieldProvider::FEATURE_ALL, v28);
  }
  Str = 0;
  if ( (int)ShieldProvider::GetConfigString(v18, L"PlatformId", (unsigned __int16 *)&Str, v16) < 0 )
  {
    pguid = 0;
    v30 = CoCreateGuid(&pguid);
    if ( v30 < 0 )
    {
      v34 = 288;
LABEL_55:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\service\\utils.cpp",
        (const char *)(unsigned int)v30,
        (int)v37);
      goto LABEL_56;
    }
    if ( Str )
    {
      operator delete(Str, v31);
      Str = 0;
    }
    v30 = CommonUtil::UtilFormatStringFromUuid((CommonUtil *)&Str, (unsigned __int16 **)&pguid, v32, v33, v37);
    if ( v30 < 0 )
    {
      v34 = 292;
      goto LABEL_55;
    }
    v30 = ShieldProvider::SetConfigString(v35, L"PlatformId", Str, v36);
    if ( v30 < 0 )
    {
      v34 = 297;
      goto LABEL_55;
    }
  }
LABEL_56:
  if ( Str )
    operator delete(Str, v29);
  if ( v6 )
    operator delete(v6, v29);
  return 0;
}

```

## disassembly

```asm
0x18001bc88  push    rbp
0x18001bc8a  push    rbx
0x18001bc8b  push    rsi
0x18001bc8c  push    rdi
0x18001bc8d  push    r12
0x18001bc8f  push    r13
0x18001bc91  push    r14
0x18001bc93  push    r15
0x18001bc95  lea     rbp, [rsp-1Fh]
0x18001bc9a  sub     rsp, 98h
0x18001bca1  mov     rax, cs:__security_cookie
0x18001bca8  xor     rax, rsp
0x18001bcab  mov     [rbp+57h+var_50], rax
0x18001bcaf  lea     rcx, [rbp+57h+Str]; this
0x18001bcb3  mov     [rbp+57h+Str], 0
0x18001bcbb  call    ?GetInstallLocation@ShieldProvider@@YAJPEAPEAG@Z; ShieldProvider::GetInstallLocation(ushort * *)
0x18001bcc0  mov     ebx, eax
0x18001bcc2  test    eax, eax
0x18001bcc4  jns     short loc_18001BD0C
0x18001bcc6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bccd  lea     rdi, WPP_GLOBAL_Control
0x18001bcd4  cmp     rcx, rdi
0x18001bcd7  jz      short loc_18001BCF7
0x18001bcd9  test    byte ptr [rcx+1Ch], 1
0x18001bcdd  jz      short loc_18001BCF7
0x18001bcdf  mov     rcx, [rcx+10h]
0x18001bce3  lea     r8, WPP_000ecca967ad310820d6b0106919f4ce_Traceguids
0x18001bcea  mov     edx, 16h
0x18001bcef  mov     r9d, eax
0x18001bcf2  call    WPP_SF_d
0x18001bcf7  mov     rcx, [rbp+57h+Str]; void *
0x18001bcfb  test    rcx, rcx
0x18001bcfe  jz      short loc_18001BD05
0x18001bd00  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001bd05  mov     eax, ebx
0x18001bd07  jmp     loc_18001C029
0x18001bd0c  mov     rbx, [rbp+57h+Str]
0x18001bd10  mov     rcx, rbx; String2
0x18001bd13  call    ShieldProvider__IsBinaryDifferentFromLastKnownGood
0x18001bd18  xor     r8d, r8d; unsigned __int16 *
0x18001bd1b  mov     [rbp+57h+var_7F], al
0x18001bd1e  lea     rdx, stru_1800F5338; unsigned __int16 *
0x18001bd25  mov     dil, al
0x18001bd28  lea     rcx, aSoftwareMicros_25; "SOFTWARE\\Microsoft\\Windows Security H"...
0x18001bd2f  call    ?GetConfigDword@ShieldProvider@@YAKPEBG0K@Z; ShieldProvider::GetConfigDword(ushort const *,ushort const *,ulong)
0x18001bd34  mov     r13d, eax
0x18001bd37  call    ?SanityCheckPlatformDCOMEntriesRegistered@ShieldProvider@@YA_NXZ; ShieldProvider::SanityCheckPlatformDCOMEntriesRegistered(void)
0x18001bd3c  mov     r15b, al
0x18001bd3f  xor     r15b, 1
0x18001bd43  test    dil, dil
0x18001bd46  jnz     short loc_18001BD57
0x18001bd48  test    r13d, r13d
0x18001bd4b  jz      short loc_18001BD57
0x18001bd4d  test    r15b, r15b
0x18001bd50  jnz     short loc_18001BD57
0x18001bd52  xor     sil, sil
0x18001bd55  jmp     short loc_18001BD5A
0x18001bd57  mov     sil, 1
0x18001bd5a  mov     rcx, rbx
0x18001bd5d  call    ShieldProvider__RegisterMamProtocolIfRequired
0x18001bd62  test    eax, eax
0x18001bd64  jns     short loc_18001BD7E
0x18001bd66  mov     rcx, [rbp+5Fh]; this
0x18001bd6a  lea     r8, aOnecoreAmcoreA_7; "onecore\\amcore\\antimalware\\source\\s"...
0x18001bd71  mov     r9d, eax; char *
0x18001bd74  mov     edx, 0E6h; void *
0x18001bd79  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001bd7e  movzx   r12d, cs:?g_fDefaultBits@@3_NA; bool g_fDefaultBits
0x18001bd86  mov     edx, 5Ch ; '\'; Ch
0x18001bd8b  mov     rcx, rbx; Str
0x18001bd8e  call    cs:__imp_wcsrchr
0x18001bd94  mov     r14, rax
0x18001bd97  test    rax, rax
0x18001bd9a  jz      short loc_18001BDA2
0x18001bd9c  add     r14, 2
0x18001bda0  jmp     short loc_18001BDA9
0x18001bda2  lea     r14, word_1800F4E78
0x18001bda9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bdb0  lea     rdi, WPP_GLOBAL_Control
0x18001bdb7  cmp     rcx, rdi
0x18001bdba  jz      short loc_18001BDF9
0x18001bdbc  test    byte ptr [rcx+1Ch], 4
0x18001bdc0  jz      short loc_18001BDF9
0x18001bdc2  movzx   eax, [rbp+57h+var_7F]
0x18001bdc6  xor     r8d, r8d
0x18001bdc9  mov     rcx, [rcx+10h]
0x18001bdcd  test    r13d, r13d
0x18001bdd0  mov     [rsp+0D0h+var_90], r14
0x18001bdd5  mov     dword ptr [rsp+0D0h+var_98], r12d
0x18001bdda  setz    r8b
0x18001bdde  movzx   r10d, r15b
0x18001bde2  mov     dword ptr [rsp+0D0h+var_A0], r10d
0x18001bde7  mov     dword ptr [rsp+0D0h+var_A8], r8d
0x18001bdec  movzx   r9d, sil
0x18001bdf0  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18001bdf4  call    WPP_SF_dddddS
0x18001bdf9  test    r12b, r12b
0x18001bdfc  jnz     short loc_18001BE55
0x18001bdfe  lea     rcx, aIgnoredowngrad; "IgnoreDowngrade"
0x18001be05  call    ?GetMiscFlagIfApplicable@ShieldProvider@@YA_NPEBG@Z; ShieldProvider::GetMiscFlagIfApplicable(ushort const *)
0x18001be0a  test    al, al
0x18001be0c  jnz     short loc_18001BE55
0x18001be0e  lea     rcx, [rbp+57h+var_80]
0x18001be12  mov     [rbp+57h+var_80], al
0x18001be15  call    ShieldProvider__GetIsRunningDowngradedBits
0x18001be1a  test    eax, eax
0x18001be1c  js      short loc_18001BE55
0x18001be1e  cmp     [rbp+57h+var_80], r12b
0x18001be22  jz      short loc_18001BE55
0x18001be24  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be2b  cmp     rcx, rdi
0x18001be2e  jz      short loc_18001BE4B
0x18001be30  test    byte ptr [rcx+1Ch], 2
0x18001be34  jz      short loc_18001BE4B
0x18001be36  mov     rcx, [rcx+10h]
0x18001be3a  lea     r8, WPP_000ecca967ad310820d6b0106919f4ce_Traceguids
0x18001be41  mov     edx, 18h
0x18001be46  call    WPP_SF_
0x18001be4b  mov     ecx, 2; this
0x18001be50  call    ?StopPlatform@ShieldProvider@@YAXK@Z; ShieldProvider::StopPlatform(ulong)
0x18001be55  test    sil, sil
0x18001be58  jz      loc_18001BF7A
0x18001be5e  mov     rcx, rbx; this
0x18001be61  call    ?RegisterPlatform@ShieldProvider@@YAJPEBG@Z; ShieldProvider::RegisterPlatform(ushort const *)
0x18001be66  mov     ecx, cs:dword_18012F2B8
0x18001be6c  mov     esi, eax
0x18001be6e  cmp     ecx, 5
0x18001be71  jbe     loc_18001BEF7
0x18001be77  mov     rdx, 800000000000h
0x18001be81  lea     rcx, dword_18012F2B8
0x18001be88  call    _tlgKeywordOn
0x18001be8d  test    al, al
0x18001be8f  jz      short loc_18001BEF7
0x18001be91  movzx   eax, r15b
0x18001be95  lea     rdx, word_18012146E
0x18001be9c  mov     [rbp+57h+var_68], eax
0x18001be9f  xor     eax, eax
0x18001bea1  test    r13d, r13d
0x18001bea4  mov     [rbp+57h+var_70], esi
0x18001bea7  mov     qword ptr [rbp+57h+pguid.Data1], r14
0x18001beab  setz    al
0x18001beae  mov     [rbp+57h+var_6C], r12d
0x18001beb2  mov     [rbp+57h+var_64], eax
0x18001beb5  movzx   eax, [rbp+57h+var_7F]
0x18001beb9  mov     dword ptr [rbp+57h+Str], eax
0x18001bebc  lea     rax, [rbp+57h+var_70]
0x18001bec0  mov     [rsp+0D0h+var_88], rax
0x18001bec5  lea     rax, [rbp+57h+pguid]
0x18001bec9  mov     [rsp+0D0h+var_90], rax
0x18001bece  lea     rax, [rbp+57h+var_6C]
0x18001bed2  mov     [rsp+0D0h+var_98], rax
0x18001bed7  lea     rax, [rbp+57h+var_68]
0x18001bedb  mov     [rsp+0D0h+var_A0], rax
0x18001bee0  lea     rax, [rbp+57h+var_64]
0x18001bee4  mov     [rsp+0D0h+var_A8], rax
0x18001bee9  lea     rax, [rbp+57h+Str]
0x18001beed  mov     [rsp+0D0h+var_B0], rax; int
0x18001bef2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001bef7  test    esi, esi
0x18001bef9  jns     short loc_18001BF39
0x18001befb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf02  cmp     rcx, rdi
0x18001bf05  jz      short loc_18001BF25
0x18001bf07  test    byte ptr [rcx+1Ch], 1
0x18001bf0b  jz      short loc_18001BF25
0x18001bf0d  mov     edx, 19h
0x18001bf12  mov     rcx, [rcx+10h]
0x18001bf16  lea     r8, WPP_000ecca967ad310820d6b0106919f4ce_Traceguids
0x18001bf1d  mov     r9d, esi
0x18001bf20  call    WPP_SF_d
0x18001bf25  test    rbx, rbx
0x18001bf28  jz      short loc_18001BF32
0x18001bf2a  mov     rcx, rbx; void *
0x18001bf2d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001bf32  mov     eax, esi
0x18001bf34  jmp     loc_18001C029
0x18001bf39  mov     r8, rbx; unsigned __int16 *
0x18001bf3c  lea     rdx, aCorelocation; "CoreLocation"
0x18001bf43  call    ?SetConfigString@ShieldProvider@@YAJPEBG00@Z; ShieldProvider::SetConfigString(ushort const *,ushort const *,ushort const *)
0x18001bf48  mov     esi, eax
0x18001bf4a  test    eax, eax
0x18001bf4c  jns     short loc_18001BF67
0x18001bf4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf55  cmp     rcx, rdi
0x18001bf58  jz      short loc_18001BF25
0x18001bf5a  test    byte ptr [rcx+1Ch], 1
0x18001bf5e  jz      short loc_18001BF25
0x18001bf60  mov     edx, 1Ah
0x18001bf65  jmp     short loc_18001BF12
0x18001bf67  mov     r8, cs:?FEATURE_ALL@ShieldProvider@@3_KA; unsigned __int16 *
0x18001bf6e  lea     rdx, aFeatures; "Features"
0x18001bf75  call    ?SetConfigQword@ShieldProvider@@YAJPEBG0_K@Z; ShieldProvider::SetConfigQword(ushort const *,ushort const *,unsigned __int64)
0x18001bf7a  lea     r8, [rbp+57h+Str]; unsigned __int16 *
0x18001bf7e  mov     [rbp+57h+Str], 0
0x18001bf86  lea     rdx, aPlatformid; "PlatformId"
0x18001bf8d  call    ?GetConfigString@ShieldProvider@@YAJPEBG0PEAPEAG@Z; ShieldProvider::GetConfigString(ushort const *,ushort const *,ushort * *)
0x18001bf92  test    eax, eax
0x18001bf94  jns     short loc_18001C00C
0x18001bf96  xorps   xmm0, xmm0
0x18001bf99  lea     rcx, [rbp+57h+pguid]; pguid
0x18001bf9d  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x18001bfa1  call    cs:__imp_CoCreateGuid
0x18001bfa7  test    eax, eax
0x18001bfa9  jns     short loc_18001BFB2
0x18001bfab  mov     edx, 120h
0x18001bfb0  jmp     short loc_18001BFF9
0x18001bfb2  mov     rcx, [rbp+57h+Str]; void *
0x18001bfb6  test    rcx, rcx
0x18001bfb9  jz      short loc_18001BFC8
0x18001bfbb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001bfc0  mov     [rbp+57h+Str], 0
0x18001bfc8  lea     rdx, [rbp+57h+pguid]; unsigned __int16 **
0x18001bfcc  lea     rcx, [rbp+57h+Str]; this
0x18001bfd0  call    ?UtilFormatStringFromUuid@CommonUtil@@YAJPEAPEAGAEBU_GUID@@PEBG2@Z; CommonUtil::UtilFormatStringFromUuid(ushort * *,_GUID const &,ushort const *,ushort const *)
0x18001bfd5  test    eax, eax
0x18001bfd7  jns     short loc_18001BFE0
0x18001bfd9  mov     edx, 124h
0x18001bfde  jmp     short loc_18001BFF9
0x18001bfe0  mov     r8, [rbp+57h+Str]; unsigned __int16 *
0x18001bfe4  lea     rdx, aPlatformid; "PlatformId"
0x18001bfeb  call    ?SetConfigString@ShieldProvider@@YAJPEBG00@Z; ShieldProvider::SetConfigString(ushort const *,ushort const *,ushort const *)
0x18001bff0  test    eax, eax
0x18001bff2  jns     short loc_18001C00C
0x18001bff4  mov     edx, 129h; void *
0x18001bff9  mov     rcx, [rbp+5Fh]; this
0x18001bffd  lea     r8, aOnecoreAmcoreA_7; "onecore\\amcore\\antimalware\\source\\s"...
0x18001c004  mov     r9d, eax; char *
0x18001c007  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c00c  mov     rcx, [rbp+57h+Str]; void *
0x18001c010  test    rcx, rcx
0x18001c013  jz      short loc_18001C01A
0x18001c015  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c01a  test    rbx, rbx
0x18001c01d  jz      short loc_18001C027
0x18001c01f  mov     rcx, rbx; void *
0x18001c022  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c027  xor     eax, eax
0x18001c029  mov     rcx, [rbp+57h+var_50]
0x18001c02d  xor     rcx, rsp; StackCookie
0x18001c030  call    __security_check_cookie
0x18001c035  add     rsp, 98h
0x18001c03c  pop     r15
0x18001c03e  pop     r14
0x18001c040  pop     r13
0x18001c042  pop     r12
0x18001c044  pop     rdi
0x18001c045  pop     rsi
0x18001c046  pop     rbx
0x18001c047  pop     rbp
0x18001c048  retn
```
