# NgcKspServer::NgcUserIdKey::Finalize(void * const,bool)

- ea: `0x18007a8d0`
- end: `0x18007ad59`
- name: `?Finalize@NgcUserIdKey@NgcKspServer@@UEAAJQEAX_N@Z`
- size: `1161`
- prototype: `__int64 __fastcall(NgcKspServer::NgcUserIdKey *__hidden this, void *const, bool)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180021690`
- `0x1800281e0`
- `0x1800288a0`
- `0x180028d18`
- `0x180038764`
- `0x18003d8c0`
- `0x18003e12c`
- `0x180046d90`
- `0x180048394`
- `0x18005cee0`
- `0x18005dd2c`
- `0x18005dd44`
- `0x18005fef4`
- `0x1800787f4`
- `0x18007a8d0`
- `0x1800c4090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007a939`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007a939`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007a9c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007ac83`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007ad1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007a9c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007ac83`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007ad1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ab18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ac40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ab18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ac40`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007aa7d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007aa7d`
- `ntdll!RtlPublishWnfStateData` at `0x18007abf4`
- `ntdll!RtlPublishWnfStateData` at `0x18007abf4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007ab72`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007ab72`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioRemoveCredential` at `0x18007aac9`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioRemoveCredential` at `0x18007aac9`

## string_xrefs

- `0x18007acc4`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcKspServer::NgcUserIdKey::Finalize(NgcKspServer::NgcUserIdKey *this, void *const a2, bool a3)
{
  WCHAR *v5; // rsi
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // edi
  __int64 v10; // r8
  HRESULT v11; // eax
  unsigned __int8 *v12; // rdx
  int v13; // r10d
  int v14; // eax
  unsigned __int8 *v15; // rdx
  int v17; // [rsp+20h] [rbp-E0h]
  bool v18; // [rsp+30h] [rbp-D0h] BYREF
  DWORD LastError; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v20; // [rsp+3Ch] [rbp-C4h] BYREF
  __int16 v21; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v24[4]; // [rsp+58h] [rbp-A8h] BYREF
  char v25; // [rsp+78h] [rbp-88h]
  WINBIO_IDENTITY Identity; // [rsp+80h] [rbp-80h] BYREF
  _BYTE Src[2160]; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD pDestinationSid[3]; // [rsp+940h] [rbp+840h] BYREF
  _OWORD v29[2]; // [rsp+970h] [rbp+870h]
  int v30; // [rsp+990h] [rbp+890h] BYREF
  unsigned __int16 v31[1076]; // [rsp+994h] [rbp+894h] BYREF
  char v32; // [rsp+11FCh] [rbp+10FCh]
  wil::details::in1diag3 *retaddr; // [rsp+1228h] [rbp+1128h]

  v18 = a3;
  v20 = 0;
  v24[1] = this;
  v24[2] = &v18;
  v24[3] = &v20;
  v25 = 1;
  v5 = (WCHAR *)((char *)this + 272);
  AcquireSRWLockExclusive((PSRWLOCK)this + 34);
  StringSid = v5;
  if ( *((_BYTE *)this + 297) && !*((_BYTE *)this + 296) )
  {
    v23 = 0;
    v21 = *(_WORD *)((char *)this + 585);
    v24[0] = &v21;
    LOBYTE(v6) = v18;
    v9 = NgcKspServer::NgcUserIdKey::PerformOperationWithGesture(this, a2, v6, 8, v24, &v23);
    v10 = (unsigned int)v9;
    v20 = v9;
    if ( v9 < 0 )
    {
      if ( v5 )
      {
        ReleaseSRWLockExclusive((PSRWLOCK)v5);
        LODWORD(v10) = v20;
      }
      goto LABEL_43;
    }
    if ( (unsigned int)dword_180122070 > 4 && (unsigned __int8)tlgKeywordOn(&dword_180122070, 0x200000000000LL) )
    {
      LastError = v20;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_180103F4B,
        0,
        0,
        (__int64)&LastError);
    }
    *((_BYTE *)this + 296) = 1;
    if ( *((_BYTE *)this + 368) && (unsigned __int8)IsWinBioRemoveCredentialPresent(v8, v7, v10) )
    {
      memset_0(pDestinationSid, 0, 0x4Cu);
      LODWORD(pDestinationSid[0]) = 3;
      if ( !CopySid(0x44u, (char *)pDestinationSid + 8, *((PSID *)this + 4)) )
      {
        if ( (unsigned int)dword_180122070 <= 3 )
          goto LABEL_22;
        LastError = GetLastError();
        v12 = (unsigned __int8 *)byte_180103EBB;
        goto LABEL_21;
      }
      *(_OWORD *)&Identity.Type = pDestinationSid[0];
      *(_OWORD *)&Identity.Value.AccountSid.Data[8] = pDestinationSid[1];
      *(_OWORD *)&Identity.Value.AccountSid.Data[24] = pDestinationSid[2];
      *(_OWORD *)&Identity.Value.AccountSid.Data[40] = v29[0];
      *(_OWORD *)&Identity.Value.AccountSid.Data[52] = *(_OWORD *)((char *)v29 + 12);
      v11 = WinBioRemoveCredential(&Identity, WINBIO_CREDENTIAL_ALL);
      if ( v11 >= 0 )
      {
        if ( (unsigned int)dword_180122070 <= 4 )
          goto LABEL_22;
        LastError = v11;
        v12 = (unsigned __int8 *)&dword_180103F14;
        goto LABEL_21;
      }
      if ( v11 != -2146861007 && (unsigned int)dword_180122070 > 3 )
      {
        LastError = v11;
        v12 = (unsigned __int8 *)&unk_180103EE0;
LABEL_21:
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          v12,
          0,
          0,
          (__int64)&LastError);
      }
    }
