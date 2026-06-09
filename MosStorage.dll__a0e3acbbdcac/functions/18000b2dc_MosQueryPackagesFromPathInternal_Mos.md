# MosQueryPackagesFromPathInternal_Mos

- ea: `0x18000b2dc`
- end: `0x18000b59d`
- name: `MosQueryPackagesFromPathInternal_Mos`
- size: `705`
- prototype: `__int64 __fastcall(__int64, char, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b284`

## callees

- `0x180001c80`
- `0x180002802`
- `0x180002870`
- `0x180006100`
- `0x18000ac28`
- `0x18000b2dc`
- `0x18000d1b4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000b3cf`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000b3cf`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000b4f7`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000b4f7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000b56f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000b56f`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x18000b448`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x18000b448`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000b55a`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000b55a`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000b518`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000b518`

## string_xrefs

- `0x18000b43c`: `MosQueryPackagesFromPathInternal_Mos`
- `0x18000b50f`: `MosQueryPackagesFromPathInternal_Mos`
- `0x18000b54e`: `MosQueryPackagesFromPathInternal_Mos`
- `0x18000b363`: `diskcache`

## pseudocode

```c
__int64 __fastcall MosQueryPackagesFromPathInternal_Mos(__int64 a1, char a2, _QWORD *a3)
{
  __int64 FirstFileW; // rbx
  int v7; // eax
  int v8; // ecx
  unsigned int v9; // esi
  _DWORD *v10; // rdx
  unsigned int v11; // edi
  int v12; // r8d
  unsigned int v13; // eax
  int v14; // r8d
  __int64 v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+20h] [rbp-E0h]
  __int64 v18; // [rsp+28h] [rbp-D8h]
  bool v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v23[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR FileName[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  wchar_t Format[264]; // [rsp+6C0h] [rbp+5C0h] BYREF
  unsigned __int16 v26[264]; // [rsp+8D0h] [rbp+7D0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = -1;
  v21 = -1;
  if ( !a1 )
  {
    v14 = 118;
    goto LABEL_33;
  }
  if ( !a3 )
  {
    v14 = 119;
LABEL_33:
    v13 = ZTraceReportOriginationNoThis(-2147467261, "MosQueryPackagesFromPathInternal_Mos", v14);
    goto LABEL_34;
  }
  if ( *a3 != a3[1] )
    a3[1] = *a3;
  v7 = StringCchPrintfW(v23, 0x104u, L"%s\\%s\\%s\\%s", a1, L"diskcache", L"BundleStore", L"PACKAGES");
  if ( v7 < 0 )
  {
    v12 = 122;
  }
  else
  {
    LODWORD(v16) = 0;
    v7 = StringCchPrintfW(FileName, 0x104u, L"%s\\*.P%02X", v23, v16);
    if ( v7 < 0 )
    {
      v12 = 124;
    }
    else
    {
      FirstFileW = (__int64)FindFirstFileW(FileName, &FindFileData);
      v21 = FirstFileW;
      if ( FirstFileW == -1 )
      {
LABEL_24:
        v11 = 0;
        goto LABEL_35;
      }
      v7 = StringCchPrintfW(Format, 0x104u, L"%%08X\\*.P%02X", 0);
      if ( v7 >= 0 )
      {
        while ( 1 )
        {
          if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
          {
            v20 = 0;
            if ( swscanf_s(FindFileData.cFileName, Format, &v20) != 1 )
              ZTraceReportIgnoreNoThis(-2143748095, "MosQueryPackagesFromPathInternal_Mos", 142);
            v8 = v20;
            if ( v20 )
            {
              v9 = 1;
              while ( 1 )
              {
                v19 = 0;
                LODWORD(v18) = *((_DWORD *)qword_180012B90 + v9);
                LODWORD(v17) = v8;
                v7 = StringCchPrintfW(v26, 0x104u, L"%s\\%08X.P%02X", v23, v17, v18);
                if ( v7 < 0 )
                {
                  v12 = 154;
                  goto LABEL_26;
                }
                v7 = FileExists(v26, &v19);
                if ( v7 < 0 )
                {
                  v12 = 156;
                  goto LABEL_26;
                }
                if ( !v19 )
                  goto LABEL_23;
                if ( ++v9 >= 5 )
                  break;
                v8 = v20;
              }
              v10 = (_DWORD *)a3[1];
              if ( v10 == (_DWORD *)a3[2] )
              {
                std::vector<unsigned int>::_Emplace_reallocate<unsigned int const &>(a3, v10, &v20);
              }
              else
              {
                *v10 = v20;
                a3[1] += 4LL;
              }
              if ( a2 )
                goto LABEL_24;
            }
          }
LABEL_23:
          if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
            goto LABEL_24;
        }
      }
      v12 = 131;
    }
  }
LABEL_26:
  v13 = ZTraceReportPropagationNoThis(v7, "MosQueryPackagesFromPathInternal_Mos", v12);
LABEL_34:
  v11 = v13;
LABEL_35:
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose((HANDLE)FirstFileW);
  return v11;
}

```

## disassembly

```asm
0x18000b2dc  mov     [rsp-8+arg_8], rbx
0x18000b2e1  push    rbp
0x18000b2e2  push    rsi
0x18000b2e3  push    rdi
0x18000b2e4  push    r12
0x18000b2e6  push    r14
0x18000b2e8  lea     rbp, [rsp-9F0h]
0x18000b2f0  sub     rsp, 0AF0h
0x18000b2f7  mov     rax, cs:__security_cookie
0x18000b2fe  xor     rax, rsp
0x18000b301  mov     [rbp+0A10h+var_30], rax
0x18000b308  mov     rdi, r8
0x18000b30b  mov     r14b, dl
0x18000b30e  mov     rsi, rcx
0x18000b311  xor     edx, edx; Val
0x18000b313  mov     r8d, 250h; Size
0x18000b319  lea     rcx, [rsp+0B10h+FindFileData]; void *
0x18000b31e  call    memset_0
0x18000b323  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000b327  mov     [rsp+0B10h+var_AC8], rbx
0x18000b32c  test    rsi, rsi
0x18000b32f  jz      loc_18000B548
0x18000b335  test    rdi, rdi
0x18000b338  jz      loc_18000B540
0x18000b33e  mov     rax, [rdi]
0x18000b341  cmp     rax, [rdi+8]
0x18000b345  jz      short loc_18000B34B
0x18000b347  mov     [rdi+8], rax
0x18000b34b  lea     rax, aPackages; "PACKAGES"
0x18000b352  mov     [rsp+0B10h+var_AE0], rax
0x18000b357  lea     rax, aBundlestore; "BundleStore"
0x18000b35e  mov     [rsp+0B10h+var_AE8], rax
0x18000b363  lea     rax, aDiskcache; "diskcache"
0x18000b36a  mov     [rsp+0B10h+var_AF0], rax
0x18000b36f  mov     r9, rsi
0x18000b372  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x18000b379  mov     r12d, 104h
0x18000b37f  mov     edx, r12d; unsigned __int64
0x18000b382  lea     rcx, [rbp+0A10h+var_870]; unsigned __int16 *
0x18000b389  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b38e  test    eax, eax
0x18000b390  js      loc_18000B538
0x18000b396  mov     dword ptr [rsp+0B10h+var_AF0], 0
0x18000b39e  lea     r9, [rbp+0A10h+var_870]
0x18000b3a5  lea     r8, aSP02x; "%s\\*.P%02X"
0x18000b3ac  mov     edx, r12d; unsigned __int64
0x18000b3af  lea     rcx, [rbp+0A10h+FileName]; unsigned __int16 *
0x18000b3b6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b3bb  test    eax, eax
0x18000b3bd  js      loc_18000B530
0x18000b3c3  lea     rdx, [rsp+0B10h+FindFileData]; lpFindFileData
0x18000b3c8  lea     rcx, [rbp+0A10h+FileName]; lpFileName
0x18000b3cf  call    cs:__imp_FindFirstFileW
0x18000b3d5  mov     rbx, rax
0x18000b3d8  mov     [rsp+0B10h+var_AC8], rax
0x18000b3dd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b3e1  jz      loc_18000B505
0x18000b3e7  xor     r9d, r9d
0x18000b3ea  lea     r8, a08xP02x; "%%08X\\*.P%02X"
0x18000b3f1  mov     edx, r12d; unsigned __int64
0x18000b3f4  lea     rcx, [rbp+0A10h+Format]; unsigned __int16 *
0x18000b3fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b400  test    eax, eax
0x18000b402  js      loc_18000B528
0x18000b408  test    byte ptr [rsp+0B10h+FindFileData.dwFileAttributes], 10h
0x18000b40d  jnz     loc_18000B4EF
0x18000b413  mov     [rsp+0B10h+var_ACC], 0
0x18000b41b  lea     r8, [rsp+0B10h+var_ACC]
0x18000b420  lea     rdx, [rbp+0A10h+Format]; Format
0x18000b427  lea     rcx, [rsp+0B10h+FindFileData.cFileName]; Buffer
0x18000b42c  call    swscanf_s
0x18000b431  cmp     eax, 1
0x18000b434  jz      short loc_18000B44E
0x18000b436  mov     r8d, 8Eh
0x18000b43c  lea     rdx, aMosquerypackag_2; "MosQueryPackagesFromPathInternal_Mos"
0x18000b443  mov     ecx, 80390001h
0x18000b448  call    cs:__imp_?ZTraceReportIgnoreNoThis@@YAXHPEBDH@Z; ZTraceReportIgnoreNoThis(int,char const *,int)
0x18000b44e  mov     ecx, [rsp+0B10h+var_ACC]
0x18000b452  test    ecx, ecx
0x18000b454  jz      loc_18000B4EF
0x18000b45a  mov     esi, 1
0x18000b45f  mov     [rsp+0B10h+var_AD0], 0
0x18000b464  mov     eax, esi
0x18000b466  lea     rdx, qword_180012B90
0x18000b46d  mov     eax, [rdx+rax*4]
0x18000b470  mov     dword ptr [rsp+0B10h+var_AE8], eax
0x18000b474  mov     dword ptr [rsp+0B10h+var_AF0], ecx
0x18000b478  lea     r9, [rbp+0A10h+var_870]
0x18000b47f  lea     r8, aS08xP02x; "%s\\%08X.P%02X"
0x18000b486  mov     rdx, r12; unsigned __int64
0x18000b489  lea     rcx, [rbp+0A10h+var_240]; unsigned __int16 *
0x18000b490  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b495  test    eax, eax
0x18000b497  js      loc_18000B520
0x18000b49d  lea     rdx, [rsp+0B10h+var_AD0]; bool *
0x18000b4a2  lea     rcx, [rbp+0A10h+var_240]; unsigned __int16 *
0x18000b4a9  call    ?FileExists@@YAJPEBGPEA_N@Z; FileExists(ushort const *,bool *)
0x18000b4ae  test    eax, eax
0x18000b4b0  js      short loc_18000B509
0x18000b4b2  cmp     [rsp+0B10h+var_AD0], 0
0x18000b4b7  jz      short loc_18000B4EF
0x18000b4b9  inc     esi
0x18000b4bb  cmp     esi, 5
0x18000b4be  jnb     short loc_18000B4C6
0x18000b4c0  mov     ecx, [rsp+0B10h+var_ACC]
0x18000b4c4  jmp     short loc_18000B45F
0x18000b4c6  mov     rdx, [rdi+8]
0x18000b4ca  cmp     rdx, [rdi+10h]
0x18000b4ce  jz      short loc_18000B4DD
0x18000b4d0  mov     eax, [rsp+0B10h+var_ACC]
0x18000b4d4  mov     [rdx], eax
0x18000b4d6  add     qword ptr [rdi+8], 4
0x18000b4db  jmp     short loc_18000B4EA
0x18000b4dd  lea     r8, [rsp+0B10h+var_ACC]
0x18000b4e2  mov     rcx, rdi
0x18000b4e5  call    ??$_Emplace_reallocate@AEBI@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAIAEBI@Z; std::vector<uint>::_Emplace_reallocate<uint const &>(uint * const,uint const &)
0x18000b4ea  test    r14b, r14b
0x18000b4ed  jnz     short loc_18000B505
0x18000b4ef  lea     rdx, [rsp+0B10h+FindFileData]; lpFindFileData
0x18000b4f4  mov     rcx, rbx; hFindFile
0x18000b4f7  call    cs:__imp_FindNextFileW
0x18000b4fd  test    eax, eax
0x18000b4ff  jnz     loc_18000B408
0x18000b505  xor     edi, edi
0x18000b507  jmp     short loc_18000B562
0x18000b509  mov     r8d, 9Ch
0x18000b50f  lea     rdx, aMosquerypackag_2; "MosQueryPackagesFromPathInternal_Mos"
0x18000b516  mov     ecx, eax
0x18000b518  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000b51e  jmp     short loc_18000B560
0x18000b520  mov     r8d, 9Ah
0x18000b526  jmp     short loc_18000B50F
0x18000b528  mov     r8d, 83h
0x18000b52e  jmp     short loc_18000B50F
0x18000b530  mov     r8d, 7Ch ; '|'
0x18000b536  jmp     short loc_18000B50F
0x18000b538  mov     r8d, 7Ah ; 'z'
0x18000b53e  jmp     short loc_18000B50F
0x18000b540  mov     r8d, 77h ; 'w'
0x18000b546  jmp     short loc_18000B54E
0x18000b548  mov     r8d, 76h ; 'v'
0x18000b54e  lea     rdx, aMosquerypackag_2; "MosQueryPackagesFromPathInternal_Mos"
0x18000b555  mov     ecx, 80004003h
0x18000b55a  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000b560  mov     edi, eax
0x18000b562  lea     rax, [rbx-1]
0x18000b566  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b56a  ja      short loc_18000B575
0x18000b56c  mov     rcx, rbx; hFindFile
0x18000b56f  call    cs:__imp_FindClose
0x18000b575  mov     eax, edi
0x18000b577  mov     rcx, [rbp+0A10h+var_30]
0x18000b57e  xor     rcx, rsp; StackCookie
0x18000b581  call    __security_check_cookie
0x18000b586  mov     rbx, [rsp+0B10h+arg_8]
0x18000b58e  add     rsp, 0AF0h
0x18000b595  pop     r14
0x18000b597  pop     r12
0x18000b599  pop     rdi
0x18000b59a  pop     rsi
0x18000b59b  pop     rbp
0x18000b59c  retn
```
