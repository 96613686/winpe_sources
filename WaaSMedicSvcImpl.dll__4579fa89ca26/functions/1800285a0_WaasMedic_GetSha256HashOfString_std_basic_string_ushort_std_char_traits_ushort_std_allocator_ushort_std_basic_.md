# WaasMedic::GetSha256HashOfString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800285a0`
- end: `0x180028898`
- name: `?GetSha256HashOfString@WaasMedic@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z`
- size: `760`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18001e83c`

## callees

- `0x1800050a0`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000c638`
- `0x180010db4`
- `0x1800285a0`
- `0x18002a300`
- `0x18002a4e4`
- `0x18002a7b4`
- `0x18002e81c`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x180028754`
- `bcrypt!BCryptFinishHash` at `0x180028754`
- `bcrypt!BCryptCreateHash` at `0x1800286fe`
- `bcrypt!BCryptCreateHash` at `0x1800286fe`
- `bcrypt!BCryptGetProperty` at `0x180028654`
- `bcrypt!BCryptGetProperty` at `0x1800286b1`
- `bcrypt!BCryptGetProperty` at `0x180028654`
- `bcrypt!BCryptGetProperty` at `0x1800286b1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180028811`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180028811`
- `bcrypt!BCryptDestroyHash` at `0x180028820`
- `bcrypt!BCryptDestroyHash` at `0x180028820`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180028602`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180028602`
- `bcrypt!BCryptHashData` at `0x18002873a`
- `bcrypt!BCryptHashData` at `0x18002873a`

## string_xrefs

- `0x180028615`: `BCryptOpenAlgorithmProvider failed. Error code: 0x%08x`
- `0x180028711`: `BCryptCreateHash failed. Error code: 0x%08x`
- `0x18002888b`: `Failed to write bytes to the allocated string. Error code: 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::GetSha256HashOfString(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rsi
  UCHAR *v4; // r13
  UCHAR *v5; // r12
  WaasMedic *v6; // r15
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
  __int64 v22; // r8
  UCHAR v24[4]; // [rsp+40h] [rbp-39h] BYREF
  UCHAR pbOutput[4]; // [rsp+44h] [rbp-35h] BYREF
  ULONG pcbResult; // [rsp+48h] [rbp-31h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-29h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-21h] BYREF
  __int64 v29; // [rsp+60h] [rbp-19h]
  _QWORD *v30; // [rsp+68h] [rbp-11h]
  _OWORD v31[2]; // [rsp+70h] [rbp-9h] BYREF

  v29 = a2;
  v30 = a1;
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
    || (a1[3] <= 7u ? (v19 = (UCHAR *)a1) : (v19 = (UCHAR *)*a1),
        (v18 = BCryptHashData(phHash, v19, 2 * *((_DWORD *)a1 + 4), 0), (v8 = v18) != 0)
     || (v18 = BCryptFinishHash(phHash, v5, *(ULONG *)v24, 0), (v8 = v18) != 0)) )
  {
    v9 = WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(v18);
    v10 = L"BCryptCreateHash failed. Error code: 0x%08x";
    goto LABEL_3;
  }
  v6 = (WaasMedic *)WaasMedic::SafeAlloc((WaasMedic *)(2LL * (unsigned int)(2 * *(_DWORD *)v24 + 1)), v20, v21);
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
      v9 = StringCchPrintfW((unsigned __int16 *)v6 + 2 * v3, 3u, L"%02x", v5[v3]);
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
  memset(v31, 0, sizeof(v31));
  v22 = -1;
  do
    ++v22;
  while ( *((_WORD *)v6 + v22) );
  std::wstring::_Construct<1,unsigned short const *>(v31, v6);
  std::wstring::operator=(v29, v31);
  std::wstring::~wstring(v31);
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
    WaasMedic::SafeFree(v6, v12);
  if ( v8 < 0 )
    v11 = WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(v8);
  std::wstring::~wstring(a1);
  return v11;
}

```

## disassembly

