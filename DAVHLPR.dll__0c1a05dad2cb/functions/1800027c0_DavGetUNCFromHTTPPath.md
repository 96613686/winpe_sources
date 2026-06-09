# DavGetUNCFromHTTPPath

- ea: `0x1800027c0`
- end: `0x180003176`
- name: `DavGetUNCFromHTTPPath`
- size: `2486`
- prototype: `DWORD __stdcall(LPCWSTR Url, LPWSTR UncPath, LPDWORD lpSize)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180005450`

## callees

- `0x1800027c0`
- `0x180003180`
- `0x180003300`
- `0x180003570`
- `0x180003be0`
- `0x1800040b0`
- `0x180004850`

## import_xrefs

- `msvcrt!wcscspn` at `0x18000286b`
- `msvcrt!wcscspn` at `0x1800028bb`
- `msvcrt!wcscspn` at `0x1800028e8`
- `msvcrt!wcscspn` at `0x180002925`
- `msvcrt!wcscspn` at `0x180002d32`
- `msvcrt!wcscspn` at `0x180002f57`
- `msvcrt!wcscspn` at `0x180002fcc`
- `msvcrt!wcscspn` at `0x18000286b`
- `msvcrt!wcscspn` at `0x1800028bb`
- `msvcrt!wcscspn` at `0x1800028e8`
- `msvcrt!wcscspn` at `0x180002925`
- `msvcrt!wcscspn` at `0x180002d32`
- `msvcrt!wcscspn` at `0x180002f57`
- `msvcrt!wcscspn` at `0x180002fcc`
- `msvcrt!towupper` at `0x18000298a`
- `msvcrt!towupper` at `0x18000298a`
- `msvcrt!_wcsnicmp` at `0x180002964`
- `msvcrt!_wcsnicmp` at `0x180002964`
- `KERNEL32!LocalFree` at `0x180002b08`
- `KERNEL32!LocalFree` at `0x180002b96`
- `KERNEL32!LocalFree` at `0x180002c8b`
- `KERNEL32!LocalFree` at `0x18000312d`
- `KERNEL32!LocalFree` at `0x180002b08`
- `KERNEL32!LocalFree` at `0x180002b96`
- `KERNEL32!LocalFree` at `0x180002c8b`
- `KERNEL32!LocalFree` at `0x18000312d`
- `KERNEL32!GetLastError` at `0x180002e86`
- `KERNEL32!GetLastError` at `0x180003115`
- `KERNEL32!GetLastError` at `0x180002e86`
- `KERNEL32!GetLastError` at `0x180003115`
- `KERNEL32!LocalAlloc` at `0x1800029cc`
- `KERNEL32!LocalAlloc` at `0x180002c0d`
- `KERNEL32!LocalAlloc` at `0x1800029cc`
- `KERNEL32!LocalAlloc` at `0x180002c0d`

## pseudocode

