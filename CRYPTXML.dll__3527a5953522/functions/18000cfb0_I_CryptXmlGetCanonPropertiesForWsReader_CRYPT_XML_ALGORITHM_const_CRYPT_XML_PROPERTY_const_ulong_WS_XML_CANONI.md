# I_CryptXmlGetCanonPropertiesForWsReader(_CRYPT_XML_ALGORITHM const *,_CRYPT_XML_PROPERTY const *,ulong,_WS_XML_CANONICALIZATION_PROPERTY *,ulong *,int *)

- ea: `0x18000cfb0`
- end: `0x18000d1e0`
- name: `?I_CryptXmlGetCanonPropertiesForWsReader@@YAJPEBU_CRYPT_XML_ALGORITHM@@PEBU_CRYPT_XML_PROPERTY@@KPEAU_WS_XML_CANONICALIZATION_PROPERTY@@PEAKPEAH@Z`
- size: `560`
- prototype: `int(const struct _CRYPT_XML_ALGORITHM *, const struct _CRYPT_XML_PROPERTY *, unsigned int, struct _WS_XML_CANONICALIZATION_PROPERTY *, unsigned int *, int *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009f80`
- `0x18000c990`
- `0x18000e290`
- `0x18000fe50`

## callees

- `0x1800070d0`
- `0x18000cfb0`
- `0x180014ce0`
- `0x180018625`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d042`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d0cf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d111`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d153`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d042`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d0cf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d111`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d153`

## string_xrefs

- `0x18000d021`: `http://www.w3.org/TR/2001/REC-xml-c14n-20010315`
- `0x18000d0ae`: `http://www.w3.org/TR/2001/REC-xml-c14n-20010315#WithComments`
- `0x18000d180`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000d1b0`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000d0f0`: `http://www.w3.org/2001/10/xml-exc-c14n#`
- `0x18000d132`: `http://www.w3.org/2001/10/xml-exc-c14n#WithComments`

## pseudocode

