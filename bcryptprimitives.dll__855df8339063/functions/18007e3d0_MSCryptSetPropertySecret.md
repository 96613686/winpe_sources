# MSCryptSetPropertySecret

- ea: `0x18007e3d0`
- end: `0x18007e5bf`
- name: `MSCryptSetPropertySecret`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180068d90`

## callees

- `0x18000ecb0`
- `0x180011740`
- `0x180049c68`
- `0x180049e04`
- `0x18004bef4`
- `0x18007e3d0`
- `0x18007f765`

## string_xrefs

- `0x18007e596`: `onecore\ds\security\cryptoapi\ncrypt\msprim\common\secret.c`

## pseudocode

```c
__int64 __fastcall MSCryptSetPropertySecret(__int64 a1, const wchar_t *a2, wchar_t *a3, unsigned int a4, int a5)
{
  __int64 v5; // rdi
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rbx
  __int64 SymCryptMacAlgorithm; // rax
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v18; // [rsp+50h] [rbp+8h] BYREF

  v5 = a4;
  v18 = 0;
  if ( !a1 )
  {
    v8 = -1073741816;
    v9 = 352;
    v10 = 3221225480LL;
LABEL_38:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\common\\secret.c", v9);
    return v8;
  }
  if ( a5 || !a2 )
  {
    v9 = 360;
    goto LABEL_37;
  }
  v11 = MSCryptValidateSecret(a1, &v18);
  v8 = v11;
  if ( v11 < 0 )
  {
    v9 = 368;
    v10 = (unsigned int)v11;
    goto LABEL_38;
  }
  if ( wcscmp_0(a2, L"HkdfHashAlgorithm") )
  {
    if ( !wcscmp_0(a2, L"HkdfSaltAndFinalize") )
    {
      v14 = v18;
      if ( *(_DWORD *)(v18 + 32) == 1 || (v15 = *(_QWORD *)(v18 + 56)) == 0 )
      {
        v9 = 414;
        goto LABEL_37;
      }
      if ( (unsigned int)SymCryptHkdfExpandKey(
                           (int)v18 + 64,
                           v15,
                           (int)v18 + 624,
                           *(_DWORD *)(v18 + 16),
                           (__int64)a3,
                           v5) )
      {
        v9 = 430;
LABEL_23:
        v8 = -1073741823;
        v10 = 3221225473LL;
        goto LABEL_38;
      }
    }
    else
    {
      if ( wcscmp_0(a2, L"HkdfPrkAndFinalize") )
      {
        v9 = 478;
        goto LABEL_17;
      }
      v14 = v18;
      if ( *(_DWORD *)(v18 + 32) == 1 || (v16 = *(_QWORD *)(v18 + 56)) == 0 || a3 || (_DWORD)v5 )
      {
        v9 = 451;
        goto LABEL_37;
      }
      if ( (unsigned int)SymCryptHkdfPrkExpandKey(v18 + 64, v16, v18 + 624, *(unsigned int *)(v18 + 16)) )
      {
        v9 = 466;
        goto LABEL_23;
      }
    }
    *(_DWORD *)(v14 + 32) = 1;
    return 0;
  }
  v12 = v18;
  if ( *(_DWORD *)(v18 + 32) == 1 )
  {
    v9 = 380;
LABEL_37:
    v8 = -1073741811;
    v10 = 3221225485LL;
    goto LABEL_38;
  }
  if ( (unsigned int)v5 < 2 )
  {
LABEL_14:
    v9 = 389;
    goto LABEL_37;
  }
  LODWORD(v5) = (unsigned int)v5 >> 1;
  while ( 1 )
  {
    v5 = (unsigned int)(v5 - 1);
    if ( !a3[v5] )
      break;
    if ( !(_DWORD)v5 )
      goto LABEL_14;
  }
  SymCryptMacAlgorithm = GetSymCryptMacAlgorithm(a3);
  *(_QWORD *)(v12 + 56) = SymCryptMacAlgorithm;
  if ( !SymCryptMacAlgorithm )
  {
    v9 = 401;
LABEL_17:
    v8 = -1073741637;
    v10 = 3221225659LL;
    goto LABEL_38;
  }
  return 0;
}

