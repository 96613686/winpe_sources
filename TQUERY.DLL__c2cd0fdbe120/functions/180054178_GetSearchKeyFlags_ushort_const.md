# GetSearchKeyFlags(ushort const *)

- ea: `0x180054178`
- end: `0x18005439b`
- name: `?GetSearchKeyFlags@@YA?AW4SEARCHKEY_FLAGS@@PEBG@Z`
- size: `547`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180052b10`
- `0x180053ac4`

## callees

- `0x180054178`
- `0x180056dc8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800541d3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180054210`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005424d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005428c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800542c5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800541d3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180054210`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005424d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005428c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800542c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005435d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005435d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800542d8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180054371`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800542d8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180054371`

## pseudocode

```c
__int64 __fastcall GetSearchKeyFlags(const WCHAR *a1)
{
  __int64 v1; // rdi
  __int64 v3; // rcx
  int cchCount2; // eax
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // eax
  int v14; // eax
  __int16 SystemPreferredLocale; // ax
  unsigned int i; // edx
  int pvData; // [rsp+78h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp+18h] BYREF

  v1 = -1;
  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  cchCount2 = 2;
  if ( (unsigned int)v3 < 2 )
    cchCount2 = v3;
  if ( CompareStringW(0x7Fu, 1u, String1, 2, a1, cchCount2) == 2 )
    goto LABEL_34;
  v5 = -1;
  do
    ++v5;
  while ( a1[v5] );
  v6 = 2;
  if ( (unsigned int)v5 < 2 )
    v6 = v5;
  if ( CompareStringW(0x7Fu, 1u, aOc, 2, a1, v6) == 2 )
    goto LABEL_34;
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  v8 = 2;
  if ( (unsigned int)v7 < 2 )
    v8 = v7;
  v9 = 0;
  if ( CompareStringW(0x7Fu, 1u, aWo_0, 2, a1, v8) == 2 )
LABEL_34:
    v9 = 1;
  v10 = -1;
  do
    ++v10;
  while ( a1[v10] );
  v11 = 2;
  if ( (unsigned int)v10 < 2 )
    v11 = v10;
  if ( CompareStringW(0x7Fu, 1u, aZh_0, 2, a1, v11) == 2 )
    goto LABEL_30;
  do
    ++v1;
  while ( a1[v1] );
  v12 = 12;
  if ( (unsigned int)v1 < 0xC )
    v12 = v1;
  if ( CompareStringW(0x7Fu, 1u, aJaJpRadstr, 12, a1, v12) == 2 )
LABEL_30:
    v9 |= 2u;
  if ( !g_dwNormalization || GetTickCount() - g_dwTicksNormalization > 0x4E20 )
  {
    pvData = 0;
    pcbData = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows Search",
           L"SystemIndexNormalization",
           0x18u,
           0,
           &pvData,
           &pcbData) )
    {
      pvData = 1;
      SystemPreferredLocale = GetSystemPreferredLocale();
      for ( i = 0; i < 0x44; ++i )
      {
        if ( SystemPreferredLocale == *((_WORD *)&g_rgLanguageDiacriticSensitive + i) )
        {
          v14 = pvData | 2;
          pvData |= 2u;
          goto LABEL_33;
        }
      }
    }
    v14 = pvData;
LABEL_33:
    g_dwNormalization = v14;
    g_dwTicksNormalization = GetTickCount();
  }
  if ( (g_dwNormalization & 2) != 0 )
    v9 |= 4u;
  return v9;
}

```

## disassembly

