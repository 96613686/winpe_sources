# CNG_AesKeyUnwrap(uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x1800173d8`
- end: `0x180017632`
- name: `?CNG_AesKeyUnwrap@@YAJPEAEK0KPEAPEAEPEAK@Z`
- size: `602`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR pbSecret@<r8>, unsigned int@<r9d>, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017e20`

## callees

- `0x180010920`
- `0x180010950`
- `0x180010f9c`
- `0x1800173d8`
- `0x18001a450`
- `0x18001a6ac`

## import_xrefs

- `bcrypt!BCryptExportKey` at `0x18001750f`
- `bcrypt!BCryptExportKey` at `0x180017570`
- `bcrypt!BCryptExportKey` at `0x18001750f`
- `bcrypt!BCryptExportKey` at `0x180017570`
- `bcrypt!BCryptDestroyKey` at `0x1800175c6`
- `bcrypt!BCryptDestroyKey` at `0x1800175d5`
- `bcrypt!BCryptDestroyKey` at `0x1800175c6`
- `bcrypt!BCryptDestroyKey` at `0x1800175d5`
- `bcrypt!BCryptImportKey` at `0x1800174d8`
- `bcrypt!BCryptImportKey` at `0x1800174d8`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18001747a`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18001747a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180017611`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180017611`

## string_xrefs

- `0x180017449`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyprotect.cxx`
- `0x18001748c`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyprotect.cxx`

## pseudocode

```c
__int64 __fastcall CNG_AesKeyUnwrap(
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbSecret,
        __int64 a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  unsigned int *v9; // rdi
  int CachedBCryptHandle; // eax
  unsigned int v11; // ebx
  unsigned int v12; // r9d
  unsigned int v13; // ecx
  NTSTATUS v14; // esi
  unsigned int v15; // r9d
  UCHAR *v16; // rax
  unsigned __int64 v17; // rsi
  unsigned __int8 *v18; // rax
  unsigned __int8 *v19; // r14
  __int64 v20; // rax
  unsigned int *v21; // rcx
  int v23; // [rsp+50h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+58h] [rbp-18h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+60h] [rbp-10h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+68h] [rbp-8h] BYREF
  ULONG pcbResult; // [rsp+B8h] [rbp+48h] BYREF

  v23 = 1;
  hAlgorithm = 0;
  phKey = 0;
  hKey = 0;
  pcbResult = 0;
  v9 = 0;
  CachedBCryptHandle = GetCachedBCryptHandle((WCHAR *)L"AES", &hAlgorithm, 1u, &v23);
  v11 = CachedBCryptHandle;
  if ( CachedBCryptHandle < 0 )
  {
    v12 = 267;
    v13 = CachedBCryptHandle;
LABEL_3:
    SidKeyDebugTraceError(v13, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyprotect.cxx", v12);
    goto LABEL_19;
  }
  v14 = BCryptGenerateSymmetricKey(hAlgorithm, &phKey, 0, 0, pbSecret, 0x20u, 0);
  if ( v14 < 0 )
  {
    v15 = 282;
LABEL_6:
    SidKeyDebugTraceError(v14, "status", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyprotect.cxx", v15);
    v11 = v14 | 0x10000000;
    goto LABEL_19;
  }
  v14 = BCryptImportKey(hAlgorithm, phKey, L"Rfc3565KeyWrapBlob", &hKey, 0, 0, pbInput, cbInput, 0);
  if ( v14 < 0 )
  {
    v15 = 302;
    goto LABEL_6;
  }
  v14 = BCryptExportKey(hKey, 0, L"KeyDataBlob", 0, 0, &pcbResult, 0);
  if ( v14 < 0 )
  {
    v15 = 318;
    goto LABEL_6;
  }
  v16 = (UCHAR *)SIDKeyProvAlloc(pcbResult);
  v9 = (unsigned int *)v16;
  if ( !v16 )
  {
    v12 = 327;
LABEL_13:
    v11 = -2146893810;
    v13 = -2146893810;
    goto LABEL_3;
  }
  v14 = BCryptExportKey(hKey, 0, L"KeyDataBlob", v16, pcbResult, &pcbResult, 0);
  if ( v14 < 0 )
  {
    v15 = 341;
    goto LABEL_6;
  }
  v17 = v9[2];
  v18 = (unsigned __int8 *)SIDKeyProvAlloc(v17);
  v19 = v18;
  if ( !v18 )
  {
    v12 = 352;
    goto LABEL_13;
  }
  memcpy_0(v18, v9 + 3, v17);
  *a5 = v19;
  *a6 = v17;
LABEL_19:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( hKey )
    BCryptDestroyKey(hKey);
  if ( v9 )
  {
    v20 = pcbResult;
    v21 = v9;
    if ( pcbResult )
    {
      do
      {
        *(_BYTE *)v21 = 0;
        v21 = (unsigned int *)((char *)v21 + 1);
        --v20;
      }
      while ( v20 );
    }
    SIDKeyProvFree(v9);
  }
  if ( !v23 && hAlgorithm )
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  return v11;
}

```