```

## disassembly

```asm
0x18007e3d0  mov     [rsp+arg_8], rbx
0x18007e3d5  mov     [rsp+arg_10], rbp
0x18007e3da  push    rsi
0x18007e3db  push    rdi
0x18007e3dc  push    r14
0x18007e3de  sub     rsp, 30h
0x18007e3e2  xor     r14d, r14d
0x18007e3e5  mov     edi, r9d
0x18007e3e8  mov     [rsp+48h+arg_0], r14
0x18007e3ed  mov     rbp, r8
0x18007e3f0  mov     rsi, rdx
0x18007e3f3  test    rcx, rcx
0x18007e3f6  jnz     short loc_18007E40D
0x18007e3f8  mov     ebx, 0C0000008h
0x18007e3fd  mov     r9d, 160h
0x18007e403  mov     ecx, 0C0000008h
0x18007e408  jmp     loc_18007E596
0x18007e40d  cmp     [rsp+48h+arg_20], r14d
0x18007e412  jnz     loc_18007E586
0x18007e418  test    rsi, rsi
0x18007e41b  jz      loc_18007E586
0x18007e421  lea     rdx, [rsp+48h+arg_0]
0x18007e426  call    MSCryptValidateSecret
0x18007e42b  mov     ebx, eax
0x18007e42d  test    eax, eax
0x18007e42f  jns     short loc_18007E43E
0x18007e431  mov     r9d, 170h
0x18007e437  mov     ecx, eax
0x18007e439  jmp     loc_18007E596
0x18007e43e  lea     rdx, aHkdfhashalgori; "HkdfHashAlgorithm"
0x18007e445  mov     rcx, rsi; String1
0x18007e448  call    wcscmp_0
0x18007e44d  test    eax, eax
0x18007e44f  jnz     short loc_18007E4B1
0x18007e451  mov     rbx, [rsp+48h+arg_0]
0x18007e456  cmp     dword ptr [rbx+20h], 1
0x18007e45a  jnz     short loc_18007E467
0x18007e45c  mov     r9d, 17Ch
0x18007e462  jmp     loc_18007E58C
0x18007e467  cmp     edi, 2
0x18007e46a  jb      short loc_18007E47C
0x18007e46c  shr     edi, 1
0x18007e46e  dec     edi
0x18007e470  cmp     [rbp+rdi*2+0], r14w
0x18007e476  jz      short loc_18007E487
0x18007e478  test    edi, edi
0x18007e47a  jnz     short loc_18007E46E
0x18007e47c  mov     r9d, 185h
0x18007e482  jmp     loc_18007E58C
0x18007e487  mov     rcx, rbp; String1
0x18007e48a  call    GetSymCryptMacAlgorithm
0x18007e48f  mov     [rbx+38h], rax
0x18007e493  test    rax, rax
0x18007e496  jnz     loc_18007E56E
0x18007e49c  mov     r9d, 191h
0x18007e4a2  mov     ebx, 0C00000BBh
0x18007e4a7  mov     ecx, 0C00000BBh
0x18007e4ac  jmp     loc_18007E596
0x18007e4b1  lea     rdx, aHkdfsaltandfin; "HkdfSaltAndFinalize"
0x18007e4b8  mov     rcx, rsi; String1
0x18007e4bb  call    wcscmp_0
0x18007e4c0  test    eax, eax
0x18007e4c2  jnz     short loc_18007E517
0x18007e4c4  mov     rbx, [rsp+48h+arg_0]
0x18007e4c9  cmp     dword ptr [rbx+20h], 1
0x18007e4cd  jz      short loc_18007E50F
0x18007e4cf  mov     rdx, [rbx+38h]
0x18007e4d3  test    rdx, rdx
0x18007e4d6  jz      short loc_18007E50F
0x18007e4d8  mov     r9d, [rbx+10h]
0x18007e4dc  lea     r8, [rbx+270h]
0x18007e4e3  lea     rcx, [rbx+40h]
0x18007e4e7  mov     [rsp+48h+var_20], rdi
0x18007e4ec  mov     [rsp+48h+var_28], rbp
0x18007e4f1  call    SymCryptHkdfExpandKey
0x18007e4f6  test    eax, eax
0x18007e4f8  jz      short loc_18007E567
0x18007e4fa  mov     r9d, 1AEh
0x18007e500  mov     ebx, 0C0000001h
0x18007e505  mov     ecx, 0C0000001h
0x18007e50a  jmp     loc_18007E596
0x18007e50f  mov     r9d, 19Eh
0x18007e515  jmp     short loc_18007E58C
0x18007e517  lea     rdx, aHkdfprkandfina; "HkdfPrkAndFinalize"
0x18007e51e  mov     rcx, rsi; String1
0x18007e521  call    wcscmp_0
0x18007e526  test    eax, eax
0x18007e528  jnz     short loc_18007E57B
0x18007e52a  mov     rbx, [rsp+48h+arg_0]
0x18007e52f  cmp     dword ptr [rbx+20h], 1
0x18007e533  jz      short loc_18007E573
0x18007e535  mov     rdx, [rbx+38h]
0x18007e539  test    rdx, rdx
0x18007e53c  jz      short loc_18007E573
0x18007e53e  test    rbp, rbp
0x18007e541  jnz     short loc_18007E573
0x18007e543  test    edi, edi
0x18007e545  jnz     short loc_18007E573
0x18007e547  mov     r9d, [rbx+10h]
0x18007e54b  lea     r8, [rbx+270h]
0x18007e552  lea     rcx, [rbx+40h]
0x18007e556  call    SymCryptHkdfPrkExpandKey
0x18007e55b  test    eax, eax
0x18007e55d  jz      short loc_18007E567
0x18007e55f  mov     r9d, 1D2h
0x18007e565  jmp     short loc_18007E500
0x18007e567  mov     dword ptr [rbx+20h], 1
0x18007e56e  mov     ebx, r14d
0x18007e571  jmp     short loc_18007E5A9
0x18007e573  mov     r9d, 1C3h
0x18007e579  jmp     short loc_18007E58C
0x18007e57b  mov     r9d, 1DEh
0x18007e581  jmp     loc_18007E4A2
0x18007e586  mov     r9d, 168h
0x18007e58c  mov     ebx, 0C000000Dh
0x18007e591  mov     ecx, 0C000000Dh
0x18007e596  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e59d  lea     rdx, aStatus; "Status"
0x18007e5a4  call    DebugTraceError
0x18007e5a9  mov     rbp, [rsp+48h+arg_10]
0x18007e5ae  mov     eax, ebx
0x18007e5b0  mov     rbx, [rsp+48h+arg_8]
0x18007e5b5  add     rsp, 30h
0x18007e5b9  pop     r14
0x18007e5bb  pop     rdi
0x18007e5bc  pop     rsi
0x18007e5bd  retn
```
