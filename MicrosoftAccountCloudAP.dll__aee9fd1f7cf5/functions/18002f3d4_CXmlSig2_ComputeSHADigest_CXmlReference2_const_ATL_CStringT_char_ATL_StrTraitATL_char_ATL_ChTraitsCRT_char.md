# CXmlSig2::ComputeSHADigest(CXmlReference2 const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)

- ea: `0x18002f3d4`
- end: `0x18002f5a8`
- name: `?ComputeSHADigest@CXmlSig2@@AEAAJAEBVCXmlReference2@@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z`
- size: `468`
- prototype: `__int64 __fastcall(CBCryptAlgorithmProvCache *, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f38c`

## callees

- `0x180025ee8`
- `0x1800260d4`
- `0x18002634c`
- `0x180026528`
- `0x180026c8c`
- `0x180028050`
- `0x18002e2c4`
- `0x18002f3d4`
- `0x18002f5b0`
- `0x18002f8c4`
- `0x18002f9f8`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18002f593`
- `bcrypt!BCryptDestroyHash` at `0x18002f593`
- `bcrypt!BCryptFinishHash` at `0x18002f4e7`
- `bcrypt!BCryptFinishHash` at `0x18002f4e7`
- `bcrypt!BCryptHashData` at `0x18002f478`
- `bcrypt!BCryptHashData` at `0x18002f478`

## string_xrefs

- `0x18002f573`: `onecoreuap\ds\ext\live\identity\passport\lib\xmlsig\xmlsig2.cpp`
- `0x18002f42d`: `hr = g_algProvCache.GetAlgorithmProv( BCRYPT_SHA256_ALGORITHM, 0, hAlgProv)`
- `0x18002f56c`: `CXmlSig2::ComputeSHADigest`
- `0x18002f491`: `hr = referenceHash.AddData( (const PBYTE)((LPCSTR)xmlRef.m_strText), xmlRef.m_strText.GetLength())`

## pseudocode

```c
__int64 __fastcall CXmlSig2::ComputeSHADigest(CBCryptAlgorithmProvCache *a1, const unsigned __int16 *a2, __int64 a3)
{
  signed int AlgorithmProv; // edi
  const char *v6; // rax
  unsigned int v7; // r8d
  NTSTATUS v8; // eax
  ULONG v9; // ebx
  NTSTATUS v10; // eax
  char *BufferSetLength; // rax
  int v12; // ebx
  unsigned int v14; // [rsp+20h] [rbp-30h]
  BCRYPT_HASH_HANDLE hHash; // [rsp+30h] [rbp-20h] BYREF
  int v16; // [rsp+38h] [rbp-18h] BYREF
  PUCHAR pbOutput; // [rsp+40h] [rbp-10h]
  int v18; // [rsp+48h] [rbp-8h]
  ULONG cbOutput; // [rsp+70h] [rbp+20h] BYREF
  int v20; // [rsp+74h] [rbp+24h]
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+88h] [rbp+38h] BYREF

  v20 = HIDWORD(a1);
  hAlgorithm = 0;
  hHash = 0;
  cbOutput = 0;
  pbOutput = 0;
  v16 = 0;
  v18 = 0;
  AlgorithmProv = CBCryptAlgorithmProvCache::GetAlgorithmProv(a1, a2, 0, &hAlgorithm);
  if ( AlgorithmProv >= 0 )
  {
    AlgorithmProv = CBCryptHash::Initialize(&hHash, hAlgorithm, 0, 0, v14);
    if ( AlgorithmProv >= 0 )
    {
      v8 = BCryptHashData(hHash, *(PUCHAR *)a2, *(_DWORD *)(*(_QWORD *)a2 - 16LL), 0);
      AlgorithmProv = v8;
      if ( v8 > 0 )
        AlgorithmProv = (unsigned __int16)v8 | 0x80070000;
      if ( AlgorithmProv >= 0 )
      {
        AlgorithmProv = CBCryptHash::GetSize((CBCryptHash *)&hHash, &cbOutput);
        if ( AlgorithmProv >= 0 )
        {
          v9 = cbOutput;
          CBytePtr::SetLength((CBytePtr *)&v16, cbOutput, 0);
          v10 = BCryptFinishHash(hHash, pbOutput, v9, 0);
          AlgorithmProv = v10;
          if ( v10 > 0 )
            AlgorithmProv = (unsigned __int16)v10 | 0x80070000;
          if ( AlgorithmProv >= 0 )
          {
            LODWORD(hAlgorithm) = ATL::Base64EncodeGetRequiredLength(v16, 0);
            BufferSetLength = (char *)ATL::CSimpleStringT<char,0>::GetBufferSetLength(a3, (unsigned int)hAlgorithm);
            v12 = ATL::Base64Encode(pbOutput, v16, BufferSetLength, (int *)&hAlgorithm, 0);
            ATL::CSimpleStringT<char,0>::ReleaseBuffer(a3, (unsigned int)hAlgorithm);
            if ( v12 )
              goto LABEL_18;
            AlgorithmProv = -2147197938;
            v6 = "bRet";
            v7 = 151;
          }
          else
          {
            v6 = "hr = referenceHash.GetValue( bpDigest.GetBufferSetLength(dwSize, FALSE), dwSize)";
            v7 = 136;
          }
        }
        else
        {
          v6 = "hr = referenceHash.GetSize(&dwSize)";
          v7 = 131;
        }
      }
      else
      {
        v6 = "hr = referenceHash.AddData( (const PBYTE)((LPCSTR)xmlRef.m_strText), xmlRef.m_strText.GetLength())";
        v7 = 128;
      }
    }
    else
    {
      v6 = "hr = referenceHash.Initialize( hAlgProv, nullptr, 0)";
      v7 = 124;
    }
  }
  else
  {
    v6 = "hr = g_algProvCache.GetAlgorithmProv( BCRYPT_SHA256_ALGORITHM, 0, hAlgProv)";
    v7 = 119;
  }
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\passport\\lib\\xmlsig\\xmlsig2.cpp",
    "CXmlSig2::ComputeSHADigest",
    v7,
    AlgorithmProv,
    v6);