## disassembly

```asm
0x1800173d8  mov     [rsp-28h+arg_0], rbx
0x1800173dd  mov     [rsp-28h+arg_8], rsi
0x1800173e2  mov     [rsp-28h+pcbResult], r9d
0x1800173e7  push    rbp
0x1800173e8  push    rdi
0x1800173e9  push    r12
0x1800173eb  push    r13
0x1800173ed  push    r14
0x1800173ef  mov     rbp, rsp
0x1800173f2  sub     rsp, 70h
0x1800173f6  xor     r13d, r13d
0x1800173f9  mov     [rbp+var_20], 1
0x180017400  mov     rsi, r8
0x180017403  mov     [rbp+hAlgorithm], r13
0x180017407  mov     r14d, edx
0x18001740a  mov     [rbp+phKey], r13
0x18001740e  mov     r12, rcx
0x180017411  mov     [rbp+hKey], r13
0x180017415  lea     r8d, [r13+1]; unsigned int
0x180017419  mov     [rbp+pcbResult], r13d
0x18001741d  lea     r9, [rbp+var_20]; int *
0x180017421  mov     edi, r13d
0x180017424  lea     rdx, [rbp+hAlgorithm]; void **
0x180017428  lea     rcx, aAes; "AES"
0x18001742f  call    ?GetCachedBCryptHandle@@YAJPEBGPEAPEAXKPEAH@Z; GetCachedBCryptHandle(ushort const *,void * *,ulong,int *)
0x180017434  mov     ebx, eax
0x180017436  test    eax, eax
0x180017438  jns     short loc_18001745A
0x18001743a  mov     r9d, 10Bh; unsigned int
0x180017440  mov     ecx, eax; unsigned int
0x180017442  lea     rdx, aHr; "hr"
0x180017449  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180017450  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180017455  jmp     loc_1800175BD
0x18001745a  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x18001745e  lea     rdx, [rbp+phKey]; phKey
0x180017462  mov     [rsp+70h+dwFlags], r13d; dwFlags
0x180017467  xor     r9d, r9d; cbKeyObject
0x18001746a  mov     [rsp+70h+cbSecret], 20h ; ' '; cbSecret
0x180017472  xor     r8d, r8d; pbKeyObject
0x180017475  mov     [rsp+70h+pbSecret], rsi; pbSecret
0x18001747a  call    cs:__imp_BCryptGenerateSymmetricKey
0x180017480  mov     esi, eax
0x180017482  test    eax, eax
0x180017484  jns     short loc_1800174AC
0x180017486  mov     r9d, 11Ah; unsigned int
0x18001748c  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180017493  mov     ecx, esi; unsigned int
0x180017495  lea     rdx, aStatus; "status"
0x18001749c  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800174a1  mov     ebx, esi
0x1800174a3  bts     ebx, 1Ch
0x1800174a7  jmp     loc_1800175BD
0x1800174ac  mov     rdx, [rbp+phKey]; hImportKey
0x1800174b0  lea     r9, [rbp+hKey]; phKey
0x1800174b4  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x1800174b8  lea     r8, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x1800174bf  mov     [rsp+70h+var_30], r13d; dwFlags
0x1800174c4  mov     [rsp+70h+cbInput], r14d; cbInput
0x1800174c9  mov     qword ptr [rsp+70h+dwFlags], r12; pbInput
0x1800174ce  mov     [rsp+70h+cbSecret], r13d; cbKeyObject
0x1800174d3  mov     [rsp+70h+pbSecret], r13; pbKeyObject
0x1800174d8  call    cs:__imp_BCryptImportKey
0x1800174de  mov     esi, eax
0x1800174e0  test    eax, eax
0x1800174e2  jns     short loc_1800174EC
0x1800174e4  mov     r9d, 12Eh
0x1800174ea  jmp     short loc_18001748C
0x1800174ec  mov     rcx, [rbp+hKey]; hKey
0x1800174f0  lea     rax, [rbp+pcbResult]
0x1800174f4  mov     [rsp+70h+dwFlags], r13d; dwFlags
0x1800174f9  lea     r8, aKeydatablob; "KeyDataBlob"
0x180017500  mov     qword ptr [rsp+70h+cbSecret], rax; pcbResult
0x180017505  xor     r9d, r9d; pbOutput
0x180017508  xor     edx, edx; hExportKey
0x18001750a  mov     dword ptr [rsp+70h+pbSecret], r13d; cbOutput
0x18001750f  call    cs:__imp_BCryptExportKey
0x180017515  mov     esi, eax
0x180017517  test    eax, eax
0x180017519  jns     short loc_180017526
0x18001751b  mov     r9d, 13Eh
0x180017521  jmp     loc_18001748C
0x180017526  mov     ecx, [rbp+pcbResult]; unsigned __int64
0x180017529  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18001752e  mov     rdi, rax
0x180017531  test    rax, rax
0x180017534  jnz     short loc_18001754B
0x180017536  mov     r9d, 147h
0x18001753c  mov     ebx, 8009000Eh
0x180017541  mov     ecx, 8009000Eh
0x180017546  jmp     loc_180017442
0x18001754b  mov     rcx, [rbp+hKey]; hKey
0x18001754f  lea     rax, [rbp+pcbResult]
0x180017553  mov     [rsp+70h+dwFlags], r13d; dwFlags
0x180017558  lea     r8, aKeydatablob; "KeyDataBlob"
0x18001755f  mov     qword ptr [rsp+70h+cbSecret], rax; pcbResult
0x180017564  mov     r9, rdi; pbOutput
0x180017567  mov     eax, [rbp+pcbResult]
0x18001756a  xor     edx, edx; hExportKey
0x18001756c  mov     dword ptr [rsp+70h+pbSecret], eax; cbOutput
0x180017570  call    cs:__imp_BCryptExportKey
0x180017576  mov     esi, eax
0x180017578  test    eax, eax
0x18001757a  jns     short loc_180017587
0x18001757c  mov     r9d, 155h
0x180017582  jmp     loc_18001748C
0x180017587  mov     esi, [rdi+8]
0x18001758a  mov     ecx, esi; unsigned __int64
0x18001758c  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180017591  mov     r14, rax
0x180017594  test    rax, rax
0x180017597  jnz     short loc_1800175A1
0x180017599  mov     r9d, 160h
0x18001759f  jmp     short loc_18001753C
0x1800175a1  lea     rdx, [rdi+0Ch]; Src
0x1800175a5  mov     r8, rsi; Size
0x1800175a8  mov     rcx, r14; void *
0x1800175ab  call    memcpy_0
0x1800175b0  mov     rax, [rbp+arg_20]
0x1800175b4  mov     [rax], r14
0x1800175b7  mov     rax, [rbp+arg_28]
0x1800175bb  mov     [rax], esi
0x1800175bd  mov     rcx, [rbp+phKey]; hKey
0x1800175c1  test    rcx, rcx
0x1800175c4  jz      short loc_1800175CC
0x1800175c6  call    cs:__imp_BCryptDestroyKey
0x1800175cc  mov     rcx, [rbp+hKey]; hKey
0x1800175d0  test    rcx, rcx
0x1800175d3  jz      short loc_1800175DB
0x1800175d5  call    cs:__imp_BCryptDestroyKey
0x1800175db  test    rdi, rdi
0x1800175de  jz      short loc_1800175FF
0x1800175e0  mov     eax, [rbp+pcbResult]
0x1800175e3  mov     rcx, rdi
0x1800175e6  test    rax, rax
0x1800175e9  jz      short loc_1800175F7
0x1800175eb  mov     [rcx], r13b
0x1800175ee  inc     rcx
0x1800175f1  sub     rax, 1
0x1800175f5  jnz     short loc_1800175EB
0x1800175f7  mov     rcx, rdi; lpMem
0x1800175fa  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x1800175ff  cmp     [rbp+var_20], r13d
0x180017603  jnz     short loc_180017617
0x180017605  cmp     [rbp+hAlgorithm], r13
0x180017609  jz      short loc_180017617
0x18001760b  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x18001760f  xor     edx, edx; dwFlags
0x180017611  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180017617  lea     r11, [rsp+70h+var_s0]
0x18001761c  mov     eax, ebx
0x18001761e  mov     rbx, [r11+30h]
0x180017622  mov     rsi, [r11+38h]
0x180017626  mov     rsp, r11
0x180017629  pop     r14
0x18001762b  pop     r13
0x18001762d  pop     r12
0x18001762f  pop     rdi
0x180017630  pop     rbp
0x180017631  retn
```
