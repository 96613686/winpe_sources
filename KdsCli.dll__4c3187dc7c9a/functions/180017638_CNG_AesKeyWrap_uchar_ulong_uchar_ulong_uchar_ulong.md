# CNG_AesKeyWrap(uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180017638`
- end: `0x180017840`
- name: `?CNG_AesKeyWrap@@YAJPEAEK0KPEAPEAEPEAK@Z`
- size: `520`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbSecret@<rcx>, ULONG cbSecret@<edx>, PUCHAR@<r8>, unsigned int@<r9d>, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017850`

## callees

- `0x180010920`
- `0x180010950`
- `0x180010f9c`
- `0x180017638`
- `0x18001a450`

## import_xrefs

- `bcrypt!BCryptExportKey` at `0x18001775b`
- `bcrypt!BCryptExportKey` at `0x1800177c2`
- `bcrypt!BCryptExportKey` at `0x18001775b`
- `bcrypt!BCryptExportKey` at `0x1800177c2`
- `bcrypt!BCryptDestroyKey` at `0x1800177f5`
- `bcrypt!BCryptDestroyKey` at `0x180017804`
- `bcrypt!BCryptDestroyKey` at `0x1800177f5`
- `bcrypt!BCryptDestroyKey` at `0x180017804`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800176d2`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180017723`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800176d2`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180017723`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001782a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001782a`

## string_xrefs

- `0x1800176a2`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyprotect.cxx`
- `0x1800176e5`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyprotect.cxx`

## pseudocode

```c
__int64 __fastcall CNG_AesKeyWrap(
        PUCHAR pbSecret,
        ULONG cbSecret,
        PUCHAR a3,
        __int64 a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  unsigned __int8 *v6; // rdi
  int CachedBCryptHandle; // eax
  unsigned int v11; // ebx
  unsigned int v12; // r9d
  unsigned int v13; // ecx
  NTSTATUS v14; // r14d
  unsigned int v15; // r9d
  UCHAR *v16; // rax
  unsigned int *v17; // rcx
  int v19; // [rsp+40h] [rbp-28h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-18h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+58h] [rbp-10h] BYREF
  ULONG pcbResult; // [rsp+B8h] [rbp+50h] BYREF

  v6 = 0;
  hAlgorithm = 0;
  phKey = 0;
  hKey = 0;
  pcbResult = 0;
  v19 = 1;
  CachedBCryptHandle = GetCachedBCryptHandle((WCHAR *)L"AES", &hAlgorithm, 1u, &v19);
  v11 = CachedBCryptHandle;
  if ( CachedBCryptHandle < 0 )
  {
    v12 = 124;
    v13 = CachedBCryptHandle;
LABEL_3:
    SidKeyDebugTraceError(v13, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyprotect.cxx", v12);
    goto LABEL_16;
  }
  v14 = BCryptGenerateSymmetricKey(hAlgorithm, &phKey, 0, 0, a3, 0x20u, 0);
  if ( v14 < 0 )
  {
    v15 = 139;
LABEL_6:
    SidKeyDebugTraceError(v14, "status", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyprotect.cxx", v15);
    v11 = v14 | 0x10000000;
    goto LABEL_16;
  }
  v14 = BCryptGenerateSymmetricKey(hAlgorithm, &hKey, 0, 0, pbSecret, cbSecret, 0);
  if ( v14 < 0 )
  {
    v15 = 157;
    goto LABEL_6;
  }
  v14 = BCryptExportKey(hKey, phKey, L"Rfc3565KeyWrapBlob", 0, 0, &pcbResult, 0);
  if ( v14 < 0 )
  {
    v15 = 173;
    goto LABEL_6;
  }
  v16 = (UCHAR *)SIDKeyProvAlloc(pcbResult);
  v6 = v16;
  if ( !v16 )
  {
    v11 = -2146893810;
    v12 = 182;
    v13 = -2146893810;
    goto LABEL_3;
  }
  v14 = BCryptExportKey(hKey, phKey, L"Rfc3565KeyWrapBlob", v16, pcbResult, &pcbResult, 0);
  if ( v14 < 0 )
  {
    v15 = 197;
    goto LABEL_6;
  }
  v17 = a6;
  *a5 = v6;
  v6 = 0;
  *v17 = pcbResult;
LABEL_16:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( hKey )
    BCryptDestroyKey(hKey);
  if ( v6 )
    SIDKeyProvFree(v6);
  if ( !v19 && hAlgorithm )
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  return v11;
}

```

