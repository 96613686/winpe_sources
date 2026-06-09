# GenerateClass5Guid

- ea: `0x180024fd4`
- end: `0x180025210`
- name: `GenerateClass5Guid`
- size: `572`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c0d0`
- `0x1800359d8`
- `0x18003b790`
- `0x1800513ac`
- `0x180051ae0`

## callees

- `0x180005358`
- `0x180007580`
- `0x180024fd4`
- `0x18003e920`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x1800251bc`
- `bcrypt!BCryptDestroyHash` at `0x1800251bc`
- `bcrypt!BCryptGetProperty` at `0x180025091`
- `bcrypt!BCryptGetProperty` at `0x180025091`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800250b7`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800251cd`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800250b7`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800251cd`
- `bcrypt!BCryptCreateHash` at `0x1800250eb`
- `bcrypt!BCryptCreateHash` at `0x1800250eb`
- `bcrypt!BCryptFinishHash` at `0x18002516d`
- `bcrypt!BCryptFinishHash` at `0x18002516d`
- `bcrypt!BCryptHashData` at `0x180025139`
- `bcrypt!BCryptHashData` at `0x180025152`
- `bcrypt!BCryptHashData` at `0x180025139`
- `bcrypt!BCryptHashData` at `0x180025152`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180025061`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180025061`

## pseudocode

```c
__int64 __fastcall GenerateClass5Guid(__int64 a1, UCHAR *a2, ULONG a3, __int64 a4)
{
  UCHAR *v8; // rsi
  NTSTATUS Property; // ebx
  UCHAR *v10; // rax
  unsigned __int32 v12; // eax
  __int16 v13; // ax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-29h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-21h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-19h] BYREF
  ULONG pcbResult; // [rsp+58h] [rbp-11h] BYREF
  UCHAR pbInput[16]; // [rsp+60h] [rbp-9h] BYREF
  UCHAR v19[24]; // [rsp+70h] [rbp+7h] BYREF

  pcbResult = 0;
  *(_DWORD *)pbOutput = 0;
  phAlgorithm = 0;
  phHash = 0;
  *(_OWORD *)pbInput = 0;
  if ( !a1 || !a4 || !a2 && a3 )
    return 2147942487LL;
  v8 = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", L"Microsoft Primitive Provider", 0);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      v10 = (UCHAR *)operator new(*(unsigned int *)pbOutput);
      v8 = v10;
      if ( !v10 )
      {
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
        return 2147942414LL;
      }
      Property = BCryptCreateHash(phAlgorithm, &phHash, v10, *(ULONG *)pbOutput, 0, 0, 0);
      if ( Property >= 0 )
      {
        v12 = _byteswap_ulong(*(_DWORD *)a1);
        *(_OWORD *)pbInput = *(_OWORD *)a1;
        *(_DWORD *)pbInput = v12;
        *(_WORD *)&pbInput[4] = __ROR2__(*(_WORD *)(a1 + 4), 8);
        *(_WORD *)&pbInput[6] = __ROR2__(*(_WORD *)(a1 + 6), 8);
        Property = BCryptHashData(phHash, pbInput, 0x10u, 0);
        if ( Property >= 0 )
        {
          Property = BCryptHashData(phHash, a2, a3, 0);
          if ( Property >= 0 )
          {
            Property = BCryptFinishHash(phHash, v19, 0x14u, 0);
            if ( Property >= 0 )
            {
              *(_OWORD *)a4 = *(_OWORD *)v19;
              *(_DWORD *)a4 = _byteswap_ulong(*(_DWORD *)a4);
              *(_WORD *)(a4 + 4) = __ROR2__(*(_WORD *)(a4 + 4), 8);
              v13 = *(_WORD *)(a4 + 6);
              *(_BYTE *)(a4 + 8) &= 0x3Fu;
              *(_BYTE *)(a4 + 8) |= 0x80u;
              *(_WORD *)(a4 + 6) = __ROR2__(v13, 8) & 0xFFF | 0x5000;
            }
          }
        }
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v8 )
    operator delete(v8);
  return (Property >> 31) & 0x80004005;
}

```

