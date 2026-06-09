# MSCryptSetRsaProperty

- ea: `0x18003c4f0`
- end: `0x18003c5eb`
- name: `MSCryptSetRsaProperty`
- size: `251`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, int *, int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18003c4f0`
- `0x18003cfd4`
- `0x18007f765`

## string_xrefs

- `0x18003c56f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003c58d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180081f08`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptSetRsaProperty(__int64 a1, const wchar_t *a2, int *a3, int a4, int a5)
{
  int v8; // edx
  __int64 v9; // rbx
  unsigned int v10; // ebx
  __int64 v12; // r9
  int v13; // ecx

  if ( a5 )
  {
    v10 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        88);
  }
  else
  {
    v9 = validateMSCryptRsaKey();
    if ( v9 )
    {
      if ( !wcscmp_0(a2, L"KeyLength") || !wcscmp_0(a2, L"KeyStrength") )
      {
        if ( a4 == 4 )
        {
          v13 = *a3;
          if ( (unsigned int)(*a3 - 512) <= 0x3E00 && (v13 & 7) == 0 )
          {
            *(_DWORD *)(v9 + 12) = v13;
            return 0;
          }
          v12 = 890;
        }
        else
        {
          v12 = 878;
        }
        v10 = -1073741811;
        DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v12);
        return v10;
      }
      return (unsigned int)-1073741637;
    }
    else
    {
      v10 = -1073741816;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v8,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          (unsigned int)"Status",
          8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          97);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18003c4f0  push    rbx
0x18003c4f2  push    rsi
0x18003c4f3  push    rdi
0x18003c4f4  push    r14
0x18003c4f6  sub     rsp, 48h
0x18003c4fa  cmp     [rsp+68h+arg_20], 0
0x18003c502  mov     esi, r9d
0x18003c505  mov     r14, r8
0x18003c508  mov     rdi, rdx
0x18003c50b  jnz     short loc_18003C549
0x18003c50d  call    validateMSCryptRsaKey
0x18003c512  mov     rbx, rax
0x18003c515  test    rax, rax
0x18003c518  jnz     loc_18003C5B3
0x18003c51e  mov     ebx, 0C0000008h
0x18003c523  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c52a  lea     rax, WPP_GLOBAL_Control
0x18003c531  cmp     rcx, rax
0x18003c534  jz      short loc_18003C53C
0x18003c536  test    byte ptr [rcx+1Ch], 1
0x18003c53a  jnz     short loc_18003C585
0x18003c53c  mov     eax, ebx
0x18003c53e  add     rsp, 48h
0x18003c542  pop     r14
0x18003c544  pop     rdi
0x18003c545  pop     rsi
0x18003c546  pop     rbx
0x18003c547  retn
0x18003c549  mov     ebx, 0C000000Dh
0x18003c54e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c555  lea     rax, WPP_GLOBAL_Control
0x18003c55c  cmp     rcx, rax
0x18003c55f  jz      short loc_18003C53C
0x18003c561  test    byte ptr [rcx+1Ch], 1
0x18003c565  jz      short loc_18003C53C
0x18003c567  mov     [rsp+68h+var_38], 358h
0x18003c56f  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003c576  mov     [rsp+68h+var_40], r8
0x18003c57b  mov     [rsp+68h+var_48], 0C000000Dh
0x18003c583  jmp     short loc_18003C5A1
0x18003c585  mov     [rsp+68h+var_38], 361h
0x18003c58d  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003c594  mov     [rsp+68h+var_40], r8
0x18003c599  mov     [rsp+68h+var_48], 0C0000008h
0x18003c5a1  mov     rcx, [rcx+10h]
0x18003c5a5  lea     r9, aStatus; "Status"
0x18003c5ac  call    WPP_SF_sDsd
0x18003c5b1  jmp     short loc_18003C53C
0x18003c5b3  lea     rdx, aKeylength; "KeyLength"
0x18003c5ba  mov     rcx, rdi; String1
0x18003c5bd  call    wcscmp_0
0x18003c5c2  test    eax, eax
0x18003c5c4  jz      loc_180081ED6
0x18003c5ca  lea     rdx, aKeystrength; "KeyStrength"
0x18003c5d1  mov     rcx, rdi; String1
0x18003c5d4  call    wcscmp_0
0x18003c5d9  test    eax, eax
0x18003c5db  jz      loc_180081ED6
0x18003c5e1  mov     ebx, 0C00000BBh
0x18003c5e6  jmp     loc_18003C53C
0x180081ed6  cmp     esi, 4
0x180081ed9  jz      short loc_180081EE3
0x180081edb  mov     r9d, 36Eh
0x180081ee1  jmp     short loc_180081F08
0x180081ee3  mov     ecx, [r14]
0x180081ee6  lea     eax, [rcx-200h]
0x180081eec  cmp     eax, 3E00h
0x180081ef1  ja      short loc_180081F02
0x180081ef3  test    cl, 7
0x180081ef6  jnz     short loc_180081F02
0x180081ef8  mov     [rbx+0Ch], ecx
0x180081efb  xor     ebx, ebx
0x180081efd  jmp     loc_18003C53C
0x180081f02  mov     r9d, 37Ah
0x180081f08  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180081f0f  mov     ecx, 0C000000Dh
0x180081f14  lea     rdx, aStatus; "Status"
0x180081f1b  mov     ebx, 0C000000Dh
0x180081f20  call    DebugTraceError
0x180081f25  nop
0x180081f26  jmp     loc_18003C53C
```
