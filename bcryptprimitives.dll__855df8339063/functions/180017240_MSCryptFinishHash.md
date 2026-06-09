# MSCryptFinishHash

- ea: `0x180017240`
- end: `0x1800173e0`
- name: `MSCryptFinishHash`
- size: `416`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800117d0`
- `0x180016af4`
- `0x180016db0`
- `0x180058a04`
- `0x18006c5c4`
- `0x18007d95c`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180017240`
- `0x180017590`
- `0x1800185c0`
- `0x1800185e0`
- `0x1800593e0`
- `0x18007f790`

## string_xrefs

- `0x18001733f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x180080c75`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptFinishHash(__int64 a1, __int64 a2, int a3, unsigned int a4)
{
  unsigned int *v7; // rax
  __int64 v8; // rdx
  unsigned int v9; // r8d
  __int64 v10; // r9
  unsigned int *v11; // rdi
  int v12; // r14d
  int v13; // edx
  int v14; // ebx
  __int64 v16; // r9
  __int64 v17; // rcx
  unsigned int v18; // r8d
  __int64 v19; // rdx
  int v20; // eax
  unsigned int v21; // r9d
  __int64 i; // r8
  _BYTE v23[16]; // [rsp+40h] [rbp-D8h] BYREF
  _BYTE v24[64]; // [rsp+50h] [rbp-C8h] BYREF
  _BYTE v25[64]; // [rsp+90h] [rbp-88h] BYREF

  if ( (a4 & 0xFFFFFFFE) != 0 )
  {
    v16 = 2915;
    goto LABEL_16;
  }
  v7 = (unsigned int *)validateMSCryptHash(a1, a2);
  v11 = v7;
  if ( !v7 || v7[5] || v7[9] )
  {
    v14 = -1073741816;
    v16 = 2926;
    v17 = 3221225480LL;
    goto LABEL_35;
  }
  if ( v7[2] - 131093 > 5 )
  {
    v12 = 0;
    if ( (a4 & 1) != 0 )
    {
      v16 = 2941;
      goto LABEL_16;
    }
  }
  else
  {
    v12 = 1;
  }
  if ( !a2 || !v12 && a3 != v7[3] )
  {
    v16 = 2951;
LABEL_16:
    v14 = -1073741811;
    v17 = 3221225485LL;
LABEL_35:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v16);
    return (unsigned int)v14;
  }
  if ( v7[7] == 1 )
  {
    if ( !v7[8] )
    {
      v18 = v7[28];
      v19 = 0;
      for ( v7[8] = 1; (unsigned int)v19 < v18; v19 = (unsigned int)(v19 + 1) )
        v24[v19] = *((_BYTE *)v7 + v19 + 48) ^ 0x36;
      v14 = MSCryptHashDataInternal(v7, v24);
      SymCryptWipeAsm(v24, 64);
      if ( v14 < 0 )
      {
        v16 = 2981;
LABEL_34:
        v17 = (unsigned int)v14;
        goto LABEL_35;
      }
    }
    v20 = MSCryptHashResultInternal((__int64)v11, (__int64)v23, v11[3], a4);
    v14 = v20;
    if ( v20 >= 0 )
    {
      v21 = v11[28];
      for ( i = 0; (unsigned int)i < v21; i = (unsigned int)(i + 1) )
        v25[i] = *((_BYTE *)v11 + i + 48) ^ 0x5C;
      v14 = MSCryptHashDataInternal(v11, v25);
      SymCryptWipeAsm(v25, 64);
      if ( v14 < 0 )
      {
        SymCryptWipeAsm(v23, 16);
        v16 = 3014;
        goto LABEL_34;
      }
      v14 = MSCryptHashDataInternal(v11, v23);
      SymCryptWipeAsm(v23, 16);
      if ( v14 < 0 )
      {
        v16 = 3025;
        goto LABEL_34;
      }
      v20 = MSCryptHashResultInternal((__int64)v11, a2, v11[3], a4);
      v14 = v20;
      if ( v20 >= 0 )
      {
        v11[8] = 0;
LABEL_11:
        if ( !v11[6] && (!v12 || (a4 & 1) == 0) )
          v11[5] = 1;
        return 0;
      }
      v16 = 3035;
    }
    else
    {
      v16 = 2993;
    }
    v17 = (unsigned int)v20;
    goto LABEL_35;
  }
  v14 = MSCryptHashResultInternal((__int64)v7, v8, v9, v10);
  if ( v14 >= 0 )
    goto LABEL_11;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
      (unsigned int)"Status",
      v14,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
      235);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180017240  push    rbx
