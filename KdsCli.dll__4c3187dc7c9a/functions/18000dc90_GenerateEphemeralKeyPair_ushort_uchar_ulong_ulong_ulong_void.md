# GenerateEphemeralKeyPair(ushort *,uchar *,ulong,ulong,ulong,void * *)

- ea: `0x18000dc90`
- end: `0x18000de71`
- name: `?GenerateEphemeralKeyPair@@YAJPEAGPEAEKKKPEAPEAX@Z`
- size: `481`
- prototype: `int(unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned int, unsigned int, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e8a0`
- `0x1800189b8`

## callees

- `0x18000dc90`
- `0x180010920`
- `0x180010950`
- `0x180010f9c`
- `0x18001a450`

## import_xrefs

- `bcrypt!BCryptFinalizeKeyPair` at `0x18000ddea`
- `bcrypt!BCryptFinalizeKeyPair` at `0x18000ddea`
- `bcrypt!BCryptGenerateKeyPair` at `0x18000dd0a`
- `bcrypt!BCryptGenerateKeyPair` at `0x18000dd0a`
- `bcrypt!BCryptSetProperty` at `0x18000dd56`
- `bcrypt!BCryptSetProperty` at `0x18000ddcd`
- `bcrypt!BCryptSetProperty` at `0x18000dd56`
- `bcrypt!BCryptSetProperty` at `0x18000ddcd`
- `bcrypt!BCryptGenRandom` at `0x18000dd9d`
- `bcrypt!BCryptGenRandom` at `0x18000dd9d`
- `bcrypt!BCryptDestroyKey` at `0x18000de36`
- `bcrypt!BCryptDestroyKey` at `0x18000de36`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000de27`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000de27`

## string_xrefs

- `0x18000dcea`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeysecagr.cxx`
- `0x18000dd1c`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeysecagr.cxx`

## pseudocode

```c
__int64 __fastcall GenerateEphemeralKeyPair(
        unsigned __int16 *a1,
        unsigned __int8 *a2,
        ULONG a3,
        unsigned int a4,
        ULONG dwLength,
        void **a6)
{
  unsigned __int64 v6; // r14
  UCHAR *v9; // rdi
  int CachedBCryptHandle; // eax
  unsigned int v11; // ebx
  unsigned int v12; // r9d
  unsigned int v13; // ecx
  NTSTATUS v14; // esi
  unsigned int v15; // r9d
  UCHAR *v16; // rax
  BCRYPT_KEY_HANDLE v17; // rdx
  unsigned __int64 v18; // rcx
  UCHAR *v19; // rax
  int v21; // [rsp+30h] [rbp-20h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+38h] [rbp-18h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+40h] [rbp-10h] BYREF

  v6 = a4;
  hAlgorithm = 0;
  v9 = 0;
  phKey = 0;
  v21 = 1;
  CachedBCryptHandle = GetCachedBCryptHandle(a1, &hAlgorithm, 4u, &v21);
  v11 = CachedBCryptHandle;
  if ( CachedBCryptHandle >= 0 )
  {
    v14 = BCryptGenerateKeyPair(hAlgorithm, &phKey, dwLength, 0);
    if ( v14 >= 0 )
    {
      if ( a2 && (v14 = BCryptSetProperty(phKey, L"SecretAgreementParam", a2, a3, 0), v14 < 0) )
      {
        v15 = 473;
      }
      else
      {
        v16 = (UCHAR *)SIDKeyProvAlloc(v6);
        v9 = v16;
        if ( !v16 )
        {
          v11 = -2147024882;
          v12 = 483;
          v13 = -2147024882;
          goto LABEL_3;
        }
        v14 = BCryptGenRandom(0, v16, v6, 2u);
        if ( v14 >= 0 )
        {
          v14 = BCryptSetProperty(phKey, L"PrivKeyVal", v9, v6, 0);
          if ( v14 >= 0 )
          {
            v14 = BCryptFinalizeKeyPair(phKey, 0);
            if ( v14 >= 0 )
            {
              v17 = phKey;
              phKey = 0;
              *a6 = v17;
              goto LABEL_19;
            }
            v15 = 517;
          }
          else
          {
            v15 = 507;
          }
        }
        else
        {
          v15 = 494;
        }
      }
    }
    else
    {
      v15 = 458;
    }
    SidKeyDebugTraceError(v14, "status", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeysecagr.cxx", v15);
    v11 = v14 | 0x10000000;
    goto LABEL_19;
  }
  v12 = 446;
  v13 = CachedBCryptHandle;
LABEL_3:
  SidKeyDebugTraceError(v13, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeysecagr.cxx", v12);
LABEL_19:
  if ( !v21 && hAlgorithm )
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( v9 )
  {
    v18 = v6;
    v19 = v9;
    if ( (_DWORD)v6 )
    {
      do
      {
        *v19++ = 0;
        --v18;
      }
      while ( v18 );
    }
    SIDKeyProvFree(v9);
  }
  return v11;
}

```

