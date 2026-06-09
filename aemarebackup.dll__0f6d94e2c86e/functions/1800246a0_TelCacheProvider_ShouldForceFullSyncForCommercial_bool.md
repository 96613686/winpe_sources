# TelCacheProvider::ShouldForceFullSyncForCommercial(bool)

- ea: `0x1800246a0`
- end: `0x1800248f4`
- name: `?ShouldForceFullSyncForCommercial@TelCacheProvider@@AEAAH_N@Z`
- size: `596`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024458`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x18001dbec`
- `0x180021354`
- `0x1800246a0`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002478e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002478e`

## string_xrefs

- `0x1800247b0`: `commercialId`
- `0x180024894`: `commercialId`
- `0x18002480a`: `Full sync may be needed because of Commercial ID change`
- `0x18002486e`: `Full sync may be needed because of Commercial 45 day sync policy`
- `0x18002487b`: `TelCacheProvider::ShouldForceFullSyncForCommercial`

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
0x1800246a0  push    rbp
0x1800246a2  push    rbx
0x1800246a3  push    rsi
0x1800246a4  push    rdi
0x1800246a5  push    r14
0x1800246a7  push    r15
0x1800246a9  lea     rbp, [rsp-1C8h]
0x1800246b1  sub     rsp, 2C8h
0x1800246b8  mov     rax, cs:__security_cookie
0x1800246bf  xor     rax, rsp
0x1800246c2  mov     [rbp+1F0h+var_40], rax
0x1800246c9  xor     r15d, r15d
0x1800246cc  mov     sil, dl
0x1800246cf  cmp     cs:?AlreadyRetrieved@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4_NA, r15b; bool `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::AlreadyRetrieved
0x1800246d6  mov     r14, rcx
0x1800246d9  mov     edi, r15d
0x1800246dc  jnz     loc_18002476C
0x1800246e2  xor     edx, edx; Val
0x1800246e4  lea     rcx, [rbp+1F0h+var_250]; void *
0x1800246e8  mov     r8d, 208h; Size
0x1800246ee  call    memset_0
0x1800246f3  lea     r9, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x1800246fa  mov     [rsp+2F0h+var_2D0], 1; int
0x180024702  lea     r8, aDatacollection; "DataCollectionGroupPolicy"
0x180024709  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x18002470d  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x180024712  lea     r9, [rbp+1F0h+var_250]
0x180024716  mov     ebx, eax
0x180024718  test    eax, eax
0x18002471a  jns     short loc_180024723
0x18002471c  lea     r9, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180024723  call    ?ReadString@?$RegistryKeyWrapper@$0?HPPPPPPO@@Shared@Compat@Windows@@SAJPEAG_KPEBG22@Z; Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(ushort *,unsigned __int64,ushort const *,ushort const *,ushort const *)
0x180024728  cmp     cs:?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA, r15w; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x180024730  jnz     short loc_180024765
0x180024732  lea     r9, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180024739  mov     [rsp+2F0h+var_2D0], 1; int
0x180024741  lea     r8, aDiagnosticsAll; "Diagnostics_AllowTelemetry"
0x180024748  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x18002474c  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x180024751  lea     r9, [rbp+1F0h+var_250]
0x180024755  test    ebx, ebx
0x180024757  jns     short loc_180024760
0x180024759  lea     r9, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180024760  call    ?ReadString@?$RegistryKeyWrapper@$0?HPPPPPPO@@Shared@Compat@Windows@@SAJPEAG_KPEBG22@Z; Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(ushort *,unsigned __int64,ushort const *,ushort const *,ushort const *)
0x180024765  mov     cs:?AlreadyRetrieved@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4_NA, 1; bool `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::AlreadyRetrieved
0x18002476c  xor     edx, edx; Val
0x18002476e  lea     rcx, [rsp+2F0h+var_2A0]; void *
0x180024773  lea     r8d, [rdx+50h]; Size
0x180024777  call    memset_0
0x18002477c  lea     rcx, [rsp+2F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180024781  mov     [rsp+2F0h+var_2C0], 28h ; '('
0x180024789  mov     qword ptr [rsp+2F0h+SystemTimeAsFileTime.dwLowDateTime], r15
0x18002478e  call    cs:__imp_GetSystemTimeAsFileTime
0x180024794  mov     rbx, qword ptr [rsp+2F0h+SystemTimeAsFileTime.dwLowDateTime]
0x180024799  test    sil, sil
0x18002479c  jnz     loc_18002488C
0x1800247a2  mov     rcx, [r14+58h]
0x1800247a6  lea     r9, [rsp+2F0h+var_2C0]
0x1800247ab  lea     r8, [rsp+2F0h+var_2A0]
0x1800247b0  lea     rdx, aCommercialid_0; "commercialId"
0x1800247b7  mov     rax, [rcx]
0x1800247ba  mov     rax, [rax+38h]
0x1800247be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247c3  mov     r9d, eax
0x1800247c6  cmp     eax, 80070002h
0x1800247cb  jnz     short loc_1800247D3
0x1800247cd  mov     [rsp+2F0h+var_2A0], r15w
0x1800247d3  lea     rax, [rsp+2F0h+var_2A0]
0x1800247d8  lea     rdx, ?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x1800247df  sub     rdx, rax
0x1800247e2  movzx   ecx, word ptr [rax]
0x1800247e5  movzx   r8d, word ptr [rax+rdx]
0x1800247ea  sub     ecx, r8d
0x1800247ed  jnz     short loc_1800247F8
0x1800247ef  add     rax, 2
0x1800247f3  test    r8d, r8d
0x1800247f6  jnz     short loc_1800247E2
0x1800247f8  test    ecx, ecx
0x1800247fa  jz      short loc_180024819
0x1800247fc  mov     edi, 1
0x180024801  test    r9d, r9d
0x180024804  js      loc_18002488C
0x18002480a  lea     r9, aFullSyncMayBeN_3; "Full sync may be needed because of Comm"...
0x180024811  mov     r8d, 7D4h
0x180024817  jmp     short loc_18002487B
0x180024819  cmp     cs:?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA, r15w; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x180024821  jz      loc_1800248D3
0x180024827  mov     rcx, [r14+58h]
0x18002482b  lea     r8, [rsp+2F0h+var_2B0]
0x180024830  mov     [rsp+2F0h+var_2B0], r15
0x180024835  lea     rdx, aLastfullsync; "lastFullSync"
0x18002483c  mov     rax, [rcx]
0x18002483f  mov     rax, [rax+40h]
0x180024843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024848  test    eax, eax
0x18002484a  js      short loc_180024869
0x18002484c  mov     rax, rbx
0x18002484f  mov     rcx, 235C7496C000h
0x180024859  sub     rax, [rsp+2F0h+var_2B0]
0x18002485e  cmp     rax, rcx
0x180024861  setnbe  dil
0x180024865  jbe     short loc_1800248D3
0x180024867  jmp     short loc_18002488C
0x180024869  mov     edi, 1
0x18002486e  lea     r9, aFullSyncMayBeN; "Full sync may be needed because of Comm"...
0x180024875  mov     r8d, 7E2h
0x18002487b  lea     rdx, aTelcacheprovid_26; "TelCacheProvider::ShouldForceFullSyncFo"...
0x180024882  mov     ecx, 3
0x180024887  call    AslLogCallPrintf
0x18002488c  cmp     cs:?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA, r15w; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x180024894  lea     rdx, aCommercialid_0; "commercialId"
0x18002489b  mov     rcx, [r14+58h]
0x18002489f  mov     rax, [rcx]
0x1800248a2  mov     rax, [rax+50h]
0x1800248a6  jz      short loc_1800248B1
0x1800248a8  lea     r8, ?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x1800248af  jmp     short loc_1800248B4
0x1800248b1  xor     r8d, r8d
0x1800248b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248b9  mov     rcx, [r14+58h]
0x1800248bd  lea     rdx, aLastfullsync; "lastFullSync"
0x1800248c4  mov     r8, rbx
0x1800248c7  mov     r9, [rcx]
0x1800248ca  mov     rax, [r9+58h]
0x1800248ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248d3  mov     eax, edi
0x1800248d5  mov     rcx, [rbp+1F0h+var_40]
0x1800248dc  xor     rcx, rsp; StackCookie
0x1800248df  call    __security_check_cookie
0x1800248e4  add     rsp, 2C8h
0x1800248eb  pop     r15
0x1800248ed  pop     r14
0x1800248ef  pop     rdi
0x1800248f0  pop     rsi
0x1800248f1  pop     rbx
0x1800248f2  pop     rbp
0x1800248f3  retn
```
