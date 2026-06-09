# GameInputServerDevice::GenerateAppLocalDeviceId(unsigned __int64,void const *,APP_LOCAL_DEVICE_ID &)

- ea: `0x18003b5b4`
- end: `0x18003b753`
- name: `?GenerateAppLocalDeviceId@GameInputServerDevice@@CAJ_KPEBXAEAUAPP_LOCAL_DEVICE_ID@@@Z`
- size: `415`
- prototype: `__int64 __fastcall(ULONG cbInput, PUCHAR pbInput, PUCHAR pbOutput)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180030308`
- `0x180030ee0`
- `0x18003197c`

## callees

- `0x180001304`
- `0x18003b5b4`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18003b6a7`
- `bcrypt!BCryptDestroyHash` at `0x18003b6a7`
- `bcrypt!BCryptHashData` at `0x18003b64f`
- `bcrypt!BCryptHashData` at `0x18003b676`
- `bcrypt!BCryptHashData` at `0x18003b64f`
- `bcrypt!BCryptHashData` at `0x18003b676`
- `bcrypt!BCryptCreateHash` at `0x18003b630`
- `bcrypt!BCryptCreateHash` at `0x18003b630`
- `bcrypt!BCryptFinishHash` at `0x18003b695`
- `bcrypt!BCryptFinishHash` at `0x18003b695`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003b5eb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003b5eb`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18003b6b9`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18003b6b9`

## pseudocode

```c
__int64 __fastcall GameInputServerDevice::GenerateAppLocalDeviceId(ULONG cbInput, PUCHAR pbInput, PUCHAR pbOutput)
{
  NTSTATUS v6; // ebx
  int v7; // r8d
  int v8; // r9d
  int v10; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-18h] BYREF
  const char *v12; // [rsp+50h] [rbp-10h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+98h] [rbp+38h] BYREF

  phAlgorithm = 0;
  v6 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( v6 >= 0 )
  {
    phHash = 0;
    v6 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
    if ( v6 >= 0 )
    {
      v6 = BCryptHashData(phHash, pbInput, cbInput, 0);
      if ( v6 >= 0 )
      {
        v6 = BCryptHashData(phHash, (PUCHAR)&::pbInput, 0x20u, 0);
        if ( v6 >= 0 )
          v6 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
      }
      BCryptDestroyHash(phHash);
    }
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    if ( v6 >= 0 )
      return 0;
  }
  if ( (unsigned int)dword_180069000 > 2
    && (qword_180069010 & 0x400) != 0
    && (qword_180069018 & 0x400) == qword_180069018 )
  {
    LODWORD(phHash) = v6;
    v12 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
    v10 = 2308;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned int)&byte_18006127F,
      v7,
      v8,
      (__int64)&v12,
      (__int64)&v10,
      (__int64)&phHash);
  }
  return v6 | 0x10000000u;
}

```

## disassembly

