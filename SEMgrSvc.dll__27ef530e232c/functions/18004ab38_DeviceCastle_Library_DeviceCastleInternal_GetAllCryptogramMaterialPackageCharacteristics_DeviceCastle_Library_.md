# DeviceCastle::Library::DeviceCastleInternal::GetAllCryptogramMaterialPackageCharacteristics(DeviceCastle::Library::CallerIdentity &,ushort const *,_GetAllCryptogramMaterialPackageCharacteristicsResult * *)

- ea: `0x18004ab38`
- end: `0x18004aff5`
- name: `?GetAllCryptogramMaterialPackageCharacteristics@DeviceCastleInternal@Library@DeviceCastle@@QEAAJAEAVCallerIdentity@23@PEBGPEAPEAU_GetAllCryptogramMaterialPackageCharacteristicsResult@@@Z`
- size: `1213`
- prototype: `__int64 __fastcall(DeviceCastle::Library::DeviceCastleInternal *__hidden this, struct DeviceCastle::Library::CallerIdentity *, const unsigned __int16 *, struct _GetAllCryptogramMaterialPackageCharacteristicsResult **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180042b40`

## callees

- `0x180005858`
- `0x1800106ac`
- `0x180044ee0`
- `0x1800457b0`
- `0x180048ee4`
- `0x1800492f8`
- `0x180049458`
- `0x180049908`
- `0x18004ab38`
- `0x18004d238`
- `0x18004d298`
- `0x18004d2cc`
- `0x18004d5c0`
- `0x18004db3c`
- `0x18004dc80`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004addc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ae6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004af4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004af60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004af93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004afa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004addc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ae6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004af4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004af60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004af93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004afa7`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall DeviceCastle::Library::DeviceCastleInternal::GetAllCryptogramMaterialPackageCharacteristics(
        DeviceCastle::Library::DeviceCastleInternal *this,
        struct DeviceCastle::Library::CallerIdentity *a2,
        const unsigned __int16 *a3,
        struct _GetAllCryptogramMaterialPackageCharacteristicsResult **a4)
{
  int v7; // ebx
  const unsigned __int16 *v8; // r14
  char *v9; // rdi
  __int64 v10; // rcx
  volatile signed __int32 *v11; // rdi
  int v12; // eax
  volatile signed __int32 *v13; // rbx
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdi
  __int64 i; // rcx
  const unsigned __int16 *v17; // rax
  signed __int64 v18; // r14
  _QWORD *cotaskmem_string; // rax
  __int64 v20; // rbx
  const unsigned __int16 *v21; // rax
  signed __int64 v22; // r14
  _QWORD *v23; // rax
  void *v24; // rcx
  struct _GetAllCryptogramMaterialPackageCharacteristicsResult *v25; // rax
  unsigned __int64 v26; // r8
  unsigned __int64 v27; // r8
  void *v28; // rcx
  void *v29; // rcx
  void *v30; // rcx
  void *v31; // rcx
  LPVOID v33; // [rsp+20h] [rbp-49h] BYREF
  __int128 v34; // [rsp+28h] [rbp-41h] BYREF
  __int64 v35; // [rsp+38h] [rbp-31h]
  void *v36[2]; // [rsp+40h] [rbp-29h] BYREF
  void *v37; // [rsp+50h] [rbp-19h]
  void *v38[2]; // [rsp+58h] [rbp-11h] BYREF
  void *v39; // [rsp+68h] [rbp-1h]
  LPVOID v40[2]; // [rsp+70h] [rbp+7h] BYREF
  LPVOID pv[8]; // [rsp+80h] [rbp+17h] BYREF
  const unsigned __int16 *v42; // [rsp+E0h] [rbp+77h] BYREF
  void *v43; // [rsp+E8h] [rbp+7Fh] BYREF

  v42 = a3;
  v34 = 0;
  v35 = 0;
  if ( !a4 )
  {
    v7 = -2147467261;
    goto LABEL_60;
  }
  *a4 = 0;
  if ( a3 && *a3 == 42 && !a3[1] )
  {
    v7 = DeviceCastle::Library::DeviceCastleInternal::VerifyAllStorageKeysStillExist(this, a2);
    if ( v7 < 0 )
      goto LABEL_60;
    v8 = 0;
    v9 = (char *)this + 176;
    goto LABEL_21;
  }
  if ( !(unsigned __int8)DeviceCastle::Library::ValidOrDefaultName(&v42) )
  {
    v7 = -2134834648;
    goto LABEL_60;
  }
  *(_OWORD *)v40 = 0;
  v9 = (char *)this + 176;
  v8 = v42;
  if ( (unsigned __int8)DeviceCastle::Library::Internal::DeviceCastleDatabase::GetProtectionKey(v9, a2, v42, v40) )
  {
    v12 = DeviceCastle::Library::DeviceCastleInternal::VerifyStorageKeyStillExists(v10, a2, v40);
    v7 = v12;
    if ( v12 < 0 )
      goto LABEL_11;
    if ( !v12 )
    {
      v13 = (volatile signed __int32 *)v40[1];
      if ( v40[1] )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)v40[1] + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( !_InterlockedDecrement(v13 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
LABEL_21:
      if ( (unsigned __int8)DeviceCastle::Library::Internal::DeviceCastleDatabase::EnumeratePackages(v9, a2, v8, &v34) )
      {
        *(_OWORD *)v38 = 0;
        v39 = 0;
        *(_OWORD *)v36 = 0;
        v37 = 0;
        wil::make_unique_cotaskmem<_GetAllCryptogramMaterialPackageCharacteristicsResult,>(&v33);
        wil::make_unique_cotaskmem<_CryptogramMaterialPackageCharacteristics [0]>(
          &v43,
          (__int64)(*((_QWORD *)&v34 + 1) - v34) >> 4);
        memset_0(v43, 0, 32 * ((__int64)(*((_QWORD *)&v34 + 1) - v34) >> 4));
        *(_OWORD *)v33 = 0;
        v14 = (__int64)(*((_QWORD *)&v34 + 1) - v34) >> 4;
        if ( v14 > 0xFFFFFFFF )
        {
          *(_DWORD *)v33 = -1;
          v7 = -2147024362;
          v30 = v43;
          v43 = 0;
          if ( v30 )
            CoTaskMemFree(v30);
          v31 = v33;
          v33 = 0;
          if ( v31 )
            CoTaskMemFree(v31);
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v36);
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v38);
        }
        else
        {
          *(_DWORD *)v33 = v14;
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::reserve(
            v38,
            (__int64)(*((_QWORD *)&v34 + 1) - v34) >> 4);
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::reserve(
            v36,
            (__int64)(*((_QWORD *)&v34 + 1) - v34) >> 4);
          v15 = 0;
          for ( i = v34; v15 < (__int64)(*((_QWORD *)&v34 + 1) - v34) >> 4; i = v34 )
          {
            v17 = (const unsigned __int16 *)DeviceCastle::Library::UserSafeName(*(_QWORD *)(i + 16 * v15), a2);
            if ( v17 )
            {
              v18 = ((char *)v38[1] - (char *)v38[0]) >> 3;
              cotaskmem_string = (_QWORD *)wil::make_cotaskmem_string((wil *)pv, v17, 0xFFFFFFFFFFFFFFFFuLL);
              if ( v38[1] == v39 )
              {
                std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                  v38,
                  v38[1],
                  cotaskmem_string);
              }
              else
              {
                *(_QWORD *)v38[1] = *cotaskmem_string;
                *cotaskmem_string = 0;
                v38[1] = (char *)v38[1] + 8;
              }
              if ( pv[0] )
                CoTaskMemFree(pv[0]);
              v20 = 32 * v15;
              *((_QWORD *)v43 + 4 * v15) = *((_QWORD *)v38[0] + v18);
            }
            else
            {
              v20 = 32 * v15;
            }
            v21 = (const unsigned __int16 *)DeviceCastle::Library::UserSafeName(
                                              *(_QWORD *)(*(_QWORD *)(v34 + 16 * v15) + 32LL) + 16LL,
                                              a2);
            if ( v21 )
            {
              v22 = ((char *)v36[1] - (char *)v36[0]) >> 3;
              v23 = (_QWORD *)wil::make_cotaskmem_string((wil *)v40, v21, 0xFFFFFFFFFFFFFFFFuLL);
              if ( v36[1] == v37 )
              {
                std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                  v36,
                  v36[1],
                  v23);
              }
              else
              {
                *(_QWORD *)v36[1] = *v23;
                *v23 = 0;
                v36[1] = (char *)v36[1] + 8;
              }
              if ( v40[0] )
                CoTaskMemFree(v40[0]);
              *(_QWORD *)((char *)v43 + v20 + 8) = *((_QWORD *)v36[0] + v22);
            }
            *(_QWORD *)((char *)v43 + v20 + 16) = *(_QWORD *)(*(_QWORD *)(v34 + 16 * v15) + 88LL);
            *(_DWORD *)((char *)v43 + v20 + 24) = *(_DWORD *)(*(_QWORD *)(v34 + 16 * v15++) + 48LL);
          }
          v24 = v43;
          v43 = 0;
          *((_QWORD *)v33 + 1) = v24;
          v25 = (struct _GetAllCryptogramMaterialPackageCharacteristicsResult *)v33;
          v33 = 0;
          *a4 = v25;
          v26 = (unsigned __int64)((char *)v38[1] - (char *)v38[0] + 7) >> 3;
          if ( v38[0] > v38[1] )
            v26 = 0;
          if ( v26 )
            memset_0(v38[0], 0, 8 * v26);
          v27 = (unsigned __int64)((char *)v36[1] - (char *)v36[0] + 7) >> 3;
          if ( v36[0] > v36[1] )
            v27 = 0;
          if ( v27 )
            memset_0(v36[0], 0, 8 * v27);
          v28 = v43;
          v43 = 0;
          if ( v28 )
            CoTaskMemFree(v28);
          v29 = v33;
          v33 = 0;
          if ( v29 )
            CoTaskMemFree(v29);
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v36);
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v38);
          v7 = 0;
        }
      }
      else
      {
        v7 = -2134834660;
      }
      goto LABEL_60;
    }
  }
  v7 = -2134834658;
LABEL_11:
  v11 = (volatile signed __int32 *)v40[1];
  if ( v40[1] )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)v40[1] + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( !_InterlockedDecrement(v11 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
LABEL_60:
  std::vector<std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation>>::~vector<std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation>>(&v34);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004ab38  mov     [rsp-8+arg_0], rbx
0x18004ab3d  mov     [rsp-8+arg_10], r8
0x18004ab42  push    rbp
0x18004ab43  push    rsi
0x18004ab44  push    rdi
0x18004ab45  push    r12
0x18004ab47  push    r13
0x18004ab49  push    r14
0x18004ab4b  push    r15
0x18004ab4d  lea     rbp, [rsp-27h]
0x18004ab52  sub     rsp, 90h
0x18004ab59  mov     r12, r9
0x18004ab5c  mov     rsi, rdx
0x18004ab5f  mov     rdi, rcx
0x18004ab62  xor     r13d, r13d
0x18004ab65  xorps   xmm0, xmm0
0x18004ab68  movdqu  [rbp+57h+var_98], xmm0
0x18004ab6d  mov     [rbp+57h+var_88], r13
0x18004ab71  test    r9, r9
0x18004ab74  jnz     short loc_18004AB80
0x18004ab76  mov     ebx, 80004003h
0x18004ab7b  jmp     loc_18004AFCF
0x18004ab80  mov     [r9], r13
0x18004ab83  or      r15, 0FFFFFFFFFFFFFFFFh
0x18004ab87  test    r8, r8
0x18004ab8a  jz      short loc_18004ABBB
0x18004ab8c  lea     eax, [r15+2Bh]
0x18004ab90  cmp     ax, [r8]
0x18004ab94  jnz     short loc_18004ABBB
0x18004ab96  cmp     r13w, [r8+2]
0x18004ab9b  jnz     short loc_18004ABBB
0x18004ab9d  call    ?VerifyAllStorageKeysStillExist@DeviceCastleInternal@Library@DeviceCastle@@AEAAJAEAVCallerIdentity@23@@Z; DeviceCastle::Library::DeviceCastleInternal::VerifyAllStorageKeysStillExist(DeviceCastle::Library::CallerIdentity &)
0x18004aba2  mov     ebx, eax
0x18004aba4  test    eax, eax
0x18004aba6  js      loc_18004AFCF
0x18004abac  mov     r14, r13
0x18004abaf  add     rdi, 0B0h
0x18004abb6  jmp     loc_18004AC9F
0x18004abbb  lea     rcx, [rbp+57h+arg_10]
0x18004abbf  call    DeviceCastle__Library__ValidOrDefaultName
0x18004abc4  test    al, al
0x18004abc6  jz      loc_18004AFCA
0x18004abcc  xorps   xmm0, xmm0
0x18004abcf  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x18004abd4  add     rdi, 0B0h
0x18004abdb  lea     r9, [rbp+57h+var_50]
0x18004abdf  mov     r14, [rbp+57h+arg_10]
0x18004abe3  mov     r8, r14
0x18004abe6  mov     rdx, rsi
0x18004abe9  mov     rcx, rdi
0x18004abec  call    ?GetProtectionKey@DeviceCastleDatabase@Internal@Library@DeviceCastle@@QEAA_NAEAVCallerIdentity@34@PEBGAEAV?$shared_ptr@VCryptogramMaterialProtectionKeyInformation@Internal@Library@DeviceCastle@@@std@@@Z; DeviceCastle::Library::Internal::DeviceCastleDatabase::GetProtectionKey(DeviceCastle::Library::CallerIdentity &,ushort const *,std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation> &)
0x18004abf1  test    al, al
0x18004abf3  jnz     short loc_18004AC4B
0x18004abf5  mov     ebx, 80C1021Eh
0x18004abfa  mov     rdi, [rbp+57h+var_50+8]
0x18004abfe  test    rdi, rdi
0x18004ac01  jz      loc_18004AFCF
0x18004ac07  mov     eax, r15d
0x18004ac0a  lock xadd [rdi+8], eax
0x18004ac0f  add     eax, r15d
0x18004ac12  jnz     loc_18004AFCF
0x18004ac18  mov     rax, [rdi]
0x18004ac1b  mov     rcx, rdi
0x18004ac1e  mov     rax, [rax]
0x18004ac21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac26  mov     eax, r15d
0x18004ac29  lock xadd [rdi+0Ch], eax
0x18004ac2e  add     eax, r15d
0x18004ac31  jnz     loc_18004AFCF
0x18004ac37  mov     rax, [rdi]
0x18004ac3a  mov     rcx, rdi
0x18004ac3d  mov     rax, [rax+8]
0x18004ac41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac46  jmp     loc_18004AFCF
0x18004ac4b  lea     r8, [rbp+57h+var_50]
0x18004ac4f  mov     rdx, rsi
0x18004ac52  call    ?VerifyStorageKeyStillExists@DeviceCastleInternal@Library@DeviceCastle@@AEAAJAEAVCallerIdentity@23@AEBV?$shared_ptr@VCryptogramMaterialProtectionKeyInformation@Internal@Library@DeviceCastle@@@std@@@Z; DeviceCastle::Library::DeviceCastleInternal::VerifyStorageKeyStillExists(DeviceCastle::Library::CallerIdentity &,std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation> const &)
0x18004ac57  mov     ebx, eax
0x18004ac59  test    eax, eax
0x18004ac5b  js      short loc_18004ABFA
0x18004ac5d  jnz     short loc_18004ABF5
0x18004ac5f  mov     rbx, [rbp+57h+var_50+8]
0x18004ac63  test    rbx, rbx
0x18004ac66  jz      short loc_18004AC9F
0x18004ac68  mov     eax, r15d
0x18004ac6b  lock xadd [rbx+8], eax
0x18004ac70  add     eax, r15d
0x18004ac73  jnz     short loc_18004AC9F
0x18004ac75  mov     rax, [rbx]
0x18004ac78  mov     rcx, rbx
0x18004ac7b  mov     rax, [rax]
0x18004ac7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac83  mov     eax, r15d
0x18004ac86  lock xadd [rbx+0Ch], eax
0x18004ac8b  add     eax, r15d
0x18004ac8e  jnz     short loc_18004AC9F
0x18004ac90  mov     rax, [rbx]
0x18004ac93  mov     rcx, rbx
0x18004ac96  mov     rax, [rax+8]
0x18004ac9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac9f  lea     r9, [rbp+57h+var_98]
0x18004aca3  mov     r8, r14
0x18004aca6  mov     rdx, rsi
0x18004aca9  mov     rcx, rdi
0x18004acac  call    ?EnumeratePackages@DeviceCastleDatabase@Internal@Library@DeviceCastle@@QEAA_NAEAVCallerIdentity@34@PEBGAEAV?$vector@V?$shared_ptr@VCryptogramMaterialPackageInformation@Internal@Library@DeviceCastle@@@std@@V?$allocator@V?$shared_ptr@VCryptogramMaterialPackageInformation@Internal@Library@DeviceCastle@@@std@@@2@@std@@@Z; DeviceCastle::Library::Internal::DeviceCastleDatabase::EnumeratePackages(DeviceCastle::Library::CallerIdentity &,ushort const *,std::vector<std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialPackageInformation>> &)
0x18004acb1  test    al, al
0x18004acb3  jz      loc_18004AFC3
0x18004acb9  xorps   xmm0, xmm0
0x18004acbc  movdqu  xmmword ptr [rbp+57h+var_68], xmm0
0x18004acc1  mov     [rbp+57h+var_58], r13
0x18004acc5  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x18004acca  mov     [rbp+57h+var_70], r13
0x18004acce  lea     rcx, [rbp+57h+var_A0]
0x18004acd2  call    ??$make_unique_cotaskmem@U_GetAllCryptogramMaterialPackageCharacteristicsResult@@$$V@wil@@YA?AV?$unique_ptr@U_GetAllCryptogramMaterialPackageCharacteristicsResult@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ; wil::make_unique_cotaskmem<_GetAllCryptogramMaterialPackageCharacteristicsResult,>(void)
0x18004acd7  nop
0x18004acd8  mov     rdx, qword ptr [rbp+57h+var_98+8]
0x18004acdc  sub     rdx, qword ptr [rbp+57h+var_98]
0x18004ace0  sar     rdx, 4
0x18004ace4  lea     rcx, [rbp+57h+arg_18]
0x18004ace8  call    ??$make_unique_cotaskmem@$$BY0A@U_CryptogramMaterialPackageCharacteristics@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_CryptogramMaterialPackageCharacteristics@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<_CryptogramMaterialPackageCharacteristics [0]>(unsigned __int64)
0x18004aced  nop
0x18004acee  mov     r8, qword ptr [rbp+57h+var_98+8]
0x18004acf2  sub     r8, qword ptr [rbp+57h+var_98]
0x18004acf6  sar     r8, 4
0x18004acfa  shl     r8, 5; Size
0x18004acfe  xor     edx, edx; Val
0x18004ad00  mov     rcx, [rbp+57h+arg_18]; void *
0x18004ad04  call    memset_0
0x18004ad09  xorps   xmm0, xmm0
0x18004ad0c  mov     rax, [rbp+57h+var_A0]
0x18004ad10  movups  xmmword ptr [rax], xmm0
0x18004ad13  mov     rax, [rbp+57h+var_A0]
0x18004ad17  mov     rcx, qword ptr [rbp+57h+var_98+8]
0x18004ad1b  sub     rcx, qword ptr [rbp+57h+var_98]
0x18004ad1f  sar     rcx, 4
0x18004ad23  mov     edx, 0FFFFFFFFh
0x18004ad28  cmp     rcx, rdx
0x18004ad2b  ja      loc_18004AF7F
0x18004ad31  mov     [rax], ecx
0x18004ad33  mov     rdx, qword ptr [rbp+57h+var_98+8]
0x18004ad37  sub     rdx, qword ptr [rbp+57h+var_98]
0x18004ad3b  sar     rdx, 4
0x18004ad3f  lea     rcx, [rbp+57h+var_68]
0x18004ad43  call    ?reserve@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAX_K@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::reserve(unsigned __int64)
0x18004ad48  mov     rdx, qword ptr [rbp+57h+var_98+8]
0x18004ad4c  sub     rdx, qword ptr [rbp+57h+var_98]
0x18004ad50  sar     rdx, 4
0x18004ad54  lea     rcx, [rbp+57h+var_80]
0x18004ad58  call    ?reserve@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAX_K@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::reserve(unsigned __int64)
0x18004ad5d  mov     rdi, r13
0x18004ad60  mov     rax, qword ptr [rbp+57h+var_98+8]
0x18004ad64  mov     rcx, qword ptr [rbp+57h+var_98]
0x18004ad68  sub     rax, rcx
0x18004ad6b  sar     rax, 4
0x18004ad6f  test    rax, rax
0x18004ad72  jz      loc_18004AECC
0x18004ad78  mov     r15, rdi
0x18004ad7b  add     r15, r15
0x18004ad7e  mov     rdx, rsi
0x18004ad81  mov     rcx, [rcx+r15*8]
0x18004ad85  call    DeviceCastle__Library__UserSafeName
0x18004ad8a  test    rax, rax
0x18004ad8d  jz      short loc_18004ADFB
0x18004ad8f  mov     r14, [rbp+57h+var_68+8]
0x18004ad93  sub     r14, [rbp+57h+var_68]
0x18004ad97  sar     r14, 3
0x18004ad9b  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x18004ad9f  mov     rdx, rax; unsigned __int16 *
0x18004ada2  lea     rcx, [rbp+57h+pv]; this
0x18004ada6  call    ?make_cotaskmem_string@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string(ushort const *,unsigned __int64)
0x18004adab  nop
0x18004adac  mov     rdx, [rbp+57h+var_68+8]
0x18004adb0  cmp     rdx, [rbp+57h+var_58]
0x18004adb4  jz      short loc_18004ADC6
0x18004adb6  mov     rcx, [rax]
0x18004adb9  mov     [rdx], rcx
0x18004adbc  mov     [rax], r13
0x18004adbf  add     [rbp+57h+var_68+8], 8
0x18004adc4  jmp     short loc_18004ADD3
0x18004adc6  mov     r8, rax
0x18004adc9  lea     rcx, [rbp+57h+var_68]
0x18004adcd  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18004add2  nop
0x18004add3  mov     rcx, [rbp+57h+pv]; pv
0x18004add7  test    rcx, rcx
0x18004adda  jz      short loc_18004ADE2
0x18004addc  call    cs:__imp_CoTaskMemFree
0x18004ade2  mov     rbx, rdi
0x18004ade5  shl     rbx, 5
0x18004ade9  mov     rax, [rbp+57h+var_68]
0x18004aded  mov     rcx, [rax+r14*8]
0x18004adf1  mov     rax, [rbp+57h+arg_18]
0x18004adf5  mov     [rbx+rax], rcx
0x18004adf9  jmp     short loc_18004AE02
0x18004adfb  mov     rbx, rdi
0x18004adfe  shl     rbx, 5
0x18004ae02  mov     rax, qword ptr [rbp+57h+var_98]
0x18004ae06  mov     rcx, [rax+r15*8]
0x18004ae0a  mov     rcx, [rcx+20h]
0x18004ae0e  add     rcx, 10h
0x18004ae12  mov     rdx, rsi
0x18004ae15  call    DeviceCastle__Library__UserSafeName
0x18004ae1a  test    rax, rax
0x18004ae1d  jz      short loc_18004AE83
0x18004ae1f  mov     r14, [rbp+57h+var_80+8]
0x18004ae23  sub     r14, [rbp+57h+var_80]
0x18004ae27  sar     r14, 3
0x18004ae2b  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x18004ae2f  mov     rdx, rax; unsigned __int16 *
0x18004ae32  lea     rcx, [rbp+57h+var_50]; this
0x18004ae36  call    ?make_cotaskmem_string@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string(ushort const *,unsigned __int64)
0x18004ae3b  nop
0x18004ae3c  mov     rdx, [rbp+57h+var_80+8]
0x18004ae40  cmp     rdx, [rbp+57h+var_70]
0x18004ae44  jz      short loc_18004AE56
0x18004ae46  mov     rcx, [rax]
0x18004ae49  mov     [rdx], rcx
0x18004ae4c  mov     [rax], r13
0x18004ae4f  add     [rbp+57h+var_80+8], 8
0x18004ae54  jmp     short loc_18004AE63
0x18004ae56  mov     r8, rax
0x18004ae59  lea     rcx, [rbp+57h+var_80]
0x18004ae5d  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18004ae62  nop
0x18004ae63  mov     rcx, [rbp+57h+var_50]; pv
0x18004ae67  test    rcx, rcx
0x18004ae6a  jz      short loc_18004AE72
0x18004ae6c  call    cs:__imp_CoTaskMemFree
0x18004ae72  mov     rax, [rbp+57h+var_80]
0x18004ae76  mov     rcx, [rax+r14*8]
0x18004ae7a  mov     rax, [rbp+57h+arg_18]
0x18004ae7e  mov     [rbx+rax+8], rcx
0x18004ae83  mov     r8, rdi
0x18004ae86  add     r8, r8
0x18004ae89  mov     rax, qword ptr [rbp+57h+var_98]
0x18004ae8d  mov     rcx, [rax+r8*8]
0x18004ae91  mov     rdx, [rcx+58h]
0x18004ae95  mov     rax, [rbp+57h+arg_18]
0x18004ae99  mov     [rbx+rax+10h], rdx
0x18004ae9e  mov     rax, qword ptr [rbp+57h+var_98]
0x18004aea2  mov     rcx, [rax+r8*8]
0x18004aea6  mov     edx, [rcx+30h]
0x18004aea9  mov     rax, [rbp+57h+arg_18]
0x18004aead  mov     [rbx+rax+18h], edx
0x18004aeb1  inc     rdi
0x18004aeb4  mov     rax, qword ptr [rbp+57h+var_98+8]
0x18004aeb8  mov     rcx, qword ptr [rbp+57h+var_98]
0x18004aebc  sub     rax, rcx
0x18004aebf  sar     rax, 4
0x18004aec3  cmp     rdi, rax
0x18004aec6  jb      loc_18004AD78
0x18004aecc  mov     rcx, [rbp+57h+arg_18]
0x18004aed0  mov     [rbp+57h+arg_18], r13
0x18004aed4  mov     rax, [rbp+57h+var_A0]
0x18004aed8  mov     [rax+8], rcx
0x18004aedc  mov     rax, [rbp+57h+var_A0]
0x18004aee0  mov     [rbp+57h+var_A0], r13
0x18004aee4  mov     [r12], rax
0x18004aee8  mov     rcx, [rbp+57h+var_68]; void *
0x18004aeec  mov     r8, [rbp+57h+var_68+8]
0x18004aef0  sub     r8, rcx
0x18004aef3  add     r8, 7
0x18004aef7  shr     r8, 3
0x18004aefb  cmp     rcx, [rbp+57h+var_68+8]
0x18004aeff  cmova   r8, r13
0x18004af03  test    r8, r8
0x18004af06  jz      short loc_18004AF13
0x18004af08  shl     r8, 3; Size
0x18004af0c  xor     edx, edx; Val
0x18004af0e  call    memset_0
0x18004af13  mov     rcx, [rbp+57h+var_80]; void *
0x18004af17  mov     r8, [rbp+57h+var_80+8]
0x18004af1b  sub     r8, rcx
0x18004af1e  add     r8, 7
0x18004af22  shr     r8, 3
0x18004af26  cmp     rcx, [rbp+57h+var_80+8]
0x18004af2a  cmova   r8, r13
0x18004af2e  test    r8, r8
0x18004af31  jz      short loc_18004AF3F
0x18004af33  shl     r8, 3; Size
0x18004af37  xor     edx, edx; Val
0x18004af39  call    memset_0
0x18004af3e  nop
0x18004af3f  mov     rcx, [rbp+57h+arg_18]; pv
0x18004af43  mov     [rbp+57h+arg_18], r13
0x18004af47  test    rcx, rcx
0x18004af4a  jz      short loc_18004AF53
0x18004af4c  call    cs:__imp_CoTaskMemFree
0x18004af52  nop
0x18004af53  mov     rcx, [rbp+57h+var_A0]; pv
0x18004af57  mov     [rbp+57h+var_A0], r13
0x18004af5b  test    rcx, rcx
0x18004af5e  jz      short loc_18004AF67
0x18004af60  call    cs:__imp_CoTaskMemFree
0x18004af66  nop
0x18004af67  lea     rcx, [rbp+57h+var_80]
0x18004af6b  call    ??1?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18004af70  nop
0x18004af71  lea     rcx, [rbp+57h+var_68]
0x18004af75  call    ??1?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
  ... truncated ...
```
