# CScmPatternTbl::InitTbl(void)

- ea: `0x180066678`
- end: `0x1800669a8`
- name: `?InitTbl@CScmPatternTbl@@QEAAJXZ`
- size: `816`
- prototype: `HRESULT __fastcall(CScmPatternTbl *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180066c7c`

## callees

- `0x18001248c`
- `0x18001b810`
- `0x180034bfc`
- `0x180036488`
- `0x180052390`
- `0x180052a10`
- `0x180053014`
- `0x180066678`
- `0x180066b10`
- `0x1800bf6c4`
- `0x1800c4651`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066901`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066901`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800666b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800668d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800666b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800668d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006695c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066975`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006695c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066975`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18006673b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18006682c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18006673b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18006682c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800667ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800667ed`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800667c3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800667c3`

## string_xrefs

- `0x180066761`: `Clsid\`

## pseudocode

```c
__int64 __fastcall CScmPatternTbl::InitTbl(CScmPatternTbl *this)
{
  unsigned __int8 *v2; // rax
  unsigned __int8 *v3; // rbx
  DWORD i; // r15d
  DWORD j; // r14d
  unsigned int v7; // edx
  unsigned __int64 v8; // rcx
  int v9; // r9d
  _DWORD *v10; // rdi
  unsigned int v11; // ecx
  unsigned int v12; // r8d
  unsigned int v13; // ecx
  unsigned int v14; // eax
  unsigned int v15; // r12d
  unsigned __int8 *v16; // rax
  unsigned __int8 *v17; // rsi
  SPatternEntry *v18; // rdi
  unsigned int ulCb; // eax
  unsigned int Size; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int cb; // [rsp+44h] [rbp-BCh] BYREF
  HKEY__ *hkClsid; // [rsp+48h] [rbp-B8h] BYREF
  HKEY__ *hkFileType; // [rsp+50h] [rbp-B0h] BYREF
  int cbTemp; // [rsp+58h] [rbp-A8h] BYREF
  _GUID clsid; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t szNum[16]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t szBuf[40]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t szClsid[80]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t szTemp[264]; // [rsp+180h] [rbp+80h] BYREF
  wchar_t szPattern[520]; // [rsp+390h] [rbp+290h] BYREF

  v2 = (unsigned __int8 *)HeapAlloc(g_hHeap, 0, 0x800u);
  this->_pLocTbl = v2;
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  *(_QWORD *)v2 = 2048;
  *((_DWORD *)v2 + 2) = 16;
  *((_DWORD *)v2 + 3) = 16;
  hkFileType = 0;
  if ( !(unsigned int)OpenClassesRootKeyExW(L"FileType", 0x2000000u, &hkFileType) )
  {
    for ( i = 0; ; ++i )
    {
      Size = 40;
      if ( RegEnumKeyExW(hkFileType, i, szBuf, &Size, 0, 0, 0, 0) )
        break;
      szBuf[39] = 0;
      memset_0(szTemp, 0, 0x208u);
      cbTemp = 520;
      StringCchCopyW(szClsid, 0x50u, L"Clsid\\");
      StringCchCatW(szClsid, 0x50u, szBuf);
      if ( !QueryClassesRootValueW(szClsid, szTemp, &cbTemp) )
      {
        hkClsid = 0;
        clsid = 0;
        if ( CLSIDFromString(szBuf, &clsid) >= 0 && !RegOpenKeyExW(hkFileType, szBuf, 0, 0x20019u, &hkClsid) )
        {
          for ( j = 0; ; ++j )
          {
            Size = 10;
            if ( RegEnumKeyExW(hkClsid, j, szNum, &Size, 0, 0, 0, 0) )
            {
              RegCloseKey(hkClsid);
              break;
            }
            cb = 1024;
            if ( !wRegQueryValue(hkClsid, szNum, szPattern, &cb) )
            {
              v7 = cb;
              v8 = cb & 0xFFFFFFFE;
              if ( v8 >= 0x402 )
                _report_rangecheckfailure();
              *(wchar_t *)((char *)szPattern + v8) = 0;
              v9 = 1;
              v10 = v3 + 12;
              if ( v7 + 1 < v7 || (v11 = (v7 + 1) >> 1, v12 = v11 + *v10, v12 < v11) || (v13 = v12 + 32, v12 + 32 < v12) )
                v13 = -1;
              else
                v9 = 0;
              if ( v13 <= *(_DWORD *)v3 )
              {
                if ( v9 )
                  continue;
                goto LABEL_25;
              }
              if ( !v9 )
              {
                v14 = *(_DWORD *)v3 + 2048;
                if ( v13 > v14 )
                  v14 = v13;
                v15 = v14;
                v16 = (unsigned __int8 *)HeapAlloc(g_hHeap, 0, v14);
                v17 = v16;
                if ( v16 )
                {
                  memcpy_0(v16, v3, (unsigned int)*v10);
                  HeapFree(g_hHeap, 0, v3);
                  this->_pLocTbl = v17;
                  v3 = v17;
                  *(_DWORD *)v17 = v15;
                  v7 = cb;
LABEL_25:
                  v18 = (SPatternEntry *)&this->_pLocTbl[*((unsigned int *)v3 + 3)];
                  if ( ParseEntry(szPattern, v7, v18, &clsid) )
                  {
                    ulCb = *((_DWORD *)v3 + 1);
                    if ( ulCb <= v18->ulCb )
                      ulCb = v18->ulCb;
                    *((_DWORD *)v3 + 1) = ulCb;
                    *((_DWORD *)v3 + 3) += v18->ulEntryLen;
                  }
                  continue;
                }
              }
            }
          }
        }
      }
    }
    RegCloseKey(hkFileType);
  }
  *(_DWORD *)v3 = *((_DWORD *)v3 + 3) + 16;
  return 0;
}

