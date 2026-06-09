# VBSAttestationBuildRootClaimHashBuffer

- ea: `0x1400377b8`
- end: `0x140037a16`
- name: `VBSAttestationBuildRootClaimHashBuffer`
- size: `606`
- prototype: `__int64 __usercall@<rax>(BCRYPT_HANDLE hObject@<rcx>, PUCHAR, ULONG cbInput, PUCHAR pbInput)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140012864`

## callees

- `0x140037264`
- `0x1400377b8`
- `0x1400385f0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x140037956`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x140037956`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400379e5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400379e5`
- `bcrypt!BCryptFinishHash` at `0x140037987`
- `bcrypt!BCryptFinishHash` at `0x140037987`
- `bcrypt!BCryptDestroyHash` at `0x1400379f5`
- `bcrypt!BCryptDestroyHash` at `0x1400379f5`
- `bcrypt!BCryptHashData` at `0x1400378a7`
- `bcrypt!BCryptHashData` at `0x1400378cd`
- `bcrypt!BCryptHashData` at `0x1400378f3`
- `bcrypt!BCryptHashData` at `0x1400378a7`
- `bcrypt!BCryptHashData` at `0x1400378cd`
- `bcrypt!BCryptHashData` at `0x1400378f3`
- `bcrypt!BCryptCreateHash` at `0x140037816`
- `bcrypt!BCryptCreateHash` at `0x140037816`
- `bcrypt!BCryptGetProperty` at `0x14003792c`
- `bcrypt!BCryptGetProperty` at `0x14003792c`

## string_xrefs

- `0x14003782a`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\vbsattesthelper.cxx`
- `0x1400379ca`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\vbsattesthelper.cxx`

## pseudocode

```c
__int64 __fastcall VBSAttestationBuildRootClaimHashBuffer(
        BCRYPT_HANDLE hObject,
        UCHAR **a2,
        UCHAR *a3,
        __int64 a4,
        PUCHAR a5,
        ULONG cbInput,
        PUCHAR pbInput)
{
  PUCHAR v10; // rdi
  NTSTATUS Property; // eax
  unsigned int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  UCHAR *v15; // rax
  UCHAR *v16; // rdi
  NTSTATUS v17; // eax
  __int64 v18; // rcx
  __int64 v19; // r9
  BCRYPT_HASH_HANDLE hHash; // [rsp+60h] [rbp-38h] BYREF
  ULONG pcbResult; // [rsp+B0h] [rbp+18h] BYREF

  hHash = 0;
  pcbResult = 0;
  if ( a3 && (v10 = pbInput) != 0 )
  {
    Property = BCryptCreateHash(hObject, &hHash, 0, 0, 0, 0, 0);
    v12 = Property;
    if ( Property < 0 )
    {
      v13 = 297;
LABEL_5:
      v14 = (unsigned int)Property;
LABEL_6:
      DebugTraceError(
        v14,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\vbsattesthelper.cxx",
        v13);
      goto LABEL_28;
    }
    Property = VBSAttestationHashClaimGeneralParams(hHash, a5, cbInput, 0, 0, 0, 0, 0);
    v12 = Property;
    if ( Property < 0 )
    {
      v13 = 315;
      goto LABEL_5;
    }
    Property = BCryptHashData(hHash, v10, 4u, 0);
    v12 = Property;
    if ( Property < 0 )
    {
      v13 = 326;
      goto LABEL_5;
    }
    Property = BCryptHashData(hHash, v10 + 4, 4u, 0);
    v12 = Property;
    if ( Property < 0 )
    {
      v13 = 337;
      goto LABEL_5;
    }
    Property = BCryptHashData(hHash, v10 + 16, 4u, 0);
    v12 = Property;
    if ( Property < 0 )
    {
      v13 = 349;
      goto LABEL_5;
    }
    Property = BCryptGetProperty(hObject, L"HashDigestLength", a3, 4u, &pcbResult, 0);
    v12 = Property;
    if ( Property < 0 )
    {
      v13 = 363;
      goto LABEL_5;
    }
    if ( !pcbResult || !*(_DWORD *)a3 )
    {
      v12 = -1073741595;
      v13 = 371;
      v14 = 3221225701LL;
      goto LABEL_6;
    }
    v15 = (UCHAR *)LocalAlloc(0, *(unsigned int *)a3);
    v16 = v15;
    if ( !v15 )
    {
      v12 = -1073741801;
      v13 = 380;
      v14 = 3221225495LL;
      goto LABEL_6;
    }
    v17 = BCryptFinishHash(hHash, v15, *(_DWORD *)a3, 0);
    v12 = v17;
    if ( v17 >= 0 )
    {
      *a2 = v16;
      goto LABEL_28;
    }
    v18 = (unsigned int)v17;
    v19 = 392;
  }
  else
  {
    v16 = 0;
    v12 = -1073741595;
    v18 = 3221225701LL;
    v19 = 282;
  }
  DebugTraceError(
    v18,
    "Status",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\vbsattesthelper.cxx",
    v19);
  if ( v16 )
    LocalFree(v16);
LABEL_28:
  if ( hHash )
    BCryptDestroyHash(hHash);
  return v12;
}

```

