# V4ConnectionFiles::CreateV4ConnectionFileStruct(HKEY__ *,V4ConnectionFiles * *)

- ea: `0x180034518`
- end: `0x180034886`
- name: `?CreateV4ConnectionFileStruct@V4ConnectionFiles@@SAJPEAUHKEY__@@PEAPEAU1@@Z`
- size: `878`
- prototype: `__int64 __fastcall(HKEY hkey, struct V4ConnectionFiles **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800343d0`

## callees

- `0x180001ee0`
- `0x180002498`
- `0x1800028d8`
- `0x18000298c`
- `0x18001fe90`
- `0x180028418`
- `0x180034518`
- `0x180034cf8`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x18003474f`
- `ADVAPI32!RegEnumValueW` at `0x18003474f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18003468e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18003468e`

## pseudocode

```c
__int64 __fastcall V4ConnectionFiles::CreateV4ConnectionFileStruct(HKEY hkey, struct V4ConnectionFiles **a2)
{
  WCHAR *v2; // r14
  struct V4ConnectionFiles *v6; // rdx
  unsigned int i; // ecx
  __int64 v8; // rax
  __int64 v9; // r13
  signed int ConnectionSpecificDirectory; // ebx
  __int64 v11; // rdx
  wchar_t *v12; // rax
  BYTE *v13; // r15
  LSTATUS v14; // eax
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rax
  DWORD v18; // esi
  LSTATUS v19; // eax
  unsigned int v20; // edx
  WCHAR *v21; // rcx
  int v22; // eax
  int v23; // r8d
  __int64 v24; // rbx
  __int64 v25; // rdi
  unsigned __int64 v26; // r13
  unsigned __int64 v27; // rax
  wchar_t *v28; // rax
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cValues; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbData; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-90h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h]
  HKEY hKey; // [rsp+80h] [rbp-80h]
  wchar_t pszDest[264]; // [rsp+90h] [rbp-70h] BYREF

  v2 = 0;
  hKey = hkey;
  if ( !a2 )
    return 2147942487LL;
  v6 = (struct V4ConnectionFiles *)operator new(0x68u, (const struct std::nothrow_t *)byte_18006C430);
  if ( v6 )
  {
    for ( i = 0; i < 0xD; ++i )
    {
      v8 = (int)i;
      *(_QWORD *)((char *)v6 + *((_QWORD *)&V4ConnectionFiles::s_connectionFiles + 2 * v8 + 1)) = 0;
    }
    *a2 = v6;
    memset_0(pszDest, 0, 0x208u);
    v34 = 0;
    LODWORD(v9) = 0;
    ConnectionSpecificDirectory = GetConnectionSpecificDirectory(hkey, (BYTE *)pszDest, 0x104u);
    if ( ConnectionSpecificDirectory >= 0 )
    {
      ConnectionSpecificDirectory = StringCchCatW(pszDest, 0x104u, L"\\");
      if ( ConnectionSpecificDirectory >= 0 )
      {
        v11 = 260;
        v12 = pszDest;
        do
        {
          if ( !*v12 )
            break;
          ++v12;
          --v11;
        }
        while ( v11 );
        ConnectionSpecificDirectory = v11 == 0 ? 0x80070057 : 0;
        v9 = (260 - v11) & -(__int64)(v11 != 0);
        v34 = v9;
      }
    }
    cValues = 0;
    v13 = 0;
    cbMaxValueNameLen = 0;
    cbMaxValueLen = 0;
    if ( ConnectionSpecificDirectory >= 0 )
    {
      v14 = RegQueryInfoKeyW(hkey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
      if ( v14 )
      {
        if ( v14 > 0 )
          ConnectionSpecificDirectory = (unsigned __int16)v14 | 0x80070000;
        else
          ConnectionSpecificDirectory = v14;
      }
      else
      {
        v15 = 2LL * (cbMaxValueNameLen + 1);
        if ( !is_mul_ok(cbMaxValueNameLen + 1, 2u) )
          v15 = -1;
        v2 = (WCHAR *)operator new(v15, (const struct std::nothrow_t *)byte_18006C430);
        v16 = (unsigned __int64)cbMaxValueLen >> 1;
        v17 = 2 * v16;
        if ( !is_mul_ok(v16, 2u) )
          v17 = -1;
        v13 = (BYTE *)operator new(v17, (const struct std::nothrow_t *)byte_18006C430);
        if ( !v13 || !v2 )
          ConnectionSpecificDirectory = -2147024882;
      }
    }
    v18 = 0;
    if ( ConnectionSpecificDirectory >= 0 )
    {
LABEL_25:
      while ( v18 < cValues )
      {
        cchValueName = cbMaxValueNameLen + 1;
        cbData = cbMaxValueLen;
        v19 = RegEnumValueW(hKey, v18, v2, &cchValueName, 0, 0, v13, &cbData);
        if ( v19 )
        {
          if ( v19 > 0 )
            ConnectionSpecificDirectory = (unsigned __int16)v19 | 0x80070000;
          else
            ConnectionSpecificDirectory = v19;
        }
        else
        {
          *(_WORD *)&v13[2 * ((unsigned __int64)cbMaxValueLen >> 1) - 2] = 0;
          v2[cbMaxValueNameLen] = 0;
        }
        if ( ConnectionSpecificDirectory >= 0 )
        {
          v20 = 0;
          while ( 1 )
          {
            v21 = v2;
            do
            {
              v22 = *(WCHAR *)((char *)v21 + *((_QWORD *)&V4ConnectionFiles::s_connectionFiles + 2 * v20) - (_QWORD)v2);
              v23 = *v21 - v22;
              if ( v23 )
                break;
              ++v21;
            }
            while ( v22 );
            if ( !v23 )
              break;
            if ( ++v20 >= 0xD )
            {
              ++v18;
              goto LABEL_25;
            }
          }
          v24 = (__int64)*a2;
          v25 = *((_QWORD *)&V4ConnectionFiles::s_connectionFiles + 2 * v20 + 1);
          v26 = (cbData >> 1) + (unsigned int)v9;
          v27 = 2 * v26;
          if ( !is_mul_ok(v26, 2u) )
            v27 = -1;
          v28 = (wchar_t *)operator new(v27, (const struct std::nothrow_t *)byte_18006C430);
          *(_QWORD *)(v25 + v24) = v28;
          if ( !v28 )
          {
            ConnectionSpecificDirectory = -2147024882;
            break;
          }
          ConnectionSpecificDirectory = StringCchPrintfW(v28, (unsigned int)v26, L"%ws%ws", pszDest, v13);
        }
        ++v18;
        if ( ConnectionSpecificDirectory < 0 )
          break;
        LODWORD(v9) = v34;
      }
    }
    operator delete(v13);
    operator delete(v2);
    return (unsigned int)ConnectionSpecificDirectory;
  }
  else
  {
    *a2 = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180034518  mov     [rsp-8+arg_10], rbx
0x18003451d  push    rbp
0x18003451e  push    rsi
0x18003451f  push    rdi
0x180034520  push    r12
0x180034522  push    r13
0x180034524  push    r14
0x180034526  push    r15
0x180034528  lea     rbp, [rsp-1B0h]
0x180034530  sub     rsp, 2B0h
0x180034537  mov     rax, cs:__security_cookie
0x18003453e  xor     rax, rsp
0x180034541  mov     [rbp+1E0h+var_40], rax
0x180034548  xor     r14d, r14d
0x18003454b  mov     [rbp+1E0h+hKey], rcx
0x18003454f  mov     r12, rdx
0x180034552  mov     rsi, rcx
0x180034555  test    rdx, rdx
0x180034558  jnz     short loc_180034564
0x18003455a  mov     eax, 80070057h
0x18003455f  jmp     loc_18003485C
0x180034564  lea     rdx, byte_18006C430; struct std::nothrow_t *
0x18003456b  mov     ecx, 68h ; 'h'; unsigned __int64
0x180034570  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180034575  mov     rdx, rax
0x180034578  test    rax, rax
0x18003457b  jz      loc_180034853
0x180034581  mov     ecx, r14d
0x180034584  lea     r8, ?s_connectionFiles@V4ConnectionFiles@@0QBUConnectionFileToRetrieve@1@B; V4ConnectionFiles::ConnectionFileToRetrieve const near * const V4ConnectionFiles::s_connectionFiles
0x18003458b  movsxd  rax, ecx
0x18003458e  inc     ecx
0x180034590  add     rax, rax
0x180034593  mov     rax, [r8+rax*8+8]
0x180034598  mov     [rdx+rax], r14
0x18003459c  cmp     ecx, 0Dh
0x18003459f  jb      short loc_18003458B
0x1800345a1  mov     [r12], rdx
0x1800345a5  lea     rcx, [rbp+1E0h+pszDest]; void *
0x1800345a9  xor     edx, edx; Val
0x1800345ab  mov     r8d, 208h; Size
0x1800345b1  call    memset_0
0x1800345b6  mov     edi, 104h
0x1800345bb  mov     [rsp+2E0h+var_268], r14
0x1800345c0  mov     r8d, edi; cchDest
0x1800345c3  lea     rdx, [rbp+1E0h+pszDest]; pszDest
0x1800345c7  mov     rcx, rsi; hkey
0x1800345ca  mov     r13, r14
0x1800345cd  call    ?GetConnectionSpecificDirectory@@YAJPEAUHKEY__@@PEAGK@Z; GetConnectionSpecificDirectory(HKEY__ *,ushort *,ulong)
0x1800345d2  mov     ebx, eax
0x1800345d4  test    eax, eax
0x1800345d6  js      short loc_180034633
0x1800345d8  lea     r8, SubBlock; "\\"
0x1800345df  mov     edx, edi; cchDest
0x1800345e1  lea     rcx, [rbp+1E0h+pszDest]; pszDest
0x1800345e5  call    StringCchCatW
0x1800345ea  mov     ebx, eax
0x1800345ec  test    eax, eax
0x1800345ee  js      short loc_180034633
0x1800345f0  mov     edx, edi
0x1800345f2  lea     rax, [rbp+1E0h+pszDest]
0x1800345f6  cmp     [rax], r14w
0x1800345fa  jz      short loc_180034606
0x1800345fc  add     rax, 2
0x180034600  sub     rdx, 1
0x180034604  jnz     short loc_1800345F6
0x180034606  mov     rax, rdx
0x180034609  neg     rax
0x18003460c  mov     rax, rdx
0x18003460f  sbb     ebx, ebx
0x180034611  sub     rdi, rdx
0x180034614  not     ebx
0x180034616  and     ebx, 80070057h
0x18003461c  neg     rax
0x18003461f  sbb     rcx, rcx
0x180034622  and     rcx, rdi
0x180034625  neg     rdx
0x180034628  sbb     r13, r13
0x18003462b  and     r13, rcx
0x18003462e  mov     [rsp+2E0h+var_268], r13
0x180034633  xor     edi, edi
0x180034635  mov     [rsp+2E0h+cValues], edi
0x180034639  mov     r15d, edi
0x18003463c  mov     [rsp+2E0h+cbMaxValueNameLen], edi
0x180034640  mov     [rsp+2E0h+cbMaxValueLen], edi
0x180034644  test    ebx, ebx
0x180034646  js      loc_180034702
0x18003464c  mov     [rsp+2E0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180034651  lea     rax, [rsp+2E0h+cbMaxValueLen]
0x180034656  mov     [rsp+2E0h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x18003465b  xor     r9d, r9d; lpReserved
0x18003465e  mov     [rsp+2E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180034663  xor     r8d, r8d; lpcchClass
0x180034666  lea     rax, [rsp+2E0h+cbMaxValueNameLen]
0x18003466b  xor     edx, edx; lpClass
0x18003466d  mov     [rsp+2E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180034672  mov     rcx, rsi; hKey
0x180034675  lea     rax, [rsp+2E0h+cValues]
0x18003467a  mov     [rsp+2E0h+lpcValues], rax; lpcValues
0x18003467f  mov     [rsp+2E0h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180034684  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x180034689  mov     [rsp+2E0h+lpcSubKeys], rdi; lpcSubKeys
0x18003468e  call    cs:__imp_RegQueryInfoKeyW
0x180034694  test    eax, eax
0x180034696  jnz     short loc_1800346F3
0x180034698  mov     ecx, [rsp+2E0h+cbMaxValueNameLen]
0x18003469c  lea     esi, [rdi+2]
0x18003469f  inc     ecx
0x1800346a1  lea     r15, [rdi-1]
0x1800346a5  mov     eax, esi
0x1800346a7  mul     rcx
0x1800346aa  lea     rdx, byte_18006C430; struct std::nothrow_t *
0x1800346b1  cmovb   rax, r15
0x1800346b5  mov     rcx, rax; unsigned __int64
0x1800346b8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800346bd  mov     ecx, [rsp+2E0h+cbMaxValueLen]
0x1800346c1  mov     r14, rax
0x1800346c4  shr     rcx, 1
0x1800346c7  mov     eax, esi
0x1800346c9  mul     rcx
0x1800346cc  lea     rdx, byte_18006C430; struct std::nothrow_t *
0x1800346d3  cmovb   rax, r15
0x1800346d7  mov     rcx, rax; unsigned __int64
0x1800346da  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800346df  mov     r15, rax
0x1800346e2  test    rax, rax
0x1800346e5  jz      short loc_1800346EC
0x1800346e7  test    r14, r14
0x1800346ea  jnz     short loc_180034702
0x1800346ec  mov     ebx, 8007000Eh
0x1800346f1  jmp     short loc_180034702
0x1800346f3  jg      short loc_1800346F9
0x1800346f5  mov     ebx, eax
0x1800346f7  jmp     short loc_180034702
0x1800346f9  movzx   ebx, ax
0x1800346fc  or      ebx, 80070000h
0x180034702  mov     esi, edi
0x180034704  test    ebx, ebx
0x180034706  js      loc_18003483F
0x18003470c  cmp     esi, [rsp+2E0h+cValues]
0x180034710  jnb     loc_18003483F
0x180034716  mov     eax, [rsp+2E0h+cbMaxValueNameLen]
0x18003471a  lea     r9, [rsp+2E0h+cchValueName]; lpcchValueName
0x18003471f  mov     rcx, [rbp+1E0h+hKey]; hKey
0x180034723  inc     eax
0x180034725  mov     [rsp+2E0h+cchValueName], eax
0x180034729  mov     r8, r14; lpValueName
0x18003472c  mov     eax, [rsp+2E0h+cbMaxValueLen]
0x180034730  mov     edx, esi; dwIndex
0x180034732  mov     [rsp+2E0h+cbData], eax
0x180034736  lea     rax, [rsp+2E0h+cbData]
0x18003473b  mov     [rsp+2E0h+lpcValues], rax; lpcbData
0x180034740  mov     [rsp+2E0h+lpcbMaxClassLen], r15; lpData
0x180034745  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rdi; lpType
0x18003474a  mov     [rsp+2E0h+lpcSubKeys], rdi; lpReserved
0x18003474f  call    cs:__imp_RegEnumValueW
0x180034755  test    eax, eax
0x180034757  jz      short loc_18003476A
0x180034759  jg      short loc_18003475F
0x18003475b  mov     ebx, eax
0x18003475d  jmp     short loc_180034780
0x18003475f  movzx   ebx, ax
0x180034762  or      ebx, 80070000h
0x180034768  jmp     short loc_180034780
0x18003476a  mov     ecx, [rsp+2E0h+cbMaxValueLen]
0x18003476e  shr     rcx, 1
0x180034771  mov     [r15+rcx*2-2], di
0x180034777  mov     ecx, [rsp+2E0h+cbMaxValueNameLen]
0x18003477b  mov     [r14+rcx*2], di
0x180034780  test    ebx, ebx
0x180034782  js      loc_18003482A
0x180034788  mov     edx, edi
0x18003478a  lea     r10, ?s_connectionFiles@V4ConnectionFiles@@0QBUConnectionFileToRetrieve@1@B; V4ConnectionFiles::ConnectionFileToRetrieve const near * const V4ConnectionFiles::s_connectionFiles
0x180034791  mov     eax, edx
0x180034793  mov     rcx, r14
0x180034796  add     rax, rax
0x180034799  mov     r9, [r10+rax*8]
0x18003479d  sub     r9, r14
0x1800347a0  movzx   r8d, word ptr [rcx]
0x1800347a4  movzx   eax, word ptr [rcx+r9]
0x1800347a9  sub     r8d, eax
0x1800347ac  jnz     short loc_1800347B6
0x1800347ae  add     rcx, 2
0x1800347b2  test    eax, eax
0x1800347b4  jnz     short loc_1800347A0
0x1800347b6  test    r8d, r8d
0x1800347b9  jz      short loc_1800347C9
0x1800347bb  inc     edx
0x1800347bd  cmp     edx, 0Dh
0x1800347c0  jb      short loc_180034791
0x1800347c2  inc     esi
0x1800347c4  jmp     loc_18003470C
0x1800347c9  mov     rbx, [r12]
0x1800347cd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800347d4  mov     eax, edx
0x1800347d6  add     rax, rax
0x1800347d9  mov     rdi, [r10+rax*8+8]
0x1800347de  mov     eax, [rsp+2E0h+cbData]
0x1800347e2  shr     eax, 1
0x1800347e4  add     r13d, eax
0x1800347e7  mov     eax, 2
0x1800347ec  mul     r13
0x1800347ef  lea     rdx, byte_18006C430; struct std::nothrow_t *
0x1800347f6  cmovb   rax, rcx
0x1800347fa  mov     rcx, rax; unsigned __int64
0x1800347fd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180034802  mov     [rdi+rbx], rax
0x180034806  xor     edi, edi
0x180034808  test    rax, rax
0x18003480b  jz      short loc_18003483A
0x18003480d  lea     r9, [rbp+1E0h+pszDest]
0x180034811  mov     [rsp+2E0h+lpcSubKeys], r15
0x180034816  lea     r8, aWsWs; "%ws%ws"
0x18003481d  mov     edx, r13d; cchDest
0x180034820  mov     rcx, rax; pszDest
0x180034823  call    StringCchPrintfW
0x180034828  mov     ebx, eax
0x18003482a  inc     esi
0x18003482c  test    ebx, ebx
0x18003482e  js      short loc_18003483F
0x180034830  mov     r13, [rsp+2E0h+var_268]
0x180034835  jmp     loc_18003470C
0x18003483a  mov     ebx, 8007000Eh
0x18003483f  mov     rcx, r15; Block
0x180034842  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034847  mov     rcx, r14; Block
0x18003484a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003484f  mov     eax, ebx
0x180034851  jmp     short loc_18003485C
0x180034853  mov     [r12], r14
0x180034857  mov     eax, 8007000Eh
0x18003485c  mov     rcx, [rbp+1E0h+var_40]
0x180034863  xor     rcx, rsp; StackCookie
0x180034866  call    __security_check_cookie
0x18003486b  mov     rbx, [rsp+2E0h+arg_10]
0x180034873  add     rsp, 2B0h
0x18003487a  pop     r15
0x18003487c  pop     r14
0x18003487e  pop     r13
0x180034880  pop     r12
0x180034882  pop     rdi
0x180034883  pop     rsi
0x180034884  pop     rbp
0x180034885  retn
```
