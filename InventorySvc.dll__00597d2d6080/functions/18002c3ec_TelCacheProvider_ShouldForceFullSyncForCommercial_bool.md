# TelCacheProvider::ShouldForceFullSyncForCommercial(bool)

- ea: `0x18002c3ec`
- end: `0x18002c640`
- name: `?ShouldForceFullSyncForCommercial@TelCacheProvider@@AEAAH_N@Z`
- size: `596`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c1a4`

## callees

- `0x180002bf0`
- `0x1800038b8`
- `0x1800152d0`
- `0x180026430`
- `0x180029434`
- `0x18002c3ec`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002c4da`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002c4da`

## string_xrefs

- `0x18002c4fc`: `commercialId`
- `0x18002c5e0`: `commercialId`
- `0x18002c556`: `Full sync may be needed because of Commercial ID change`
- `0x18002c5c7`: `TelCacheProvider::ShouldForceFullSyncForCommercial`
- `0x18002c5ba`: `Full sync may be needed because of Commercial 45 day sync policy`

## pseudocode

```c
__int64 __fastcall TelCacheProvider::ShouldForceFullSyncForCommercial(TelCacheProvider *this, char a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  int PersistedLocation; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned __int16 *v10; // r9
  int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  unsigned __int16 *v16; // r9
  struct _FILETIME v17; // rbx
  unsigned int v18; // eax
  __int64 v19; // r9
  unsigned __int16 *v20; // rax
  int v21; // r8d
  int v22; // ecx
  __int64 v23; // rcx
  unsigned __int16 *v24; // r8
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v29[40]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v30[264]; // [rsp+A0h] [rbp-60h] BYREF

  v4 = 0;
  if ( !`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::AlreadyRetrieved )
  {
    memset_0(v30, 0, 0x208u);
    PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(
                          v30,
                          v5,
                          L"DataCollectionGroupPolicy",
                          L"Software\\Policies\\Microsoft\\Windows\\DataCollection",
                          1);
    v10 = v30;
    v11 = PersistedLocation;
    if ( PersistedLocation < 0 )
      v10 = L"Software\\Policies\\Microsoft\\Windows\\DataCollection";
    Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(v8, v7, v9, v10);
    if ( !`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId )
    {
      Windows::Compat::Shared::Registry::GetPersistedLocation(
        v30,
        v12,
        L"Diagnostics_AllowTelemetry",
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\DataCollection",
        1);
      v16 = v30;
      if ( v11 < 0 )
        v16 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\DataCollection";
      Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(v14, v13, v15, v16);
    }
    `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::AlreadyRetrieved = 1;
  }
  memset_0(v29, 0, sizeof(v29));
  v26 = 40;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v17 = SystemTimeAsFileTime;
  if ( !a2 )
  {
    v18 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _WORD *, int *))(**((_QWORD **)this + 11) + 56LL))(
            *((_QWORD *)this + 11),
            L"commercialId",
            v29,
            &v26);
    v19 = v18;
    if ( v18 == -2147024894 )
      v29[0] = 0;
    v20 = v29;
    do
    {
      v21 = *(unsigned __int16 *)((char *)v20
                                + (char *)&`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId
                                - (char *)v29);
      v22 = *v20 - v21;
      if ( v22 )
        break;
      ++v20;
    }
    while ( v21 );
    if ( v22 )
    {
      v4 = 1;
      if ( (int)v19 >= 0 )
        AslLogCallPrintf(
          3,
          "TelCacheProvider::ShouldForceFullSyncForCommercial",
          2004,
          "Full sync may be needed because of Commercial ID change");
    }
    else
    {
      if ( !`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId )
        return v4;
      v23 = *((_QWORD *)this + 11);
      v28 = 0;
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, __int64 *, __int64))(*(_QWORD *)v23 + 64LL))(
             v23,
             L"lastFullSync",
             &v28,
             v19) < 0 )
      {
        v4 = 1;
        AslLogCallPrintf(
          3,
          "TelCacheProvider::ShouldForceFullSyncForCommercial",
          2018,
          "Full sync may be needed because of Commercial 45 day sync policy");
      }
      else
      {
        LOBYTE(v4) = (unsigned __int64)(*(_QWORD *)&v17 - v28) > 0x235C7496C000LL;
        if ( (unsigned __int64)(*(_QWORD *)&v17 - v28) <= 0x235C7496C000LL )
          return v4;
      }
    }
  }
  if ( `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId )
    v24 = &`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId;
  else
    v24 = 0;
  (*(void (__fastcall **)(_QWORD, const wchar_t *, unsigned __int16 *))(**((_QWORD **)this + 11) + 80LL))(
    *((_QWORD *)this + 11),
    L"commercialId",
    v24);
  (*(void (__fastcall **)(_QWORD, const wchar_t *, struct _FILETIME))(**((_QWORD **)this + 11) + 88LL))(
    *((_QWORD *)this + 11),
    L"lastFullSync",
    v17);
  return v4;
}

```

## disassembly

```asm
0x18002c3ec  push    rbp
0x18002c3ee  push    rbx
0x18002c3ef  push    rsi
0x18002c3f0  push    rdi
0x18002c3f1  push    r14
0x18002c3f3  push    r15
0x18002c3f5  lea     rbp, [rsp-1C8h]
0x18002c3fd  sub     rsp, 2C8h
0x18002c404  mov     rax, cs:__security_cookie
0x18002c40b  xor     rax, rsp
0x18002c40e  mov     [rbp+1F0h+var_40], rax
0x18002c415  xor     r15d, r15d
0x18002c418  mov     sil, dl
0x18002c41b  cmp     cs:?AlreadyRetrieved@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4_NA, r15b; bool `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::AlreadyRetrieved
0x18002c422  mov     r14, rcx
0x18002c425  mov     edi, r15d
0x18002c428  jnz     loc_18002C4B8
0x18002c42e  xor     edx, edx; Val
0x18002c430  lea     rcx, [rbp+1F0h+var_250]; void *
0x18002c434  mov     r8d, 208h; Size
0x18002c43a  call    memset_0
0x18002c43f  lea     r9, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18002c446  mov     [rsp+2F0h+var_2D0], 1; int
0x18002c44e  lea     r8, aDatacollection; "DataCollectionGroupPolicy"
0x18002c455  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x18002c459  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x18002c45e  lea     r9, [rbp+1F0h+var_250]
0x18002c462  mov     ebx, eax
0x18002c464  test    eax, eax
0x18002c466  jns     short loc_18002C46F
0x18002c468  lea     r9, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18002c46f  call    ?ReadString@?$RegistryKeyWrapper@$0?HPPPPPPO@@Shared@Compat@Windows@@SAJPEAG_KPEBG22@Z; Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(ushort *,unsigned __int64,ushort const *,ushort const *,ushort const *)
0x18002c474  cmp     cs:?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA, r15w; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x18002c47c  jnz     short loc_18002C4B1
0x18002c47e  lea     r9, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002c485  mov     [rsp+2F0h+var_2D0], 1; int
0x18002c48d  lea     r8, aDiagnosticsAll; "Diagnostics_AllowTelemetry"
0x18002c494  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x18002c498  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x18002c49d  lea     r9, [rbp+1F0h+var_250]
0x18002c4a1  test    ebx, ebx
0x18002c4a3  jns     short loc_18002C4AC
0x18002c4a5  lea     r9, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002c4ac  call    ?ReadString@?$RegistryKeyWrapper@$0?HPPPPPPO@@Shared@Compat@Windows@@SAJPEAG_KPEBG22@Z; Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(ushort *,unsigned __int64,ushort const *,ushort const *,ushort const *)
0x18002c4b1  mov     cs:?AlreadyRetrieved@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4_NA, 1; bool `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::AlreadyRetrieved
0x18002c4b8  xor     edx, edx; Val
0x18002c4ba  lea     rcx, [rsp+2F0h+var_2A0]; void *
0x18002c4bf  lea     r8d, [rdx+50h]; Size
0x18002c4c3  call    memset_0
0x18002c4c8  lea     rcx, [rsp+2F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002c4cd  mov     [rsp+2F0h+var_2C0], 28h ; '('
0x18002c4d5  mov     qword ptr [rsp+2F0h+SystemTimeAsFileTime.dwLowDateTime], r15
0x18002c4da  call    cs:__imp_GetSystemTimeAsFileTime
0x18002c4e0  mov     rbx, qword ptr [rsp+2F0h+SystemTimeAsFileTime.dwLowDateTime]
0x18002c4e5  test    sil, sil
0x18002c4e8  jnz     loc_18002C5D8
0x18002c4ee  mov     rcx, [r14+58h]
0x18002c4f2  lea     r9, [rsp+2F0h+var_2C0]
0x18002c4f7  lea     r8, [rsp+2F0h+var_2A0]
0x18002c4fc  lea     rdx, aCommercialid_0; "commercialId"
0x18002c503  mov     rax, [rcx]
0x18002c506  mov     rax, [rax+38h]
0x18002c50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c50f  mov     r9d, eax
0x18002c512  cmp     eax, 80070002h
0x18002c517  jnz     short loc_18002C51F
0x18002c519  mov     [rsp+2F0h+var_2A0], r15w
0x18002c51f  lea     rax, [rsp+2F0h+var_2A0]
0x18002c524  lea     rdx, ?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x18002c52b  sub     rdx, rax
0x18002c52e  movzx   ecx, word ptr [rax]
0x18002c531  movzx   r8d, word ptr [rax+rdx]
0x18002c536  sub     ecx, r8d
0x18002c539  jnz     short loc_18002C544
0x18002c53b  add     rax, 2
0x18002c53f  test    r8d, r8d
0x18002c542  jnz     short loc_18002C52E
0x18002c544  test    ecx, ecx
0x18002c546  jz      short loc_18002C565
0x18002c548  mov     edi, 1
0x18002c54d  test    r9d, r9d
0x18002c550  js      loc_18002C5D8
0x18002c556  lea     r9, aFullSyncMayBeN_3; "Full sync may be needed because of Comm"...
0x18002c55d  mov     r8d, 7D4h
0x18002c563  jmp     short loc_18002C5C7
0x18002c565  cmp     cs:?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA, r15w; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x18002c56d  jz      loc_18002C61F
0x18002c573  mov     rcx, [r14+58h]
0x18002c577  lea     r8, [rsp+2F0h+var_2B0]
0x18002c57c  mov     [rsp+2F0h+var_2B0], r15
0x18002c581  lea     rdx, aLastfullsync; "lastFullSync"
0x18002c588  mov     rax, [rcx]
0x18002c58b  mov     rax, [rax+40h]
0x18002c58f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c594  test    eax, eax
0x18002c596  js      short loc_18002C5B5
0x18002c598  mov     rax, rbx
0x18002c59b  mov     rcx, 235C7496C000h
0x18002c5a5  sub     rax, [rsp+2F0h+var_2B0]
0x18002c5aa  cmp     rax, rcx
0x18002c5ad  setnbe  dil
0x18002c5b1  jbe     short loc_18002C61F
0x18002c5b3  jmp     short loc_18002C5D8
0x18002c5b5  mov     edi, 1
0x18002c5ba  lea     r9, aFullSyncMayBeN; "Full sync may be needed because of Comm"...
0x18002c5c1  mov     r8d, 7E2h
0x18002c5c7  lea     rdx, aTelcacheprovid_15; "TelCacheProvider::ShouldForceFullSyncFo"...
0x18002c5ce  mov     ecx, 3
0x18002c5d3  call    AslLogCallPrintf
0x18002c5d8  cmp     cs:?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA, r15w; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x18002c5e0  lea     rdx, aCommercialid_0; "commercialId"
0x18002c5e7  mov     rcx, [r14+58h]
0x18002c5eb  mov     rax, [rcx]
0x18002c5ee  mov     rax, [rax+50h]
0x18002c5f2  jz      short loc_18002C5FD
0x18002c5f4  lea     r8, ?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x18002c5fb  jmp     short loc_18002C600
0x18002c5fd  xor     r8d, r8d
0x18002c600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c605  mov     rcx, [r14+58h]
0x18002c609  lea     rdx, aLastfullsync; "lastFullSync"
0x18002c610  mov     r8, rbx
0x18002c613  mov     r9, [rcx]
0x18002c616  mov     rax, [r9+58h]
0x18002c61a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c61f  mov     eax, edi
0x18002c621  mov     rcx, [rbp+1F0h+var_40]
0x18002c628  xor     rcx, rsp; StackCookie
0x18002c62b  call    __security_check_cookie
0x18002c630  add     rsp, 2C8h
0x18002c637  pop     r15
0x18002c639  pop     r14
0x18002c63b  pop     rdi
0x18002c63c  pop     rsi
0x18002c63d  pop     rbx
0x18002c63e  pop     rbp
0x18002c63f  retn
```
