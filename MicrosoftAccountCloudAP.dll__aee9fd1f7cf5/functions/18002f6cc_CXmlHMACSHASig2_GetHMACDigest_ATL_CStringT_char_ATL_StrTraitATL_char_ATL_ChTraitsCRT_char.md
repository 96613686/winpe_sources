# CXmlHMACSHASig2::GetHMACDigest(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)

- ea: `0x18002f6cc`
- end: `0x18002f8be`
- name: `?GetHMACDigest@CXmlHMACSHASig2@@QEAAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z`
- size: `498`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18002ea30`
- `0x18002f1c0`

## callees

- `0x180025ee8`
- `0x1800260d4`
- `0x18002634c`
- `0x180026528`
- `0x180026c8c`
- `0x180028050`
- `0x18002e2c4`
- `0x18002f5b0`
- `0x18002f6cc`
- `0x18002f8c4`
- `0x18002f9f8`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18002f8a9`
- `bcrypt!BCryptDestroyHash` at `0x18002f8a9`
- `bcrypt!BCryptFinishHash` at `0x18002f7fd`
- `bcrypt!BCryptFinishHash` at `0x18002f7fd`
- `bcrypt!BCryptHashData` at `0x18002f78e`
- `bcrypt!BCryptHashData` at `0x18002f78e`

## string_xrefs

- `0x18002f889`: `onecoreuap\ds\ext\live\identity\passport\lib\xmlsig\xmlsig2.cpp`
- `0x18002f882`: `CXmlHMACSHASig2::GetHMACDigest`
- `0x18002f740`: `hr = g_algProvCache.GetAlgorithmProv( BCRYPT_SHA256_ALGORITHM, BCRYPT_ALG_HANDLE_HMAC_FLAG, hAlgProv)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXmlHMACSHASig2::GetHMACDigest(__int64 a1, const unsigned __int16 *a2)
{
  int AlgorithmProv; // edi
  const char *v5; // rax
  unsigned int v6; // r8d
  NTSTATUS v7; // eax
  ULONG v8; // ebx
  NTSTATUS v9; // eax
  char *BufferSetLength; // rax
  int v11; // ebx
  unsigned int v13; // [rsp+20h] [rbp-30h]
  int v14; // [rsp+30h] [rbp-20h] BYREF
  PUCHAR pbOutput; // [rsp+38h] [rbp-18h]
  int v16; // [rsp+40h] [rbp-10h]
  ULONG cbOutput; // [rsp+70h] [rbp+20h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+80h] [rbp+30h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+88h] [rbp+38h] BYREF

  hAlgorithm = 0;
  hHash = 0;
  pbOutput = 0;
  v14 = 0;
  v16 = 0;
  cbOutput = 0;
  if ( *(_DWORD *)(a1 + 88) )
  {
    AlgorithmProv = CBCryptAlgorithmProvCache::GetAlgorithmProv((CBCryptAlgorithmProvCache *)a1, a2, 8u, &hAlgorithm);
    if ( AlgorithmProv >= 0 )
    {
      AlgorithmProv = CBCryptHash::Initialize(&hHash, hAlgorithm, *(PUCHAR *)(a1 + 96), *(_DWORD *)(a1 + 88), v13);
      if ( AlgorithmProv >= 0 )
      {
        v7 = BCryptHashData(hHash, *(PUCHAR *)(a1 + 64), *(_DWORD *)(*(_QWORD *)(a1 + 64) - 16LL), 0);
        AlgorithmProv = v7;
        if ( v7 > 0 )
          AlgorithmProv = (unsigned __int16)v7 | 0x80070000;
        if ( AlgorithmProv >= 0 )
        {
          AlgorithmProv = CBCryptHash::GetSize((CBCryptHash *)&hHash, &cbOutput);
          if ( AlgorithmProv >= 0 )
          {
            v8 = cbOutput;
            CBytePtr::SetLength((CBytePtr *)&v14, cbOutput, 0);
            v9 = BCryptFinishHash(hHash, pbOutput, v8, 0);
            AlgorithmProv = v9;
            if ( v9 > 0 )
              AlgorithmProv = (unsigned __int16)v9 | 0x80070000;
            if ( AlgorithmProv >= 0 )
            {
              LODWORD(hAlgorithm) = ATL::Base64EncodeGetRequiredLength(v14, 0);
              BufferSetLength = (char *)ATL::CSimpleStringT<char,0>::GetBufferSetLength(a2, (unsigned int)hAlgorithm);
              v11 = ATL::Base64Encode(pbOutput, v14, BufferSetLength, (int *)&hAlgorithm, 0);
              ATL::CSimpleStringT<char,0>::ReleaseBuffer(a2, (unsigned int)hAlgorithm);
              if ( v11 )
                goto LABEL_20;
              AlgorithmProv = -2147197938;
              v5 = "bRet";
              v6 = 329;
            }
            else
            {
              v5 = "hr = signedInfoHash.GetValue( bpSigValue.GetBufferSetLength(dwSize, FALSE), dwSize)";
              v6 = 314;
            }
          }
          else
          {
            v5 = "hr = signedInfoHash.GetSize(&dwSize)";
            v6 = 309;
          }
        }
        else
        {
          v5 = "hr = signedInfoHash.AddData( const_cast<PUCHAR>(reinterpret_cast<const UCHAR*>(static_cast<LPCSTR>(m_strC"
               "14NSignedInfo))), m_strC14NSignedInfo.GetLength() *sizeof(CHAR))";
          v6 = 306;
        }
      }
      else
      {
        v5 = "hr = signedInfoHash.Initialize( hAlgProv, m_pbSecretKey.GetBuffer(), m_pbSecretKey.GetLength())";
        v6 = 302;
      }
    }
    else
    {
      v5 = "hr = g_algProvCache.GetAlgorithmProv( BCRYPT_SHA256_ALGORITHM, BCRYPT_ALG_HANDLE_HMAC_FLAG, hAlgProv)";
      v6 = 297;
    }
  }
  else
  {
    AlgorithmProv = -2147216615;
    v5 = "m_pbSecretKey.GetLength() != 0";
    v6 = 292;
  }
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\passport\\lib\\xmlsig\\xmlsig2.cpp",
    "CXmlHMACSHASig2::GetHMACDigest",
    v6,
    AlgorithmProv,
    v5);
LABEL_20:
  CBytePtr::Empty((CBytePtr *)&v14);
  if ( hHash )
    BCryptDestroyHash(hHash);
  return (unsigned int)AlgorithmProv;
}

```

