# VBSAttestationBuildIdentityClaimHashBuffer

- ea: `0x14003753c`
- end: `0x1400377b2`
- name: `VBSAttestationBuildIdentityClaimHashBuffer`
- size: `630`
- prototype: `__int64 __usercall@<rax>(BCRYPT_HANDLE hObject@<rcx>, PUCHAR, PUCHAR, PUCHAR, PUCHAR, PUCHAR pbInput)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001260c`

## callees

- `0x140037264`
- `0x14003753c`
- `0x1400385f0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1400376fd`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1400376fd`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14003778a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14003778a`
- `bcrypt!BCryptFinishHash` at `0x14003772d`
- `bcrypt!BCryptFinishHash` at `0x14003772d`
- `bcrypt!BCryptDestroyHash` at `0x140037799`
- `bcrypt!BCryptDestroyHash` at `0x140037799`
- `bcrypt!BCryptHashData` at `0x140037633`
- `bcrypt!BCryptHashData` at `0x140037658`
- `bcrypt!BCryptHashData` at `0x14003767d`
- `bcrypt!BCryptHashData` at `0x1400376a2`
- `bcrypt!BCryptHashData` at `0x140037633`
- `bcrypt!BCryptHashData` at `0x140037658`
- `bcrypt!BCryptHashData` at `0x14003767d`
- `bcrypt!BCryptHashData` at `0x1400376a2`
- `bcrypt!BCryptCreateHash` at `0x140037599`
- `bcrypt!BCryptCreateHash` at `0x140037599`
- `bcrypt!BCryptGetProperty` at `0x1400376d7`
- `bcrypt!BCryptGetProperty` at `0x1400376d7`

## string_xrefs

- `0x1400375ad`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\vbsattesthelper.cxx`
- `0x14003776f`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\vbsattesthelper.cxx`

## pseudocode

```c
__int64 __fastcall VBSAttestationBuildIdentityClaimHashBuffer(
        BCRYPT_HANDLE hObject,
        UCHAR **a2,
        UCHAR *a3,
        __int64 a4,
        PUCHAR a5,
        PUCHAR a6,
        PUCHAR a7,
        PUCHAR a8,
        PUCHAR pbInput)
{
  PUCHAR v12; // rdi
  NTSTATUS Property; // eax
  unsigned int v14; // ebx
  __int64 v15; // r9
  __int64 v16; // rcx
  UCHAR *v17; // rax
  UCHAR *v18; // rdi
  NTSTATUS v19; // eax
  __int64 v20; // rcx
  __int64 v21; // r9
  BCRYPT_HASH_HANDLE phHash; // [rsp+60h] [rbp-18h] BYREF
  ULONG pcbResult; // [rsp+D0h] [rbp+58h] BYREF

  phHash = 0;
  pcbResult = 0;
  if ( a3 && (v12 = pbInput) != 0 )
  {
    Property = BCryptCreateHash(hObject, &phHash, 0, 0, 0, 0, 0);
    v14 = Property;
    if ( Property < 0 )
    {
      v15 = 449;
LABEL_5:
      v16 = (unsigned int)Property;
LABEL_6:
      DebugTraceError(
        v16,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\vbsattesthelper.cxx",
        v15);
      goto LABEL_30;
    }
    Property = VBSAttestationHashClaimGeneralParams(
                 phHash,
                 a5,
                 *((_DWORD *)v12 + 3),
                 a6,
                 *((_DWORD *)v12 + 4),
                 a7,
                 *((_DWORD *)v12 + 6),
                 a8);
    v14 = Property;
    if ( Property < 0 )
    {
      v15 = 467;
      goto LABEL_5;
    }
    Property = BCryptHashData(phHash, v12, 4u, 0);
    v14 = Property;
    if ( Property < 0 )
    {
      v15 = 478;
      goto LABEL_5;
    }
    Property = BCryptHashData(phHash, v12 + 4, 4u, 0);
    v14 = Property;
    if ( Property < 0 )
    {
      v15 = 489;
      goto LABEL_5;
    }
    Property = BCryptHashData(phHash, v12 + 16, 4u, 0);
    v14 = Property;
    if ( Property < 0 )
    {
      v15 = 500;
      goto LABEL_5;
    }
    Property = BCryptHashData(phHash, v12 + 20, 4u, 0);
    v14 = Property;
    if ( Property < 0 )
    {
      v15 = 511;
      goto LABEL_5;
    }
    Property = BCryptGetProperty(hObject, L"HashDigestLength", a3, 4u, &pcbResult, 0);
    v14 = Property;
    if ( Property < 0 )
    {
      v15 = 525;
      goto LABEL_5;
    }
    if ( !pcbResult || !*(_DWORD *)a3 )
    {
      v14 = -1073741595;
      v15 = 533;
      v16 = 3221225701LL;
      goto LABEL_6;
    }
    v17 = (UCHAR *)LocalAlloc(0, *(unsigned int *)a3);
    v18 = v17;
    if ( !v17 )
    {
      v14 = -1073741801;
      v15 = 542;
      v16 = 3221225495LL;
      goto LABEL_6;
    }
    v19 = BCryptFinishHash(phHash, v17, *(_DWORD *)a3, 0);
    v14 = v19;
    if ( v19 >= 0 )
    {
      *a2 = v18;
      goto LABEL_30;
    }
    v20 = (unsigned int)v19;
    v21 = 554;
  }
  else
  {
    v18 = 0;
    v14 = -1073741595;
    v20 = 3221225701LL;
    v21 = 434;
  }
  DebugTraceError(
    v20,
    "Status",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\vbsattesthelper.cxx",
    v21);
  if ( v18 )
    LocalFree(v18);
LABEL_30:
  if ( phHash )
    BCryptDestroyHash(phHash);
  return v14;
}

```

