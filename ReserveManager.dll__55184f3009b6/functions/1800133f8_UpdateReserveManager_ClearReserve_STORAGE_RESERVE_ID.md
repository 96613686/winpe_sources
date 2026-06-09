# UpdateReserveManager::ClearReserve(_STORAGE_RESERVE_ID)

- ea: `0x1800133f8`
- end: `0x1800135f1`
- name: `?ClearReserve@UpdateReserveManager@@AEAAJW4_STORAGE_RESERVE_ID@@@Z`
- size: `505`
- prototype: `__int64 __fastcall(UpdateReserveManager *this, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800133c4`
- `0x180013600`
- `0x18001b8f0`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x1800133f8`
- `0x180015ad0`
- `0x18001cb28`
- `0x18001d53c`
- `0x180021e80`
- `0x1800262e0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800134a0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800134a0`

## string_xrefs

- `0x1800134ba`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800134cd`: `UpdateReserveManager::ClearReserve`
- `0x18001346c`: `DisableDeletes`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::ClearReserve(UpdateReserveManager *this, unsigned int a2)
{
  __int64 result; // rax
  int v5; // r14d
  HKEY v6; // rcx
  int ValueW; // ebx
  char IsEnabled; // al
  __int64 v9; // r8
  int pvData; // [rsp+28h] [rbp-21h]
  __int128 v11; // [rsp+40h] [rbp-9h] BYREF
  unsigned __int64 v12; // [rsp+50h] [rbp+7h]
  const char *v13; // [rsp+58h] [rbp+Fh]
  __int128 v14; // [rsp+60h] [rbp+17h] BYREF
  unsigned __int64 v15; // [rsp+70h] [rbp+27h]
  int v16; // [rsp+78h] [rbp+2Fh] BYREF
  DWORD pcbData; // [rsp+7Ch] [rbp+33h] BYREF

  result = UpdateReserveManager::EnsureNotInSafeMode(this);
  if ( (int)result >= 0 )
  {
    v5 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl)
      && a2 == 1 )
    {
      v5 = (*(__int64 (__fastcall **)(UpdateReserveManager *))(*(_QWORD *)this + 176LL))(this);
    }
    v6 = (HKEY)*((_QWORD *)this + 13);
    v16 = 0;
    pcbData = 4;
    ValueW = RegGetValueW(
               v6,
               L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
               L"DisableDeletes",
               0x10u,
               0,
               &v16,
               &pcbData);
    if ( ValueW == 2 )
    {
      v16 = 1;
LABEL_12:
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl);
      CUpdateReserveManagerDiagnostics::ReportClearReserve(
        (const char *)this + 1200,
        1u,
        a2,
        0,
        0,
        IsEnabled != 0 ? v5 : 0);
      return 0;
    }
    if ( ValueW )
    {
      v12 = 2848;
      *(_QWORD *)&v11 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      *((_QWORD *)&v11 + 1) = "UpdateReserveManager::ClearReserve";
      v13 = "RetValue";
      if ( ValueW > 0 )
        ValueW = (unsigned __int16)ValueW | 0x80070000;
      RtlReportErrorOrigination(&v11, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)ValueW);
      return (unsigned int)ValueW;
    }
    else
    {
      if ( v16 )
        goto LABEL_12;
      v12 = 0;
      v11 = 0;
      result = UpdateReserveManager::QueryReserveAreaByReserveId(this, 0, a2, &v11);
      if ( (int)result >= 0 )
      {
        StorageReserveHelper::DeleteReserveAreaContent(
          (UpdateReserveManager *)((char *)this + 656),
          (const unsigned __int16 *)a2,
          v9);
        v15 = 0;
        v14 = 0;
        result = UpdateReserveManager::QueryReserveAreaByReserveId(this, 0, a2, &v14);
        if ( (int)result >= 0 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
            pvData = v5;
          else
            pvData = 0;
          CUpdateReserveManagerDiagnostics::ReportClearReserve((const char *)this + 1200, 0, a2, v12, v15, pvData);
          return 0;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800133f8  mov     [rsp-8+arg_10], rbx
0x1800133fd  mov     [rsp-8+arg_18], rsi
0x180013402  push    rbp
0x180013403  push    rdi
0x180013404  push    r14
0x180013406  lea     rbp, [rsp-47h]
0x18001340b  sub     rsp, 90h
0x180013412  mov     rax, cs:__security_cookie
0x180013419  xor     rax, rsp
0x18001341c  mov     [rbp+57h+var_20], rax
0x180013420  mov     esi, edx
0x180013422  mov     rdi, rcx
0x180013425  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001342a  test    eax, eax
0x18001342c  js      loc_1800135CD
0x180013432  xor     r14d, r14d
0x180013435  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18001343c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x180013441  test    al, al
0x180013443  jz      short loc_18001345F
0x180013445  cmp     esi, 1
0x180013448  jnz     short loc_18001345F
0x18001344a  mov     rax, [rdi]
0x18001344d  mov     rcx, rdi
0x180013450  mov     rax, [rax+0B0h]
0x180013457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001345c  mov     r14d, eax
0x18001345f  mov     rcx, [rdi+68h]; hkey
0x180013463  lea     rax, [rbp+57h+var_24]
0x180013467  mov     [rsp+0A0h+pcbData], rax; pcbData
0x18001346c  lea     r8, aDisabledeletes; "DisableDeletes"
0x180013473  lea     rax, [rbp+57h+var_28]
0x180013477  mov     [rbp+57h+var_28], 0
0x18001347e  mov     [rsp+0A0h+pvData], rax; pvData
0x180013483  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x18001348a  mov     r9d, 10h; dwFlags
0x180013490  mov     [rsp+0A0h+pdwType], 0; pdwType
0x180013499  mov     [rbp+57h+var_24], 4
0x1800134a0  call    cs:__imp_RegGetValueW
0x1800134a6  mov     ebx, eax
0x1800134a8  cmp     eax, 2
0x1800134ab  jnz     short loc_1800134B6
0x1800134ad  mov     [rbp+57h+var_28], 1
0x1800134b4  jmp     short loc_18001350E
0x1800134b6  test    ebx, ebx
0x1800134b8  jz      short loc_180013508
0x1800134ba  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800134c1  mov     [rbp+57h+var_50], 0B20h
0x1800134c9  mov     qword ptr [rbp+57h+var_60], rax
0x1800134cd  lea     rax, aUpdatereservem_47; "UpdateReserveManager::ClearReserve"
0x1800134d4  mov     qword ptr [rbp+57h+var_60+8], rax
0x1800134d8  lea     rax, aRetvalue; "RetValue"
0x1800134df  mov     [rbp+57h+var_48], rax
0x1800134e3  jle     short loc_1800134EE
0x1800134e5  movzx   ebx, bx
0x1800134e8  or      ebx, 80070000h
0x1800134ee  mov     r8d, ebx
0x1800134f1  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800134f8  lea     rcx, [rbp+57h+var_60]
0x1800134fc  call    RtlReportErrorOrigination
0x180013501  mov     eax, ebx
0x180013503  jmp     loc_1800135CD
0x180013508  cmp     [rbp+57h+var_28], 0
0x18001350c  jz      short loc_18001353C
0x18001350e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x180013515  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18001351a  neg     al
0x18001351c  sbb     r8d, r8d
0x18001351f  and     r8d, r14d
0x180013522  xor     r9d, r9d
0x180013525  mov     dword ptr [rsp+0A0h+pvData], r8d
0x18001352a  mov     [rsp+0A0h+pdwType], 0
0x180013533  lea     edx, [r9+1]
0x180013537  jmp     loc_1800135BC
0x18001353c  xorps   xmm0, xmm0
0x18001353f  lea     r9, [rbp+57h+var_60]
0x180013543  xor     eax, eax
0x180013545  mov     r8d, esi
0x180013548  xor     edx, edx
0x18001354a  mov     [rbp+57h+var_50], rax
0x18001354e  mov     rcx, rdi
0x180013551  movups  [rbp+57h+var_60], xmm0
0x180013555  call    ?QueryReserveAreaByReserveId@UpdateReserveManager@@AEAAJW4QueryReserveAreaFlags@IUpdateReserveManager@@W4_STORAGE_RESERVE_ID@@PEAURESERVE_AREA_INFORMATION@3@@Z; UpdateReserveManager::QueryReserveAreaByReserveId(IUpdateReserveManager::QueryReserveAreaFlags,_STORAGE_RESERVE_ID,IUpdateReserveManager::RESERVE_AREA_INFORMATION *)
0x18001355a  test    eax, eax
0x18001355c  js      short loc_1800135CD
0x18001355e  lea     rcx, [rdi+290h]; this
0x180013565  mov     edx, esi; unsigned __int16 *
0x180013567  call    ?DeleteReserveAreaContent@StorageReserveHelper@@YAJPEBGW4_STORAGE_RESERVE_ID@@@Z; StorageReserveHelper::DeleteReserveAreaContent(ushort const *,_STORAGE_RESERVE_ID)
0x18001356c  xorps   xmm0, xmm0
0x18001356f  lea     r9, [rbp+57h+var_40]
0x180013573  xor     eax, eax
0x180013575  mov     r8d, esi
0x180013578  xor     edx, edx
0x18001357a  mov     [rbp+57h+var_30], rax
0x18001357e  mov     rcx, rdi
0x180013581  movups  [rbp+57h+var_40], xmm0
0x180013585  call    ?QueryReserveAreaByReserveId@UpdateReserveManager@@AEAAJW4QueryReserveAreaFlags@IUpdateReserveManager@@W4_STORAGE_RESERVE_ID@@PEAURESERVE_AREA_INFORMATION@3@@Z; UpdateReserveManager::QueryReserveAreaByReserveId(IUpdateReserveManager::QueryReserveAreaFlags,_STORAGE_RESERVE_ID,IUpdateReserveManager::RESERVE_AREA_INFORMATION *)
0x18001358a  test    eax, eax
0x18001358c  js      short loc_1800135CD
0x18001358e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x180013595  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18001359a  mov     r9, [rbp+57h+var_50]; unsigned __int64
0x18001359e  xor     edx, edx; unsigned int
0x1800135a0  test    al, al
0x1800135a2  mov     rax, [rbp+57h+var_30]
0x1800135a6  jz      short loc_1800135AF
0x1800135a8  mov     dword ptr [rsp+0A0h+pvData], r14d
0x1800135ad  jmp     short loc_1800135B7
0x1800135af  mov     dword ptr [rsp+0A0h+pvData], 0; int
0x1800135b7  mov     [rsp+0A0h+pdwType], rax; unsigned __int64
0x1800135bc  mov     r8d, esi; unsigned int
0x1800135bf  lea     rcx, [rdi+4B0h]; char *
0x1800135c6  call    ?ReportClearReserve@CUpdateReserveManagerDiagnostics@@SAXPEBDKK_K1J@Z; CUpdateReserveManagerDiagnostics::ReportClearReserve(char const *,ulong,ulong,unsigned __int64,unsigned __int64,long)
0x1800135cb  xor     eax, eax
0x1800135cd  mov     rcx, [rbp+57h+var_20]
0x1800135d1  xor     rcx, rsp; StackCookie
0x1800135d4  call    __security_check_cookie
0x1800135d9  lea     r11, [rsp+0A0h+var_10]
0x1800135e1  mov     rbx, [r11+30h]
0x1800135e5  mov     rsi, [r11+38h]
0x1800135e9  mov     rsp, r11
0x1800135ec  pop     r14
0x1800135ee  pop     rdi
0x1800135ef  pop     rbp
0x1800135f0  retn
```
