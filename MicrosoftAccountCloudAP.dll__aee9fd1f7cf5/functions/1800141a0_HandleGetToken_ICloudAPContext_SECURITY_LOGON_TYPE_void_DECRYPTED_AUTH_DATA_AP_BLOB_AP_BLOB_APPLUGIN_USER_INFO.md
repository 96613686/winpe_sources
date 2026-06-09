# HandleGetToken(ICloudAPContext *,_SECURITY_LOGON_TYPE,void *,_DECRYPTED_AUTH_DATA *,_AP_BLOB *,_AP_BLOB *,_APPLUGIN_USER_INFO * *)

- ea: `0x1800141a0`
- end: `0x1800144ac`
- name: `?HandleGetToken@@YAJPEAVICloudAPContext@@W4_SECURITY_LOGON_TYPE@@PEAXPEAU_DECRYPTED_AUTH_DATA@@PEAU_AP_BLOB@@4PEAPEAU_APPLUGIN_USER_INFO@@@Z`
- size: `780`
- prototype: `__int64 __fastcall(struct ICloudAPContext *, enum _SECURITY_LOGON_TYPE, void *, struct _DECRYPTED_AUTH_DATA *, struct _AP_BLOB *, struct _AP_BLOB *, struct _APPLUGIN_USER_INFO **)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009df0`

## callees

- `0x1800011fc`
- `0x1800019c8`
- `0x180008440`
- `0x18000baac`
- `0x18000d968`
- `0x18000d980`
- `0x18000e0f0`
- `0x18000ed44`
- `0x180010040`
- `0x180010064`
- `0x180010320`
- `0x180010860`
- `0x180012130`
- `0x1800141a0`
- `0x180015468`
- `0x180032010`

## string_xrefs

- `0x18001422d`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180014209`: `HandleGetToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall HandleGetToken(
        struct ICloudAPContext *a1,
        enum _SECURITY_LOGON_TYPE a2,
        void *a3,
        struct _DECRYPTED_AUTH_DATA *a4,
        struct _AP_BLOB *a5,
        struct _AP_BLOB *a6,
        struct _APPLUGIN_USER_INFO **a7)
{
  struct MSACloudAPValidationInfo *v10; // r14
  void *v11; // r13
  struct _APPLUGIN_USER_INFO **v12; // rdi
  struct _AP_BLOB *v13; // rbx
  struct _AP_BLOB *v14; // rcx
  struct LOGON_CREDS *v15; // rdx
  int v16; // ecx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  __int64 v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  unsigned int v23; // ebx
  const unsigned __int16 *SourceString; // [rsp+20h] [rbp-71h]
  struct LOGON_CREDS *v26[3]; // [rsp+30h] [rbp-61h] BYREF
  void *v27[3]; // [rsp+48h] [rbp-49h] BYREF
  __int64 v28; // [rsp+60h] [rbp-31h] BYREF
  struct MSACloudAPValidationInfo *v29[3]; // [rsp+68h] [rbp-29h] BYREF
  _QWORD v30[10]; // [rsp+80h] [rbp-11h] BYREF
  enum _SECURITY_LOGON_TYPE v31; // [rsp+E0h] [rbp+4Fh] BYREF
  int LogonCredsFromAuthData; // [rsp+F0h] [rbp+5Fh] BYREF
  int v33; // [rsp+F4h] [rbp+63h]
  PCWSTR v34; // [rsp+F8h] [rbp+67h] BYREF

