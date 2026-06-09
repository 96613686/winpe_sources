# AipIsLifetimeSigningCert

- ea: `0x18000a5a8`
- end: `0x18000a702`
- name: `AipIsLifetimeSigningCert`
- size: `346`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, _DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000944c`
- `0x18000a708`

## callees

- `0x18000880c`
- `0x18000a5a8`
- `0x18000c0ae`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a66a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a66a`
- `ntdll!RtlFreeHeap` at `0x18000a6e6`
- `ntdll!RtlFreeHeap` at `0x18000a6e6`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18000a5d6`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18000a660`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18000a5d6`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18000a660`

## pseudocode

```c
__int64 __fastcall AipIsLifetimeSigningCert(PCCERT_CONTEXT pCertContext, _DWORD *a2)
{
  struct _CTL_USAGE *v4; // rdi
  signed int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r8
  void (__fastcall *v8)(const wchar_t *, const wchar_t *, __int64); // rax
  const wchar_t *v9; // rdx
  const wchar_t *v10; // rcx
  struct _CTL_USAGE *v11; // rax
  signed int LastError; // eax
  LPSTR *rgpszUsageIdentifier; // r15
  __int64 v14; // rsi
  DWORD pcbUsage; // [rsp+50h] [rbp+18h] BYREF

  pcbUsage = 0;
  CertGetEnhancedKeyUsage(pCertContext, 2u, 0, &pcbUsage);
  if ( pcbUsage )
  {
    v11 = (struct _CTL_USAGE *)AiAlloc(pcbUsage);
    v4 = v11;
    if ( !v11 )
    {
      v6 = 8;
      goto LABEL_24;
    }
    if ( CertGetEnhancedKeyUsage(pCertContext, 2u, v11, &pcbUsage) )
    {
      v6 = 0;
      *a2 = 0;
      if ( v4->cUsageIdentifier )
      {
        rgpszUsageIdentifier = v4->rgpszUsageIdentifier;
        v14 = 0;
        while ( strcmp_0(rgpszUsageIdentifier[v14], "1.3.6.1.4.1.311.10.3.13") )
        {
          v14 = (unsigned int)(v14 + 1);
          if ( (unsigned int)v14 >= v4->cUsageIdentifier )
            goto LABEL_24;
        }
        *a2 = 1;
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0xC0070000;
      else
        v7 = (unsigned int)LastError;
      v8 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
      if ( g_AiLogFunctionCallErrorEvent )
      {
        v9 = L".0";
        v10 = L"02";
        goto LABEL_9;
      }
    }
  }
  else
  {
    v4 = 0;
    v5 = GetLastError();
    v6 = v5;
    if ( v5 == -2146885628 )
    {
      *a2 = 0;
      v6 = 0;
      goto LABEL_24;
    }
    if ( v5 > 0 )
      v7 = (unsigned __int16)v5 | 0xC0070000;
    else
      v7 = (unsigned int)v5;
    v8 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
    if ( g_AiLogFunctionCallErrorEvent )
    {
      v9 = L".0";
      v10 = L"02";
LABEL_9:
      v8(v10, v9, v7);
    }
  }
LABEL_24:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return v6;
}

```

## disassembly

