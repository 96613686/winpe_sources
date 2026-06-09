# DavGetUNCFromHTTPPathInternal

- ea: `0x180001e80`
- end: `0x1800027ae`
- name: `DavGetUNCFromHTTPPathInternal`
- size: `2350`
- prototype: `__int64 __usercall@<rax>(wchar_t *String1@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180003830`

## callees

- `0x180001e80`
- `0x180003300`
- `0x180003570`
- `0x180003be0`
- `0x1800040b0`
- `0x180004850`

## import_xrefs

- `msvcrt!wcscspn` at `0x180001f1d`
- `msvcrt!wcscspn` at `0x180001f6e`
- `msvcrt!wcscspn` at `0x180001f9b`
- `msvcrt!wcscspn` at `0x180001fe0`
- `msvcrt!wcscspn` at `0x180002395`
- `msvcrt!wcscspn` at `0x1800025d1`
- `msvcrt!wcscspn` at `0x180002646`
- `msvcrt!wcscspn` at `0x180001f1d`
- `msvcrt!wcscspn` at `0x180001f6e`
- `msvcrt!wcscspn` at `0x180001f9b`
- `msvcrt!wcscspn` at `0x180001fe0`
- `msvcrt!wcscspn` at `0x180002395`
- `msvcrt!wcscspn` at `0x1800025d1`
- `msvcrt!wcscspn` at `0x180002646`
- `msvcrt!towupper` at `0x180002045`
- `msvcrt!towupper` at `0x180002045`
- `msvcrt!_wcsnicmp` at `0x18000201e`
- `msvcrt!_wcsnicmp` at `0x18000201e`
- `KERNEL32!LocalFree` at `0x1800021cf`
- `KERNEL32!LocalFree` at `0x1800022da`
- `KERNEL32!LocalFree` at `0x180002383`
- `KERNEL32!LocalFree` at `0x1800021cf`
- `KERNEL32!LocalFree` at `0x1800022da`
- `KERNEL32!LocalFree` at `0x180002383`
- `KERNEL32!GetLastError` at `0x1800024ea`
- `KERNEL32!GetLastError` at `0x180002784`
- `KERNEL32!GetLastError` at `0x1800024ea`
- `KERNEL32!GetLastError` at `0x180002784`
- `KERNEL32!LocalAlloc` at `0x18000208a`
- `KERNEL32!LocalAlloc` at `0x180002249`
- `KERNEL32!LocalAlloc` at `0x18000208a`
- `KERNEL32!LocalAlloc` at `0x180002249`

## pseudocode

