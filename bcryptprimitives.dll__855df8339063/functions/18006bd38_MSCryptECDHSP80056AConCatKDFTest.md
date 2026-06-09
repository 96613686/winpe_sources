# MSCryptECDHSP80056AConCatKDFTest

- ea: `0x18006bd38`
- end: `0x18006bee5`
- name: `MSCryptECDHSP80056AConCatKDFTest`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800631b4`

## callees

- `0x18000ecb0`
- `0x180010270`
- `0x1800102a0`
- `0x180010bb0`
- `0x180020408`
- `0x1800568e0`
- `0x1800631a8`
- `0x18006bd38`
- `0x18007f790`

## string_xrefs

- `0x18006bdb5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptECDHSP80056AConCatKDFTest(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rsi
  const void *v7; // rdi
  __int64 v8; // r9
  __int64 v9; // rcx
  int v10; // edx
  int v11; // r8d
  _BYTE *v12; // rax
  _DWORD *v14; // [rsp+40h] [rbp-29h] BYREF
  int v15; // [rsp+48h] [rbp-21h] BYREF
  __int128 v16; // [rsp+50h] [rbp-19h] BYREF
  __int128 v17; // [rsp+60h] [rbp-9h] BYREF
  __int128 v18; // [rsp+70h] [rbp+7h]
  __int128 v19; // [rsp+80h] [rbp+17h]

  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v4 = MSCryptCreateSecret(rgbEcDhSharedSecret256, 0x20u, &v14, a4, 196615);
  v5 = v4;
  v6 = 64;
  if ( v4 < 0 )
  {
    v7 = 0;
    v8 = 2521;
LABEL_3:
    v9 = (unsigned int)v4;
LABEL_4:
    DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v8);
    goto LABEL_13;
  }
  *(_QWORD *)&v17 = 0x800000008LL;
  *((_QWORD *)&v17 + 1) = algorithmID;
  *((_QWORD *)&v18 + 1) = "ALICE123";
  *((_QWORD *)&v19 + 1) = "BOBBY456";
  *(_QWORD *)&v18 = 0x900000008LL;
  *(_QWORD *)&v19 = 0xA00000008LL;
  *((_QWORD *)&v16 + 1) = &v17;
  *(_QWORD *)&v16 = 0x300000000LL;
  v7 = (const void *)SafeAllocaAllocateFromHeap(64);
  if ( !v7 )
  {
    v8 = 2550;
LABEL_7:
    v5 = -1073741823;
    v9 = 3221225473LL;
    goto LABEL_4;
  }
  v4 = MSCryptDeriveKey((__int64)v14, L"SP800_56A_CONCAT", (signed __int64)&v16, (__int64)v7, 64, (__int64)&v15, 0);
  v5 = v4;
  if ( v4 < 0 )
  {
    v8 = 2564;
    goto LABEL_3;
  }
  if ( memcmp_0(v7, rgbEcDhDerivedKey256, 0x40u) )
  {
    v8 = 2572;
    goto LABEL_7;
  }
  v5 = 0;
LABEL_13:
  if ( v14 )
    MSCryptDestroySecret(v14, v10, v11);
  if ( v7 )
  {
    v12 = v7;
    do
    {
      *v12++ = 0;
      --v6;
    }
    while ( v6 );
    MSCryptFree(v7);
  }
  return v5;
}

