# PerformHash

- ea: `0x180062d20`
- end: `0x180062f9f`
- name: `PerformHash`
- size: `639`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE hAlgorithm)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180064a80`

## callees

- `0x18001f4ac`
- `0x18001f5d4`
- `0x1800293a0`
- `0x180062cd0`
- `0x180062d20`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x180062f2f`
- `bcrypt!BCryptFinishHash` at `0x180062f2f`
- `bcrypt!BCryptGetProperty` at `0x180062d80`
- `bcrypt!BCryptGetProperty` at `0x180062d80`
- `bcrypt!BCryptHashData` at `0x180062ee9`
- `bcrypt!BCryptHashData` at `0x180062ee9`
- `bcrypt!BCryptCreateHash` at `0x180062e7b`
- `bcrypt!BCryptCreateHash` at `0x180062e7b`

## string_xrefs

- `0x180062ea9`: `::BCryptCreateHash( Alg, Hash.GetInitPointer(), nullptr, 0, nullptr, 0, 0)`

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
0x180062d20  mov     [rsp-18h+arg_18], rbx
0x180062d25  push    rbp
0x180062d26  push    rsi
0x180062d27  push    rdi
0x180062d28  mov     rbp, rsp
0x180062d2b  sub     rsp, 80h
0x180062d32  mov     rax, cs:__security_cookie
0x180062d39  xor     rax, rsp
0x180062d3c  mov     [rbp+var_8], rax
0x180062d40  mov     rbx, r8
0x180062d43  mov     [rsp+80h+dwFlags], 0; dwFlags
0x180062d4b  mov     rdi, rdx
0x180062d4e  mov     [rbp+var_20], 0
0x180062d55  lea     rax, [rbp+var_10]
0x180062d59  mov     dword ptr [rbp+pbOutput], 0
0x180062d60  lea     r8, [rbp+pbOutput]; pbOutput
0x180062d64  mov     [rsp+80h+pcbResult], rax; pcbResult
0x180062d69  lea     rdx, pszProperty; "HashDigestLength"
0x180062d70  mov     [rbp+var_10], 0
0x180062d77  mov     r9d, 4; cbOutput
0x180062d7d  mov     rsi, rcx
0x180062d80  call    cs:__imp_BCryptGetProperty
0x180062d87  nop     dword ptr [rax+rax+00h]
0x180062d8c  test    eax, eax
0x180062d8e  jns     short loc_180062DCE
0x180062d90  lea     rcx, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180062d97  mov     [rbp+var_30], 424h
0x180062d9f  mov     [rbp+var_40], rcx
0x180062da3  mov     r8d, eax
0x180062da6  lea     rcx, aPerformhash; "PerformHash"
0x180062dad  mov     [rbp+var_38], rcx
0x180062db1  lea     rcx, aBcryptgetprope_0; "::BCryptGetProperty( Alg, L\"HashDigest"...
0x180062db8  mov     [rbp+var_28], rcx
0x180062dbc  lea     rdx, [rbp+var_40]
0x180062dc0  lea     rcx, [rbp+var_20]
0x180062dc4  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180062dc9  jmp     loc_180062F7F
0x180062dce  mov     eax, dword ptr [rbp+pbOutput]
0x180062dd1  cmp     [rbx+8], rax
0x180062dd5  jnb     short loc_180062E08
0x180062dd7  lea     rcx, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180062dde  mov     [rbp+var_30], 426h
0x180062de6  mov     [rbp+var_40], rcx
0x180062dea  lea     rax, aDataoutMaximum_0; "DataOut->MaximumLength < HashLength"
0x180062df1  lea     rcx, aPerformhash; "PerformHash"
0x180062df8  mov     [rbp+var_28], rax
0x180062dfc  mov     [rbp+var_38], rcx
0x180062e00  mov     r8d, 0C0000023h
0x180062e06  jmp     short loc_180062DBC
0x180062e08  mov     eax, 0FFFFFFFFh
0x180062e0d  cmp     [rdi], rax
0x180062e10  jb      short loc_180062E4D
0x180062e12  lea     rcx, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180062e19  mov     [rbp+var_30], 427h
0x180062e21  mov     [rbp+var_40], rcx
0x180062e25  lea     rax, aDatainLength0x; "DataIn.Length < 0xffffffffUL"
0x180062e2c  lea     rcx, aPerformhash; "PerformHash"
0x180062e33  mov     [rbp+var_28], rax
0x180062e37  mov     [rbp+var_38], rcx
0x180062e3b  lea     rdx, [rbp+var_40]
0x180062e3f  lea     rcx, [rbp+var_20]
0x180062e43  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180062e48  jmp     loc_180062F7F
0x180062e4d  mov     [rsp+80h+var_50], 0; dwFlags
0x180062e55  lea     rdx, [rbp+phHash]; phHash
0x180062e59  mov     [rsp+80h+dwFlags], 0; cbSecret
0x180062e61  xor     r9d, r9d; cbHashObject
0x180062e64  xor     r8d, r8d; pbHashObject
0x180062e67  mov     [rsp+80h+pcbResult], 0; pbSecret
0x180062e70  mov     rcx, rsi; hAlgorithm
0x180062e73  mov     [rbp+phHash], 0
0x180062e7b  call    cs:__imp_BCryptCreateHash
0x180062e82  nop     dword ptr [rax+rax+00h]
0x180062e87  test    eax, eax
0x180062e89  jns     short loc_180062EDB
0x180062e8b  lea     rcx, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180062e92  mov     [rbp+var_30], 432h
0x180062e9a  mov     [rbp+var_40], rcx
0x180062e9e  lea     rcx, aPerformhash; "PerformHash"
0x180062ea5  mov     [rbp+var_38], rcx
0x180062ea9  lea     rcx, aBcryptcreateha_0; "::BCryptCreateHash( Alg, Hash.GetInitPo"...
0x180062eb0  mov     [rbp+var_28], rcx
0x180062eb4  lea     rdx, [rbp+var_40]
0x180062eb8  lea     rcx, [rbp+var_20]
0x180062ebc  mov     r8d, eax
0x180062ebf  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180062ec4  mov     rcx, [rbp+phHash]; this
0x180062ec8  mov     ebx, eax
0x180062eca  test    rcx, rcx
0x180062ecd  jz      short loc_180062ED4
0x180062ecf  call    ?CloseWithBCryptDestroyHash@Detail@Windows@@YAXPEAX@Z; Windows::Detail::CloseWithBCryptDestroyHash(void *)
0x180062ed4  mov     eax, ebx
0x180062ed6  jmp     loc_180062F7F
0x180062edb  mov     r8d, [rdi]; cbInput
0x180062ede  xor     r9d, r9d; dwFlags
0x180062ee1  mov     rdx, [rdi+10h]; pbInput
0x180062ee5  mov     rcx, [rbp+phHash]; hHash
0x180062ee9  call    cs:__imp_BCryptHashData
0x180062ef0  nop     dword ptr [rax+rax+00h]
0x180062ef5  test    eax, eax
0x180062ef7  jns     short loc_180062F20
0x180062ef9  lea     rcx, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180062f00  mov     [rbp+var_30], 439h
0x180062f08  mov     [rbp+var_40], rcx
0x180062f0c  lea     rcx, aPerformhash; "PerformHash"
0x180062f13  mov     [rbp+var_38], rcx
0x180062f17  lea     rcx, aBcrypthashdata_0; "::BCryptHashData( Hash, DataIn.Buffer, "...
0x180062f1e  jmp     short loc_180062EB0
0x180062f20  mov     r8d, dword ptr [rbp+pbOutput]; cbOutput
0x180062f24  xor     r9d, r9d; dwFlags
0x180062f27  mov     rdx, [rbx+10h]; pbOutput
0x180062f2b  mov     rcx, [rbp+phHash]; hHash
0x180062f2f  call    cs:__imp_BCryptFinishHash
0x180062f36  nop     dword ptr [rax+rax+00h]
0x180062f3b  test    eax, eax
0x180062f3d  jns     short loc_180062F69
0x180062f3f  lea     rcx, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180062f46  mov     [rbp+var_30], 440h
0x180062f4e  mov     [rbp+var_40], rcx
0x180062f52  lea     rcx, aPerformhash; "PerformHash"
0x180062f59  mov     [rbp+var_38], rcx
0x180062f5d  lea     rcx, aBcryptfinishha_0; "::BCryptFinishHash( Hash, DataOut->Buff"...
0x180062f64  jmp     loc_180062EB0
0x180062f69  mov     rcx, [rbp+phHash]; this
0x180062f6d  mov     eax, dword ptr [rbp+pbOutput]
0x180062f70  mov     [rbx], rax
0x180062f73  test    rcx, rcx
0x180062f76  jz      short loc_180062F7D
0x180062f78  call    ?CloseWithBCryptDestroyHash@Detail@Windows@@YAXPEAX@Z; Windows::Detail::CloseWithBCryptDestroyHash(void *)
0x180062f7d  xor     eax, eax
0x180062f7f  mov     rcx, [rbp+var_8]
0x180062f83  xor     rcx, rsp; StackCookie
0x180062f86  call    __security_check_cookie
0x180062f8b  mov     rbx, [rsp+80h+arg_18]
0x180062f93  add     rsp, 80h
0x180062f9a  pop     rdi
0x180062f9b  pop     rsi
0x180062f9c  pop     rbp
0x180062f9d  retn
```