```c
__int64 __fastcall DavGetUNCFromHTTPPathInternal(wchar_t *String1, _QWORD *a2, _BYTE *a3, _DWORD *a4, _DWORD *a5)
{
  wchar_t *v5; // r14
  size_t v6; // rax
  unsigned __int16 *v7; // r13
  const wchar_t *v8; // rbx
  unsigned __int16 *v9; // rdi
  bool v10; // zf
  size_t v11; // rax
  const wchar_t *v12; // r12
  char v13; // r15
  size_t v14; // rax
  unsigned __int16 *v15; // rsi
  unsigned __int64 v16; // rdi
  size_t v17; // r8
  unsigned __int64 v18; // rdi
  char v19; // dl
  int v20; // ecx
  __int64 v21; // rsi
  SIZE_T v22; // rsi
  _WORD *v23; // r9
  unsigned __int64 v24; // r15
  unsigned int v25; // r12d
  char v26; // r14
  char v27; // r10
  int v28; // eax
  SIZE_T v29; // r11
  __int64 v30; // rsi
  int v31; // eax
  unsigned int v32; // ecx
  DWORD LastError; // ebx
  _WORD *v35; // rdi
  _WORD *v36; // rax
  int v37; // ecx
  unsigned __int16 v38; // ax
  char v39; // dl
  unsigned __int16 v40; // r8
  char v41; // al
  unsigned __int8 v42; // dl
  size_t v43; // rax
  __int64 v44; // r8
  unsigned __int16 v45; // ax
  unsigned __int16 v46; // r8
  __int16 v47; // ax
  unsigned __int16 v48; // ax
  DWORD v49; // eax
  unsigned int v50; // r9d
  _WORD v51[2]; // [rsp+38h] [rbp-D0h] BYREF
  char v52[2]; // [rsp+3Ch] [rbp-CCh] BYREF
  unsigned __int16 v53; // [rsp+3Eh] [rbp-CAh]
  unsigned __int16 v54[2]; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v55; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int8 v56; // [rsp+4Ch] [rbp-BCh]
  char v57; // [rsp+4Dh] [rbp-BBh]
  unsigned __int64 v58; // [rsp+50h] [rbp-B8h] BYREF
  char32_t v59[2]; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t *hMem; // [rsp+60h] [rbp-A8h] BYREF
  HLOCAL hMem_8[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v62; // [rsp+78h] [rbp-90h]
  __int64 v63; // [rsp+88h] [rbp-80h]
  __int128 v64; // [rsp+98h] [rbp-70h]
  __int128 v65; // [rsp+C8h] [rbp-40h]
  __int128 v66; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int16 *v67; // [rsp+168h] [rbp+60h] BYREF
  _QWORD *v68; // [rsp+170h] [rbp+68h]
  _BYTE *v69; // [rsp+178h] [rbp+70h]
  _DWORD *v70; // [rsp+180h] [rbp+78h]

  v70 = a4;
  v69 = a3;
  v68 = a2;
  v5 = String1;
  v63 = 0;
  hMem = 0;
  *(_OWORD *)hMem_8 = 0;
  v62 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v6 = wcscspn(String1, L":/");
  if ( v5[v6] == 58 )
  {
    if ( !v6 )
      goto LABEL_83;
    *(_QWORD *)&v64 = v5;
    v7 = &v5[v6 + 1];
    *((_QWORD *)&v64 + 1) = &v5[v6];
  }
  else
  {
    v7 = v5;
    v5 = (wchar_t *)v64;
  }
  if ( *v7 != 47 || v7[1] != 47 )
  {
    v12 = (const wchar_t *)*((_QWORD *)&v65 + 1);
    v8 = (const wchar_t *)v65;
    goto LABEL_17;
  }
  v8 = v7 + 2;
  v9 = &v7[wcscspn(v7 + 2, L"@/") + 2];
  if ( *v9 == 64 )
  {
    wcscspn(v7 + 2, L":@");
    v8 = v9 + 1;
  }
  v10 = *v8 == 91;
  *(_QWORD *)&v65 = v8;
  if ( v10 )
  {
    v43 = wcscspn(v8, L"]/");
    v10 = v8[v43] == 93;
    v7 = (unsigned __int16 *)&v8[v43];
    v12 = &v8[v43];
    *((_QWORD *)&v65 + 1) = &v8[v43];
    if ( !v10 || (__int64)((v43 * 2) & 0xFFFFFFFFFFFFFFFEuLL) < 6 )
      goto LABEL_83;
  }
  else
  {
    v11 = wcscspn(v8, L":/");
    v7 = (unsigned __int16 *)&v8[v11];
    *((_QWORD *)&v65 + 1) = &v8[v11];
    v12 = &v8[v11];
    if ( (__int64)((v11 * 2) & 0xFFFFFFFFFFFFFFFEuLL) < 2 )
      goto LABEL_83;
  }
  if ( *v7 == 58 )
  {
    v67 = v7 + 1;
    if ( !(unsigned int)DavpParseUInt16(&v67, &v66) )
    {
      v7 = v67;
      if ( !*v67 || *v67 == 47 )
      {
        v12 = (const wchar_t *)*((_QWORD *)&v65 + 1);
        v13 = 1;
        v8 = (const wchar_t *)v65;
        v5 = (wchar_t *)v64;
        goto LABEL_18;
      }
    }
LABEL_83:
    LastError = 53;
    goto LABEL_49;
  }
LABEL_17:
  v13 = BYTE2(v66);
LABEL_18:
  v14 = wcscspn(v7, L"?#");
  v15 = &v7[v14];
  if ( *v15 == 63 )
    wcscspn(&v7[v14], L"#");
  v16 = (__int64)(*((_QWORD *)&v64 + 1) - (_QWORD)v5) >> 1;
  v17 = v16;
  if ( v16 > 4 )
    v17 = 4;
  if ( _wcsnicmp(v5, L"http", v17) )
    goto LABEL_102;
  v18 = v16 - 4;
  if ( !v18 )
  {
    v20 = (int)hMem_8[0];
    v19 = 0;
    goto LABEL_27;
  }
  if ( v18 != 1 || towupper(v5[4]) != 83 )
  {
LABEL_102:
    LastError = 87;
    goto LABEL_49;
  }
  v19 = 1;
  v20 = LODWORD(hMem_8[0]) | 1;
  LODWORD(hMem_8[0]) |= 1u;
LABEL_27:
  *(_QWORD *)&v62 = v12;
  hMem_8[1] = (HLOCAL)v8;
  LOBYTE(v67) = v19;
  if ( v13 )
  {
    v47 = 443;
    if ( !v19 )
      v47 = 80;
    if ( (_WORD)v66 != v47 )
    {
      WORD2(hMem_8[0]) = v66;
      LODWORD(hMem_8[0]) = v20 | 2;
    }
  }
  v21 = v15 - v7;
  v10 = v21 == 0;
  v22 = 2 * v21;
  if ( !v10 )
  {
    *((_QWORD *)&v62 + 1) = LocalAlloc(0, v22);
    if ( !*((_QWORD *)&v62 + 1) )
    {
      LastError = GetLastError();
      goto LABEL_49;
    }
  }
  v23 = (_WORD *)*((_QWORD *)&v62 + 1);
  v24 = (unsigned __int64)&v7[v22 / 2];
  v25 = v55;
  v26 = 0;
  v27 = 0;
  v58 = (unsigned __int64)v7;
  v28 = 0;
  v57 = 0;
  v29 = *((_QWORD *)&v62 + 1) + v22;
  v52[0] = 0;
  v30 = 0;
  v51[0] = 0;
  while ( (unsigned __int64)v7 < v24 )
  {
    if ( (unsigned __int64)v23 >= v29 )
    {
      while ( (unsigned __int64)v7 < v24 )
      {
        v59[0] = 0;
        v49 = DavpUrlDecodeToNtPathDecodeHelper((unsigned __int16 **)&v58, v24, (__int64)&v55, (__int64)v52, v59);
        if ( v49 == 997 )
          goto LABEL_132;
        if ( v49 )
          goto LABEL_135;
        v49 = Utf16Encoder::ProcessCodePoint((Utf16Encoder *)v51, v59[0], v54);
        ++v30;
        if ( !v49 )
        {
LABEL_132:
          v7 = (unsigned __int16 *)v58;
        }
        else
        {
          if ( v49 != 234 )
            goto LABEL_135;
          v49 = Utf16Encoder::ProcessCodePoint((Utf16Encoder *)v51, v50, v54);
          if ( v49 )
            goto LABEL_135;
          v7 = (unsigned __int16 *)v58;
          ++v30;
        }
      }
      v26 = v57;
      v28 = 122;
      v27 = v52[0];
      break;
    }
    v31 = *v7;
    v32 = 0;
    if ( v31 != 37 )
    {
      if ( v26 )
        goto LABEL_48;
      if ( v27 )
      {
        v27 = 0;
        v48 = v31 + 9216;
        v52[0] = 0;
        if ( v48 <= 0x3FFu )
        {
          v32 = v48 + (v53 << 10) + 0x10000;
          LastError = 0;
          goto LABEL_38;
        }
      }
      else
      {
        if ( (unsigned __int16)(v31 + 10240) >= 0x800u )
        {
          v32 = *v7;
          LastError = 0;
LABEL_38:
          ++v7;
          goto LABEL_39;
        }
        if ( (unsigned __int16)(v31 + 10240) <= 0x3FFu )
        {
          v27 = 1;
          v53 = v31 + 10240;
          v52[0] = 1;
          LastError = 997;
          goto LABEL_38;
        }
      }
      LastError = 582;
      goto LABEL_38;
    }
    if ( v27 || (__int64)((v24 - (_QWORD)v7) & 0xFFFFFFFFFFFFFFFEuLL) < 6 )
    {
LABEL_48:
      LastError = 582;
      goto LABEL_49;
    }
    v38 = v7[1];
    v39 = v38 - 48;
    if ( (unsigned __int16)(v38 - 48) >= 0xAu )
    {
      v45 = (v38 | 0x20) - 97;
      if ( v45 >= 6u )
        goto LABEL_48;
      v39 = v45 + 10;
    }
    v40 = v7[2];
    v41 = v40 - 48;
    if ( (unsigned __int16)(v40 - 48) >= 0xAu )
    {
      v46 = (v40 | 0x20) - 97;
      if ( v46 >= 6u )
        goto LABEL_48;
      v41 = v46 + 10;
    }
    v42 = v41 | (16 * v39);
    if ( v26 )
    {
      if ( (v42 & 0xC0) == 0x80 )
      {
        v25 = (v25 << 6) | v42 & 0x3F;
        v10 = v26-- == 1;
        v55 = v25;
        v57 = v26;
        if ( !v10 )
        {
          LastError = 997;
LABEL_79:
          v7 += 3;
          goto LABEL_39;
        }
        if ( v25 >= dword_1800076F0[v56] && (v25 <= 0xD7FF || v25 - 57344 <= 0x101FFF) )
        {
          LastError = 0;
          v32 = v25;
          goto LABEL_79;
        }
      }
LABEL_87:
      LastError = 582;
      v7 += 3;
      goto LABEL_39;
    }
    if ( v42 < 0x80u )
    {
      v32 = (char)v42;
      LastError = 0;
      goto LABEL_79;
    }
    v44 = *((unsigned __int8 *)qword_1800074E8 + ((unsigned __int64)v42 >> 3));
    if ( !(_BYTE)v44 )
      goto LABEL_87;
    v26 = v44 - 1;
    v25 = v42 & ~(unsigned __int8)byte_1800076E1[2 * v44];
    v56 = *((_BYTE *)qword_1800074E8 + ((unsigned __int64)v42 >> 3));
    v55 = v25;
    v7 += 3;
    v57 = v44 - 1;
    LastError = 997;
LABEL_39:
    v58 = (unsigned __int64)v7;
    if ( !LastError && v32 == 47 )
      v32 = 92;
    v28 = LastError;
    if ( LastError != 997 )
    {
      if ( LastError )
        goto LABEL_49;
      if ( v32 <= 0x10FFFF && v32 - 55296 > 0x7FF )
      {
        if ( v32 > 0xFFFF )
        {
          *v23++ = ((v32 - 0x10000) >> 10) | 0xD800;
          if ( (unsigned __int64)v23 < v29 )
          {
            v28 = 0;
            *v23 = v32 & 0x3FF | 0xDC00;
            v51[0] = 0;
            ++v23;
          }
          else
          {
            v51[0] = 0;
            v28 = 122;
          }
          v30 += 2;
        }
        else
        {
          *v23 = v32;
          v28 = 0;
          ++v23;
          ++v30;
        }
      }
      else
      {
        v28 = 582;
        ++v23;
        ++v30;
      }
    }
  }
  if ( v26 )
    LastError = 582;
  else
    LastError = v27 != 0 ? 0x246 : 0;
  if ( !LastError )
    LastError = v28;
  if ( !LastError )
  {
    v35 = 0;
    v58 = 0;
    v63 = *((_QWORD *)&v62 + 1) + 2 * v30;
    LastError = DavCreateUncPath(hMem_8, 0, &v58);
    if ( LastError != 122 )
      goto LABEL_61;
    if ( is_mul_ok(v58, 2u) )
    {
      v36 = LocalAlloc(0, 2 * v58);
      v35 = v36;
      if ( v36 )
      {
        LastError = DavCreateUncPath(hMem_8, v36, &v58);
LABEL_61:
        if ( !LastError )
        {
          if ( v35[v58 - 2] == 92 )
            v35[v58 - 2] = 0;
          v37 = DavCanonicalizeUncPathAndDetermineType(v35, &hMem, a5);
          if ( v37 )
          {
            *v68 = hMem;
            if ( v69 )
              *v69 = (_BYTE)v67;
            if ( v70 )
              *v70 = v37;
            LastError = 0;
          }
          else
          {
            LastError = 67;
            if ( hMem )
              LocalFree(hMem);
          }
        }
        if ( v35 )
          LocalFree(v35);
      }
      else
      {
        v49 = GetLastError();
LABEL_135:
        LastError = v49;
      }
    }
    else
    {
      LastError = 534;
    }
  }
LABEL_49:
  if ( *((_QWORD *)&v62 + 1) )
    LocalFree(*((HLOCAL *)&v62 + 1));
  return LastError;
}

```