## disassembly

```asm
0x1400377b8  mov     rax, rsp
0x1400377bb  mov     [rax+8], rbx
0x1400377bf  mov     [rax+10h], rbp
0x1400377c3  push    rsi
0x1400377c4  push    rdi
0x1400377c5  push    r12
0x1400377c7  push    r14
0x1400377c9  push    r15
0x1400377cb  sub     rsp, 70h
0x1400377cf  xor     r12d, r12d
0x1400377d2  mov     r14, r9
0x1400377d5  mov     [rax-38h], r12
0x1400377d9  mov     rsi, r8
0x1400377dc  mov     [rax+18h], r12d
0x1400377e0  mov     r15, rdx
0x1400377e3  mov     rbp, rcx
0x1400377e6  test    r8, r8
0x1400377e9  jz      loc_1400379B7
0x1400377ef  mov     rdi, [rsp+98h+pbInput]
0x1400377f7  test    rdi, rdi
0x1400377fa  jz      loc_1400379B7
0x140037800  mov     [rax-68h], r12d
0x140037804  lea     rdx, [rax-38h]; phHash
0x140037808  mov     [rax-70h], r12d
0x14003780c  xor     r9d, r9d; cbHashObject
0x14003780f  xor     r8d, r8d; pbHashObject
0x140037812  mov     [rax-78h], r12
0x140037816  call    cs:__imp_BCryptCreateHash
0x14003781c  mov     ebx, eax
0x14003781e  test    eax, eax
0x140037820  jns     short loc_140037842
0x140037822  mov     r9d, 129h
0x140037828  mov     ecx, eax
0x14003782a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140037831  lea     rdx, aStatus; "Status"
0x140037838  call    DebugTraceError
0x14003783d  jmp     loc_1400379EB
0x140037842  mov     eax, [rsp+98h+cbInput]
0x140037849  mov     r8, r14
0x14003784c  mov     r9d, [rdi+8]
0x140037850  mov     edx, [rdi+14h]
0x140037853  mov     rcx, [rsp+98h+hHash]; hHash
0x140037858  mov     [rsp+98h+var_48], r12; PUCHAR
0x14003785d  mov     [rsp+98h+var_50], r12d; ULONG
0x140037862  mov     [rsp+98h+var_58], r12; PUCHAR
0x140037867  mov     [rsp+98h+var_60], r12d; ULONG
0x14003786c  mov     [rsp+98h+var_68], r12; PUCHAR
0x140037871  mov     [rsp+98h+dwFlags], eax; cbInput
0x140037875  mov     rax, [rsp+98h+arg_20]
0x14003787d  mov     [rsp+98h+pcbResult], rax; PUCHAR
0x140037882  call    VBSAttestationHashClaimGeneralParams
0x140037887  mov     ebx, eax
0x140037889  test    eax, eax
0x14003788b  jns     short loc_140037895
0x14003788d  mov     r9d, 13Bh
0x140037893  jmp     short loc_140037828
0x140037895  mov     rcx, [rsp+98h+hHash]; hHash
0x14003789a  xor     r9d, r9d; dwFlags
0x14003789d  mov     rdx, rdi; pbInput
0x1400378a0  lea     r14d, [r9+4]
0x1400378a4  mov     r8d, r14d; cbInput
0x1400378a7  call    cs:__imp_BCryptHashData
0x1400378ad  mov     ebx, eax
0x1400378af  test    eax, eax
0x1400378b1  jns     short loc_1400378BE
0x1400378b3  mov     r9d, 146h
0x1400378b9  jmp     loc_140037828
0x1400378be  mov     rcx, [rsp+98h+hHash]; hHash
0x1400378c3  lea     rdx, [rdi+4]; pbInput
0x1400378c7  xor     r9d, r9d; dwFlags
0x1400378ca  mov     r8d, r14d; cbInput
0x1400378cd  call    cs:__imp_BCryptHashData
0x1400378d3  mov     ebx, eax
0x1400378d5  test    eax, eax
0x1400378d7  jns     short loc_1400378E4
0x1400378d9  mov     r9d, 151h
0x1400378df  jmp     loc_140037828
0x1400378e4  mov     rcx, [rsp+98h+hHash]; hHash
0x1400378e9  lea     rdx, [rdi+10h]; pbInput
0x1400378ed  xor     r9d, r9d; dwFlags
0x1400378f0  mov     r8d, r14d; cbInput
0x1400378f3  call    cs:__imp_BCryptHashData
0x1400378f9  mov     ebx, eax
0x1400378fb  test    eax, eax
0x1400378fd  jns     short loc_14003790A
0x1400378ff  mov     r9d, 15Dh
0x140037905  jmp     loc_140037828
0x14003790a  lea     rax, [rsp+98h+arg_10]
0x140037912  mov     [rsp+98h+dwFlags], r12d; dwFlags
0x140037917  mov     r9d, r14d; cbOutput
0x14003791a  mov     [rsp+98h+pcbResult], rax; pcbResult
0x14003791f  mov     r8, rsi; pbOutput
0x140037922  lea     rdx, aHashdigestleng; "HashDigestLength"
0x140037929  mov     rcx, rbp; hObject
0x14003792c  call    cs:__imp_BCryptGetProperty
0x140037932  mov     ebx, eax
0x140037934  test    eax, eax
0x140037936  jns     short loc_140037943
0x140037938  mov     r9d, 16Bh
0x14003793e  jmp     loc_140037828
0x140037943  cmp     [rsp+98h+arg_10], r12d
0x14003794b  jz      short loc_1400379A2
0x14003794d  cmp     [rsi], r12d
0x140037950  jz      short loc_1400379A2
0x140037952  mov     edx, [rsi]; uBytes
0x140037954  xor     ecx, ecx; uFlags
0x140037956  call    cs:__imp_LocalAlloc
0x14003795c  mov     rdi, rax
0x14003795f  test    rax, rax
0x140037962  jnz     short loc_140037979
0x140037964  mov     ebx, 0C0000017h
0x140037969  mov     r9d, 17Ch
0x14003796f  mov     ecx, 0C0000017h
0x140037974  jmp     loc_14003782A
0x140037979  mov     r8d, [rsi]; cbOutput
0x14003797c  xor     r9d, r9d; dwFlags
0x14003797f  mov     rcx, [rsp+98h+hHash]; hHash
0x140037984  mov     rdx, rdi; pbOutput
0x140037987  call    cs:__imp_BCryptFinishHash
0x14003798d  mov     ebx, eax
0x14003798f  test    eax, eax
0x140037991  jns     short loc_14003799D
0x140037993  mov     ecx, eax
0x140037995  mov     r9d, 188h
0x14003799b  jmp     short loc_1400379CA
0x14003799d  mov     [r15], rdi
0x1400379a0  jmp     short loc_1400379EB
0x1400379a2  mov     ebx, 0C00000E5h
0x1400379a7  mov     r9d, 173h
0x1400379ad  mov     ecx, 0C00000E5h
0x1400379b2  jmp     loc_14003782A
0x1400379b7  mov     rdi, r12
0x1400379ba  mov     ebx, 0C00000E5h
0x1400379bf  mov     ecx, 0C00000E5h
0x1400379c4  mov     r9d, 11Ah
0x1400379ca  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1400379d1  lea     rdx, aStatus; "Status"
0x1400379d8  call    DebugTraceError
0x1400379dd  test    rdi, rdi
0x1400379e0  jz      short loc_1400379EB
0x1400379e2  mov     rcx, rdi; hMem
0x1400379e5  call    cs:__imp_LocalFree
0x1400379eb  mov     rcx, [rsp+98h+hHash]; hHash
0x1400379f0  test    rcx, rcx
0x1400379f3  jz      short loc_1400379FB
0x1400379f5  call    cs:__imp_BCryptDestroyHash
0x1400379fb  lea     r11, [rsp+98h+var_28]
0x140037a00  mov     eax, ebx
0x140037a02  mov     rbx, [r11+30h]
0x140037a06  mov     rbp, [r11+38h]
0x140037a0a  mov     rsp, r11
0x140037a0d  pop     r15
0x140037a0f  pop     r14
0x140037a11  pop     r12
0x140037a13  pop     rdi
0x140037a14  pop     rsi
0x140037a15  retn
```
