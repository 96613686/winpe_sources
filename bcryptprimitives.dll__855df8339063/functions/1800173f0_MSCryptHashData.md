# MSCryptHashData

- ea: `0x1800173f0`
- end: `0x180017587`
- name: `MSCryptHashData`
- size: `407`
- prototype: ``
- caller_count: `8`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800117d0`
- `0x180016af4`
- `0x180016db0`
- `0x180053de4`
- `0x180058a04`
- `0x180063a78`
- `0x18006c5c4`
- `0x18007d95c`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x1800173f0`
- `0x180017590`
- `0x1800178a8`
- `0x1800593e0`
- `0x18007f790`

## string_xrefs

- `0x18001745b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x180017503`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18001756d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x180080daf`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptHashData(__int64 a1, __int64 a2, int a3, int a4)
{
  unsigned int v6; // edi
  int v7; // eax
  unsigned int v9; // r8d
  __int64 v10; // rdx
  _BYTE v11[64]; // [rsp+40h] [rbp-68h] BYREF

  if ( (a4 & 0xFFFFFFFB) != 0 )
  {
    v6 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        253);
  }
  else if ( !a1 || *(_DWORD *)(a1 + 4) != 1297303624 || *(_DWORD *)(a1 + 20) || *(_DWORD *)(a1 + 36) )
  {
    v6 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        8);
  }
  else if ( (a4 & 4) != 0 )
  {
    if ( *(_BYTE *)(a1 + 40) )
      return (unsigned int)MSCryptHashDataTlsCbcHmacVerify();
    else
      return (unsigned int)-1073741811;
  }
  else
  {
    if ( !a3 )
      return 0;
    if ( *(_DWORD *)(a1 + 28) == 1 && !*(_DWORD *)(a1 + 32) )
    {
      v9 = *(_DWORD *)(a1 + 112);
      v10 = 0;
      for ( *(_DWORD *)(a1 + 32) = 1; (unsigned int)v10 < v9; v10 = (unsigned int)(v10 + 1) )
        v11[v10] = *(_BYTE *)(v10 + a1 + 48) ^ 0x36;
      v6 = MSCryptHashDataInternal(a1, v11);
      SymCryptWipeAsm(v11, 64);
      if ( (v6 & 0x80000000) != 0 )
      {
        DebugTraceError(v6, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", 2356);
        return v6;
      }
    }
    v7 = MSCryptHashDataInternal(a1, a2);
    v6 = v7;
    if ( v7 < 0 )
      DebugTraceError(
        (unsigned int)v7,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        2367);
    else
      return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x1800173f0  mov     [rsp+arg_18], rbx
0x1800173f5  push    rbp
0x1800173f6  push    rsi
0x1800173f7  push    rdi
0x1800173f8  sub     rsp, 90h
0x1800173ff  mov     rax, cs:__security_cookie
0x180017406  xor     rax, rsp
0x180017409  mov     [rsp+0A8h+var_28], rax
0x180017411  mov     esi, r8d
0x180017414  mov     rbp, rdx
0x180017417  mov     rbx, rcx
0x18001741a  test    r9d, 0FFFFFFFBh
0x180017421  jnz     loc_1800174DD
0x180017427  test    rcx, rcx
0x18001742a  jz      short loc_180017435
0x18001742c  cmp     dword ptr [rcx+4], 4D534848h
0x180017433  jz      short loc_180017474
0x180017435  mov     edi, 0C0000008h
0x18001743a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017441  lea     rax, WPP_GLOBAL_Control
0x180017448  cmp     rcx, rax
0x18001744b  jz      short loc_1800174B7
0x18001744d  test    byte ptr [rcx+1Ch], 1
0x180017451  jz      short loc_1800174B7
0x180017453  mov     [rsp+0A8h+var_78], 908h
0x18001745b  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017462  mov     [rsp+0A8h+var_80], rax
0x180017467  mov     [rsp+0A8h+var_88], 0C0000008h
0x18001746f  jmp     loc_180017517
0x180017474  test    rbx, rbx
0x180017477  jz      short loc_180017435
0x180017479  cmp     dword ptr [rcx+14h], 0
0x18001747d  jnz     short loc_180017435
0x18001747f  cmp     dword ptr [rcx+24h], 0
0x180017483  jnz     short loc_180017435
0x180017485  test    r9b, 4
0x180017489  jnz     loc_180017529
0x18001748f  test    esi, esi
0x180017491  jz      short loc_1800174B5
0x180017493  cmp     dword ptr [rcx+1Ch], 1
0x180017497  jz      loc_180017542
0x18001749d  mov     r8d, esi
0x1800174a0  mov     rdx, rbp
0x1800174a3  mov     rcx, rbx
0x1800174a6  call    MSCryptHashDataInternal
0x1800174ab  mov     edi, eax
0x1800174ad  test    eax, eax
0x1800174af  js      loc_180017567
0x1800174b5  xor     edi, edi
0x1800174b7  mov     eax, edi
0x1800174b9  mov     rcx, [rsp+0A8h+var_28]
0x1800174c1  xor     rcx, rsp; StackCookie
0x1800174c4  call    __security_check_cookie
0x1800174c9  mov     rbx, [rsp+0A8h+arg_18]
0x1800174d1  add     rsp, 90h
0x1800174d8  pop     rdi
0x1800174d9  pop     rsi
0x1800174da  pop     rbp
0x1800174db  retn
0x1800174dd  mov     edi, 0C000000Dh
0x1800174e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800174e9  lea     rax, WPP_GLOBAL_Control
0x1800174f0  cmp     rcx, rax
0x1800174f3  jz      short loc_1800174B7
0x1800174f5  test    byte ptr [rcx+1Ch], 1
0x1800174f9  jz      short loc_1800174B7
0x1800174fb  mov     [rsp+0A8h+var_78], 8FDh
0x180017503  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001750a  mov     [rsp+0A8h+var_80], rax
0x18001750f  mov     [rsp+0A8h+var_88], 0C000000Dh
0x180017517  mov     rcx, [rcx+10h]
0x18001751b  lea     r9, aStatus; "Status"
0x180017522  call    WPP_SF_sDsd
0x180017527  jmp     short loc_1800174B7
0x180017529  cmp     byte ptr [rcx+28h], 0
0x18001752d  jnz     short loc_180017536
0x18001752f  mov     edi, 0C000000Dh
0x180017534  jmp     short loc_1800174B7
0x180017536  call    MSCryptHashDataTlsCbcHmacVerify
0x18001753b  mov     edi, eax
0x18001753d  jmp     loc_1800174B7
0x180017542  cmp     dword ptr [rcx+20h], 0
0x180017546  jnz     loc_18001749D
0x18001754c  mov     r8d, [rcx+70h]
0x180017550  xor     edx, edx
0x180017552  mov     dword ptr [rcx+20h], 1
0x180017559  test    r8d, r8d
0x18001755c  jnz     loc_180080D74
0x180017562  jmp     loc_180080D86
0x180017567  mov     r9d, 93Fh
0x18001756d  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017574  lea     rdx, aStatus; "Status"
0x18001757b  mov     ecx, eax
0x18001757d  call    DebugTraceError
0x180017582  jmp     loc_1800174B7
0x180080d74  movzx   eax, byte ptr [rdx+rcx+30h]
0x180080d79  xor     al, 36h
0x180080d7b  mov     [rsp+rdx+0A8h+var_68], al
0x180080d7f  inc     edx
0x180080d81  cmp     edx, r8d
0x180080d84  jb      short loc_180080D74
0x180080d86  lea     rdx, [rsp+0A8h+var_68]
0x180080d8b  call    MSCryptHashDataInternal
0x180080d90  mov     edx, 40h ; '@'
0x180080d95  lea     rcx, [rsp+0A8h+var_68]
0x180080d9a  mov     edi, eax
0x180080d9c  call    SymCryptWipeAsm
0x180080da1  test    edi, edi
0x180080da3  jns     loc_18001749D
0x180080da9  mov     r9d, 934h
0x180080daf  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180080db6  lea     rdx, aStatus; "Status"
0x180080dbd  mov     ecx, edi
0x180080dbf  call    DebugTraceError
0x180080dc4  nop
0x180080dc5  jmp     loc_1800174B7
```