LABEL_22:
    if ( NgcKspServer::NgcUserIdKey::IsFidoKey(this) )
      *((_BYTE *)this + 584) = 1;
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    if ( ConvertSidToStringSidW(*((PSID *)this + 4), &StringSid) )
    {
      v30 = 8;
      memset_0(Src, 0, 0x868u);
      memcpy_0(v31, Src, sizeof(v31));
      v32 = 0;
      v13 = StringCchCopyW(v31, 0x433u, StringSid);
      if ( v13 < 0 )
      {
        if ( (unsigned int)dword_180122070 <= 3 )
          goto LABEL_34;
        LastError = v13;
        v15 = (unsigned __int8 *)byte_180103E4D;
      }
      else
      {
        v14 = RtlPublishWnfStateData(WNF_NGC_CREDENTIAL_REFRESH_REQUIRED, 0, &v30, 2160, 0);
        if ( v14 >= 0 || (unsigned int)dword_180122070 <= 3 )
        {
LABEL_34:
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
          LODWORD(v10) = v20;
          v9 = v20;
          if ( v5 )
          {
            ReleaseSRWLockExclusive((PSRWLOCK)v5);
            LODWORD(v10) = v20;
          }
          goto LABEL_43;
        }
        LastError = v14 | 0x10000000;
        v15 = (unsigned __int8 *)&dword_180103E24;
      }
    }
    else
    {
      if ( (unsigned int)dword_180122070 <= 3 )
        goto LABEL_34;
      LastError = GetLastError();
      v15 = (unsigned __int8 *)&word_180103E86;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      v15,
      0,
      0,
      (__int64)&LastError);
    goto LABEL_34;
  }
  v20 = -2146893813;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x762,
      (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
      (const char *)v20,
      v17);
  }
  else if ( (unsigned int)dword_180122070 > 2 )
  {
    LastError = v20;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)byte_180103F7B,
      0,
      0,
      (__int64)&LastError);
  }
  LODWORD(v10) = v20;
  v9 = v20;
  if ( v5 )
  {
    ReleaseSRWLockExclusive((PSRWLOCK)v5);
    LODWORD(v10) = v20;
  }
LABEL_43:
  NgcKspServer::NgcUserIdKey::EventWriteFinalizeKey(this, v18, v10);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18007a8d0  mov     [rsp-8+arg_18], rbx