## disassembly

```asm
0x18000dc90  push    rbp
0x18000dc92  push    rbx
0x18000dc93  push    rsi
0x18000dc94  push    rdi
0x18000dc95  push    r13
0x18000dc97  push    r14
0x18000dc99  push    r15
0x18000dc9b  mov     rbp, rsp
0x18000dc9e  sub     rsp, 50h
0x18000dca2  mov     r14d, r9d
0x18000dca5  mov     r13d, r8d
0x18000dca8  mov     r15, rdx
0x18000dcab  mov     [rbp+hAlgorithm], 0
0x18000dcb3  xor     edi, edi
0x18000dcb5  mov     [rbp+phKey], 0
0x18000dcbd  lea     r9, [rbp+var_20]; int *
0x18000dcc1  mov     [rbp+var_20], 1
0x18000dcc8  lea     rdx, [rbp+hAlgorithm]; void **
0x18000dccc  lea     r8d, [rdi+4]; unsigned int
0x18000dcd0  call    ?GetCachedBCryptHandle@@YAJPEBGPEAPEAXKPEAH@Z; GetCachedBCryptHandle(ushort const *,void * *,ulong,int *)
0x18000dcd5  mov     ebx, eax
0x18000dcd7  test    eax, eax
0x18000dcd9  jns     short loc_18000DCFB
0x18000dcdb  mov     r9d, 1BEh; unsigned int
0x18000dce1  mov     ecx, eax; unsigned int
0x18000dce3  lea     rdx, aHr; "hr"
0x18000dcea  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000dcf1  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000dcf6  jmp     loc_18000DE14
0x18000dcfb  mov     r8d, [rbp+dwLength]; dwLength
0x18000dcff  lea     rdx, [rbp+phKey]; phKey
0x18000dd03  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x18000dd07  xor     r9d, r9d; dwFlags
0x18000dd0a  call    cs:__imp_BCryptGenerateKeyPair
0x18000dd10  mov     esi, eax
0x18000dd12  test    eax, eax
0x18000dd14  jns     short loc_18000DD3C
0x18000dd16  mov     r9d, 1CAh; unsigned int
0x18000dd1c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000dd23  mov     ecx, esi; unsigned int
0x18000dd25  lea     rdx, aStatus; "status"
0x18000dd2c  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000dd31  mov     ebx, esi
0x18000dd33  bts     ebx, 1Ch
0x18000dd37  jmp     loc_18000DE14
0x18000dd3c  test    r15, r15
0x18000dd3f  jz      short loc_18000DD6A
0x18000dd41  mov     rcx, [rbp+phKey]; hObject
0x18000dd45  lea     rdx, pszProperty; "SecretAgreementParam"
0x18000dd4c  mov     r9d, r13d; cbInput
0x18000dd4f  mov     [rsp+50h+dwFlags], edi; dwFlags
0x18000dd53  mov     r8, r15; pbInput
0x18000dd56  call    cs:__imp_BCryptSetProperty
0x18000dd5c  mov     esi, eax
0x18000dd5e  test    eax, eax
0x18000dd60  jns     short loc_18000DD6A
0x18000dd62  mov     r9d, 1D9h
0x18000dd68  jmp     short loc_18000DD1C
0x18000dd6a  mov     rcx, r14; unsigned __int64
0x18000dd6d  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000dd72  mov     rdi, rax
0x18000dd75  test    rax, rax
0x18000dd78  jnz     short loc_18000DD8F
0x18000dd7a  mov     ebx, 8007000Eh
0x18000dd7f  mov     r9d, 1E3h
0x18000dd85  mov     ecx, 8007000Eh
0x18000dd8a  jmp     loc_18000DCE3
0x18000dd8f  mov     r9d, 2; dwFlags
0x18000dd95  mov     r8d, r14d; cbBuffer
0x18000dd98  mov     rdx, rdi; pbBuffer
0x18000dd9b  xor     ecx, ecx; hAlgorithm
0x18000dd9d  call    cs:__imp_BCryptGenRandom
0x18000dda3  mov     esi, eax
0x18000dda5  test    eax, eax
0x18000dda7  jns     short loc_18000DDB4
0x18000dda9  mov     r9d, 1EEh
0x18000ddaf  jmp     loc_18000DD1C
0x18000ddb4  mov     rcx, [rbp+phKey]; hObject
0x18000ddb8  lea     rdx, aPrivkeyval; "PrivKeyVal"
0x18000ddbf  mov     r9d, r14d; cbInput
0x18000ddc2  mov     [rsp+50h+dwFlags], 0; dwFlags
0x18000ddca  mov     r8, rdi; pbInput
0x18000ddcd  call    cs:__imp_BCryptSetProperty
0x18000ddd3  mov     esi, eax
0x18000ddd5  test    eax, eax
0x18000ddd7  jns     short loc_18000DDE4
0x18000ddd9  mov     r9d, 1FBh
0x18000dddf  jmp     loc_18000DD1C
0x18000dde4  mov     rcx, [rbp+phKey]; hKey
0x18000dde8  xor     edx, edx; dwFlags
0x18000ddea  call    cs:__imp_BCryptFinalizeKeyPair
0x18000ddf0  mov     esi, eax
0x18000ddf2  test    eax, eax
0x18000ddf4  jns     short loc_18000DE01
0x18000ddf6  mov     r9d, 205h
0x18000ddfc  jmp     loc_18000DD1C
0x18000de01  mov     rdx, [rbp+phKey]
0x18000de05  mov     rax, [rbp+arg_28]
0x18000de09  mov     [rbp+phKey], 0
0x18000de11  mov     [rax], rdx
0x18000de14  cmp     [rbp+var_20], 0
0x18000de18  jnz     short loc_18000DE2D
0x18000de1a  cmp     [rbp+hAlgorithm], 0
0x18000de1f  jz      short loc_18000DE2D
0x18000de21  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x18000de25  xor     edx, edx; dwFlags
0x18000de27  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000de2d  mov     rcx, [rbp+phKey]; hKey
0x18000de31  test    rcx, rcx
0x18000de34  jz      short loc_18000DE3C
0x18000de36  call    cs:__imp_BCryptDestroyKey
0x18000de3c  test    rdi, rdi
0x18000de3f  jz      short loc_18000DE60
0x18000de41  mov     rcx, r14
0x18000de44  mov     rax, rdi
0x18000de47  test    r14d, r14d
0x18000de4a  jz      short loc_18000DE58
0x18000de4c  mov     byte ptr [rax], 0
0x18000de4f  inc     rax
0x18000de52  sub     rcx, 1
0x18000de56  jnz     short loc_18000DE4C
0x18000de58  mov     rcx, rdi; lpMem
0x18000de5b  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000de60  mov     eax, ebx
0x18000de62  add     rsp, 50h
0x18000de66  pop     r15
0x18000de68  pop     r14
0x18000de6a  pop     r13
0x18000de6c  pop     rdi
0x18000de6d  pop     rsi
0x18000de6e  pop     rbx
0x18000de6f  pop     rbp
0x18000de70  retn
```