## disassembly

```asm
0x180001e80  mov     rax, rsp
0x180001e83  mov     [rax+20h], r9
0x180001e87  mov     [rax+18h], r8
0x180001e8b  mov     [rax+10h], rdx
0x180001e8f  push    rbp
0x180001e90  lea     rbp, [rax-58h]
0x180001e94  sub     rsp, 150h
0x180001e9b  mov     [rax-38h], r14
0x180001e9f  xorps   xmm0, xmm0
0x180001ea2  mov     r14, rcx
0x180001ea5  mov     rax, r9
0x180001ea8  xor     ecx, ecx
0x180001eaa  mov     [rbp+50h+var_D0], rcx
0x180001eae  mov     [rsp+150h+hMem], rcx
0x180001eb3  movups  xmmword ptr [rsp+150h+hMem+8], xmm0
0x180001eb8  movups  xmmword ptr [rsp+150h+var_E8+8], xmm0
0x180001ebd  test    r8, r8
0x180001ec0  jnz     loc_1800025A4
0x180001ec6  test    rax, rax
0x180001ec9  jnz     loc_1800025AC
0x180001ecf  mov     rax, [rbp+50h+arg_20]
0x180001ed6  test    rax, rax
0x180001ed9  jnz     loc_1800025B4
0x180001edf  mov     [rsp+148h], rbx
0x180001ee7  lea     rdx, asc_1800073A0; ":/"
0x180001eee  mov     [rsp+150h+var_18], rdi
0x180001ef6  mov     rcx, r14; String
0x180001ef9  mov     [rsp+150h+var_20], r12
0x180001f01  mov     [rsp+150h+var_28], r13
0x180001f09  mov     [rsp+150h+var_38], r15
0x180001f11  movups  [rbp+50h+var_C0], xmm0
0x180001f15  movups  [rbp+50h+var_90], xmm0
0x180001f19  movups  [rbp+50h+var_80], xmm0
0x180001f1d  call    cs:__imp_wcscspn
0x180001f23  cmp     word ptr [r14+rax*2], 3Ah ; ':'
0x180001f29  lea     rcx, [r14+rax*2]
0x180001f2d  jnz     loc_1800025BB
0x180001f33  test    rax, rax
0x180001f36  jz      loc_1800023B4
0x180001f3c  mov     qword ptr [rbp+50h+var_C0], r14
0x180001f40  lea     r13, [rcx+2]
0x180001f44  mov     qword ptr [rbp+50h+var_C0+8], rcx
0x180001f48  cmp     word ptr [r13+0], 2Fh ; '/'
0x180001f4e  jnz     loc_180002401
0x180001f54  cmp     word ptr [r13+2], 2Fh ; '/'
0x180001f5a  jnz     loc_180002401
0x180001f60  lea     rbx, [r13+4]
0x180001f64  mov     rcx, rbx; String
0x180001f67  lea     rdx, asc_1800073BC; "@/"
0x180001f6e  call    cs:__imp_wcscspn
0x180001f74  cmp     word ptr [rbx+rax*2], 40h ; '@'
0x180001f79  lea     rdi, [rbx+rax*2]
0x180001f7d  jz      loc_1800025C7
0x180001f83  cmp     word ptr [rbx], 5Bh ; '['
0x180001f87  mov     rcx, rbx; String
0x180001f8a  mov     qword ptr [rbp+50h+var_90], rbx
0x180001f8e  jz      loc_18000238E
0x180001f94  lea     rdx, asc_1800073A0; ":/"
0x180001f9b  call    cs:__imp_wcscspn
0x180001fa1  add     rax, rax
0x180001fa4  lea     r13, [rax+rbx]
0x180001fa8  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001fac  mov     qword ptr [rbp+50h+var_90+8], r13
0x180001fb0  mov     r12, r13
0x180001fb3  cmp     rax, 2
0x180001fb7  jl      loc_1800023B4
0x180001fbd  cmp     word ptr [r13+0], 3Ah ; ':'
0x180001fc3  jz      loc_1800025F3
0x180001fc9  movzx   r15d, byte ptr [rbp+50h+var_80+2]
0x180001fce  lea     rdx, asc_1800074E0; "?#"
0x180001fd5  mov     [rsp+150h+var_10], rsi
0x180001fdd  mov     rcx, r13; String
0x180001fe0  call    cs:__imp_wcscspn
0x180001fe6  lea     rsi, ds:0[rax*2]
0x180001fee  add     rsi, r13
0x180001ff1  cmp     word ptr [rsi], 3Fh ; '?'
0x180001ff5  jz      loc_18000263C
0x180001ffb  mov     rdi, qword ptr [rbp+50h+var_C0+8]
0x180001fff  lea     rdx, aHttp; "http"
0x180002006  mov     eax, 4
0x18000200b  sub     rdi, r14
0x18000200e  sar     rdi, 1
0x180002011  mov     rcx, r14; String1
0x180002014  cmp     rdi, rax
0x180002017  mov     r8, rdi
0x18000201a  cmova   r8, rax; MaxCount
0x18000201e  call    cs:__imp__wcsnicmp
0x180002024  test    eax, eax
0x180002026  jnz     loc_180002501
0x18000202c  sub     rdi, 4
0x180002030  jz      loc_180002651
0x180002036  cmp     rdi, 1
0x18000203a  jnz     loc_180002501
0x180002040  movzx   ecx, word ptr [r14+8]; C
0x180002045  call    cs:__imp_towupper
0x18000204b  cmp     ax, 53h ; 'S'
0x18000204f  jnz     loc_180002501
0x180002055  mov     ecx, dword ptr [rsp+150h+hMem+8]
0x180002059  movzx   edx, dil
0x18000205d  or      ecx, edi
0x18000205f  mov     dword ptr [rsp+150h+hMem+8], ecx
0x180002063  mov     qword ptr [rsp+150h+var_E8+8], r12
0x180002068  mov     qword ptr [rsp+150h+var_E8], rbx
0x18000206d  mov     byte ptr [rbp+50h+arg_0], dl
0x180002070  test    r15b, r15b
0x180002073  jnz     loc_18000265C
0x180002079  sub     rsi, r13
0x18000207c  sar     rsi, 1
0x18000207f  lea     rsi, [rsi+rsi]
0x180002083  jz      short loc_18000209E
0x180002085  mov     rdx, rsi; uBytes
0x180002088  xor     ecx, ecx; uFlags
0x18000208a  call    cs:__imp_LocalAlloc
0x180002090  mov     qword ptr [rsp+150h+var_E8+10h], rax
0x180002095  test    rax, rax
0x180002098  jz      loc_1800024EA
0x18000209e  mov     r9, qword ptr [rsp+150h+var_E8+10h]
0x1800020a3  lea     r15, [rsi+r13]
0x1800020a7  mov     r12d, dword ptr [rsp+150h+var_110]
0x1800020ac  xor     r14b, r14b
0x1800020af  xor     r10b, r10b
0x1800020b2  mov     [rsp+150h+var_108], r13
0x1800020b7  xor     eax, eax
0x1800020b9  mov     byte ptr [rsp+150h+var_110+5], r14b
0x1800020be  lea     r11, [r9+rsi]
0x1800020c2  mov     [rsp+150h+var_11C], r10b
0x1800020c7  xor     esi, esi
0x1800020c9  mov     r8d, 2800h
0x1800020cf  xor     edi, edi
0x1800020d1  mov     [rsp+150h+var_120], di
0x1800020d6  nop     word ptr [rax+rax+00000000h]
0x1800020e0  mov     edx, 3FFh
0x1800020e5  cmp     r13, r15
0x1800020e8  jnb     loc_1800021E8
0x1800020ee  cmp     r9, r11
0x1800020f1  jnb     loc_1800026E0
0x1800020f7  movzx   eax, word ptr [r13+0]
0x1800020fc  xor     ecx, ecx
0x1800020fe  cmp     eax, 25h ; '%'
0x180002101  jz      loc_180002187
0x180002107  test    r14b, r14b
0x18000210a  jnz     loc_180002190
0x180002110  test    r10b, r10b
0x180002113  jnz     loc_1800026AD
0x180002119  lea     edx, [r8+rax]
0x18000211d  mov     ebx, 800h
0x180002122  cmp     dx, bx
0x180002125  jb      loc_1800024D2
0x18000212b  mov     ecx, eax
0x18000212d  xor     ebx, ebx
0x18000212f  add     r13, 2
0x180002133  mov     [rsp+150h+var_108], r13
0x180002138  test    ebx, ebx
0x18000213a  jnz     short loc_180002146
0x18000213c  cmp     ecx, 2Fh ; '/'
0x18000213f  jnz     short loc_180002146
0x180002141  mov     ecx, 5Ch ; '\'
0x180002146  mov     eax, ebx
0x180002148  cmp     ebx, 3E5h
0x18000214e  jz      short loc_1800020E0
0x180002150  test    ebx, ebx
0x180002152  jnz     short loc_180002195
0x180002154  test    di, di
0x180002157  jnz     loc_18000240E
0x18000215d  cmp     ecx, 10FFFFh
0x180002163  ja      short loc_180002176
0x180002165  lea     eax, [rcx-0D800h]
0x18000216b  cmp     eax, 7FFh
0x180002170  ja      loc_18000250B
0x180002176  mov     eax, 246h
0x18000217b  add     r9, 2
0x18000217f  inc     rsi
0x180002182  jmp     loc_1800020E0
0x180002187  test    r10b, r10b
0x18000218a  jz      loc_1800022E5
0x180002190  mov     ebx, 246h
0x180002195  mov     rsi, [rsp+150h+var_10]
0x18000219d  mov     rcx, qword ptr [rsp+150h+var_E8+10h]; hMem
0x1800021a2  mov     r15, [rsp+150h+var_38]
0x1800021aa  mov     r14, [rsp+150h+var_30]
0x1800021b2  mov     r13, [rsp+150h+var_28]
0x1800021ba  mov     r12, [rsp+150h+var_20]
0x1800021c2  mov     rdi, [rsp+150h+var_18]
0x1800021ca  test    rcx, rcx
0x1800021cd  jz      short loc_1800021D5
0x1800021cf  call    cs:__imp_LocalFree
0x1800021d5  mov     eax, ebx
0x1800021d7  mov     rbx, [rsp+148h]
0x1800021df  add     rsp, 150h
0x1800021e6  pop     rbp
0x1800021e7  retn
0x1800021e8  test    r14b, r14b
0x1800021eb  jnz     loc_1800023BE
0x1800021f1  neg     r10b
0x1800021f4  sbb     ebx, ebx
0x1800021f6  and     ebx, 246h
0x1800021fc  test    ebx, ebx
0x1800021fe  cmovz   ebx, eax
0x180002201  test    ebx, ebx
0x180002203  jnz     short loc_180002195
0x180002205  mov     rax, qword ptr [rsp+150h+var_E8+10h]
0x18000220a  lea     r8, [rsp+150h+var_108]
0x18000220f  xor     edi, edi
0x180002211  xor     edx, edx
0x180002213  mov     [rsp+150h+var_108], rdi
0x180002218  lea     rcx, [rax+rsi*2]
0x18000221c  mov     [rbp+50h+var_D0], rcx
0x180002220  lea     rcx, [rsp+150h+hMem+8]
0x180002225  call    DavCreateUncPath
0x18000222a  mov     ebx, eax
0x18000222c  cmp     eax, 7Ah ; 'z'
0x18000222f  jnz     short loc_18000226F
0x180002231  mov     eax, 2
0x180002236  mul     [rsp+150h+var_108]
0x18000223b  test    rdx, rdx
0x18000223e  jnz     loc_1800024F7
0x180002244  mov     rdx, rax; uBytes
0x180002247  xor     ecx, ecx; uFlags
0x180002249  call    cs:__imp_LocalAlloc
0x18000224f  mov     rdi, rax
0x180002252  test    rax, rax
0x180002255  jz      loc_180002784
0x18000225b  lea     r8, [rsp+150h+var_108]
0x180002260  mov     rdx, rax
0x180002263  lea     rcx, [rsp+150h+hMem+8]
0x180002268  call    DavCreateUncPath
0x18000226d  mov     ebx, eax
0x18000226f  test    ebx, ebx
0x180002271  jnz     short loc_1800022CE
0x180002273  mov     rax, [rsp+150h+var_108]
0x180002278  cmp     word ptr [rdi+rax*2-4], 5Ch ; '\'
0x18000227e  lea     rcx, [rdi+rax*2]
0x180002282  jz      loc_180002791
0x180002288  mov     r8, [rbp+50h+arg_20]
0x18000228f  lea     rdx, [rsp+150h+hMem]
0x180002294  mov     rcx, rdi; Src
0x180002297  call    DavCanonicalizeUncPathAndDetermineType
0x18000229c  mov     ecx, eax
0x18000229e  test    eax, eax
0x1800022a0  jz      loc_180002370
0x1800022a6  mov     rax, [rsp+150h+hMem]
0x1800022ab  mov     rdx, [rbp+50h+arg_8]
0x1800022af  mov     [rdx], rax
0x1800022b2  mov     rax, [rbp+50h+arg_10]
0x1800022b6  test    rax, rax
0x1800022b9  jnz     loc_18000279C
0x1800022bf  mov     rax, [rbp+50h+arg_18]
0x1800022c3  test    rax, rax
0x1800022c6  jnz     loc_1800027A7
0x1800022cc  xor     ebx, ebx
0x1800022ce  test    rdi, rdi
0x1800022d1  jz      loc_180002195
0x1800022d7  mov     rcx, rdi; hMem
0x1800022da  call    cs:__imp_LocalFree
0x1800022e0  jmp     loc_180002195
0x1800022e5  mov     rax, r15
0x1800022e8  sub     rax, r13
0x1800022eb  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800022ef  cmp     rax, 6
0x1800022f3  jl      loc_180002190
0x1800022f9  movzx   eax, word ptr [r13+2]
0x1800022fe  lea     edx, [rax-30h]
0x180002301  cmp     dx, 0Ah
0x180002305  jnb     loc_180002421
0x18000230b  movzx   r8d, word ptr [r13+4]
0x180002310  lea     eax, [r8-30h]
0x180002314  cmp     ax, 0Ah
0x180002318  jnb     loc_18000243B
0x18000231e  shl     dl, 4
0x180002321  or      dl, al
0x180002323  test    r14b, r14b
0x180002326  jz      loc_1800023C8
0x18000232c  movzx   eax, dl
0x18000232f  and     al, 0C0h
0x180002331  cmp     al, 80h
0x180002333  jnz     loc_1800023ED
0x180002339  mov     eax, r12d
0x18000233c  and     edx, 3Fh
0x18000233f  shl     eax, 6
0x180002342  mov     r12d, edx
0x180002345  or      r12d, eax
0x180002348  add     r14b, 0FFh
0x18000234c  mov     dword ptr [rsp+150h+var_110], r12d
0x180002351  mov     byte ptr [rsp+150h+var_110+5], r14b
0x180002356  jz      loc_180002492
0x18000235c  mov     ebx, 3E5h
0x180002361  add     r13, 6
0x180002365  mov     r8d, 2800h
0x18000236b  jmp     loc_180002133
0x180002370  mov     ebx, 43h ; 'C'
0x180002375  mov     rcx, [rsp+150h+hMem]; hMem
0x18000237a  test    rcx, rcx
0x18000237d  jz      loc_1800022CE
0x180002383  call    cs:__imp_LocalFree
0x180002389  jmp     loc_1800022CE
0x18000238e  lea     rdx, asc_180007414; "]/"
0x180002395  call    cs:__imp_wcscspn
0x18000239b  add     rax, rax
0x18000239e  cmp     word ptr [rax+rbx], 5Dh ; ']'
0x1800023a3  lea     r13, [rax+rbx]
  ... truncated ...
```
