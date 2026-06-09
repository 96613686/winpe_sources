# WaasMedic::GetSha256HashOfString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14000f3ec`
- end: `0x14000f6ed`
- name: `?GetSha256HashOfString@WaasMedic@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z`
- size: `769`
- prototype: `__int64 __fastcall(_QWORD *pbInput, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x14000a120`

## callees

- `0x140002a30`
- `0x140004290`
- `0x140004670`
- `0x140006e60`
- `0x14000b470`
- `0x14000efd4`
- `0x14000f228`
- `0x14000f34c`
- `0x14000f3ec`
- `0x14000ff6c`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x14000f675`
- `bcrypt!BCryptDestroyHash` at `0x14000f675`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14000f666`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14000f666`
- `bcrypt!BCryptHashData` at `0x14000f58f`
- `bcrypt!BCryptHashData` at `0x14000f58f`
- `bcrypt!BCryptFinishHash` at `0x14000f5a9`
- `bcrypt!BCryptFinishHash` at `0x14000f5a9`
- `bcrypt!BCryptCreateHash` at `0x14000f553`
- `bcrypt!BCryptCreateHash` at `0x14000f553`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14000f457`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14000f457`
- `bcrypt!BCryptGetProperty` at `0x14000f4a9`
- `bcrypt!BCryptGetProperty` at `0x14000f506`
- `bcrypt!BCryptGetProperty` at `0x14000f4a9`
- `bcrypt!BCryptGetProperty` at `0x14000f506`

## string_xrefs

- `0x14000f46a`: `BCryptOpenAlgorithmProvider failed. Error code: 0x%08x`
- `0x14000f566`: `BCryptCreateHash failed. Error code: 0x%08x`
- `0x14000f6e0`: `Failed to write bytes to the allocated string. Error code: 0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::GetSha256HashOfString(_QWORD *pbInput, __int64 a2)
{
  __int64 v3; // rsi
  UCHAR *v4; // r13
  UCHAR *v5; // r12
  unsigned __int16 *v6; // r15
  NTSTATUS v7; // eax
  int v8; // edi
  int v9; // eax
  const unsigned __int16 *v10; // rdx
  unsigned int v11; // ebx
  void *v12; // rdx
  NTSTATUS Property; // eax
  unsigned __int64 v14; // rdx
  bool v15; // r8
  unsigned __int64 v16; // rdx
  bool v17; // r8
  NTSTATUS v18; // eax
  UCHAR *v19; // rdx
  unsigned __int64 v20; // rdx
  bool v21; // r8
  unsigned __int64 v22; // r8
  UCHAR v24[4]; // [rsp+48h] [rbp-39h] BYREF
  UCHAR pbOutput[4]; // [rsp+4Ch] [rbp-35h] BYREF
  ULONG pcbResult; // [rsp+50h] [rbp-31h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-29h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+60h] [rbp-21h] BYREF
  __int64 v29; // [rsp+68h] [rbp-19h]
  __int64 v30; // [rsp+70h] [rbp-11h]
  _QWORD *v31; // [rsp+78h] [rbp-9h]
  _OWORD v32[2]; // [rsp+80h] [rbp-1h] BYREF

  v30 = -2;
  v29 = a2;
  v31 = pbInput;
  v3 = 0;
  phAlgorithm = 0;
  phHash = 0;
  *(_DWORD *)pbOutput = 0;
  v4 = 0;
  v5 = 0;
  *(_DWORD *)v24 = 0;
  pcbResult = 0;
  v6 = 0;
  v7 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  v8 = v7;
  if ( v7 )
  {
    v9 = WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(v7);
    v10 = L"BCryptOpenAlgorithmProvider failed. Error code: 0x%08x";
LABEL_3:
    v11 = v9;
LABEL_4:
    LogLevelW(2u, v10, (unsigned int)v9);
    goto LABEL_28;
  }
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  v8 = Property;
  if ( Property )
    goto LABEL_7;
  v4 = (UCHAR *)WaasMedic::SafeAlloc((WaasMedic *)*(unsigned int *)pbOutput, v14, v15);
  if ( !v4 )
  {
    v11 = -2147024882;
    LogLevelW(2u, L"Allocation of hash object failed. Error code: 0x%08x", 2147942414LL);
    goto LABEL_28;
  }
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v24, 4u, &pcbResult, 0);
  v8 = Property;
  if ( Property )
  {
LABEL_7:
    v9 = WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(Property);
    v10 = L"BCryptGetProperty failed. Error code: 0x%08x";
    goto LABEL_3;
  }
  v5 = (UCHAR *)WaasMedic::SafeAlloc((WaasMedic *)*(unsigned int *)v24, v16, v17);
  if ( !v5 )
  {
    v11 = -2147024882;
    LogLevelW(2u, L"Allocation of byte array for hash failed. Error code: 0x%08x", 2147942414LL);
    goto LABEL_28;
  }
  v18 = BCryptCreateHash(phAlgorithm, &phHash, v4, *(ULONG *)pbOutput, 0, 0, 0);
  v8 = v18;
  if ( v18
    || (pbInput[3] <= 7u ? (v19 = (UCHAR *)pbInput) : (v19 = (UCHAR *)*pbInput),
        (v18 = BCryptHashData(phHash, v19, 2 * *((_DWORD *)pbInput + 4), 0), (v8 = v18) != 0)
     || (v18 = BCryptFinishHash(phHash, v5, *(ULONG *)v24, 0), (v8 = v18) != 0)) )
  {
    v9 = WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(v18);
    v10 = L"BCryptCreateHash failed. Error code: 0x%08x";
    goto LABEL_3;
  }
  v6 = (unsigned __int16 *)WaasMedic::SafeAlloc((WaasMedic *)(2LL * (unsigned int)(2 * *(_DWORD *)v24 + 1)), v20, v21);
  if ( !v6 )
  {
    v11 = -2147024882;
    LogLevelW(2u, L"Allocation of string failed. Error code: 0x%08x", 2147942414LL);
    goto LABEL_28;
  }
  v11 = 0;
  if ( *(_DWORD *)v24 )
  {
    while ( 1 )
    {
      v9 = StringCchPrintfW(&v6[2 * v3], 3u, L"%02x", v5[v3]);
      v11 = v9;
      if ( v9 < 0 )
        break;
      if ( ++v3 >= (unsigned __int64)*(unsigned int *)v24 )
        goto LABEL_25;
    }
    v10 = L"Failed to write bytes to the allocated string. Error code: 0x%08x";
    goto LABEL_4;
  }