0x180017242  push    rbp
0x180017243  push    rdi
0x180017244  push    r12
0x180017246  push    r14
0x180017248  push    r15
0x18001724a  sub     rsp, 0E8h
0x180017251  mov     rax, cs:__security_cookie
0x180017258  xor     rax, rsp
0x18001725b  mov     [rsp+118h+var_48], rax
0x180017263  mov     ebp, r9d
0x180017266  mov     r12d, r8d
0x180017269  mov     r15, rdx
0x18001726c  test    r9d, 0FFFFFFFEh
0x180017273  jnz     loc_18001739B
0x180017279  call    validateMSCryptHash
0x18001727e  mov     rdi, rax
0x180017281  test    rax, rax
0x180017284  jz      loc_1800173CB
0x18001728a  cmp     dword ptr [rax+14h], 0
0x18001728e  jnz     loc_1800173CB
0x180017294  cmp     dword ptr [rax+24h], 0
0x180017298  jnz     loc_1800173CB
0x18001729e  mov     eax, [rax+8]
0x1800172a1  sub     eax, 20015h
0x1800172a6  cmp     eax, 5
0x1800172a9  ja      loc_180017383
0x1800172af  mov     r14d, 1
0x1800172b5  test    r15, r15
0x1800172b8  jz      short loc_18001730D
0x1800172ba  test    r14d, r14d
0x1800172bd  jz      short loc_180017307
0x1800172bf  cmp     dword ptr [rdi+1Ch], 1
0x1800172c3  jz      loc_1800173A6
0x1800172c9  mov     rcx, rdi
0x1800172cc  call    MSCryptHashResultInternal
0x1800172d1  mov     ebx, eax
0x1800172d3  test    eax, eax
0x1800172d5  js      short loc_180017322
0x1800172d7  cmp     dword ptr [rdi+18h], 0
0x1800172db  jz      loc_180017368
0x1800172e1  xor     ebx, ebx
0x1800172e3  mov     eax, ebx
0x1800172e5  mov     rcx, [rsp+118h+var_48]
0x1800172ed  xor     rcx, rsp; StackCookie
0x1800172f0  call    __security_check_cookie
0x1800172f5  add     rsp, 0E8h
0x1800172fc  pop     r15
0x1800172fe  pop     r14
0x180017300  pop     r12
0x180017302  pop     rdi
0x180017303  pop     rbp
0x180017304  pop     rbx
0x180017305  retn
0x180017307  cmp     r12d, [rdi+0Ch]
0x18001730b  jz      short loc_1800172BF
0x18001730d  mov     r9d, 0B87h
0x180017313  mov     ebx, 0C000000Dh
0x180017318  mov     ecx, 0C000000Dh
0x18001731d  jmp     loc_180080C75
0x180017322  mov     rcx, cs:WPP_GLOBAL_Control
0x180017329  lea     rax, WPP_GLOBAL_Control
0x180017330  cmp     rcx, rax
0x180017333  jz      short loc_1800172E3
0x180017335  test    byte ptr [rcx+1Ch], 1
0x180017339  jz      short loc_1800172E3
0x18001733b  mov     rcx, [rcx+10h]
0x18001733f  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017346  mov     [rsp+118h+var_E8], 0BEBh
0x18001734e  lea     r9, aStatus; "Status"
0x180017355  mov     [rsp+118h+var_F0], r8
0x18001735a  mov     [rsp+118h+var_F8], ebx
0x18001735e  call    WPP_SF_sDsd
0x180017363  jmp     loc_1800172E3
0x180017368  test    r14d, r14d
0x18001736b  jz      short loc_180017377
0x18001736d  test    bpl, 1
0x180017371  jnz     loc_1800172E1
0x180017377  mov     dword ptr [rdi+14h], 1
0x18001737e  jmp     loc_1800172E1
0x180017383  xor     r14d, r14d
0x180017386  test    bpl, 1
0x18001738a  jz      loc_1800172B5
0x180017390  mov     r9d, 0B7Dh
0x180017396  jmp     loc_180017313
0x18001739b  mov     r9d, 0B63h
0x1800173a1  jmp     loc_180017313
0x1800173a6  cmp     dword ptr [rdi+20h], 0
0x1800173aa  jnz     loc_180080C8E
0x1800173b0  mov     r8d, [rdi+70h]
0x1800173b4  xor     edx, edx
0x1800173b6  mov     dword ptr [rdi+20h], 1
0x1800173bd  test    r8d, r8d
0x1800173c0  jnz     loc_180080C32
0x1800173c6  jmp     loc_180080C43
0x1800173cb  mov     ebx, 0C0000008h
0x1800173d0  mov     r9d, 0B6Eh
0x1800173d6  mov     ecx, 0C0000008h
0x1800173db  jmp     loc_180080C75
0x180080c32  mov     al, [rdx+rdi+30h]
0x180080c36  xor     al, 36h
0x180080c38  mov     [rsp+rdx+118h+var_C8], al
0x180080c3c  inc     edx
0x180080c3e  cmp     edx, r8d
0x180080c41  jb      short loc_180080C32
0x180080c43  lea     rdx, [rsp+118h+var_C8]
0x180080c48  mov     rcx, rdi
0x180080c4b  call    MSCryptHashDataInternal
0x180080c50  mov     edx, 40h ; '@'
0x180080c55  lea     rcx, [rsp+118h+var_C8]
0x180080c5a  mov     ebx, eax
0x180080c5c  call    SymCryptWipeAsm
0x180080c61  test    ebx, ebx
0x180080c63  jns     short loc_180080C8E
0x180080c65  mov     r9d, 0BA5h
0x180080c6b  jmp     short loc_180080C73
0x180080c6d  mov     r9d, 0BD1h
0x180080c73  mov     ecx, ebx
0x180080c75  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180080c7c  lea     rdx, aStatus; "Status"
0x180080c83  call    DebugTraceError
0x180080c88  nop
0x180080c89  jmp     loc_1800172E3
0x180080c8e  mov     r8d, [rdi+0Ch]
0x180080c92  lea     rdx, [rsp+118h+var_D8]
0x180080c97  mov     r9d, ebp
0x180080c9a  mov     rcx, rdi
0x180080c9d  call    MSCryptHashResultInternal
0x180080ca2  mov     ebx, eax
0x180080ca4  test    eax, eax
0x180080ca6  jns     short loc_180080CBA
0x180080ca8  mov     r9d, 0BB1h
0x180080cae  jmp     short loc_180080CB6
0x180080cb0  mov     r9d, 0BDBh
0x180080cb6  mov     ecx, eax
0x180080cb8  jmp     short loc_180080C75
0x180080cba  mov     r9d, [rdi+70h]
0x180080cbe  xor     r8d, r8d
0x180080cc1  test    r9d, r9d
0x180080cc4  jz      short loc_180080CDD
0x180080cc6  mov     al, [r8+rdi+30h]
0x180080ccb  xor     al, 5Ch
0x180080ccd  mov     [rsp+r8+118h+var_88], al
0x180080cd5  inc     r8d
0x180080cd8  cmp     r8d, r9d
0x180080cdb  jb      short loc_180080CC6
0x180080cdd  mov     r8d, r9d
0x180080ce0  lea     rdx, [rsp+118h+var_88]
0x180080ce8  mov     rcx, rdi
0x180080ceb  call    MSCryptHashDataInternal
0x180080cf0  mov     edx, 40h ; '@'
0x180080cf5  lea     rcx, [rsp+118h+var_88]
0x180080cfd  mov     ebx, eax
0x180080cff  call    SymCryptWipeAsm
0x180080d04  test    ebx, ebx
0x180080d06  jns     short loc_180080D22
0x180080d08  mov     edx, 10h
0x180080d0d  lea     rcx, [rsp+118h+var_D8]
0x180080d12  call    SymCryptWipeAsm
0x180080d17  mov     r9d, 0BC6h
0x180080d1d  jmp     loc_180080C73
0x180080d22  mov     r8d, r12d
0x180080d25  lea     rdx, [rsp+118h+var_D8]
0x180080d2a  mov     rcx, rdi
0x180080d2d  call    MSCryptHashDataInternal
0x180080d32  mov     edx, 10h
0x180080d37  lea     rcx, [rsp+118h+var_D8]
0x180080d3c  mov     ebx, eax
0x180080d3e  call    SymCryptWipeAsm
0x180080d43  test    ebx, ebx
0x180080d45  js      loc_180080C6D
0x180080d4b  mov     r8d, [rdi+0Ch]
0x180080d4f  mov     r9d, ebp
0x180080d52  mov     rdx, r15
0x180080d55  mov     rcx, rdi
0x180080d58  call    MSCryptHashResultInternal
0x180080d5d  mov     ebx, eax
0x180080d5f  test    eax, eax
0x180080d61  js      loc_180080CB0
0x180080d67  mov     dword ptr [rdi+20h], 0
0x180080d6e  jmp     loc_1800172D7
```