## disassembly

```asm
0x14003753c  push    rbp
0x14003753e  push    rbx
0x14003753f  push    rsi
0x140037540  push    rdi
0x140037541  push    r12
0x140037543  push    r13
0x140037545  push    r14
0x140037547  push    r15
0x140037549  mov     rbp, rsp
0x14003754c  sub     rsp, 78h
0x140037550  xor     r13d, r13d
0x140037553  mov     r12, r9
0x140037556  mov     [rbp+phHash], r13
0x14003755a  mov     rsi, r8
0x14003755d  mov     [rbp+pcbResult], r13d
0x140037561  mov     r15, rdx
0x140037564  mov     r14, rcx
0x140037567  test    r8, r8
0x14003756a  jz      loc_14003775D
0x140037570  mov     rdi, [rbp+pbInput]
0x140037577  test    rdi, rdi
0x14003757a  jz      loc_14003775D
0x140037580  mov     [rsp+78h+dwFlags], r13d; dwFlags
0x140037585  lea     rdx, [rbp+phHash]; phHash
0x140037589  mov     [rsp+78h+cbSecret], r13d; cbSecret
0x14003758e  xor     r9d, r9d; cbHashObject
0x140037591  xor     r8d, r8d; pbHashObject
0x140037594  mov     [rsp+78h+pbSecret], r13; pbSecret
0x140037599  call    cs:__imp_BCryptCreateHash
0x14003759f  mov     ebx, eax
0x1400375a1  test    eax, eax
0x1400375a3  jns     short loc_1400375C5
0x1400375a5  mov     r9d, 1C1h
0x1400375ab  mov     ecx, eax
0x1400375ad  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1400375b4  lea     rdx, aStatus; "Status"
0x1400375bb  call    DebugTraceError
0x1400375c0  jmp     loc_140037790
0x1400375c5  mov     rax, [rbp+arg_38]
0x1400375cc  mov     r8, r12
0x1400375cf  mov     r9d, [rdi+8]
0x1400375d3  mov     edx, [rdi+1Ch]
0x1400375d6  mov     rcx, [rbp+phHash]; hHash
0x1400375da  mov     [rsp+78h+var_28], rax; PUCHAR
0x1400375df  mov     eax, [rdi+18h]
0x1400375e2  mov     [rsp+78h+var_30], eax; ULONG
0x1400375e6  mov     rax, [rbp+arg_30]
0x1400375ea  mov     [rsp+78h+var_38], rax; PUCHAR
0x1400375ef  mov     eax, [rdi+10h]
0x1400375f2  mov     [rsp+78h+var_40], eax; ULONG
0x1400375f6  mov     rax, [rbp+arg_28]
0x1400375fa  mov     qword ptr [rsp+78h+dwFlags], rax; PUCHAR
0x1400375ff  mov     eax, [rdi+0Ch]
0x140037602  mov     [rsp+78h+cbSecret], eax; cbInput
0x140037606  mov     rax, [rbp+arg_20]
0x14003760a  mov     [rsp+78h+pbSecret], rax; PUCHAR
0x14003760f  call    VBSAttestationHashClaimGeneralParams
0x140037614  mov     ebx, eax
0x140037616  test    eax, eax
0x140037618  jns     short loc_140037622
0x14003761a  mov     r9d, 1D3h
0x140037620  jmp     short loc_1400375AB
0x140037622  mov     rcx, [rbp+phHash]; hHash
0x140037626  xor     r9d, r9d; dwFlags
0x140037629  mov     rdx, rdi; pbInput
0x14003762c  lea     r12d, [r9+4]
0x140037630  mov     r8d, r12d; cbInput
0x140037633  call    cs:__imp_BCryptHashData
0x140037639  mov     ebx, eax
0x14003763b  test    eax, eax
0x14003763d  jns     short loc_14003764A
0x14003763f  mov     r9d, 1DEh
0x140037645  jmp     loc_1400375AB
0x14003764a  mov     rcx, [rbp+phHash]; hHash
0x14003764e  lea     rdx, [rdi+4]; pbInput
0x140037652  xor     r9d, r9d; dwFlags
0x140037655  mov     r8d, r12d; cbInput
0x140037658  call    cs:__imp_BCryptHashData
0x14003765e  mov     ebx, eax
0x140037660  test    eax, eax
0x140037662  jns     short loc_14003766F
0x140037664  mov     r9d, 1E9h
0x14003766a  jmp     loc_1400375AB
0x14003766f  mov     rcx, [rbp+phHash]; hHash
0x140037673  lea     rdx, [rdi+10h]; pbInput
0x140037677  xor     r9d, r9d; dwFlags
0x14003767a  mov     r8d, r12d; cbInput
0x14003767d  call    cs:__imp_BCryptHashData
0x140037683  mov     ebx, eax
0x140037685  test    eax, eax
0x140037687  jns     short loc_140037694
0x140037689  mov     r9d, 1F4h
0x14003768f  jmp     loc_1400375AB
0x140037694  mov     rcx, [rbp+phHash]; hHash
0x140037698  lea     rdx, [rdi+14h]; pbInput
0x14003769c  xor     r9d, r9d; dwFlags
0x14003769f  mov     r8d, r12d; cbInput
0x1400376a2  call    cs:__imp_BCryptHashData
0x1400376a8  mov     ebx, eax
0x1400376aa  test    eax, eax
0x1400376ac  jns     short loc_1400376B9
0x1400376ae  mov     r9d, 1FFh
0x1400376b4  jmp     loc_1400375AB
0x1400376b9  lea     rax, [rbp+pcbResult]
0x1400376bd  mov     [rsp+78h+cbSecret], r13d; dwFlags
0x1400376c2  mov     r9d, r12d; cbOutput
0x1400376c5  mov     [rsp+78h+pbSecret], rax; pcbResult
0x1400376ca  mov     r8, rsi; pbOutput
0x1400376cd  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1400376d4  mov     rcx, r14; hObject
0x1400376d7  call    cs:__imp_BCryptGetProperty
0x1400376dd  mov     ebx, eax
0x1400376df  test    eax, eax
0x1400376e1  jns     short loc_1400376EE
0x1400376e3  mov     r9d, 20Dh
0x1400376e9  jmp     loc_1400375AB
0x1400376ee  cmp     [rbp+pcbResult], r13d
0x1400376f2  jz      short loc_140037748
0x1400376f4  cmp     [rsi], r13d
0x1400376f7  jz      short loc_140037748
0x1400376f9  mov     edx, [rsi]; uBytes
0x1400376fb  xor     ecx, ecx; uFlags
0x1400376fd  call    cs:__imp_LocalAlloc
0x140037703  mov     rdi, rax
0x140037706  test    rax, rax
0x140037709  jnz     short loc_140037720
0x14003770b  mov     ebx, 0C0000017h
0x140037710  mov     r9d, 21Eh
0x140037716  mov     ecx, 0C0000017h
0x14003771b  jmp     loc_1400375AD
0x140037720  mov     r8d, [rsi]; cbOutput
0x140037723  xor     r9d, r9d; dwFlags
0x140037726  mov     rcx, [rbp+phHash]; hHash
0x14003772a  mov     rdx, rdi; pbOutput
0x14003772d  call    cs:__imp_BCryptFinishHash
0x140037733  mov     ebx, eax
0x140037735  test    eax, eax
0x140037737  jns     short loc_140037743
0x140037739  mov     ecx, eax
0x14003773b  mov     r9d, 22Ah
0x140037741  jmp     short loc_14003776F
0x140037743  mov     [r15], rdi
0x140037746  jmp     short loc_140037790
0x140037748  mov     ebx, 0C00000E5h
0x14003774d  mov     r9d, 215h
0x140037753  mov     ecx, 0C00000E5h
0x140037758  jmp     loc_1400375AD
0x14003775d  xor     edi, edi
0x14003775f  mov     ebx, 0C00000E5h
0x140037764  mov     ecx, 0C00000E5h
0x140037769  mov     r9d, 1B2h
0x14003776f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140037776  lea     rdx, aStatus; "Status"
0x14003777d  call    DebugTraceError
0x140037782  test    rdi, rdi
0x140037785  jz      short loc_140037790
0x140037787  mov     rcx, rdi; hMem
0x14003778a  call    cs:__imp_LocalFree
0x140037790  mov     rcx, [rbp+phHash]; hHash
0x140037794  test    rcx, rcx
0x140037797  jz      short loc_14003779F
0x140037799  call    cs:__imp_BCryptDestroyHash
0x14003779f  mov     eax, ebx
0x1400377a1  add     rsp, 78h
0x1400377a5  pop     r15
0x1400377a7  pop     r14
0x1400377a9  pop     r13
0x1400377ab  pop     r12
0x1400377ad  pop     rdi
0x1400377ae  pop     rsi
0x1400377af  pop     rbx
0x1400377b0  pop     rbp
0x1400377b1  retn
```
