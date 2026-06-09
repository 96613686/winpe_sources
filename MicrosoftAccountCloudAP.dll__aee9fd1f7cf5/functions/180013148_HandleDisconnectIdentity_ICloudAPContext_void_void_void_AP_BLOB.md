# HandleDisconnectIdentity(ICloudAPContext *,void *,void *,void *,_AP_BLOB *)

- ea: `0x180013148`
- end: `0x18001346f`
- name: `?HandleDisconnectIdentity@@YAJPEAVICloudAPContext@@PEAX11PEAU_AP_BLOB@@@Z`
- size: `807`
- prototype: `__int64 __fastcall(struct ICloudAPContext *, void *, void *, void *, struct _AP_BLOB *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009bb0`

## callees

- `0x1800011fc`
- `0x180001584`
- `0x180008440`
- `0x18000baac`
- `0x18000d91c`
- `0x18000d980`
- `0x18000e0f0`
- `0x180010064`
- `0x180012058`
- `0x1800120a4`
- `0x180012130`
- `0x1800121b4`
- `0x180013148`
- `0x180015338`
- `0x1800267c0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001326a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001326a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013274`
- `cryptngc!NgcEnumUserIdKeys` at `0x1800132e3`
- `cryptngc!NgcEnumUserIdKeys` at `0x1800132e3`
- `cryptngc!NgcDeleteUserIdKey` at `0x1800132fc`
- `cryptngc!NgcDeleteUserIdKey` at `0x1800132fc`

## string_xrefs

- `0x180013201`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x18001332d`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x1800132dc`: `login.live.com`
- `0x180013306`: `NgcDeleteUserIdKey failed, hr=0x%x.`

## pseudocode

