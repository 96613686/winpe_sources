# SCardCertToNgc

- ea: `0x1800e32b4`
- end: `0x1800e336d`
- name: `SCardCertToNgc`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180057c6c`
- `0x1800e3684`

## callees

- `0x1800e32b4`
- `0x1800e3374`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e3343`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e3343`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e3333`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e3333`
- `ncrypt!NCryptOpenKey` at `0x1800e3323`
- `ncrypt!NCryptOpenKey` at `0x1800e3323`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800e32ff`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800e32ff`
- `ncrypt!NCryptFreeObject` at `0x1800e3353`
- `ncrypt!NCryptFreeObject` at `0x1800e3353`

## pseudocode

```c
__int64 __fastcall SCardCertToNgc(const CERT_CONTEXT *a1, __int64 a2, NCRYPT_KEY_HANDLE *a3)
{
  SECURITY_STATUS v4; // ebx
  NCRYPT_PROV_HANDLE phProvider; // [rsp+58h] [rbp+20h] BYREF

  phProvider = 0;
  if ( !a1 || !a3 )
    return 2148073511LL;
  v4 = SCardCertToNgcKeyName(a1);
  if ( v4 >= 0 )
  {
    v4 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
    if ( v4 >= 0 )
      v4 = NCryptOpenKey(phProvider, a3, 0, 0, 0);
  }
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800e32b4  mov     rax, rsp
0x1800e32b7  mov     [rax+10h], rbx
0x1800e32bb  push    rsi
0x1800e32bc  sub     rsp, 30h
0x1800e32c0  mov     qword ptr [rax+20h], 0
0x1800e32c8  mov     rsi, r8
0x1800e32cb  mov     qword ptr [rax+8], 0
0x1800e32d3  test    rcx, rcx
0x1800e32d6  jz      loc_1800E335D
0x1800e32dc  test    r8, r8
0x1800e32df  jz      short loc_1800E335D
0x1800e32e1  lea     rdx, [rax+8]
0x1800e32e5  call    SCardCertToNgcKeyName
0x1800e32ea  mov     ebx, eax
0x1800e32ec  test    eax, eax
0x1800e32ee  js      short loc_1800E332B
0x1800e32f0  xor     r8d, r8d; dwFlags
0x1800e32f3  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x1800e32fa  lea     rcx, [rsp+38h+phProvider]; phProvider
0x1800e32ff  call    cs:__imp_NCryptOpenStorageProvider
0x1800e3305  mov     ebx, eax
0x1800e3307  test    eax, eax
0x1800e3309  js      short loc_1800E332B
0x1800e330b  mov     r8, [rsp+38h+pszKeyName]; pszKeyName
0x1800e3310  xor     r9d, r9d; dwLegacyKeySpec
0x1800e3313  mov     rcx, [rsp+38h+phProvider]; hProvider
0x1800e3318  mov     rdx, rsi; phKey
0x1800e331b  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1800e3323  call    cs:__imp_NCryptOpenKey
0x1800e3329  mov     ebx, eax
0x1800e332b  cmp     [rsp+38h+pszKeyName], 0
0x1800e3331  jz      short loc_1800E3349
0x1800e3333  call    cs:__imp_GetProcessHeap
0x1800e3339  mov     r8, [rsp+38h+pszKeyName]; lpMem
0x1800e333e  xor     edx, edx; dwFlags
0x1800e3340  mov     rcx, rax; hHeap
0x1800e3343  call    cs:__imp_HeapFree
0x1800e3349  mov     rcx, [rsp+38h+phProvider]; hObject
0x1800e334e  test    rcx, rcx
0x1800e3351  jz      short loc_1800E3359
0x1800e3353  call    cs:__imp_NCryptFreeObject
0x1800e3359  mov     eax, ebx
0x1800e335b  jmp     short loc_1800E3362
0x1800e335d  mov     eax, 80090027h
0x1800e3362  mov     rbx, [rsp+38h+arg_8]
0x1800e3367  add     rsp, 30h
0x1800e336b  pop     rsi
0x1800e336c  retn
```
