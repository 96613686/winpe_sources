# MSCryptExportKey

- ea: `0x18002b960`
- end: `0x18002bc33`
- name: `MSCryptExportKey`
- size: `723`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000ae00`
- `0x18002b7b0`

## callees

- `0x18000afd0`
- `0x18000ecb0`
- `0x18000ee60`
- `0x18002b960`
- `0x18002bc40`
- `0x180063170`
- `0x18007f765`

## string_xrefs

- `0x18002bb10`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18002bb4a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18002bba1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18002bbd4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18002bc18`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptExportKey(
        _DWORD *a1,
        __int64 a2,
        const wchar_t *a3,
        _DWORD *a4,
        unsigned int a5,
        _DWORD *a6,
        int a7)
{
  _DWORD *v11; // rbx
  int v12; // eax
  unsigned int v13; // edi
  unsigned int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rcx
  unsigned int v18[14]; // [rsp+40h] [rbp-38h] BYREF

  v18[0] = 0;
  if ( a7 )
  {
    v13 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        17);
LABEL_16:
    v11 = a6;
    if ( !a6 )
      return v13;
    goto LABEL_8;
  }
  if ( !a1 || a1[1] != 1297306443 )
  {
    v13 = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", 1306);
    goto LABEL_16;
  }
  v11 = a6;
  if ( a6 )
  {
    if ( !a3 )
    {
      v13 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
          40);
      goto LABEL_8;
    }
    if ( !wcscmp_0(a3, L"OpaqueKeyBlob") )
    {
      v12 = MSCryptExportKeyOpaque(a1, a4, a5, v18);
      v13 = v12;
      if ( v12 >= 0 )
      {
LABEL_8:
        *v11 = v18[0];
        return v13;
      }
      v16 = 1329;
    }
    else
    {
      if ( !wcscmp_0(a3, L"KeyDataBlob") )
      {
        v15 = a1[14] + 12;
        v18[0] = v15;
        if ( a4 )
        {
          if ( a5 < v15 )
          {
            v13 = -1073741789;
          }
          else
          {
            *a4 = 1296188491;
            a4[1] = 1;
            v13 = 0;
            a4[2] = a1[14];
            memcpy_0(a4 + 3, a1 + 15, (unsigned int)a1[14]);
          }
        }
        else
        {
          v13 = 0;
        }
        goto LABEL_8;
      }
      if ( wcscmp_0(a3, L"Rfc3565KeyWrapBlob") )
      {
        v13 = -1073741637;
        v16 = 1378;
        v17 = 3221225659LL;
        goto LABEL_33;
      }
      v12 = MSCryptAesKeyWrap((__int64)a1, a2, a4, a5, v18);
      v13 = v12;
      if ( v12 >= 0 )
        goto LABEL_8;
      v16 = 1371;
    }
    v17 = (unsigned int)v12;
LABEL_33:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v16);
    goto LABEL_8;
  }
  v13 = -1073741811;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return v13;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    a2,
    (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
    (unsigned int)"Status",
    13,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
    33);
  return 3221225485LL;
}

