# CreateKerbECDHKeyAgreement(KerbCredIsoApi *,ulong,long *)

- ea: `0x14001debc`
- end: `0x14001df9e`
- name: `?CreateKerbECDHKeyAgreement@@YAPEAVKerbKeyAgreement@@PEAVKerbCredIsoApi@@KPEAJ@Z`
- size: `226`
- prototype: `struct KerbKeyAgreement *(struct KerbCredIsoApi *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140016fd0`

## callees

- `0x140003a48`
- `0x14001cfac`
- `0x14001debc`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x14001def2`
- `bcrypt!BCryptDestroyKey` at `0x14001def2`
- `bcrypt!BCryptFinalizeKeyPair` at `0x14001df77`
- `bcrypt!BCryptFinalizeKeyPair` at `0x14001df77`
- `bcrypt!BCryptGenerateKeyPair` at `0x14001df62`
- `bcrypt!BCryptGenerateKeyPair` at `0x14001df62`

## pseudocode

```c
struct KerbKeyAgreement *__fastcall CreateKerbECDHKeyAgreement(struct KerbCredIsoApi *a1, unsigned int a2, int *a3)
{
  void *AlgHandle; // rax
  int v6; // edi
  char *v7; // rbx
  char *v8; // rax
  BCRYPT_KEY_HANDLE hKey; // [rsp+50h] [rbp+8h] BYREF

  hKey = 0;
  AlgHandle = KerbGetAlgHandle(a2);
  if ( AlgHandle )
  {
    v6 = 60;
    if ( BCryptGenerateKeyPair(AlgHandle, &hKey, a2, 0) >= 0 && BCryptFinalizeKeyPair(hKey, 0) >= 0 )
    {
      *a3 = 0;
      v8 = (char *)operator new(0x48u, (const struct std::nothrow_t *)ECDHNoThrow);
      v7 = v8;
      if ( !v8 )
        return 0;
      v8[40] = 0;
      *(_OWORD *)(v8 + 8) = 0;
      *(_OWORD *)(v8 + 24) = 0;
      *((_QWORD *)v8 + 6) = 0;
      *(_QWORD *)v8 = &KerbECDHKeyAgreement::`vftable';
      *((_DWORD *)v8 + 14) = a2;
      *((_QWORD *)v8 + 8) = hKey;
      return (struct KerbKeyAgreement *)v7;
    }
  }
  else
  {
    v6 = 65;
  }
  v7 = 0;
  if ( hKey )
  {
    BCryptDestroyKey(hKey);
    hKey = 0;
  }
  *a3 = v6;
  return (struct KerbKeyAgreement *)v7;
}

```

## disassembly

```asm
0x14001debc  mov     [rsp+hKey], rcx
0x14001dec1  push    rbx
0x14001dec2  push    rbp
0x14001dec3  push    rsi
0x14001dec4  push    rdi
0x14001dec5  sub     rsp, 28h
0x14001dec9  mov     ecx, edx; unsigned int
0x14001decb  mov     [rsp+48h+hKey], 0
0x14001ded4  mov     rsi, r8
0x14001ded7  mov     ebp, edx
0x14001ded9  call    ?KerbGetAlgHandle@@YAPEAXK@Z; KerbGetAlgHandle(ulong)
0x14001dede  test    rax, rax
0x14001dee1  jnz     short loc_14001DF4F
0x14001dee3  lea     edi, [rax+41h]
0x14001dee6  mov     rcx, [rsp+48h+hKey]; hKey
0x14001deeb  xor     ebx, ebx
0x14001deed  test    rcx, rcx
0x14001def0  jz      short loc_14001DEFD
0x14001def2  call    cs:__imp_BCryptDestroyKey
0x14001def8  mov     [rsp+48h+hKey], rbx
0x14001defd  mov     [rsi], edi
0x14001deff  test    edi, edi
0x14001df01  jnz     loc_14001DF92
0x14001df07  lea     rdx, ?ECDHNoThrow@@3Unothrow_t@std@@A; struct std::nothrow_t *
0x14001df0e  mov     ecx, 48h ; 'H'; unsigned __int64
0x14001df13  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001df18  mov     rbx, rax
0x14001df1b  test    rax, rax
0x14001df1e  jz      short loc_14001DF90
0x14001df20  mov     byte ptr [rax+28h], 0
0x14001df24  xorps   xmm0, xmm0
0x14001df27  movups  xmmword ptr [rax+8], xmm0
0x14001df2b  movups  xmmword ptr [rax+18h], xmm0
0x14001df2f  lea     rax, ??_7KerbECDHKeyAgreement@@6B@; const KerbECDHKeyAgreement::`vftable'
0x14001df36  mov     qword ptr [rbx+30h], 0
0x14001df3e  mov     [rbx], rax
0x14001df41  mov     [rbx+38h], ebp
0x14001df44  mov     rax, [rsp+48h+hKey]
0x14001df49  mov     [rbx+40h], rax
0x14001df4d  jmp     short loc_14001DF92
0x14001df4f  xor     r9d, r9d; dwFlags
0x14001df52  lea     rdx, [rsp+48h+hKey]; phKey
0x14001df57  mov     r8d, ebp; dwLength
0x14001df5a  mov     rcx, rax; hAlgorithm
0x14001df5d  mov     edi, 3Ch ; '<'
0x14001df62  call    cs:__imp_BCryptGenerateKeyPair
0x14001df68  test    eax, eax
0x14001df6a  js      loc_14001DEE6
0x14001df70  mov     rcx, [rsp+48h+hKey]; hKey
0x14001df75  xor     edx, edx; dwFlags
0x14001df77  call    cs:__imp_BCryptFinalizeKeyPair
0x14001df7d  test    eax, eax
0x14001df7f  js      loc_14001DEE6
0x14001df85  mov     dword ptr [rsi], 0
0x14001df8b  jmp     loc_14001DF07
0x14001df90  xor     ebx, ebx
0x14001df92  mov     rax, rbx
0x14001df95  add     rsp, 28h
0x14001df99  pop     rdi
0x14001df9a  pop     rsi
0x14001df9b  pop     rbp
0x14001df9c  pop     rbx
0x14001df9d  retn
```
