# MSCryptDsaGenerateKeyPair

- ea: `0x1800528e0`
- end: `0x180052ae8`
- name: `MSCryptDsaGenerateKeyPair`
- size: `520`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180010270`
- `0x1800102a0`
- `0x1800528e0`
- `0x18005723c`
- `0x180058288`

## string_xrefs

- `0x180052978`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`
- `0x1800529f9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`
- `0x180052a55`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`
- `0x180052ab3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptDsaGenerateKeyPair(_DWORD *a1, _QWORD *a2, unsigned int a3, int a4)
{
  __int64 v6; // r9
  unsigned int v7; // ebx
  __int64 v8; // rax
  unsigned int *v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // edx
  int v15; // r8d
  __int64 v16; // rax
  unsigned int *v17; // rcx

  if ( a1 && a2 && !a4 )
  {
    if ( a3 && ((a3 & 0x3F) != 0 || a3 - 512 > 0xA00) )
    {
      v6 = 161;
LABEL_25:
      v10 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v6);
      v11 = 1186;
      v12 = 3221225485LL;
      goto LABEL_26;
    }
    if ( *a1 != 16 || a1[1] != 1297301836 || a1[2] != 196611 )
    {
      v6 = 175;
      goto LABEL_25;
    }
    if ( a3 )
      v7 = a3 >> 3;
    else
      v7 = 128;
    v8 = SafeAllocaAllocateFromHeap(48);
    v9 = (unsigned int *)v8;
    if ( !v8 )
    {
      v10 = -1073741801;
      v11 = 1198;
      v12 = 3221225495LL;
LABEL_26:
      DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v11);
      return v10;
    }
    *(_OWORD *)v8 = 0;
    *(_OWORD *)(v8 + 16) = 0;
    *(_OWORD *)(v8 + 32) = 0;
    *(_DWORD *)v8 = 48;
    *(_DWORD *)(v8 + 4) = 1297304409;
    *(_DWORD *)(v8 + 8) = a1[2];
    *(_DWORD *)(v8 + 12) = v7;
    SetKeyPropertiesBasedOnKeyLength(v7, v8);
    v13 = SymCryptDlgroupAllocate(8 * v9[3], 8 * v9[4]);
    *((_QWORD *)v9 + 4) = v13;
    if ( v13 )
    {
      v10 = 0;
      *((_QWORD *)v9 + 5) = 0;
      *a2 = v9;
    }
    else
    {
      v10 = -1073741801;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          v15,
          (unsigned int)"Status",
          23,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c",
          193);
      v16 = *v9;
      v17 = v9;
      if ( *v9 )
      {
        do
        {
          *(_BYTE *)v9 = 0;
          v9 = (unsigned int *)((char *)v9 + 1);
          --v16;
        }
        while ( v16 );
      }
      MSCryptFree(v17);
    }
  }
  else
  {
    v10 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c",
        151);
  }
  return v10;
}

