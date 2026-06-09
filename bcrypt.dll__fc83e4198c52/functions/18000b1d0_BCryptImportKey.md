# BCryptImportKey

- ea: `0x18000b1d0`
- end: `0x18000b679`
- name: `BCryptImportKey`
- size: `1193`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_KEY_HANDLE hImportKey, LPCWSTR pszBlobType, BCRYPT_KEY_HANDLE *phKey, PUCHAR pbKeyObject, ULONG cbKeyObject, PUCHAR pbInput, ULONG cbInput, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180005060`
- `0x180005f50`
- `0x180006bd0`
- `0x180007a7c`
- `0x180009430`
- `0x180009740`
- `0x18000b1d0`
- `0x180015834`
- `0x180015a7c`
- `0x18001b7b5`
- `0x18001c010`

## string_xrefs

- `0x18000b3c2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000b478`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000b4b3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000b59a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000b5cd`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000b617`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptImportKey(
        BCRYPT_ALG_HANDLE hAlgorithm,
        BCRYPT_KEY_HANDLE hImportKey,
        LPCWSTR pszBlobType,
        BCRYPT_KEY_HANDLE *phKey,
        PUCHAR pbKeyObject,
        ULONG cbKeyObject,
        PUCHAR pbInput,
        ULONG cbInput,
        ULONG dwFlags)
{
  UCHAR *v9; // rbp
  ULONG v13; // r15d
  PUCHAR v14; // rbx
  int v15; // edx
  __int64 v16; // rsi
  int v17; // r8d
  __int64 v18; // r13
  int v19; // eax
  NTSTATUS v20; // ebx
  _DWORD *v21; // r14
  __int64 (__fastcall *v22)(_QWORD, __int64, LPCWSTR, _DWORD *, unsigned __int64, int, PUCHAR, ULONG, ULONG); // r10
  int v23; // ecx
  int v24; // eax
  _QWORD *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // r14
  bool v29; // zf
  int v30; // eax
  __int64 v31; // r9
  __int64 v32; // rcx
  __int64 v33; // r9
  __int64 v34; // rcx
  size_t Size; // [rsp+30h] [rbp-88h]
  char Sizea; // [rsp+30h] [rbp-88h]
  ULONG v37; // [rsp+60h] [rbp-58h] BYREF
  int v38; // [rsp+64h] [rbp-54h]
  UCHAR *v39; // [rsp+68h] [rbp-50h] BYREF
  __int64 v40; // [rsp+70h] [rbp-48h]

  v9 = 0;
  v39 = 0;
  v37 = 0;
  v13 = cbKeyObject;
  v14 = pbKeyObject;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qqSqqdqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)pbInput,
      (_DWORD)pszBlobType,
      (_DWORD)hAlgorithm,
      (char)hImportKey,
      (__int64)pszBlobType,
      (char)phKey,
      (char)pbKeyObject,
      cbKeyObject,
      (char)pbInput,
      cbInput,
      dwFlags);
  v16 = ValidateBaseAlgHandle(hAlgorithm);
  if ( !v16 )
  {
    v20 = -1073741816;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v20;
    Sizea = 36;
    goto LABEL_27;
  }
  v38 = 0;
  if ( hImportKey )
  {
    v27 = ValidateBaseKeyHandle(hImportKey);
    v18 = v27;
    if ( v27 )
    {
      v28 = *(_QWORD *)(v27 + 8);
      if ( !pszBlobType || (v29 = wcscmp_0(pszBlobType, L"PKCS11RsaAesWrapBlob") == 0, v30 = 3, !v29) )
        v30 = 1;
      if ( !v28 )
      {
        v20 = -1073739510;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v15,
            v17,
            (unsigned int)"Status",
            10,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
            58);
        return v20;
      }
      if ( *(_DWORD *)(v28 + 36) == v30 )
      {
        if ( *(_QWORD *)(v28 + 40) == *(_QWORD *)(v16 + 40) )
        {
LABEL_35:
          v40 = *(_QWORD *)(v18 + 16);
          goto LABEL_7;
        }
        if ( !wcscmp_0(pszBlobType, L"Rfc3565KeyWrapBlob") )
        {
          v38 = 1;
          goto LABEL_35;
        }
        v20 = -1073741811;
        v31 = 4687;
        v32 = 3221225485LL;
      }
      else
      {
        v20 = -1073741816;
        v31 = 4673;
        v32 = 3221225480LL;
      }
      DebugTraceError(v32, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v31);
      return v20;
    }
    v20 = -1073741816;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v20;
    Sizea = 46;
LABEL_27:
    WPP_SF_sDsd(
      v26[2],
      v15,
      v17,
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      Sizea);
    return v20;
  }
  LODWORD(v18) = 0;
  v40 = 0;
LABEL_7:
  if ( !pbKeyObject && !cbKeyObject )
  {
    v19 = AllocateObjectBuffer(hAlgorithm, &v39, &v37);
    v20 = v19;
    if ( v19 < 0 )
    {
      DebugTraceError((unsigned int)v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 4703);
      v9 = v39;
      goto LABEL_42;
    }
    v9 = v39;
    v13 = v37;
    v14 = v39;
  }
  if ( phKey && v14 && pszBlobType )
  {
    if ( v13 < 0x3E )
    {
      v20 = -1073741789;
      goto LABEL_42;
    }
    v21 = (_DWORD *)((unsigned __int64)(v14 + 15) & 0xFFFFFFFFFFFFFFF0uLL);
    v21[1] = 1431655762;
    *((_QWORD *)v21 + 1) = v16;
    *v21 = (_DWORD)v14 - (_DWORD)v21 + v13;
    *((_QWORD *)v21 + 3) = v9;
    if ( *(_DWORD *)(v16 + 36) == 1 )
    {
      v22 = *(__int64 (__fastcall **)(_QWORD, __int64, LPCWSTR, _DWORD *, unsigned __int64, int, PUCHAR, ULONG, ULONG))(v16 + 112);
    }
    else
    {
      if ( *(_DWORD *)(v16 + 36) != 7 )
      {
        v20 = -1073741637;
        v33 = 4760;
        v34 = 3221225659LL;
LABEL_58:
        DebugTraceError(v34, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v33);
        goto LABEL_42;
      }
      v22 = *(__int64 (__fastcall **)(_QWORD, __int64, LPCWSTR, _DWORD *, unsigned __int64, int, PUCHAR, ULONG, ULONG))(v16 + 120);
    }
    v23 = (_DWORD)v14 + v13 - (((_DWORD)v21 + 47) & 0xFFFFFFF0);
    if ( v38 )
    {
      LODWORD(Size) = cbInput;
      v24 = RouterAesKeyUnwrap(v16, v18, (int)v21 + 16, ((_DWORD)v21 + 47) & 0xFFFFFFF0, v23, pbInput, Size);
      v20 = v24;
      if ( v24 >= 0 )
        goto LABEL_19;
      v33 = 4777;
    }
    else
    {
      v24 = v22(
              *(_QWORD *)(v16 + 24),
              v40,
              pszBlobType,
              v21 + 4,
              ((unsigned __int64)v21 + 47) & 0xFFFFFFFFFFFFFFF0uLL,
              v23,
              pbInput,
              cbInput,
              dwFlags);
      v20 = v24;
      if ( v24 >= 0 )
      {
LABEL_19:
        v20 = 0;
        *phKey = v21;
LABEL_20:
        _InterlockedAdd((volatile signed __int32 *)(v16 + 16), 1u);
        return v20;
      }
      v33 = 4796;
    }
    v34 = (unsigned int)v24;
    goto LABEL_58;
  }
  v20 = -1073741811;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      v17,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      114);
LABEL_42:
  if ( v9 )
    MSCryptFree(v9);
  if ( v20 >= 0 )
    goto LABEL_20;
  return v20;
}

```

