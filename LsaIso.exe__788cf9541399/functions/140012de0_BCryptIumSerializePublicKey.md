# BCryptIumSerializePublicKey

- ea: `0x140012de0`
- end: `0x140012edf`
- name: `BCryptIumSerializePublicKey`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400123a4`

## callees

- `0x140012de0`
- `0x140037b10`

## import_xrefs

- `iumcrypt!iumCryptEncodeObject` at `0x140012ea8`
- `iumcrypt!iumCryptEncodeObject` at `0x140012ea8`
- `iumcrypt!iumCryptExportPublicKeyInfoFromBCryptKeyHandle` at `0x140012e1e`
- `iumcrypt!iumCryptExportPublicKeyInfoFromBCryptKeyHandle` at `0x140012e83`
- `iumcrypt!iumCryptExportPublicKeyInfoFromBCryptKeyHandle` at `0x140012e1e`
- `iumcrypt!iumCryptExportPublicKeyInfoFromBCryptKeyHandle` at `0x140012e83`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x140012e3e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x140012e3e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140012ece`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140012ece`

## string_xrefs

- `0x140012ebf`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`

## pseudocode

```c
__int64 __fastcall BCryptIumSerializePublicKey(void *a1, unsigned __int8 *a2, unsigned int *a3)
{
  struct _CERT_PUBLIC_KEY_INFO *v6; // rdi
  __int64 v7; // r8
  unsigned int v8; // ebx
  __int64 v9; // rcx
  SIZE_T uBytes; // [rsp+88h] [rbp+20h] BYREF

  LODWORD(uBytes) = 0;
  if ( !iumCryptExportPublicKeyInfoFromBCryptKeyHandle(a1, 1u, 0, 0, 0, 0, (unsigned int *)&uBytes) )
  {
    v6 = 0;
    v7 = 270;
LABEL_9:
    v9 = 3221225701LL;
    v8 = -1073741595;
    goto LABEL_10;
  }
  v6 = (struct _CERT_PUBLIC_KEY_INFO *)LocalAlloc(0, (unsigned int)uBytes);
  if ( !v6 )
  {
    v8 = -1073741801;
    v7 = 278;
    v9 = 3221225495LL;
LABEL_10:
    VBS_ATTEST_TRACE_ERROR_IN(v9, "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx", v7);
    goto LABEL_11;
  }
  if ( !iumCryptExportPublicKeyInfoFromBCryptKeyHandle(a1, 1u, 0, 0, 0, v6, (unsigned int *)&uBytes) )
  {
    v7 = 292;
    goto LABEL_9;
  }
  v8 = 0;
  if ( !iumCryptEncodeObject(1u, (const char *)8, v6, a2, a3) )
  {
    v7 = 305;
    goto LABEL_9;
  }
LABEL_11:
  LocalFree(v6);
  return v8;
}

```

## disassembly

```asm
0x140012de0  mov     r11, rsp
0x140012de3  push    rbx
0x140012de4  push    rbp
0x140012de5  push    rsi
0x140012de6  push    rdi
0x140012de7  sub     rsp, 48h
0x140012deb  xor     r9d, r9d
0x140012dee  mov     dword ptr [r11+20h], 0
0x140012df6  lea     rax, [r11+20h]
0x140012dfa  mov     rsi, r8
0x140012dfd  mov     [r11-38h], rax
0x140012e01  mov     rbp, rdx
0x140012e04  mov     qword ptr [r11-40h], 0
0x140012e0c  xor     r8d, r8d
0x140012e0f  lea     edx, [r9+1]
0x140012e13  mov     qword ptr [r11-48h], 0
0x140012e1b  mov     rbx, rcx
0x140012e1e  call    cs:__imp_?iumCryptExportPublicKeyInfoFromBCryptKeyHandle@@YAHPEAXKPEADK0PEAU_CERT_PUBLIC_KEY_INFO@@PEAK@Z; iumCryptExportPublicKeyInfoFromBCryptKeyHandle(void *,ulong,char *,ulong,void *,_CERT_PUBLIC_KEY_INFO *,ulong *)
0x140012e24  test    eax, eax
0x140012e26  jnz     short loc_140012E35
0x140012e28  xor     edi, edi
0x140012e2a  mov     r8d, 10Eh
0x140012e30  jmp     loc_140012EB8
0x140012e35  mov     edx, dword ptr [rsp+68h+uBytes]; uBytes
0x140012e3c  xor     ecx, ecx; uFlags
0x140012e3e  call    cs:__imp_LocalAlloc
0x140012e44  mov     rdi, rax
0x140012e47  test    rax, rax
0x140012e4a  jnz     short loc_140012E5B
0x140012e4c  mov     ebx, 0C0000017h
0x140012e51  mov     r8d, 116h
0x140012e57  mov     ecx, ebx
0x140012e59  jmp     short loc_140012EBF
0x140012e5b  xor     r9d, r9d
0x140012e5e  lea     rax, [rsp+68h+uBytes]
0x140012e66  mov     [rsp+68h+var_38], rax
0x140012e6b  xor     r8d, r8d
0x140012e6e  mov     [rsp+68h+var_40], rdi
0x140012e73  mov     rcx, rbx
0x140012e76  mov     [rsp+68h+var_48], 0
0x140012e7f  lea     edx, [r9+1]
0x140012e83  call    cs:__imp_?iumCryptExportPublicKeyInfoFromBCryptKeyHandle@@YAHPEAXKPEADK0PEAU_CERT_PUBLIC_KEY_INFO@@PEAK@Z; iumCryptExportPublicKeyInfoFromBCryptKeyHandle(void *,ulong,char *,ulong,void *,_CERT_PUBLIC_KEY_INFO *,ulong *)
0x140012e89  test    eax, eax
0x140012e8b  jnz     short loc_140012E95
0x140012e8d  mov     r8d, 124h
0x140012e93  jmp     short loc_140012EB8
0x140012e95  xor     ebx, ebx
0x140012e97  mov     [rsp+68h+var_48], rsi
0x140012e9c  mov     r9, rbp
0x140012e9f  mov     r8, rdi
0x140012ea2  lea     edx, [rbx+8]
0x140012ea5  lea     ecx, [rbx+1]
0x140012ea8  call    cs:__imp_?iumCryptEncodeObject@@YAHKPEBDPEBXPEAEPEAK@Z; iumCryptEncodeObject(ulong,char const *,void const *,uchar *,ulong *)
0x140012eae  test    eax, eax
0x140012eb0  jnz     short loc_140012ECB
0x140012eb2  mov     r8d, 131h
0x140012eb8  mov     ecx, 0C00000E5h
0x140012ebd  mov     ebx, ecx
0x140012ebf  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140012ec6  call    VBS_ATTEST_TRACE_ERROR_IN
0x140012ecb  mov     rcx, rdi; hMem
0x140012ece  call    cs:__imp_LocalFree
0x140012ed4  mov     eax, ebx
0x140012ed6  add     rsp, 48h
0x140012eda  pop     rdi
0x140012edb  pop     rsi
0x140012edc  pop     rbp
0x140012edd  pop     rbx
0x140012ede  retn
```
