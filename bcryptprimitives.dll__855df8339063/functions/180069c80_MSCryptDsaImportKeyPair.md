# MSCryptDsaImportKeyPair

- ea: `0x180069c80`
- end: `0x180069e22`
- name: `MSCryptDsaImportKeyPair`
- size: `418`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _DWORD *, unsigned int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18001b36c`
- `0x180052794`
- `0x1800693c8`
- `0x180069c80`

## string_xrefs

- `0x180069df8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`
- `0x180069d73`: `onecore\ds\security\cryptoapi\ncrypt\common\keyblobvalidate.c`

## pseudocode

```c
__int64 __fastcall MSCryptDsaImportKeyPair(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        unsigned int a6,
        int a7)
{
  int v8; // r15d
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  _DWORD *v12; // rdi
  int v13; // ebp
  int v14; // eax
  __int64 v15; // r9
  int v16; // eax
  _QWORD v18[5]; // [rsp+30h] [rbp-28h] BYREF
  int v19; // [rsp+68h] [rbp+10h] BYREF

  v19 = 0;
  v18[0] = 0;
  v8 = a3;
  if ( a2 )
  {
    v9 = -1073741637;
    v10 = 2030;
    v11 = 3221225659LL;
LABEL_30:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v10);
    return v9;
  }
  if ( !a1 || !a3 || !a4 || (v12 = a5) == 0 || !a6 )
  {
    v10 = 2040;
    goto LABEL_29;
  }
  v13 = a7;
  if ( (a7 & 0xFFFFFFC7) != 0 )
  {
    v10 = 2051;
LABEL_29:
    v9 = -1073741811;
    v11 = 3221225485LL;
    goto LABEL_30;
  }
  v14 = ValidateDSAAlgorithm(a1, 0, &v19, v18);
  v9 = v14;
  if ( v14 < 0 )
  {
    v10 = 2058;
LABEL_12:
    v11 = (unsigned int)v14;
    goto LABEL_30;
  }
  if ( a6 < 0x1C )
  {
    v15 = 410;
LABEL_20:
    DebugTraceError(3221225485LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\keyblobvalidate.c", v15);
    v10 = 2068;
    goto LABEL_29;
  }
  if ( *v12 == 1112560452 || *v12 == 1448104772 )
  {
    v16 = 0;
  }
  else
  {
    if ( *v12 != 843206724 && *v12 != 844517444 )
    {
      v15 = 427;
      goto LABEL_20;
    }
    v16 = 1;
  }
  if ( v16 )
  {
    v14 = ImportV2KeyBlob(v18[0], v8, (_DWORD)v12, a6, v13, a4);
    v9 = v14;
    if ( v14 < 0 )
    {
      v10 = 2083;
      goto LABEL_12;
    }
  }
  else
  {
    v14 = ImportV1KeyBlob(v18[0], v8, (_DWORD)v12, a6, v13, a4);
    v9 = v14;
    if ( v14 < 0 )
    {
      v10 = 2098;
      goto LABEL_12;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180069c80  mov     rax, rsp
0x180069c83  mov     [rax+8], rbx
0x180069c87  mov     [rax+18h], rbp
0x180069c8b  push    rdi
0x180069c8c  push    r14
0x180069c8e  push    r15
0x180069c90  sub     rsp, 40h
0x180069c94  mov     dword ptr [rax+10h], 0
0x180069c9b  mov     r14, r9
0x180069c9e  mov     qword ptr [rax-28h], 0
0x180069ca6  mov     r15, r8
0x180069ca9  test    rdx, rdx
0x180069cac  jz      short loc_180069CC3
0x180069cae  mov     ebx, 0C00000BBh
0x180069cb3  mov     r9d, 7EEh
0x180069cb9  mov     ecx, 0C00000BBh
0x180069cbe  jmp     loc_180069DF8
0x180069cc3  test    rcx, rcx
0x180069cc6  jz      loc_180069DE8
0x180069ccc  test    r15, r15
0x180069ccf  jz      loc_180069DE8
0x180069cd5  test    r14, r14
0x180069cd8  jz      loc_180069DE8
0x180069cde  mov     rdi, [rsp+58h+arg_20]
0x180069ce6  test    rdi, rdi
0x180069ce9  jz      loc_180069DE8
0x180069cef  cmp     [rsp+58h+arg_28], 0
0x180069cf7  jz      loc_180069DE8
0x180069cfd  mov     ebp, [rsp+58h+arg_30]
0x180069d04  test    ebp, 0FFFFFFC7h
0x180069d0a  jz      short loc_180069D17
0x180069d0c  mov     r9d, 803h
0x180069d12  jmp     loc_180069DEE
0x180069d17  lea     r9, [rsp+58h+var_28]
0x180069d1c  xor     edx, edx
0x180069d1e  lea     r8, [rsp+58h+arg_8]
0x180069d23  call    ValidateDSAAlgorithm
0x180069d28  mov     ebx, eax
0x180069d2a  test    eax, eax
0x180069d2c  jns     short loc_180069D3B
0x180069d2e  mov     r9d, 80Ah
0x180069d34  mov     ecx, eax
0x180069d36  jmp     loc_180069DF8
0x180069d3b  cmp     [rsp+58h+arg_28], 1Ch
0x180069d43  jnb     short loc_180069D4D
0x180069d45  mov     r9d, 19Ah
0x180069d4b  jmp     short loc_180069D73
0x180069d4d  cmp     dword ptr [rdi], 42505344h
0x180069d53  jz      short loc_180069D9A
0x180069d55  cmp     dword ptr [rdi], 56505344h
0x180069d5b  jz      short loc_180069D9A
0x180069d5d  cmp     dword ptr [rdi], 32425044h
0x180069d63  jz      short loc_180069D93
0x180069d65  cmp     dword ptr [rdi], 32565044h
0x180069d6b  jz      short loc_180069D93
0x180069d6d  mov     r9d, 1ABh
0x180069d73  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180069d7a  mov     ecx, 0C000000Dh
0x180069d7f  lea     rdx, aStatus_0; "status"
0x180069d86  call    DebugTraceError
0x180069d8b  mov     r9d, 814h
0x180069d91  jmp     short loc_180069DEE
0x180069d93  mov     eax, 1
0x180069d98  jmp     short loc_180069D9C
0x180069d9a  xor     eax, eax
0x180069d9c  mov     r9d, [rsp+58h+arg_28]
0x180069da4  mov     r8, rdi
0x180069da7  mov     rcx, [rsp+58h+var_28]
0x180069dac  mov     rdx, r15
0x180069daf  mov     [rsp+58h+var_30], r14
0x180069db4  mov     [rsp+58h+var_38], ebp
0x180069db8  test    eax, eax
0x180069dba  jz      short loc_180069DD2
0x180069dbc  call    ImportV2KeyBlob
0x180069dc1  mov     ebx, eax
0x180069dc3  test    eax, eax
0x180069dc5  jns     short loc_180069E0B
0x180069dc7  mov     r9d, 823h
0x180069dcd  jmp     loc_180069D34
0x180069dd2  call    ImportV1KeyBlob
0x180069dd7  mov     ebx, eax
0x180069dd9  test    eax, eax
0x180069ddb  jns     short loc_180069E0B
0x180069ddd  mov     r9d, 832h
0x180069de3  jmp     loc_180069D34
0x180069de8  mov     r9d, 7F8h
0x180069dee  mov     ebx, 0C000000Dh
0x180069df3  mov     ecx, 0C000000Dh
0x180069df8  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180069dff  lea     rdx, aStatus; "Status"
0x180069e06  call    DebugTraceError
0x180069e0b  mov     rbp, [rsp+58h+arg_10]
0x180069e10  mov     eax, ebx
0x180069e12  mov     rbx, [rsp+58h+arg_0]
0x180069e17  add     rsp, 40h
0x180069e1b  pop     r15
0x180069e1d  pop     r14
0x180069e1f  pop     rdi
0x180069e20  retn
```
