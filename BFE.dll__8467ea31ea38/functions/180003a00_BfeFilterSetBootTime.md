# BfeFilterSetBootTime

- ea: `0x180003a00`
- end: `0x180003dd0`
- name: `BfeFilterSetBootTime`
- size: `976`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config`

## callees

- `0x1800039e4`
- `0x180003a00`
- `0x180004850`
- `0x1800049f8`
- `0x18000e000`
- `0x18000e4e0`
- `0x18001236c`
- `0x180018b74`
- `0x180022730`
- `0x18003e23c`
- `0x180058b30`
- `0x180064b18`
- `0x180066f44`
- `0x180087dc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003c31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003d5c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003c31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003d5c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003b6d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003b6d`

## string_xrefs

- `0x180003db0`: `BfeRegSetBinary`
- `0x180003d9c`: `RegSetValueExW`

## pseudocode

```c
__int64 __fastcall BfeFilterSetBootTime(unsigned int **a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v3; // r12
  unsigned int *v4; // rdx
  size_t cbData; // r13
  unsigned int v7; // eax
  __int64 v8; // rcx
  LPBYTE v10; // r14
  int v11; // esi
  DWORD v12; // edi
  int v13; // r12d
  LPBYTE v14; // rsi
  unsigned int v15; // eax
  __int64 v16; // rcx
  const char *v17; // rdx
  LPBYTE v18; // [rsp+78h] [rbp-88h] BYREF
  BYTE *lpData; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h]
  LPBYTE v21; // [rsp+90h] [rbp-70h] BYREF
  __int64 v22; // [rsp+98h] [rbp-68h]
  DWORD v23; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v24[2]; // [rsp+A8h] [rbp-58h] BYREF
  DWORD Type; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t pszDest[40]; // [rsp+D0h] [rbp-30h] BYREF

  v2 = 0;
  v22 = a2;
  lpData = 0;
  v3 = a2;
  Type = 0;
  v4 = *a1;
  memset(v24, 0, sizeof(v24));
  if ( (v4[8] & 2) == 0 )
    goto LABEL_11;
  DWORD1(v24[0]) = *(unsigned __int16 *)(*(_QWORD *)a1[1] + 64LL);
  if ( (v4[32] & 0x4000) != 0 )
    *(_OWORD *)((char *)v24 + 8) = *(_OWORD *)(v4 + 33);
  *((_QWORD *)&v24[1] + 1) = a1[2];
  v2 = WfpMidlObjectEncode(&WFP_BOOTTIME_FILTER_MARSHAL_Encode, v24, &lpData, &Type);
  if ( v2 )
    goto LABEL_11;
  StringCchPrintfW(
    pszDest,
    0x27u,
    L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
    **a1,
    *((unsigned __int16 *)*a1 + 2),
    *((unsigned __int16 *)*a1 + 3),
    *((unsigned __int8 *)*a1 + 8),
    *((unsigned __int8 *)*a1 + 9),
    *((unsigned __int8 *)*a1 + 10),
    *((unsigned __int8 *)*a1 + 11),
    *((unsigned __int8 *)*a1 + 12),
    *((unsigned __int8 *)*a1 + 13),
    *((unsigned __int8 *)*a1 + 14),
    *((unsigned __int8 *)*a1 + 15));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF__guid__guid_I(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      *(_DWORD *)a1 + 64,
      (unsigned int)*a1,
      (__int64)(*a1 + 16));
  }
  cbData = Type;
  if ( *(_DWORD *)(v3 + 8) )
    goto LABEL_8;
  BfeCallGetSysTxn();
  hKey = *(HKEY *)v3;
  v10 = 0;
  v23 = 4096;
  Type = 0;
  v18 = 0;
  v11 = 0;
  v21 = 0;
  v12 = 0;
  v13 = 1;
  v2 = WfpMemAlloc(0x1000u, 0);
  if ( !v2 )
  {
    v14 = v18;
    v15 = RegQueryValueExW(hKey, pszDest, 0, &Type, v18, &v23);
    if ( v15 == 234 )
    {
      v2 = WfpMemReAlloc(v23, (__int64)&v18);
      if ( v2 )
        goto LABEL_17;
      v14 = v18;
      v15 = RegQueryValueExW(hKey, pszDest, 0, &Type, v18, &v23);
    }
    v12 = 0;
    if ( v15 != 2 && v15 != 234 )
    {
      if ( v15 )
      {
        v2 = WfpReportSysErrorAsWinError(v16, "RegQueryValueExW", v15);
      }
      else if ( Type == 3 )
      {
        v12 = v23;
        v10 = v14;
        v21 = v14;
        v11 = 1;
        v18 = 0;
        goto LABEL_18;
      }
    }
LABEL_17:
    v11 = 0;
  }