## disassembly

```asm
0x18000b1d0  mov     rax, rsp
0x18000b1d3  mov     [rax+10h], rbx
0x18000b1d7  mov     [rax+20h], r9
0x18000b1db  mov     [rax+8], rcx
0x18000b1df  push    rbp
0x18000b1e0  push    rsi
0x18000b1e1  push    rdi
0x18000b1e2  push    r12
0x18000b1e4  push    r13
0x18000b1e6  push    r14
0x18000b1e8  push    r15
0x18000b1ea  sub     rsp, 80h
0x18000b1f1  xor     ebp, ebp
0x18000b1f3  mov     r12, r8
0x18000b1f6  mov     [rax-50h], rbp
0x18000b1fa  mov     r14, rdx
0x18000b1fd  mov     [rax-58h], ebp
0x18000b200  mov     rdi, rcx
0x18000b203  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b20a  lea     r13, WPP_GLOBAL_Control
0x18000b211  mov     r15d, [rsp+0B8h+cbKeyObject]
0x18000b219  mov     rbx, [rsp+0B8h+pbKeyObject]
0x18000b221  cmp     rcx, r13
0x18000b224  jz      short loc_18000B230
0x18000b226  test    byte ptr [rcx+1Ch], 4
0x18000b22a  jnz     loc_18000B524
0x18000b230  mov     rcx, rdi
0x18000b233  call    ValidateBaseAlgHandle
0x18000b238  mov     rsi, rax
0x18000b23b  test    rax, rax
0x18000b23e  jz      loc_18000B39E
0x18000b244  mov     [rsp+0B8h+var_54], ebp
0x18000b248  mov     edi, 1
0x18000b24d  test    r14, r14
0x18000b250  jnz     loc_18000B3E8
0x18000b256  xor     r13d, r13d
0x18000b259  mov     [rsp+0B8h+var_48], rbp
0x18000b25e  test    rbx, rbx
0x18000b261  jnz     short loc_18000B296
0x18000b263  test    r15d, r15d
0x18000b266  jnz     short loc_18000B296
0x18000b268  mov     rcx, [rsp+0B8h+arg_0]
0x18000b270  lea     r8, [rsp+0B8h+var_58]
0x18000b275  lea     rdx, [rsp+0B8h+var_50]
0x18000b27a  call    AllocateObjectBuffer
0x18000b27f  mov     ebx, eax
0x18000b281  test    eax, eax
0x18000b283  js      loc_18000B5C7
0x18000b289  mov     rbp, [rsp+0B8h+var_50]
0x18000b28e  mov     r15d, [rsp+0B8h+var_58]
0x18000b293  mov     rbx, rbp
0x18000b296  cmp     [rsp+0B8h+arg_18], 0
0x18000b29f  jz      loc_18000B491
0x18000b2a5  test    rbx, rbx
0x18000b2a8  jz      loc_18000B491
0x18000b2ae  test    r12, r12
0x18000b2b1  jz      loc_18000B491
0x18000b2b7  cmp     r15d, 3Eh ; '>'
0x18000b2bb  jb      loc_18000B5EC
0x18000b2c1  lea     r14, [rbx+0Fh]
0x18000b2c5  and     r14, 0FFFFFFFFFFFFFFF0h
0x18000b2c9  sub     ebx, r14d
0x18000b2cc  mov     dword ptr [r14+4], 55555552h
0x18000b2d4  lea     edx, [rbx+r15]
0x18000b2d8  mov     [r14+8], rsi
0x18000b2dc  mov     [r14], edx
0x18000b2df  mov     [r14+18h], rbp
0x18000b2e3  mov     ecx, [rsi+24h]
0x18000b2e6  sub     ecx, edi
0x18000b2e8  jnz     loc_18000B38C
0x18000b2ee  mov     r10, [rsi+70h]
0x18000b2f2  lea     rax, [r14+2Fh]
0x18000b2f6  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000b2fa  sub     edx, eax
0x18000b2fc  cmp     [rsp+0B8h+var_54], 0
0x18000b301  lea     ecx, [rdx+r14]
0x18000b305  jnz     loc_18000B628
0x18000b30b  mov     r8d, [rsp+0B8h+dwFlags]
0x18000b313  lea     r9, [r14+10h]
0x18000b317  mov     rdx, [rsp+0B8h+var_48]
0x18000b31c  mov     [rsp+0B8h+var_78], r8d
0x18000b321  mov     r8d, [rsp+0B8h+cbInput]
0x18000b329  mov     dword ptr [rsp+0B8h+var_80], r8d
0x18000b32e  mov     r8, [rsp+0B8h+pbInput]
0x18000b336  mov     [rsp+0B8h+Size], r8
0x18000b33b  mov     r8, r12
0x18000b33e  mov     dword ptr [rsp+0B8h+Src], ecx
0x18000b342  mov     rcx, [rsi+18h]
0x18000b346  mov     qword ptr [rsp+0B8h+var_98], rax
0x18000b34b  mov     rax, r10
0x18000b34e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b353  mov     ebx, eax
0x18000b355  test    eax, eax
0x18000b357  js      loc_18000B664
0x18000b35d  mov     rax, [rsp+0B8h+arg_18]
0x18000b365  xor     ebx, ebx
0x18000b367  mov     [rax], r14
0x18000b36a  lock add [rsi+10h], edi
0x18000b36e  mov     eax, ebx
0x18000b370  mov     rbx, [rsp+0B8h+arg_8]
0x18000b378  add     rsp, 80h
0x18000b37f  pop     r15
0x18000b381  pop     r14
0x18000b383  pop     r13
0x18000b385  pop     r12
0x18000b387  pop     rdi
0x18000b388  pop     rsi
0x18000b389  pop     rbp
0x18000b38a  retn
0x18000b38c  cmp     ecx, 6
0x18000b38f  jnz     loc_18000B5F6
0x18000b395  mov     r10, [rsi+78h]
0x18000b399  jmp     loc_18000B2F2
0x18000b39e  mov     ebx, 0C0000008h
0x18000b3a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3aa  cmp     rcx, r13
0x18000b3ad  jz      short loc_18000B36E
0x18000b3af  mov     edi, 1
0x18000b3b4  test    [rcx+1Ch], dil
0x18000b3b8  jz      short loc_18000B36E
0x18000b3ba  mov     dword ptr [rsp+0B8h+Size], 1224h
0x18000b3c2  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b3c9  mov     [rsp+0B8h+Src], rax
0x18000b3ce  mov     [rsp+0B8h+var_98], 0C0000008h
0x18000b3d6  mov     rcx, [rcx+10h]
0x18000b3da  lea     r9, aStatus; "Status"
0x18000b3e1  call    WPP_SF_sDsd
0x18000b3e6  jmp     short loc_18000B36E
0x18000b3e8  mov     rcx, r14
0x18000b3eb  call    ValidateBaseKeyHandle
0x18000b3f0  mov     r13, rax
0x18000b3f3  test    rax, rax
0x18000b3f6  jz      loc_18000B4F1
0x18000b3fc  mov     r14, [rax+8]
0x18000b400  test    r12, r12
0x18000b403  jz      short loc_18000B41D
0x18000b405  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x18000b40c  mov     rcx, r12; String1
0x18000b40f  call    wcscmp_0
0x18000b414  test    eax, eax
0x18000b416  mov     eax, 3
0x18000b41b  jz      short loc_18000B41F
0x18000b41d  mov     eax, edi
0x18000b41f  test    r14, r14
0x18000b422  jz      short loc_18000B44A
0x18000b424  cmp     [r14+24h], eax
0x18000b428  jnz     loc_18000B571
0x18000b42e  mov     rax, [rsi+28h]
0x18000b432  cmp     [r14+28h], rax
0x18000b436  jnz     loc_18000B5AB
0x18000b43c  mov     rax, [r13+10h]
0x18000b440  mov     [rsp+0B8h+var_48], rax
0x18000b445  jmp     loc_18000B25E
0x18000b44a  mov     ebx, 0C000090Ah
0x18000b44f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b456  lea     rax, WPP_GLOBAL_Control
0x18000b45d  cmp     rcx, rax
0x18000b460  jz      loc_18000B36E
0x18000b466  test    [rcx+1Ch], dil
0x18000b46a  jz      loc_18000B36E
0x18000b470  mov     dword ptr [rsp+0B8h+Size], 123Ah
0x18000b478  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b47f  mov     [rsp+0B8h+Src], rax
0x18000b484  mov     [rsp+0B8h+var_98], 0C000090Ah
0x18000b48c  jmp     loc_18000B3D6
0x18000b491  mov     ebx, 0C000000Dh
0x18000b496  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b49d  lea     rax, WPP_GLOBAL_Control
0x18000b4a4  cmp     rcx, rax
0x18000b4a7  jz      short loc_18000B4DB
0x18000b4a9  test    [rcx+1Ch], dil
0x18000b4ad  jz      short loc_18000B4DB
0x18000b4af  mov     rcx, [rcx+10h]
0x18000b4b3  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b4ba  mov     dword ptr [rsp+0B8h+Size], 1272h
0x18000b4c2  lea     r9, aStatus; "Status"
0x18000b4c9  mov     [rsp+0B8h+Src], rax
0x18000b4ce  mov     [rsp+0B8h+var_98], 0C000000Dh
0x18000b4d6  call    WPP_SF_sDsd
0x18000b4db  test    rbp, rbp
0x18000b4de  jnz     loc_18000B66C
0x18000b4e4  test    ebx, ebx
0x18000b4e6  jns     loc_18000B36A
0x18000b4ec  jmp     loc_18000B36E
0x18000b4f1  mov     ebx, 0C0000008h
0x18000b4f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4fd  lea     rax, WPP_GLOBAL_Control
0x18000b504  cmp     rcx, rax
0x18000b507  jz      loc_18000B36E
0x18000b50d  test    [rcx+1Ch], dil
0x18000b511  jz      loc_18000B36E
0x18000b517  mov     dword ptr [rsp+0B8h+Size], 122Eh
0x18000b51f  jmp     loc_18000B3C2
0x18000b524  mov     edx, [rsp+0B8h+dwFlags]
0x18000b52b  mov     rcx, [rcx+10h]
0x18000b52f  mov     [rsp+0B8h+var_60], edx
0x18000b533  mov     edx, [rsp+0B8h+cbInput]
0x18000b53a  mov     [rsp+0B8h+var_68], edx
0x18000b53e  mov     rdx, [rsp+0B8h+pbInput]
0x18000b546  mov     [rsp+0B8h+var_70], rdx
0x18000b54b  mov     [rsp+0B8h+var_78], r15d
0x18000b550  mov     [rsp+0B8h+var_80], rbx
0x18000b555  mov     [rsp+0B8h+Size], r9
0x18000b55a  mov     r9, rdi
0x18000b55d  mov     [rsp+0B8h+Src], r12
0x18000b562  mov     qword ptr [rsp+0B8h+var_98], r14
0x18000b567  call    WPP_SF_qqSqqdqdD
0x18000b56c  jmp     loc_18000B230
0x18000b571  mov     ebx, 0C0000008h
0x18000b576  mov     r9d, 1241h
0x18000b57c  mov     ecx, 0C0000008h
0x18000b581  jmp     short loc_18000B593
0x18000b583  mov     ebx, 0C000000Dh
0x18000b588  mov     r9d, 124Fh
0x18000b58e  mov     ecx, 0C000000Dh
0x18000b593  lea     rdx, aStatus; "Status"
0x18000b59a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b5a1  call    DebugTraceError
0x18000b5a6  jmp     loc_18000B36E
0x18000b5ab  lea     rdx, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x18000b5b2  mov     rcx, r12; String1
0x18000b5b5  call    wcscmp_0
0x18000b5ba  test    eax, eax
0x18000b5bc  jnz     short loc_18000B583
0x18000b5be  mov     [rsp+0B8h+var_54], edi
0x18000b5c2  jmp     loc_18000B43C
0x18000b5c7  mov     r9d, 125Fh
0x18000b5cd  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b5d4  lea     rdx, aStatus; "Status"
0x18000b5db  mov     ecx, eax
0x18000b5dd  call    DebugTraceError
0x18000b5e2  mov     rbp, [rsp+0B8h+var_50]
0x18000b5e7  jmp     loc_18000B4DB
0x18000b5ec  mov     ebx, 0C0000023h
0x18000b5f1  jmp     loc_18000B4DB
0x18000b5f6  mov     ebx, 0C00000BBh
0x18000b5fb  mov     r9d, 1298h
0x18000b601  mov     ecx, 0C00000BBh
0x18000b606  jmp     short loc_18000B610
0x18000b608  mov     r9d, 12A9h
0x18000b60e  mov     ecx, eax
0x18000b610  lea     rdx, aStatus; "Status"
0x18000b617  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b61e  call    DebugTraceError
0x18000b623  jmp     loc_18000B4DB
0x18000b628  mov     r8d, [rsp+0B8h+cbInput]
0x18000b630  mov     r9, rax; int
0x18000b633  mov     dword ptr [rsp+0B8h+Size], r8d; Size
0x18000b638  mov     rdx, r13; int
0x18000b63b  mov     r8, [rsp+0B8h+pbInput]
0x18000b643  mov     [rsp+0B8h+Src], r8; Src
0x18000b648  lea     r8, [r14+10h]; int
0x18000b64c  mov     [rsp+0B8h+var_98], ecx; int
0x18000b650  mov     rcx, rsi; int
0x18000b653  call    RouterAesKeyUnwrap
0x18000b658  mov     ebx, eax
0x18000b65a  test    eax, eax
0x18000b65c  jns     loc_18000B35D
0x18000b662  jmp     short loc_18000B608
0x18000b664  mov     r9d, 12BCh
0x18000b66a  jmp     short loc_18000B60E
0x18000b66c  mov     rcx, rbp
0x18000b66f  call    MSCryptFree
0x18000b674  jmp     loc_18000B4E4
```
