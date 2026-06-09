# MSCryptDsaExportKeyPair

- ea: `0x1800697b0`
- end: `0x180069892`
- name: `MSCryptDsaExportKeyPair`
- size: `226`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18005196c`
- `0x180068f50`
- `0x180069168`
- `0x1800697b0`

## string_xrefs

- `0x180069873`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptDsaExportKeyPair(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        _DWORD *a4,
        unsigned int a5,
        unsigned int *a6,
        int a7)
{
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  unsigned int *v12; // rdi
  int v13; // eax
  __int64 v15; // [rsp+68h] [rbp+10h] BYREF

  v15 = 0;
  if ( a2 )
  {
    v9 = -1073741637;
    v10 = 2414;
    v11 = 3221225659LL;
LABEL_16:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v10);
    return v9;
  }
  if ( !a1 || !a3 || (v12 = a6) == 0 || a7 )
  {
    v9 = -1073741811;
    v10 = 2425;
    v11 = 3221225485LL;
    goto LABEL_16;
  }
  v13 = ValidateDSAKey(a1, 0, &v15);
  v9 = v13;
  if ( v13 < 0 )
  {
    v10 = 2432;
LABEL_9:
    v11 = (unsigned int)v13;
    goto LABEL_16;
  }
  if ( *(_DWORD *)(v15 + 20) )
  {
    v13 = ExportV2KeyBlob(v15, a3, a4, a5, v12);
    v9 = v13;
    if ( v13 < 0 )
    {
      v10 = 2461;
      goto LABEL_9;
    }
  }
  else
  {
    v13 = ExportV1KeyBlob(v15, a3, a4, a5, v12);
    v9 = v13;
    if ( v13 < 0 )
    {
      v10 = 2446;
      goto LABEL_9;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800697b0  push    rbx
0x1800697b2  push    rbp
0x1800697b3  push    rsi
0x1800697b4  push    rdi
0x1800697b5  sub     rsp, 38h
0x1800697b9  mov     [rsp+58h+arg_8], 0
0x1800697c2  mov     rbp, r9
0x1800697c5  mov     rsi, r8
0x1800697c8  test    rdx, rdx
0x1800697cb  jz      short loc_1800697E2
0x1800697cd  mov     ebx, 0C00000BBh
0x1800697d2  mov     r9d, 96Eh
0x1800697d8  mov     ecx, 0C00000BBh
0x1800697dd  jmp     loc_180069873
0x1800697e2  test    rcx, rcx
0x1800697e5  jz      short loc_180069863
0x1800697e7  test    rsi, rsi
0x1800697ea  jz      short loc_180069863
0x1800697ec  mov     rdi, [rsp+58h+arg_28]
0x1800697f4  test    rdi, rdi
0x1800697f7  jz      short loc_180069863
0x1800697f9  cmp     [rsp+58h+arg_30], 0
0x180069801  jnz     short loc_180069863
0x180069803  lea     r8, [rsp+58h+arg_8]
0x180069808  xor     edx, edx
0x18006980a  call    ValidateDSAKey
0x18006980f  mov     ebx, eax
0x180069811  test    eax, eax
0x180069813  jns     short loc_18006981F
0x180069815  mov     r9d, 980h
0x18006981b  mov     ecx, eax
0x18006981d  jmp     short loc_180069873
0x18006981f  mov     rcx, [rsp+58h+arg_8]
0x180069824  mov     r8, rbp
0x180069827  mov     r9d, [rsp+58h+arg_20]
0x18006982f  mov     rdx, rsi
0x180069832  mov     [rsp+58h+var_38], rdi
0x180069837  cmp     dword ptr [rcx+14h], 0
0x18006983b  jnz     short loc_180069850
0x18006983d  call    ExportV1KeyBlob
0x180069842  mov     ebx, eax
0x180069844  test    eax, eax
0x180069846  jns     short loc_180069886
0x180069848  mov     r9d, 98Eh
0x18006984e  jmp     short loc_18006981B
0x180069850  call    ExportV2KeyBlob
0x180069855  mov     ebx, eax
0x180069857  test    eax, eax
0x180069859  jns     short loc_180069886
0x18006985b  mov     r9d, 99Dh
0x180069861  jmp     short loc_18006981B
0x180069863  mov     ebx, 0C000000Dh
0x180069868  mov     r9d, 979h
0x18006986e  mov     ecx, 0C000000Dh
0x180069873  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006987a  lea     rdx, aStatus; "Status"
0x180069881  call    DebugTraceError
0x180069886  mov     eax, ebx
0x180069888  add     rsp, 38h
0x18006988c  pop     rdi
0x18006988d  pop     rsi
0x18006988e  pop     rbp
0x18006988f  pop     rbx
0x180069890  retn
```
