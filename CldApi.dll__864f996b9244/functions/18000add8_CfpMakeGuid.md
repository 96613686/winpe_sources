# CfpMakeGuid

- ea: `0x18000add8`
- end: `0x18000afb7`
- name: `CfpMakeGuid`
- size: `479`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006060`

## callees

- `0x18000add8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000ae2e`
- `ntdll!RtlNtStatusToDosError` at `0x18000ae76`
- `ntdll!RtlNtStatusToDosError` at `0x18000aefa`
- `ntdll!RtlNtStatusToDosError` at `0x18000af25`
- `ntdll!RtlNtStatusToDosError` at `0x18000af51`
- `ntdll!RtlNtStatusToDosError` at `0x18000ae2e`
- `ntdll!RtlNtStatusToDosError` at `0x18000ae76`
- `ntdll!RtlNtStatusToDosError` at `0x18000aefa`
- `ntdll!RtlNtStatusToDosError` at `0x18000af25`
- `ntdll!RtlNtStatusToDosError` at `0x18000af51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af77`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aea4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aea4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000af85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000af85`
- `bcrypt!BCryptHashData` at `0x18000af1d`
- `bcrypt!BCryptHashData` at `0x18000af1d`
- `bcrypt!BCryptDestroyHash` at `0x18000af6c`
- `bcrypt!BCryptDestroyHash` at `0x18000af6c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000af96`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000af96`
- `bcrypt!BCryptFinishHash` at `0x18000af49`
- `bcrypt!BCryptFinishHash` at `0x18000af49`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000ae26`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000ae26`
- `bcrypt!BCryptGetProperty` at `0x18000ae6e`
- `bcrypt!BCryptGetProperty` at `0x18000ae6e`
- `bcrypt!BCryptCreateHash` at `0x18000aef2`
- `bcrypt!BCryptCreateHash` at `0x18000aef2`

## pseudocode

```c
__int64 __fastcall CfpMakeGuid(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)
{
  UCHAR *v6; // rdi
  NTSTATUS v7; // eax
  signed int v8; // eax
  signed int v9; // ebx
  NTSTATUS Property; // eax
  signed int v11; // eax
  ULONG v12; // ebx
  HANDLE ProcessHeap; // rax
  NTSTATUS v14; // eax
  signed int v15; // eax
  NTSTATUS v16; // eax
  signed int v17; // eax
  NTSTATUS v18; // eax
  signed int v19; // eax
  HANDLE v20; // rax
  ULONG cbOutput; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-10h] BYREF
  ULONG pbOutputa; // [rsp+A8h] [rbp+48h] BYREF

  phAlgorithm = 0;
  cbOutput = 4;
  v6 = 0;
  pbOutputa = 0;
  phHash = 0;
  v7 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"MD5", L"Microsoft Primitive Provider", 0);
  v8 = RtlNtStatusToDosError(v7);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutputa, cbOutput, &cbOutput, 0);
    v11 = RtlNtStatusToDosError(Property);
    v9 = v11;
    if ( v11 > 0 )
      v9 = (unsigned __int16)v11 | 0x80070000;
    if ( v9 >= 0 )
    {
      v12 = pbOutputa;
      ProcessHeap = GetProcessHeap();
      v6 = (UCHAR *)HeapAlloc(ProcessHeap, 8u, v12);
      v9 = v6 == 0 ? 8 : 0;
      if ( !v6 )
        v9 |= 0x80070000;
      if ( v9 >= 0 )
      {
        v14 = BCryptCreateHash(phAlgorithm, &phHash, v6, pbOutputa, 0, 0, 0);
        v15 = RtlNtStatusToDosError(v14);
        v9 = v15;
        if ( v15 > 0 )
          v9 = (unsigned __int16)v15 | 0x80070000;
        if ( v9 >= 0 )
        {
          v16 = BCryptHashData(phHash, pbInput, cbInput, 0);
          v17 = RtlNtStatusToDosError(v16);
          v9 = v17;
          if ( v17 > 0 )
            v9 = (unsigned __int16)v17 | 0x80070000;
          if ( v9 >= 0 )
          {
            v18 = BCryptFinishHash(phHash, pbOutput, 0x10u, 0);
            v19 = RtlNtStatusToDosError(v18);
            v9 = v19;
            if ( v19 > 0 )
              v9 = (unsigned __int16)v19 | 0x80070000;
          }
        }
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v6 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v6);
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000add8  mov     [rsp-28h+arg_0], rbx
0x18000addd  mov     [rsp-28h+arg_8], rsi
0x18000ade2  push    rbp
0x18000ade3  push    rdi
0x18000ade4  push    r13
0x18000ade6  push    r14
0x18000ade8  push    r15
0x18000adea  mov     rbp, rsp
0x18000aded  sub     rsp, 60h
0x18000adf1  mov     r15, r8
0x18000adf4  mov     [rbp+phAlgorithm], 0
0x18000adfc  mov     esi, edx
0x18000adfe  mov     [rbp+cbOutput], 4
0x18000ae05  mov     r14, rcx
0x18000ae08  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18000ae0f  xor     edi, edi
0x18000ae11  lea     rdx, pszAlgId; "MD5"
0x18000ae18  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18000ae1c  mov     [rbp+pbOutput], edi
0x18000ae1f  xor     r9d, r9d; dwFlags
0x18000ae22  mov     [rbp+phHash], rdi
0x18000ae26  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000ae2c  mov     ecx, eax; Status
0x18000ae2e  call    cs:__imp_RtlNtStatusToDosError
0x18000ae34  mov     ebx, eax
0x18000ae36  mov     r13d, 80070000h
0x18000ae3c  test    eax, eax
0x18000ae3e  jle     short loc_18000AE46
0x18000ae40  movzx   ebx, ax
0x18000ae43  or      ebx, r13d
0x18000ae46  test    ebx, ebx
0x18000ae48  js      loc_18000AF63
0x18000ae4e  mov     r9d, [rbp+cbOutput]; cbOutput
0x18000ae52  lea     rax, [rbp+cbOutput]
0x18000ae56  mov     rcx, [rbp+phAlgorithm]; hObject
0x18000ae5a  lea     r8, [rbp+pbOutput]; pbOutput
0x18000ae5e  mov     [rsp+60h+dwFlags], edi; dwFlags
0x18000ae62  lea     rdx, pszProperty; "ObjectLength"
0x18000ae69  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18000ae6e  call    cs:__imp_BCryptGetProperty
0x18000ae74  mov     ecx, eax; Status
0x18000ae76  call    cs:__imp_RtlNtStatusToDosError
0x18000ae7c  mov     ebx, eax
0x18000ae7e  test    eax, eax
0x18000ae80  jle     short loc_18000AE88
0x18000ae82  movzx   ebx, ax
0x18000ae85  or      ebx, r13d
0x18000ae88  test    ebx, ebx
0x18000ae8a  js      loc_18000AF63
0x18000ae90  mov     ebx, [rbp+pbOutput]
0x18000ae93  call    cs:__imp_GetProcessHeap
0x18000ae99  mov     r8d, ebx; dwBytes
0x18000ae9c  mov     edx, 8; dwFlags
0x18000aea1  mov     rcx, rax; hHeap
0x18000aea4  call    cs:__imp_HeapAlloc
0x18000aeaa  mov     rdi, rax
0x18000aead  neg     rax
0x18000aeb0  sbb     ebx, ebx
0x18000aeb2  not     ebx
0x18000aeb4  and     ebx, 8
0x18000aeb7  mov     eax, ebx
0x18000aeb9  or      eax, r13d
0x18000aebc  test    rdi, rdi
0x18000aebf  cmovz   ebx, eax
0x18000aec2  test    ebx, ebx
0x18000aec4  js      loc_18000AF63
0x18000aeca  mov     r9d, [rbp+pbOutput]; cbHashObject
0x18000aece  lea     rdx, [rbp+phHash]; phHash
0x18000aed2  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18000aed6  mov     r8, rdi; pbHashObject
0x18000aed9  mov     [rsp+60h+var_30], 0; dwFlags
0x18000aee1  mov     [rsp+60h+dwFlags], 0; cbSecret
0x18000aee9  mov     [rsp+60h+pcbResult], 0; pbSecret
0x18000aef2  call    cs:__imp_BCryptCreateHash
0x18000aef8  mov     ecx, eax; Status
0x18000aefa  call    cs:__imp_RtlNtStatusToDosError
0x18000af00  mov     ebx, eax
0x18000af02  test    eax, eax
0x18000af04  jle     short loc_18000AF0C
0x18000af06  movzx   ebx, ax
0x18000af09  or      ebx, r13d
0x18000af0c  test    ebx, ebx
0x18000af0e  js      short loc_18000AF63
0x18000af10  mov     rcx, [rbp+phHash]; hHash
0x18000af14  xor     r9d, r9d; dwFlags
0x18000af17  mov     r8d, esi; cbInput
0x18000af1a  mov     rdx, r14; pbInput
0x18000af1d  call    cs:__imp_BCryptHashData
0x18000af23  mov     ecx, eax; Status
0x18000af25  call    cs:__imp_RtlNtStatusToDosError
0x18000af2b  mov     ebx, eax
0x18000af2d  test    eax, eax
0x18000af2f  jle     short loc_18000AF37
0x18000af31  movzx   ebx, ax
0x18000af34  or      ebx, r13d
0x18000af37  test    ebx, ebx
0x18000af39  js      short loc_18000AF63
0x18000af3b  mov     rcx, [rbp+phHash]; hHash
0x18000af3f  xor     r9d, r9d; dwFlags
0x18000af42  mov     rdx, r15; pbOutput
0x18000af45  lea     r8d, [r9+10h]; cbOutput
0x18000af49  call    cs:__imp_BCryptFinishHash
0x18000af4f  mov     ecx, eax; Status
0x18000af51  call    cs:__imp_RtlNtStatusToDosError
0x18000af57  mov     ebx, eax
0x18000af59  test    eax, eax
0x18000af5b  jle     short loc_18000AF63
0x18000af5d  movzx   ebx, ax
0x18000af60  or      ebx, r13d
0x18000af63  mov     rcx, [rbp+phHash]; hHash
0x18000af67  test    rcx, rcx
0x18000af6a  jz      short loc_18000AF72
0x18000af6c  call    cs:__imp_BCryptDestroyHash
0x18000af72  test    rdi, rdi
0x18000af75  jz      short loc_18000AF8B
0x18000af77  call    cs:__imp_GetProcessHeap
0x18000af7d  mov     r8, rdi; lpMem
0x18000af80  xor     edx, edx; dwFlags
0x18000af82  mov     rcx, rax; hHeap
0x18000af85  call    cs:__imp_HeapFree
0x18000af8b  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18000af8f  test    rcx, rcx
0x18000af92  jz      short loc_18000AF9C
0x18000af94  xor     edx, edx; dwFlags
0x18000af96  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000af9c  lea     r11, [rsp+60h+var_s0]
0x18000afa1  mov     eax, ebx
0x18000afa3  mov     rbx, [r11+30h]
0x18000afa7  mov     rsi, [r11+38h]
0x18000afab  mov     rsp, r11
0x18000afae  pop     r15
0x18000afb0  pop     r14
0x18000afb2  pop     r13
0x18000afb4  pop     rdi
0x18000afb5  pop     rbp
0x18000afb6  retn
```