```asm
0x1800285a0  mov     [rsp-8+arg_10], rbx
0x1800285a5  push    rbp
0x1800285a6  push    rsi
0x1800285a7  push    rdi
0x1800285a8  push    r12
0x1800285aa  push    r13
0x1800285ac  push    r14
0x1800285ae  push    r15
0x1800285b0  lea     rbp, [rsp-27h]
0x1800285b5  sub     rsp, 0A0h
0x1800285bc  mov     rax, cs:__security_cookie
0x1800285c3  xor     rax, rsp
0x1800285c6  mov     [rbp+57h+var_40], rax
0x1800285ca  mov     [rbp+57h+var_70], rdx
0x1800285ce  mov     r14, rcx
0x1800285d1  mov     [rbp+57h+var_68], rcx
0x1800285d5  xor     esi, esi
0x1800285d7  mov     [rbp+57h+phAlgorithm], rsi
0x1800285db  mov     [rbp+57h+phHash], rsi
0x1800285df  mov     dword ptr [rbp+57h+pbOutput], esi
0x1800285e2  mov     r13d, esi
0x1800285e5  mov     r12d, esi
0x1800285e8  mov     dword ptr [rbp+57h+var_90], esi
0x1800285eb  mov     [rbp+57h+var_88], esi
0x1800285ee  mov     r15d, esi
0x1800285f1  xor     r9d, r9d; dwFlags
0x1800285f4  xor     r8d, r8d; pszImplementation
0x1800285f7  lea     rdx, aSha256; "SHA256"
0x1800285fe  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x180028602  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180028608  mov     edi, eax
0x18002860a  test    eax, eax
0x18002860c  jz      short loc_180028630
0x18002860e  mov     ecx, eax; int
0x180028610  call    ?HRESULT_FROM_NTSTATUS@MiscUtil@WaasMedic@@SAJJ@Z; WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(long)
0x180028615  lea     rdx, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider failed. Err"...
0x18002861c  mov     ebx, eax
0x18002861e  mov     r8d, eax
0x180028621  mov     ecx, 2; unsigned __int8
0x180028626  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002862b  jmp     loc_180028806
0x180028630  mov     [rsp+0D0h+dwFlags], esi; dwFlags
0x180028634  lea     rax, [rbp+57h+var_88]
0x180028638  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x18002863d  mov     ebx, 4
0x180028642  mov     r9d, ebx; cbOutput
0x180028645  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x180028649  lea     rdx, pszProperty; "ObjectLength"
0x180028650  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x180028654  call    cs:__imp_BCryptGetProperty
0x18002865a  mov     edi, eax
0x18002865c  test    eax, eax
0x18002865e  jz      short loc_180028670
0x180028660  mov     ecx, eax; int
0x180028662  call    ?HRESULT_FROM_NTSTATUS@MiscUtil@WaasMedic@@SAJJ@Z; WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(long)
0x180028667  lea     rdx, aBcryptgetprope_0; "BCryptGetProperty failed. Error code: 0"...
0x18002866e  jmp     short loc_18002861C
0x180028670  mov     ecx, dword ptr [rbp+57h+pbOutput]; this
0x180028673  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x180028678  mov     r13, rax
0x18002867b  test    rax, rax
0x18002867e  jnz     short loc_180028692
0x180028680  mov     r8d, 8007000Eh
0x180028686  mov     ebx, r8d
0x180028689  lea     rdx, aAllocationOfHa; "Allocation of hash object failed. Error"...
0x180028690  jmp     short loc_180028621
0x180028692  mov     [rsp+0D0h+dwFlags], esi; dwFlags
0x180028696  lea     rax, [rbp+57h+var_88]
0x18002869a  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x18002869f  mov     r9d, ebx; cbOutput
0x1800286a2  lea     r8, [rbp+57h+var_90]; pbOutput
0x1800286a6  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800286ad  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x1800286b1  call    cs:__imp_BCryptGetProperty
0x1800286b7  mov     edi, eax
0x1800286b9  test    eax, eax
0x1800286bb  jnz     short loc_180028660
0x1800286bd  mov     ecx, dword ptr [rbp+57h+var_90]; this
0x1800286c0  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x1800286c5  mov     r12, rax
0x1800286c8  test    rax, rax
0x1800286cb  jnz     short loc_1800286E2
0x1800286cd  mov     r8d, 8007000Eh
0x1800286d3  mov     ebx, r8d
0x1800286d6  lea     rdx, aAllocationOfBy; "Allocation of byte array for hash faile"...
0x1800286dd  jmp     loc_180028621
0x1800286e2  mov     [rsp+0D0h+var_A0], esi; dwFlags
0x1800286e6  mov     [rsp+0D0h+dwFlags], esi; cbSecret
0x1800286ea  mov     [rsp+0D0h+pcbResult], rsi; pbSecret
0x1800286ef  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x1800286f3  mov     r8, r13; pbHashObject
0x1800286f6  lea     rdx, [rbp+57h+phHash]; phHash
0x1800286fa  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800286fe  call    cs:__imp_BCryptCreateHash
0x180028704  mov     edi, eax
0x180028706  test    eax, eax
0x180028708  jz      short loc_18002871D
0x18002870a  mov     ecx, eax; int
0x18002870c  call    ?HRESULT_FROM_NTSTATUS@MiscUtil@WaasMedic@@SAJJ@Z; WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(long)
0x180028711  lea     rdx, aBcryptcreateha_0; "BCryptCreateHash failed. Error code: 0x"...
0x180028718  jmp     loc_18002861C
0x18002871d  mov     r8d, [r14+10h]
0x180028721  add     r8d, r8d; cbInput
0x180028724  cmp     qword ptr [r14+18h], 7
0x180028729  jbe     short loc_180028730
0x18002872b  mov     rdx, [r14]
0x18002872e  jmp     short loc_180028733
0x180028730  mov     rdx, r14; pbInput
0x180028733  xor     r9d, r9d; dwFlags
0x180028736  mov     rcx, [rbp+57h+phHash]; hHash
0x18002873a  call    cs:__imp_BCryptHashData
0x180028740  mov     edi, eax
0x180028742  test    eax, eax
0x180028744  jnz     short loc_18002870A
0x180028746  xor     r9d, r9d; dwFlags
0x180028749  mov     r8d, dword ptr [rbp+57h+var_90]; cbOutput
0x18002874d  mov     rdx, r12; pbOutput
0x180028750  mov     rcx, [rbp+57h+phHash]; hHash
0x180028754  call    cs:__imp_BCryptFinishHash
0x18002875a  mov     edi, eax
0x18002875c  test    eax, eax
0x18002875e  jnz     short loc_18002870A
0x180028760  mov     eax, dword ptr [rbp+57h+var_90]
0x180028763  lea     ecx, ds:1[rax*2]
0x18002876a  add     rcx, rcx; this
0x18002876d  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x180028772  mov     r15, rax
0x180028775  test    rax, rax
0x180028778  jnz     short loc_18002878F
0x18002877a  mov     r8d, 8007000Eh
0x180028780  mov     ebx, r8d
0x180028783  lea     rdx, aAllocationOfSt; "Allocation of string failed. Error code"...
0x18002878a  jmp     loc_180028621
0x18002878f  mov     ebx, esi
0x180028791  cmp     dword ptr [rbp+57h+var_90], esi
0x180028794  jbe     short loc_1800287C5
0x180028796  movzx   r9d, byte ptr [r12+rsi]
0x18002879b  lea     rcx, [r15+rsi*4]; unsigned __int16 *
0x18002879f  lea     r8, a02x; "%02x"
0x1800287a6  mov     edx, 3; unsigned __int64
0x1800287ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800287b0  mov     ebx, eax
0x1800287b2  test    eax, eax
0x1800287b4  js      loc_18002888B
0x1800287ba  inc     rsi
0x1800287bd  mov     eax, dword ptr [rbp+57h+var_90]
0x1800287c0  cmp     rsi, rax
0x1800287c3  jb      short loc_180028796
0x1800287c5  xorps   xmm0, xmm0
0x1800287c8  movups  [rbp+57h+var_60], xmm0
0x1800287cc  xorps   xmm1, xmm1
0x1800287cf  movdqu  [rbp+57h+var_50], xmm1
0x1800287d4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800287d8  xor     esi, esi
0x1800287da  inc     r8
0x1800287dd  cmp     [r15+r8*2], si
0x1800287e2  jnz     short loc_1800287DA
0x1800287e4  mov     rdx, r15
0x1800287e7  lea     rcx, [rbp+57h+var_60]
0x1800287eb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800287f0  lea     rdx, [rbp+57h+var_60]
0x1800287f4  mov     rcx, [rbp+57h+var_70]
0x1800287f8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800287fd  lea     rcx, [rbp+57h+var_60]; void *
0x180028801  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028806  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x18002880a  test    rcx, rcx
0x18002880d  jz      short loc_180028817
0x18002880f  xor     edx, edx; dwFlags
0x180028811  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180028817  mov     rcx, [rbp+57h+phHash]; hHash
0x18002881b  test    rcx, rcx
0x18002881e  jz      short loc_180028826
0x180028820  call    cs:__imp_BCryptDestroyHash
0x180028826  test    r13, r13
0x180028829  jz      short loc_180028833
0x18002882b  mov     rcx, r13; this
0x18002882e  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x180028833  test    r12, r12
0x180028836  jz      short loc_180028840
0x180028838  mov     rcx, r12; this
0x18002883b  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x180028840  test    r15, r15
0x180028843  jz      short loc_18002884D
0x180028845  mov     rcx, r15; this
0x180028848  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18002884d  test    edi, edi
0x18002884f  jns     short loc_18002885A
0x180028851  mov     ecx, edi; int
0x180028853  call    ?HRESULT_FROM_NTSTATUS@MiscUtil@WaasMedic@@SAJJ@Z; WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(long)
0x180028858  mov     ebx, eax
0x18002885a  mov     rcx, r14; void *
0x18002885d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028862  mov     eax, ebx
0x180028864  mov     rcx, [rbp+57h+var_40]
0x180028868  xor     rcx, rsp; StackCookie
0x18002886b  call    __security_check_cookie
0x180028870  mov     rbx, [rsp+0D0h+arg_10]
0x180028878  add     rsp, 0A0h
0x18002887f  pop     r15
0x180028881  pop     r14
0x180028883  pop     r13
0x180028885  pop     r12
0x180028887  pop     rdi
0x180028888  pop     rsi
0x180028889  pop     rbp
0x18002888a  retn
0x18002888b  lea     rdx, aFailedToWriteB; "Failed to write bytes to the allocated "...
0x180028892  jmp     loc_18002861E
```