  v33 = HIDWORD(a3);
  LogonCredsFromAuthData = 0;
  v10 = 0;
  memset(v29, 0, sizeof(v29));
  memset(v26, 0, sizeof(v26));
  v34 = 0;
  v11 = (void *)(*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v27[0] = 0;
  v27[2] = v11;
  v27[1] = 0;
  v30[0] = "HandleGetToken";
  v30[1] = &LogonCredsFromAuthData;
  v30[2] = 0;
  v30[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
    "HandleGetToken",
    (const char *)0x373,
    0,
    SourceString);
  v12 = a7;
  v13 = a6;
  if ( a4 && (v14 = a5) != 0 && a6 && a7 )
  {
    *(_OWORD *)a6 = 0;
    *v12 = 0;
    if ( *(_DWORD *)v14 )
    {
      LogonCredsFromAuthData = DeserializeOpaqueBlob(v14, v29);
      if ( LogonCredsFromAuthData < 0 )
        goto LABEL_31;
      v10 = v29[0];
    }
    LogonCredsFromAuthData = GetLogonCredsFromAuthData(a1, a4, v26);
    if ( LogonCredsFromAuthData < 0 )
      goto LABEL_31;
    v15 = v26[0];
    v16 = *((_DWORD *)v26[0] + 6);
    if ( (unsigned int)(v16 - 1) <= 1 )
    {
      v20 = *((_QWORD *)v26[0] + 4);
      if ( !v20 )
        goto LABEL_28;
      v21 = -1;
      do
        ++v21;
      while ( *(_WORD *)(v20 + 2 * v21) );
      if ( !v21 )
      {
LABEL_28:
        LogonCredsFromAuthData = -1073741718;
        goto LABEL_31;
      }
    }
    else
    {
      if ( v16 != 3 || !*((_QWORD *)v26[0] + 16) )
      {
        LogonCredsFromAuthData = -1073741811;
        goto LABEL_31;
      }
      if ( (unsigned int)dword_18004D048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004D048, 0x200000000000LL) )
      {
        v28 = 50331648;
        v31 = a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v17,
          (unsigned int)byte_18004419D,
          v18,
          v19,
          (__int64)&v31,
          (__int64)&v28);
      }
      if ( ((a2 - 10) & 0xFFFFFFFD) == 0 )
      {
        LogonCredsFromAuthData = -1073741790;
        goto LABEL_31;
      }
      v15 = v26[0];
    }
    LogonCredsFromAuthData = LogonIdentity(a1, v15, v10, v27);
    if ( LogonCredsFromAuthData < 0
      || (v22 = (*(__int64 (__fastcall **)(void *, void *, const wchar_t *, PCWSTR *))(*(_QWORD *)v11 + 152LL))(
                  v11,
                  v27[0],
                  L"CID",
                  &v34),
          LogonCredsFromAuthData = LiveMapHResultToNtStatus(v22),
          LogonCredsFromAuthData < 0)
      || (LogonCredsFromAuthData = SerializeOpaqueBlob(a1, v27[0], v34, *((_DWORD *)v26[0] + 6), v13),
          LogonCredsFromAuthData < 0) )
    {
LABEL_31:
      if ( *v12 )
      {
        (*((void (**)(void))g_MSACloudAPPluginLsaFunctions + 7))();
        *v12 = 0;
      }
      goto LABEL_33;
    }
    LogonCredsFromAuthData = PopulateUserInfo(a1, v10, v27[0], *(const unsigned __int16 **)v26[0], v34, v12);
    if ( LogonCredsFromAuthData >= 0 )
      goto LABEL_35;
  }
  else
  {
    LogonCredsFromAuthData = -1073741811;
  }
  if ( v12 )
    goto LABEL_31;
LABEL_33:
  if ( v13 )
  {
    LiveFree(*((void **)v13 + 1));
    *(_OWORD *)v13 = 0;
  }
LABEL_35:
  v23 = LogonCredsFromAuthData;
  CTraceFuncW<long>::~CTraceFuncW<long>(v30);
  Auto<void *,WLIDHandleFunctor,ILiveIdNtService>::~Auto<void *,WLIDHandleFunctor,ILiveIdNtService>(v27);
  if ( v34 )
  {
    LiveFree((void *)v34);
    v34 = 0;
  }
  Auto<LOGON_CREDS *,LogonCredsFunctor,DummyContext>::~Auto<LOGON_CREDS *,LogonCredsFunctor,DummyContext>(v26);
  Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>::~Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>(v29);
  return v23;
}

