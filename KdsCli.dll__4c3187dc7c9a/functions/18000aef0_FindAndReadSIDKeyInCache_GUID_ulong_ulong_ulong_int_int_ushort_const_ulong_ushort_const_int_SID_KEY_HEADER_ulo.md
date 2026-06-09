# FindAndReadSIDKeyInCache(_GUID *,ulong,ulong,ulong,int,int,ushort const *,ulong,ushort const *,int *,_SID_KEY_HEADER * *,ulong *)

- ea: `0x18000aef0`
- end: `0x18000b307`
- name: `?FindAndReadSIDKeyInCache@@YAJPEAU_GUID@@KKKHHPEBGK1PEAHPEAPEAU_SID_KEY_HEADER@@PEAK@Z`
- size: `1047`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned int, int, int, int, int, const unsigned __int16 *, unsigned int, unsigned __int16 *, int *, struct _SID_KEY_HEADER **, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b310`
- `0x1800187ec`

## callees

- `0x180001630`
- `0x180001f7c`
- `0x18000aef0`
- `0x18000bb30`
- `0x18000bd0c`
- `0x18000c1fc`
- `0x180010920`
- `0x180010950`
- `0x18001a450`
- `0x18001a6ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b21c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b21c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000b2ad`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000b2ad`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000b20e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000b20e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18000b034`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18000b034`

## string_xrefs

- `0x18000afc4`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`
- `0x18000b05e`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`
- `0x18000b22f`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`
- `0x18000b2e5`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`

## pseudocode

