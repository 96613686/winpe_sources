# DeviceCastle::Library::Internal::ProtectionKeyManager::OpenKey(std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation> const &,bool)

- ea: `0x18005c2d8`
- end: `0x18005c507`
- name: `?OpenKey@ProtectionKeyManager@Internal@Library@DeviceCastle@@QEAAJAEBV?$shared_ptr@VCryptogramMaterialProtectionKeyInformation@Internal@Library@DeviceCastle@@@std@@_N@Z`
- size: `559`
- prototype: `__int64 __fastcall(DeviceCastle::Library::Internal::ProtectionKeyManager *this)`
- caller_count: `8`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180042980`
- `0x18004b2a8`
- `0x18004bf38`
- `0x18004d5c0`
- `0x18004ee7c`
- `0x18005a958`
- `0x18005aa2c`
- `0x18005baf8`

## callees

- `0x180044700`
- `0x18004bf9c`
- `0x18005a958`
- `0x18005bcb8`
- `0x18005c2d8`
- `0x18005c60c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c37a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c43e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c37a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c43e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c467`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c333`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c38d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c451`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c47a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c333`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c38d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c451`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c47a`
- `ncrypt!NCryptFreeObject` at `0x18005c32b`
- `ncrypt!NCryptFreeObject` at `0x18005c385`
- `ncrypt!NCryptFreeObject` at `0x18005c449`
- `ncrypt!NCryptFreeObject` at `0x18005c472`
- `ncrypt!NCryptFreeObject` at `0x18005c32b`
- `ncrypt!NCryptFreeObject` at `0x18005c385`
- `ncrypt!NCryptFreeObject` at `0x18005c449`
- `ncrypt!NCryptFreeObject` at `0x18005c472`
- `ncrypt!NCryptOpenStorageProvider` at `0x18005c349`
- `ncrypt!NCryptOpenStorageProvider` at `0x18005c349`
- `ncrypt!NCryptSetProperty` at `0x18005c4f3`
- `ncrypt!NCryptSetProperty` at `0x18005c4f3`
- `ncrypt!NCryptOpenKey` at `0x18005c3a9`
- `ncrypt!NCryptOpenKey` at `0x18005c3a9`

## string_xrefs

- `0x18005c3eb`: `Device Castle failed to open expected Storage Key '%1!s!' named '%3!s!' in Provider '%2!s!'. The error code was %4!#08I32x!.`

## pseudocode