```c
DWORD __stdcall DavGetUNCFromHTTPPath(LPCWSTR Url, LPWSTR UncPath, LPDWORD lpSize)
{
  LPWSTR v3; // r15
  LPCWSTR v4; // rbx
  WCHAR *v6; // r14
  size_t v7; // rax
  unsigned __int16 *v8; // r13
  const wchar_t *v9; // rdi
  unsigned __int16 *v10; // rsi
  bool v11; // zf
  size_t v12; // rax
  const wchar_t *v13; // r12
  char v14; // r15
  size_t v15; // rax
  unsigned __int16 *v16; // r14
  unsigned __int64 v17; // rsi
  size_t v18; // r8
  unsigned __int64 v19; // rsi
  char v20; // dl
  int v21; // ecx
  __int64 v22; // r14
  SIZE_T v23; // r14
  char *v24; // r9
  unsigned __int16 *v25; // r15
  unsigned int v26; // r12d
  char v27; // r10
  __int64 v28; // rsi
  int v29; // eax
  char *v30; // r11
  char v31; // r14
  int v32; // eax
  unsigned int v33; // ecx
  DWORD v34; // ebx
  _DWORD *v35; // r10
  __int64 v36; // rdx
  __int64 v37; // rax
  WCHAR *v38; // rcx
  __int64 v39; // r9
  LPWSTR v40; // rcx
  __int64 v41; // r8
  int v42; // eax
  _WORD *v43; // rdi
  _WORD *v44; // rax
  unsigned __int16 v45; // ax
  char v46; // dl
  unsigned __int16 v47; // r8
  char v48; // al
  unsigned __int8 v49; // dl
  size_t v50; // rax
  __int64 v51; // r8
  unsigned __int16 v52; // ax
  unsigned __int16 v53; // r8
  DWORD LastError; // eax
  __int16 v55; // ax
  unsigned __int16 v56; // ax
  char32_t v57; // r9d
  __int64 v58; // rcx
  unsigned __int64 v59; // rcx
  __int16 v60; // bx
  char v61; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v62; // [rsp+32h] [rbp-CEh]
  unsigned int v63; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int8 v64; // [rsp+3Ch] [rbp-C4h]
  char v65; // [rsp+3Dh] [rbp-C3h]
  HLOCAL v66; // [rsp+40h] [rbp-C0h]
  char32_t v67; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v68; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL v69; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v70; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem[2]; // [rsp+70h] [rbp-90h]
  char *v72; // [rsp+80h] [rbp-80h]
  __int128 v73; // [rsp+90h] [rbp-70h]
  __int128 v74; // [rsp+C0h] [rbp-40h]
  __int128 v75; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v76; // [rsp+160h] [rbp+60h] BYREF
  LPWSTR v77; // [rsp+168h] [rbp+68h]
  LPDWORD v78; // [rsp+170h] [rbp+70h]
  __int16 v79; // [rsp+178h] [rbp+78h] BYREF

  v78 = lpSize;
  v77 = UncPath;
  v3 = UncPath;
  v4 = Url;
  if ( !Url || !lpSize || *lpSize && !UncPath )
    return 87;
  v6 = 0;
  v66 = 0;
  TriggerStartWebclientServiceIfNotRunning();
  v70 = 0;
  v72 = 0;
  *(_OWORD *)hMem = 0;
  v69 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v7 = wcscspn(v4, L":/");
  if ( v4[v7] == 58 )
  {
    if ( !v7 )
      goto LABEL_96;
    *(_QWORD *)&v73 = v4;
    v8 = (unsigned __int16 *)&v4[v7 + 1];
    *((_QWORD *)&v73 + 1) = &v4[v7];
  }
  else
  {
    v8 = (unsigned __int16 *)v4;
    v4 = (LPCWSTR)v73;
  }
  if ( *v8 != 47 || v8[1] != 47 )
  {
    v13 = (const wchar_t *)*((_QWORD *)&v74 + 1);
    v9 = (const wchar_t *)v74;
    goto LABEL_15;
  }
  v9 = v8 + 2;
  v10 = &v8[wcscspn(v8 + 2, L"@/") + 2];
  if ( *v10 == 64 )
  {
    wcscspn(v8 + 2, L":@");
    v9 = v10 + 1;
  }
  v11 = *v9 == 91;
  *(_QWORD *)&v74 = v9;
  if ( v11 )
  {
    v50 = wcscspn(v9, L"]/");
    v11 = v9[v50] == 93;
    v8 = (unsigned __int16 *)&v9[v50];
    v13 = &v9[v50];
    *((_QWORD *)&v74 + 1) = &v9[v50];
    if ( !v11 || (__int64)((v50 * 2) & 0xFFFFFFFFFFFFFFFEuLL) < 6 )
      goto LABEL_96;
  }
  else
  {
    v12 = wcscspn(v9, L":/");
    v8 = (unsigned __int16 *)&v9[v12];
    *((_QWORD *)&v74 + 1) = &v9[v12];
    v13 = &v9[v12];
    if ( (__int64)((v12 * 2) & 0xFFFFFFFFFFFFFFFEuLL) < 2 )
      goto LABEL_96;
  }
  if ( *v8 != 58 )
  {
LABEL_15:
    v14 = BYTE2(v75);
    goto LABEL_16;
  }
  v76 = v8 + 1;
  if ( (unsigned int)DavpParseUInt16(&v76, &v75) || (v8 = v76, *v76) && *v76 != 47 )
  {
LABEL_96:
    v34 = 53;
    goto LABEL_49;
  }
  v13 = (const wchar_t *)*((_QWORD *)&v74 + 1);
  v14 = 1;
  v9 = (const wchar_t *)v74;
  v4 = (LPCWSTR)v73;
LABEL_16:
  v15 = wcscspn(v8, L"?#");
  v16 = &v8[v15];
  if ( *v16 == 63 )
    wcscspn(&v8[v15], L"#");
  v17 = (__int64)(*((_QWORD *)&v73 + 1) - (_QWORD)v4) >> 1;
  v18 = v17;
  if ( v17 > 4 )
    v18 = 4;
  if ( _wcsnicmp(v4, L"http", v18) )
    goto LABEL_116;
  v19 = v17 - 4;
  if ( v19 )
  {
    if ( v19 == 1 && towupper(v4[4]) == 83 )
    {
      v20 = 1;
      v21 = v70 | 1;
      LODWORD(v70) = v70 | 1;
      goto LABEL_25;
    }
LABEL_116:
    v34 = 87;
    goto LABEL_47;
  }
  v21 = v70;
  v20 = 0;
LABEL_25:
  hMem[0] = (HLOCAL)v13;
  *((_QWORD *)&v70 + 1) = v9;
  if ( v14 )
  {
    v55 = 443;
    if ( !v20 )
      v55 = 80;
    if ( (_WORD)v75 != v55 )
    {
      WORD2(v70) = v75;
      LODWORD(v70) = v21 | 2;
    }
  }
  v22 = v16 - v8;
  v11 = v22 == 0;
  v23 = 2 * v22;
  if ( !v11 )
  {
    hMem[1] = LocalAlloc(0, v23);
    if ( !hMem[1] )
    {
      LastError = GetLastError();
LABEL_114:
      v34 = LastError;
      goto LABEL_47;
    }
  }
  v24 = (char *)hMem[1];
  v25 = &v8[v23 / 2];
  v26 = v63;
  v27 = 0;
  v28 = 0;
  v68 = v8;
  v29 = 0;
  v61 = 0;
  v30 = (char *)hMem[1] + v23;
  v31 = 0;
  v65 = 0;
  v79 = 0;
  while ( v8 < v25 )
  {
    if ( v24 >= v30 )
    {
      while ( v8 < v25 )
      {
        v67 = 0;
        LastError = DavpUrlDecodeToNtPathDecodeHelper(
                      (unsigned int)&v68,
                      (_DWORD)v25,
                      (unsigned int)&v63,
                      (unsigned int)&v61,
                      (__int64)&v67);
        if ( LastError == 997 )
          goto LABEL_146;
        if ( LastError )
          goto LABEL_114;
        LastError = Utf16Encoder::ProcessCodePoint((Utf16Encoder *)&v79, v67, (unsigned __int16 *)&v76);
        ++v28;
        if ( !LastError )
        {
LABEL_146:
          v8 = v68;
        }
        else
        {
          if ( LastError != 234 )
            goto LABEL_114;
          LastError = Utf16Encoder::ProcessCodePoint((Utf16Encoder *)&v79, v57, (unsigned __int16 *)&v76);
          if ( LastError )
            goto LABEL_114;
          v8 = v68;
          ++v28;
        }
      }
      v31 = v65;
      v29 = 122;
      v27 = v61;
      break;
    }
    v32 = *v8;
    v33 = 0;
    if ( v32 != 37 )
    {
      if ( v31 )
        goto LABEL_46;
      if ( v27 )
      {
        v27 = 0;
        v56 = v32 + 9216;
        v61 = 0;
        if ( v56 <= 0x3FFu )
        {
          v33 = v56 + (v62 << 10) + 0x10000;
          v34 = 0;
          goto LABEL_36;
        }
      }
      else
      {
        if ( (unsigned __int16)(v32 + 10240) >= 0x800u )
        {
          v33 = *v8;
          v34 = 0;
LABEL_36:
          ++v8;
          goto LABEL_37;
        }
        if ( (unsigned __int16)(v32 + 10240) <= 0x3FFu )
        {
          v27 = 1;
          v62 = v32 + 10240;
          v61 = 1;
          v34 = 997;
          goto LABEL_36;
        }
      }
      v34 = 582;
      goto LABEL_36;
    }
    if ( v27 || (__int64)(((char *)v25 - (char *)v8) & 0xFFFFFFFFFFFFFFFEuLL) < 6 )
    {
LABEL_46:
      v34 = 582;
      goto LABEL_47;
    }
    v45 = v8[1];
    v46 = v45 - 48;
    if ( (unsigned __int16)(v45 - 48) >= 0xAu )
    {
      v52 = (v45 | 0x20) - 97;
      if ( v52 >= 6u )
        goto LABEL_46;
      v46 = v52 + 10;
    }
    v47 = v8[2];
    v48 = v47 - 48;
    if ( (unsigned __int16)(v47 - 48) >= 0xAu )
    {
      v53 = (v47 | 0x20) - 97;
      if ( v53 >= 6u )
        goto LABEL_46;
      v48 = v53 + 10;
    }
    v49 = v48 | (16 * v46);
    if ( v31 )
    {
      if ( (v49 & 0xC0) == 0x80 )
      {
        v26 = (v26 << 6) | v49 & 0x3F;
        v11 = v31-- == 1;
        v63 = v26;
        v65 = v31;
        if ( !v11 )
        {
          v34 = 997;
LABEL_94:
          v8 += 3;
          goto LABEL_37;
        }
        if ( v26 >= dword_1800076F0[v64] && (v26 <= 0xD7FF || v26 - 57344 <= 0x101FFF) )
        {
          v34 = 0;
          v33 = v26;
          goto LABEL_94;
        }
      }
LABEL_100:
      v34 = 582;
      v8 += 3;
      goto LABEL_37;
    }
    if ( v49 < 0x80u )
    {
      v33 = (char)v49;
      v34 = 0;
      goto LABEL_94;
    }
    v51 = *((unsigned __int8 *)qword_1800074E8 + ((unsigned __int64)v49 >> 3));
    if ( !(_BYTE)v51 )
      goto LABEL_100;
    v31 = v51 - 1;
    v26 = v49 & ~(unsigned __int8)byte_1800076E1[2 * v51];
    v64 = *((_BYTE *)qword_1800074E8 + ((unsigned __int64)v49 >> 3));
    v63 = v26;
    v8 += 3;
    v65 = v51 - 1;
    v34 = 997;
LABEL_37:
    v68 = v8;
    if ( !v34 && v33 == 47 )
      v33 = 92;
    v29 = v34;
    if ( v34 != 997 )
    {
      if ( v34 )
        goto LABEL_47;
      if ( v33 <= 0x10FFFF && v33 - 55296 > 0x7FF )
      {
        if ( v33 > 0xFFFF )
        {
          *(_WORD *)v24 = ((v33 - 0x10000) >> 10) | 0xD800;
          v24 += 2;
          if ( v24 < v30 )
          {
            v29 = 0;
            *(_WORD *)v24 = v33 & 0x3FF | 0xDC00;
            v79 = 0;
            v24 += 2;
          }
          else
          {
            v79 = 0;
            v29 = 122;
          }
          v28 += 2;
        }
        else
        {
          *(_WORD *)v24 = v33;
          v29 = 0;
          v24 += 2;
          ++v28;
        }
      }
      else
      {
        v29 = 582;
        v24 += 2;
        ++v28;
      }
    }
  }
  if ( v31 )
    v34 = 582;
  else
    v34 = v27 != 0 ? 0x246 : 0;
  if ( !v34 )
    v34 = v29;
  if ( v34 )
  {
LABEL_47:
    v6 = (WCHAR *)v66;
    goto LABEL_48;
  }
  v43 = 0;
  v76 = 0;
  v72 = (char *)hMem[1] + 2 * v28;
  v34 = DavCreateUncPath((int *)&v70, 0, (unsigned __int64 *)&v76);
  if ( v34 != 122 )
    goto LABEL_75;
  if ( !is_mul_ok((unsigned __int64)v76, 2u) )
  {
    v34 = 534;
    v6 = 0;
    goto LABEL_48;
  }
  v44 = LocalAlloc(0, 2LL * (_QWORD)v76);
  v43 = v44;
  if ( !v44 )
  {
    v34 = GetLastError();
    goto LABEL_47;
  }
  v34 = DavCreateUncPath((int *)&v70, v44, (unsigned __int64 *)&v76);
LABEL_75:
  if ( v34 )
    goto LABEL_82;
  if ( v43[(_QWORD)v76 - 2] == 92 )
    v43[(_QWORD)v76 - 2] = 0;
  if ( !(unsigned int)DavCanonicalizeUncPathAndDetermineType(v43, (wchar_t **)&v69, 0) )
  {
    v34 = 67;
    if ( v69 )
      LocalFree(v69);
LABEL_82:
    v6 = (WCHAR *)v66;
    goto LABEL_83;
  }
  v6 = (WCHAR *)v69;
  v34 = 0;
LABEL_83:
  if ( v43 )
    LocalFree(v43);
LABEL_48:
  v3 = v77;
LABEL_49:
  if ( hMem[1] )
    LocalFree(hMem[1]);
  if ( !v34 )
  {
    v35 = v78;
    v36 = *v78;
    if ( (_DWORD)v36 )
    {
      if ( (unsigned int)v36 > 0x7FFFFFFF )
      {
        *v3 = 0;
      }
      else
      {
        v37 = 2147483646;
        v38 = v6;
        v39 = 0;
        do
        {
          if ( !v37 )
            break;
          if ( !*v38 )
            break;
          *v3++ = *v38++;
          --v37;
          ++v39;
          --v36;
        }
        while ( v36 );
        v40 = v3 - 1;
        v41 = v39 - 1;
        if ( v36 )
        {
          v40 = v3;
          v41 = v39;
        }
        *v40 = 0;
        if ( v36 )
        {
          v42 = ((2 * v41) >> 1) + 1;
          v34 = 0;
          goto LABEL_62;
        }
      }
    }
    v58 = -1;
    do
      ++v58;
    while ( v6[v58] );
    v59 = v58 + 1;
    v42 = -1;
    if ( v59 <= 0xFFFFFFFF )
      v42 = v59;
    v60 = 0;
    if ( v59 > 0xFFFFFFFF )
      v60 = -1;
    v34 = (v60 & 0x19C) + 122;
LABEL_62:
    *v35 = v42;
  }
  if ( v6 )
    LocalFree(v6);
  return v34;
}

```

