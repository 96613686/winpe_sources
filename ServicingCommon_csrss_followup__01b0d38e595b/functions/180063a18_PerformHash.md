# PerformHash

- ea: `0x180063a18`
- end: `0x180063c97`
- name: `PerformHash`
- size: `639`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE hAlgorithm)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180065390`

## callees

- `0x18001f1d8`
- `0x18001f840`
- `0x18002d2b0`
- `0x1800639c8`
- `0x180063a18`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x180063c27`
- `bcrypt!BCryptFinishHash` at `0x180063c27`
- `bcrypt!BCryptGetProperty` at `0x180063a78`
- `bcrypt!BCryptGetProperty` at `0x180063a78`
- `bcrypt!BCryptHashData` at `0x180063be1`
- `bcrypt!BCryptHashData` at `0x180063be1`
- `bcrypt!BCryptCreateHash` at `0x180063b73`
- `bcrypt!BCryptCreateHash` at `0x180063b73`

## string_xrefs

- `0x180063ba1`: `::BCryptCreateHash( Alg, Hash.GetInitPointer(), nullptr, 0, nullptr, 0, 0)`

## pseudocode

```c
__int64 __fastcall PerformHash(BCRYPT_ALG_HANDLE hAlgorithm, __int64 a2, __int64 a3)
{
  NTSTATUS Property; // eax
  __int64 v7; // r8
  NTSTATUS v9; // eax
  const char *v10; // rcx
  void *v11; // rdx
  unsigned int v12; // ebx
  void *v13; // rdx
  Windows::Detail *v14; // rcx
  const char *v15; // [rsp+40h] [rbp-40h] BYREF
  const char *v16; // [rsp+48h] [rbp-38h]
  __int64 v17; // [rsp+50h] [rbp-30h]
  const char *v18; // [rsp+58h] [rbp-28h]
  int v19; // [rsp+60h] [rbp-20h] BYREF
  UCHAR pbOutput[4]; // [rsp+64h] [rbp-1Ch] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+68h] [rbp-18h] BYREF
  ULONG pcbResult; // [rsp+70h] [rbp-10h] BYREF

  v19 = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  Property = BCryptGetProperty(hAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    v17 = 1060;
    v15 = "onecore\\base\\lstring\\lblob.cpp";
    v7 = (unsigned int)Property;
    v16 = "PerformHash";
    v18 = "::BCryptGetProperty( Alg, L\"HashDigestLength\", reinterpret_cast<PUCHAR>(&HashLength), sizeof(HashLength), &Unused, 0)";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v19,
             &v15,
             v7);
  }
  if ( *(_QWORD *)(a3 + 8) < (unsigned __int64)*(unsigned int *)pbOutput )
  {
    v17 = 1062;
    v15 = "onecore\\base\\lstring\\lblob.cpp";
    v18 = "DataOut->MaximumLength < HashLength";
    v16 = "PerformHash";
    v7 = 3221225507LL;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v19,
             &v15,
             v7);
  }
  if ( *(_QWORD *)a2 >= 0xFFFFFFFF )
  {
    v17 = 1063;
    v15 = "onecore\\base\\lstring\\lblob.cpp";
    v18 = "DataIn.Length < 0xffffffffUL";
    v16 = "PerformHash";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v19,
             &v15);
  }
  phHash = 0;
  v9 = BCryptCreateHash(hAlgorithm, &phHash, 0, 0, 0, 0, 0);
  if ( v9 < 0 )
  {
    v17 = 1074;
    v15 = "onecore\\base\\lstring\\lblob.cpp";
    v16 = "PerformHash";
    v10 = "::BCryptCreateHash( Alg, Hash.GetInitPointer(), nullptr, 0, nullptr, 0, 0)";
LABEL_10:
    v18 = v10;
    v12 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
            &v19,
            &v15,
            (unsigned int)v9);
    if ( phHash )
      Windows::Detail::CloseWithBCryptDestroyHash((Windows::Detail *)phHash, v11);
    return v12;
  }
  v9 = BCryptHashData(phHash, *(PUCHAR *)(a2 + 16), *(_DWORD *)a2, 0);
  if ( v9 < 0 )
  {
    v17 = 1081;
    v15 = "onecore\\base\\lstring\\lblob.cpp";
    v16 = "PerformHash";
    v10 = "::BCryptHashData( Hash, DataIn.Buffer, static_cast<ULONG>(DataIn.Length), 0)";
    goto LABEL_10;
  }
  v9 = BCryptFinishHash(phHash, *(PUCHAR *)(a3 + 16), *(ULONG *)pbOutput, 0);
  if ( v9 < 0 )
  {
    v17 = 1088;
    v15 = "onecore\\base\\lstring\\lblob.cpp";
    v16 = "PerformHash";
    v10 = "::BCryptFinishHash( Hash, DataOut->Buffer, HashLength, 0)";
    goto LABEL_10;
  }
  v14 = (Windows::Detail *)phHash;
  *(_QWORD *)a3 = *(unsigned int *)pbOutput;
  if ( v14 )
    Windows::Detail::CloseWithBCryptDestroyHash(v14, v13);
  return 0;
}

```