```c
__int64 __fastcall HandleDisconnectIdentity(
        struct ICloudAPContext *a1,
        void *a2,
        void *a3,
        void *a4,
        struct _AP_BLOB *a5)
{
  __int64 v8; // rax
  __int64 v9; // r14
  __int64 v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // r8
  signed int LastError; // ebx
  const unsigned __int16 *v14; // rsi
  int v15; // eax
  const unsigned __int16 *v16; // r9
  unsigned int v17; // r8d
  int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // r9
  const unsigned __int16 *v24; // [rsp+20h] [rbp-A1h]
  __int64 v25; // [rsp+20h] [rbp-A1h]
  _QWORD v26[3]; // [rsp+30h] [rbp-91h] BYREF
  __int64 v27[3]; // [rsp+48h] [rbp-79h] BYREF
  _QWORD v28[3]; // [rsp+60h] [rbp-61h] BYREF
  struct MSACloudAPValidationInfo *v29[3]; // [rsp+78h] [rbp-49h] BYREF
  _QWORD v30[3]; // [rsp+90h] [rbp-31h] BYREF
  void **v31; // [rsp+A8h] [rbp-19h] BYREF
  int v32; // [rsp+B0h] [rbp-11h]
  __int64 v33; // [rsp+B8h] [rbp-9h]
  _QWORD v34[10]; // [rsp+C0h] [rbp-1h] BYREF
  __int64 v35; // [rsp+120h] [rbp+5Fh] BYREF
  int v36; // [rsp+128h] [rbp+67h] BYREF
  int v37; // [rsp+12Ch] [rbp+6Bh]
  const unsigned __int16 *v38; // [rsp+130h] [rbp+6Fh] BYREF

  v37 = HIDWORD(a2);
  v36 = 0;
  memset(v29, 0, sizeof(v29));
  memset(v28, 0, sizeof(v28));
  v8 = (*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 8LL))(a1);
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8);
  v10 = (*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v31 = &AutoImpersonateClient::`vftable';
  v32 = 0;
  v33 = v9;
  v27[0] = 0;
  v27[2] = v10;
  v27[1] = 0;
  v34[0] = "HandleDisconnectIdentity";
  v34[1] = &v36;
  v34[2] = 0;
  v34[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
    "HandleDisconnectIdentity",
    (const char *)0x12E,
    0,
    v24);
  if ( !a3 || !a5 || !a4 )
  {
    LastError = -1073741811;
    v36 = -1073741811;
    goto LABEL_24;
  }
  LastError = DeserializeOpaqueBlob(a5, v29);
  v36 = LastError;
  if ( LastError >= 0 )
  {
    if ( (*(unsigned int (__fastcall **)(__int64, void *, _QWORD *))(*(_QWORD *)v9 + 192LL))(v9, a4, v28)
      || ((int)GetLastError() > 0
        ? (LastError = (unsigned __int16)GetLastError() | 0xC0070000)
        : (LastError = GetLastError()),
          v36 = LastError,
          LastError >= 0) )
    {
      v35 = (__int64)&NgcFunctions::`vftable';
      v30[0] = 0;
      v30[2] = &v35;
      v30[1] = 0;
      memset(v26, 0, sizeof(v26));
      v14 = (const unsigned __int16 *)((char *)v29[0] + 8);
      v15 = NgcEnumUserIdKeys(L"login.live.com", 0, (char *)v29[0] + 8, v28[0], v26, v30);
      if ( v15 < 0 )
      {
        if ( v15 != -2146893782 )
        {
          v16 = L"NgcEnumUserIdKeys failed, hr=0x%x.";
          v17 = 351;
          goto LABEL_15;
        }
      }
      else
      {
        v15 = NgcDeleteUserIdKey(*(_QWORD *)(v26[0] + 32LL));
        if ( v15 < 0 )
        {
          v16 = L"NgcDeleteUserIdKey failed, hr=0x%x.";
          v17 = 346;
LABEL_15:
          LODWORD(v25) = v15;
          TracePrintW(5u, "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp", v17, v16, v25);
        }
      }
      Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(v26);
      Auto<void *,NgcKeyEnumStateFunctor<void *>,INgcFunctions>::~Auto<void *,NgcKeyEnumStateFunctor<void *>,INgcFunctions>(v30);
      v18 = AutoImpersonateClient::Impersonate((AutoImpersonateClient *)&v31, a3);
      LastError = LiveMapHResultToNtStatus(v18);
      v36 = LastError;
      if ( LastError >= 0 )
      {
        v19 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const wchar_t *, __int64, __int64 *))(*(_QWORD *)v10 + 48LL))(
                v10,
                &qword_18003AB48,
                L"{ba1e4578-b17c-48b0-986e-2178f2da7eef}",
                0x800000,
                v27);
        LastError = LiveMapHResultToNtStatus(v19);
        v36 = LastError;
        if ( LastError >= 0 )
        {
          v20 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 80LL))(v10, v27[0]);
          LastError = LiveMapHResultToNtStatus(v20);
          v36 = LastError;
          if ( LastError >= 0 )
          {
            if ( (unsigned int)dword_18004D048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004D048, 0x800000000000LL) )
            {
              v35 = 50331648;
              v38 = v14;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
                v21,
                (__int64)qword_180044350,
                v12,
                v22,
                &v38,
                (__int64)&v35);
            }
            LastError = v36;
          }
        }
      }
    }
  }
LABEL_24:
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v34, v11, v12);
  Auto<void *,WLIDHandleFunctor,ILiveIdNtService>::~Auto<void *,WLIDHandleFunctor,ILiveIdNtService>(v27);
  AutoImpersonateClient::~AutoImpersonateClient((AutoImpersonateClient *)&v31);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)v28);
  Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>::~Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>((__int64)v29);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180013148  mov     [rsp-8+arg_8], rdx
0x18001314d  push    rbp
0x18001314e  push    rbx
0x18001314f  push    rsi
0x180013150  push    rdi
0x180013151  push    r12
0x180013153  push    r14
0x180013155  push    r15
0x180013157  lea     rbp, [rsp-1Fh]
0x18001315c  sub     rsp, 0E0h
0x180013163  mov     rsi, r9
0x180013166  mov     r15, r8
0x180013169  mov     rbx, rcx
0x18001316c  xor     r12d, r12d
0x18001316f  mov     dword ptr [rbp+4Fh+arg_8], r12d
0x180013173  mov     [rbp+4Fh+var_98], r12
0x180013177  mov     [rbp+4Fh+var_88], r12
0x18001317b  mov     [rbp+4Fh+var_90], r12
0x18001317f  mov     [rbp+4Fh+var_B0], r12
0x180013183  mov     [rbp+4Fh+var_A0], r12
0x180013187  mov     [rbp+4Fh+var_A8], r12
0x18001318b  mov     rax, [rcx]
0x18001318e  mov     rax, [rax+8]
0x180013192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013197  mov     rdx, rax
0x18001319a  mov     rcx, [rax]
0x18001319d  mov     rax, [rcx+18h]
0x1800131a1  mov     rcx, rdx
0x1800131a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131a9  mov     r14, rax
0x1800131ac  mov     rcx, [rbx]
0x1800131af  mov     rax, [rcx+18h]
0x1800131b3  mov     rcx, rbx
0x1800131b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131bb  mov     rdi, rax
0x1800131be  lea     rax, ??_7AutoImpersonateClient@@6B@; const AutoImpersonateClient::`vftable'
0x1800131c5  mov     [rbp+4Fh+var_68], rax
0x1800131c9  mov     [rbp+4Fh+var_60], r12d
0x1800131cd  mov     [rbp+4Fh+var_58], r14
0x1800131d1  mov     [rbp+4Fh+var_C8], r12
0x1800131d5  mov     [rbp+4Fh+var_B8], rdi
0x1800131d9  mov     [rbp+4Fh+var_C0], r12
0x1800131dd  lea     rdx, aHandledisconne; "HandleDisconnectIdentity"
0x1800131e4  mov     [rbp+4Fh+var_50], rdx
0x1800131e8  lea     rax, [rbp+4Fh+arg_8]
0x1800131ec  mov     [rbp+4Fh+var_48], rax
0x1800131f0  mov     [rbp+4Fh+var_40], r12
0x1800131f4  mov     [rbp+4Fh+var_38], r12
0x1800131f8  xor     r9d, r9d; unsigned int
0x1800131fb  mov     r8d, 12Eh; char *
0x180013201  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180013208  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18001320d  nop
0x18001320e  test    r15, r15
0x180013211  jz      loc_180013422
0x180013217  mov     rcx, [rbp+4Fh+arg_20]; struct _AP_BLOB *
0x18001321b  test    rcx, rcx
0x18001321e  jz      loc_180013422
0x180013224  test    rsi, rsi
0x180013227  jz      loc_180013422
0x18001322d  lea     rdx, [rbp+4Fh+var_98]; struct MSACloudAPValidationInfo **
0x180013231  call    ?DeserializeOpaqueBlob@@YAJPEAU_AP_BLOB@@PEAPEAUMSACloudAPValidationInfo@@@Z; DeserializeOpaqueBlob(_AP_BLOB *,MSACloudAPValidationInfo * *)
0x180013236  mov     ebx, eax
0x180013238  mov     dword ptr [rbp+4Fh+arg_8], eax
0x18001323b  test    eax, eax
0x18001323d  js      loc_18001342A
0x180013243  mov     rax, [r14]
0x180013246  lea     r8, [rbp+4Fh+var_B0]
0x18001324a  mov     rdx, rsi
0x18001324d  mov     rcx, r14
0x180013250  mov     rax, [rax+0C0h]
0x180013257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001325c  test    eax, eax
0x18001325e  jnz     short loc_18001328E
0x180013260  call    cs:__imp_GetLastError
0x180013266  test    eax, eax
0x180013268  jg      short loc_180013274
0x18001326a  call    cs:__imp_GetLastError
0x180013270  mov     ebx, eax
0x180013272  jmp     short loc_180013283
0x180013274  call    cs:__imp_GetLastError
0x18001327a  movzx   ebx, ax
0x18001327d  or      ebx, 0C0070000h
0x180013283  mov     dword ptr [rbp+4Fh+arg_8], ebx
0x180013286  test    ebx, ebx
0x180013288  js      loc_18001342A
0x18001328e  lea     rax, ??_7NgcFunctions@@6B@; const NgcFunctions::`vftable'
0x180013295  mov     [rbp+4Fh+arg_0], rax
0x180013299  mov     [rbp+4Fh+var_80], r12
0x18001329d  lea     rax, [rbp+4Fh+arg_0]
0x1800132a1  mov     [rbp+4Fh+var_70], rax
0x1800132a5  mov     [rbp+4Fh+var_78], r12
0x1800132a9  mov     [rsp+110h+var_E0], r12
0x1800132ae  mov     [rsp+110h+var_D0], r12
0x1800132b3  mov     [rsp+110h+var_D8], r12
0x1800132b8  mov     rsi, [rbp+4Fh+var_98]
0x1800132bc  add     rsi, 8
0x1800132c0  lea     rax, [rbp+4Fh+var_80]
0x1800132c4  mov     [rsp+110h+var_E8], rax
0x1800132c9  lea     rax, [rsp+110h+var_E0]
0x1800132ce  mov     [rsp+110h+var_F0], rax
0x1800132d3  mov     r9, [rbp+4Fh+var_B0]
0x1800132d7  mov     r8, rsi
0x1800132da  xor     edx, edx
0x1800132dc  lea     rcx, aLoginLiveCom; "login.live.com"
0x1800132e3  call    cs:__imp_NgcEnumUserIdKeys
0x1800132e9  mov     r14d, 5
0x1800132ef  test    eax, eax
0x1800132f1  js      short loc_180013315
0x1800132f3  mov     rcx, [rsp+110h+var_E0]
0x1800132f8  mov     rcx, [rcx+20h]
0x1800132fc  call    cs:__imp_NgcDeleteUserIdKey
0x180013302  test    eax, eax
0x180013304  jns     short loc_18001333C
0x180013306  lea     r9, aNgcdeleteuseri_0; "NgcDeleteUserIdKey failed, hr=0x%x."
0x18001330d  mov     r8d, 15Ah
0x180013313  jmp     short loc_180013329
0x180013315  cmp     eax, 8009002Ah
0x18001331a  jz      short loc_18001333C
0x18001331c  lea     r9, aNgcenumuseridk_0; "NgcEnumUserIdKeys failed, hr=0x%x."
0x180013323  mov     r8d, 15Fh; unsigned int
0x180013329  mov     dword ptr [rsp+110h+var_F0], eax
0x18001332d  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180013334  mov     ecx, r14d; unsigned __int8
0x180013337  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001333c  lea     rcx, [rsp+110h+var_E0]
0x180013341  call    ??1?$Auto@PEAU_NGC_USER_ID_KEY_INFO@@V?$LocalAllocFunctor@PEAU_NGC_USER_ID_KEY_INFO@@@@VDummyContext@@@@QEAA@XZ; Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(void)
0x180013346  lea     rcx, [rbp+4Fh+var_80]
0x18001334a  call    ??1?$Auto@PEAXV?$NgcKeyEnumStateFunctor@PEAX@@VINgcFunctions@@@@QEAA@XZ; Auto<void *,NgcKeyEnumStateFunctor<void *>,INgcFunctions>::~Auto<void *,NgcKeyEnumStateFunctor<void *>,INgcFunctions>(void)
0x18001334f  mov     rdx, r15; void *
0x180013352  lea     rcx, [rbp+4Fh+var_68]; this
0x180013356  call    ?Impersonate@AutoImpersonateClient@@QEAAJPEAX@Z; AutoImpersonateClient::Impersonate(void *)
0x18001335b  mov     ecx, eax; int
0x18001335d  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180013362  mov     ebx, eax
0x180013364  mov     dword ptr [rbp+4Fh+arg_8], eax
0x180013367  test    eax, eax
0x180013369  js      loc_18001342A
0x18001336f  mov     rax, [rdi]
0x180013372  lea     rcx, [rbp+4Fh+var_C8]
0x180013376  mov     [rsp+110h+var_F0], rcx
0x18001337b  mov     r9d, 800000h
0x180013381  lea     r8, aBa1e4578B17c48; "{ba1e4578-b17c-48b0-986e-2178f2da7eef}"
0x180013388  lea     rdx, qword_18003AB48
0x18001338f  mov     rcx, rdi
0x180013392  mov     rax, [rax+30h]
0x180013396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001339b  mov     ecx, eax; int
0x18001339d  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x1800133a2  mov     ebx, eax
0x1800133a4  mov     dword ptr [rbp+4Fh+arg_8], eax
0x1800133a7  test    eax, eax
0x1800133a9  js      short loc_18001342A
0x1800133ab  mov     rax, [rdi]
0x1800133ae  mov     rdx, [rbp+4Fh+var_C8]
0x1800133b2  mov     rcx, rdi
0x1800133b5  mov     rax, [rax+50h]
0x1800133b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133be  mov     ecx, eax; int
0x1800133c0  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x1800133c5  mov     ebx, eax
0x1800133c7  mov     dword ptr [rbp+4Fh+arg_8], eax
0x1800133ca  test    eax, eax
0x1800133cc  js      short loc_18001342A
0x1800133ce  mov     eax, cs:dword_18004D048
0x1800133d4  cmp     eax, r14d
0x1800133d7  jbe     short loc_18001341D
0x1800133d9  mov     rdx, 800000000000h
0x1800133e3  lea     rcx, dword_18004D048
0x1800133ea  call    _tlgKeywordOn
0x1800133ef  test    al, al
0x1800133f1  jz      short loc_18001341D
0x1800133f3  mov     [rbp+4Fh+arg_0], 3000000h
0x1800133fb  mov     [rbp+4Fh+arg_10], rsi
0x1800133ff  lea     rax, [rbp+4Fh+arg_0]
0x180013403  mov     [rsp+110h+var_E8], rax
0x180013408  lea     rax, [rbp+4Fh+arg_10]
0x18001340c  mov     [rsp+110h+var_F0], rax
0x180013411  lea     rdx, qword_180044350
0x180013418  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x18001341d  mov     ebx, dword ptr [rbp+4Fh+arg_8]
0x180013420  jmp     short loc_18001342A
0x180013422  mov     ebx, 0C000000Dh
0x180013427  mov     dword ptr [rbp+4Fh+arg_8], ebx
0x18001342a  lea     rcx, [rbp+4Fh+var_50]
0x18001342e  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180013433  nop
0x180013434  lea     rcx, [rbp+4Fh+var_C8]
0x180013438  call    ??1?$Auto@PEAXVWLIDHandleFunctor@@VILiveIdNtService@@@@QEAA@XZ; Auto<void *,WLIDHandleFunctor,ILiveIdNtService>::~Auto<void *,WLIDHandleFunctor,ILiveIdNtService>(void)
0x18001343d  nop
0x18001343e  lea     rcx, [rbp+4Fh+var_68]; this
0x180013442  call    ??1AutoImpersonateClient@@UEAA@XZ; AutoImpersonateClient::~AutoImpersonateClient(void)
0x180013447  nop
0x180013448  lea     rcx, [rbp+4Fh+var_B0]
0x18001344c  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x180013451  nop
0x180013452  lea     rcx, [rbp+4Fh+var_98]
0x180013456  call    ??1?$Auto@PEAUMSACloudAPValidationInfo@@VValidationInfoFunctor@@VDummyContext@@@@QEAA@XZ; Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>::~Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>(void)
0x18001345b  mov     eax, ebx
0x18001345d  add     rsp, 0E0h
0x180013464  pop     r15
0x180013466  pop     r14
0x180013468  pop     r12
0x18001346a  pop     rdi
0x18001346b  pop     rsi
0x18001346c  pop     rbx
0x18001346d  pop     rbp
0x18001346e  retn
```