```

## disassembly

```asm
0x1800528e0  push    rbx
0x1800528e2  push    rsi
0x1800528e3  push    rdi
0x1800528e4  push    r14
0x1800528e6  sub     rsp, 48h
0x1800528ea  mov     ebx, r8d
0x1800528ed  mov     r14, rdx
0x1800528f0  mov     rsi, rcx
0x1800528f3  test    rcx, rcx
0x1800528f6  jz      loc_180052A91
0x1800528fc  test    rdx, rdx
0x1800528ff  jz      loc_180052A91
0x180052905  test    r9d, r9d
0x180052908  jnz     loc_180052A91
0x18005290e  test    ebx, ebx
0x180052910  jz      short loc_180052930
0x180052912  test    bl, 3Fh
0x180052915  jnz     short loc_180052925
0x180052917  lea     eax, [r8-200h]
0x18005291e  cmp     eax, 0A00h
0x180052923  jbe     short loc_180052930
0x180052925  mov     r9d, 0A1h
0x18005292b  jmp     loc_180052A55
0x180052930  cmp     dword ptr [rcx], 10h
0x180052933  jnz     loc_180052A4F
0x180052939  cmp     dword ptr [rcx+4], 4D53414Ch
0x180052940  jnz     loc_180052A4F
0x180052946  cmp     dword ptr [rcx+8], 30003h
0x18005294d  jnz     loc_180052A4F
0x180052953  test    ebx, ebx
0x180052955  jnz     short loc_18005295E
0x180052957  mov     ebx, 80h
0x18005295c  jmp     short loc_180052961
0x18005295e  shr     ebx, 3
0x180052961  mov     ecx, 30h ; '0'
0x180052966  call    SafeAllocaAllocateFromHeap
0x18005296b  mov     rdi, rax
0x18005296e  test    rax, rax
0x180052971  jnz     short loc_18005298F
0x180052973  mov     ebx, 0C0000017h
0x180052978  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005297f  mov     r9d, 4AEh
0x180052985  mov     ecx, 0C0000017h
0x18005298a  jmp     loc_180052A83
0x18005298f  xorps   xmm0, xmm0
0x180052992  mov     rdx, rdi
0x180052995  movups  xmmword ptr [rax], xmm0
0x180052998  mov     ecx, ebx
0x18005299a  movups  xmmword ptr [rax+10h], xmm0
0x18005299e  movups  xmmword ptr [rax+20h], xmm0
0x1800529a2  mov     dword ptr [rax], 30h ; '0'
0x1800529a8  mov     dword ptr [rax+4], 4D534B59h
0x1800529af  mov     eax, [rsi+8]
0x1800529b2  mov     [rdi+8], eax
0x1800529b5  mov     [rdi+0Ch], ebx
0x1800529b8  call    SetKeyPropertiesBasedOnKeyLength
0x1800529bd  mov     edx, [rdi+10h]
0x1800529c0  mov     ecx, [rdi+0Ch]
0x1800529c3  shl     edx, 3
0x1800529c6  shl     ecx, 3
0x1800529c9  call    SymCryptDlgroupAllocate
0x1800529ce  mov     [rdi+20h], rax
0x1800529d2  test    rax, rax
0x1800529d5  jnz     short loc_180052A41
0x1800529d7  mov     ebx, 0C0000017h
0x1800529dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800529e3  lea     rax, WPP_GLOBAL_Control
0x1800529ea  cmp     rcx, rax
0x1800529ed  jz      short loc_180052A21
0x1800529ef  test    byte ptr [rcx+1Ch], 1
0x1800529f3  jz      short loc_180052A21
0x1800529f5  mov     rcx, [rcx+10h]
0x1800529f9  lea     rsi, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052a00  mov     [rsp+68h+var_38], 4C1h
0x180052a08  lea     r9, aStatus; "Status"
0x180052a0f  mov     [rsp+68h+var_40], rsi
0x180052a14  mov     [rsp+68h+var_48], 0C0000017h
0x180052a1c  call    WPP_SF_sDsd
0x180052a21  mov     eax, [rdi]
0x180052a23  mov     rcx, rdi
0x180052a26  test    rax, rax
0x180052a29  jz      short loc_180052A37
0x180052a2b  mov     byte ptr [rdi], 0
0x180052a2e  inc     rdi
0x180052a31  sub     rax, 1
0x180052a35  jnz     short loc_180052A2B
0x180052a37  call    MSCryptFree
0x180052a3c  jmp     loc_180052ADB
0x180052a41  xor     ebx, ebx
0x180052a43  mov     [rdi+28h], rbx
0x180052a47  mov     [r14], rdi
0x180052a4a  jmp     loc_180052ADB
0x180052a4f  mov     r9d, 0AFh
0x180052a55  lea     rsi, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052a5c  mov     ecx, 0C000000Dh
0x180052a61  mov     r8, rsi
0x180052a64  lea     rdx, aStatus; "Status"
0x180052a6b  mov     ebx, 0C000000Dh
0x180052a70  call    DebugTraceError
0x180052a75  mov     r9d, 4A2h
0x180052a7b  mov     r8, rsi
0x180052a7e  mov     ecx, 0C000000Dh
0x180052a83  lea     rdx, aStatus; "Status"
0x180052a8a  call    DebugTraceError
0x180052a8f  jmp     short loc_180052ADB
0x180052a91  mov     ebx, 0C000000Dh
0x180052a96  mov     rcx, cs:WPP_GLOBAL_Control
0x180052a9d  lea     rax, WPP_GLOBAL_Control
0x180052aa4  cmp     rcx, rax
0x180052aa7  jz      short loc_180052ADB
0x180052aa9  test    byte ptr [rcx+1Ch], 1
0x180052aad  jz      short loc_180052ADB
0x180052aaf  mov     rcx, [rcx+10h]
0x180052ab3  lea     rsi, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052aba  mov     [rsp+68h+var_38], 497h
0x180052ac2  lea     r9, aStatus; "Status"
0x180052ac9  mov     [rsp+68h+var_40], rsi
0x180052ace  mov     [rsp+68h+var_48], 0C000000Dh
0x180052ad6  call    WPP_SF_sDsd
0x180052adb  mov     eax, ebx
0x180052add  add     rsp, 48h
0x180052ae1  pop     r14
0x180052ae3  pop     rdi
0x180052ae4  pop     rsi
0x180052ae5  pop     rbx
0x180052ae6  retn
```