## disassembly

```asm
0x180063a18  mov     [rsp-18h+arg_18], rbx
0x180063a1d  push    rbp
0x180063a1e  push    rsi
0x180063a1f  push    rdi
0x180063a20  mov     rbp, rsp
0x180063a23  sub     rsp, 80h
0x180063a2a  mov     rax, cs:__security_cookie
0x180063a31  xor     rax, rsp
0x180063a34  mov     [rbp+var_8], rax
0x180063a38  mov     rbx, r8
0x180063a3b  mov     [rsp+80h+dwFlags], 0; dwFlags
0x180063a43  mov     rdi, rdx
0x180063a46  mov     [rbp+var_20], 0
0x180063a4d  lea     rax, [rbp+var_10]
0x180063a51  mov     dword ptr [rbp+pbOutput], 0
0x180063a58  lea     r8, [rbp+pbOutput]; pbOutput
0x180063a5c  mov     [rsp+80h+pcbResult], rax; pcbResult
0x180063a61  lea     rdx, pszProperty; "HashDigestLength"
0x180063a68  mov     [rbp+var_10], 0
0x180063a6f  mov     r9d, 4; cbOutput
0x180063a75  mov     rsi, rcx
0x180063a78  call    cs:__imp_BCryptGetProperty
0x180063a7f  nop     dword ptr [rax+rax+00h]
0x180063a84  test    eax, eax
0x180063a86  jns     short loc_180063AC6
0x180063a88  lea     rcx, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180063a8f  mov     [rbp+var_30], 424h
0x180063a97  mov     [rbp+var_40], rcx
0x180063a9b  mov     r8d, eax
0x180063a9e  lea     rcx, aPerformhash; "PerformHash"
0x180063aa5  mov     [rbp+var_38], rcx
0x180063aa9  lea     rcx, aBcryptgetprope_0; "::BCryptGetProperty( Alg, L\"HashDigest"...
0x180063ab0  mov     [rbp+var_28], rcx
0x180063ab4  lea     rdx, [rbp+var_40]
0x180063ab8  lea     rcx, [rbp+var_20]
0x180063abc  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180063ac1  jmp     loc_180063C77
0x180063ac6  mov     eax, dword ptr [rbp+pbOutput]
0x180063ac9  cmp     [rbx+8], rax
0x180063acd  jnb     short loc_180063B00
0x180063acf  lea     rcx, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180063ad6  mov     [rbp+var_30], 426h
0x180063ade  mov     [rbp+var_40], rcx
0x180063ae2  lea     rax, aDataoutMaximum_0; "DataOut->MaximumLength < HashLength"
0x180063ae9  lea     rcx, aPerformhash; "PerformHash"
0x180063af0  mov     [rbp+var_28], rax
0x180063af4  mov     [rbp+var_38], rcx
0x180063af8  mov     r8d, 0C0000023h
0x180063afe  jmp     short loc_180063AB4
0x180063b00  mov     eax, 0FFFFFFFFh
0x180063b05  cmp     [rdi], rax
0x180063b08  jb      short loc_180063B45
0x180063b0a  lea     rcx, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180063b11  mov     [rbp+var_30], 427h
0x180063b19  mov     [rbp+var_40], rcx
0x180063b1d  lea     rax, aDatainLength0x; "DataIn.Length < 0xffffffffUL"
0x180063b24  lea     rcx, aPerformhash; "PerformHash"
0x180063b2b  mov     [rbp+var_28], rax
0x180063b2f  mov     [rbp+var_38], rcx
0x180063b33  lea     rdx, [rbp+var_40]
0x180063b37  lea     rcx, [rbp+var_20]
0x180063b3b  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180063b40  jmp     loc_180063C77
0x180063b45  mov     [rsp+80h+var_50], 0; dwFlags
0x180063b4d  lea     rdx, [rbp+phHash]; phHash
0x180063b51  mov     [rsp+80h+dwFlags], 0; cbSecret
0x180063b59  xor     r9d, r9d; cbHashObject
0x180063b5c  xor     r8d, r8d; pbHashObject
0x180063b5f  mov     [rsp+80h+pcbResult], 0; pbSecret
0x180063b68  mov     rcx, rsi; hAlgorithm
0x180063b6b  mov     [rbp+phHash], 0
0x180063b73  call    cs:__imp_BCryptCreateHash
0x180063b7a  nop     dword ptr [rax+rax+00h]
0x180063b7f  test    eax, eax
0x180063b81  jns     short loc_180063BD3
0x180063b83  lea     rcx, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180063b8a  mov     [rbp+var_30], 432h
0x180063b92  mov     [rbp+var_40], rcx
0x180063b96  lea     rcx, aPerformhash; "PerformHash"
0x180063b9d  mov     [rbp+var_38], rcx
0x180063ba1  lea     rcx, aBcryptcreateha_0; "::BCryptCreateHash( Alg, Hash.GetInitPo"...
0x180063ba8  mov     [rbp+var_28], rcx
0x180063bac  lea     rdx, [rbp+var_40]
0x180063bb0  lea     rcx, [rbp+var_20]
0x180063bb4  mov     r8d, eax
0x180063bb7  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180063bbc  mov     rcx, [rbp+phHash]; this
0x180063bc0  mov     ebx, eax
0x180063bc2  test    rcx, rcx
0x180063bc5  jz      short loc_180063BCC
0x180063bc7  call    ?CloseWithBCryptDestroyHash@Detail@Windows@@YAXPEAX@Z; Windows::Detail::CloseWithBCryptDestroyHash(void *)
0x180063bcc  mov     eax, ebx
0x180063bce  jmp     loc_180063C77
0x180063bd3  mov     r8d, [rdi]; cbInput
0x180063bd6  xor     r9d, r9d; dwFlags
0x180063bd9  mov     rdx, [rdi+10h]; pbInput
0x180063bdd  mov     rcx, [rbp+phHash]; hHash
0x180063be1  call    cs:__imp_BCryptHashData
0x180063be8  nop     dword ptr [rax+rax+00h]
0x180063bed  test    eax, eax
0x180063bef  jns     short loc_180063C18
0x180063bf1  lea     rcx, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180063bf8  mov     [rbp+var_30], 439h
0x180063c00  mov     [rbp+var_40], rcx
0x180063c04  lea     rcx, aPerformhash; "PerformHash"
0x180063c0b  mov     [rbp+var_38], rcx
0x180063c0f  lea     rcx, aBcrypthashdata_0; "::BCryptHashData( Hash, DataIn.Buffer, "...
0x180063c16  jmp     short loc_180063BA8
0x180063c18  mov     r8d, dword ptr [rbp+pbOutput]; cbOutput
0x180063c1c  xor     r9d, r9d; dwFlags
0x180063c1f  mov     rdx, [rbx+10h]; pbOutput
0x180063c23  mov     rcx, [rbp+phHash]; hHash
0x180063c27  call    cs:__imp_BCryptFinishHash
0x180063c2e  nop     dword ptr [rax+rax+00h]
0x180063c33  test    eax, eax
0x180063c35  jns     short loc_180063C61
0x180063c37  lea     rcx, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180063c3e  mov     [rbp+var_30], 440h
0x180063c46  mov     [rbp+var_40], rcx
0x180063c4a  lea     rcx, aPerformhash; "PerformHash"
0x180063c51  mov     [rbp+var_38], rcx
0x180063c55  lea     rcx, aBcryptfinishha_0; "::BCryptFinishHash( Hash, DataOut->Buff"...
0x180063c5c  jmp     loc_180063BA8
0x180063c61  mov     rcx, [rbp+phHash]; this
0x180063c65  mov     eax, dword ptr [rbp+pbOutput]
0x180063c68  mov     [rbx], rax
0x180063c6b  test    rcx, rcx
0x180063c6e  jz      short loc_180063C75
0x180063c70  call    ?CloseWithBCryptDestroyHash@Detail@Windows@@YAXPEAX@Z; Windows::Detail::CloseWithBCryptDestroyHash(void *)
0x180063c75  xor     eax, eax
0x180063c77  mov     rcx, [rbp+var_8]
0x180063c7b  xor     rcx, rsp; StackCookie
0x180063c7e  call    __security_check_cookie
0x180063c83  mov     rbx, [rsp+80h+arg_18]
0x180063c8b  add     rsp, 80h
0x180063c92  pop     rdi
0x180063c93  pop     rsi
0x180063c94  pop     rbp
0x180063c95  retn
```
