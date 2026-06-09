# BfeFilterSetBootTime

- ea: `0x180003a20`
- end: `0x180003da6`
- name: `BfeFilterSetBootTime`
- size: `902`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config`

## callees

- `0x180003a20`
- `0x180004070`
- `0x1800048a8`
- `0x180005238`
- `0x18000e7e0`
- `0x18000ecf0`
- `0x180012d8c`
- `0x1800197d0`
- `0x180024e40`
- `0x18003f4ec`
- `0x18005aa60`
- `0x180066ea8`
- `0x18006944c`
- `0x18008ad60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003c5c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008b4f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003c5c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008b4f4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003b91`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003b91`

## string_xrefs

- `0x180003d72`: `RegSetValueExW`
- `0x180003d86`: `BfeRegSetBinary`

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
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_082cac24a57a3351f8a132228278c8a6_Traceguids, *a1);
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
0x180003a20  mov     [rsp-8+arg_10], rbx
0x180003a25  push    rbp
0x180003a26  push    rsi
0x180003a27  push    rdi
0x180003a28  push    r12
0x180003a2a  push    r13
0x180003a2c  push    r14
0x180003a2e  push    r15
0x180003a30  lea     rbp, [rsp-30h]
0x180003a35  sub     rsp, 130h
0x180003a3c  mov     rax, cs:__security_cookie
0x180003a43  xor     rax, rsp
0x180003a46  mov     [rbp+60h+var_40], rax
0x180003a4a  xor     ebx, ebx
0x180003a4c  mov     [rbp+60h+var_C8], rdx
0x180003a50  xorps   xmm0, xmm0
0x180003a53  mov     [rbp+60h+var_E0], rbx
0x180003a57  mov     r12, rdx
0x180003a5a  mov     [rbp+60h+Type], ebx
0x180003a5d  mov     rdx, [rcx]
0x180003a60  mov     r15, rcx
0x180003a63  movups  [rbp+60h+var_B8], xmm0
0x180003a67  movups  [rbp+60h+var_A8], xmm0
0x180003a6b  test    byte ptr [rdx+20h], 2
0x180003a6f  jz      loc_180003BB5
0x180003a75  mov     rax, [rcx+8]
0x180003a79  mov     rcx, [rax]
0x180003a7c  movzx   eax, word ptr [rcx+40h]
0x180003a80  mov     dword ptr [rbp+60h+var_B8+4], eax
0x180003a83  test    dword ptr [rdx+80h], 4000h
0x180003a8d  jz      short loc_180003A9B
0x180003a8f  movups  xmm0, xmmword ptr [rdx+84h]
0x180003a96  movdqu  [rbp+60h+var_B8+8], xmm0
0x180003a9b  mov     rax, [r15+10h]
0x180003a9f  lea     r9, [rbp+60h+Type]
0x180003aa3  lea     r8, [rbp+60h+var_E0]
0x180003aa7  mov     qword ptr [rbp+60h+var_A8+8], rax
0x180003aab  lea     rdx, [rbp+60h+var_B8]
0x180003aaf  lea     rcx, WFP_BOOTTIME_FILTER_MARSHAL_Encode
0x180003ab6  call    WfpMidlObjectEncode
0x180003abb  mov     rbx, rax
0x180003abe  test    rax, rax
0x180003ac1  jnz     loc_180003BB5
0x180003ac7  mov     r9, [r15]
0x180003aca  movzx   ecx, byte ptr [r9+0Eh]
0x180003acf  movzx   edx, byte ptr [r9+0Dh]
0x180003ad4  movzx   r8d, byte ptr [r9+0Ch]
0x180003ad9  movzx   eax, byte ptr [r9+0Fh]
0x180003ade  movzx   r10d, byte ptr [r9+0Bh]
0x180003ae3  movzx   r11d, byte ptr [r9+0Ah]
0x180003ae8  movzx   ebx, byte ptr [r9+9]
0x180003aed  movzx   edi, byte ptr [r9+8]
0x180003af2  movzx   esi, word ptr [r9+6]
0x180003af7  movzx   r14d, word ptr [r9+4]
0x180003afc  mov     r9d, [r9]
0x180003aff  mov     [rsp+160h+var_F8], eax
0x180003b03  mov     [rsp+160h+var_100], ecx
0x180003b07  lea     rcx, [rbp+60h+pszDest]; pszDest
0x180003b0b  mov     [rsp+160h+var_108], edx
0x180003b0f  mov     edx, 27h ; '''; cchDest
0x180003b14  mov     [rsp+160h+var_110], r8d
0x180003b19  lea     r8, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x180003b20  mov     [rsp+160h+var_118], r10d
0x180003b25  mov     [rsp+160h+var_120], r11d
0x180003b2a  mov     [rsp+160h+var_128], ebx
0x180003b2e  mov     [rsp+160h+var_130], edi
0x180003b32  mov     [rsp+160h+cbData], esi
0x180003b36  mov     dword ptr [rsp+160h+lpData], r14d
0x180003b3b  call    StringCchPrintfW
0x180003b40  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b47  lea     rax, WPP_GLOBAL_Control
0x180003b4e  cmp     rcx, rax
0x180003b51  jz      short loc_180003B5D
0x180003b53  cmp     byte ptr [rcx+19h], 4
0x180003b57  jnb     loc_180003D08
0x180003b5d  cmp     dword ptr [r12+8], 0
0x180003b63  mov     r13d, [rbp+60h+Type]
0x180003b67  jz      loc_180003BF2
0x180003b6d  call    BfeCallGetSysTxn
0x180003b72  mov     rax, [rbp+60h+var_E0]
0x180003b76  lea     rdx, [rbp+60h+pszDest]; lpValueName
0x180003b7a  mov     rcx, [r12]; hKey
0x180003b7e  xor     ebx, ebx
0x180003b80  mov     [rsp+160h+cbData], r13d; cbData
0x180003b85  xor     r8d, r8d; Reserved
0x180003b88  mov     [rsp+160h+lpData], rax; lpData
0x180003b8d  lea     r9d, [rbx+3]; dwType
0x180003b91  call    cs:__imp_RegSetValueExW
0x180003b98  nop     dword ptr [rax+rax+00h]
0x180003b9d  test    eax, eax
0x180003b9f  jnz     loc_180003D6F
0x180003ba5  xor     ecx, ecx
0x180003ba7  call    BfeRegCloseKey
0x180003bac  test    rbx, rbx
0x180003baf  jnz     loc_180003D86
0x180003bb5  lea     rcx, [rbp+60h+var_E0]
0x180003bb9  call    WfpMemFree
0x180003bbe  test    rbx, rbx
0x180003bc1  jnz     loc_180003D92
0x180003bc7  mov     rax, rbx
0x180003bca  mov     rcx, [rbp+60h+var_40]
0x180003bce  xor     rcx, rsp; StackCookie
0x180003bd1  call    __security_check_cookie
0x180003bd6  mov     rbx, [rsp+160h+arg_10]
0x180003bde  add     rsp, 130h
0x180003be5  pop     r15
0x180003be7  pop     r14
0x180003be9  pop     r13
0x180003beb  pop     r12
0x180003bed  pop     rdi
0x180003bee  pop     rsi
0x180003bef  pop     rbp
0x180003bf0  retn
0x180003bf2  call    BfeCallGetSysTxn
0x180003bf7  mov     rax, [r12]
0x180003bfb  lea     r8, [rsp+160h+var_E8]
0x180003c00  mov     ecx, 1000h; dwBytes
0x180003c05  mov     [rbp+60h+hKey], rax
0x180003c09  xor     r14d, r14d
0x180003c0c  mov     [rbp+60h+var_C0], ecx
0x180003c0f  xor     edx, edx; dwFlags
0x180003c11  mov     [rbp+60h+Type], 0
0x180003c18  mov     [rsp+160h+var_E8], 0
0x180003c21  xor     esi, esi
0x180003c23  mov     [rbp+60h+var_D0], r14
0x180003c27  call    WfpMemAlloc
0x180003c2c  xor     edi, edi
0x180003c2e  lea     r12d, [r14+1]
0x180003c32  mov     rbx, rax
0x180003c35  test    rax, rax
0x180003c38  jnz     short loc_180003C7C
0x180003c3a  mov     rsi, [rsp+160h+var_E8]
0x180003c3f  lea     rax, [rbp+60h+var_C0]
0x180003c43  mov     rcx, [rbp+60h+hKey]; hKey
0x180003c47  lea     r9, [rbp+60h+Type]; lpType
0x180003c4b  mov     qword ptr [rsp+160h+cbData], rax; lpcbData
0x180003c50  lea     rdx, [rbp+60h+pszDest]; lpValueName
0x180003c54  xor     r8d, r8d; lpReserved
0x180003c57  mov     [rsp+160h+lpData], rsi; lpData
0x180003c5c  call    cs:__imp_RegQueryValueExW
0x180003c63  nop     dword ptr [rax+rax+00h]
0x180003c68  cmp     eax, 0EAh
0x180003c6d  jz      loc_18008B4A8
0x180003c73  xor     edi, edi
0x180003c75  cmp     eax, 2
0x180003c78  jnz     short loc_180003CDC
0x180003c7a  mov     esi, edi
0x180003c7c  lea     rcx, [rsp+160h+var_E8]
0x180003c81  call    WfpMemFree
0x180003c86  xor     ecx, ecx
0x180003c88  call    BfeRegCloseKey
0x180003c8d  test    rbx, rbx
0x180003c90  jnz     loc_180003D54
0x180003c96  test    esi, esi
0x180003c98  jz      loc_18008B506
0x180003c9e  cmp     r13d, edi
0x180003ca1  jnz     loc_18008B506
0x180003ca7  mov     rcx, [rbp+60h+var_E0]; Buf1
0x180003cab  mov     r8, r13; Size
0x180003cae  mov     rdx, r14; Buf2
0x180003cb1  call    memcmp_0
0x180003cb6  test    eax, eax
0x180003cb8  jnz     loc_18008B506
0x180003cbe  xor     r12d, r12d
0x180003cc1  lea     rcx, [rbp+60h+var_D0]
0x180003cc5  call    WfpMemFree
0x180003cca  test    r12d, r12d
0x180003ccd  jz      loc_180003BB5
0x180003cd3  mov     r12, [rbp+60h+var_C8]
0x180003cd7  jmp     loc_180003B6D
0x180003cdc  cmp     eax, 0EAh
0x180003ce1  jz      short loc_180003C7A
0x180003ce3  test    eax, eax
0x180003ce5  jnz     short loc_180003D3D
0x180003ce7  cmp     [rbp+60h+Type], 3
0x180003ceb  jnz     short loc_180003C7A
0x180003ced  mov     edi, [rbp+60h+var_C0]
0x180003cf0  mov     r14, rsi
0x180003cf3  mov     [rbp+60h+var_D0], rsi
0x180003cf7  mov     esi, r12d
0x180003cfa  mov     [rsp+160h+var_E8], 0
0x180003d03  jmp     loc_180003C7C
0x180003d08  test    byte ptr [rcx+1Ch], 2
0x180003d0c  jz      loc_180003B5D
0x180003d12  mov     r9, [r15]
0x180003d15  mov     edx, 16h
0x180003d1a  mov     rcx, [rcx+10h]
0x180003d1e  mov     rax, [r9+0B0h]
0x180003d25  lea     r8, [r9+40h]
0x180003d29  mov     qword ptr [rsp+160h+cbData], rax
0x180003d2e  mov     [rsp+160h+lpData], r8
0x180003d33  call    WPP_SF__guid__guid_I
0x180003d38  jmp     loc_180003B5D
0x180003d3d  mov     r8d, eax
0x180003d40  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x180003d47  call    WfpReportSysErrorAsWinError
0x180003d4c  mov     rbx, rax
0x180003d4f  jmp     loc_180003C7A
0x180003d54  lea     rdx, aBferegqueryval; "BfeRegQueryValue"
0x180003d5b  mov     rcx, rbx
0x180003d5e  call    WfpReportError
0x180003d63  lea     rdx, aBferegquerybin; "BfeRegQueryBinary"
0x180003d6a  jmp     loc_18008B54F
0x180003d6f  mov     r8d, eax
0x180003d72  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x180003d79  call    WfpReportSysErrorAsWinError
0x180003d7e  mov     rbx, rax
0x180003d81  jmp     loc_180003BA5
0x180003d86  lea     rdx, aBferegsetbinar; "BfeRegSetBinary"
0x180003d8d  jmp     loc_18008B54F
0x180003d92  lea     rdx, aBfefiltersetbo; "BfeFilterSetBootTime"
0x180003d99  mov     rcx, rbx
0x180003d9c  call    WfpReportError
0x180003da1  jmp     loc_180003BC7
0x18008b4a8  mov     ecx, [rbp+60h+var_C0]; dwBytes
0x18008b4ab  lea     rax, [rsp+160h+var_E8]
0x18008b4b0  mov     r9, rsi
0x18008b4b3  mov     [rsp+160h+lpData], rax; __int64
0x18008b4b8  xor     r8d, r8d
0x18008b4bb  lea     edx, [rcx-1000h]
0x18008b4c1  call    WfpMemReAlloc
0x18008b4c6  mov     rbx, rax
0x18008b4c9  test    rax, rax
0x18008b4cc  jnz     loc_180003C7A
0x18008b4d2  mov     rsi, [rsp+160h+var_E8]
0x18008b4d7  lea     rax, [rbp+60h+var_C0]
0x18008b4db  mov     rcx, [rbp+60h+hKey]; hKey
0x18008b4df  lea     r9, [rbp+60h+Type]; lpType
0x18008b4e3  mov     qword ptr [rsp+160h+cbData], rax; lpcbData
0x18008b4e8  lea     rdx, [rbp+60h+pszDest]; lpValueName
0x18008b4ec  xor     r8d, r8d; lpReserved
0x18008b4ef  mov     [rsp+160h+lpData], rsi; lpData
0x18008b4f4  call    cs:__imp_RegQueryValueExW
0x18008b4fb  nop     dword ptr [rax+rax+00h]
0x18008b500  nop
0x18008b501  jmp     loc_180003C73
0x18008b506  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b50d  lea     rax, WPP_GLOBAL_Control
0x18008b514  cmp     rcx, rax
0x18008b517  jz      loc_180003CC1
0x18008b51d  cmp     byte ptr [rcx+19h], 3
0x18008b521  jb      loc_180003CC1
0x18008b527  test    byte ptr [rcx+1Ch], 2
0x18008b52b  jz      loc_180003CC1
0x18008b531  mov     r9, [r15]
0x18008b534  lea     r8, WPP_082cac24a57a3351f8a132228278c8a6_Traceguids
0x18008b53b  mov     rcx, [rcx+10h]
0x18008b53f  mov     edx, 17h
0x18008b544  call    WPP_SF__guid_
0x18008b549  nop
0x18008b54a  jmp     loc_180003CC1
0x18008b54f  mov     rcx, rbx
0x18008b552  call    WfpReportError
0x18008b557  nop
0x18008b558  jmp     loc_180003BB5
```