LABEL_18:
  WfpMemFree(&v18);
  BfeRegCloseKey(0);
  if ( v2 )
  {
    WfpReportError(v2, "BfeRegQueryValue");
    v17 = "BfeRegQueryBinary";
    goto LABEL_40;
  }
  if ( v11 && (_DWORD)cbData == v12 && !memcmp_0(lpData, v10, cbData) )
  {
    v13 = 0;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_0ac2aa085a863ed18a171940451ff39f_Traceguids, *a1);
  }
  WfpMemFree(&v21);
  if ( v13 )
  {
    v3 = v22;
LABEL_8:
    BfeCallGetSysTxn();
    v2 = 0;
    v7 = RegSetValueExW(*(HKEY *)v3, pszDest, 0, 3u, lpData, cbData);
    if ( v7 )
      v2 = WfpReportSysErrorAsWinError(v8, "RegSetValueExW", v7);
    BfeRegCloseKey(0);
    if ( !v2 )
      goto LABEL_11;
    v17 = "BfeRegSetBinary";
LABEL_40:
    WfpReportError(v2, v17);
  }
LABEL_11:
  WfpMemFree(&lpData);
  if ( v2 )
    WfpReportError(v2, "BfeFilterSetBootTime");
  return v2;
}

```

## disassembly

```asm
0x180003a00  mov     [rsp-8+arg_10], rbx
0x180003a05  push    rbp
0x180003a06  push    rsi
0x180003a07  push    rdi
0x180003a08  push    r12
0x180003a0a  push    r13
0x180003a0c  push    r14
0x180003a0e  push    r15
0x180003a10  lea     rbp, [rsp-30h]
0x180003a15  sub     rsp, 130h
0x180003a1c  mov     rax, cs:__security_cookie
0x180003a23  xor     rax, rsp
0x180003a26  mov     [rbp+60h+var_40], rax
0x180003a2a  xor     ebx, ebx
0x180003a2c  mov     [rbp+60h+var_C8], rdx
0x180003a30  xorps   xmm0, xmm0
0x180003a33  mov     [rbp+60h+var_E0], rbx
0x180003a37  mov     r12, rdx
0x180003a3a  mov     [rbp+60h+Type], ebx
0x180003a3d  mov     rdx, [rcx]
0x180003a40  mov     r15, rcx
0x180003a43  movups  [rbp+60h+var_B8], xmm0
0x180003a47  movups  [rbp+60h+var_A8], xmm0
0x180003a4b  test    byte ptr [rdx+20h], 2
0x180003a4f  jz      loc_180003B8B
0x180003a55  mov     rax, [rcx+8]
0x180003a59  mov     rcx, [rax]
0x180003a5c  movzx   eax, word ptr [rcx+40h]
0x180003a60  mov     dword ptr [rbp+60h+var_B8+4], eax
0x180003a63  test    dword ptr [rdx+80h], 4000h
0x180003a6d  jz      short loc_180003A7B
0x180003a6f  movups  xmm0, xmmword ptr [rdx+84h]
0x180003a76  movdqu  [rbp+60h+var_B8+8], xmm0
0x180003a7b  mov     rax, [r15+10h]
0x180003a7f  lea     r9, [rbp+60h+Type]
0x180003a83  lea     r8, [rbp+60h+var_E0]
0x180003a87  mov     qword ptr [rbp+60h+var_A8+8], rax
0x180003a8b  lea     rdx, [rbp+60h+var_B8]
0x180003a8f  lea     rcx, WFP_BOOTTIME_FILTER_MARSHAL_Encode
0x180003a96  call    WfpMidlObjectEncode
0x180003a9b  mov     rbx, rax
0x180003a9e  test    rax, rax
0x180003aa1  jnz     loc_180003B8B
0x180003aa7  mov     r9, [r15]
0x180003aaa  movzx   ecx, byte ptr [r9+0Eh]
0x180003aaf  movzx   edx, byte ptr [r9+0Dh]
0x180003ab4  movzx   r8d, byte ptr [r9+0Ch]
0x180003ab9  movzx   eax, byte ptr [r9+0Fh]
0x180003abe  movzx   r10d, byte ptr [r9+0Bh]
0x180003ac3  movzx   r11d, byte ptr [r9+0Ah]
0x180003ac8  movzx   ebx, byte ptr [r9+9]
0x180003acd  movzx   edi, byte ptr [r9+8]
0x180003ad2  movzx   esi, word ptr [r9+6]
0x180003ad7  movzx   r14d, word ptr [r9+4]
0x180003adc  mov     r9d, [r9]
0x180003adf  mov     [rsp+160h+var_F8], eax
0x180003ae3  mov     [rsp+160h+var_100], ecx
0x180003ae7  lea     rcx, [rbp+60h+pszDest]; pszDest
0x180003aeb  mov     [rsp+160h+var_108], edx
0x180003aef  mov     edx, 27h ; '''; cchDest
0x180003af4  mov     [rsp+160h+var_110], r8d
0x180003af9  lea     r8, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x180003b00  mov     [rsp+160h+var_118], r10d
0x180003b05  mov     [rsp+160h+var_120], r11d
0x180003b0a  mov     [rsp+160h+var_128], ebx
0x180003b0e  mov     [rsp+160h+var_130], edi
0x180003b12  mov     [rsp+160h+cbData], esi
0x180003b16  mov     dword ptr [rsp+160h+lpData], r14d
0x180003b1b  call    StringCchPrintfW
0x180003b20  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b27  lea     rax, WPP_GLOBAL_Control
0x180003b2e  cmp     rcx, rax
0x180003b31  jz      short loc_180003B3D
0x180003b33  cmp     byte ptr [rcx+19h], 4
0x180003b37  jnb     loc_180003CDB
0x180003b3d  cmp     dword ptr [r12+8], 0
0x180003b43  mov     r13d, [rbp+60h+Type]
0x180003b47  jz      short loc_180003BC7
0x180003b49  call    BfeCallGetSysTxn
0x180003b4e  mov     rax, [rbp+60h+var_E0]
0x180003b52  lea     rdx, [rbp+60h+pszDest]; lpValueName
0x180003b56  mov     rcx, [r12]; hKey
0x180003b5a  xor     ebx, ebx
0x180003b5c  mov     [rsp+160h+cbData], r13d; cbData
0x180003b61  xor     r8d, r8d; Reserved
0x180003b64  mov     [rsp+160h+lpData], rax; lpData
0x180003b69  lea     r9d, [rbx+3]; dwType
0x180003b6d  call    cs:__imp_RegSetValueExW
0x180003b73  test    eax, eax
0x180003b75  jnz     loc_180003D99
0x180003b7b  xor     ecx, ecx
0x180003b7d  call    BfeRegCloseKey
0x180003b82  test    rbx, rbx
0x180003b85  jnz     loc_180003DB0
0x180003b8b  lea     rcx, [rbp+60h+var_E0]
0x180003b8f  call    WfpMemFree
0x180003b94  test    rbx, rbx
0x180003b97  jnz     loc_180003DBC
0x180003b9d  mov     rax, rbx
0x180003ba0  mov     rcx, [rbp+60h+var_40]
0x180003ba4  xor     rcx, rsp; StackCookie
0x180003ba7  call    __security_check_cookie
0x180003bac  mov     rbx, [rsp+160h+arg_10]
0x180003bb4  add     rsp, 130h
0x180003bbb  pop     r15
0x180003bbd  pop     r14
0x180003bbf  pop     r13
0x180003bc1  pop     r12
0x180003bc3  pop     rdi
0x180003bc4  pop     rsi
0x180003bc5  pop     rbp
0x180003bc6  retn
0x180003bc7  call    BfeCallGetSysTxn
0x180003bcc  mov     rax, [r12]
0x180003bd0  lea     r8, [rsp+160h+var_E8]
0x180003bd5  mov     ecx, 1000h; dwBytes
0x180003bda  mov     [rbp+60h+hKey], rax
0x180003bde  xor     r14d, r14d
0x180003be1  mov     [rbp+60h+var_C0], ecx
0x180003be4  xor     edx, edx; dwFlags
0x180003be6  mov     [rbp+60h+Type], 0
0x180003bed  mov     [rsp+160h+var_E8], 0
0x180003bf6  xor     esi, esi
0x180003bf8  mov     [rbp+60h+var_D0], r14
0x180003bfc  call    WfpMemAlloc
0x180003c01  xor     edi, edi
0x180003c03  lea     r12d, [r14+1]
0x180003c07  mov     rbx, rax
0x180003c0a  test    rax, rax
0x180003c0d  jnz     short loc_180003C4B
0x180003c0f  mov     rsi, [rsp+160h+var_E8]
0x180003c14  lea     rax, [rbp+60h+var_C0]
0x180003c18  mov     rcx, [rbp+60h+hKey]; hKey
0x180003c1c  lea     r9, [rbp+60h+Type]; lpType
0x180003c20  mov     qword ptr [rsp+160h+cbData], rax; lpcbData
0x180003c25  lea     rdx, [rbp+60h+pszDest]; lpValueName
0x180003c29  xor     r8d, r8d; lpReserved
0x180003c2c  mov     [rsp+160h+lpData], rsi; lpData
0x180003c31  call    cs:__imp_RegQueryValueExW
0x180003c37  cmp     eax, 0EAh
0x180003c3c  jz      loc_180003D10
0x180003c42  xor     edi, edi
0x180003c44  cmp     eax, 2
0x180003c47  jnz     short loc_180003CAB
0x180003c49  mov     esi, edi
0x180003c4b  lea     rcx, [rsp+160h+var_E8]
0x180003c50  call    WfpMemFree
0x180003c55  xor     ecx, ecx
0x180003c57  call    BfeRegCloseKey
0x180003c5c  test    rbx, rbx
0x180003c5f  jnz     loc_180003D7E
0x180003c65  test    esi, esi
0x180003c67  jz      loc_180088508
0x180003c6d  cmp     r13d, edi
0x180003c70  jnz     loc_180088508
0x180003c76  mov     rcx, [rbp+60h+var_E0]; Buf1
0x180003c7a  mov     r8, r13; Size
0x180003c7d  mov     rdx, r14; Buf2
0x180003c80  call    memcmp_0
0x180003c85  test    eax, eax
0x180003c87  jnz     loc_180088508
0x180003c8d  xor     r12d, r12d
0x180003c90  lea     rcx, [rbp+60h+var_D0]
0x180003c94  call    WfpMemFree
0x180003c99  test    r12d, r12d
0x180003c9c  jz      loc_180003B8B
0x180003ca2  mov     r12, [rbp+60h+var_C8]
0x180003ca6  jmp     loc_180003B49
0x180003cab  cmp     eax, 0EAh
0x180003cb0  jz      short loc_180003C49
0x180003cb2  test    eax, eax
0x180003cb4  jnz     loc_180003D67
0x180003cba  cmp     [rbp+60h+Type], 3
0x180003cbe  jnz     short loc_180003C49
0x180003cc0  mov     edi, [rbp+60h+var_C0]
0x180003cc3  mov     r14, rsi
0x180003cc6  mov     [rbp+60h+var_D0], rsi
0x180003cca  mov     esi, r12d
0x180003ccd  mov     [rsp+160h+var_E8], 0
0x180003cd6  jmp     loc_180003C4B
0x180003cdb  test    byte ptr [rcx+1Ch], 2
0x180003cdf  jz      loc_180003B3D
0x180003ce5  mov     r9, [r15]
0x180003ce8  mov     edx, 16h
0x180003ced  mov     rcx, [rcx+10h]
0x180003cf1  mov     rax, [r9+0B0h]
0x180003cf8  lea     r8, [r9+40h]
0x180003cfc  mov     qword ptr [rsp+160h+cbData], rax
0x180003d01  mov     [rsp+160h+lpData], r8
0x180003d06  call    WPP_SF__guid__guid_I
0x180003d0b  jmp     loc_180003B3D
0x180003d10  mov     ecx, [rbp+60h+var_C0]; dwBytes
0x180003d13  lea     rax, [rsp+160h+var_E8]
0x180003d18  mov     r9, rsi
0x180003d1b  mov     [rsp+160h+lpData], rax; __int64
0x180003d20  xor     r8d, r8d
0x180003d23  lea     edx, [rcx-1000h]
0x180003d29  call    WfpMemReAlloc
0x180003d2e  mov     rbx, rax
0x180003d31  test    rax, rax
0x180003d34  jnz     loc_180003C49
0x180003d3a  mov     rsi, [rsp+160h+var_E8]
0x180003d3f  lea     rax, [rbp+60h+var_C0]
0x180003d43  mov     rcx, [rbp+60h+hKey]; hKey
0x180003d47  lea     r9, [rbp+60h+Type]; lpType
0x180003d4b  mov     qword ptr [rsp+160h+cbData], rax; lpcbData
0x180003d50  lea     rdx, [rbp+60h+pszDest]; lpValueName
0x180003d54  xor     r8d, r8d; lpReserved
0x180003d57  mov     [rsp+160h+lpData], rsi; lpData
0x180003d5c  call    cs:__imp_RegQueryValueExW
0x180003d62  jmp     loc_180003C42
0x180003d67  mov     r8d, eax
0x180003d6a  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x180003d71  call    WfpReportSysErrorAsWinError
0x180003d76  mov     rbx, rax
0x180003d79  jmp     loc_180003C49
0x180003d7e  lea     rdx, aBferegqueryval; "BfeRegQueryValue"
0x180003d85  mov     rcx, rbx
0x180003d88  call    WfpReportError
0x180003d8d  lea     rdx, aBferegquerybin; "BfeRegQueryBinary"
0x180003d94  jmp     loc_180088551
0x180003d99  mov     r8d, eax
0x180003d9c  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x180003da3  call    WfpReportSysErrorAsWinError
0x180003da8  mov     rbx, rax
0x180003dab  jmp     loc_180003B7B
0x180003db0  lea     rdx, aBferegsetbinar; "BfeRegSetBinary"
0x180003db7  jmp     loc_180088551
0x180003dbc  lea     rdx, aBfefiltersetbo; "BfeFilterSetBootTime"
0x180003dc3  mov     rcx, rbx
0x180003dc6  call    WfpReportError
0x180003dcb  jmp     loc_180003B9D
0x180088508  mov     rcx, cs:WPP_GLOBAL_Control
0x18008850f  lea     rax, WPP_GLOBAL_Control
0x180088516  cmp     rcx, rax
0x180088519  jz      loc_180003C90
0x18008851f  cmp     byte ptr [rcx+19h], 3
0x180088523  jb      loc_180003C90
0x180088529  test    byte ptr [rcx+1Ch], 2
0x18008852d  jz      loc_180003C90
0x180088533  mov     r9, [r15]
0x180088536  lea     r8, WPP_0ac2aa085a863ed18a171940451ff39f_Traceguids
0x18008853d  mov     rcx, [rcx+10h]
0x180088541  mov     edx, 17h
0x180088546  call    WPP_SF__guid_
0x18008854b  nop
0x18008854c  jmp     loc_180003C90
0x180088551  mov     rcx, rbx
0x180088554  call    WfpReportError
0x180088559  nop
0x18008855a  jmp     loc_180003B8B
```