```asm
0x18003b5b4  mov     [rsp-18h+arg_0], rbx
0x18003b5b9  mov     [rsp-18h+arg_8], rsi
0x18003b5be  push    rbp
0x18003b5bf  push    rdi
0x18003b5c0  push    r14
0x18003b5c2  mov     rbp, rsp
0x18003b5c5  sub     rsp, 60h
0x18003b5c9  mov     r14, r8
0x18003b5cc  mov     [rbp+phAlgorithm], 0
0x18003b5d4  mov     rdi, rdx
0x18003b5d7  mov     rsi, rcx
0x18003b5da  xor     r8d, r8d; pszImplementation
0x18003b5dd  lea     rdx, pszAlgId; "SHA256"
0x18003b5e4  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18003b5e8  xor     r9d, r9d; dwFlags
0x18003b5eb  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003b5f2  nop     dword ptr [rax+rax+00h]
0x18003b5f7  mov     ebx, eax
0x18003b5f9  test    eax, eax
0x18003b5fb  js      loc_18003B6CD
0x18003b601  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18003b605  lea     rdx, [rbp+phHash]; phHash
0x18003b609  mov     [rsp+60h+dwFlags], 0; dwFlags
0x18003b611  xor     r9d, r9d; cbHashObject
0x18003b614  mov     [rsp+60h+cbSecret], 0; cbSecret
0x18003b61c  xor     r8d, r8d; pbHashObject
0x18003b61f  mov     [rsp+60h+pbSecret], 0; pbSecret
0x18003b628  mov     [rbp+phHash], 0
0x18003b630  call    cs:__imp_BCryptCreateHash
0x18003b637  nop     dword ptr [rax+rax+00h]
0x18003b63c  mov     ebx, eax
0x18003b63e  test    eax, eax
0x18003b640  js      short loc_18003B6B3
0x18003b642  mov     rcx, [rbp+phHash]; hHash
0x18003b646  mov     r8d, esi; cbInput
0x18003b649  xor     r9d, r9d; dwFlags
0x18003b64c  mov     rdx, rdi; pbInput
0x18003b64f  call    cs:__imp_BCryptHashData
0x18003b656  nop     dword ptr [rax+rax+00h]
0x18003b65b  mov     ebx, eax
0x18003b65d  test    eax, eax
0x18003b65f  js      short loc_18003B6A3
0x18003b661  mov     rcx, [rbp+phHash]; hHash
0x18003b665  lea     rdx, pbInput; pbInput
0x18003b66c  xor     r9d, r9d; dwFlags
0x18003b66f  lea     edi, [r9+20h]
0x18003b673  mov     r8d, edi; cbInput
0x18003b676  call    cs:__imp_BCryptHashData
0x18003b67d  nop     dword ptr [rax+rax+00h]
0x18003b682  mov     ebx, eax
0x18003b684  test    eax, eax
0x18003b686  js      short loc_18003B6A3
0x18003b688  mov     rcx, [rbp+phHash]; hHash
0x18003b68c  xor     r9d, r9d; dwFlags
0x18003b68f  mov     r8d, edi; cbOutput
0x18003b692  mov     rdx, r14; pbOutput
0x18003b695  call    cs:__imp_BCryptFinishHash
0x18003b69c  nop     dword ptr [rax+rax+00h]
0x18003b6a1  mov     ebx, eax
0x18003b6a3  mov     rcx, [rbp+phHash]; hHash
0x18003b6a7  call    cs:__imp_BCryptDestroyHash
0x18003b6ae  nop     dword ptr [rax+rax+00h]
0x18003b6b3  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18003b6b7  xor     edx, edx; dwFlags
0x18003b6b9  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18003b6c0  nop     dword ptr [rax+rax+00h]
0x18003b6c5  test    ebx, ebx
0x18003b6c7  js      short loc_18003B6CD
0x18003b6c9  xor     eax, eax
0x18003b6cb  jmp     short loc_18003B73D
0x18003b6cd  mov     eax, cs:dword_180069000
0x18003b6d3  cmp     eax, 2
0x18003b6d6  jbe     short loc_18003B737
0x18003b6d8  mov     rcx, cs:qword_180069018
0x18003b6df  mov     edx, 400h
0x18003b6e4  mov     rax, cs:qword_180069010
0x18003b6eb  test    rdx, rax
0x18003b6ee  jz      short loc_18003B737
0x18003b6f0  mov     rax, rcx
0x18003b6f3  and     rax, rdx
0x18003b6f6  cmp     rax, rcx
0x18003b6f9  jnz     short loc_18003B737
0x18003b6fb  lea     rax, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x18003b702  mov     dword ptr [rbp+phHash], ebx
0x18003b705  mov     [rbp+var_10], rax
0x18003b709  lea     rdx, byte_18006127F
0x18003b710  lea     rax, [rbp+phHash]
0x18003b714  mov     [rbp+var_20], 904h
0x18003b71b  mov     qword ptr [rsp+60h+dwFlags], rax
0x18003b720  lea     rax, [rbp+var_20]
0x18003b724  mov     qword ptr [rsp+60h+cbSecret], rax
0x18003b729  lea     rax, [rbp+var_10]
0x18003b72d  mov     [rsp+60h+pbSecret], rax
0x18003b732  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003b737  bts     ebx, 1Ch
0x18003b73b  mov     eax, ebx
0x18003b73d  lea     r11, [rsp+60h+var_s0]
0x18003b742  mov     rbx, [r11+20h]
0x18003b746  mov     rsi, [r11+28h]
0x18003b74a  mov     rsp, r11
0x18003b74d  pop     r14
0x18003b74f  pop     rdi
0x18003b750  pop     rbp
0x18003b751  retn
```