LABEL_25:
  memset(v32, 0, sizeof(v32));
  v22 = -1;
  do
    ++v22;
  while ( v6[v22] );
  std::wstring::_Construct<1,unsigned short const *>((char **)v32, v6, v22);
  std::wstring::operator=(v29, v32);
  std::wstring::~wstring((char **)v32);
LABEL_28:
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v4 )
    WaasMedic::SafeFree((WaasMedic *)v4, v12);
  if ( v5 )
    WaasMedic::SafeFree((WaasMedic *)v5, v12);
  if ( v6 )
    WaasMedic::SafeFree((WaasMedic *)v6, v12);
  if ( v8 < 0 )
    v11 = WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(v8);
  std::wstring::~wstring((char **)pbInput);
  return v11;
}

```

## disassembly

```asm
0x14000f3ec  mov     rax, rsp
0x14000f3ef  push    rbp
0x14000f3f0  push    rsi
0x14000f3f1  push    rdi
0x14000f3f2  push    r12
0x14000f3f4  push    r13
0x14000f3f6  push    r14
0x14000f3f8  push    r15
0x14000f3fa  lea     rbp, [rax-5Fh]
0x14000f3fe  sub     rsp, 0A0h
0x14000f405  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x14000f40d  mov     [rax+18h], rbx
0x14000f411  mov     rax, cs:__security_cookie
0x14000f418  xor     rax, rsp
0x14000f41b  mov     [rbp+57h+var_38], rax
0x14000f41f  mov     [rbp+57h+var_70], rdx
0x14000f423  mov     r14, rcx
0x14000f426  mov     [rbp+57h+var_60], rcx
0x14000f42a  xor     esi, esi
0x14000f42c  mov     [rbp+57h+phAlgorithm], rsi
0x14000f430  mov     [rbp+57h+phHash], rsi
0x14000f434  mov     dword ptr [rbp+57h+pbOutput], esi
0x14000f437  mov     r13d, esi
0x14000f43a  mov     r12d, esi
0x14000f43d  mov     dword ptr [rbp+57h+var_90], esi
0x14000f440  mov     [rbp+57h+var_88], esi
0x14000f443  mov     r15d, esi
0x14000f446  xor     r9d, r9d; dwFlags
0x14000f449  xor     r8d, r8d; pszImplementation
0x14000f44c  lea     rdx, pszAlgId; "SHA256"
0x14000f453  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x14000f457  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14000f45d  mov     edi, eax
0x14000f45f  test    eax, eax
0x14000f461  jz      short loc_14000F485
0x14000f463  mov     ecx, eax; int
0x14000f465  call    ?HRESULT_FROM_NTSTATUS@MiscUtil@WaasMedic@@SAJJ@Z; WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(long)
0x14000f46a  lea     rdx, aBcryptopenalgo; "BCryptOpenAlgorithmProvider failed. Err"...
0x14000f471  mov     ebx, eax
0x14000f473  mov     r8d, eax
0x14000f476  mov     ecx, 2; unsigned __int8
0x14000f47b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000f480  jmp     loc_14000F65B
0x14000f485  mov     [rsp+0D0h+dwFlags], esi; dwFlags
0x14000f489  lea     rax, [rbp+57h+var_88]
0x14000f48d  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x14000f492  mov     ebx, 4
0x14000f497  mov     r9d, ebx; cbOutput
0x14000f49a  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x14000f49e  lea     rdx, pszProperty; "ObjectLength"
0x14000f4a5  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x14000f4a9  call    cs:__imp_BCryptGetProperty
0x14000f4af  mov     edi, eax
0x14000f4b1  test    eax, eax
0x14000f4b3  jz      short loc_14000F4C5
0x14000f4b5  mov     ecx, eax; int
0x14000f4b7  call    ?HRESULT_FROM_NTSTATUS@MiscUtil@WaasMedic@@SAJJ@Z; WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(long)
0x14000f4bc  lea     rdx, aBcryptgetprope; "BCryptGetProperty failed. Error code: 0"...
0x14000f4c3  jmp     short loc_14000F471
0x14000f4c5  mov     ecx, dword ptr [rbp+57h+pbOutput]; this
0x14000f4c8  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x14000f4cd  mov     r13, rax
0x14000f4d0  test    rax, rax
0x14000f4d3  jnz     short loc_14000F4E7
0x14000f4d5  mov     r8d, 8007000Eh
0x14000f4db  mov     ebx, r8d
0x14000f4de  lea     rdx, aAllocationOfHa; "Allocation of hash object failed. Error"...
0x14000f4e5  jmp     short loc_14000F476
0x14000f4e7  mov     [rsp+0D0h+dwFlags], esi; dwFlags
0x14000f4eb  lea     rax, [rbp+57h+var_88]
0x14000f4ef  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x14000f4f4  mov     r9d, ebx; cbOutput
0x14000f4f7  lea     r8, [rbp+57h+var_90]; pbOutput
0x14000f4fb  lea     rdx, aHashdigestleng; "HashDigestLength"
0x14000f502  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x14000f506  call    cs:__imp_BCryptGetProperty
0x14000f50c  mov     edi, eax
0x14000f50e  test    eax, eax
0x14000f510  jnz     short loc_14000F4B5
0x14000f512  mov     ecx, dword ptr [rbp+57h+var_90]; this
0x14000f515  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x14000f51a  mov     r12, rax
0x14000f51d  test    rax, rax
0x14000f520  jnz     short loc_14000F537
0x14000f522  mov     r8d, 8007000Eh
0x14000f528  mov     ebx, r8d
0x14000f52b  lea     rdx, aAllocationOfBy; "Allocation of byte array for hash faile"...
0x14000f532  jmp     loc_14000F476
0x14000f537  mov     [rsp+30h], esi; dwFlags
0x14000f53b  mov     [rsp+0D0h+dwFlags], esi; cbSecret
0x14000f53f  mov     [rsp+0D0h+pcbResult], rsi; pbSecret
0x14000f544  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x14000f548  mov     r8, r13; pbHashObject
0x14000f54b  lea     rdx, [rbp+57h+phHash]; phHash
0x14000f54f  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x14000f553  call    cs:__imp_BCryptCreateHash
0x14000f559  mov     edi, eax
0x14000f55b  test    eax, eax
0x14000f55d  jz      short loc_14000F572
0x14000f55f  mov     ecx, eax; int
0x14000f561  call    ?HRESULT_FROM_NTSTATUS@MiscUtil@WaasMedic@@SAJJ@Z; WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(long)
0x14000f566  lea     rdx, aBcryptcreateha; "BCryptCreateHash failed. Error code: 0x"...
0x14000f56d  jmp     loc_14000F471
0x14000f572  mov     r8d, [r14+10h]
0x14000f576  add     r8d, r8d; cbInput
0x14000f579  cmp     qword ptr [r14+18h], 7
0x14000f57e  jbe     short loc_14000F585
0x14000f580  mov     rdx, [r14]
0x14000f583  jmp     short loc_14000F588
0x14000f585  mov     rdx, r14; pbInput
0x14000f588  xor     r9d, r9d; dwFlags
0x14000f58b  mov     rcx, [rbp+57h+phHash]; hHash
0x14000f58f  call    cs:__imp_BCryptHashData
0x14000f595  mov     edi, eax
0x14000f597  test    eax, eax
0x14000f599  jnz     short loc_14000F55F
0x14000f59b  xor     r9d, r9d; dwFlags
0x14000f59e  mov     r8d, dword ptr [rbp+57h+var_90]; cbOutput
0x14000f5a2  mov     rdx, r12; pbOutput
0x14000f5a5  mov     rcx, [rbp+57h+phHash]; hHash
0x14000f5a9  call    cs:__imp_BCryptFinishHash
0x14000f5af  mov     edi, eax
0x14000f5b1  test    eax, eax
0x14000f5b3  jnz     short loc_14000F55F
0x14000f5b5  mov     eax, dword ptr [rbp+57h+var_90]
0x14000f5b8  lea     ecx, ds:1[rax*2]
0x14000f5bf  add     rcx, rcx; this
0x14000f5c2  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x14000f5c7  mov     r15, rax
0x14000f5ca  test    rax, rax
0x14000f5cd  jnz     short loc_14000F5E4
0x14000f5cf  mov     r8d, 8007000Eh
0x14000f5d5  mov     ebx, r8d
0x14000f5d8  lea     rdx, aAllocationOfSt; "Allocation of string failed. Error code"...
0x14000f5df  jmp     loc_14000F476
0x14000f5e4  mov     ebx, esi
0x14000f5e6  cmp     dword ptr [rbp+57h+var_90], esi
0x14000f5e9  jbe     short loc_14000F61A
0x14000f5eb  movzx   r9d, byte ptr [r12+rsi]
0x14000f5f0  lea     rcx, [r15+rsi*4]; unsigned __int16 *
0x14000f5f4  lea     r8, a02x; "%02x"
0x14000f5fb  mov     edx, 3; unsigned __int64
0x14000f600  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000f605  mov     ebx, eax
0x14000f607  test    eax, eax
0x14000f609  js      loc_14000F6E0
0x14000f60f  inc     rsi
0x14000f612  mov     eax, dword ptr [rbp+57h+var_90]
0x14000f615  cmp     rsi, rax
0x14000f618  jb      short loc_14000F5EB
0x14000f61a  xorps   xmm0, xmm0
0x14000f61d  movups  [rbp+57h+var_58], xmm0
0x14000f621  xorps   xmm1, xmm1
0x14000f624  movdqu  [rbp+57h+var_48], xmm1
0x14000f629  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000f62d  xor     esi, esi
0x14000f62f  inc     r8
0x14000f632  cmp     [r15+r8*2], si
0x14000f637  jnz     short loc_14000F62F
0x14000f639  mov     rdx, r15
0x14000f63c  lea     rcx, [rbp+57h+var_58]
0x14000f640  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000f645  lea     rdx, [rbp+57h+var_58]
0x14000f649  mov     rcx, [rbp+57h+var_70]
0x14000f64d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000f652  lea     rcx, [rbp+57h+var_58]; void *
0x14000f656  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f65b  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x14000f65f  test    rcx, rcx
0x14000f662  jz      short loc_14000F66C
0x14000f664  xor     edx, edx; dwFlags
0x14000f666  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000f66c  mov     rcx, [rbp+57h+phHash]; hHash
0x14000f670  test    rcx, rcx
0x14000f673  jz      short loc_14000F67B
0x14000f675  call    cs:__imp_BCryptDestroyHash
0x14000f67b  test    r13, r13
0x14000f67e  jz      short loc_14000F688
0x14000f680  mov     rcx, r13; this
0x14000f683  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x14000f688  test    r12, r12
0x14000f68b  jz      short loc_14000F695
0x14000f68d  mov     rcx, r12; this
0x14000f690  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x14000f695  test    r15, r15
0x14000f698  jz      short loc_14000F6A2
0x14000f69a  mov     rcx, r15; this
0x14000f69d  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x14000f6a2  test    edi, edi
0x14000f6a4  jns     short loc_14000F6AF
0x14000f6a6  mov     ecx, edi; int
0x14000f6a8  call    ?HRESULT_FROM_NTSTATUS@MiscUtil@WaasMedic@@SAJJ@Z; WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(long)
0x14000f6ad  mov     ebx, eax
0x14000f6af  mov     rcx, r14; void *
0x14000f6b2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f6b7  mov     eax, ebx
0x14000f6b9  mov     rcx, [rbp+57h+var_38]
0x14000f6bd  xor     rcx, rsp; StackCookie
0x14000f6c0  call    __security_check_cookie
0x14000f6c5  mov     rbx, [rsp+0D0h+arg_10]
0x14000f6cd  add     rsp, 0A0h
0x14000f6d4  pop     r15
0x14000f6d6  pop     r14
0x14000f6d8  pop     r13
0x14000f6da  pop     r12
0x14000f6dc  pop     rdi
0x14000f6dd  pop     rsi
0x14000f6de  pop     rbp
0x14000f6df  retn
0x14000f6e0  lea     rdx, aFailedToWriteB; "Failed to write bytes to the allocated "...
0x14000f6e7  jmp     loc_14000F473
```