```

## disassembly

```asm
0x1800141a0  mov     [rsp-8+arg_8], rbx
0x1800141a5  mov     [rsp-8+arg_10], r8
0x1800141aa  push    rbp
0x1800141ab  push    rsi
0x1800141ac  push    rdi
0x1800141ad  push    r12
0x1800141af  push    r13
0x1800141b1  push    r14
0x1800141b3  push    r15
0x1800141b5  lea     rbp, [rsp-0Fh]
0x1800141ba  sub     rsp, 0A0h
0x1800141c1  mov     r12, r9
0x1800141c4  mov     r15d, edx
0x1800141c7  mov     rsi, rcx
0x1800141ca  xor     ebx, ebx
0x1800141cc  mov     dword ptr [rbp+3Fh+arg_10], ebx
0x1800141cf  mov     r14d, ebx
0x1800141d2  mov     [rbp+3Fh+var_68], rbx
0x1800141d6  mov     [rbp+3Fh+var_58], rbx
0x1800141da  mov     [rbp+3Fh+var_60], rbx
0x1800141de  mov     [rbp+3Fh+var_A0], rbx
0x1800141e2  mov     [rbp+3Fh+var_90], rbx
0x1800141e6  mov     [rbp+3Fh+var_98], rbx
0x1800141ea  mov     [rbp+3Fh+arg_18], rbx
0x1800141ee  mov     rax, [rcx]
0x1800141f1  mov     rax, [rax+18h]
0x1800141f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141fa  mov     r13, rax
0x1800141fd  mov     [rbp+3Fh+var_88], rbx
0x180014201  mov     [rbp+3Fh+var_78], rax
0x180014205  mov     [rbp+3Fh+var_80], rbx
0x180014209  lea     rdx, aHandlegettoken; "HandleGetToken"
0x180014210  mov     [rbp+3Fh+var_50], rdx
0x180014214  lea     rax, [rbp+3Fh+arg_10]
0x180014218  mov     [rbp+3Fh+var_48], rax
0x18001421c  mov     [rbp+3Fh+var_40], rbx
0x180014220  mov     [rbp+3Fh+var_38], rbx
0x180014224  xor     r9d, r9d; unsigned int
0x180014227  mov     r8d, 373h; char *
0x18001422d  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180014234  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180014239  nop
0x18001423a  mov     rdi, [rbp+3Fh+arg_30]
0x18001423e  mov     rbx, [rbp+3Fh+arg_28]
0x180014242  test    r12, r12
0x180014245  jz      loc_18001440F
0x18001424b  mov     rcx, [rbp+3Fh+arg_20]; struct _AP_BLOB *
0x18001424f  test    rcx, rcx
0x180014252  jz      loc_18001440F
0x180014258  test    rbx, rbx
0x18001425b  jz      loc_18001440F
0x180014261  test    rdi, rdi
0x180014264  jz      loc_18001440F
0x18001426a  xorps   xmm0, xmm0
0x18001426d  movdqu  xmmword ptr [rbx], xmm0
0x180014271  mov     [rdi], r14
0x180014274  cmp     [rcx], r14d
0x180014277  jz      short loc_180014291
0x180014279  lea     rdx, [rbp+3Fh+var_68]; struct MSACloudAPValidationInfo **
0x18001427d  call    ?DeserializeOpaqueBlob@@YAJPEAU_AP_BLOB@@PEAPEAUMSACloudAPValidationInfo@@@Z; DeserializeOpaqueBlob(_AP_BLOB *,MSACloudAPValidationInfo * *)
0x180014282  mov     dword ptr [rbp+3Fh+arg_10], eax
0x180014285  test    eax, eax
0x180014287  js      loc_180014420
0x18001428d  mov     r14, [rbp+3Fh+var_68]
0x180014291  lea     r8, [rbp+3Fh+var_A0]; struct LOGON_CREDS **
0x180014295  mov     rdx, r12; struct _DECRYPTED_AUTH_DATA *
0x180014298  mov     rcx, rsi; struct ICloudAPContext *
0x18001429b  call    ?GetLogonCredsFromAuthData@@YAJPEAVICloudAPContext@@PEAU_DECRYPTED_AUTH_DATA@@PEAPEAULOGON_CREDS@@@Z; GetLogonCredsFromAuthData(ICloudAPContext *,_DECRYPTED_AUTH_DATA *,LOGON_CREDS * *)
0x1800142a0  mov     dword ptr [rbp+3Fh+arg_10], eax
0x1800142a3  xor     r12d, r12d
0x1800142a6  test    eax, eax
0x1800142a8  js      loc_180014423
0x1800142ae  mov     rdx, [rbp+3Fh+var_A0]; struct LOGON_CREDS *
0x1800142b2  mov     ecx, [rdx+18h]
0x1800142b5  lea     eax, [rcx-1]
0x1800142b8  cmp     eax, 1
0x1800142bb  jbe     loc_180014347
0x1800142c1  cmp     ecx, 3
0x1800142c4  jnz     short loc_18001433B
0x1800142c6  cmp     [rdx+80h], r12
0x1800142cd  jz      short loc_18001433B
0x1800142cf  mov     eax, cs:dword_18004D048
0x1800142d5  cmp     eax, 5
0x1800142d8  jbe     short loc_18001431E
0x1800142da  mov     rdx, 200000000000h
0x1800142e4  lea     rcx, dword_18004D048
0x1800142eb  call    _tlgKeywordOn
0x1800142f0  test    al, al
0x1800142f2  jz      short loc_18001431E
0x1800142f4  mov     [rbp+3Fh+var_70], 3000000h
0x1800142fc  mov     [rbp+3Fh+arg_0], r15d
0x180014300  lea     rax, [rbp+3Fh+var_70]
0x180014304  mov     [rsp+0D0h+var_A8], rax
0x180014309  lea     rax, [rbp+3Fh+arg_0]
0x18001430d  mov     [rsp+0D0h+SourceString], rax
0x180014312  lea     rdx, byte_18004419D
0x180014319  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001431e  lea     eax, [r15-0Ah]
0x180014322  test    eax, 0FFFFFFFDh
0x180014327  jnz     short loc_180014335
0x180014329  mov     dword ptr [rbp+3Fh+arg_10], 0C0000022h
0x180014330  jmp     loc_180014423
0x180014335  mov     rdx, [rbp+3Fh+var_A0]
0x180014339  jmp     short loc_18001436B
0x18001433b  mov     dword ptr [rbp+3Fh+arg_10], 0C000000Dh
0x180014342  jmp     loc_180014423
0x180014347  mov     rcx, [rdx+20h]
0x18001434b  test    rcx, rcx
0x18001434e  jz      loc_180014406
0x180014354  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014358  inc     rax
0x18001435b  cmp     [rcx+rax*2], r12w
0x180014360  jnz     short loc_180014358
0x180014362  test    rax, rax
0x180014365  jz      loc_180014406
0x18001436b  lea     r9, [rbp+3Fh+var_88]; void **
0x18001436f  mov     r8, r14; struct MSACloudAPValidationInfo *
0x180014372  mov     rcx, rsi; struct ICloudAPContext *
0x180014375  call    ?LogonIdentity@@YAJPEAVICloudAPContext@@PEAULOGON_CREDS@@PEAUMSACloudAPValidationInfo@@PEAPEAX@Z; LogonIdentity(ICloudAPContext *,LOGON_CREDS *,MSACloudAPValidationInfo *,void * *)
0x18001437a  mov     dword ptr [rbp+3Fh+arg_10], eax
0x18001437d  test    eax, eax
0x18001437f  js      loc_180014423
0x180014385  mov     rax, [r13+0]
0x180014389  lea     r9, [rbp+3Fh+arg_18]
0x18001438d  lea     r8, aCid; "CID"
0x180014394  mov     rdx, [rbp+3Fh+var_88]
0x180014398  mov     rcx, r13
0x18001439b  mov     rax, [rax+98h]
0x1800143a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143a7  mov     ecx, eax; int
0x1800143a9  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x1800143ae  mov     dword ptr [rbp+3Fh+arg_10], eax
0x1800143b1  test    eax, eax
0x1800143b3  js      short loc_180014423
0x1800143b5  mov     [rsp+0D0h+SourceString], rbx; struct _AP_BLOB *
0x1800143ba  mov     r9, [rbp+3Fh+var_A0]
0x1800143be  mov     r9d, [r9+18h]; unsigned int
0x1800143c2  mov     r8, [rbp+3Fh+arg_18]; unsigned __int16 *
0x1800143c6  mov     rdx, [rbp+3Fh+var_88]; void *
0x1800143ca  mov     rcx, rsi; struct ICloudAPContext *
0x1800143cd  call    ?SerializeOpaqueBlob@@YAJPEAVICloudAPContext@@PEAXPEBGKPEAU_AP_BLOB@@@Z; SerializeOpaqueBlob(ICloudAPContext *,void *,ushort const *,ulong,_AP_BLOB *)
0x1800143d2  mov     dword ptr [rbp+3Fh+arg_10], eax
0x1800143d5  test    eax, eax
0x1800143d7  js      short loc_180014423
0x1800143d9  mov     [rsp+0D0h+var_A8], rdi; struct _APPLUGIN_USER_INFO **
0x1800143de  mov     rax, [rbp+3Fh+arg_18]
0x1800143e2  mov     [rsp+0D0h+SourceString], rax; SourceString
0x1800143e7  mov     r9, [rbp+3Fh+var_A0]
0x1800143eb  mov     r9, [r9]; unsigned __int16 *
0x1800143ee  mov     r8, [rbp+3Fh+var_88]; void *
0x1800143f2  mov     rdx, r14; struct MSACloudAPValidationInfo *
0x1800143f5  mov     rcx, rsi; struct ICloudAPContext *
0x1800143f8  call    ?PopulateUserInfo@@YAJPEAVICloudAPContext@@PEAUMSACloudAPValidationInfo@@PEAXPEBG3PEAPEAU_APPLUGIN_USER_INFO@@@Z; PopulateUserInfo(ICloudAPContext *,MSACloudAPValidationInfo *,void *,ushort const *,ushort const *,_APPLUGIN_USER_INFO * *)
0x1800143fd  mov     dword ptr [rbp+3Fh+arg_10], eax
0x180014400  test    eax, eax
0x180014402  jns     short loc_180014453
0x180014404  jmp     short loc_180014419
0x180014406  mov     dword ptr [rbp+3Fh+arg_10], 0C000006Ah
0x18001440d  jmp     short loc_180014423
0x18001440f  mov     dword ptr [rbp+3Fh+arg_10], 0C000000Dh
0x180014416  xor     r12d, r12d
0x180014419  test    rdi, rdi
0x18001441c  jz      short loc_18001443E
0x18001441e  jmp     short loc_180014423
0x180014420  xor     r12d, r12d
0x180014423  mov     rcx, [rdi]
0x180014426  test    rcx, rcx
0x180014429  jz      short loc_18001443E
0x18001442b  mov     rax, cs:?g_MSACloudAPPluginLsaFunctions@@3PEAU_CLOUDAP_SECPKG_FUNCTION_TABLE@@EA; _CLOUDAP_SECPKG_FUNCTION_TABLE * g_MSACloudAPPluginLsaFunctions
0x180014432  mov     rax, [rax+38h]
0x180014436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001443b  mov     [rdi], r12
0x18001443e  test    rbx, rbx
0x180014441  jz      short loc_180014453
0x180014443  mov     rcx, [rbx+8]; void *
0x180014447  call    ?LiveFree@@YAXPEAX@Z; LiveFree(void *)
0x18001444c  xorps   xmm0, xmm0
0x18001444f  movdqu  xmmword ptr [rbx], xmm0
0x180014453  mov     ebx, dword ptr [rbp+3Fh+arg_10]
0x180014456  lea     rcx, [rbp+3Fh+var_50]
0x18001445a  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18001445f  nop
0x180014460  lea     rcx, [rbp+3Fh+var_88]
0x180014464  call    ??1?$Auto@PEAXVWLIDHandleFunctor@@VILiveIdNtService@@@@QEAA@XZ; Auto<void *,WLIDHandleFunctor,ILiveIdNtService>::~Auto<void *,WLIDHandleFunctor,ILiveIdNtService>(void)
0x180014469  nop
0x18001446a  mov     rcx, [rbp+3Fh+arg_18]; void *
0x18001446e  test    rcx, rcx
0x180014471  jz      short loc_18001447C
0x180014473  call    ?LiveFree@@YAXPEAX@Z; LiveFree(void *)
0x180014478  mov     [rbp+3Fh+arg_18], r12
0x18001447c  lea     rcx, [rbp+3Fh+var_A0]
0x180014480  call    ??1?$Auto@PEAULOGON_CREDS@@VLogonCredsFunctor@@VDummyContext@@@@QEAA@XZ; Auto<LOGON_CREDS *,LogonCredsFunctor,DummyContext>::~Auto<LOGON_CREDS *,LogonCredsFunctor,DummyContext>(void)
0x180014485  nop
0x180014486  lea     rcx, [rbp+3Fh+var_68]
0x18001448a  call    ??1?$Auto@PEAUMSACloudAPValidationInfo@@VValidationInfoFunctor@@VDummyContext@@@@QEAA@XZ; Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>::~Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>(void)
0x18001448f  mov     eax, ebx
0x180014491  mov     rbx, [rsp+0D0h+arg_8]
0x180014499  add     rsp, 0A0h
0x1800144a0  pop     r15
0x1800144a2  pop     r14
0x1800144a4  pop     r13
0x1800144a6  pop     r12
0x1800144a8  pop     rdi
0x1800144a9  pop     rsi
0x1800144aa  pop     rbp
0x1800144ab  retn
```