## disassembly

```asm
0x18002f6cc  mov     [rsp-18h+arg_8], rbx
0x18002f6d1  push    rbp
0x18002f6d2  push    rsi
0x18002f6d3  push    rdi
0x18002f6d4  mov     rbp, rsp
0x18002f6d7  sub     rsp, 50h
0x18002f6db  mov     rsi, rdx
0x18002f6de  mov     rbx, rcx
0x18002f6e1  mov     [rbp+hAlgorithm], 0
0x18002f6e9  mov     [rbp+hHash], 0
0x18002f6f1  mov     [rbp+pbOutput], 0
0x18002f6f9  mov     [rbp+var_20], 0
0x18002f700  mov     [rbp+var_10], 0
0x18002f707  mov     [rbp+cbOutput], 0
0x18002f70e  cmp     dword ptr [rcx+58h], 0
0x18002f712  jnz     short loc_18002F72B
0x18002f714  mov     edi, 80041319h
0x18002f719  lea     rax, aMPbsecretkeyGe; "m_pbSecretKey.GetLength() != 0"
0x18002f720  mov     r8d, 124h
0x18002f726  jmp     loc_18002F87A
0x18002f72b  lea     r9, [rbp+hAlgorithm]; void **
0x18002f72f  mov     r8d, 8; unsigned int
0x18002f735  call    ?GetAlgorithmProv@CBCryptAlgorithmProvCache@@QEAAJPEBGKAEAPEAX@Z; CBCryptAlgorithmProvCache::GetAlgorithmProv(ushort const *,ulong,void * &)
0x18002f73a  mov     edi, eax
0x18002f73c  test    eax, eax
0x18002f73e  jns     short loc_18002F752
0x18002f740  lea     rax, aHrGAlgprovcach; "hr = g_algProvCache.GetAlgorithmProv( B"...
0x18002f747  mov     r8d, 129h
0x18002f74d  jmp     loc_18002F87A
0x18002f752  mov     r9d, [rbx+58h]; cbSecret
0x18002f756  mov     r8, [rbx+60h]; pbSecret
0x18002f75a  mov     rdx, [rbp+hAlgorithm]; hAlgorithm
0x18002f75e  lea     rcx, [rbp+hHash]; phHash
0x18002f762  call    ?Initialize@CBCryptHash@@QEAAJPEAXPEAEKK@Z; CBCryptHash::Initialize(void *,uchar *,ulong,ulong)
0x18002f767  mov     edi, eax
0x18002f769  test    eax, eax
0x18002f76b  jns     short loc_18002F77F
0x18002f76d  lea     rax, aHrSignedinfoha_2; "hr = signedInfoHash.Initialize( hAlgPro"...
0x18002f774  mov     r8d, 12Eh
0x18002f77a  jmp     loc_18002F87A
0x18002f77f  mov     rdx, [rbx+40h]; pbInput
0x18002f783  xor     r9d, r9d; dwFlags
0x18002f786  mov     r8d, [rdx-10h]; cbInput
0x18002f78a  mov     rcx, [rbp+hHash]; hHash
0x18002f78e  call    cs:__imp_BCryptHashData
0x18002f794  mov     edi, eax
0x18002f796  test    eax, eax
0x18002f798  jle     short loc_18002F7A3
0x18002f79a  movzx   edi, ax
0x18002f79d  or      edi, 80070000h
0x18002f7a3  test    edi, edi
0x18002f7a5  jns     short loc_18002F7B9
0x18002f7a7  lea     rax, aHrSignedinfoha_1; "hr = signedInfoHash.AddData( const_cast"...
0x18002f7ae  mov     r8d, 132h
0x18002f7b4  jmp     loc_18002F87A
0x18002f7b9  lea     rdx, [rbp+cbOutput]; unsigned int *
0x18002f7bd  lea     rcx, [rbp+hHash]; this
0x18002f7c1  call    ?GetSize@CBCryptHash@@QEAAJPEAK@Z; CBCryptHash::GetSize(ulong *)
0x18002f7c6  mov     edi, eax
0x18002f7c8  test    eax, eax
0x18002f7ca  jns     short loc_18002F7DE
0x18002f7cc  lea     rax, aHrSignedinfoha; "hr = signedInfoHash.GetSize(&dwSize)"
0x18002f7d3  mov     r8d, 135h
0x18002f7d9  jmp     loc_18002F87A
0x18002f7de  mov     ebx, [rbp+cbOutput]
0x18002f7e1  xor     r8d, r8d; bool
0x18002f7e4  mov     edx, ebx; unsigned int
0x18002f7e6  lea     rcx, [rbp+var_20]; this
0x18002f7ea  call    ?SetLength@CBytePtr@@QEAAXK_N@Z; CBytePtr::SetLength(ulong,bool)
0x18002f7ef  xor     r9d, r9d; dwFlags
0x18002f7f2  mov     r8d, ebx; cbOutput
0x18002f7f5  mov     rdx, [rbp+pbOutput]; pbOutput
0x18002f7f9  mov     rcx, [rbp+hHash]; hHash
0x18002f7fd  call    cs:__imp_BCryptFinishHash
0x18002f803  mov     edi, eax
0x18002f805  test    eax, eax
0x18002f807  jle     short loc_18002F812
0x18002f809  movzx   edi, ax
0x18002f80c  or      edi, 80070000h
0x18002f812  test    edi, edi
0x18002f814  jns     short loc_18002F825
0x18002f816  lea     rax, aHrSignedinfoha_0; "hr = signedInfoHash.GetValue( bpSigValu"...
0x18002f81d  mov     r8d, 13Ah
0x18002f823  jmp     short loc_18002F87A
0x18002f825  xor     edx, edx; unsigned int
0x18002f827  mov     ecx, [rbp+var_20]; int
0x18002f82a  call    ?Base64EncodeGetRequiredLength@ATL@@YAHHK@Z; ATL::Base64EncodeGetRequiredLength(int,ulong)
0x18002f82f  mov     dword ptr [rbp+hAlgorithm], eax
0x18002f832  mov     edx, eax
0x18002f834  mov     rcx, rsi
0x18002f837  call    ?GetBufferSetLength@?$CSimpleStringT@D$0A@@ATL@@QEAAPEADH@Z; ATL::CSimpleStringT<char,0>::GetBufferSetLength(int)
0x18002f83c  mov     [rsp+50h+var_30], 0; unsigned int
0x18002f844  lea     r9, [rbp+hAlgorithm]; int *
0x18002f848  mov     r8, rax; char *
0x18002f84b  mov     edx, [rbp+var_20]; int
0x18002f84e  mov     rcx, [rbp+pbOutput]; unsigned __int8 *
0x18002f852  call    ?Base64Encode@ATL@@YAHPEBEHPEADPEAHK@Z; ATL::Base64Encode(uchar const *,int,char *,int *,ulong)
0x18002f857  mov     ebx, eax
0x18002f859  mov     edx, dword ptr [rbp+hAlgorithm]
0x18002f85c  mov     rcx, rsi
0x18002f85f  call    ?ReleaseBuffer@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::ReleaseBuffer(int)
0x18002f864  test    ebx, ebx
0x18002f866  jnz     short loc_18002F896
0x18002f868  mov     edi, 80045C0Eh
0x18002f86d  lea     rax, aBret; "bRet"
0x18002f874  mov     r8d, 149h; unsigned int
0x18002f87a  mov     qword ptr [rsp+50h+var_30], rax; char *
0x18002f87f  mov     r9d, edi; int
0x18002f882  lea     rdx, aCxmlhmacshasig; "CXmlHMACSHASig2::GetHMACDigest"
0x18002f889  lea     rcx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\pa"...
0x18002f890  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18002f895  nop
0x18002f896  lea     rcx, [rbp+var_20]; this
0x18002f89a  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x18002f89f  nop
0x18002f8a0  mov     rcx, [rbp+hHash]; hHash
0x18002f8a4  test    rcx, rcx
0x18002f8a7  jz      short loc_18002F8AF
0x18002f8a9  call    cs:__imp_BCryptDestroyHash
0x18002f8af  mov     eax, edi
0x18002f8b1  mov     rbx, [rsp+50h+arg_8]
0x18002f8b6  add     rsp, 50h
0x18002f8ba  pop     rdi
0x18002f8bb  pop     rsi
0x18002f8bc  pop     rbp
0x18002f8bd  retn
```