LABEL_18:
  CBytePtr::Empty((CBytePtr *)&v16);
  if ( hHash )
    BCryptDestroyHash(hHash);
  return (unsigned int)AlgorithmProv;
}

```

## disassembly

```asm
0x18002f3d4  mov     [rsp-18h+arg_8], rbx
0x18002f3d9  mov     qword ptr [rsp-18h+cbOutput], rcx
0x18002f3de  push    rbp
0x18002f3df  push    rsi
0x18002f3e0  push    rdi
0x18002f3e1  mov     rbp, rsp
0x18002f3e4  sub     rsp, 50h
0x18002f3e8  mov     rsi, r8
0x18002f3eb  mov     rbx, rdx
0x18002f3ee  mov     [rbp+hAlgorithm], 0
0x18002f3f6  mov     [rbp+hHash], 0
0x18002f3fe  mov     [rbp+cbOutput], 0
0x18002f405  mov     [rbp+pbOutput], 0
0x18002f40d  mov     [rbp+var_18], 0
0x18002f414  mov     [rbp+var_8], 0
0x18002f41b  lea     r9, [rbp+hAlgorithm]; void **
0x18002f41f  xor     r8d, r8d; unsigned int
0x18002f422  call    ?GetAlgorithmProv@CBCryptAlgorithmProvCache@@QEAAJPEBGKAEAPEAX@Z; CBCryptAlgorithmProvCache::GetAlgorithmProv(ushort const *,ulong,void * &)
0x18002f427  mov     edi, eax
0x18002f429  test    eax, eax
0x18002f42b  jns     short loc_18002F43F
0x18002f42d  lea     rax, aHrGAlgprovcach_0; "hr = g_algProvCache.GetAlgorithmProv( B"...
0x18002f434  mov     r8d, 77h ; 'w'
0x18002f43a  jmp     loc_18002F564
0x18002f43f  xor     r9d, r9d; cbSecret
0x18002f442  xor     r8d, r8d; pbSecret
0x18002f445  mov     rdx, [rbp+hAlgorithm]; hAlgorithm
0x18002f449  lea     rcx, [rbp+hHash]; phHash
0x18002f44d  call    ?Initialize@CBCryptHash@@QEAAJPEAXPEAEKK@Z; CBCryptHash::Initialize(void *,uchar *,ulong,ulong)
0x18002f452  mov     edi, eax
0x18002f454  test    eax, eax
0x18002f456  jns     short loc_18002F46A
0x18002f458  lea     rax, aHrReferencehas_1; "hr = referenceHash.Initialize( hAlgProv"...
0x18002f45f  mov     r8d, 7Ch ; '|'
0x18002f465  jmp     loc_18002F564
0x18002f46a  mov     rdx, [rbx]; pbInput
0x18002f46d  xor     r9d, r9d; dwFlags
0x18002f470  mov     r8d, [rdx-10h]; cbInput
0x18002f474  mov     rcx, [rbp+hHash]; hHash
0x18002f478  call    cs:__imp_BCryptHashData
0x18002f47e  mov     edi, eax
0x18002f480  test    eax, eax
0x18002f482  jle     short loc_18002F48D
0x18002f484  movzx   edi, ax
0x18002f487  or      edi, 80070000h
0x18002f48d  test    edi, edi
0x18002f48f  jns     short loc_18002F4A3
0x18002f491  lea     rax, aHrReferencehas; "hr = referenceHash.AddData( (const PBYT"...
0x18002f498  mov     r8d, 80h
0x18002f49e  jmp     loc_18002F564
0x18002f4a3  lea     rdx, [rbp+cbOutput]; unsigned int *
0x18002f4a7  lea     rcx, [rbp+hHash]; this
0x18002f4ab  call    ?GetSize@CBCryptHash@@QEAAJPEAK@Z; CBCryptHash::GetSize(ulong *)
0x18002f4b0  mov     edi, eax
0x18002f4b2  test    eax, eax
0x18002f4b4  jns     short loc_18002F4C8
0x18002f4b6  lea     rax, aHrReferencehas_2; "hr = referenceHash.GetSize(&dwSize)"
0x18002f4bd  mov     r8d, 83h
0x18002f4c3  jmp     loc_18002F564
0x18002f4c8  mov     ebx, [rbp+cbOutput]
0x18002f4cb  xor     r8d, r8d; bool
0x18002f4ce  mov     edx, ebx; unsigned int
0x18002f4d0  lea     rcx, [rbp+var_18]; this
0x18002f4d4  call    ?SetLength@CBytePtr@@QEAAXK_N@Z; CBytePtr::SetLength(ulong,bool)
0x18002f4d9  xor     r9d, r9d; dwFlags
0x18002f4dc  mov     r8d, ebx; cbOutput
0x18002f4df  mov     rdx, [rbp+pbOutput]; pbOutput
0x18002f4e3  mov     rcx, [rbp+hHash]; hHash
0x18002f4e7  call    cs:__imp_BCryptFinishHash
0x18002f4ed  mov     edi, eax
0x18002f4ef  test    eax, eax
0x18002f4f1  jle     short loc_18002F4FC
0x18002f4f3  movzx   edi, ax
0x18002f4f6  or      edi, 80070000h
0x18002f4fc  test    edi, edi
0x18002f4fe  jns     short loc_18002F50F
0x18002f500  lea     rax, aHrReferencehas_0; "hr = referenceHash.GetValue( bpDigest.G"...
0x18002f507  mov     r8d, 88h
0x18002f50d  jmp     short loc_18002F564
0x18002f50f  xor     edx, edx; unsigned int
0x18002f511  mov     ecx, [rbp+var_18]; int
0x18002f514  call    ?Base64EncodeGetRequiredLength@ATL@@YAHHK@Z; ATL::Base64EncodeGetRequiredLength(int,ulong)
0x18002f519  mov     dword ptr [rbp+hAlgorithm], eax
0x18002f51c  mov     edx, eax
0x18002f51e  mov     rcx, rsi
0x18002f521  call    ?GetBufferSetLength@?$CSimpleStringT@D$0A@@ATL@@QEAAPEADH@Z; ATL::CSimpleStringT<char,0>::GetBufferSetLength(int)
0x18002f526  mov     [rsp+50h+var_30], 0; unsigned int
0x18002f52e  lea     r9, [rbp+hAlgorithm]; int *
0x18002f532  mov     r8, rax; char *
0x18002f535  mov     edx, [rbp+var_18]; int
0x18002f538  mov     rcx, [rbp+pbOutput]; unsigned __int8 *
0x18002f53c  call    ?Base64Encode@ATL@@YAHPEBEHPEADPEAHK@Z; ATL::Base64Encode(uchar const *,int,char *,int *,ulong)
0x18002f541  mov     ebx, eax
0x18002f543  mov     edx, dword ptr [rbp+hAlgorithm]
0x18002f546  mov     rcx, rsi
0x18002f549  call    ?ReleaseBuffer@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::ReleaseBuffer(int)
0x18002f54e  test    ebx, ebx
0x18002f550  jnz     short loc_18002F580
0x18002f552  mov     edi, 80045C0Eh
0x18002f557  lea     rax, aBret; "bRet"
0x18002f55e  mov     r8d, 97h; unsigned int
0x18002f564  mov     qword ptr [rsp+50h+var_30], rax; char *
0x18002f569  mov     r9d, edi; int
0x18002f56c  lea     rdx, aCxmlsig2Comput_0; "CXmlSig2::ComputeSHADigest"
0x18002f573  lea     rcx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\pa"...
0x18002f57a  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18002f57f  nop
0x18002f580  lea     rcx, [rbp+var_18]; this
0x18002f584  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x18002f589  nop
0x18002f58a  mov     rcx, [rbp+hHash]; hHash
0x18002f58e  test    rcx, rcx
0x18002f591  jz      short loc_18002F599
0x18002f593  call    cs:__imp_BCryptDestroyHash
0x18002f599  mov     eax, edi
0x18002f59b  mov     rbx, [rsp+50h+arg_8]
0x18002f5a0  add     rsp, 50h
0x18002f5a4  pop     rdi
0x18002f5a5  pop     rsi
0x18002f5a6  pop     rbp
0x18002f5a7  retn
```
