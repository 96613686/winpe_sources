# MSCryptEcDhImportKeyPair

- ea: `0x180047620`
- end: `0x1800476ca`
- name: `MSCryptEcDhImportKeyPair`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x1800225d0`
- `0x180047620`
- `0x1800476d0`

## string_xrefs

- `0x1800476a5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEcDhImportKeyPair(
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
  v8 = MSCryptEccImportKeyPair(a1, a2, a3, &v14, a5, a6, a7, 0, &v13);
  v10 = v8;
  if ( v8 < 0 )
  {
    DebugTraceError((unsigned int)v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 4585);
    v11 = v14;
  }
  else
  {
    v11 = 0;
    *a4 = v14;
    v10 = 0;
  }
  if ( v11 )
    MSCryptEccDestroyKeyPair(v11, 0, v9);
  return v10;
}

```

## disassembly

```asm
0x180047620  mov     r11, rsp
0x180047623  mov     [r11+8], rbx
0x180047627  push    rdi
0x180047628  sub     rsp, 60h
0x18004762c  lea     rax, [r11-18h]
0x180047630  mov     [rsp+68h+var_18], 0
0x180047638  mov     [r11-28h], rax
0x18004763c  mov     rdi, r9
0x18004763f  mov     eax, [rsp+68h+arg_30]
0x180047646  lea     r9, [r11-10h]
0x18004764a  mov     [rsp+68h+var_30], 0
0x180047652  mov     [rsp+68h+var_38], eax
0x180047656  mov     eax, [rsp+68h+arg_28]
0x18004765d  mov     [rsp+68h+var_40], eax
0x180047661  mov     rax, [rsp+68h+arg_20]
0x180047669  mov     [r11-48h], rax
0x18004766d  mov     qword ptr [r11-10h], 0
0x180047675  call    MSCryptEccImportKeyPair
0x18004767a  mov     ebx, eax
0x18004767c  test    eax, eax
0x18004767e  js      short loc_18004769F
0x180047680  mov     rax, [rsp+68h+var_10]
0x180047685  xor     ecx, ecx; P
0x180047687  mov     [rdi], rax
0x18004768a  xor     ebx, ebx
0x18004768c  test    rcx, rcx
0x18004768f  jnz     short loc_1800476C1
0x180047691  mov     eax, ebx
0x180047693  mov     rbx, [rsp+68h+arg_0]
0x180047698  add     rsp, 60h
0x18004769c  pop     rdi
0x18004769d  retn
0x18004769f  mov     r9d, 11E9h
0x1800476a5  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800476ac  lea     rdx, aStatus; "Status"
0x1800476b3  mov     ecx, eax
0x1800476b5  call    DebugTraceError
0x1800476ba  mov     rcx, [rsp+68h+var_10]
0x1800476bf  jmp     short loc_18004768C
0x1800476c1  xor     edx, edx
0x1800476c3  call    MSCryptEccDestroyKeyPair
0x1800476c8  jmp     short loc_180047691
```