```

## disassembly

```asm
0x18006bd38  push    rbp
0x18006bd3a  push    rbx
0x18006bd3b  push    rsi
0x18006bd3c  push    rdi
0x18006bd3d  lea     rbp, [rsp-3Fh]
0x18006bd42  sub     rsp, 0A8h
0x18006bd49  mov     rax, cs:__security_cookie
0x18006bd50  xor     rax, rsp
0x18006bd53  mov     [rbp+57h+var_30], rax
0x18006bd57  xorps   xmm1, xmm1
0x18006bd5a  mov     [rbp+57h+var_80], 0
0x18006bd62  xorps   xmm0, xmm0
0x18006bd65  mov     [rbp+57h+var_78], 0
0x18006bd6c  lea     r8, [rbp+57h+var_80]
0x18006bd70  mov     [rsp+0C0h+var_A0], 30007h; int
0x18006bd78  mov     edx, 20h ; ' '; Size
0x18006bd7d  lea     rcx, rgbEcDhSharedSecret256; Src
0x18006bd84  movups  [rbp+57h+var_70], xmm0
0x18006bd88  movups  [rbp+57h+var_60], xmm1
0x18006bd8c  movups  [rbp+57h+var_50], xmm1
0x18006bd90  movups  [rbp+57h+var_40], xmm1
0x18006bd94  call    MSCryptCreateSecret
0x18006bd99  mov     ebx, eax
0x18006bd9b  mov     esi, 40h ; '@'
0x18006bda0  test    eax, eax
0x18006bda2  jns     short loc_18006BDC6
0x18006bda4  xor     edi, edi
0x18006bda6  mov     r9d, 9D9h
0x18006bdac  mov     ecx, eax
0x18006bdae  lea     rdx, aStatus; "Status"
0x18006bdb5  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006bdbc  call    DebugTraceError
0x18006bdc1  jmp     loc_18006BE9E
0x18006bdc6  mov     ecx, 8
0x18006bdcb  mov     dword ptr [rbp+57h+var_50+4], 9
0x18006bdd2  lea     rax, algorithmID
0x18006bdd9  mov     dword ptr [rbp+57h+var_60], ecx
0x18006bddc  mov     qword ptr [rbp+57h+var_60+8], rax
0x18006bde0  lea     rax, partyUInfo; "ALICE123"
0x18006bde7  mov     qword ptr [rbp+57h+var_50+8], rax
0x18006bdeb  lea     rax, partyVInfo; "BOBBY456"
0x18006bdf2  mov     qword ptr [rbp+57h+var_40+8], rax
0x18006bdf6  lea     rax, [rbp+57h+var_60]
0x18006bdfa  mov     dword ptr [rbp+57h+var_60+4], ecx
0x18006bdfd  mov     dword ptr [rbp+57h+var_50], ecx
0x18006be00  mov     dword ptr [rbp+57h+var_40], ecx
0x18006be03  mov     rcx, rsi
0x18006be06  mov     qword ptr [rbp+57h+var_70+8], rax
0x18006be0a  mov     dword ptr [rbp+57h+var_40+4], 0Ah
0x18006be11  mov     dword ptr [rbp+57h+var_70+4], 3
0x18006be18  mov     dword ptr [rbp+57h+var_70], 0
0x18006be1f  call    SafeAllocaAllocateFromHeap
0x18006be24  mov     rdi, rax
0x18006be27  test    rax, rax
0x18006be2a  jnz     short loc_18006BE41
0x18006be2c  mov     r9d, 9F6h
0x18006be32  mov     ebx, 0C0000001h
0x18006be37  mov     ecx, 0C0000001h
0x18006be3c  jmp     loc_18006BDAE
0x18006be41  mov     rcx, [rbp+57h+var_80]
0x18006be45  lea     rax, [rbp+57h+var_78]
0x18006be49  mov     [rsp+0C0h+var_90], 0
0x18006be51  lea     r8, [rbp+57h+var_70]
0x18006be55  mov     [rsp+0C0h+var_98], rax
0x18006be5a  lea     rdx, aSp80056aConcat; "SP800_56A_CONCAT"
0x18006be61  mov     r9, rdi
0x18006be64  mov     [rsp+0C0h+var_A0], esi
0x18006be68  call    MSCryptDeriveKey
0x18006be6d  mov     ebx, eax
0x18006be6f  test    eax, eax
0x18006be71  jns     short loc_18006BE7E
0x18006be73  mov     r9d, 0A04h
0x18006be79  jmp     loc_18006BDAC
0x18006be7e  mov     r8, rsi; Size
0x18006be81  lea     rdx, rgbEcDhDerivedKey256; Buf2
0x18006be88  mov     rcx, rdi; Buf1
0x18006be8b  call    memcmp_0
0x18006be90  test    eax, eax
0x18006be92  jz      short loc_18006BE9C
0x18006be94  mov     r9d, 0A0Ch
0x18006be9a  jmp     short loc_18006BE32
0x18006be9c  xor     ebx, ebx
0x18006be9e  cmp     [rbp+57h+var_80], 0
0x18006bea3  jz      short loc_18006BEAE
0x18006bea5  mov     rcx, [rbp+57h+var_80]
0x18006bea9  call    MSCryptDestroySecret
0x18006beae  test    rdi, rdi
0x18006beb1  jz      short loc_18006BECA
0x18006beb3  mov     rax, rdi
0x18006beb6  mov     byte ptr [rax], 0
0x18006beb9  inc     rax
0x18006bebc  sub     rsi, 1
0x18006bec0  jnz     short loc_18006BEB6
0x18006bec2  mov     rcx, rdi
0x18006bec5  call    MSCryptFree
0x18006beca  mov     eax, ebx
0x18006becc  mov     rcx, [rbp+57h+var_30]
0x18006bed0  xor     rcx, rsp; StackCookie
0x18006bed3  call    __security_check_cookie
0x18006bed8  add     rsp, 0A8h
0x18006bedf  pop     rdi
0x18006bee0  pop     rsi
0x18006bee1  pop     rbx
0x18006bee2  pop     rbp
0x18006bee3  retn
```
