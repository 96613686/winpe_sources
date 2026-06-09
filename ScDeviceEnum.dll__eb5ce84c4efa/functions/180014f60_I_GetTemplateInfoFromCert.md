# I_GetTemplateInfoFromCert

- ea: `0x180014f60`
- end: `0x18001531e`
- name: `I_GetTemplateInfoFromCert`
- size: `958`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800160c8`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x180014f60`
- `0x18001ca98`
- `0x18001cc6c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015159`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015170`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001518b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015159`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015170`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001518b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015079`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015113`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015219`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001527a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015079`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015113`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015219`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001527a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015145`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015145`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015258`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800150f6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001513b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800150f6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001513b`
- `CRYPT32!CertFindExtension` at `0x180015012`
- `CRYPT32!CertFindExtension` at `0x1800151b5`
- `CRYPT32!CertFindExtension` at `0x180015012`
- `CRYPT32!CertFindExtension` at `0x1800151b5`
- `CRYPT32!CryptDecodeObject` at `0x18001504f`
- `CRYPT32!CryptDecodeObject` at `0x1800150b0`
- `CRYPT32!CryptDecodeObject` at `0x1800151f8`
- `CRYPT32!CryptDecodeObject` at `0x18001524e`
- `CRYPT32!CryptDecodeObject` at `0x18001504f`
- `CRYPT32!CryptDecodeObject` at `0x1800150b0`
- `CRYPT32!CryptDecodeObject` at `0x1800151f8`
- `CRYPT32!CryptDecodeObject` at `0x18001524e`

## pseudocode

```c
__int64 __fastcall I_GetTemplateInfoFromCert(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  PVOID v6; // rcx
  PCERT_EXTENSION Extension; // rax
  PCERT_EXTENSION v8; // rdi
  DWORD LastError; // ebx
  _DWORD *pvStructInfo; // rsi
  int v11; // r14d
  DWORD v12; // eax
  void *v13; // rbp
  LPVOID v14; // rdi
  PCERT_EXTENSION v15; // rax
  PCERT_EXTENSION v16; // rbp
  SIZE_T v17; // r14
  wchar_t *v18; // rax
  unsigned __int16 v19; // ax
  DWORD pcbStructInfo; // [rsp+70h] [rbp+8h] BYREF

  pcbStructInfo = 0;
  WppTraceIndent(a1, 0);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( !a1 || !a2 || !a3 )
  {
    LastError = 87;
    goto LABEL_37;
  }
  *a2 = 0;
  *a3 = 0;
  Extension = CertFindExtension(
                "1.3.6.1.4.1.311.21.7",
                *(_DWORD *)(*(_QWORD *)(a1 + 24) + 192LL),
                *(CERT_EXTENSION **)(*(_QWORD *)(a1 + 24) + 200LL));
  v8 = Extension;
  if ( !Extension )
  {
    v15 = CertFindExtension(
            "1.3.6.1.4.1.311.20.2",
            *(_DWORD *)(*(_QWORD *)(a1 + 24) + 192LL),
            *(CERT_EXTENSION **)(*(_QWORD *)(a1 + 24) + 200LL));
    v16 = v15;
    if ( v15 )
    {
      if ( !CryptDecodeObject(1u, (LPCSTR)0x18, v15->Value.pbData, v15->Value.cbData, 0, 0, &pcbStructInfo) )
        goto LABEL_10;
      LastError = 8;
      v14 = HeapAlloc(hHeap, 8u, pcbStructInfo);
      if ( !v14 )
        goto LABEL_10;
      pvStructInfo = 0;
      if ( CryptDecodeObject(1u, (LPCSTR)0x18, v16->Value.pbData, v16->Value.cbData, 0, v14, &pcbStructInfo) )
      {
        v17 = (unsigned int)(*((_DWORD *)v14 + 2) + 2);
        v18 = (wchar_t *)HeapAlloc(hHeap, 8u, v17);
        v13 = v18;
        if ( v18 )
        {
          v19 = StringCchCopyW(v18, (unsigned int)v17, *((STRSAFE_LPCWSTR *)v14 + 2));
          LastError = v19;
          if ( v19 )
            goto LABEL_20;
          v11 = 0;
          goto LABEL_35;
        }
      }
      else
      {
        LastError = GetLastError();
      }
LABEL_22:
      HeapFree(hHeap, 0, v14);
LABEL_23:
      if ( !pvStructInfo )
        goto LABEL_37;
LABEL_24:
      HeapFree(hHeap, 0, pvStructInfo);
      goto LABEL_37;
    }
LABEL_27:
    LastError = 1168;
    goto LABEL_37;
  }
  if ( CryptDecodeObject(
         1u,
         "1.3.6.1.4.1.311.21.7",
         Extension->Value.pbData,
         Extension->Value.cbData,
         0,
         0,
         &pcbStructInfo) )
  {
    LastError = 8;
    pvStructInfo = HeapAlloc(hHeap, 8u, pcbStructInfo);
    if ( pvStructInfo )
    {
      if ( !CryptDecodeObject(
              1u,
              "1.3.6.1.4.1.311.21.7",
              v8->Value.pbData,
              v8->Value.cbData,
              0,
              pvStructInfo,
              &pcbStructInfo) )
        goto LABEL_13;
      if ( !*(_QWORD *)pvStructInfo )
      {
        LastError = 1168;
        goto LABEL_24;
      }
      v11 = pvStructInfo[2];
      v12 = MultiByteToWideChar(0, 0, *(LPCCH *)pvStructInfo, -1, 0, 0);
      pcbStructInfo = v12;
      if ( !v12 )
      {
LABEL_13:
        LastError = GetLastError();
        goto LABEL_24;
      }
      v13 = HeapAlloc(hHeap, 8u, 2LL * v12);
      if ( !v13 )
        goto LABEL_24;
      v14 = 0;
      if ( !MultiByteToWideChar(0, 0, *(LPCCH *)pvStructInfo, -1, (LPWSTR)v13, pcbStructInfo) )
      {
        LastError = GetLastError();
LABEL_20:
        HeapFree(hHeap, 0, v13);
        goto LABEL_21;
      }
      LastError = 0;
LABEL_35:
      *a3 = v11;
      *a2 = v13;
LABEL_21:
      if ( !v14 )
        goto LABEL_23;
      goto LABEL_22;
    }
    goto LABEL_27;
  }
LABEL_10:
  LastError = GetLastError();
LABEL_37:
  WppTraceIndent(v6, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180014f60  mov     [rsp+arg_8], rbx
0x180014f65  mov     [rsp+arg_10], rbp
0x180014f6a  push    rsi
0x180014f6b  push    rdi
0x180014f6c  push    r12
0x180014f6e  push    r14
0x180014f70  push    r15
0x180014f72  sub     rsp, 40h
0x180014f76  mov     r12, rdx
0x180014f79  mov     [rsp+68h+arg_0], 0
0x180014f81  xor     edx, edx
0x180014f83  mov     r15, r8
0x180014f86  mov     rbx, rcx
0x180014f89  call    WppTraceIndent
0x180014f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f95  lea     rax, WPP_GLOBAL_Control
0x180014f9c  mov     r14d, 18h
0x180014fa2  cmp     rcx, rax
0x180014fa5  jz      short loc_180014FCD
0x180014fa7  test    byte ptr [rcx+1Ch], 2
0x180014fab  jz      short loc_180014FCD
0x180014fad  cmp     byte ptr [rcx+19h], 5
0x180014fb1  jb      short loc_180014FCD
0x180014fb3  mov     r9, cs:WPP_pszIndent
0x180014fba  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180014fc1  mov     rcx, [rcx+10h]
0x180014fc5  mov     edx, r14d
0x180014fc8  call    WPP_SF_s
0x180014fcd  test    rbx, rbx
0x180014fd0  jz      loc_1800152B5
0x180014fd6  test    r12, r12
0x180014fd9  jz      loc_1800152B5
0x180014fdf  test    r15, r15
0x180014fe2  jz      loc_1800152B5
0x180014fe8  mov     qword ptr [r12], 0
0x180014ff0  lea     rbp, szStructType; "1.3.6.1.4.1.311.21.7"
0x180014ff7  mov     dword ptr [r15], 0
0x180014ffe  mov     rcx, rbp; pszObjId
0x180015001  mov     rdx, [rbx+18h]
0x180015005  mov     r8, [rdx+0C8h]; rgExtensions
0x18001500c  mov     edx, [rdx+0C0h]; cExtensions
0x180015012  call    cs:__imp_CertFindExtension
0x180015018  mov     rdi, rax
0x18001501b  test    rax, rax
0x18001501e  jz      loc_18001519D
0x180015024  mov     r9d, [rdi+10h]; cbEncoded
0x180015028  lea     rax, [rsp+68h+arg_0]
0x18001502d  mov     r8, [rdi+18h]; pbEncoded
0x180015031  mov     rdx, rbp; lpszStructType
0x180015034  mov     [rsp+68h+pcbStructInfo], rax; pcbStructInfo
0x180015039  mov     ecx, 1; dwCertEncodingType
0x18001503e  mov     [rsp+68h+pvStructInfo], 0; pvStructInfo
0x180015047  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18001504f  call    cs:__imp_CryptDecodeObject
0x180015055  test    eax, eax
0x180015057  jnz     short loc_180015066
0x180015059  call    cs:__imp_GetLastError
0x18001505f  mov     ebx, eax
0x180015061  jmp     loc_1800152BA
0x180015066  mov     r8d, [rsp+68h+arg_0]; dwBytes
0x18001506b  mov     ebx, 8
0x180015070  mov     rcx, cs:hHeap; hHeap
0x180015077  mov     edx, ebx; dwFlags
0x180015079  call    cs:__imp_HeapAlloc
0x18001507f  mov     rsi, rax
0x180015082  test    rax, rax
0x180015085  jz      loc_1800151C3
0x18001508b  mov     r9d, [rdi+10h]; cbEncoded
0x18001508f  lea     rax, [rsp+68h+arg_0]
0x180015094  mov     r8, [rdi+18h]; pbEncoded
0x180015098  lea     ecx, [rbx-7]; dwCertEncodingType
0x18001509b  mov     [rsp+68h+pcbStructInfo], rax; pcbStructInfo
0x1800150a0  mov     rdx, rbp; lpszStructType
0x1800150a3  mov     [rsp+68h+pvStructInfo], rsi; pvStructInfo
0x1800150a8  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1800150b0  call    cs:__imp_CryptDecodeObject
0x1800150b6  test    eax, eax
0x1800150b8  jnz     short loc_1800150C7
0x1800150ba  call    cs:__imp_GetLastError
0x1800150c0  mov     ebx, eax
0x1800150c2  jmp     loc_18001517F
0x1800150c7  mov     r8, [rsi]; lpMultiByteStr
0x1800150ca  test    r8, r8
0x1800150cd  jnz     short loc_1800150D9
0x1800150cf  mov     ebx, 490h
0x1800150d4  jmp     loc_18001517F
0x1800150d9  mov     r14d, [rsi+8]
0x1800150dd  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800150e1  mov     dword ptr [rsp+68h+pvStructInfo], 0; cchWideChar
0x1800150e9  xor     edx, edx; dwFlags
0x1800150eb  xor     ecx, ecx; CodePage
0x1800150ed  mov     qword ptr [rsp+68h+dwFlags], 0; lpWideCharStr
0x1800150f6  call    cs:__imp_MultiByteToWideChar
0x1800150fc  mov     [rsp+68h+arg_0], eax
0x180015100  test    eax, eax
0x180015102  jz      short loc_1800150BA
0x180015104  mov     rcx, cs:hHeap; hHeap
0x18001510b  mov     edx, ebx; dwFlags
0x18001510d  mov     r8d, eax
0x180015110  add     r8, r8; dwBytes
0x180015113  call    cs:__imp_HeapAlloc
0x180015119  mov     rbp, rax
0x18001511c  test    rax, rax
0x18001511f  jz      short loc_18001517F
0x180015121  mov     eax, [rsp+68h+arg_0]
0x180015125  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180015129  mov     r8, [rsi]; lpMultiByteStr
0x18001512c  xor     edx, edx; dwFlags
0x18001512e  mov     dword ptr [rsp+68h+pvStructInfo], eax; cchWideChar
0x180015132  xor     ecx, ecx; CodePage
0x180015134  mov     qword ptr [rsp+68h+dwFlags], rbp; lpWideCharStr
0x180015139  xor     edi, edi
0x18001513b  call    cs:__imp_MultiByteToWideChar
0x180015141  test    eax, eax
0x180015143  jnz     short loc_180015196
0x180015145  call    cs:__imp_GetLastError
0x18001514b  mov     ebx, eax
0x18001514d  mov     rcx, cs:hHeap; hHeap
0x180015154  mov     r8, rbp; lpMem
0x180015157  xor     edx, edx; dwFlags
0x180015159  call    cs:__imp_HeapFree
0x18001515f  test    rdi, rdi
0x180015162  jz      short loc_180015176
0x180015164  mov     rcx, cs:hHeap; hHeap
0x18001516b  mov     r8, rdi; lpMem
0x18001516e  xor     edx, edx; dwFlags
0x180015170  call    cs:__imp_HeapFree
0x180015176  test    rsi, rsi
0x180015179  jz      loc_1800152BA
0x18001517f  mov     rcx, cs:hHeap; hHeap
0x180015186  mov     r8, rsi; lpMem
0x180015189  xor     edx, edx; dwFlags
0x18001518b  call    cs:__imp_HeapFree
0x180015191  jmp     loc_1800152BA
0x180015196  xor     ebx, ebx
0x180015198  jmp     loc_1800152A9
0x18001519d  mov     rdx, [rbx+18h]
0x1800151a1  lea     rcx, pszObjId; "1.3.6.1.4.1.311.20.2"
0x1800151a8  mov     r8, [rdx+0C8h]; rgExtensions
0x1800151af  mov     edx, [rdx+0C0h]; cExtensions
0x1800151b5  call    cs:__imp_CertFindExtension
0x1800151bb  mov     rbp, rax
0x1800151be  test    rax, rax
0x1800151c1  jnz     short loc_1800151CD
0x1800151c3  mov     ebx, 490h
0x1800151c8  jmp     loc_1800152BA
0x1800151cd  mov     r9d, [rbp+10h]; cbEncoded
0x1800151d1  lea     rax, [rsp+68h+arg_0]
0x1800151d6  mov     r8, [rbp+18h]; pbEncoded
0x1800151da  mov     rdx, r14; lpszStructType
0x1800151dd  mov     [rsp+68h+pcbStructInfo], rax; pcbStructInfo
0x1800151e2  mov     ecx, 1; dwCertEncodingType
0x1800151e7  mov     [rsp+68h+pvStructInfo], 0; pvStructInfo
0x1800151f0  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1800151f8  call    cs:__imp_CryptDecodeObject
0x1800151fe  test    eax, eax
0x180015200  jz      loc_180015059
0x180015206  mov     r8d, [rsp+68h+arg_0]; dwBytes
0x18001520b  mov     ebx, 8
0x180015210  mov     rcx, cs:hHeap; hHeap
0x180015217  mov     edx, ebx; dwFlags
0x180015219  call    cs:__imp_HeapAlloc
0x18001521f  mov     rdi, rax
0x180015222  test    rax, rax
0x180015225  jz      loc_180015059
0x18001522b  mov     r9d, [rbp+10h]; cbEncoded
0x18001522f  lea     rax, [rsp+68h+arg_0]
0x180015234  mov     r8, [rbp+18h]; pbEncoded
0x180015238  lea     ecx, [rbx-7]; dwCertEncodingType
0x18001523b  mov     [rsp+68h+pcbStructInfo], rax; pcbStructInfo
0x180015240  xor     esi, esi
0x180015242  mov     [rsp+68h+pvStructInfo], rdi; pvStructInfo
0x180015247  mov     rdx, r14; lpszStructType
0x18001524a  mov     [rsp+68h+dwFlags], esi; dwFlags
0x18001524e  call    cs:__imp_CryptDecodeObject
0x180015254  test    eax, eax
0x180015256  jnz     short loc_180015265
0x180015258  call    cs:__imp_GetLastError
0x18001525e  mov     ebx, eax
0x180015260  jmp     loc_180015164
0x180015265  mov     eax, [rdi+8]
0x180015268  mov     edx, ebx; dwFlags
0x18001526a  mov     rcx, cs:hHeap; hHeap
0x180015271  add     eax, 2
0x180015274  mov     r8d, eax; dwBytes
0x180015277  mov     r14d, eax
0x18001527a  call    cs:__imp_HeapAlloc
0x180015280  mov     rbp, rax
0x180015283  test    rax, rax
0x180015286  jz      loc_180015164
0x18001528c  mov     r8, [rdi+10h]; pszSrc
0x180015290  mov     edx, r14d; cchDest
0x180015293  mov     rcx, rax; pszDest
0x180015296  call    StringCchCopyW
0x18001529b  movzx   ebx, ax
0x18001529e  test    ebx, ebx
0x1800152a0  jnz     loc_18001514D
0x1800152a6  xor     r14d, r14d
0x1800152a9  mov     [r15], r14d
0x1800152ac  mov     [r12], rbp
0x1800152b0  jmp     loc_18001515F
0x1800152b5  mov     ebx, 57h ; 'W'
0x1800152ba  mov     edx, 1
0x1800152bf  call    WppTraceIndent
0x1800152c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152cb  lea     rax, WPP_GLOBAL_Control
0x1800152d2  cmp     rcx, rax
0x1800152d5  jz      short loc_180015303
0x1800152d7  test    byte ptr [rcx+1Ch], 2
0x1800152db  jz      short loc_180015303
0x1800152dd  cmp     byte ptr [rcx+19h], 5
0x1800152e1  jb      short loc_180015303
0x1800152e3  mov     r9, cs:WPP_pszIndent
0x1800152ea  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800152f1  mov     rcx, [rcx+10h]
0x1800152f5  mov     edx, 19h
0x1800152fa  mov     [rsp+68h+dwFlags], ebx
0x1800152fe  call    WPP_SF_sd
0x180015303  lea     r11, [rsp+68h+var_28]
0x180015308  mov     eax, ebx
0x18001530a  mov     rbx, [r11+38h]
0x18001530e  mov     rbp, [r11+40h]
0x180015312  mov     rsp, r11
0x180015315  pop     r15
0x180015317  pop     r14
0x180015319  pop     r12
0x18001531b  pop     rdi
0x18001531c  pop     rsi
0x18001531d  retn
```
