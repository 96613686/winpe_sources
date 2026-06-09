# AesCcm

- ea: `0x18003d9f0`
- end: `0x18003db8a`
- name: `AesCcm`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180031b10`
- `0x18003d9f0`
- `0x18003db90`
- `0x18003f24c`

## string_xrefs

- `0x18003dad4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x18008200e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`

## pseudocode

```c
__int64 __fastcall AesCcm(
        int a1,
        __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int a7,
        __int64 a8,
        __int64 a9,
        unsigned int a10,
        __int64 a11,
        unsigned int a12,
        int a13)
{
  int v14; // edx
  int v15; // r8d
  __int64 v16; // r9
  __int64 v17; // r10
  int v18; // r11d
  unsigned int v19; // ebx
  __int64 v21; // r9
  __int64 v22; // rcx

  if ( (unsigned int)SymCryptCcmValidateParameters(a1, a5, a3, a7, a12) )
  {
    v19 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
        202);
  }
  else
  {
    if ( v15 != 16 )
    {
      v19 = -1073741811;
      v21 = 209;
      v22 = 3221225485LL;
      goto LABEL_13;
    }
    v19 = 0;
    if ( !a13 )
    {
      if ( !(unsigned int)SymCryptCcmDecrypt(a10, a1, v18, v14, a9, a10, a6, a8, v16, a11, v17) )
        return v19;
      v19 = -1073700862;
      v21 = 232;
      v22 = 3221266434LL;
LABEL_13:
      DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c", v21);
      return v19;
    }
    if ( a13 == 1 )
      SymCryptCcmEncrypt(a10, a1, v18, v14, a9, a10, a6, a8, v16, a11, v17);
  }
  return v19;
}

```

## disassembly

```asm
0x18003d9f0  mov     [rsp+arg_0], rbx
0x18003d9f5  push    rdi
0x18003d9f6  sub     rsp, 60h
0x18003d9fa  mov     r10d, [rsp+68h+arg_58]
0x18003da02  mov     r11, r9
0x18003da05  mov     r9d, [rsp+68h+arg_30]
0x18003da0d  mov     rdi, rcx
0x18003da10  mov     edx, [rsp+68h+arg_20]
0x18003da17  mov     [rsp+68h+var_48], r10
0x18003da1c  call    SymCryptCcmValidateParameters
0x18003da21  test    eax, eax
0x18003da23  jnz     loc_18003DAB2
0x18003da29  cmp     r8d, 10h
0x18003da2d  jnz     loc_18003DAFE
0x18003da33  mov     ecx, [rsp+68h+arg_60]
0x18003da3a  xor     ebx, ebx
0x18003da3c  test    ecx, ecx
0x18003da3e  jnz     loc_18003DB13
0x18003da44  mov     rax, [rsp+68h+arg_50]
0x18003da4c  mov     r8, r11
0x18003da4f  mov     ecx, [rsp+68h+arg_48]
0x18003da56  mov     [rsp+68h+var_18], r10
0x18003da5b  mov     [rsp+68h+var_20], rax
0x18003da60  mov     rax, [rsp+68h+arg_38]
0x18003da68  mov     [rsp+68h+var_28], r9
0x18003da6d  mov     r9d, edx
0x18003da70  mov     [rsp+68h+var_30], rax
0x18003da75  mov     rdx, rdi
0x18003da78  mov     rax, [rsp+68h+arg_28]
0x18003da80  mov     [rsp+68h+var_38], rax
0x18003da85  mov     rax, [rsp+68h+arg_40]
0x18003da8d  mov     [rsp+68h+var_40], rcx
0x18003da92  mov     [rsp+68h+var_48], rax
0x18003da97  call    SymCryptCcmDecrypt
0x18003da9c  test    eax, eax
0x18003da9e  jnz     loc_18003DB75
0x18003daa4  mov     eax, ebx
0x18003daa6  mov     rbx, [rsp+68h+arg_0]
0x18003daab  add     rsp, 60h
0x18003daaf  pop     rdi
0x18003dab0  retn
0x18003dab2  mov     ebx, 0C000000Dh
0x18003dab7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dabe  lea     rax, WPP_GLOBAL_Control
0x18003dac5  cmp     rcx, rax
0x18003dac8  jz      short loc_18003DAA4
0x18003daca  test    byte ptr [rcx+1Ch], 1
0x18003dace  jz      short loc_18003DAA4
0x18003dad0  mov     rcx, [rcx+10h]
0x18003dad4  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003dadb  mov     dword ptr [rsp+68h+var_38], 0CAh
0x18003dae3  lea     r9, aStatus; "Status"
0x18003daea  mov     [rsp+68h+var_40], r8
0x18003daef  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x18003daf7  call    WPP_SF_sDsd
0x18003dafc  jmp     short loc_18003DAA4
0x18003dafe  mov     ebx, 0C000000Dh
0x18003db03  mov     r9d, 0D1h
0x18003db09  mov     ecx, 0C000000Dh
0x18003db0e  jmp     loc_18008200E
0x18003db13  cmp     ecx, 1
0x18003db16  jnz     short loc_18003DAA4
0x18003db18  mov     rax, [rsp+68h+arg_50]
0x18003db20  mov     r8, r11
0x18003db23  mov     ecx, [rsp+68h+arg_48]
0x18003db2a  mov     [rsp+68h+var_18], r10
0x18003db2f  mov     [rsp+68h+var_20], rax
0x18003db34  mov     rax, [rsp+68h+arg_38]
0x18003db3c  mov     [rsp+68h+var_28], r9
0x18003db41  mov     r9, rdx
0x18003db44  mov     [rsp+68h+var_30], rax
0x18003db49  mov     rdx, rdi
0x18003db4c  mov     rax, [rsp+68h+arg_28]
0x18003db54  mov     [rsp+68h+var_38], rax
0x18003db59  mov     rax, [rsp+68h+arg_40]
0x18003db61  mov     [rsp+68h+var_40], rcx
0x18003db66  mov     [rsp+68h+var_48], rax
0x18003db6b  call    SymCryptCcmEncrypt
0x18003db70  jmp     loc_18003DAA4
0x18003db75  mov     ebx, 0C000A002h
0x18003db7a  mov     r9d, 0E8h
0x18003db80  mov     ecx, 0C000A002h
0x18003db85  jmp     loc_18008200E
0x18008200e  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180082015  lea     rdx, aStatus; "Status"
0x18008201c  call    DebugTraceError
0x180082021  nop
0x180082022  jmp     loc_18003DAA4
```