```asm
0x180054178  mov     [rsp+arg_0], rbx
0x18005417d  mov     [rsp+arg_18], rbp
0x180054182  push    rsi
0x180054183  push    rdi
0x180054184  push    r12
0x180054186  push    r14
0x180054188  push    r15
0x18005418a  sub     rsp, 40h
0x18005418e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180054192  mov     rsi, rcx
0x180054195  mov     rcx, rdi
0x180054198  xor     ebp, ebp
0x18005419a  inc     rcx
0x18005419d  cmp     [rsi+rcx*2], bp
0x1800541a1  jnz     short loc_18005419A
0x1800541a3  mov     r14d, 2
0x1800541a9  lea     r8, String1; "fr"
0x1800541b0  cmp     ecx, r14d
0x1800541b3  mov     eax, r14d
0x1800541b6  mov     r9d, r14d; cchCount1
0x1800541b9  cmovb   eax, ecx
0x1800541bc  mov     [rsp+68h+cchCount2], eax; cchCount2
0x1800541c0  lea     r15d, [r14-1]
0x1800541c4  lea     r12d, [r14+7Dh]
0x1800541c8  mov     [rsp+68h+lpString2], rsi; lpString2
0x1800541cd  mov     edx, r15d; dwCmpFlags
0x1800541d0  mov     ecx, r12d; Locale
0x1800541d3  call    cs:__imp_CompareStringW
0x1800541d9  cmp     eax, r14d
0x1800541dc  jz      loc_180054382
0x1800541e2  mov     rcx, rdi
0x1800541e5  inc     rcx
0x1800541e8  cmp     [rsi+rcx*2], bp
0x1800541ec  jnz     short loc_1800541E5
0x1800541ee  cmp     ecx, r14d
0x1800541f1  lea     r8, aOc; "oc"
0x1800541f8  mov     eax, r14d
0x1800541fb  mov     r9d, r14d; cchCount1
0x1800541fe  cmovb   eax, ecx
0x180054201  mov     edx, r15d; dwCmpFlags
0x180054204  mov     [rsp+68h+cchCount2], eax; cchCount2
0x180054208  mov     ecx, r12d; Locale
0x18005420b  mov     [rsp+68h+lpString2], rsi; lpString2
0x180054210  call    cs:__imp_CompareStringW
0x180054216  cmp     eax, r14d
0x180054219  jz      loc_180054382
0x18005421f  mov     rcx, rdi
0x180054222  inc     rcx
0x180054225  cmp     [rsi+rcx*2], bp
0x180054229  jnz     short loc_180054222
0x18005422b  cmp     ecx, r14d
0x18005422e  lea     r8, aWo_0; "wo"
0x180054235  mov     eax, r14d
0x180054238  mov     r9d, r14d; cchCount1
0x18005423b  cmovb   eax, ecx
0x18005423e  mov     edx, r15d; dwCmpFlags
0x180054241  mov     [rsp+68h+cchCount2], eax; cchCount2
0x180054245  mov     ecx, r12d; Locale
0x180054248  mov     [rsp+68h+lpString2], rsi; lpString2
0x18005424d  call    cs:__imp_CompareStringW
0x180054253  mov     ebx, ebp
0x180054255  cmp     eax, r14d
0x180054258  jz      loc_180054382
0x18005425e  mov     rcx, rdi
0x180054261  inc     rcx
0x180054264  cmp     [rsi+rcx*2], bp
0x180054268  jnz     short loc_180054261
0x18005426a  cmp     ecx, r14d
0x18005426d  lea     r8, aZh_0; "zh"
0x180054274  mov     eax, r14d
0x180054277  mov     r9d, r14d; cchCount1
0x18005427a  cmovb   eax, ecx
0x18005427d  mov     edx, r15d; dwCmpFlags
0x180054280  mov     [rsp+68h+cchCount2], eax; cchCount2
0x180054284  mov     ecx, r12d; Locale
0x180054287  mov     [rsp+68h+lpString2], rsi; lpString2
0x18005428c  call    cs:__imp_CompareStringW
0x180054292  cmp     eax, r14d
0x180054295  jz      short loc_180054312
0x180054297  inc     rdi
0x18005429a  cmp     [rsi+rdi*2], bp
0x18005429e  jnz     short loc_180054297
0x1800542a0  mov     r9d, 0Ch; cchCount1
0x1800542a6  lea     r8, aJaJpRadstr; "ja-JP_radstr"
0x1800542ad  cmp     edi, r9d
0x1800542b0  mov     eax, r9d
0x1800542b3  mov     edx, r15d; dwCmpFlags
0x1800542b6  mov     ecx, r12d; Locale
0x1800542b9  cmovb   eax, edi
0x1800542bc  mov     [rsp+68h+cchCount2], eax; cchCount2
0x1800542c0  mov     [rsp+68h+lpString2], rsi; lpString2
0x1800542c5  call    cs:__imp_CompareStringW
0x1800542cb  cmp     eax, r14d
0x1800542ce  jz      short loc_180054312
0x1800542d0  cmp     cs:?g_dwNormalization@@3KA, ebp; ulong g_dwNormalization
0x1800542d6  jz      short loc_180054317
0x1800542d8  call    cs:__imp_GetTickCount
0x1800542de  sub     eax, cs:?g_dwTicksNormalization@@3KA; ulong g_dwTicksNormalization
0x1800542e4  cmp     eax, 4E20h
0x1800542e9  ja      short loc_180054317
0x1800542eb  test    byte ptr cs:?g_dwNormalization@@3KA, r14b; ulong g_dwNormalization
0x1800542f2  jz      short loc_1800542F7
0x1800542f4  or      ebx, 4
0x1800542f7  lea     r11, [rsp+68h+var_28]
0x1800542fc  mov     eax, ebx
0x1800542fe  mov     rbx, [r11+30h]
0x180054302  mov     rbp, [r11+48h]
0x180054306  mov     rsp, r11
0x180054309  pop     r15
0x18005430b  pop     r14
0x18005430d  pop     r12
0x18005430f  pop     rdi
0x180054310  pop     rsi
0x180054311  retn
0x180054312  or      ebx, r14d
0x180054315  jmp     short loc_1800542D0
0x180054317  lea     rax, [rsp+68h+arg_10]
0x18005431f  mov     [rsp+68h+pvData], ebp
0x180054323  mov     [rsp+68h+pcbData], rax; pcbData
0x180054328  lea     r8, Value; "SystemIndexNormalization"
0x18005432f  lea     rax, [rsp+68h+pvData]
0x180054334  mov     [rsp+68h+arg_10], 4
0x18005433f  mov     qword ptr [rsp+68h+cchCount2], rax; pvData
0x180054344  lea     rdx, aSoftwareMicros_15; "SOFTWARE\\Microsoft\\Windows Search"
0x18005434b  mov     r9d, 18h; dwFlags
0x180054351  mov     [rsp+68h+lpString2], rbp; pdwType
0x180054356  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18005435d  call    cs:__imp_RegGetValueW
0x180054363  test    eax, eax
0x180054365  jnz     short loc_18005438A
0x180054367  mov     eax, [rsp+68h+pvData]
0x18005436b  mov     cs:?g_dwNormalization@@3KA, eax; ulong g_dwNormalization
0x180054371  call    cs:__imp_GetTickCount
0x180054377  mov     cs:?g_dwTicksNormalization@@3KA, eax; ulong g_dwTicksNormalization
0x18005437d  jmp     loc_1800542EB
0x180054382  mov     ebx, r15d
0x180054385  jmp     loc_18005425E
0x18005438a  mov     [rsp+68h+pvData], r15d
0x18005438f  call    ?GetSystemPreferredLocale@@YAKXZ; GetSystemPreferredLocale(void)
0x180054394  mov     edx, ebp
0x180054396  jmp     loc_1802B7BCC
0x1802b7bcc  cmp     edx, 44h ; 'D'
0x1802b7bcf  jnb     loc_180054367
0x1802b7bd5  mov     ecx, edx
0x1802b7bd7  lea     r8, ?g_rgLanguageDiacriticSensitive@@3QBGB; ushort const near * const g_rgLanguageDiacriticSensitive
0x1802b7bde  cmp     ax, [r8+rcx*2]
0x1802b7be3  jz      short loc_1802B7BEA
0x1802b7be5  add     edx, r15d
0x1802b7be8  jmp     short loc_1802B7BCC
0x1802b7bea  mov     eax, [rsp+68h+pvData]
0x1802b7bee  or      eax, r14d
0x1802b7bf1  mov     [rsp+68h+pvData], eax
0x1802b7bf5  jmp     loc_18005436B
```