```c
__int64 __fastcall FindAndReadSIDKeyInCache(
        struct _GUID *a1,
        unsigned int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        const unsigned __int16 *a7,
        unsigned int a8,
        unsigned __int16 *a9,
        int *a10,
        struct _SID_KEY_HEADER **a11,
        unsigned int *a12)
{
  struct _SID_KEY_HEADER *v14; // rdi
  WCHAR *v15; // r13
  int v16; // r14d
  int SIDKeyFileName; // ebx
  unsigned int v18; // r9d
  WCHAR *v19; // r15
  DWORD LastError; // eax
  int v21; // esi
  WCHAR *v22; // rsi
  __int64 v23; // rax
  size_t v24; // rbx
  __int64 v25; // rax
  unsigned int v26; // r13d
  WCHAR *v27; // rax
  WCHAR *v28; // rdi
  size_t v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  DWORD v32; // eax
  __int64 v33; // rax
  struct _SID_KEY_HEADER *v34; // rdx
  LPCWSTR lpFileName; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v37; // [rsp+68h] [rbp-98h] BYREF
  int v38; // [rsp+6Ch] [rbp-94h]
  int v39; // [rsp+70h] [rbp-90h] BYREF
  struct _SID_KEY_HEADER *v40; // [rsp+78h] [rbp-88h] BYREF
  int v41; // [rsp+80h] [rbp-80h]
  int v42; // [rsp+84h] [rbp-7Ch]
  unsigned int v43; // [rsp+88h] [rbp-78h]
  void *Src; // [rsp+90h] [rbp-70h]
  struct _GUID *v45; // [rsp+98h] [rbp-68h]
  struct _SID_KEY_HEADER **v46; // [rsp+A0h] [rbp-60h]
  unsigned int *v47; // [rsp+A8h] [rbp-58h]
  struct _GUID v48; // [rsp+B0h] [rbp-50h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-40h] BYREF

  v14 = 0;
  v46 = a11;
  v15 = 0;
  v42 = a3;
  v43 = a2;
  v45 = a1;
  v47 = a12;
  v41 = a4;
  Src = a9;
  lpFileName = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v39 = 0;
  v40 = 0;
  v16 = 0;
  v37 = 0;
  if ( a1 )
  {
    v48 = *a1;
    SIDKeyFileName = GetSIDKeyFileName(&v48, a2, a5, a9, (unsigned __int16 **)&lpFileName);
    if ( SIDKeyFileName < 0 )
    {
      v18 = 1261;
LABEL_4:
      SidKeyDebugTraceError(
        SIDKeyFileName,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
        v18);
      v19 = (WCHAR *)lpFileName;
      *a10 = 0;
      goto LABEL_41;
    }
    v38 = 1;
  }
  else
  {
    SIDKeyFileName = GetSIDKeyFileNameFilter(a2, a5, a9, (unsigned __int16 **)&lpFileName);
    if ( SIDKeyFileName < 0 )
    {
      v18 = 1276;
      goto LABEL_4;
    }
    v38 = 0;
  }
  v19 = (WCHAR *)lpFileName;
  lpFileName = (LPCWSTR)FindFirstFileExW(lpFileName, FindExInfoStandard, &FindFileData, FindExSearchNameMatch, 0, 0);
  v15 = (WCHAR *)lpFileName;
  if ( lpFileName == (LPCWSTR)-1LL )
  {
    LastError = GetLastError();
    v21 = LastError;
    if ( LastError - 2 > 1 )
    {
      SidKeyDebugTraceError(
        LastError,
        "dwReturn",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
        0x510u);
      if ( v21 > 0 )
        SIDKeyFileName = (unsigned __int16)v21 | 0x80070000;
      else
        SIDKeyFileName = v21;
    }
    *a10 = 0;
  }
  else
  {
    v22 = 0;
    do
    {
      if ( v38 )
      {
        v28 = v19;
      }
      else
      {
        v23 = -1;
        do
          ++v23;
        while ( *((_WORD *)Src + v23) );
        v24 = (unsigned int)(2 * v23);
        v25 = -1;
        do
          ++v25;
        while ( FindFileData.cFileName[v25] );
        v26 = 2 * v25;
        v27 = (WCHAR *)SIDKeyProvAlloc((unsigned int)v24 + 2 * (_DWORD)v25 + (a5 != 0 ? 24 : 26));
        v28 = v27;
        if ( !v27 )
        {
          SIDKeyFileName = -2147024882;
          SidKeyDebugTraceError(
            0x8007000E,
            "hr",
            "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
            0x522u);
          goto LABEL_37;
        }
        memcpy_0(v27, Src, v24);
        *(WCHAR *)((char *)v28 + v24) = asc_18001CD7C[0];
        v29 = (size_t)v28 + v24 + 2;
        if ( a5 )
        {
          *(_OWORD *)v29 = *(_OWORD *)L"PublicKey\\";
          *(_DWORD *)(v29 + 16) = *(_DWORD *)L"y\\";
          v30 = 20;
        }
        else
        {
          v30 = 22;
          *(_OWORD *)v29 = *(_OWORD *)L"PrivateKey\\";
          *(_QWORD *)(v29 + 14) = *(_QWORD *)L"Key\\";
        }
        memcpy_0((void *)(v30 + v29), FindFileData.cFileName, v26);
        v15 = (WCHAR *)lpFileName;
        v22 = v28;
      }
      v31 = ParseFileSearchResult(
              v28,
              *(_QWORD *)&FindFileData.ftLastWriteTime,
              v45,
              v43,
              v42,
              v41,
              a5,
              a6,
              a7,
              &v39,
              &v40,
              &v37);
      v16 = v39;
      v14 = 0;
      SIDKeyFileName = v31;
      if ( v31 < 0 )
      {
        if ( v31 != -2146893821 )
          goto LABEL_37;
      }
      else if ( v39 )
      {
        goto LABEL_29;
      }
      if ( v22 )
      {
        SIDKeyProvFree(v22);
        v22 = 0;
      }
    }
    while ( FindNextFileW(v15, &FindFileData) );
    v32 = GetLastError();
    SIDKeyFileName = v32;
    if ( v32 == 18 )
    {
LABEL_29:
      SIDKeyFileName = 0;
      *v46 = v40;
      *v47 = v37;
      goto LABEL_38;
    }
    SidKeyDebugTraceError(
      v32,
      "dwReturn",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
      0x54Eu);
    if ( SIDKeyFileName > 0 )
      SIDKeyFileName = (unsigned __int16)SIDKeyFileName | 0x80070000;
LABEL_37:
    v14 = v40;
LABEL_38:
    *a10 = v16;
    if ( v22 )
      SIDKeyProvFree(v22);
    v15 = (WCHAR *)lpFileName;
  }
LABEL_41:
  if ( v14 )
  {
    v33 = v37;
    v34 = v14;
    if ( v37 )
    {
      do
      {
        *(_BYTE *)v34 = 0;
        v34 = (struct _SID_KEY_HEADER *)((char *)v34 + 1);
        --v33;
      }
      while ( v33 );
    }
    SIDKeyProvFree(v14);
  }
  if ( v19 )
    SIDKeyProvFree(v19);
  if ( (unsigned __int64)v15 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose(v15);
  return (unsigned int)SIDKeyFileName;
}

```