```

## disassembly

```asm
0x18002b960  push    rbx
0x18002b962  push    rbp
0x18002b963  push    rsi
0x18002b964  push    rdi
0x18002b965  push    r14
0x18002b967  sub     rsp, 50h
0x18002b96b  cmp     [rsp+78h+arg_30], 0
0x18002b973  mov     r14, r9
0x18002b976  mov     rdi, r8
0x18002b979  mov     [rsp+78h+var_38], 0
0x18002b981  mov     rbp, rdx
0x18002b984  mov     rsi, rcx
0x18002b987  jnz     loc_18002BA2C
0x18002b98d  test    rcx, rcx
0x18002b990  jz      loc_18002BBCE
0x18002b996  cmp     dword ptr [rcx+4], 4D53534Bh
0x18002b99d  jnz     loc_18002BBCE
0x18002b9a3  mov     rbx, [rsp+78h+arg_28]
0x18002b9ab  test    rbx, rbx
0x18002b9ae  jz      loc_18002BAE6
0x18002b9b4  test    r8, r8
0x18002b9b7  jz      loc_18002BB77
0x18002b9bd  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x18002b9c4  mov     rcx, r8; String1
0x18002b9c7  call    wcscmp_0
0x18002b9cc  test    eax, eax
0x18002b9ce  jnz     short loc_18002BA06
0x18002b9d0  mov     r8d, [rsp+78h+arg_20]
0x18002b9d8  lea     r9, [rsp+78h+var_38]
0x18002b9dd  mov     rdx, r14
0x18002b9e0  mov     rcx, rsi
0x18002b9e3  call    MSCryptExportKeyOpaque
0x18002b9e8  mov     edi, eax
0x18002b9ea  test    eax, eax
0x18002b9ec  js      loc_18002BBF6
0x18002b9f2  mov     eax, [rsp+78h+var_38]
0x18002b9f6  mov     [rbx], eax
0x18002b9f8  mov     eax, edi
0x18002b9fa  add     rsp, 50h
0x18002b9fe  pop     r14
0x18002ba00  pop     rdi
0x18002ba01  pop     rsi
0x18002ba02  pop     rbp
0x18002ba03  pop     rbx
0x18002ba04  retn
0x18002ba06  lea     rdx, aKeydatablob; "KeyDataBlob"
0x18002ba0d  mov     rcx, rdi; String1
0x18002ba10  call    wcscmp_0
0x18002ba15  test    eax, eax
0x18002ba17  jnz     short loc_18002BA98
0x18002ba19  mov     eax, [rsi+38h]
0x18002ba1c  add     eax, 0Ch
0x18002ba1f  mov     [rsp+78h+var_38], eax
0x18002ba23  test    r14, r14
0x18002ba26  jnz     short loc_18002BA5D
0x18002ba28  xor     edi, edi
0x18002ba2a  jmp     short loc_18002B9F2
0x18002ba2c  mov     edi, 0C000000Dh
0x18002ba31  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba38  lea     rax, WPP_GLOBAL_Control
0x18002ba3f  cmp     rcx, rax
0x18002ba42  jz      short loc_18002BA4E
0x18002ba44  test    byte ptr [rcx+1Ch], 1
0x18002ba48  jnz     loc_18002BB46
0x18002ba4e  mov     rbx, [rsp+78h+arg_28]
0x18002ba56  test    rbx, rbx
0x18002ba59  jnz     short loc_18002B9F2
0x18002ba5b  jmp     short loc_18002B9F8
0x18002ba5d  cmp     [rsp+78h+arg_20], eax
0x18002ba64  jb      loc_18002BC29
0x18002ba6a  mov     dword ptr [r14], 4D42444Bh
0x18002ba71  lea     rdx, [rsi+3Ch]; Src
0x18002ba75  mov     dword ptr [r14+4], 1
0x18002ba7d  lea     rcx, [r14+0Ch]; void *
0x18002ba81  mov     eax, [rsi+38h]
0x18002ba84  xor     edi, edi
0x18002ba86  mov     [r14+8], eax
0x18002ba8a  mov     r8d, [rsi+38h]; Size
0x18002ba8e  call    memcpy_0
0x18002ba93  jmp     loc_18002B9F2
0x18002ba98  lea     rdx, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x18002ba9f  mov     rcx, rdi; String1
0x18002baa2  call    wcscmp_0
0x18002baa7  test    eax, eax
0x18002baa9  jnz     loc_18002BC01
0x18002baaf  mov     r9d, [rsp+78h+arg_20]
0x18002bab7  lea     rax, [rsp+78h+var_38]
0x18002babc  mov     r8, r14
0x18002babf  mov     [rsp+78h+var_58], rax
0x18002bac4  mov     rdx, rbp
0x18002bac7  mov     rcx, rsi
0x18002baca  call    MSCryptAesKeyWrap
0x18002bacf  mov     edi, eax
0x18002bad1  test    eax, eax
0x18002bad3  jns     loc_18002B9F2
0x18002bad9  mov     r9d, 55Bh
0x18002badf  mov     ecx, eax
0x18002bae1  jmp     loc_18002BC11
0x18002bae6  mov     edi, 0C000000Dh
0x18002baeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002baf2  lea     rax, WPP_GLOBAL_Control
0x18002baf9  cmp     rcx, rax
0x18002bafc  jz      loc_18002B9F8
0x18002bb02  test    byte ptr [rcx+1Ch], 1
0x18002bb06  jz      loc_18002B9F8
0x18002bb0c  mov     rcx, [rcx+10h]
0x18002bb10  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002bb17  mov     [rsp+78h+var_48], 521h
0x18002bb1f  lea     r9, aStatus; "Status"
0x18002bb26  mov     [rsp+78h+var_50], r8
0x18002bb2b  mov     dword ptr [rsp+78h+var_58], 0C000000Dh
0x18002bb33  call    WPP_SF_sDsd
0x18002bb38  mov     eax, edi
0x18002bb3a  add     rsp, 50h
0x18002bb3e  pop     r14
0x18002bb40  pop     rdi
0x18002bb41  pop     rsi
0x18002bb42  pop     rbp
0x18002bb43  pop     rbx
0x18002bb44  retn
0x18002bb46  mov     rcx, [rcx+10h]
0x18002bb4a  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002bb51  mov     [rsp+78h+var_48], 511h
0x18002bb59  lea     r9, aStatus; "Status"
0x18002bb60  mov     [rsp+78h+var_50], r8
0x18002bb65  mov     dword ptr [rsp+78h+var_58], 0C000000Dh
0x18002bb6d  call    WPP_SF_sDsd
0x18002bb72  jmp     loc_18002BA4E
0x18002bb77  mov     edi, 0C000000Dh
0x18002bb7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bb83  lea     rax, WPP_GLOBAL_Control
0x18002bb8a  cmp     rcx, rax
0x18002bb8d  jz      loc_18002B9F2
0x18002bb93  test    byte ptr [rcx+1Ch], 1
0x18002bb97  jz      loc_18002B9F2
0x18002bb9d  mov     rcx, [rcx+10h]
0x18002bba1  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002bba8  mov     [rsp+78h+var_48], 528h
0x18002bbb0  lea     r9, aStatus; "Status"
0x18002bbb7  mov     [rsp+78h+var_50], r8
0x18002bbbc  mov     dword ptr [rsp+78h+var_58], 0C000000Dh
0x18002bbc4  call    WPP_SF_sDsd
0x18002bbc9  jmp     loc_18002B9F2
0x18002bbce  mov     r9d, 51Ah
0x18002bbd4  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002bbdb  lea     rdx, aStatus; "Status"
0x18002bbe2  mov     ecx, 0C0000008h
0x18002bbe7  mov     edi, 0C0000008h
0x18002bbec  call    DebugTraceError
0x18002bbf1  jmp     loc_18002BA4E
0x18002bbf6  mov     r9d, 531h
0x18002bbfc  jmp     loc_18002BADF
0x18002bc01  mov     edi, 0C00000BBh
0x18002bc06  mov     r9d, 562h
0x18002bc0c  mov     ecx, 0C00000BBh
0x18002bc11  lea     rdx, aStatus; "Status"
0x18002bc18  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002bc1f  call    DebugTraceError
0x18002bc24  jmp     loc_18002B9F2
0x18002bc29  mov     edi, 0C0000023h
0x18002bc2e  jmp     loc_18002B9F2
```
