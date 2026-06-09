# CUserTileStore::GetUserNameW(uint,ushort * *)

- ea: `0x180006610`
- end: `0x180006843`
- name: `?GetUserNameW@CUserTileStore@@UEAAJIPEAPEAG@Z`
- size: `563`
- prototype: `int(CUserTileStore *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800064d4`
- `0x180006610`
- `0x18000684c`
- `0x1800068ac`
- `0x180006960`
- `0x180006990`
- `0x18000a910`
- `0x18003aa84`
- `0x180051524`
- `0x1800c6d24`
- `0x1800c70e0`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000673b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000673b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000671e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800067a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800067eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000671e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800067a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800067eb`
- `SspiCli!GetUserNameExW` at `0x1800066f5`
- `SspiCli!GetUserNameExW` at `0x18000677c`
- `SspiCli!GetUserNameExW` at `0x1800066f5`
- `SspiCli!GetUserNameExW` at `0x18000677c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUserTileStore::GetUserNameW(CUserTileStore *this, EXTENDED_NAME_FORMAT a2, unsigned __int16 **a3)
{
  __int64 (__fastcall *v6)(CUserTileStore *, unsigned __int16 **, unsigned __int16 **); // rdi
  unsigned __int16 **v7; // r8
  unsigned __int16 **v8; // rdx
  int Error; // edi
  unsigned __int16 *v10; // rax
  CUserTileStore *v11; // rcx
  unsigned __int16 *v12; // rsi
  unsigned __int16 *v13; // rbx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r15
  size_t v16; // rax
  unsigned __int16 *v17; // rax
  bool IsDomainUser; // bl
  __int64 v19; // rcx
  wil::TraceLoggingProvider *v20; // rax
  unsigned __int8 v21; // dl
  unsigned __int64 v22; // r8
  __int64 v23; // rcx
  UserInfoTelemetry *v24; // rcx
  unsigned __int16 *v26; // [rsp+30h] [rbp-20h] BYREF
  __int64 v27; // [rsp+38h] [rbp-18h]
  __int64 v28; // [rsp+40h] [rbp-10h]
  ULONG nSize; // [rsp+98h] [rbp+48h] BYREF
  unsigned __int16 *v30; // [rsp+A0h] [rbp+50h]

  *a3 = 0;
  if ( CUserTileStore::_IsDomainUser(this) && (unsigned int)(a2 - 13) <= 1 )
  {
    v26 = 0;
    v27 = 0;
    v28 = 0;
    v6 = *(__int64 (__fastcall **)(CUserTileStore *, unsigned __int16 **, unsigned __int16 **))(*(_QWORD *)this + 136LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v26);
    v27 = -1;
    v28 = -1;
    if ( a2 == NameGivenName )
    {
      v7 = 0;
      v8 = &v26;
    }
    else
    {
      v7 = &v26;
      v8 = 0;
    }
    Error = v6(this, v8, v7);
    if ( Error >= 0 )
    {
      v10 = v26;
      v26 = 0;
      v28 = 0;
      v27 = 0;
      *a3 = v10;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v26);
    goto LABEL_31;
  }
  v27 = -1;
  v28 = -1;
  v12 = 0;
  v26 = 0;
  nSize = 0;
  if ( !GetUserNameExW(a2, 0, &nSize) )
  {
    Error = ResultFromKnownLastError();
    if ( Error != -2147024662 )
      goto LABEL_23;
    v30 = 0;
    CoTaskMemFree(0);
    v13 = 0;
    v30 = 0;
    if ( !is_mul_ok(nSize, 2u) )
    {
      Error = -2147024362;
      goto LABEL_22;
    }
    v14 = (unsigned __int16 *)CoTaskMemAlloc(2LL * nSize);
    v15 = v14;
    v13 = v14;
    v30 = v14;
    if ( v14 )
    {
      v16 = CTCoAllocPolicy::_CoTaskMemSize(v14);
      memset_0(v13, 0, v16);
      Error = 0;
    }
    else
    {
      Error = -2147024882;
    }
    if ( Error < 0 )
      goto LABEL_22;
    if ( GetUserNameExW(a2, v13, &nSize) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
LABEL_22:
        CoTaskMemFree(v13);
        goto LABEL_23;
      }
    }
    v13 = 0;
    v12 = v15;
    v26 = v15;
    goto LABEL_22;
  }
  Error = 0;
LABEL_23:
  if ( Error < 0 )
  {
    if ( a2 == NameDisplay )
    {
      if ( Error != -2147023564 || (Error = CUserTileStore::_GetInternetPrincipalName(v11, a3), Error < 0) )
        Error = CUserTileStore::_GetLocalAccountDisplayName(v11, a3);
    }
  }
  else
  {
    v17 = v12;
    v12 = 0;
    *a3 = v17;
  }
  if ( v12 )
    CoTaskMemFree(v12);