```c
__int64 __fastcall I_CryptXmlGetCanonPropertiesForWsReader(
        const struct _CRYPT_XML_ALGORITHM *a1,
        const struct _CRYPT_XML_PROPERTY *a2,
        __int64 a3,
        struct _WS_XML_CANONICALIZATION_PROPERTY *a4,
        unsigned int *a5,
        int *a6)
{
  LPCWSTR wszAlgorithm; // r8
  int *v9; // rax
  __int64 result; // rax
  __int64 v11; // xmm1_8
  const char *v12; // rax
  const char *v13; // rax
  __int128 v14; // [rsp+30h] [rbp-198h]
  __int64 v15; // [rsp+40h] [rbp-188h] BYREF

  DWORD1(v14) = 0;
  memset_0((char *)&v15 + 4, 0, 0x16Cu);
  memset_0(a4, 0, 24LL * *a5);
  if ( a6 )
    *a6 = 0;
  wszAlgorithm = a1->wszAlgorithm;
  if ( !wszAlgorithm
    || !*wszAlgorithm
    || CompareStringW(0, 1u, wszAlgorithm, -1, L"http://www.w3.org/TR/2001/REC-xml-c14n-20010315", -1) == 2 )
  {
LABEL_6:
    v9 = &dword_1800229B4;
    goto LABEL_7;
  }
  if ( CompareStringW(0, 1u, a1->wszAlgorithm, -1, L"http://www.w3.org/TR/2001/REC-xml-c14n-20010315#WithComments", -1) == 2 )
  {
    v9 = &dword_1800229BC;
  }
  else if ( CompareStringW(0, 1u, a1->wszAlgorithm, -1, L"http://www.w3.org/2001/10/xml-exc-c14n#", -1) == 2 )
  {
    v9 = &dword_180022FE4;
  }
  else
  {
    if ( CompareStringW(0, 1u, a1->wszAlgorithm, -1, L"http://www.w3.org/2001/10/xml-exc-c14n#WithComments", -1) != 2 )
    {
      if ( !a6 )
      {
        v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885371, v12, 145);
        return 2148081925LL;
      }
      *a6 = 1;
      goto LABEL_6;
    }
    v9 = (int *)byte_1800229B8;
  }
LABEL_7:
  LODWORD(v14) = 0;
  *((_QWORD *)&v14 + 1) = v9;
  LODWORD(v15) = 4;
  if ( *a5 )
  {
    result = 0;
    v11 = v15;
    *a5 = 1;
    *(_OWORD *)&a4->id = v14;
    *(_QWORD *)&a4->valueSize = v11;
  }
  else
  {
    v13 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp");
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024662, v13, 153);
    return 2147942634LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000cfb0  mov     [rsp+arg_8], rbx
0x18000cfb5  mov     [rsp+arg_10], rbp
0x18000cfba  push    rsi
0x18000cfbb  push    rdi
0x18000cfbc  push    r14
0x18000cfbe  sub     rsp, 1B0h
0x18000cfc5  mov     rbx, [rsp+1C8h+arg_20]
0x18000cfcd  mov     rbp, rcx
0x18000cfd0  mov     rsi, [rsp+1C8h+arg_28]
0x18000cfd8  lea     rcx, [rsp+1C8h+var_188+4]; void *
0x18000cfdd  xor     eax, eax
0x18000cfdf  xor     edx, edx; Val
0x18000cfe1  mov     r8d, 16Ch; Size
0x18000cfe7  mov     dword ptr [rsp+1C8h+var_198+4], eax
0x18000cfeb  mov     rdi, r9
0x18000cfee  call    memset_0
0x18000cff3  mov     eax, [rbx]
0x18000cff5  xor     edx, edx; Val
0x18000cff7  mov     rcx, rdi; void *
0x18000cffa  lea     r8, [rax+rax*2]
0x18000cffe  shl     r8, 3; Size
0x18000d002  call    memset_0
0x18000d007  xor     r14d, r14d
0x18000d00a  test    rsi, rsi
0x18000d00d  jz      short loc_18000D012
0x18000d00f  mov     [rsi], r14d
0x18000d012  mov     r8, [rbp+8]; lpString1
0x18000d016  test    r8, r8
0x18000d019  jz      short loc_18000D053
0x18000d01b  cmp     r14w, [r8]
0x18000d01f  jz      short loc_18000D053
0x18000d021  lea     rax, aHttpWwwW3OrgTr_0; "http://www.w3.org/TR/2001/REC-xml-c14n-"...
0x18000d028  mov     [rsp+1C8h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000d030  mov     edx, 1; dwCmpFlags
0x18000d035  mov     [rsp+1C8h+lpString2], rax; lpString2
0x18000d03a  xor     ecx, ecx; Locale
0x18000d03c  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000d042  call    cs:__imp_CompareStringW
0x18000d049  nop     dword ptr [rax+rax+00h]
0x18000d04e  cmp     eax, 2
0x18000d051  jnz     short loc_18000D0AA
0x18000d053  lea     rax, dword_1800229B4
0x18000d05a  cmp     dword ptr [rbx], 1
0x18000d05d  mov     dword ptr [rsp+1C8h+var_198], r14d
0x18000d062  mov     qword ptr [rsp+1C8h+var_198+8], rax
0x18000d067  mov     dword ptr [rsp+1C8h+var_188], 4
0x18000d06f  jb      loc_18000D1B0
0x18000d075  movaps  xmm0, [rsp+1C8h+var_198]
0x18000d07a  mov     eax, r14d
0x18000d07d  movsd   xmm1, [rsp+1C8h+var_188]
0x18000d083  mov     dword ptr [rbx], 1
0x18000d089  movups  xmmword ptr [rdi], xmm0
0x18000d08c  movsd   qword ptr [rdi+10h], xmm1
0x18000d091  lea     r11, [rsp+1C8h+var_18]
0x18000d099  mov     rbx, [r11+28h]
0x18000d09d  mov     rbp, [r11+30h]
0x18000d0a1  mov     rsp, r11
0x18000d0a4  pop     r14
0x18000d0a6  pop     rdi
0x18000d0a7  pop     rsi
0x18000d0a8  retn
0x18000d0aa  mov     r8, [rbp+8]; lpString1
0x18000d0ae  lea     rax, aHttpWwwW3OrgTr; "http://www.w3.org/TR/2001/REC-xml-c14n-"...
0x18000d0b5  mov     [rsp+1C8h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000d0bd  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000d0c3  mov     edx, 1; dwCmpFlags
0x18000d0c8  mov     [rsp+1C8h+lpString2], rax; lpString2
0x18000d0cd  xor     ecx, ecx; Locale
0x18000d0cf  call    cs:__imp_CompareStringW
0x18000d0d6  nop     dword ptr [rax+rax+00h]
0x18000d0db  cmp     eax, 2
0x18000d0de  jnz     short loc_18000D0EC
0x18000d0e0  lea     rax, dword_1800229BC
0x18000d0e7  jmp     loc_18000D05A
0x18000d0ec  mov     r8, [rbp+8]; lpString1
0x18000d0f0  lea     rax, aHttpWwwW3Org20_11; "http://www.w3.org/2001/10/xml-exc-c14n#"
0x18000d0f7  mov     [rsp+1C8h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000d0ff  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000d105  mov     edx, 1; dwCmpFlags
0x18000d10a  mov     [rsp+1C8h+lpString2], rax; lpString2
0x18000d10f  xor     ecx, ecx; Locale
0x18000d111  call    cs:__imp_CompareStringW
0x18000d118  nop     dword ptr [rax+rax+00h]
0x18000d11d  cmp     eax, 2
0x18000d120  jnz     short loc_18000D12E
0x18000d122  lea     rax, dword_180022FE4
0x18000d129  jmp     loc_18000D05A
0x18000d12e  mov     r8, [rbp+8]; lpString1
0x18000d132  lea     rax, aHttpWwwW3Org20_12; "http://www.w3.org/2001/10/xml-exc-c14n#"...
0x18000d139  mov     [rsp+1C8h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000d141  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000d147  mov     edx, 1; dwCmpFlags
0x18000d14c  mov     [rsp+1C8h+lpString2], rax; lpString2
0x18000d151  xor     ecx, ecx; Locale
0x18000d153  call    cs:__imp_CompareStringW
0x18000d15a  nop     dword ptr [rax+rax+00h]
0x18000d15f  cmp     eax, 2
0x18000d162  jnz     short loc_18000D170
0x18000d164  lea     rax, byte_1800229B8
0x18000d16b  jmp     loc_18000D05A
0x18000d170  test    rsi, rsi
0x18000d173  jz      short loc_18000D180
0x18000d175  mov     dword ptr [rsi], 1
0x18000d17b  jmp     loc_18000D053
0x18000d180  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000d187  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000d18c  mov     r8, rax
0x18000d18f  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000d196  mov     edx, 80092105h
0x18000d19b  mov     r9d, 91h
0x18000d1a1  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000d1a6  mov     eax, 80092105h
0x18000d1ab  jmp     loc_18000D091
0x18000d1b0  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000d1b7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000d1bc  mov     r8, rax
0x18000d1bf  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000d1c6  mov     edx, 800700EAh
0x18000d1cb  mov     r9d, 99h
0x18000d1d1  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000d1d6  mov     eax, 800700EAh
0x18000d1db  jmp     loc_18000D091
```
