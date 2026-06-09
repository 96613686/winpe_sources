# SetEccPrivateKeyVal

- ea: `0x18006c254`
- end: `0x18006c37a`
- name: `SetEccPrivateKeyVal`
- size: `294`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180021f70`

## callees

- `0x18000ecb0`
- `0x18001ad88`
- `0x18001c380`
- `0x180022874`
- `0x1800243b8`
- `0x180056cf0`
- `0x18006c254`

## string_xrefs

- `0x18006c35b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall SetEccPrivateKeyVal(__int64 a1, __int64 a2, unsigned int a3)
{
  int v3; // esi
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 v8; // rax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  unsigned int v11; // eax

  v3 = a2;
  if ( a3 != *(_DWORD *)(**(_QWORD **)(a1 + 16) + 16LL) || !a2 )
  {
    v6 = 362;
    goto LABEL_14;
  }
  if ( (*(_BYTE *)(a1 + 32) & 2) != 0 )
  {
    v9 = -1073741816;
    v6 = 370;
    v10 = 3221225480LL;
    goto LABEL_15;
  }
  if ( (unsigned int)IsAllZeros(a2, a3) )
  {
    v6 = 377;
LABEL_14:
    v9 = -1073741811;
    v10 = 3221225485LL;
    goto LABEL_15;
  }
  v7 = *(_QWORD *)(a1 + 24);
  if ( v7 )
  {
    SymCryptEckeyFree(v7);
    *(_QWORD *)(a1 + 24) = 0;
  }
  v8 = SymCryptEckeyAllocate(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL));
  *(_QWORD *)(a1 + 24) = v8;
  if ( !v8 )
  {
    v9 = -1073741801;
    v6 = 391;
    v10 = 3221225495LL;
LABEL_15:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v6);
    return v9;
  }
  v9 = 0;
  v11 = SymCryptEckeySetValue(
          v3,
          a3,
          0,
          0,
          (unsigned int)(*(_DWORD *)(**(_QWORD **)(a1 + 16) + 4LL) != 3) + 1,
          2,
          8448,
          v8);
  if ( v11 )
  {
    v9 = SymcryptErrorCodeToNtStatus(v11);
    v10 = v9;
    v6 = 407;
    goto LABEL_15;
  }
  return v9;
}

```

## disassembly

```asm
0x18006c254  push    rbx
0x18006c256  push    rbp
0x18006c257  push    rsi
0x18006c258  push    rdi
0x18006c259  sub     rsp, 48h
0x18006c25d  mov     rax, [rcx+10h]
0x18006c261  mov     rsi, rdx
0x18006c264  mov     ebp, r8d
0x18006c267  mov     rdi, rcx
0x18006c26a  mov     r9, [rax]
0x18006c26d  cmp     r8d, [r9+10h]
0x18006c271  jnz     loc_18006C34B
0x18006c277  test    rdx, rdx
0x18006c27a  jz      loc_18006C34B
0x18006c280  test    byte ptr [rcx+20h], 2
0x18006c284  jnz     loc_18006C339
0x18006c28a  mov     edx, ebp
0x18006c28c  mov     rcx, rsi
0x18006c28f  call    IsAllZeros
0x18006c294  test    eax, eax
0x18006c296  jz      short loc_18006C2A3
0x18006c298  mov     r9d, 179h
0x18006c29e  jmp     loc_18006C351
0x18006c2a3  mov     rcx, [rdi+18h]
0x18006c2a7  test    rcx, rcx
0x18006c2aa  jz      short loc_18006C2B9
0x18006c2ac  call    SymCryptEckeyFree
0x18006c2b1  mov     qword ptr [rdi+18h], 0
0x18006c2b9  mov     rcx, [rdi+10h]
0x18006c2bd  mov     rcx, [rcx+8]
0x18006c2c1  call    SymCryptEckeyAllocate
0x18006c2c6  mov     [rdi+18h], rax
0x18006c2ca  mov     r8, rax
0x18006c2cd  test    rax, rax
0x18006c2d0  jnz     short loc_18006C2E4
0x18006c2d2  mov     ebx, 0C0000017h
0x18006c2d7  mov     r9d, 187h
0x18006c2dd  mov     ecx, 0C0000017h
0x18006c2e2  jmp     short loc_18006C35B
0x18006c2e4  mov     rax, [rdi+10h]
0x18006c2e8  xor     ebx, ebx
0x18006c2ea  mov     [rsp+68h+var_30], r8
0x18006c2ef  mov     rdx, rbp
0x18006c2f2  mov     [rsp+68h+var_38], 2100h
0x18006c2fa  mov     [rsp+68h+var_40], 2
0x18006c302  mov     rcx, [rax]
0x18006c305  xor     eax, eax
0x18006c307  cmp     dword ptr [rcx+4], 3
0x18006c30b  mov     rcx, rsi
0x18006c30e  setnz   al
0x18006c311  xor     r9d, r9d
0x18006c314  inc     eax
0x18006c316  xor     r8d, r8d
0x18006c319  mov     [rsp+68h+var_48], eax
0x18006c31d  call    SymCryptEckeySetValue
0x18006c322  test    eax, eax
0x18006c324  jz      short loc_18006C36E
0x18006c326  mov     ecx, eax
0x18006c328  call    SymcryptErrorCodeToNtStatus
0x18006c32d  mov     ebx, eax
0x18006c32f  mov     ecx, eax
0x18006c331  mov     r9d, 197h
0x18006c337  jmp     short loc_18006C35B
0x18006c339  mov     ebx, 0C0000008h
0x18006c33e  mov     r9d, 172h
0x18006c344  mov     ecx, 0C0000008h
0x18006c349  jmp     short loc_18006C35B
0x18006c34b  mov     r9d, 16Ah
0x18006c351  mov     ebx, 0C000000Dh
0x18006c356  mov     ecx, 0C000000Dh
0x18006c35b  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006c362  lea     rdx, aStatus; "Status"
0x18006c369  call    DebugTraceError
0x18006c36e  mov     eax, ebx
0x18006c370  add     rsp, 48h
0x18006c374  pop     rdi
0x18006c375  pop     rsi
0x18006c376  pop     rbp
0x18006c377  pop     rbx
0x18006c378  retn
```
