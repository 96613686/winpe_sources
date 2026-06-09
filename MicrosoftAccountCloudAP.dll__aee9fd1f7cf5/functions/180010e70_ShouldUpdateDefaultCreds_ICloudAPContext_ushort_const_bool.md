# ShouldUpdateDefaultCreds(ICloudAPContext *,ushort const *,bool *)

- ea: `0x180010e70`
- end: `0x18001107a`
- name: `?ShouldUpdateDefaultCreds@@YAJPEAVICloudAPContext@@PEBGPEA_N@Z`
- size: `522`
- prototype: `int(struct ICloudAPContext *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180014ff0`

## callees

- `0x1800011fc`
- `0x1800012c8`
- `0x18000d91c`
- `0x180010064`
- `0x180010e70`
- `0x1800267c0`
- `0x180027724`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010f48`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010f5d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010f72`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010f87`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010f48`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010f5d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010f72`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010f87`

## string_xrefs

- `0x18001100f`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`
- `0x180011045`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`
- `0x180010f52`: `PersistedFromCache`
- `0x180011038`: `GetSID failed with 0x%0x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ShouldUpdateDefaultCreds(struct ICloudAPContext *a1, const unsigned __int16 *a2, bool *a3)
{
  __int64 v5; // rdi
  struct IWinApiLite *v6; // rax
  int SID; // eax
  int v8; // ebx
  __int64 v9; // rax
  const unsigned __int16 *v10; // rdi
  int v11; // eax
  int v12; // ebx
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v18; // [rsp+20h] [rbp-50h]
  _QWORD v19[3]; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 *v20[3]; // [rsp+58h] [rbp-18h] BYREF
  const unsigned __int16 *v21; // [rsp+90h] [rbp+20h] BYREF
  const unsigned __int16 *v22; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v23; // [rsp+A8h] [rbp+38h] BYREF

  *a3 = 0;
  memset(v20, 0, sizeof(v20));
  v5 = (*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 8LL))(a1);
  v6 = (struct IWinApiLite *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
  SID = CWLIDCCHelper::GetSID(v6, a2, v20);
  v8 = SID;
  if ( SID < 0 )
  {
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
      0x8A3u,
      L"GetSID failed with 0x%0x.",
      SID);
    v13 = LiveMapHResultToNtStatus(v8);
  }
  else
  {
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 48LL))(v5);
    memset(v19, 0, sizeof(v19));
    v10 = v20[0];
    v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, const unsigned __int16 *, _QWORD *, _QWORD))(*(_QWORD *)v9 + 24LL))(
            v9,
            v20[0],
            L"DefaultCredSaved",
            v19,
            0);
    v12 = v11;
    if ( v11 < 0 )
    {
      LODWORD(v18) = v11;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
        0x89Du,
        L"GetStoredIdentityProperty(defaultCredsSaved) failed with 0x%0x.",
        v18);
      v13 = LiveMapHResultToNtStatus(v12);
    }
    else
    {
      v13 = 0;
      if ( !v19[0]
        || !(unsigned int)_o__wcsicmp(v19[0], L"DefaultCredsMissing")
        || !(unsigned int)_o__wcsicmp(v19[0], L"PersistedFromCache")
        || !(unsigned int)_o__wcsicmp(v19[0], L"DefaultCredsPersistFailed")
        || !(unsigned int)_o__wcsicmp(v19[0], L"DefaultCredsInvalid") )
      {
        *a3 = 1;
        if ( (unsigned int)dword_18004D048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004D048, 0x400000000000LL) )
        {
          v21 = (const unsigned __int16 *)v19[0];
          v22 = v10;
          v23 = 50331648;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            v14,
            (__int64)byte_180043FBD,
            v15,
            v16,
            (__int64)&v23,
            &v22,
            &v21);
        }
      }
    }
    Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)v19);
  }
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)v20);
  return v13;
}

```

## disassembly

