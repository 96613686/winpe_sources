# DeviceCastle::Library::DeviceCastleInternal::GetCryptogramMaterialStorageKeyInfo(DeviceCastle::Library::CallerIdentity &,HWND__ *,UnlockPromptingBehavior,ushort const *,_CryptogramMaterialStorageKeyInfo * *)

- ea: `0x18004b2a8`
- end: `0x18004b63b`
- name: `?GetCryptogramMaterialStorageKeyInfo@DeviceCastleInternal@Library@DeviceCastle@@QEAAJAEAVCallerIdentity@23@PEAUHWND__@@W4UnlockPromptingBehavior@@PEBGPEAPEAU_CryptogramMaterialStorageKeyInfo@@@Z`
- size: `915`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x180042b90`

## callees

- `0x180005858`
- `0x180035bc0`
- `0x1800436c0`
- `0x1800457b0`
- `0x180049bc8`
- `0x18004b2a8`
- `0x18004d298`
- `0x18004da88`
- `0x18004db3c`
- `0x18005a4f8`
- `0x18005bf14`
- `0x18005c2d8`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b43a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b54e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b58f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b5af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b43a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b54e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b58f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b5af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b3dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b3dd`

## string_xrefs

- `0x18004b629`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DeviceCastle::Library::DeviceCastleInternal::GetCryptogramMaterialStorageKeyInfo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        LPVOID a6)
{
  _QWORD *v8; // r13
  int KeyInfo; // ebx
  __int64 v10; // rsi
  _DWORD *v11; // rax
  const char *v12; // r9
  _DWORD *v13; // rdi
  __int64 *cotaskmem_string; // r14
  volatile signed __int32 *v15; // rdi
  _QWORD v17[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v18; // [rsp+40h] [rbp-C0h]
  __int64 v19; // [rsp+48h] [rbp-B8h]
  _QWORD v20[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v21; // [rsp+60h] [rbp-A0h]
  __int64 v22; // [rsp+68h] [rbp-98h]
  _QWORD v23[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v24; // [rsp+80h] [rbp-80h]
  __int64 v25; // [rsp+88h] [rbp-78h]
  LPVOID v26; // [rsp+90h] [rbp-70h] BYREF
  __int64 v27; // [rsp+98h] [rbp-68h] BYREF
  __int128 v28; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD *v29; // [rsp+B0h] [rbp-50h]
  _QWORD v30[3]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v31[144]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]
  LPVOID pv; // [rsp+170h] [rbp+70h] BYREF

  LODWORD(pv) = 0;
  v28 = 0;
  v8 = a6;
  *(_QWORD *)a6 = 0;
  if ( !*(_BYTE *)(a1 + 140) )
  {
    if ( !(unsigned __int8)DeviceCastle::Library::ValidOrDefaultName(&a5) )
    {
      KeyInfo = -2134834649;
      goto LABEL_29;
    }
    if ( !(unsigned __int8)DeviceCastle::Library::Internal::DeviceCastleDatabase::GetProtectionKey(
                             a1 + 176,
                             a2,
                             a5,
                             &v28) )
    {
      KeyInfo = -2134834658;
      goto LABEL_29;
    }
    v23[0] = &DeviceCastle::Library::Blob::`vftable';
    v23[1] = 0;
    v24 = 0;
    v25 = 0;
    v20[0] = &DeviceCastle::Library::Blob::`vftable';
    v20[1] = 0;
    v21 = 0;
    v22 = 0;
    v17[0] = &DeviceCastle::Library::Blob::`vftable';
    v17[1] = 0;
    v18 = 0;
    v19 = 0;
    DeviceCastle::Library::Internal::ProtectionKeyManager::ProtectionKeyManager(v31);
    v29 = 0;
    a6 = 0;
    v26 = 0;
    v27 = 0;
    v10 = 0;
    v30[0] = 0;
    v11 = CoTaskMemAlloc(0x40u);
    v13 = v11;
    v30[1] = v11;
    if ( v11 )
      memset_0(v11, 0, 0x40u);
    LODWORD(pv) = 1;
    if ( !v13 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x1841,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v12);
    v29 = v13;
    memset_0(v13, 0, 0x40u);
    KeyInfo = DeviceCastle::Library::Internal::ProtectionKeyManager::OpenKey((DeviceCastle::Library::Internal::ProtectionKeyManager *)v31);
    if ( KeyInfo >= 0 )
    {
      KeyInfo = DeviceCastle::Library::Internal::ProtectionKeyManager::GetKeyInfo(
                  (DeviceCastle::Library::Internal::ProtectionKeyManager *)v31,
                  (struct DeviceCastle::Library::Blob *)v23,
                  (struct DeviceCastle::Library::Blob *)v20,
                  (struct DeviceCastle::Library::Blob *)v17,
                  (enum CryptographicKeyAttestationStatus *)(v13 + 4));
      if ( KeyInfo >= 0 )
      {
        v13[12] = *(_DWORD *)(v28 + 180);
        if ( v24 > 0xFFFFFFFF )
        {
          *v13 = -1;
          KeyInfo = -2147024362;
        }
        else
        {
          *v13 = v24;
          DeviceCastle::Library::Internal::unique_cotaskmem_blob::load(
            (DeviceCastle::Library::Internal::unique_cotaskmem_blob *)&a6,
            (const struct DeviceCastle::Library::Blob *)v23);
          if ( v21 > 0xFFFFFFFF )
          {
            v13[5] = -1;
            KeyInfo = -2147024362;
          }
          else
          {
            v13[5] = v21;
            DeviceCastle::Library::Internal::unique_cotaskmem_blob::load(
              (DeviceCastle::Library::Internal::unique_cotaskmem_blob *)&v26,
              (const struct DeviceCastle::Library::Blob *)v20);
            if ( v18 <= 0xFFFFFFFF )
            {
              v13[8] = v18;
              DeviceCastle::Library::Internal::unique_cotaskmem_blob::load(
                (DeviceCastle::Library::Internal::unique_cotaskmem_blob *)&v27,
                (const struct DeviceCastle::Library::Blob *)v17);
              cotaskmem_string = (__int64 *)wil::make_cotaskmem_string(
                                              (wil *)&pv,
                                              L"{\"SupportedMaterialTypes\":{\"StaticDataAuthentication\":{},\"TripleDes11"
                                               "2\":{\"Protections\":[{\"Method\":\"Whiteboxing\",\"Version\":\"2\"}]},\""
                                               "Aes\":{\"Sizes\":[\"128\",\"256\"]},\"RsaPkcs1\":{\"Sizes\":[\"896\",\"10"
                                               "24\",\"1152\",\"1408\"]}}}",
                                              0xD2u);
              if ( v30 != cotaskmem_string )
              {
                v10 = *cotaskmem_string;
                *cotaskmem_string = 0;
              }
              if ( pv )
                CoTaskMemFree(pv);
              *((_QWORD *)v13 + 1) = a6;
              *((_QWORD *)v13 + 3) = v26;
              *((_QWORD *)v13 + 5) = v27;
              *((_QWORD *)v13 + 7) = v10;
              *v8 = v13;
              KeyInfo = 0;
              goto LABEL_11;
            }
            v13[8] = -1;
            KeyInfo = -2147024362;
            if ( v26 )
              CoTaskMemFree(v26);
          }
          if ( a6 )
            CoTaskMemFree(a6);
        }
      }
    }
    CoTaskMemFree(v13);
LABEL_11:
    DeviceCastle::Library::Internal::ProtectionKeyManager::~ProtectionKeyManager((DeviceCastle::Library::Internal::ProtectionKeyManager *)v31);
    v17[0] = &DeviceCastle::Library::Blob::`vftable';
    DeviceCastle::Library::Blob::Clear((DeviceCastle::Library::Blob *)v17);
    v20[0] = &DeviceCastle::Library::Blob::`vftable';
    DeviceCastle::Library::Blob::Clear((DeviceCastle::Library::Blob *)v20);
    v23[0] = &DeviceCastle::Library::Blob::`vftable';
    DeviceCastle::Library::Blob::Clear((DeviceCastle::Library::Blob *)v23);
    goto LABEL_29;
  }
  KeyInfo = -2134834642;
LABEL_29:
  v15 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
  if ( *((_QWORD *)&v28 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  return (unsigned int)KeyInfo;
}

```

## disassembly

```asm
0x18004b2a8  push    rbp
0x18004b2aa  push    rbx
0x18004b2ab  push    rsi
0x18004b2ac  push    rdi
0x18004b2ad  push    r12
0x18004b2af  push    r13
0x18004b2b1  push    r14
0x18004b2b3  push    r15
0x18004b2b5  lea     rbp, [rsp-28h]
0x18004b2ba  sub     rsp, 128h
0x18004b2c1  mov     esi, r9d
0x18004b2c4  mov     r14, r8
0x18004b2c7  mov     rbx, rdx
0x18004b2ca  mov     rdi, rcx
0x18004b2cd  mov     dword ptr [rbp+60h+pv], 0
0x18004b2d4  xorps   xmm0, xmm0
0x18004b2d7  movdqu  [rbp+60h+var_C0], xmm0
0x18004b2dc  mov     r13, [rbp+60h+arg_28]
0x18004b2e3  mov     qword ptr [r13+0], 0
0x18004b2eb  cmp     byte ptr [rcx+8Ch], 0
0x18004b2f2  jz      short loc_18004B2FE
0x18004b2f4  mov     ebx, 80C1022Eh
0x18004b2f9  jmp     loc_18004B5D4
0x18004b2fe  lea     rcx, [rbp+60h+arg_20]
0x18004b305  call    DeviceCastle__Library__ValidOrDefaultName
0x18004b30a  test    al, al
0x18004b30c  jnz     short loc_18004B318
0x18004b30e  mov     ebx, 80C10227h
0x18004b313  jmp     loc_18004B5D4
0x18004b318  lea     rcx, [rdi+0B0h]
0x18004b31f  lea     r9, [rbp+60h+var_C0]
0x18004b323  mov     r8, [rbp+60h+arg_20]
0x18004b32a  mov     rdx, rbx
0x18004b32d  call    ?GetProtectionKey@DeviceCastleDatabase@Internal@Library@DeviceCastle@@QEAA_NAEAVCallerIdentity@34@PEBGAEAV?$shared_ptr@VCryptogramMaterialProtectionKeyInformation@Internal@Library@DeviceCastle@@@std@@@Z; DeviceCastle::Library::Internal::DeviceCastleDatabase::GetProtectionKey(DeviceCastle::Library::CallerIdentity &,ushort const *,std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation> &)
0x18004b332  test    al, al
0x18004b334  jz      loc_18004B5CF
0x18004b33a  lea     rax, ??_7Blob@Library@DeviceCastle@@6B@; const DeviceCastle::Library::Blob::`vftable'
0x18004b341  mov     [rsp+160h+var_F0], rax
0x18004b346  mov     [rsp+160h+var_E8], 0
0x18004b34f  mov     [rbp+60h+var_E0], 0
0x18004b357  mov     [rbp+60h+var_D8], 0
0x18004b35f  mov     [rsp+160h+var_110], rax
0x18004b364  mov     [rsp+160h+var_108], 0
0x18004b36d  mov     [rsp+160h+var_100], 0
0x18004b376  mov     [rsp+160h+var_F8], 0
0x18004b37f  mov     [rsp+160h+var_130], rax
0x18004b384  mov     [rsp+160h+var_128], 0
0x18004b38d  mov     [rsp+160h+var_120], 0
0x18004b396  mov     [rsp+160h+var_118], 0
0x18004b39f  mov     r9d, esi
0x18004b3a2  mov     r8, r14
0x18004b3a5  mov     rdx, rbx
0x18004b3a8  lea     rcx, [rbp+60h+var_90]
0x18004b3ac  call    ??0ProtectionKeyManager@Internal@Library@DeviceCastle@@QEAA@AEAVCallerIdentity@23@PEAUHWND__@@W4UnlockPromptingBehavior@@@Z; DeviceCastle::Library::Internal::ProtectionKeyManager::ProtectionKeyManager(DeviceCastle::Library::CallerIdentity &,HWND__ *,UnlockPromptingBehavior)
0x18004b3b1  nop
0x18004b3b2  mov     [rbp+60h+var_B0], 0
0x18004b3ba  xor     r12d, r12d
0x18004b3bd  mov     [rbp+60h+arg_28], r12
0x18004b3c4  xor     r15d, r15d
0x18004b3c7  mov     [rbp+60h+var_D0], r15
0x18004b3cb  xor     r14d, r14d
0x18004b3ce  mov     [rbp+60h+var_C8], r14
0x18004b3d2  xor     esi, esi
0x18004b3d4  mov     [rbp+60h+var_A8], rsi
0x18004b3d8  lea     ebx, [rsi+40h]
0x18004b3db  mov     ecx, ebx; cb
0x18004b3dd  call    cs:__imp_CoTaskMemAlloc
0x18004b3e3  mov     rdi, rax
0x18004b3e6  mov     [rbp+60h+var_A0], rax
0x18004b3ea  test    rax, rax
0x18004b3ed  jz      short loc_18004B3FC
0x18004b3ef  mov     r8d, ebx; Size
0x18004b3f2  xor     edx, edx; Val
0x18004b3f4  mov     rcx, rax; void *
0x18004b3f7  call    memset_0
0x18004b3fc  mov     dword ptr [rbp+60h+pv], 1
0x18004b403  mov     rcx, [rbp+68h]; this
0x18004b407  test    rdi, rdi
0x18004b40a  jz      loc_18004B629
0x18004b410  mov     [rbp+60h+var_B0], rdi
0x18004b414  mov     r8, rbx; Size
0x18004b417  xor     edx, edx; Val
0x18004b419  mov     rcx, rdi; void *
0x18004b41c  call    memset_0
0x18004b421  mov     r8b, 1
0x18004b424  lea     rdx, [rbp+60h+var_C0]
0x18004b428  lea     rcx, [rbp+60h+var_90]; this
0x18004b42c  call    ?OpenKey@ProtectionKeyManager@Internal@Library@DeviceCastle@@QEAAJAEBV?$shared_ptr@VCryptogramMaterialProtectionKeyInformation@Internal@Library@DeviceCastle@@@std@@_N@Z; DeviceCastle::Library::Internal::ProtectionKeyManager::OpenKey(std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation> const &,bool)
0x18004b431  mov     ebx, eax
0x18004b433  test    eax, eax
0x18004b435  jns     short loc_18004B486
0x18004b437  mov     rcx, rdi; pv
0x18004b43a  call    cs:__imp_CoTaskMemFree
0x18004b440  nop
0x18004b441  lea     rcx, [rbp+60h+var_90]; this
0x18004b445  call    ??1ProtectionKeyManager@Internal@Library@DeviceCastle@@UEAA@XZ; DeviceCastle::Library::Internal::ProtectionKeyManager::~ProtectionKeyManager(void)
0x18004b44a  nop
0x18004b44b  lea     rdi, ??_7Blob@Library@DeviceCastle@@6B@; const DeviceCastle::Library::Blob::`vftable'
0x18004b452  mov     [rsp+160h+var_130], rdi
0x18004b457  lea     rcx, [rsp+160h+var_130]; this
0x18004b45c  call    ?Clear@Blob@Library@DeviceCastle@@UEAAXXZ; DeviceCastle::Library::Blob::Clear(void)
0x18004b461  nop
0x18004b462  mov     [rsp+160h+var_110], rdi
0x18004b467  lea     rcx, [rsp+160h+var_110]; this
0x18004b46c  call    ?Clear@Blob@Library@DeviceCastle@@UEAAXXZ; DeviceCastle::Library::Blob::Clear(void)
0x18004b471  nop
0x18004b472  mov     [rsp+160h+var_F0], rdi
0x18004b477  lea     rcx, [rsp+160h+var_F0]; this
0x18004b47c  call    ?Clear@Blob@Library@DeviceCastle@@UEAAXXZ; DeviceCastle::Library::Blob::Clear(void)
0x18004b481  jmp     loc_18004B5D4
0x18004b486  lea     rax, [rdi+10h]
0x18004b48a  mov     [rsp+160h+var_140], rax; enum CryptographicKeyAttestationStatus *
0x18004b48f  lea     r9, [rsp+160h+var_130]; struct DeviceCastle::Library::Blob *
0x18004b494  lea     r8, [rsp+160h+var_110]; struct DeviceCastle::Library::Blob *
0x18004b499  lea     rdx, [rsp+160h+var_F0]; struct DeviceCastle::Library::Blob *
0x18004b49e  lea     rcx, [rbp+60h+var_90]; this
0x18004b4a2  call    ?GetKeyInfo@ProtectionKeyManager@Internal@Library@DeviceCastle@@QEAAJAEAVBlob@34@00PEAW4CryptographicKeyAttestationStatus@@@Z; DeviceCastle::Library::Internal::ProtectionKeyManager::GetKeyInfo(DeviceCastle::Library::Blob &,DeviceCastle::Library::Blob &,DeviceCastle::Library::Blob &,CryptographicKeyAttestationStatus *)
0x18004b4a7  mov     ebx, eax
0x18004b4a9  test    eax, eax
0x18004b4ab  js      short loc_18004B437
0x18004b4ad  mov     rax, qword ptr [rbp+60h+var_C0]
0x18004b4b1  mov     ecx, [rax+0B4h]
0x18004b4b7  mov     [rdi+30h], ecx
0x18004b4ba  mov     rax, [rbp+60h+var_E0]
0x18004b4be  mov     ebx, 0FFFFFFFFh
0x18004b4c3  cmp     rax, rbx
0x18004b4c6  ja      loc_18004B5BA
0x18004b4cc  mov     [rdi], eax
0x18004b4ce  lea     rdx, [rsp+160h+var_F0]; struct DeviceCastle::Library::Blob *
0x18004b4d3  lea     rcx, [rbp+60h+arg_28]; this
0x18004b4da  call    ?load@unique_cotaskmem_blob@Internal@Library@DeviceCastle@@QEAAXAEBVBlob@34@@Z; DeviceCastle::Library::Internal::unique_cotaskmem_blob::load(DeviceCastle::Library::Blob const &)
0x18004b4df  mov     rax, [rsp+160h+var_100]
0x18004b4e4  cmp     rax, rbx
0x18004b4e7  ja      loc_18004B597
0x18004b4ed  mov     [rdi+14h], eax
0x18004b4f0  lea     rdx, [rsp+160h+var_110]; struct DeviceCastle::Library::Blob *
0x18004b4f5  lea     rcx, [rbp+60h+var_D0]; this
0x18004b4f9  call    ?load@unique_cotaskmem_blob@Internal@Library@DeviceCastle@@QEAAXAEBVBlob@34@@Z; DeviceCastle::Library::Internal::unique_cotaskmem_blob::load(DeviceCastle::Library::Blob const &)
0x18004b4fe  mov     rax, [rsp+160h+var_120]
0x18004b503  cmp     rax, rbx
0x18004b506  ja      short loc_18004B57E
0x18004b508  mov     [rdi+20h], eax
0x18004b50b  lea     rdx, [rsp+160h+var_130]; struct DeviceCastle::Library::Blob *
0x18004b510  lea     rcx, [rbp+60h+var_C8]; this
0x18004b514  call    ?load@unique_cotaskmem_blob@Internal@Library@DeviceCastle@@QEAAXAEBVBlob@34@@Z; DeviceCastle::Library::Internal::unique_cotaskmem_blob::load(DeviceCastle::Library::Blob const &)
0x18004b519  mov     r8d, 0D2h; unsigned __int64
0x18004b51f  lea     rdx, aSupportedmater; "{\"SupportedMaterialTypes\":{\"StaticDa"...
0x18004b526  lea     rcx, [rbp+60h+pv]; this
0x18004b52a  call    ?make_cotaskmem_string@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string(ushort const *,unsigned __int64)
0x18004b52f  mov     r14, rax
0x18004b532  lea     rax, [rbp+60h+var_A8]
0x18004b536  cmp     rax, r14
0x18004b539  jz      short loc_18004B545
0x18004b53b  mov     rsi, [r14]
0x18004b53e  mov     qword ptr [r14], 0
0x18004b545  mov     rcx, [rbp+60h+pv]; pv
0x18004b549  test    rcx, rcx
0x18004b54c  jz      short loc_18004B554
0x18004b54e  call    cs:__imp_CoTaskMemFree
0x18004b554  mov     rax, [rbp+60h+arg_28]
0x18004b55b  mov     [rdi+8], rax
0x18004b55f  mov     rax, [rbp+60h+var_D0]
0x18004b563  mov     [rdi+18h], rax
0x18004b567  mov     rax, [rbp+60h+var_C8]
0x18004b56b  mov     [rdi+28h], rax
0x18004b56f  mov     [rdi+38h], rsi
0x18004b573  mov     [r13+0], rdi
0x18004b577  xor     ebx, ebx
0x18004b579  jmp     loc_18004B441
0x18004b57e  mov     [rdi+20h], ebx
0x18004b581  mov     ebx, 80070216h
0x18004b586  mov     rcx, [rbp+60h+var_D0]; pv
0x18004b58a  test    rcx, rcx
0x18004b58d  jz      short loc_18004B59F
0x18004b58f  call    cs:__imp_CoTaskMemFree
0x18004b595  jmp     short loc_18004B59F
0x18004b597  mov     [rdi+14h], ebx
0x18004b59a  mov     ebx, 80070216h
0x18004b59f  mov     rcx, [rbp+60h+arg_28]; pv
0x18004b5a6  test    rcx, rcx
0x18004b5a9  jz      loc_18004B437
0x18004b5af  call    cs:__imp_CoTaskMemFree
0x18004b5b5  jmp     loc_18004B437
0x18004b5ba  mov     [rdi], ebx
0x18004b5bc  mov     ebx, 80070216h
0x18004b5c1  test    rdi, rdi
0x18004b5c4  jz      loc_18004B441
0x18004b5ca  jmp     loc_18004B437
0x18004b5cf  mov     ebx, 80C1021Eh
0x18004b5d4  mov     rdi, qword ptr [rbp+60h+var_C0+8]
0x18004b5d8  test    rdi, rdi
0x18004b5db  jz      short loc_18004B613
0x18004b5dd  or      esi, 0FFFFFFFFh
0x18004b5e0  mov     eax, esi
0x18004b5e2  lock xadd [rdi+8], eax
0x18004b5e7  add     eax, esi
0x18004b5e9  jnz     short loc_18004B613
0x18004b5eb  mov     rax, [rdi]
0x18004b5ee  mov     rcx, rdi
0x18004b5f1  mov     rax, [rax]
0x18004b5f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b5f9  mov     eax, esi
0x18004b5fb  lock xadd [rdi+0Ch], eax
0x18004b600  add     eax, esi
0x18004b602  jnz     short loc_18004B613
0x18004b604  mov     rax, [rdi]
0x18004b607  mov     rcx, rdi
0x18004b60a  mov     rax, [rax+8]
0x18004b60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b613  mov     eax, ebx
0x18004b615  add     rsp, 128h
0x18004b61c  pop     r15
0x18004b61e  pop     r14
0x18004b620  pop     r13
0x18004b622  pop     r12
0x18004b624  pop     rdi
0x18004b625  pop     rsi
0x18004b626  pop     rbx
0x18004b627  pop     rbp
0x18004b628  retn
0x18004b629  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004b630  mov     edx, 1841h; void *
0x18004b635  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