## disassembly

```asm
0x18000aef0  mov     [rsp-8+arg_10], rbx
0x18000aef5  push    rbp
0x18000aef6  push    rsi
0x18000aef7  push    rdi
0x18000aef8  push    r12
0x18000aefa  push    r13
0x18000aefc  push    r14
0x18000aefe  push    r15
0x18000af00  lea     rbp, [rsp-220h]
0x18000af08  sub     rsp, 320h
0x18000af0f  mov     rax, cs:__security_cookie
0x18000af16  xor     rax, rsp
0x18000af19  mov     [rbp+250h+var_40], rax
0x18000af20  mov     rax, [rbp+250h+arg_50]
0x18000af27  mov     esi, edx
0x18000af29  mov     rbx, [rbp+250h+arg_40]
0x18000af30  mov     r15, rcx
0x18000af33  mov     r12, [rbp+250h+arg_48]
0x18000af3a  xor     edi, edi
0x18000af3c  mov     [rbp+250h+var_2B0], rax
0x18000af40  mov     r13d, edi
0x18000af43  mov     rax, [rbp+250h+arg_58]
0x18000af4a  mov     [rbp+250h+var_2CC], r8d
0x18000af4e  mov     r8d, 250h; Size
0x18000af54  mov     [rbp+250h+var_2C8], edx
0x18000af57  xor     edx, edx; Val
0x18000af59  mov     [rbp+250h+var_2B8], rcx
0x18000af5d  lea     rcx, [rbp+250h+FindFileData]; void *
0x18000af61  mov     [rbp+250h+var_2A8], rax
0x18000af65  mov     [rbp+250h+var_2D0], r9d
0x18000af69  mov     [rbp+250h+Src], rbx
0x18000af6d  mov     [rsp+350h+lpFileName], rdi
0x18000af72  call    memset_0
0x18000af77  xor     eax, eax
0x18000af79  mov     [rsp+350h+var_2E0], edi
0x18000af7d  mov     [rsp+350h+var_2D8], rdi
0x18000af82  mov     r14d, edi
0x18000af85  mov     [rsp+350h+var_2E8], eax
0x18000af89  test    r15, r15
0x18000af8c  jz      short loc_18000AFF1
0x18000af8e  movups  xmm0, xmmword ptr [r15]
0x18000af92  mov     r8d, [rbp+250h+arg_20]; int
0x18000af99  lea     rax, [rsp+350h+lpFileName]
0x18000af9e  mov     r9, rbx; unsigned __int16 *
0x18000afa1  mov     [rsp+350h+lpSearchFilter], rax; unsigned __int16 **
0x18000afa6  mov     edx, esi; unsigned int
0x18000afa8  lea     rcx, [rbp+250h+var_2A0]; struct _GUID
0x18000afac  movdqu  xmmword ptr [rbp+250h+var_2A0.Data1], xmm0
0x18000afb1  call    ?GetSIDKeyFileName@@YAJU_GUID@@KHPEBGPEAPEAG@Z; GetSIDKeyFileName(_GUID,ulong,int,ushort const *,ushort * *)
0x18000afb6  mov     ebx, eax
0x18000afb8  xor     eax, eax
0x18000afba  test    ebx, ebx
0x18000afbc  jns     short loc_18000AFE7
0x18000afbe  mov     r9d, 4EDh; unsigned int
0x18000afc4  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000afcb  mov     ecx, ebx; unsigned int
0x18000afcd  lea     rdx, aHr; "hr"
0x18000afd4  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000afd9  mov     r15, [rsp+350h+lpFileName]
0x18000afde  mov     [r12], edi
0x18000afe2  jmp     loc_18000B26C
0x18000afe7  mov     [rsp+350h+var_2E4], 1
0x18000afef  jmp     short loc_18000B01A
0x18000aff1  mov     edx, [rbp+250h+arg_20]; int
0x18000aff7  lea     r9, [rsp+350h+lpFileName]; unsigned __int16 **
0x18000affc  mov     r8, rbx; unsigned __int16 *
0x18000afff  mov     ecx, esi; unsigned int
0x18000b001  call    ?GetSIDKeyFileNameFilter@@YAJKHPEBGPEAPEAG@Z; GetSIDKeyFileNameFilter(ulong,int,ushort const *,ushort * *)
0x18000b006  mov     ebx, eax
0x18000b008  xor     eax, eax
0x18000b00a  test    ebx, ebx
0x18000b00c  jns     short loc_18000B016
0x18000b00e  mov     r9d, 4FCh
0x18000b014  jmp     short loc_18000AFC4
0x18000b016  mov     [rsp+350h+var_2E4], eax
0x18000b01a  mov     r15, [rsp+350h+lpFileName]
0x18000b01f  lea     r8, [rbp+250h+FindFileData]; lpFindFileData
0x18000b023  mov     [rsp+350h+dwAdditionalFlags], eax; dwAdditionalFlags
0x18000b027  mov     rcx, r15; lpFileName
0x18000b02a  xor     r9d, r9d; fSearchOp
0x18000b02d  mov     [rsp+350h+lpSearchFilter], rax; lpSearchFilter
0x18000b032  xor     edx, edx; fInfoLevelId
0x18000b034  call    cs:__imp_FindFirstFileExW
0x18000b03a  mov     [rsp+350h+lpFileName], rax
0x18000b03f  mov     r13, rax
0x18000b042  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b046  jnz     short loc_18000B08D
0x18000b048  call    cs:__imp_GetLastError
0x18000b04e  mov     esi, eax
0x18000b050  lea     ecx, [rax-2]
0x18000b053  cmp     ecx, 1
0x18000b056  jbe     short loc_18000B084
0x18000b058  mov     r9d, 510h; unsigned int
0x18000b05e  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000b065  lea     rdx, aDwreturn; "dwReturn"
0x18000b06c  mov     ecx, eax; unsigned int
0x18000b06e  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000b073  test    esi, esi
0x18000b075  jg      short loc_18000B07B
0x18000b077  mov     ebx, esi
0x18000b079  jmp     short loc_18000B084
0x18000b07b  movzx   ebx, si
0x18000b07e  or      ebx, 80070000h
0x18000b084  mov     [r12], edi
0x18000b088  jmp     loc_18000B26C
0x18000b08d  mov     rsi, rdi
0x18000b090  cmp     [rsp+350h+var_2E4], edi
0x18000b094  jnz     loc_18000B161
0x18000b09a  mov     rcx, [rbp+250h+Src]
0x18000b09e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b0a2  inc     rax
0x18000b0a5  cmp     [rcx+rax*2], di
0x18000b0a9  jnz     short loc_18000B0A2
0x18000b0ab  lea     ebx, [rax+rax]
0x18000b0ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b0b2  lea     rcx, [rbp+250h+var_264]
0x18000b0b6  inc     rax
0x18000b0b9  cmp     [rcx+rax*2], di
0x18000b0bd  jnz     short loc_18000B0B6
0x18000b0bf  lea     r13d, [rax+rax]
0x18000b0c3  mov     eax, [rbp+250h+arg_20]
0x18000b0c9  neg     eax
0x18000b0cb  sbb     ecx, ecx
0x18000b0cd  and     ecx, 0FFFFFFFEh
0x18000b0d0  add     ecx, 1Ah
0x18000b0d3  add     ecx, r13d
0x18000b0d6  add     ecx, ebx; unsigned __int64
0x18000b0d8  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000b0dd  mov     rdi, rax
0x18000b0e0  test    rax, rax
0x18000b0e3  jz      loc_18000B2DF
0x18000b0e9  mov     rdx, [rbp+250h+Src]; Src
0x18000b0ed  mov     r8, rbx; Size
0x18000b0f0  mov     rcx, rax; void *
0x18000b0f3  call    memcpy_0
0x18000b0f8  mov     ecx, dword ptr cs:asc_18001CD7C; "\\"
0x18000b0fe  mov     [rbx+rdi], cx
0x18000b102  lea     rcx, [rdi+2]
0x18000b106  add     rcx, rbx
0x18000b109  cmp     [rbp+250h+arg_20], 0
0x18000b110  jz      short loc_18000B12C
0x18000b112  movups  xmm0, xmmword ptr cs:aPublickey; "PublicKey\\"
0x18000b119  movups  xmmword ptr [rcx], xmm0
0x18000b11c  mov     eax, dword ptr cs:aPublickey+10h; "y\\"
0x18000b122  mov     [rcx+10h], eax
0x18000b125  mov     eax, 14h
0x18000b12a  jmp     short loc_18000B148
0x18000b12c  movups  xmm0, xmmword ptr cs:aPrivatekey; "PrivateKey\\"
0x18000b133  mov     eax, 16h
0x18000b138  movups  xmmword ptr [rcx], xmm0
0x18000b13b  movsd   xmm1, qword ptr cs:aPrivatekey+0Eh; "Key\\"
0x18000b143  movsd   qword ptr [rcx+0Eh], xmm1
0x18000b148  mov     r8d, r13d; Size
0x18000b14b  lea     rdx, [rbp+250h+var_264]; Src
0x18000b14f  add     rcx, rax; void *
0x18000b152  call    memcpy_0
0x18000b157  mov     r13, [rsp+350h+lpFileName]
0x18000b15c  mov     rsi, rdi
0x18000b15f  jmp     short loc_18000B164
0x18000b161  mov     rdi, r15
0x18000b164  mov     rdx, [rbp+250h+var_27C]
0x18000b168  lea     rax, [rsp+350h+var_2E8]
0x18000b16d  mov     r9d, [rbp+250h+var_2C8]
0x18000b171  mov     rcx, rdi
0x18000b174  mov     r8, [rbp+250h+var_2B8]
0x18000b178  mov     [rsp+350h+var_2F8], rax
0x18000b17d  lea     rax, [rsp+350h+var_2D8]
0x18000b182  mov     [rsp+350h+var_300], rax
0x18000b187  lea     rax, [rsp+350h+var_2E0]
0x18000b18c  mov     [rsp+350h+var_308], rax
0x18000b191  mov     rax, [rbp+250h+arg_30]
0x18000b198  mov     [rsp+350h+var_310], rax
0x18000b19d  mov     eax, [rbp+250h+arg_28]
0x18000b1a3  mov     [rsp+350h+var_318], eax
0x18000b1a7  mov     eax, [rbp+250h+arg_20]
0x18000b1ad  mov     [rsp+350h+var_320], eax
0x18000b1b1  mov     eax, [rbp+250h+var_2D0]
0x18000b1b4  mov     [rsp+350h+dwAdditionalFlags], eax
0x18000b1b8  mov     eax, [rbp+250h+var_2CC]
0x18000b1bb  mov     dword ptr [rsp+350h+lpSearchFilter], eax
0x18000b1bf  call    ParseFileSearchResult
0x18000b1c4  mov     r14d, [rsp+350h+var_2E0]
0x18000b1c9  xor     edi, edi
0x18000b1cb  mov     ebx, eax
0x18000b1cd  test    eax, eax
0x18000b1cf  js      short loc_18000B1F0
0x18000b1d1  test    r14d, r14d
0x18000b1d4  jz      short loc_18000B1F7
0x18000b1d6  mov     rcx, [rbp+250h+var_2B0]
0x18000b1da  mov     ebx, edi
0x18000b1dc  mov     rax, [rsp+350h+var_2D8]
0x18000b1e1  mov     [rcx], rax
0x18000b1e4  mov     rcx, [rbp+250h+var_2A8]
0x18000b1e8  mov     eax, [rsp+350h+var_2E8]
0x18000b1ec  mov     [rcx], eax
0x18000b1ee  jmp     short loc_18000B256
0x18000b1f0  cmp     eax, 80090003h
0x18000b1f5  jnz     short loc_18000B251
0x18000b1f7  test    rsi, rsi
0x18000b1fa  jz      short loc_18000B207
0x18000b1fc  mov     rcx, rsi; lpMem
0x18000b1ff  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000b204  mov     rsi, rdi
0x18000b207  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x18000b20b  mov     rcx, r13; hFindFile
0x18000b20e  call    cs:__imp_FindNextFileW
0x18000b214  test    eax, eax
0x18000b216  jnz     loc_18000B090
0x18000b21c  call    cs:__imp_GetLastError
0x18000b222  mov     ebx, eax
0x18000b224  cmp     eax, 12h
0x18000b227  jz      short loc_18000B1D6
0x18000b229  mov     r9d, 54Eh; unsigned int
0x18000b22f  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000b236  lea     rdx, aDwreturn; "dwReturn"
0x18000b23d  mov     ecx, eax; unsigned int
0x18000b23f  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000b244  test    ebx, ebx
0x18000b246  jle     short loc_18000B251
0x18000b248  movzx   ebx, bx
0x18000b24b  or      ebx, 80070000h
0x18000b251  mov     rdi, [rsp+350h+var_2D8]
0x18000b256  mov     [r12], r14d
0x18000b25a  test    rsi, rsi
0x18000b25d  jz      short loc_18000B267
0x18000b25f  mov     rcx, rsi; lpMem
0x18000b262  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000b267  mov     r13, [rsp+350h+lpFileName]
0x18000b26c  xor     esi, esi
0x18000b26e  test    rdi, rdi
0x18000b271  jz      short loc_18000B293
0x18000b273  mov     eax, [rsp+350h+var_2E8]
0x18000b277  mov     rdx, rdi
0x18000b27a  test    rax, rax
0x18000b27d  jz      short loc_18000B28B
0x18000b27f  mov     [rdx], sil
0x18000b282  inc     rdx
0x18000b285  sub     rax, 1
0x18000b289  jnz     short loc_18000B27F
0x18000b28b  mov     rcx, rdi; lpMem
0x18000b28e  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000b293  test    r15, r15
0x18000b296  jz      short loc_18000B2A0
0x18000b298  mov     rcx, r15; lpMem
0x18000b29b  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000b2a0  lea     rax, [r13-1]
0x18000b2a4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b2a8  ja      short loc_18000B2B3
0x18000b2aa  mov     rcx, r13; hFindFile
0x18000b2ad  call    cs:__imp_FindClose
0x18000b2b3  mov     eax, ebx
0x18000b2b5  mov     rcx, [rbp+250h+var_40]
0x18000b2bc  xor     rcx, rsp; StackCookie
0x18000b2bf  call    __security_check_cookie
0x18000b2c4  mov     rbx, [rsp+350h+arg_10]
0x18000b2cc  add     rsp, 320h
0x18000b2d3  pop     r15
0x18000b2d5  pop     r14
0x18000b2d7  pop     r13
0x18000b2d9  pop     r12
0x18000b2db  pop     rdi
0x18000b2dc  pop     rsi
0x18000b2dd  pop     rbp
0x18000b2de  retn
0x18000b2df  mov     r9d, 522h; unsigned int
0x18000b2e5  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000b2ec  lea     rdx, aHr; "hr"
0x18000b2f3  mov     ecx, 8007000Eh; unsigned int
0x18000b2f8  mov     ebx, 8007000Eh
0x18000b2fd  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000b302  jmp     loc_18000B251
```