## disassembly

```asm
0x1800027c0  mov     [rsp-8+arg_10], r8
0x1800027c5  mov     [rsp-8+arg_8], rdx
0x1800027ca  push    rbp
0x1800027cb  push    rbx
0x1800027cc  push    r15
0x1800027ce  lea     rbp, [rsp-40h]
0x1800027d3  sub     rsp, 140h
0x1800027da  mov     rax, r8
0x1800027dd  mov     r15, rdx
0x1800027e0  mov     rbx, rcx
0x1800027e3  test    rcx, rcx
0x1800027e6  jnz     short loc_1800027F9
0x1800027e8  mov     eax, 57h ; 'W'
0x1800027ed  add     rsp, 140h
0x1800027f4  pop     r15
0x1800027f6  pop     rbx
0x1800027f7  pop     rbp
0x1800027f8  retn
0x1800027f9  test    rax, rax
0x1800027fc  jz      short loc_1800027E8
0x1800027fe  cmp     dword ptr [r8], 0
0x180002802  jnz     loc_180002C96
0x180002808  mov     [rsp+150h+var_18], rsi
0x180002810  mov     [rsp+150h+var_20], rdi
0x180002818  mov     [rsp+150h+var_28], r12
0x180002820  mov     [rsp+150h+var_30], r13
0x180002828  mov     [rsp+150h+var_38], r14
0x180002830  xor     r14d, r14d
0x180002833  mov     [rsp+150h+var_110], r14
0x180002838  call    TriggerStartWebclientServiceIfNotRunning
0x18000283d  xorps   xmm0, xmm0
0x180002840  lea     rdx, asc_1800073A0; ":/"
0x180002847  xor     eax, eax
0x180002849  mov     rcx, rbx; String
0x18000284c  movups  [rsp+150h+var_F0], xmm0
0x180002851  mov     [rbp+50h+var_D0], rax
0x180002855  movups  xmmword ptr [rsp+150h+hMem], xmm0
0x18000285a  mov     [rsp+150h+var_F8], rax
0x18000285f  movups  [rbp+50h+var_C0], xmm0
0x180002863  movups  [rbp+50h+var_90], xmm0
0x180002867  movups  [rbp+50h+var_80], xmm0
0x18000286b  call    cs:__imp_wcscspn
0x180002871  cmp     word ptr [rbx+rax*2], 3Ah ; ':'
0x180002876  lea     rcx, [rbx+rax*2]
0x18000287a  jnz     loc_180002F41
0x180002880  test    rax, rax
0x180002883  jz      loc_180002D51
0x180002889  mov     qword ptr [rbp+50h+var_C0], rbx
0x18000288d  lea     r13, [rcx+2]
0x180002891  mov     qword ptr [rbp+50h+var_C0+8], rcx
0x180002895  cmp     word ptr [r13+0], 2Fh ; '/'
0x18000289b  jnz     loc_180002D9E
0x1800028a1  cmp     word ptr [r13+2], 2Fh ; '/'
0x1800028a7  jnz     loc_180002D9E
0x1800028ad  lea     rdi, [r13+4]
0x1800028b1  mov     rcx, rdi; String
0x1800028b4  lea     rdx, asc_1800073BC; "@/"
0x1800028bb  call    cs:__imp_wcscspn
0x1800028c1  cmp     word ptr [rdi+rax*2], 40h ; '@'
0x1800028c6  lea     rsi, [rdi+rax*2]
0x1800028ca  jz      loc_180002F4D
0x1800028d0  cmp     word ptr [rdi], 5Bh ; '['
0x1800028d4  mov     rcx, rdi; String
0x1800028d7  mov     qword ptr [rbp+50h+var_90], rdi
0x1800028db  jz      loc_180002D2B
0x1800028e1  lea     rdx, asc_1800073A0; ":/"
0x1800028e8  call    cs:__imp_wcscspn
0x1800028ee  add     rax, rax
0x1800028f1  lea     r13, [rax+rdi]
0x1800028f5  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800028f9  mov     qword ptr [rbp+50h+var_90+8], r13
0x1800028fd  mov     r12, r13
0x180002900  cmp     rax, 2
0x180002904  jl      loc_180002D51
0x18000290a  cmp     word ptr [r13+0], 3Ah ; ':'
0x180002910  jz      loc_180002F79
0x180002916  movzx   r15d, byte ptr [rbp+50h+var_80+2]
0x18000291b  lea     rdx, asc_1800074E0; "?#"
0x180002922  mov     rcx, r13; String
0x180002925  call    cs:__imp_wcscspn
0x18000292b  lea     r14, ds:0[rax*2]
0x180002933  add     r14, r13
0x180002936  cmp     word ptr [r14], 3Fh ; '?'
0x18000293b  jz      loc_180002FC2
0x180002941  mov     rsi, qword ptr [rbp+50h+var_C0+8]
0x180002945  lea     rdx, aHttp; "http"
0x18000294c  mov     eax, 4
0x180002951  sub     rsi, rbx
0x180002954  sar     rsi, 1
0x180002957  mov     rcx, rbx; String1
0x18000295a  cmp     rsi, rax
0x18000295d  mov     r8, rsi
0x180002960  cmova   r8, rax; MaxCount
0x180002964  call    cs:__imp__wcsnicmp
0x18000296a  test    eax, eax
0x18000296c  jnz     loc_180002EA0
0x180002972  sub     rsi, 4
0x180002976  jz      loc_180002FD7
0x18000297c  cmp     rsi, 1
0x180002980  jnz     loc_180002EA0
0x180002986  movzx   ecx, word ptr [rbx+8]; C
0x18000298a  call    cs:__imp_towupper
0x180002990  cmp     ax, 53h ; 'S'
0x180002994  jnz     loc_180002EA0
0x18000299a  mov     ecx, dword ptr [rsp+150h+var_F0]
0x18000299e  movzx   edx, sil
0x1800029a2  or      ecx, esi
0x1800029a4  mov     dword ptr [rsp+150h+var_F0], ecx
0x1800029a8  mov     [rsp+150h+hMem], r12
0x1800029ad  mov     qword ptr [rsp+150h+var_F0+8], rdi
0x1800029b2  test    r15b, r15b
0x1800029b5  jnz     loc_180002FE2
0x1800029bb  sub     r14, r13
0x1800029be  sar     r14, 1
0x1800029c1  lea     r14, [r14+r14]
0x1800029c5  jz      short loc_1800029E0
0x1800029c7  mov     rdx, r14; uBytes
0x1800029ca  xor     ecx, ecx; uFlags
0x1800029cc  call    cs:__imp_LocalAlloc
0x1800029d2  mov     [rsp+150h+hMem+8], rax
0x1800029d7  test    rax, rax
0x1800029da  jz      loc_180002E86
0x1800029e0  mov     r9, [rsp+150h+hMem+8]
0x1800029e5  lea     r15, [r14+r13]
0x1800029e9  mov     r12d, [rsp+150h+var_118]
0x1800029ee  xor     r10b, r10b
0x1800029f1  xor     esi, esi
0x1800029f3  mov     [rsp+150h+var_100], r13
0x1800029f8  xor     eax, eax
0x1800029fa  mov     [rsp+150h+var_120], r10b
0x1800029ff  lea     r11, [r14+r9]
0x180002a03  mov     r8d, 2800h
0x180002a09  xor     r14b, r14b
0x180002a0c  xor     edi, edi
0x180002a0e  mov     [rsp+150h+var_113], r14b
0x180002a13  mov     [rbp+50h+arg_18], di
0x180002a17  nop     word ptr [rax+rax+00000000h]
0x180002a20  mov     edx, 3FFh
0x180002a25  cmp     r13, r15
0x180002a28  jnb     loc_180002BAB
0x180002a2e  cmp     r9, r11
0x180002a31  jnb     loc_180003066
0x180002a37  movzx   eax, word ptr [r13+0]
0x180002a3c  xor     ecx, ecx
0x180002a3e  cmp     eax, 25h ; '%'
0x180002a41  jz      loc_180002AC7
0x180002a47  test    r14b, r14b
0x180002a4a  jnz     loc_180002AD0
0x180002a50  test    r10b, r10b
0x180002a53  jnz     loc_180003033
0x180002a59  lea     edx, [r8+rax]
0x180002a5d  mov     ebx, 800h
0x180002a62  cmp     dx, bx
0x180002a65  jb      loc_180002E6E
0x180002a6b  mov     ecx, eax
0x180002a6d  xor     ebx, ebx
0x180002a6f  add     r13, 2
0x180002a73  mov     [rsp+150h+var_100], r13
0x180002a78  test    ebx, ebx
0x180002a7a  jnz     short loc_180002A86
0x180002a7c  cmp     ecx, 2Fh ; '/'
0x180002a7f  jnz     short loc_180002A86
0x180002a81  mov     ecx, 5Ch ; '\'
0x180002a86  mov     eax, ebx
0x180002a88  cmp     ebx, 3E5h
0x180002a8e  jz      short loc_180002A20
0x180002a90  test    ebx, ebx
0x180002a92  jnz     short loc_180002AD5
0x180002a94  test    di, di
0x180002a97  jnz     loc_180002DAB
0x180002a9d  cmp     ecx, 10FFFFh
0x180002aa3  ja      short loc_180002AB6
0x180002aa5  lea     eax, [rcx-0D800h]
0x180002aab  cmp     eax, 7FFh
0x180002ab0  ja      loc_180002EAA
0x180002ab6  mov     eax, 246h
0x180002abb  add     r9, 2
0x180002abf  inc     rsi
0x180002ac2  jmp     loc_180002A20
0x180002ac7  test    r10b, r10b
0x180002aca  jz      loc_180002CA4
0x180002ad0  mov     ebx, 246h
0x180002ad5  mov     r14, [rsp+150h+var_110]
0x180002ada  mov     r15, [rbp+50h+arg_8]
0x180002ade  mov     rcx, [rsp+150h+hMem+8]; hMem
0x180002ae3  mov     r13, [rsp+150h+var_30]
0x180002aeb  mov     r12, [rsp+150h+var_28]
0x180002af3  mov     rdi, [rsp+150h+var_20]
0x180002afb  mov     rsi, [rsp+150h+var_18]
0x180002b03  test    rcx, rcx
0x180002b06  jz      short loc_180002B0E
0x180002b08  call    cs:__imp_LocalFree
0x180002b0e  test    ebx, ebx
0x180002b10  jnz     short loc_180002B8E
0x180002b12  mov     r10, [rbp+50h+arg_10]
0x180002b16  mov     edx, [r10]
0x180002b19  test    edx, edx
0x180002b1b  jz      loc_18000313E
0x180002b21  cmp     edx, 7FFFFFFFh
0x180002b27  ja      loc_180003138
0x180002b2d  mov     eax, 7FFFFFFEh
0x180002b32  mov     rcx, r14
0x180002b35  xor     r9d, r9d
0x180002b38  test    rax, rax
0x180002b3b  jz      short loc_180002B5F
0x180002b3d  movzx   r8d, word ptr [rcx]
0x180002b41  test    r8w, r8w
0x180002b45  jz      short loc_180002B5F
0x180002b47  mov     [r15], r8w
0x180002b4b  add     rcx, 2
0x180002b4f  add     r15, 2
0x180002b53  dec     rax
0x180002b56  inc     r9
0x180002b59  sub     rdx, 1
0x180002b5d  jnz     short loc_180002B38
0x180002b5f  test    rdx, rdx
0x180002b62  lea     rcx, [r15-2]
0x180002b66  lea     r8, [r9-1]
0x180002b6a  cmovnz  rcx, r15
0x180002b6e  cmovnz  r8, r9
0x180002b72  xor     eax, eax
0x180002b74  mov     [rcx], ax
0x180002b77  test    rdx, rdx
0x180002b7a  jz      loc_18000313E
0x180002b80  lea     rax, [r8+r8]
0x180002b84  sar     rax, 1
0x180002b87  inc     eax
0x180002b89  xor     ebx, ebx
0x180002b8b  mov     [r10], eax
0x180002b8e  test    r14, r14
0x180002b91  jz      short loc_180002B9C
0x180002b93  mov     rcx, r14; hMem
0x180002b96  call    cs:__imp_LocalFree
0x180002b9c  mov     r14, [rsp+150h+var_38]
0x180002ba4  mov     eax, ebx
0x180002ba6  jmp     loc_1800027ED
0x180002bab  test    r14b, r14b
0x180002bae  jnz     loc_180002D5B
0x180002bb4  neg     r10b
0x180002bb7  sbb     ebx, ebx
0x180002bb9  and     ebx, 246h
0x180002bbf  test    ebx, ebx
0x180002bc1  cmovz   ebx, eax
0x180002bc4  test    ebx, ebx
0x180002bc6  jnz     loc_180002AD5
0x180002bcc  mov     rax, [rsp+150h+hMem+8]
0x180002bd1  lea     r8, [rbp+50h+arg_0]
0x180002bd5  xor     edi, edi
0x180002bd7  xor     edx, edx
0x180002bd9  mov     [rbp+50h+arg_0], rdi
0x180002bdd  lea     rcx, [rax+rsi*2]
0x180002be1  mov     [rbp+50h+var_D0], rcx
0x180002be5  lea     rcx, [rsp+150h+var_F0]
0x180002bea  call    DavCreateUncPath
0x180002bef  mov     ebx, eax
0x180002bf1  cmp     eax, 7Ah ; 'z'
0x180002bf4  jnz     short loc_180002C32
0x180002bf6  mov     eax, 2
0x180002bfb  mul     [rbp+50h+arg_0]
0x180002bff  test    rdx, rdx
0x180002c02  jnz     loc_180002E93
0x180002c08  mov     rdx, rax; uBytes
0x180002c0b  xor     ecx, ecx; uFlags
0x180002c0d  call    cs:__imp_LocalAlloc
0x180002c13  mov     rdi, rax
0x180002c16  test    rax, rax
0x180002c19  jz      loc_180003115
0x180002c1f  lea     r8, [rbp+50h+arg_0]
0x180002c23  mov     rdx, rax
0x180002c26  lea     rcx, [rsp+150h+var_F0]
0x180002c2b  call    DavCreateUncPath
0x180002c30  mov     ebx, eax
0x180002c32  test    ebx, ebx
0x180002c34  jnz     short loc_180002C7A
0x180002c36  mov     rax, [rbp+50h+arg_0]
0x180002c3a  cmp     word ptr [rdi+rax*2-4], 5Ch ; '\'
0x180002c40  lea     rcx, [rdi+rax*2]
0x180002c44  jz      loc_180003122
0x180002c4a  xor     r8d, r8d
0x180002c4d  lea     rdx, [rsp+150h+var_F8]
0x180002c52  mov     rcx, rdi; Src
0x180002c55  call    DavCanonicalizeUncPathAndDetermineType
0x180002c5a  test    eax, eax
0x180002c5c  jz      short loc_180002C67
0x180002c5e  mov     r14, [rsp+150h+var_F8]
0x180002c63  xor     ebx, ebx
0x180002c65  jmp     short loc_180002C7F
0x180002c67  mov     ebx, 43h ; 'C'
0x180002c6c  mov     rcx, [rsp+150h+var_F8]; hMem
0x180002c71  test    rcx, rcx
0x180002c74  jnz     loc_18000312D
0x180002c7a  mov     r14, [rsp+150h+var_110]
0x180002c7f  test    rdi, rdi
0x180002c82  jz      loc_180002ADA
0x180002c88  mov     rcx, rdi; hMem
0x180002c8b  call    cs:__imp_LocalFree
0x180002c91  jmp     loc_180002ADA
0x180002c96  test    rdx, rdx
0x180002c99  jnz     loc_180002808
0x180002c9f  jmp     loc_1800027E8
  ... truncated ...
```
