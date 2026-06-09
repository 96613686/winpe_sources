# MSCryptEcDsaImportKeyPair

- ea: `0x180047560`
- end: `0x18004760d`
- name: `MSCryptEcDsaImportKeyPair`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x1800225d0`
- `0x180047560`
- `0x1800476d0`

## string_xrefs

- `0x1800475e5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEcDsaImportKeyPair(
        int a1,
        __int64 a2,
        const wchar_t *a3,
        _QWORD *a4,
        __int64 a5,
        unsigned int a6,
        int a7)
{
  int v8; // eax
  int v9; // r8d
  unsigned int v10; // ebx
  _DWORD *v11; // rcx
  int v13; // [rsp+50h] [rbp-18h] BYREF
  _DWORD *v14; // [rsp+58h] [rbp-10h] BYREF

  v13 = 0;
  v14 = 0;
  v8 = MSCryptEccImportKeyPair(a1, a2, a3, &v14, a5, a6, a7, 1, &v13);
  v10 = v8;
  if ( v8 < 0 )
  {
    DebugTraceError((unsigned int)v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 4139);
    v11 = v14;
  }
  else
  {
    v11 = 0;
    *a4 = v14;
    v10 = 0;
  }
  if ( v11 )
    MSCryptEccDestroyKeyPair(v11, 1, v9);
  return v10;
}

```

## disassembly

```asm
0x180047560  mov     r11, rsp
0x180047563  mov     [r11+8], rbx
0x180047567  push    rdi
0x180047568  sub     rsp, 60h
0x18004756c  lea     rax, [r11-18h]
0x180047570  mov     [rsp+68h+var_18], 0
0x180047578  mov     [r11-28h], rax
0x18004757c  mov     rdi, r9
0x18004757f  mov     eax, [rsp+68h+arg_30]
0x180047586  lea     r9, [r11-10h]
0x18004758a  mov     [rsp+68h+var_30], 1
0x180047592  mov     [rsp+68h+var_38], eax
0x180047596  mov     eax, [rsp+68h+arg_28]
0x18004759d  mov     [rsp+68h+var_40], eax
0x1800475a1  mov     rax, [rsp+68h+arg_20]
0x1800475a9  mov     [r11-48h], rax
0x1800475ad  mov     qword ptr [r11-10h], 0
0x1800475b5  call    MSCryptEccImportKeyPair
0x1800475ba  mov     ebx, eax
0x1800475bc  test    eax, eax
0x1800475be  js      short loc_1800475DF
0x1800475c0  mov     rax, [rsp+68h+var_10]
0x1800475c5  xor     ecx, ecx; P
0x1800475c7  mov     [rdi], rax
0x1800475ca  xor     ebx, ebx
0x1800475cc  test    rcx, rcx
0x1800475cf  jnz     short loc_180047601
0x1800475d1  mov     eax, ebx
0x1800475d3  mov     rbx, [rsp+68h+arg_0]
0x1800475d8  add     rsp, 60h
0x1800475dc  pop     rdi
0x1800475dd  retn
0x1800475df  mov     r9d, 102Bh
0x1800475e5  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800475ec  lea     rdx, aStatus; "Status"
0x1800475f3  mov     ecx, eax
0x1800475f5  call    DebugTraceError
0x1800475fa  mov     rcx, [rsp+68h+var_10]
0x1800475ff  jmp     short loc_1800475CC
0x180047601  mov     edx, 1
0x180047606  call    MSCryptEccDestroyKeyPair
0x18004760b  jmp     short loc_1800475D1
```