## disassembly

```asm
0x180017638  mov     [rsp-30h+pcbResult], r9d
0x18001763d  push    rbp
0x18001763e  push    rbx
0x18001763f  push    rdi
0x180017640  push    r12
0x180017642  push    r14
0x180017644  push    r15
0x180017646  mov     rbp, rsp
0x180017649  sub     rsp, 68h
0x18001764d  xor     edi, edi
0x18001764f  mov     [rbp+hAlgorithm], 0
0x180017657  mov     r14, r8
0x18001765a  mov     [rbp+phKey], 0
0x180017662  mov     r15d, edx
0x180017665  mov     [rbp+hKey], 0
0x18001766d  mov     r12, rcx
0x180017670  mov     [rbp+pcbResult], edi
0x180017673  lea     r8d, [rdi+1]; unsigned int
0x180017677  lea     r9, [rbp+var_28]; int *
0x18001767b  mov     [rbp+var_28], r8d
0x18001767f  lea     rdx, [rbp+hAlgorithm]; void **
0x180017683  lea     rcx, aAes; "AES"
0x18001768a  call    ?GetCachedBCryptHandle@@YAJPEBGPEAPEAXKPEAH@Z; GetCachedBCryptHandle(ushort const *,void * *,ulong,int *)
0x18001768f  mov     ebx, eax
0x180017691  test    eax, eax
0x180017693  jns     short loc_1800176B3
0x180017695  lea     r9d, [rdi+7Ch]; unsigned int
0x180017699  mov     ecx, eax; unsigned int
0x18001769b  lea     rdx, aHr; "hr"
0x1800176a2  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800176a9  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800176ae  jmp     loc_1800177EC
0x1800176b3  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x1800176b7  lea     rdx, [rbp+phKey]; phKey
0x1800176bb  mov     [rsp+68h+dwFlags], edi; dwFlags
0x1800176bf  xor     r9d, r9d; cbKeyObject
0x1800176c2  mov     [rsp+68h+cbSecret], 20h ; ' '; cbSecret
0x1800176ca  xor     r8d, r8d; pbKeyObject
0x1800176cd  mov     [rsp+68h+pbSecret], r14; pbSecret
0x1800176d2  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800176d8  mov     r14d, eax
0x1800176db  test    eax, eax
0x1800176dd  jns     short loc_180017707
0x1800176df  mov     r9d, 8Bh; unsigned int
0x1800176e5  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800176ec  mov     ecx, r14d; unsigned int
0x1800176ef  lea     rdx, aStatus; "status"
0x1800176f6  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800176fb  mov     ebx, r14d
0x1800176fe  bts     ebx, 1Ch
0x180017702  jmp     loc_1800177EC
0x180017707  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x18001770b  lea     rdx, [rbp+hKey]; phKey
0x18001770f  mov     [rsp+68h+dwFlags], edi; dwFlags
0x180017713  xor     r9d, r9d; cbKeyObject
0x180017716  mov     [rsp+68h+cbSecret], r15d; cbSecret
0x18001771b  xor     r8d, r8d; pbKeyObject
0x18001771e  mov     [rsp+68h+pbSecret], r12; pbSecret
0x180017723  call    cs:__imp_BCryptGenerateSymmetricKey
0x180017729  mov     r14d, eax
0x18001772c  test    eax, eax
0x18001772e  jns     short loc_180017738
0x180017730  mov     r9d, 9Dh
0x180017736  jmp     short loc_1800176E5
0x180017738  mov     rdx, [rbp+phKey]; hExportKey
0x18001773c  lea     rax, [rbp+pcbResult]
0x180017740  mov     rcx, [rbp+hKey]; hKey
0x180017744  lea     r8, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x18001774b  mov     [rsp+68h+dwFlags], edi; dwFlags
0x18001774f  xor     r9d, r9d; pbOutput
0x180017752  mov     qword ptr [rsp+68h+cbSecret], rax; pcbResult
0x180017757  mov     dword ptr [rsp+68h+pbSecret], edi; cbOutput
0x18001775b  call    cs:__imp_BCryptExportKey
0x180017761  mov     r14d, eax
0x180017764  test    eax, eax
0x180017766  jns     short loc_180017773
0x180017768  mov     r9d, 0ADh
0x18001776e  jmp     loc_1800176E5
0x180017773  mov     ecx, [rbp+pcbResult]; unsigned __int64
0x180017776  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18001777b  mov     rdi, rax
0x18001777e  test    rax, rax
0x180017781  jnz     short loc_180017798
0x180017783  mov     ebx, 8009000Eh
0x180017788  mov     r9d, 0B6h
0x18001778e  mov     ecx, 8009000Eh
0x180017793  jmp     loc_18001769B
0x180017798  mov     rdx, [rbp+phKey]; hExportKey
0x18001779c  lea     rax, [rbp+pcbResult]
0x1800177a0  mov     rcx, [rbp+hKey]; hKey
0x1800177a4  lea     r8, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x1800177ab  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1800177b3  mov     r9, rdi; pbOutput
0x1800177b6  mov     qword ptr [rsp+68h+cbSecret], rax; pcbResult
0x1800177bb  mov     eax, [rbp+pcbResult]
0x1800177be  mov     dword ptr [rsp+68h+pbSecret], eax; cbOutput
0x1800177c2  call    cs:__imp_BCryptExportKey
0x1800177c8  mov     r14d, eax
0x1800177cb  test    eax, eax
0x1800177cd  jns     short loc_1800177DA
0x1800177cf  mov     r9d, 0C5h
0x1800177d5  jmp     loc_1800176E5
0x1800177da  mov     rax, [rbp+arg_20]
0x1800177de  mov     rcx, [rbp+arg_28]
0x1800177e2  mov     [rax], rdi
0x1800177e5  xor     edi, edi
0x1800177e7  mov     eax, [rbp+pcbResult]
0x1800177ea  mov     [rcx], eax
0x1800177ec  mov     rcx, [rbp+phKey]; hKey
0x1800177f0  test    rcx, rcx
0x1800177f3  jz      short loc_1800177FB
0x1800177f5  call    cs:__imp_BCryptDestroyKey
0x1800177fb  mov     rcx, [rbp+hKey]; hKey
0x1800177ff  test    rcx, rcx
0x180017802  jz      short loc_18001780A
0x180017804  call    cs:__imp_BCryptDestroyKey
0x18001780a  test    rdi, rdi
0x18001780d  jz      short loc_180017817
0x18001780f  mov     rcx, rdi; lpMem
0x180017812  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180017817  cmp     [rbp+var_28], 0
0x18001781b  jnz     short loc_180017830
0x18001781d  cmp     [rbp+hAlgorithm], 0
0x180017822  jz      short loc_180017830
0x180017824  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x180017828  xor     edx, edx; dwFlags
0x18001782a  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180017830  mov     eax, ebx
0x180017832  add     rsp, 68h
0x180017836  pop     r15
0x180017838  pop     r14
0x18001783a  pop     r12
0x18001783c  pop     rdi
0x18001783d  pop     rbx
0x18001783e  pop     rbp
0x18001783f  retn
```
