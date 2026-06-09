# VBSAttestationIsRsaKey

- ea: `0x140037a1c`
- end: `0x140037b08`
- name: `VBSAttestationIsRsaKey`
- size: `236`
- prototype: `__int64 __fastcall(BCRYPT_HANDLE hObject)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140012aac`

## callees

- `0x140037a1c`
- `0x1400385f0`
- `0x140038cde`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x140037a84`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x140037a84`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140037af6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140037af6`
- `bcrypt!BCryptGetProperty` at `0x140037a53`
- `bcrypt!BCryptGetProperty` at `0x140037ac8`
- `bcrypt!BCryptGetProperty` at `0x140037a53`
- `bcrypt!BCryptGetProperty` at `0x140037ac8`

## string_xrefs

- `0x140037a70`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\vbsattesthelper.cxx`

## pseudocode

```c
__int64 __fastcall VBSAttestationIsRsaKey(BCRYPT_HANDLE hObject, bool *a2)
{
  NTSTATUS Property; // eax
  unsigned int v5; // ebx
  UCHAR *v6; // rdi
  __int64 v7; // r9
  __int64 v8; // rcx
  ULONG cbOutput; // [rsp+70h] [rbp+18h] BYREF

  cbOutput = 0;
  Property = BCryptGetProperty(hObject, L"AlgorithmName", 0, 0, &cbOutput, 0);
  v5 = Property;
  if ( Property >= 0 )
  {
    v6 = (UCHAR *)LocalAlloc(0, cbOutput);
    if ( !v6 )
    {
      v5 = -1073741801;
      v7 = 601;
      v8 = 3221225495LL;
      goto LABEL_4;
    }
    Property = BCryptGetProperty(hObject, L"AlgorithmName", v6, cbOutput, &cbOutput, 0);
    v5 = Property;
    if ( Property >= 0 )
    {
      *a2 = wcscmp_0((const wchar_t *)v6, L"RSA") == 0;
      goto LABEL_10;
    }
    v7 = 614;
  }
  else
  {
    v6 = 0;
    v7 = 593;
  }
  v8 = (unsigned int)Property;
LABEL_4:
  DebugTraceError(
    v8,
    "Status",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\vbsattesthelper.cxx",
    v7);
LABEL_10:
  LocalFree(v6);
  return v5;
}

```

## disassembly

```asm
0x140037a1c  push    rbx
0x140037a1e  push    rsi
0x140037a1f  push    rdi
0x140037a20  push    r14
0x140037a22  sub     rsp, 38h
0x140037a26  mov     r14, rdx
0x140037a29  mov     [rsp+58h+dwFlags], 0; dwFlags
0x140037a31  lea     rax, [rsp+58h+cbOutput]
0x140037a36  mov     [rsp+58h+cbOutput], 0
0x140037a3e  lea     rdx, pszProperty; "AlgorithmName"
0x140037a45  mov     [rsp+58h+pcbResult], rax; pcbResult
0x140037a4a  xor     r9d, r9d; cbOutput
0x140037a4d  xor     r8d, r8d; pbOutput
0x140037a50  mov     rsi, rcx
0x140037a53  call    cs:__imp_BCryptGetProperty
0x140037a59  mov     ebx, eax
0x140037a5b  test    eax, eax
0x140037a5d  jns     short loc_140037A7E
0x140037a5f  xor     edi, edi
0x140037a61  mov     r9d, 251h
0x140037a67  mov     ecx, eax
0x140037a69  lea     rdx, aStatus; "Status"
0x140037a70  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140037a77  call    DebugTraceError
0x140037a7c  jmp     short loc_140037AF3
0x140037a7e  mov     edx, [rsp+58h+cbOutput]; uBytes
0x140037a82  xor     ecx, ecx; uFlags
0x140037a84  call    cs:__imp_LocalAlloc
0x140037a8a  mov     rdi, rax
0x140037a8d  test    rax, rax
0x140037a90  jnz     short loc_140037AA4
0x140037a92  mov     ebx, 0C0000017h
0x140037a97  mov     r9d, 259h
0x140037a9d  mov     ecx, 0C0000017h
0x140037aa2  jmp     short loc_140037A69
0x140037aa4  mov     r9d, [rsp+58h+cbOutput]; cbOutput
0x140037aa9  lea     rax, [rsp+58h+cbOutput]
0x140037aae  mov     [rsp+58h+dwFlags], 0; dwFlags
0x140037ab6  lea     rdx, pszProperty; "AlgorithmName"
0x140037abd  mov     r8, rdi; pbOutput
0x140037ac0  mov     [rsp+58h+pcbResult], rax; pcbResult
0x140037ac5  mov     rcx, rsi; hObject
0x140037ac8  call    cs:__imp_BCryptGetProperty
0x140037ace  mov     ebx, eax
0x140037ad0  test    eax, eax
0x140037ad2  jns     short loc_140037ADC
0x140037ad4  mov     r9d, 266h
0x140037ada  jmp     short loc_140037A67
0x140037adc  lea     rdx, aRsa; "RSA"
0x140037ae3  mov     rcx, rdi; String1
0x140037ae6  call    wcscmp_0
0x140037aeb  test    eax, eax
0x140037aed  setz    al
0x140037af0  mov     [r14], al
0x140037af3  mov     rcx, rdi; hMem
0x140037af6  call    cs:__imp_LocalFree
0x140037afc  mov     eax, ebx
0x140037afe  add     rsp, 38h
0x140037b02  pop     r14
0x140037b04  pop     rdi
0x140037b05  pop     rsi
0x140037b06  pop     rbx
0x140037b07  retn
```