```

## disassembly

```asm
0x180066678  push    rbp
0x18006667a  push    rbx
0x18006667b  push    rsi
0x18006667c  push    rdi
0x18006667d  push    r12
0x18006667f  push    r13
0x180066681  push    r14
0x180066683  push    r15
0x180066685  lea     rbp, [rsp-6B8h]
0x18006668d  sub     rsp, 7B8h
0x180066694  mov     rax, cs:__security_cookie
0x18006669b  xor     rax, rsp
0x18006669e  mov     [rbp+6F0h+var_50], rax
0x1800666a5  mov     r13, this
0x1800666a8  mov     edi, 800h
0x1800666ad  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800666b4  mov     r8d, edi; dwBytes
0x1800666b7  xor     edx, edx; dwFlags
0x1800666b9  call    cs:__imp_HeapAlloc
0x1800666bf  xor     esi, esi
0x1800666c1  mov     [r13+0], rax
0x1800666c5  mov     rbx, rax
0x1800666c8  test    rax, rax
0x1800666cb  jnz     short loc_1800666D7
0x1800666cd  mov     eax, 8007000Eh
0x1800666d2  jmp     loc_180066985
0x1800666d7  mov     [rax], rdi
0x1800666da  lea     r8, [rsp+7F0h+hkFileType]; phkResult
0x1800666df  mov     dword ptr [rax+8], 10h
0x1800666e6  lea     this, aFiletype; "FileType"
0x1800666ed  mov     dword ptr [rax+0Ch], 10h
0x1800666f4  mov     edx, 2000000h; samDesired
0x1800666f9  mov     [rsp+7F0h+hkFileType], rsi
0x1800666fe  call    OpenClassesRootKeyExW
0x180066703  test    eax, eax
0x180066705  jnz     loc_18006697B
0x18006670b  mov     r15d, esi
0x18006670e  mov     this, [rsp+7F0h+hkFileType]; hKey
0x180066713  lea     r9, [rsp+7F0h+Size]; lpcchName
0x180066718  mov     [rsp+7F0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18006671d  lea     r8, [rbp+6F0h+szBuf]; lpName
0x180066721  mov     [rsp+7F0h+lpcchClass], rsi; lpcchClass
0x180066726  mov     edx, r15d; dwIndex
0x180066729  mov     [rsp+7F0h+lpClass], rsi; lpClass
0x18006672e  mov     [rsp+7F0h+lpReserved], rsi; lpReserved
0x180066733  mov     [rsp+7F0h+Size], 28h ; '('
0x18006673b  call    cs:__imp_RegEnumKeyExW
0x180066741  test    eax, eax
0x180066743  jnz     loc_180066970
0x180066749  xor     edx, edx; Val
0x18006674b  mov     [rbp+6F0h+szBuf+4Eh], si
0x18006674f  mov     r8d, 208h; Size
0x180066755  lea     this, [rbp+6F0h+szTemp]; void *
0x18006675c  call    memset_0
0x180066761  lea     r8, aClsid_2; "Clsid\\"
0x180066768  mov     [rsp+7F0h+cbTemp], 208h
0x180066770  mov     edx, 50h ; 'P'; cchDest
0x180066775  lea     this, [rbp+6F0h+szClsid]; pszDest
0x180066779  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006677e  lea     r8, [rbp+6F0h+szBuf]; pszSrc
0x180066782  mov     edx, 50h ; 'P'; cchDest
0x180066787  lea     this, [rbp+6F0h+szClsid]; pszDest
0x18006678b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180066790  lea     r8, [rsp+7F0h+cbTemp]; lpcbValue
0x180066795  lea     rdx, [rbp+6F0h+szTemp]; pszValue
0x18006679c  lea     this, [rbp+6F0h+szClsid]; pszSubKey
0x1800667a0  call    QueryClassesRootValueW
0x1800667a5  test    eax, eax
0x1800667a7  jnz     loc_180066962
0x1800667ad  xorps   xmm0, xmm0
0x1800667b0  mov     [rsp+7F0h+hkClsid], rsi
0x1800667b5  lea     rdx, [rsp+7F0h+clsid]; pclsid
0x1800667ba  lea     this, [rbp+6F0h+szBuf]; lpsz
0x1800667be  movups  xmmword ptr [rsp+7F0h+clsid.Data1], xmm0
0x1800667c3  call    cs:__imp_CLSIDFromString
0x1800667c9  test    eax, eax
0x1800667cb  js      loc_180066962
0x1800667d1  mov     this, [rsp+7F0h+hkFileType]; hKey
0x1800667d6  lea     rax, [rsp+7F0h+hkClsid]
0x1800667db  mov     r9d, 20019h; samDesired
0x1800667e1  mov     [rsp+7F0h+lpReserved], rax; phkResult
0x1800667e6  xor     r8d, r8d; ulOptions
0x1800667e9  lea     rdx, [rbp+6F0h+szBuf]; lpSubKey
0x1800667ed  call    cs:__imp_RegOpenKeyExW
0x1800667f3  test    eax, eax
0x1800667f5  jnz     loc_180066962
0x1800667fb  mov     r14d, esi
0x1800667fe  mov     this, [rsp+7F0h+hkClsid]; hKey
0x180066803  lea     r9, [rsp+7F0h+Size]; lpcchName
0x180066808  mov     [rsp+7F0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18006680d  lea     r8, [rsp+7F0h+szNum]; lpName
0x180066812  mov     [rsp+7F0h+lpcchClass], rsi; lpcchClass
0x180066817  mov     edx, r14d; dwIndex
0x18006681a  mov     [rsp+7F0h+lpClass], rsi; lpClass
0x18006681f  mov     [rsp+7F0h+lpReserved], rsi; lpReserved
0x180066824  mov     [rsp+7F0h+Size], 0Ah
0x18006682c  call    cs:__imp_RegEnumKeyExW
0x180066832  mov     this, [rsp+7F0h+hkClsid]; hKey
0x180066837  test    eax, eax
0x180066839  jnz     loc_18006695C
0x18006683f  lea     r9, [rsp+7F0h+cb]; lpdwSize
0x180066844  mov     [rsp+7F0h+cb], 400h
0x18006684c  lea     r8, [rbp+6F0h+szPattern]; lpValue
0x180066853  lea     rdx, [rsp+7F0h+szNum]; lpSubKey
0x180066858  call    wRegQueryValue
0x18006685d  test    eax, eax
0x18006685f  jnz     loc_180066954
0x180066865  mov     edx, [rsp+7F0h+cb]; cb
0x180066869  mov     ecx, edx
0x18006686b  and     this, 0FFFFFFFFFFFFFFFEh
0x18006686f  cmp     this, 402h
0x180066876  jnb     loc_18006696A
0x18006687c  mov     [rbp+this+6F0h+szPattern], si
0x180066884  lea     r9d, [rax+1]
0x180066888  lea     ecx, [rdx+1]
0x18006688b  lea     rdi, [rbx+0Ch]
0x18006688f  cmp     ecx, edx
0x180066891  jb      short loc_1800668AE
0x180066893  mov     r8d, [rdi]
0x180066896  shr     ecx, 1
0x180066898  add     r8d, ecx
0x18006689b  cmp     r8d, ecx
0x18006689e  jb      short loc_1800668AE
0x1800668a0  lea     ecx, [r8+20h]
0x1800668a4  cmp     ecx, r8d
0x1800668a7  jb      short loc_1800668AE
0x1800668a9  mov     r9d, esi
0x1800668ac  jmp     short loc_1800668B1
0x1800668ae  or      ecx, 0FFFFFFFFh
0x1800668b1  mov     eax, [rbx]
0x1800668b3  cmp     ecx, eax
0x1800668b5  jbe     short loc_180066919
0x1800668b7  test    r9d, r9d
0x1800668ba  jnz     loc_180066954
0x1800668c0  add     eax, 800h
0x1800668c5  cmp     ecx, eax
0x1800668c7  cmova   eax, ecx
0x1800668ca  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800668d1  mov     r8d, eax; dwBytes
0x1800668d4  xor     edx, edx; dwFlags
0x1800668d6  mov     r12d, eax
0x1800668d9  call    cs:__imp_HeapAlloc
0x1800668df  mov     rsi, rax
0x1800668e2  test    rax, rax
0x1800668e5  jz      short loc_180066952
0x1800668e7  mov     r8d, [rdi]; Size
0x1800668ea  mov     rdx, rbx; Src
0x1800668ed  mov     this, rax; void *
0x1800668f0  call    memcpy_0
0x1800668f5  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800668fc  mov     r8, rbx; lpMem
0x1800668ff  xor     edx, edx; dwFlags
0x180066901  call    cs:__imp_HeapFree
0x180066907  mov     [r13+0], rsi
0x18006690b  mov     rbx, rsi
0x18006690e  mov     [rsi], r12d
0x180066911  xor     esi, esi
0x180066913  mov     edx, [rsp+7F0h+cb]
0x180066917  jmp     short loc_18006691E
0x180066919  test    r9d, r9d
0x18006691c  jnz     short loc_180066954
0x18006691e  mov     edi, [rbx+0Ch]
0x180066921  lea     r9, [rsp+7F0h+clsid]; rclsid
0x180066926  add     rdi, [r13+0]
0x18006692a  lea     this, [rbp+6F0h+szPattern]; psz
0x180066931  mov     r8, rdi; pEntry
0x180066934  call    ParseEntry
0x180066939  test    eax, eax
0x18006693b  jz      short loc_180066954
0x18006693d  mov     eax, [rbx+4]
0x180066940  cmp     eax, [rdi+18h]
0x180066943  cmovbe  eax, [rdi+18h]
0x180066947  mov     [rbx+4], eax
0x18006694a  mov     eax, [rdi+10h]
0x18006694d  add     [rbx+0Ch], eax
0x180066950  jmp     short loc_180066954
0x180066952  xor     esi, esi
0x180066954  inc     r14d
0x180066957  jmp     loc_1800667FE
0x18006695c  call    cs:__imp_RegCloseKey
0x180066962  inc     r15d
0x180066965  jmp     loc_18006670E
0x18006696a  call    __report_rangecheckfailure
0x180066970  mov     this, [rsp+7F0h+hkFileType]; hKey
0x180066975  call    cs:__imp_RegCloseKey
0x18006697b  mov     eax, [rbx+0Ch]
0x18006697e  add     eax, 10h
0x180066981  mov     [rbx], eax
0x180066983  xor     eax, eax
0x180066985  mov     this, [rbp+6F0h+var_50]
0x18006698c  xor     this, rsp; StackCookie
0x18006698f  call    __security_check_cookie
0x180066994  add     rsp, 7B8h
0x18006699b  pop     r15
0x18006699d  pop     r14
0x18006699f  pop     r13
0x1800669a1  pop     r12
0x1800669a3  pop     rdi
0x1800669a4  pop     rsi
0x1800669a5  pop     rbx
0x1800669a6  pop     rbp
0x1800669a7  retn
```