```c
__int64 __fastcall DeviceCastle::Library::Internal::ProtectionKeyManager::OpenKey(
        DeviceCastle::Library::Internal::ProtectionKeyManager *this,
        __int64 a2,
        char a3)
{
  char *v3; // r12
  DWORD v6; // r13d
  const WCHAR *v7; // rsi
  NCRYPT_PROV_HANDLE *v8; // r14
  NCRYPT_HANDLE v9; // rbp
  DWORD LastError; // ebx
  SECURITY_STATUS v11; // esi
  DWORD dwFlags; // r13d
  const WCHAR *v13; // rsi
  NCRYPT_HANDLE *v14; // r15
  NCRYPT_HANDLE v15; // rbp
  DWORD v16; // ebx
  SECURITY_STATUS v17; // ebx
  _QWORD *v18; // rax
  _QWORD *v19; // rcx
  _QWORD *v20; // rdx
  _QWORD *v21; // rax
  __int64 v22; // rdx
  int v23; // eax
  NCRYPT_HANDLE v24; // rbp
  DWORD v25; // ebx
  NCRYPT_HANDLE v26; // rdi
  DWORD v27; // ebx

  v3 = (char *)this + 56;
  std::shared_ptr<APDUChannelMgr::ChannelInfo>::operator=((char *)this + 56);
  v6 = *((_DWORD *)this + 12);
  v7 = (const WCHAR *)(*(_QWORD *)a2 + 48LL);
  if ( *(_QWORD *)(*(_QWORD *)a2 + 72LL) > 7u )
    v7 = *(const WCHAR **)v7;
  v8 = (NCRYPT_PROV_HANDLE *)((char *)this + 32);
  v9 = *((_QWORD *)this + 4);
  if ( v9 )
  {
    LastError = GetLastError();
    NCryptFreeObject(v9);
    SetLastError(LastError);
  }
  *v8 = 0;
  v11 = NCryptOpenStorageProvider((NCRYPT_PROV_HANDLE *)this + 4, v7, v6);
  if ( v11 >= 0 )
  {
    dwFlags = *((_DWORD *)this + 12);
    v13 = (const WCHAR *)(*(_QWORD *)a2 + 80LL);
    if ( *(_QWORD *)(*(_QWORD *)a2 + 104LL) > 7u )
      v13 = *(const WCHAR **)v13;
    v14 = (NCRYPT_HANDLE *)((char *)this + 40);
    v15 = *((_QWORD *)this + 5);
    if ( v15 )
    {
      v16 = GetLastError();
      NCryptFreeObject(v15);
      SetLastError(v16);
    }
    *v14 = 0;
    v17 = NCryptOpenKey(*v8, (NCRYPT_KEY_HANDLE *)this + 5, v13, 0, dwFlags);
    if ( v17 >= 0 )
    {
      if ( !*((_QWORD *)this + 2) )
        return 0;
      v11 = NCryptSetProperty(*v14, L"HWND Handle", (PBYTE)this + 16, 8u, *((_DWORD *)this + 12));
      if ( v11 >= 0 )
        return 0;
    }
    else
    {
      v18 = *(_QWORD **)v3;
      v19 = (_QWORD *)(*(_QWORD *)v3 + 80LL);
      if ( *(_QWORD *)(*(_QWORD *)v3 + 104LL) > 7u )
        v19 = (_QWORD *)*v19;
      v20 = v18 + 6;
      if ( v18[9] > 7u )
        v20 = (_QWORD *)*v20;
      v21 = v18 + 2;
      if ( v21[3] > 7u )
        v21 = (_QWORD *)*v21;
      DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(
        DeviceCastle::Library::Internal::g_pCastleInstance,
        2u,
        *((struct DeviceCastle::Library::CallerIdentity **)this + 1),
        L"Device Castle failed to open expected Storage Key '%1!s!' named '%3!s!' in Provider '%2!s!'. The error code was %4!#08I32x!.",
        v21,
        v20,
        v19,
        v17);
      v23 = DeviceCastle::Library::Internal::ProtectionKeyManager::TranslateKspStatus(
              this,
              v22,
              (unsigned int)v17,
              (unsigned int)v17);
      v11 = v23;
      if ( v23 == -2134834658 )
      {
        DeviceCastle::Library::Internal::ProtectionKeyManager::DeleteKey(this);
      }
      else if ( v23 == -2134834646 )
      {
        DeviceCastle::Library::Internal::ProtectionKeyManager::DeleteKey(this);
        if ( a3 )
          DeviceCastle::Library::Internal::ProtectionKeyManager::CheckKeysWithCapability(
            this,
            *(unsigned int *)(*(_QWORD *)v3 + 180LL));
      }
      else if ( v23 >= 0 )
      {
        return (unsigned int)v11;
      }
    }
  }
  v24 = *((_QWORD *)this + 5);
  if ( v24 )
  {
    v25 = GetLastError();
    NCryptFreeObject(v24);
    SetLastError(v25);
  }
  *((_QWORD *)this + 5) = 0;
  v26 = *v8;
  if ( *v8 )
  {
    v27 = GetLastError();
    NCryptFreeObject(v26);
    SetLastError(v27);
  }
  *v8 = 0;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18005c2d8  mov     [rsp+arg_10], r8b
0x18005c2dd  push    rbx
0x18005c2de  push    rbp
0x18005c2df  push    rsi
0x18005c2e0  push    rdi
0x18005c2e1  push    r12
0x18005c2e3  push    r13
0x18005c2e5  push    r14
0x18005c2e7  push    r15
0x18005c2e9  sub     rsp, 48h
0x18005c2ed  lea     r12, [rcx+38h]
0x18005c2f1  mov     rdi, rcx
0x18005c2f4  mov     rcx, r12
0x18005c2f7  mov     r15, rdx
0x18005c2fa  call    ??4?$shared_ptr@UChannelInfo@APDUChannelMgr@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<APDUChannelMgr::ChannelInfo>::operator=(std::shared_ptr<APDUChannelMgr::ChannelInfo> const &)
0x18005c2ff  mov     rsi, [r15]
0x18005c302  mov     r13d, [rdi+30h]
0x18005c306  add     rsi, 30h ; '0'
0x18005c30a  cmp     qword ptr [rsi+18h], 7
0x18005c30f  jbe     short loc_18005C314
0x18005c311  mov     rsi, [rsi]
0x18005c314  lea     r14, [rdi+20h]
0x18005c318  mov     rbp, [r14]
0x18005c31b  test    rbp, rbp
0x18005c31e  jz      short loc_18005C339
0x18005c320  call    cs:__imp_GetLastError
0x18005c326  mov     rcx, rbp; hObject
0x18005c329  mov     ebx, eax
0x18005c32b  call    cs:__imp_NCryptFreeObject
0x18005c331  mov     ecx, ebx; dwErrCode
0x18005c333  call    cs:__imp_SetLastError
0x18005c339  mov     r8d, r13d; dwFlags
0x18005c33c  mov     qword ptr [r14], 0
0x18005c343  mov     rdx, rsi; pszProviderName
0x18005c346  mov     rcx, r14; phProvider
0x18005c349  call    cs:__imp_NCryptOpenStorageProvider
0x18005c34f  mov     esi, eax
0x18005c351  test    eax, eax
0x18005c353  js      loc_18005C435
0x18005c359  mov     rsi, [r15]
0x18005c35c  mov     r13d, [rdi+30h]
0x18005c360  add     rsi, 50h ; 'P'
0x18005c364  cmp     qword ptr [rsi+18h], 7
0x18005c369  jbe     short loc_18005C36E
0x18005c36b  mov     rsi, [rsi]
0x18005c36e  lea     r15, [rdi+28h]
0x18005c372  mov     rbp, [r15]
0x18005c375  test    rbp, rbp
0x18005c378  jz      short loc_18005C393
0x18005c37a  call    cs:__imp_GetLastError
0x18005c380  mov     rcx, rbp; hObject
0x18005c383  mov     ebx, eax
0x18005c385  call    cs:__imp_NCryptFreeObject
0x18005c38b  mov     ecx, ebx; dwErrCode
0x18005c38d  call    cs:__imp_SetLastError
0x18005c393  xor     ebp, ebp
0x18005c395  mov     [rsp+88h+dwFlags], r13d; dwFlags
0x18005c39a  mov     [r15], rbp
0x18005c39d  xor     r9d, r9d; dwLegacyKeySpec
0x18005c3a0  mov     rcx, [r14]; hProvider
0x18005c3a3  mov     r8, rsi; pszKeyName
0x18005c3a6  mov     rdx, r15; phKey
0x18005c3a9  call    cs:__imp_NCryptOpenKey
0x18005c3af  mov     ebx, eax
0x18005c3b1  test    eax, eax
0x18005c3b3  jns     loc_18005C4D3
0x18005c3b9  mov     rax, [r12]
0x18005c3bd  lea     rcx, [rax+50h]
0x18005c3c1  cmp     qword ptr [rcx+18h], 7
0x18005c3c6  jbe     short loc_18005C3CB
0x18005c3c8  mov     rcx, [rcx]
0x18005c3cb  lea     rdx, [rax+30h]
0x18005c3cf  cmp     qword ptr [rdx+18h], 7
0x18005c3d4  jbe     short loc_18005C3D9
0x18005c3d6  mov     rdx, [rdx]
0x18005c3d9  add     rax, 10h
0x18005c3dd  cmp     qword ptr [rax+18h], 7
0x18005c3e2  jbe     short loc_18005C3E7
0x18005c3e4  mov     rax, [rax]
0x18005c3e7  mov     r8, [rdi+8]; struct DeviceCastle::Library::CallerIdentity *
0x18005c3eb  lea     r9, aDeviceCastleFa_4; "Device Castle failed to open expected S"...
0x18005c3f2  mov     [rsp+88h+var_50], ebx
0x18005c3f6  mov     [rsp+88h+var_58], rcx
0x18005c3fb  mov     rcx, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; this
0x18005c402  mov     [rsp+88h+var_60], rdx
0x18005c407  mov     edx, 2; unsigned int
0x18005c40c  mov     qword ptr [rsp+88h+dwFlags], rax
0x18005c411  call    ?LogFormattedMessage@DeviceCastleInternal@Library@DeviceCastle@@QEBAXKPEAVCallerIdentity@23@PEBGZZ; DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(ulong,DeviceCastle::Library::CallerIdentity *,ushort const *,...)
0x18005c416  mov     r9d, ebx
0x18005c419  mov     r8d, ebx
0x18005c41c  mov     rcx, rdi
0x18005c41f  call    ?TranslateKspStatus@ProtectionKeyManager@Internal@Library@DeviceCastle@@QEAAJW4CryptoAction@234@JJ@Z; DeviceCastle::Library::Internal::ProtectionKeyManager::TranslateKspStatus(DeviceCastle::Library::Internal::CryptoAction,long,long)
0x18005c424  mov     esi, eax
0x18005c426  cmp     eax, 80C1021Eh
0x18005c42b  jnz     short loc_18005C49A
0x18005c42d  mov     rcx, rdi; this
0x18005c430  call    ?DeleteKey@ProtectionKeyManager@Internal@Library@DeviceCastle@@QEAAJXZ; DeviceCastle::Library::Internal::ProtectionKeyManager::DeleteKey(void)
0x18005c435  mov     rbp, [rdi+28h]
0x18005c439  test    rbp, rbp
0x18005c43c  jz      short loc_18005C457
0x18005c43e  call    cs:__imp_GetLastError
0x18005c444  mov     rcx, rbp; hObject
0x18005c447  mov     ebx, eax
0x18005c449  call    cs:__imp_NCryptFreeObject
0x18005c44f  mov     ecx, ebx; dwErrCode
0x18005c451  call    cs:__imp_SetLastError
0x18005c457  mov     qword ptr [rdi+28h], 0
0x18005c45f  mov     rdi, [r14]
0x18005c462  test    rdi, rdi
0x18005c465  jz      short loc_18005C480
0x18005c467  call    cs:__imp_GetLastError
0x18005c46d  mov     rcx, rdi; hObject
0x18005c470  mov     ebx, eax
0x18005c472  call    cs:__imp_NCryptFreeObject
0x18005c478  mov     ecx, ebx; dwErrCode
0x18005c47a  call    cs:__imp_SetLastError
0x18005c480  mov     qword ptr [r14], 0
0x18005c487  mov     eax, esi
0x18005c489  add     rsp, 48h
0x18005c48d  pop     r15
0x18005c48f  pop     r14
0x18005c491  pop     r13
0x18005c493  pop     r12
0x18005c495  pop     rdi
0x18005c496  pop     rsi
0x18005c497  pop     rbp
0x18005c498  pop     rbx
0x18005c499  retn
0x18005c49a  cmp     eax, 80C1022Ah
0x18005c49f  jnz     short loc_18005C4CA
0x18005c4a1  mov     rcx, rdi; this
0x18005c4a4  call    ?DeleteKey@ProtectionKeyManager@Internal@Library@DeviceCastle@@QEAAJXZ; DeviceCastle::Library::Internal::ProtectionKeyManager::DeleteKey(void)
0x18005c4a9  cmp     [rsp+88h+arg_10], bpl
0x18005c4b1  jz      short loc_18005C435
0x18005c4b3  mov     rdx, [r12]
0x18005c4b7  mov     rcx, rdi
0x18005c4ba  mov     edx, [rdx+0B4h]
0x18005c4c0  call    ?CheckKeysWithCapability@ProtectionKeyManager@Internal@Library@DeviceCastle@@QEAAJW4CryptogramStorageKeyCapabilities@@@Z; DeviceCastle::Library::Internal::ProtectionKeyManager::CheckKeysWithCapability(CryptogramStorageKeyCapabilities)
0x18005c4c5  jmp     loc_18005C435
0x18005c4ca  test    eax, eax
0x18005c4cc  jns     short loc_18005C487
0x18005c4ce  jmp     loc_18005C435
0x18005c4d3  lea     r8, [rdi+10h]; pbInput
0x18005c4d7  cmp     [r8], rbp
0x18005c4da  jz      short loc_18005C503
0x18005c4dc  mov     eax, [rdi+30h]
0x18005c4df  lea     rdx, aHwndHandle; "HWND Handle"
0x18005c4e6  mov     rcx, [r15]; hObject
0x18005c4e9  mov     r9d, 8; cbInput
0x18005c4ef  mov     [rsp+88h+dwFlags], eax; dwFlags
0x18005c4f3  call    cs:__imp_NCryptSetProperty
0x18005c4f9  mov     esi, eax
0x18005c4fb  test    eax, eax
0x18005c4fd  js      loc_18005C435
0x18005c503  mov     esi, ebp
0x18005c505  jmp     short loc_18005C487
```
