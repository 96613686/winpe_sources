# MSCryptEcDsaVerifySignature

- ea: `0x18006c080`
- end: `0x18006c24d`
- name: `MSCryptEcDsaVerifySignature`
- size: `461`
- prototype: `__int64 __fastcall(int, __int64, const void *, unsigned int, __int64, unsigned int, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180010270`
- `0x1800102a0`
- `0x18001ffa0`
- `0x1800204a0`
- `0x180056cf0`
- `0x180063170`
- `0x18006c080`

## string_xrefs

- `0x18006c22a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEcDsaVerifySignature(
        int a1,
        __int64 a2,
        const void *a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        int a7)
{
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 v14; // rcx
  unsigned int *v15; // rsi
  __int64 v16; // r15
  unsigned int v17; // eax
  unsigned int v18; // edx
  size_t v19; // rbx
  _BYTE *v20; // rax
  _BYTE *v21; // rsi
  unsigned int v22; // eax
  __int64 v24; // [rsp+90h] [rbp+18h] BYREF

  v24 = 0;
  if ( !a3 || !a4 || a2 || (a7 & 0xFFFFFFF5) != 0 )
  {
    v11 = 4263;
    goto LABEL_20;
  }
  v9 = ValidateEccKey(a1, 1, 0, 1, (__int64)&v24);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 4271;
    v12 = (unsigned int)v9;
LABEL_21:
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v11);
    return v10;
  }
  v13 = v24;
  if ( (*(_BYTE *)(v24 + 32) & 2) == 0 )
  {
    v10 = -1073741816;
    v11 = 4278;
    v12 = 3221225480LL;
    goto LABEL_21;
  }
  v14 = **(_QWORD **)(v24 + 16);
  v15 = (unsigned int *)(v14 + 16);
  if ( a6 != 2 * *(_DWORD *)(v14 + 12) && a6 != 2 * *v15 )
  {
    v11 = 4294;
LABEL_20:
    v12 = 3221225485LL;
    v10 = -1073741811;
    goto LABEL_21;
  }
  v16 = a6;
  v17 = SymCryptEcDsaVerify(*(_QWORD *)(v24 + 24), (_DWORD)a3, a4, a5, a6);
  v10 = SymcryptErrorCodeToNtStatus(v17);
  if ( v10 == -1073700864 && *(_DWORD *)(v13 + 8) == 196614 )
  {
    v18 = *v15;
    if ( a4 >= *v15 && 8 * v18 >= *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 16) + 8LL) + 24LL) )
    {
      v19 = v18;
      v20 = (_BYTE *)SafeAllocaAllocateFromHeap(v18);
      v21 = v20;
      if ( !v20 )
      {
        v10 = -1073741801;
        v11 = 4330;
        v12 = 3221225495LL;
        goto LABEL_21;
      }
      memcpy_0(v20, a3, v19);
      v21[65] &= 1u;
      v22 = SymCryptEcDsaVerify(*(_QWORD *)(v13 + 24), (_DWORD)v21, v19, a5, v16);
      v10 = SymcryptErrorCodeToNtStatus(v22);
      MSCryptFree(v21);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18006c080  mov     r11, rsp
0x18006c083  push    rbx
0x18006c084  push    rbp
0x18006c085  push    rsi
0x18006c086  push    rdi
0x18006c087  push    r14
0x18006c089  push    r15
0x18006c08b  sub     rsp, 48h
0x18006c08f  mov     ebp, r9d
0x18006c092  mov     r14, r8
0x18006c095  mov     qword ptr [r11+18h], 0
0x18006c09d  test    r8, r8
0x18006c0a0  jz      loc_18006C21A
0x18006c0a6  test    r9d, r9d
0x18006c0a9  jz      loc_18006C21A
0x18006c0af  test    rdx, rdx
0x18006c0b2  jnz     loc_18006C21A
0x18006c0b8  test    [rsp+78h+arg_30], 0FFFFFFF5h
0x18006c0c3  jnz     loc_18006C21A
0x18006c0c9  lea     r9d, [rdx+1]
0x18006c0cd  xor     r8d, r8d
0x18006c0d0  lea     rax, [r11+18h]
0x18006c0d4  mov     edx, r9d
0x18006c0d7  mov     [r11-58h], rax
0x18006c0db  call    ValidateEccKey
0x18006c0e0  mov     ebx, eax
0x18006c0e2  test    eax, eax
0x18006c0e4  jns     short loc_18006C0F3
0x18006c0e6  mov     r9d, 10AFh
0x18006c0ec  mov     ecx, eax
0x18006c0ee  jmp     loc_18006C22A
0x18006c0f3  mov     rdi, [rsp+78h+arg_10]
0x18006c0fb  test    byte ptr [rdi+20h], 2
0x18006c0ff  jnz     short loc_18006C116
0x18006c101  mov     ebx, 0C0000008h
0x18006c106  mov     r9d, 10B6h
0x18006c10c  mov     ecx, 0C0000008h
0x18006c111  jmp     loc_18006C22A
0x18006c116  mov     rax, [rdi+10h]
0x18006c11a  mov     rcx, [rax]
0x18006c11d  mov     eax, [rcx+0Ch]
0x18006c120  lea     rsi, [rcx+10h]
0x18006c124  mov     ecx, [rsp+78h+arg_28]
0x18006c12b  add     eax, eax
0x18006c12d  cmp     ecx, eax
0x18006c12f  jz      short loc_18006C144
0x18006c131  mov     eax, [rsi]
0x18006c133  add     eax, eax
0x18006c135  cmp     ecx, eax
0x18006c137  jz      short loc_18006C144
0x18006c139  mov     r9d, 10C6h
0x18006c13f  jmp     loc_18006C220
0x18006c144  mov     r9, [rsp+78h+arg_20]
0x18006c14c  mov     r15, rcx
0x18006c14f  mov     [rsp+78h+var_48], 0
0x18006c157  mov     r8, rbp
0x18006c15a  mov     [rsp+78h+var_58], rcx
0x18006c15f  mov     rdx, r14
0x18006c162  mov     rcx, [rdi+18h]
0x18006c166  call    SymCryptEcDsaVerify
0x18006c16b  mov     ecx, eax
0x18006c16d  call    SymcryptErrorCodeToNtStatus
0x18006c172  mov     ebx, eax
0x18006c174  cmp     eax, 0C000A000h
0x18006c179  jnz     loc_18006C23D
0x18006c17f  cmp     dword ptr [rdi+8], 30006h
0x18006c186  jnz     loc_18006C23D
0x18006c18c  mov     edx, [rsi]
0x18006c18e  cmp     ebp, edx
0x18006c190  jb      loc_18006C23D
0x18006c196  mov     rax, [rdi+10h]
0x18006c19a  mov     rcx, [rax+8]
0x18006c19e  lea     eax, ds:0[rdx*8]
0x18006c1a5  cmp     eax, [rcx+18h]
0x18006c1a8  jb      loc_18006C23D
0x18006c1ae  mov     ecx, edx
0x18006c1b0  mov     ebx, edx
0x18006c1b2  call    SafeAllocaAllocateFromHeap
0x18006c1b7  mov     rsi, rax
0x18006c1ba  test    rax, rax
0x18006c1bd  jnz     short loc_18006C1D1
0x18006c1bf  mov     ebx, 0C0000017h
0x18006c1c4  mov     r9d, 10EAh
0x18006c1ca  mov     ecx, 0C0000017h
0x18006c1cf  jmp     short loc_18006C22A
0x18006c1d1  mov     r8, rbx; Size
0x18006c1d4  mov     rdx, r14; Src
0x18006c1d7  mov     rcx, rsi; void *
0x18006c1da  call    memcpy_0
0x18006c1df  and     byte ptr [rsi+41h], 1
0x18006c1e3  mov     r8, rbx
0x18006c1e6  mov     r9, [rsp+78h+arg_20]
0x18006c1ee  mov     rdx, rsi
0x18006c1f1  mov     rcx, [rdi+18h]
0x18006c1f5  mov     [rsp+78h+var_48], 8
0x18006c1fd  mov     [rsp+78h+var_58], r15
0x18006c202  call    SymCryptEcDsaVerify
0x18006c207  mov     ecx, eax
0x18006c209  call    SymcryptErrorCodeToNtStatus
0x18006c20e  mov     rcx, rsi
0x18006c211  mov     ebx, eax
0x18006c213  call    MSCryptFree
0x18006c218  jmp     short loc_18006C23D
0x18006c21a  mov     r9d, 10A7h
0x18006c220  mov     ecx, 0C000000Dh
0x18006c225  mov     ebx, 0C000000Dh
0x18006c22a  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006c231  lea     rdx, aStatus; "Status"
0x18006c238  call    DebugTraceError
0x18006c23d  mov     eax, ebx
0x18006c23f  add     rsp, 48h
0x18006c243  pop     r15
0x18006c245  pop     r14
0x18006c247  pop     rdi
0x18006c248  pop     rsi
0x18006c249  pop     rbp
0x18006c24a  pop     rbx
0x18006c24b  retn
```