## disassembly

```asm
0x180024fd4  push    rbp
0x180024fd6  push    rbx
0x180024fd7  push    rsi
0x180024fd8  push    rdi
0x180024fd9  push    r12
0x180024fdb  push    r14
0x180024fdd  push    r15
0x180024fdf  lea     rbp, [rsp-27h]
0x180024fe4  sub     rsp, 90h
0x180024feb  mov     rax, cs:__security_cookie
0x180024ff2  xor     rax, rsp
0x180024ff5  mov     [rbp+57h+var_38], rax
0x180024ff9  mov     [rbp+57h+var_68], 0
0x180025000  xorps   xmm0, xmm0
0x180025003  mov     dword ptr [rbp+57h+pbOutput], 0
0x18002500a  mov     rdi, r9
0x18002500d  mov     [rbp+57h+phAlgorithm], 0
0x180025015  mov     r15d, r8d
0x180025018  mov     [rbp+57h+phHash], 0
0x180025020  mov     r14, rdx
0x180025023  mov     r12, rcx
0x180025026  movups  xmmword ptr [rbp+57h+pbInput], xmm0
0x18002502a  test    rcx, rcx
0x18002502d  jz      loc_1800251ED
0x180025033  test    r9, r9
0x180025036  jz      loc_1800251ED
0x18002503c  test    rdx, rdx
0x18002503f  jnz     short loc_18002504A
0x180025041  test    r8d, r8d
0x180025044  jnz     loc_1800251ED
0x18002504a  xor     r9d, r9d; dwFlags
0x18002504d  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180025054  lea     rdx, pszAlgId; "SHA1"
0x18002505b  xor     esi, esi
0x18002505d  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x180025061  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180025067  mov     ebx, eax
0x180025069  test    eax, eax
0x18002506b  js      loc_1800251B3
0x180025071  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x180025075  lea     rax, [rbp+57h+var_68]
0x180025079  mov     [rsp+0C0h+dwFlags], esi; dwFlags
0x18002507d  lea     r9d, [rsi+4]; cbOutput
0x180025081  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x180025085  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x18002508a  lea     rdx, pszProperty; "ObjectLength"
0x180025091  call    cs:__imp_BCryptGetProperty
0x180025097  mov     ebx, eax
0x180025099  test    eax, eax
0x18002509b  js      loc_1800251B3
0x1800250a1  mov     ecx, dword ptr [rbp+57h+pbOutput]; unsigned __int64
0x1800250a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800250a9  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800250ad  mov     rsi, rax
0x1800250b0  test    rax, rax
0x1800250b3  jnz     short loc_1800250C7
0x1800250b5  xor     edx, edx; dwFlags
0x1800250b7  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800250bd  mov     eax, 8007000Eh
0x1800250c2  jmp     loc_1800251F2
0x1800250c7  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x1800250cb  lea     rdx, [rbp+57h+phHash]; phHash
0x1800250cf  mov     [rsp+0C0h+var_90], 0; dwFlags
0x1800250d7  mov     r8, rax; pbHashObject
0x1800250da  mov     [rsp+0C0h+dwFlags], 0; cbSecret
0x1800250e2  mov     [rsp+0C0h+pcbResult], 0; pbSecret
0x1800250eb  call    cs:__imp_BCryptCreateHash
0x1800250f1  mov     ebx, eax
0x1800250f3  test    eax, eax
0x1800250f5  js      loc_1800251B3
0x1800250fb  movups  xmm0, xmmword ptr [r12]
0x180025100  mov     eax, [r12]
0x180025104  lea     rdx, [rbp+57h+pbInput]; pbInput
0x180025108  mov     rcx, [rbp+57h+phHash]; hHash
0x18002510c  xor     r9d, r9d; dwFlags
0x18002510f  bswap   eax
0x180025111  movdqu  xmmword ptr [rbp+57h+pbInput], xmm0
0x180025116  mov     dword ptr [rbp+57h+pbInput], eax
0x180025119  movzx   eax, word ptr [r12+4]
0x18002511f  lea     r8d, [r9+10h]; cbInput
0x180025123  ror     ax, 8
0x180025127  mov     word ptr [rbp+57h+pbInput+4], ax
0x18002512b  movzx   eax, word ptr [r12+6]
0x180025131  ror     ax, 8
0x180025135  mov     word ptr [rbp+57h+pbInput+6], ax
0x180025139  call    cs:__imp_BCryptHashData
0x18002513f  mov     ebx, eax
0x180025141  test    eax, eax
0x180025143  js      short loc_1800251B3
0x180025145  mov     rcx, [rbp+57h+phHash]; hHash
0x180025149  xor     r9d, r9d; dwFlags
0x18002514c  mov     r8d, r15d; cbInput
0x18002514f  mov     rdx, r14; pbInput
0x180025152  call    cs:__imp_BCryptHashData
0x180025158  mov     ebx, eax
0x18002515a  test    eax, eax
0x18002515c  js      short loc_1800251B3
0x18002515e  mov     rcx, [rbp+57h+phHash]; hHash
0x180025162  lea     rdx, [rbp+57h+var_50]; pbOutput
0x180025166  xor     r9d, r9d; dwFlags
0x180025169  lea     r8d, [r9+14h]; cbOutput
0x18002516d  call    cs:__imp_BCryptFinishHash
0x180025173  mov     ebx, eax
0x180025175  test    eax, eax
0x180025177  js      short loc_1800251B3
0x180025179  movups  xmm0, xmmword ptr [rbp+57h+var_50]
0x18002517d  mov     ecx, 0FFFh
0x180025182  movdqu  xmmword ptr [rdi], xmm0
0x180025186  mov     eax, [rdi]
0x180025188  bswap   eax
0x18002518a  mov     [rdi], eax
0x18002518c  movzx   eax, word ptr [rdi+4]
0x180025190  ror     ax, 8
0x180025194  mov     [rdi+4], ax
0x180025198  movzx   eax, word ptr [rdi+6]
0x18002519c  and     byte ptr [rdi+8], 3Fh
0x1800251a0  ror     ax, 8
0x1800251a4  and     ax, cx
0x1800251a7  or      ax, 5000h
0x1800251ab  or      byte ptr [rdi+8], 80h
0x1800251af  mov     [rdi+6], ax
0x1800251b3  mov     rcx, [rbp+57h+phHash]; hHash
0x1800251b7  test    rcx, rcx
0x1800251ba  jz      short loc_1800251C2
0x1800251bc  call    cs:__imp_BCryptDestroyHash
0x1800251c2  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800251c6  test    rcx, rcx
0x1800251c9  jz      short loc_1800251D3
0x1800251cb  xor     edx, edx; dwFlags
0x1800251cd  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800251d3  test    rsi, rsi
0x1800251d6  jz      short loc_1800251E0
0x1800251d8  mov     rcx, rsi; void *
0x1800251db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800251e0  sar     ebx, 1Fh
0x1800251e3  and     ebx, 80004005h
0x1800251e9  mov     eax, ebx
0x1800251eb  jmp     short loc_1800251F2
0x1800251ed  mov     eax, 80070057h
0x1800251f2  mov     rcx, [rbp+57h+var_38]
0x1800251f6  xor     rcx, rsp; StackCookie
0x1800251f9  call    __security_check_cookie
0x1800251fe  add     rsp, 90h
0x180025205  pop     r15
0x180025207  pop     r14
0x180025209  pop     r12
0x18002520b  pop     rdi
0x18002520c  pop     rsi
0x18002520d  pop     rbx
0x18002520e  pop     rbp
0x18002520f  retn
```