```asm
0x180010e70  mov     [rsp-18h+arg_8], rbx
0x180010e75  push    rbp
0x180010e76  push    rsi
0x180010e77  push    rdi
0x180010e78  mov     rbp, rsp
0x180010e7b  sub     rsp, 70h
0x180010e7f  mov     rsi, r8
0x180010e82  mov     rbx, rdx
0x180010e85  mov     byte ptr [r8], 0
0x180010e89  mov     [rbp+var_18], 0
0x180010e91  mov     [rbp+var_8], 0
0x180010e99  mov     [rbp+var_10], 0
0x180010ea1  mov     rax, [rcx]
0x180010ea4  mov     rax, [rax+8]
0x180010ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ead  mov     rdi, rax
0x180010eb0  mov     rcx, [rax]
0x180010eb3  mov     rax, [rcx+18h]
0x180010eb7  mov     rcx, rdi
0x180010eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ebf  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180010ec3  mov     rdx, rbx; unsigned __int16 *
0x180010ec6  mov     rcx, rax; struct IWinApiLite *
0x180010ec9  call    ?GetSID@CWLIDCCHelper@@SAJPEAVIWinApiLite@@PEBGPEAPEAG@Z; CWLIDCCHelper::GetSID(IWinApiLite *,ushort const *,ushort * *)
0x180010ece  mov     ebx, eax
0x180010ed0  test    eax, eax
0x180010ed2  js      loc_180011034
0x180010ed8  mov     rax, [rdi]
0x180010edb  mov     rcx, rdi
0x180010ede  mov     rax, [rax+30h]
0x180010ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ee7  mov     r10, rax
0x180010eea  mov     [rbp+var_30], 0
0x180010ef2  mov     [rbp+var_20], 0
0x180010efa  mov     [rbp+var_28], 0
0x180010f02  mov     rcx, [rax]
0x180010f05  mov     rax, [rcx+18h]
0x180010f09  mov     [rsp+70h+var_50], 0
0x180010f12  lea     r9, [rbp+var_30]
0x180010f16  lea     r8, aDefaultcredsav; "DefaultCredSaved"
0x180010f1d  mov     rdi, [rbp+var_18]
0x180010f21  mov     rdx, rdi
0x180010f24  mov     rcx, r10
0x180010f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f2c  mov     ebx, eax
0x180010f2e  test    eax, eax
0x180010f30  js      loc_180010FFE
0x180010f36  xor     ebx, ebx
0x180010f38  mov     rcx, [rbp+var_30]
0x180010f3c  test    rcx, rcx
0x180010f3f  jz      short loc_180010F95
0x180010f41  lea     rdx, aDefaultcredsmi; "DefaultCredsMissing"
0x180010f48  call    cs:__imp__o__wcsicmp
0x180010f4e  test    eax, eax
0x180010f50  jz      short loc_180010F95
0x180010f52  lea     rdx, aPersistedfromc; "PersistedFromCache"
0x180010f59  mov     rcx, [rbp+var_30]
0x180010f5d  call    cs:__imp__o__wcsicmp
0x180010f63  test    eax, eax
0x180010f65  jz      short loc_180010F95
0x180010f67  lea     rdx, aDefaultcredspe; "DefaultCredsPersistFailed"
0x180010f6e  mov     rcx, [rbp+var_30]
0x180010f72  call    cs:__imp__o__wcsicmp
0x180010f78  test    eax, eax
0x180010f7a  jz      short loc_180010F95
0x180010f7c  lea     rdx, aDefaultcredsin; "DefaultCredsInvalid"
0x180010f83  mov     rcx, [rbp+var_30]
0x180010f87  call    cs:__imp__o__wcsicmp
0x180010f8d  test    eax, eax
0x180010f8f  jnz     loc_180011029
0x180010f95  mov     byte ptr [rsi], 1
0x180010f98  mov     eax, cs:dword_18004D048
0x180010f9e  cmp     eax, 5
0x180010fa1  jbe     loc_180011029
0x180010fa7  mov     rdx, 400000000000h
0x180010fb1  lea     rcx, dword_18004D048
0x180010fb8  call    _tlgKeywordOn
0x180010fbd  test    al, al
0x180010fbf  jz      short loc_180011029
0x180010fc1  mov     rax, [rbp+var_30]
0x180010fc5  mov     [rbp+arg_0], rax
0x180010fc9  mov     [rbp+arg_10], rdi
0x180010fcd  mov     [rbp+arg_18], 3000000h
0x180010fd5  lea     rax, [rbp+arg_0]
0x180010fd9  mov     [rsp+70h+var_40], rax
0x180010fde  lea     rax, [rbp+arg_10]
0x180010fe2  mov     [rsp+70h+var_48], rax
0x180010fe7  lea     rax, [rbp+arg_18]
0x180010feb  mov     [rsp+70h+var_50], rax
0x180010ff0  lea     rdx, byte_180043FBD
0x180010ff7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180010ffc  jmp     short loc_180011029
0x180010ffe  mov     dword ptr [rsp+70h+var_50], ebx
0x180011002  lea     r9, aGetstoredident; "GetStoredIdentityProperty(defaultCredsS"...
0x180011009  mov     r8d, 89Dh; unsigned int
0x18001100f  lea     rdx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180011016  mov     ecx, 2; unsigned __int8
0x18001101b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180011020  mov     ecx, ebx; int
0x180011022  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180011027  mov     ebx, eax
0x180011029  lea     rcx, [rbp+var_30]
0x18001102d  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x180011032  jmp     short loc_18001105F
0x180011034  mov     dword ptr [rsp+70h+var_50], ebx
0x180011038  lea     r9, aGetsidFailedWi; "GetSID failed with 0x%0x."
0x18001103f  mov     r8d, 8A3h; unsigned int
0x180011045  lea     rdx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18001104c  mov     ecx, 2; unsigned __int8
0x180011051  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180011056  mov     ecx, ebx; int
0x180011058  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18001105d  mov     ebx, eax
0x18001105f  lea     rcx, [rbp+var_18]
0x180011063  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x180011068  mov     eax, ebx
0x18001106a  mov     rbx, [rsp+70h+arg_8]
0x180011072  add     rsp, 70h
0x180011076  pop     rdi
0x180011077  pop     rsi
0x180011078  pop     rbp
0x180011079  retn
```