0x18007a8d5  push    rbp
0x18007a8d6  push    rsi
0x18007a8d7  push    rdi
0x18007a8d8  lea     rbp, [rsp-1110h]
0x18007a8e0  mov     eax, 1210h
0x18007a8e5  call    _alloca_probe
0x18007a8ea  sub     rsp, rax
0x18007a8ed  mov     rax, cs:__security_cookie
0x18007a8f4  xor     rax, rsp
0x18007a8f7  mov     [rbp+1120h+var_20], rax
0x18007a8fe  mov     rdi, rdx
0x18007a901  mov     rbx, rcx
0x18007a904  mov     [rsp+1220h+var_11F0], r8b
0x18007a909  mov     dword ptr [rsp+1220h+var_11E4], 0
0x18007a911  mov     [rsp+1220h+var_11C0], rcx
0x18007a916  lea     rax, [rsp+1220h+var_11F0]
0x18007a91b  mov     [rsp+1220h+var_11B8], rax
0x18007a920  lea     rax, [rsp+1220h+var_11E4]
0x18007a925  mov     [rsp+1220h+var_11B0], rax
0x18007a92a  mov     [rsp+1220h+var_11A8], 1
0x18007a92f  lea     rsi, [rcx+110h]
0x18007a936  mov     rcx, rsi; SRWLock
0x18007a939  call    cs:__imp_AcquireSRWLockExclusive
0x18007a93f  mov     [rsp+1220h+StringSid], rsi
0x18007a944  cmp     byte ptr [rbx+129h], 0
0x18007a94b  jz      loc_18007ACA0
0x18007a951  cmp     byte ptr [rbx+128h], 0
0x18007a958  jnz     loc_18007ACA0
0x18007a95e  mov     [rsp+1220h+var_11D0], 0
0x18007a967  mov     al, [rbx+249h]
0x18007a96d  mov     byte ptr [rsp+1220h+var_11E4+4], al
0x18007a971  mov     al, [rbx+24Ah]
0x18007a977  mov     byte ptr [rsp+1220h+var_11E4+5], al
0x18007a97b  lea     rax, [rsp+1220h+var_11E4+4]
0x18007a980  mov     [rsp+1220h+var_11C8], rax
0x18007a985  lea     rax, [rsp+1220h+var_11D0]
0x18007a98a  mov     [rsp+1220h+var_11F8], rax
0x18007a98f  lea     rax, [rsp+1220h+var_11C8]
0x18007a994  mov     [rsp+1220h+var_1200], rax
0x18007a999  mov     r9d, 8
0x18007a99f  mov     r8b, [rsp+1220h+var_11F0]
0x18007a9a4  mov     rdx, rdi
0x18007a9a7  mov     rcx, rbx
0x18007a9aa  call    ?PerformOperationWithGesture@NgcUserIdKey@NgcKspServer@@AEAAJQEAX_NW4NgcGestureOperationType@12@AEBTNgcGestureOperationInParameter@12@AEATNgcGestureOperationOutParameter@12@@Z; NgcKspServer::NgcUserIdKey::PerformOperationWithGesture(void * const,bool,NgcKspServer::NgcUserIdKey::NgcGestureOperationType,NgcKspServer::NgcUserIdKey::NgcGestureOperationInParameter const &,NgcKspServer::NgcUserIdKey::NgcGestureOperationOutParameter &)
0x18007a9af  mov     edi, eax
0x18007a9b1  mov     r8d, eax
0x18007a9b4  mov     dword ptr [rsp+1220h+var_11E4], eax
0x18007a9b8  test    eax, eax
0x18007a9ba  jns     short loc_18007A9E1
0x18007a9bc  test    rsi, rsi
0x18007a9bf  jz      short loc_18007A9CF
0x18007a9c1  mov     rcx, rsi; SRWLock
0x18007a9c4  call    cs:__imp_ReleaseSRWLockExclusive
0x18007a9ca  mov     r8d, dword ptr [rsp+1220h+var_11E4]; int
0x18007a9cf  mov     dl, [rsp+1220h+var_11F0]; bool
0x18007a9d3  mov     rcx, rbx; this
0x18007a9d6  call    ?EventWriteFinalizeKey@NgcUserIdKey@NgcKspServer@@AEAAX_NJ@Z; NgcKspServer::NgcUserIdKey::EventWriteFinalizeKey(bool,long)
0x18007a9db  nop
0x18007a9dc  jmp     loc_18007AD35
0x18007a9e1  mov     eax, cs:dword_180122070
0x18007a9e7  lea     rdi, dword_180122070
0x18007a9ee  cmp     eax, 4
0x18007a9f1  jbe     short loc_18007AA30
0x18007a9f3  mov     rdx, 200000000000h
0x18007a9fd  mov     rcx, rdi
0x18007aa00  call    _tlgKeywordOn
0x18007aa05  test    al, al
0x18007aa07  jz      short loc_18007AA30
0x18007aa09  mov     eax, dword ptr [rsp+1220h+var_11E4]
0x18007aa0d  mov     [rsp+1220h+var_11E8], eax
0x18007aa11  lea     rax, [rsp+1220h+var_11E8]
0x18007aa16  mov     [rsp+1220h+var_1200], rax
0x18007aa1b  xor     r9d, r9d
0x18007aa1e  xor     r8d, r8d
0x18007aa21  lea     rdx, byte_180103F4B
0x18007aa28  mov     rcx, rdi
0x18007aa2b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007aa30  mov     byte ptr [rbx+128h], 1
0x18007aa37  cmp     byte ptr [rbx+170h], 0
0x18007aa3e  jz      loc_18007AB41
0x18007aa44  call    IsWinBioRemoveCredentialPresent
0x18007aa49  test    al, al
0x18007aa4b  jz      loc_18007AB41
0x18007aa51  xor     edx, edx; Val
0x18007aa53  lea     r8d, [rdx+4Ch]; Size
0x18007aa57  lea     rcx, [rbp+1120h+pDestinationSid]; void *
0x18007aa5e  call    memset_0
0x18007aa63  mov     dword ptr [rbp+1120h+pDestinationSid], 3
0x18007aa6d  mov     r8, [rbx+20h]; pSourceSid
0x18007aa71  lea     rdx, [rbp+1120h+pDestinationSid+8]; pDestinationSid
0x18007aa78  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x18007aa7d  call    cs:__imp_CopySid
0x18007aa83  test    eax, eax
0x18007aa85  jz      loc_18007AB0D
0x18007aa8b  movaps  xmm0, [rbp+1120h+pDestinationSid]
0x18007aa92  movaps  xmmword ptr [rbp+1120h+Identity.Type], xmm0
0x18007aa96  movaps  xmm1, [rbp+1120h+var_8D0]
0x18007aa9d  movaps  xmmword ptr [rbp+1120h+Identity.Value+0Ch], xmm1
0x18007aaa1  movaps  xmm0, [rbp+1120h+var_8C0]
0x18007aaa8  movaps  xmmword ptr [rbp+1120h+Identity.Value+1Ch], xmm0
0x18007aaac  movaps  xmm1, xmmword ptr [rbp+1120h+var_8B0]
0x18007aab3  movaps  xmmword ptr [rbp+1120h+Identity.Value+2Ch], xmm1
0x18007aab7  movups  xmm0, xmmword ptr [rbp+1120h+var_8B0+0Ch]
0x18007aabe  movups  xmmword ptr [rbp+1120h+Identity.Value+38h], xmm0
0x18007aac2  or      edx, 0FFFFFFFFh; Type
0x18007aac5  lea     rcx, [rbp+1120h+Identity]; Identity
0x18007aac9  call    cs:__imp_WinBioRemoveCredential
0x18007aacf  mov     edx, eax
0x18007aad1  test    eax, eax
0x18007aad3  js      short loc_18007AAED
0x18007aad5  mov     ecx, cs:dword_180122070
0x18007aadb  cmp     ecx, 4
0x18007aade  jbe     short loc_18007AB41
0x18007aae0  mov     [rsp+1220h+var_11E8], eax
0x18007aae4  lea     rdx, dword_180103F14
0x18007aaeb  jmp     short loc_18007AB29
0x18007aaed  cmp     edx, 80098031h
0x18007aaf3  jz      short loc_18007AB41
0x18007aaf5  mov     eax, cs:dword_180122070
0x18007aafb  cmp     eax, 3
0x18007aafe  jbe     short loc_18007AB41
0x18007ab00  mov     [rsp+1220h+var_11E8], edx
0x18007ab04  lea     rdx, unk_180103EE0
0x18007ab0b  jmp     short loc_18007AB29
0x18007ab0d  mov     eax, cs:dword_180122070
0x18007ab13  cmp     eax, 3
0x18007ab16  jbe     short loc_18007AB41
0x18007ab18  call    cs:__imp_GetLastError
0x18007ab1e  mov     [rsp+1220h+var_11E8], eax
0x18007ab22  lea     rdx, byte_180103EBB
0x18007ab29  lea     rax, [rsp+1220h+var_11E8]
0x18007ab2e  mov     [rsp+1220h+var_1200], rax
0x18007ab33  xor     r9d, r9d
0x18007ab36  xor     r8d, r8d
0x18007ab39  mov     rcx, rdi
0x18007ab3c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007ab41  mov     rcx, rbx; this
0x18007ab44  call    ?IsFidoKey@NgcUserIdKey@NgcKspServer@@AEAA_NXZ; NgcKspServer::NgcUserIdKey::IsFidoKey(void)
0x18007ab49  test    al, al
0x18007ab4b  jz      short loc_18007AB54
0x18007ab4d  mov     byte ptr [rbx+248h], 1
0x18007ab54  mov     [rsp+1220h+StringSid], 0
0x18007ab5d  xor     edx, edx
0x18007ab5f  lea     rcx, [rsp+1220h+StringSid]
0x18007ab64  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18007ab69  lea     rdx, [rsp+1220h+StringSid]; StringSid
0x18007ab6e  mov     rcx, [rbx+20h]; Sid
0x18007ab72  call    cs:__imp_ConvertSidToStringSidW
0x18007ab78  test    eax, eax
0x18007ab7a  jz      loc_18007AC35
0x18007ab80  mov     [rbp+1120h+var_890], 8
0x18007ab8a  xor     edx, edx; Val
0x18007ab8c  mov     r8d, 868h; Size
0x18007ab92  lea     rcx, [rbp+1120h+Src]; void *
0x18007ab96  call    memset_0
0x18007ab9b  lea     rcx, [rbp+1120h+var_88C]; void *
0x18007aba2  lea     rdx, [rbp+1120h+Src]; Src
0x18007aba6  mov     r8d, 868h; Size
0x18007abac  call    memcpy_0
0x18007abb1  mov     [rbp+1120h+var_24], 0
0x18007abb8  mov     r8, [rsp+1220h+StringSid]; unsigned __int16 *
0x18007abbd  mov     edx, 433h; unsigned __int64
0x18007abc2  lea     rcx, [rbp+1120h+var_88C]; unsigned __int16 *
0x18007abc9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007abce  mov     r10d, eax
0x18007abd1  test    eax, eax
0x18007abd3  js      short loc_18007AC1C
0x18007abd5  mov     [rsp+1220h+var_1200], 0
0x18007abde  mov     r9d, 870h
0x18007abe4  lea     r8, [rbp+1120h+var_890]
0x18007abeb  xor     edx, edx
0x18007abed  mov     rcx, cs:WNF_NGC_CREDENTIAL_REFRESH_REQUIRED
0x18007abf4  call    cs:__imp_RtlPublishWnfStateData
0x18007abfa  mov     ecx, eax
0x18007abfc  or      ecx, 10000000h
0x18007ac02  jge     short loc_18007AC69
0x18007ac04  mov     eax, cs:dword_180122070
0x18007ac0a  cmp     eax, 3
0x18007ac0d  jbe     short loc_18007AC69
0x18007ac0f  mov     [rsp+1220h+var_11E8], ecx
0x18007ac13  lea     rdx, dword_180103E24
0x18007ac1a  jmp     short loc_18007AC51
0x18007ac1c  mov     eax, cs:dword_180122070
0x18007ac22  cmp     eax, 3
0x18007ac25  jbe     short loc_18007AC69
0x18007ac27  mov     [rsp+1220h+var_11E8], r10d
0x18007ac2c  lea     rdx, byte_180103E4D
0x18007ac33  jmp     short loc_18007AC51
0x18007ac35  mov     eax, cs:dword_180122070
0x18007ac3b  cmp     eax, 3
0x18007ac3e  jbe     short loc_18007AC69
0x18007ac40  call    cs:__imp_GetLastError
0x18007ac46  mov     [rsp+1220h+var_11E8], eax
0x18007ac4a  lea     rdx, word_180103E86
0x18007ac51  lea     rax, [rsp+1220h+var_11E8]
0x18007ac56  mov     [rsp+1220h+var_1200], rax
0x18007ac5b  xor     r9d, r9d
0x18007ac5e  xor     r8d, r8d
0x18007ac61  mov     rcx, rdi
0x18007ac64  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007ac69  lea     rcx, [rsp+1220h+StringSid]; void *
0x18007ac6e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18007ac73  mov     r8d, dword ptr [rsp+1220h+var_11E4]
0x18007ac78  mov     edi, r8d
0x18007ac7b  test    rsi, rsi
0x18007ac7e  jz      short loc_18007AC8E
0x18007ac80  mov     rcx, rsi; SRWLock
0x18007ac83  call    cs:__imp_ReleaseSRWLockExclusive
0x18007ac89  mov     r8d, dword ptr [rsp+1220h+var_11E4]; int
0x18007ac8e  mov     dl, [rsp+1220h+var_11F0]; bool
0x18007ac92  mov     rcx, rbx; this
0x18007ac95  call    ?EventWriteFinalizeKey@NgcUserIdKey@NgcKspServer@@AEAAX_NJ@Z; NgcKspServer::NgcUserIdKey::EventWriteFinalizeKey(bool,long)
0x18007ac9a  nop
0x18007ac9b  jmp     loc_18007AD35
0x18007aca0  mov     dword ptr [rsp+1220h+var_11E4], 8009000Bh
0x18007aca8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18007acaf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18007acb4  test    al, al
0x18007acb6  jz      short loc_18007ACD7
0x18007acb8  mov     rcx, [rbp+1128h]; this
0x18007acbf  mov     r9d, dword ptr [rsp+1220h+var_11E4]; char *
0x18007acc4  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007accb  mov     edx, 762h; void *
0x18007acd0  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18007acd5  jmp     short loc_18007AD0D
0x18007acd7  mov     eax, cs:dword_180122070
0x18007acdd  cmp     eax, 2
0x18007ace0  jbe     short loc_18007AD0D
0x18007ace2  mov     eax, dword ptr [rsp+1220h+var_11E4]
0x18007ace6  mov     [rsp+1220h+var_11E8], eax
0x18007acea  lea     rax, [rsp+1220h+var_11E8]
0x18007acef  mov     [rsp+1220h+var_1200], rax
0x18007acf4  xor     r9d, r9d
0x18007acf7  xor     r8d, r8d
0x18007acfa  lea     rdx, byte_180103F7B
0x18007ad01  lea     rcx, dword_180122070
0x18007ad08  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007ad0d  mov     r8d, dword ptr [rsp+1220h+var_11E4]
0x18007ad12  mov     edi, r8d
0x18007ad15  test    rsi, rsi
0x18007ad18  jz      short loc_18007AD28
0x18007ad1a  mov     rcx, rsi; SRWLock
0x18007ad1d  call    cs:__imp_ReleaseSRWLockExclusive
0x18007ad23  mov     r8d, dword ptr [rsp+1220h+var_11E4]; int
0x18007ad28  mov     dl, [rsp+1220h+var_11F0]; bool
0x18007ad2c  mov     rcx, rbx; this
0x18007ad2f  call    ?EventWriteFinalizeKey@NgcUserIdKey@NgcKspServer@@AEAAX_NJ@Z; NgcKspServer::NgcUserIdKey::EventWriteFinalizeKey(bool,long)
0x18007ad34  nop
0x18007ad35  mov     eax, edi
0x18007ad37  mov     rcx, [rbp+1120h+var_20]
0x18007ad3e  xor     rcx, rsp; StackCookie
0x18007ad41  call    __security_check_cookie
0x18007ad46  mov     rbx, [rsp+1220h+arg_18]
0x18007ad4e  add     rsp, 1210h
0x18007ad55  pop     rdi
0x18007ad56  pop     rsi
0x18007ad57  pop     rbp
0x18007ad58  retn
```