LABEL_31:
  IsDomainUser = CUserTileStore::_IsDomainUser(v11);
  v20 = (wil::TraceLoggingProvider *)wil::details::static_lazy<UserInfoTelemetry>::get(
                                       v19,
                                       _lambda_ce69ed42d60ac1ca0172729e13171e74_::_lambda_invoker_cdecl_);
  if ( wil::TraceLoggingProvider::IsEnabled_(v20, v21, v22) )
  {
    wil::details::static_lazy<UserInfoTelemetry>::get(
      v23,
      _lambda_ce69ed42d60ac1ca0172729e13171e74_::_lambda_invoker_cdecl_);
    UserInfoTelemetry::GetUserNameEvent_(v24, 0x23C2u, Error, IsDomainUser, a2);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180006610  push    rbp
0x180006612  push    rbx
0x180006613  push    rsi
0x180006614  push    rdi
0x180006615  push    r12
0x180006617  push    r14
0x180006619  push    r15
0x18000661b  mov     rbp, rsp
0x18000661e  sub     rsp, 50h
0x180006622  mov     r12, r8
0x180006625  mov     r14d, edx
0x180006628  mov     rbx, rcx
0x18000662b  mov     qword ptr [r8], 0
0x180006632  call    ?_IsDomainUser@CUserTileStore@@AEAA_NXZ; CUserTileStore::_IsDomainUser(void)
0x180006637  test    al, al
0x180006639  jz      loc_1800066D7
0x18000663f  lea     eax, [r14-0Dh]
0x180006643  cmp     eax, 1
0x180006646  ja      loc_1800066D7
0x18000664c  mov     [rbp+var_20], 0
0x180006654  mov     [rbp+var_18], 0
0x18000665c  mov     [rbp+var_10], 0
0x180006664  mov     rax, [rbx]
0x180006667  mov     rdi, [rax+88h]
0x18000666e  lea     rcx, [rbp+var_20]
0x180006672  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180006677  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000667b  mov     rcx, rbx
0x18000667e  mov     [rbp+var_18], rax
0x180006682  mov     [rbp+var_10], rax
0x180006686  mov     rax, rdi
0x180006689  cmp     r14d, 0Dh
0x18000668d  jnz     short loc_180006698
0x18000668f  xor     r8d, r8d
0x180006692  lea     rdx, [rbp+var_20]
0x180006696  jmp     short loc_18000669E
0x180006698  lea     r8, [rbp+var_20]
0x18000669c  xor     edx, edx
0x18000669e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066a3  mov     edi, eax
0x1800066a5  test    eax, eax
0x1800066a7  js      short loc_1800066C9
0x1800066a9  mov     rax, [rbp+var_20]
0x1800066ad  mov     [rbp+var_20], 0
0x1800066b5  mov     [rbp+var_10], 0
0x1800066bd  mov     [rbp+var_18], 0
0x1800066c5  mov     [r12], rax
0x1800066c9  lea     rcx, [rbp+var_20]
0x1800066cd  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800066d2  jmp     loc_1800067F1
0x1800066d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800066db  mov     [rbp+var_18], rax
0x1800066df  mov     [rbp+var_10], rax
0x1800066e3  xor     esi, esi
0x1800066e5  mov     [rbp+var_20], rsi
0x1800066e9  mov     [rbp+nSize], esi
0x1800066ec  lea     r8, [rbp+nSize]; nSize
0x1800066f0  xor     edx, edx; lpNameBuffer
0x1800066f2  mov     ecx, r14d; NameFormat
0x1800066f5  call    cs:__imp_GetUserNameExW
0x1800066fb  test    al, al
0x1800066fd  jz      short loc_180006706
0x1800066ff  xor     edi, edi
0x180006701  jmp     loc_1800067AE
0x180006706  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000670b  mov     edi, eax
0x18000670d  cmp     eax, 800700EAh
0x180006712  jnz     loc_1800067AE
0x180006718  mov     [rbp+arg_10], rsi
0x18000671c  xor     ecx, ecx; pv
0x18000671e  call    cs:__imp_CoTaskMemFree
0x180006724  xor     ebx, ebx
0x180006726  mov     [rbp+arg_10], rbx
0x18000672a  mov     ecx, [rbp+nSize]
0x18000672d  lea     eax, [rbx+2]
0x180006730  mul     rcx
0x180006733  test    rdx, rdx
0x180006736  jnz     short loc_1800067A0
0x180006738  mov     rcx, rax; cb
0x18000673b  call    cs:__imp_CoTaskMemAlloc
0x180006741  mov     r15, rax
0x180006744  mov     rbx, rax
0x180006747  mov     [rbp+arg_10], rax
0x18000674b  test    rax, rax
0x18000674e  jz      short loc_180006769
0x180006750  mov     rcx, rax; void *
0x180006753  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180006758  mov     r8, rax; Size
0x18000675b  xor     edx, edx; Val
0x18000675d  mov     rcx, rbx; void *
0x180006760  call    memset_0
0x180006765  xor     edi, edi
0x180006767  jmp     short loc_18000676E
0x180006769  mov     edi, 8007000Eh
0x18000676e  test    edi, edi
0x180006770  js      short loc_1800067A5
0x180006772  lea     r8, [rbp+nSize]; nSize
0x180006776  mov     rdx, rbx; lpNameBuffer
0x180006779  mov     ecx, r14d; NameFormat
0x18000677c  call    cs:__imp_GetUserNameExW
0x180006782  test    al, al
0x180006784  jz      short loc_18000678A
0x180006786  xor     edi, edi
0x180006788  jmp     short loc_180006795
0x18000678a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000678f  mov     edi, eax
0x180006791  test    eax, eax
0x180006793  js      short loc_1800067A5
0x180006795  xor     ebx, ebx
0x180006797  mov     rsi, r15
0x18000679a  mov     [rbp+var_20], r15
0x18000679e  jmp     short loc_1800067A5
0x1800067a0  mov     edi, 80070216h
0x1800067a5  mov     rcx, rbx; pv
0x1800067a8  call    cs:__imp_CoTaskMemFree
0x1800067ae  test    edi, edi
0x1800067b0  js      short loc_1800067BD
0x1800067b2  mov     rax, rsi
0x1800067b5  xor     esi, esi
0x1800067b7  mov     [r12], rax
0x1800067bb  jmp     short loc_1800067E3
0x1800067bd  cmp     r14d, 3
0x1800067c1  jnz     short loc_1800067E3
0x1800067c3  cmp     edi, 80070534h
0x1800067c9  jnz     short loc_1800067D9
0x1800067cb  mov     rdx, r12; unsigned __int16 **
0x1800067ce  call    ?_GetInternetPrincipalName@CUserTileStore@@AEAAJPEAPEAG@Z; CUserTileStore::_GetInternetPrincipalName(ushort * *)
0x1800067d3  mov     edi, eax
0x1800067d5  test    eax, eax
0x1800067d7  jns     short loc_1800067E3
0x1800067d9  mov     rdx, r12; unsigned __int16 **
0x1800067dc  call    ?_GetLocalAccountDisplayName@CUserTileStore@@AEAAJPEAPEAG@Z; CUserTileStore::_GetLocalAccountDisplayName(ushort * *)
0x1800067e1  mov     edi, eax
0x1800067e3  test    rsi, rsi
0x1800067e6  jz      short loc_1800067F1
0x1800067e8  mov     rcx, rsi; pv
0x1800067eb  call    cs:__imp_CoTaskMemFree
0x1800067f1  call    ?_IsDomainUser@CUserTileStore@@AEAA_NXZ; CUserTileStore::_IsDomainUser(void)
0x1800067f6  mov     bl, al
0x1800067f8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_ce69ed42d60ac1ca0172729e13171e74_@@CA@XZ; _lambda_ce69ed42d60ac1ca0172729e13171e74_::_lambda_invoker_cdecl_(void)
0x1800067ff  call    ?get@?$static_lazy@VUserInfoTelemetry@@@details@wil@@QEAAPEAVUserInfoTelemetry@@P6AXXZ@Z; wil::details::static_lazy<UserInfoTelemetry>::get(void (*)(void))
0x180006804  mov     rcx, rax; this
0x180006807  call    ?IsEnabled_@TraceLoggingProvider@wil@@IEBA_NE_K@Z; wil::TraceLoggingProvider::IsEnabled_(uchar,unsigned __int64)
0x18000680c  test    al, al
0x18000680e  jz      short loc_180006832
0x180006810  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_ce69ed42d60ac1ca0172729e13171e74_@@CA@XZ; _lambda_ce69ed42d60ac1ca0172729e13171e74_::_lambda_invoker_cdecl_(void)
0x180006817  call    ?get@?$static_lazy@VUserInfoTelemetry@@@details@wil@@QEAAPEAVUserInfoTelemetry@@P6AXXZ@Z; wil::details::static_lazy<UserInfoTelemetry>::get(void (*)(void))
0x18000681c  mov     [rsp+50h+var_30], r14d; enum EXTENDED_NAME_FORMAT
0x180006821  mov     r9b, bl; bool
0x180006824  mov     r8d, edi; int
0x180006827  mov     edx, 23C2h; unsigned int
0x18000682c  call    ?GetUserNameEvent_@UserInfoTelemetry@@QEAAXKJ_NW4EXTENDED_NAME_FORMAT@@@Z; UserInfoTelemetry::GetUserNameEvent_(ulong,long,bool,EXTENDED_NAME_FORMAT)
0x180006831  nop
0x180006832  mov     eax, edi
0x180006834  add     rsp, 50h
0x180006838  pop     r15
0x18000683a  pop     r14
0x18000683c  pop     r12
0x18000683e  pop     rdi
0x18000683f  pop     rsi
0x180006840  pop     rbx
0x180006841  pop     rbp
0x180006842  retn
```