```asm
0x18000a5a8  mov     rax, rsp
0x18000a5ab  mov     [rax+8], rbx
0x18000a5af  mov     [rax+10h], rsi
0x18000a5b3  push    rdi
0x18000a5b4  push    r14
0x18000a5b6  push    r15
0x18000a5b8  sub     rsp, 20h
0x18000a5bc  xor     r8d, r8d; pUsage
0x18000a5bf  mov     dword ptr [rax+18h], 0
0x18000a5c6  mov     r14, rdx
0x18000a5c9  lea     r9, [rax+18h]; pcbUsage
0x18000a5cd  mov     rbx, rcx
0x18000a5d0  lea     esi, [r8+2]
0x18000a5d4  mov     edx, esi; dwFlags
0x18000a5d6  call    cs:__imp_CertGetEnhancedKeyUsage
0x18000a5dc  mov     eax, [rsp+38h+pcbUsage]
0x18000a5e0  test    eax, eax
0x18000a5e2  jnz     short loc_18000A63B
0x18000a5e4  xor     edi, edi
0x18000a5e6  call    cs:__imp_GetLastError
0x18000a5ec  mov     ebx, eax
0x18000a5ee  cmp     eax, 80092004h
0x18000a5f3  jnz     short loc_18000A5FF
0x18000a5f5  mov     [r14], edi
0x18000a5f8  xor     ebx, ebx
0x18000a5fa  jmp     loc_18000A6D4
0x18000a5ff  test    eax, eax
0x18000a601  jg      short loc_18000A608
0x18000a603  mov     r8d, eax
0x18000a606  jmp     short loc_18000A613
0x18000a608  movzx   r8d, ax
0x18000a60c  or      r8d, 0C0070000h
0x18000a613  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000a61a  test    rax, rax
0x18000a61d  jz      loc_18000A6D4
0x18000a623  lea     rdx, a0_12; ".0"
0x18000a62a  lea     rcx, a02; "02"
0x18000a631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a636  jmp     loc_18000A6D4
0x18000a63b  mov     rcx, rax
0x18000a63e  call    AiAlloc
0x18000a643  mov     rdi, rax
0x18000a646  test    rax, rax
0x18000a649  jnz     short loc_18000A653
0x18000a64b  lea     ebx, [rax+8]
0x18000a64e  jmp     loc_18000A6D4
0x18000a653  lea     r9, [rsp+38h+pcbUsage]; pcbUsage
0x18000a658  mov     r8, rdi; pUsage
0x18000a65b  mov     edx, esi; dwFlags
0x18000a65d  mov     rcx, rbx; pCertContext
0x18000a660  call    cs:__imp_CertGetEnhancedKeyUsage
0x18000a666  test    eax, eax
0x18000a668  jnz     short loc_18000A6A2
0x18000a66a  call    cs:__imp_GetLastError
0x18000a670  mov     ebx, eax
0x18000a672  test    eax, eax
0x18000a674  jg      short loc_18000A67B
0x18000a676  mov     r8d, eax
0x18000a679  jmp     short loc_18000A686
0x18000a67b  movzx   r8d, ax
0x18000a67f  or      r8d, 0C0070000h
0x18000a686  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000a68d  test    rax, rax
0x18000a690  jz      short loc_18000A6D4
0x18000a692  lea     rdx, a0_13; ".0"
0x18000a699  lea     rcx, a02_0; "02"
0x18000a6a0  jmp     short loc_18000A631
0x18000a6a2  xor     ebx, ebx
0x18000a6a4  mov     [r14], ebx
0x18000a6a7  cmp     [rdi], ebx
0x18000a6a9  jbe     short loc_18000A6D4
0x18000a6ab  mov     r15, [rdi+8]
0x18000a6af  xor     esi, esi
0x18000a6b1  mov     rcx, [r15+rsi*8]; Str1
0x18000a6b5  lea     rdx, Str2; "1.3.6.1.4.1.311.10.3.13"
0x18000a6bc  call    strcmp_0
0x18000a6c1  test    eax, eax
0x18000a6c3  jz      short loc_18000A6CD
0x18000a6c5  inc     esi
0x18000a6c7  cmp     esi, [rdi]
0x18000a6c9  jb      short loc_18000A6B1
0x18000a6cb  jmp     short loc_18000A6D4
0x18000a6cd  mov     dword ptr [r14], 1
0x18000a6d4  mov     rcx, gs:60h
0x18000a6dd  mov     r8, rdi; P
0x18000a6e0  xor     edx, edx; Flags
0x18000a6e2  mov     rcx, [rcx+30h]; HeapHandle
0x18000a6e6  call    cs:__imp_RtlFreeHeap
0x18000a6ec  mov     rsi, [rsp+38h+arg_8]
0x18000a6f1  mov     eax, ebx
0x18000a6f3  mov     rbx, [rsp+38h+arg_0]
0x18000a6f8  add     rsp, 20h
0x18000a6fc  pop     r15
0x18000a6fe  pop     r14
0x18000a700  pop     rdi
0x18000a701  retn
```
