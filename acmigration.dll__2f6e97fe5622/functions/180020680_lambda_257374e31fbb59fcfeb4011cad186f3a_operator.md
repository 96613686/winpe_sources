# _lambda_257374e31fbb59fcfeb4011cad186f3a_::operator()

- ea: `0x180020680`
- end: `0x180020d14`
- name: `_lambda_257374e31fbb59fcfeb4011cad186f3a_::operator()`
- size: `1684`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021644`

## callees

- `0x180001cf0`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000c190`
- `0x18000dfd8`
- `0x18000e064`
- `0x180016e60`
- `0x18002058c`
- `0x180020680`
- `0x180040224`
- `0x1800543c0`
- `0x180065150`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800206f2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020781`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800206f2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020781`
- `KERNEL32!LoadLibraryExW` at `0x180020827`
- `KERNEL32!LoadLibraryExW` at `0x180020827`
- `KERNEL32!GetProcAddress` at `0x18002088f`
- `KERNEL32!GetProcAddress` at `0x18002088f`
- `KERNEL32!GetLastError` at `0x180020840`
- `KERNEL32!GetLastError` at `0x1800208a8`
- `KERNEL32!GetLastError` at `0x180020840`
- `KERNEL32!GetLastError` at `0x1800208a8`

## string_xrefs

- `0x1800207aa`: `devinv.dll`
- `0x1800207c0`: `devinv.dll`
- `0x180020717`: `aeinv.dll`
- `0x18002072d`: `aeinv.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall lambda_257374e31fbb59fcfeb4011cad186f3a_::operator()(_QWORD *a1)
{
  _OWORD *v2; // rax
  _QWORD *v3; // rdx
  const WCHAR **v4; // r14
  __int64 v5; // rcx
  _WORD *v6; // rbx
  __int64 v7; // r8
  const CHAR **v8; // rsi
  __int64 v9; // rcx
  _BYTE *v10; // r15
  const char *v11; // rdx
  const char *v12; // r9
  _QWORD *v13; // rdx
  __int64 v14; // rcx
  _WORD *v15; // rbx
  const WCHAR *v16; // rcx
  HMODULE v17; // rcx
  DWORD LastError; // eax
  const WCHAR *v19; // rcx
  const char *v20; // r9
  __int64 v21; // r8
  const CHAR *v23; // rdx
  __int64 (__fastcall *v24)(_QWORD, _QWORD, _QWORD); // rax
  const CHAR *v25; // rax
  __int64 v26; // rsi
  __int64 v27; // rcx
  _QWORD *v28; // rax
  unsigned __int64 i; // r14
  __int64 v30; // rbx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r15
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rax
  _DWORD *v41; // rbx
  __int64 v42; // rax
  _WORD *v43; // rcx
  unsigned __int64 j; // rsi
  __int64 v45; // r14
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  _QWORD *v53; // rax
  DWORD v54; // [rsp+28h] [rbp-B1h]
  int v55; // [rsp+28h] [rbp-B1h]
  __int128 v56; // [rsp+40h] [rbp-99h] BYREF
  __int128 v57; // [rsp+50h] [rbp-89h]
  __int128 Src; // [rsp+60h] [rbp-79h] BYREF
  __int128 v59; // [rsp+70h] [rbp-69h]
  __int128 v60; // [rsp+80h] [rbp-59h] BYREF
  __int128 v61; // [rsp+90h] [rbp-49h]
  __int128 v62; // [rsp+A0h] [rbp-39h] BYREF
  __int128 v63; // [rsp+B0h] [rbp-29h]
  _OWORD v64[2]; // [rsp+C0h] [rbp-19h] BYREF

  v2 = (_OWORD *)*a1;
  *v2 = 0;
  v2[1] = 0;
  *(_QWORD *)*a1 = 32;
  *(_DWORD *)(*a1 + 16LL) = *(_DWORD *)a1[1];
  v3 = (_QWORD *)a1[2];
  if ( v3[3] > 7u )
    v3 = (_QWORD *)*v3;
  if ( (unsigned int)_o__wcsicmp(L"App", v3) )
  {
    v13 = (_QWORD *)a1[2];
    if ( v13[3] > 7u )
      v13 = (_QWORD *)*v13;
    if ( (unsigned int)_o__wcsicmp(L"Device", v13) )
    {
      AslLogCallPrintf(
        1,
        "GetInventoryMatch::<lambda_257374e31fbb59fcfeb4011cad186f3a>::operator ()",
        220,
        "Invalid Inventory. Must be 'App' or 'Device'.");
      return 2147942487LL;
    }
    v4 = (const WCHAR **)(a1 + 3);
    v14 = a1[3];
    if ( *(_QWORD *)(v14 + 24) < 0xAu )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v14);
    }
    else
    {
      v15 = *(_WORD **)v14;
      *(_QWORD *)(v14 + 16) = 10;
      memmove_0(v15, L"devinv.dll", 0x14u);
      v15[10] = 0;
    }
    v8 = (const CHAR **)(a1 + 4);
    v9 = a1[4];
    if ( *(_QWORD *)(v9 + 24) >= 0xFu )
    {
      if ( *(_QWORD *)(v9 + 24) <= 0xFu )
        v10 = (_BYTE *)a1[4];
      else
        v10 = *(_BYTE **)v9;
      v11 = "GetDevInventory";
      goto LABEL_24;
    }
    v12 = "GetDevInventory";
LABEL_26:
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(v9, 15, v7, v12);
    goto LABEL_27;
  }
  v4 = (const WCHAR **)(a1 + 3);
  v5 = a1[3];
  if ( *(_QWORD *)(v5 + 24) < 9u )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v5);
  }
  else
  {
    v6 = *(_WORD **)v5;
    *(_QWORD *)(v5 + 16) = 9;
    memmove_0(v6, L"aeinv.dll", 0x12u);
    v6[9] = 0;
  }
  v8 = (const CHAR **)(a1 + 4);
  v9 = a1[4];
  if ( *(_QWORD *)(v9 + 24) < 0xFu )
  {
    v12 = "GetAppInventory";
    goto LABEL_26;
  }
  if ( *(_QWORD *)(v9 + 24) <= 0xFu )
    v10 = (_BYTE *)a1[4];
  else
    v10 = *(_BYTE **)v9;
  v11 = "GetAppInventory";
LABEL_24:
  *(_QWORD *)(v9 + 16) = 15;
  memmove_0(v10, v11, 0xFu);
  v10[15] = 0;
LABEL_27:
  v16 = *v4;
  if ( *((_QWORD *)*v4 + 3) > 7u )
    v16 = *(const WCHAR **)v16;
  *(_QWORD *)a1[5] = LoadLibraryExW(v16, 0, 0x800u);
  v17 = *(HMODULE *)a1[5];
  if ( !v17 )
  {
    LastError = GetLastError();
    v19 = *v4;
    if ( *((_QWORD *)*v4 + 3) > 7u )
      v19 = *(const WCHAR **)v19;
    v20 = "%ws could not be loaded. [0x%x]";
    v21 = 227;
LABEL_33:
    v54 = LastError;
    AslLogCallPrintf(1, "GetInventoryMatch::<lambda_257374e31fbb59fcfeb4011cad186f3a>::operator ()", v21, v20, v19, v54);
    return 2147500037LL;
  }
  v23 = *v8;
  if ( *((_QWORD *)*v8 + 3) > 0xFu )
    v23 = *(const CHAR **)v23;
  *(_QWORD *)a1[6] = GetProcAddress(v17, v23);
  v24 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))a1[6];
  if ( !v24 )
  {
    LastError = GetLastError();
    v19 = (const WCHAR *)*v8;
    if ( *((_QWORD *)*v8 + 3) > 0xFu )
      v19 = *(const WCHAR **)v19;
    v20 = "GetProcAddress %s failed. [0x%x]";
    v21 = 235;
    goto LABEL_33;
  }
  *(_DWORD *)a1[7] = v24(a1[8], *a1, 0);
  if ( *(int *)a1[7] < 0 )
  {
    v25 = *v8;
    if ( *((_QWORD *)*v8 + 3) > 0xFu )
      v25 = *(const CHAR **)v25;
    v55 = *(_DWORD *)a1[7];
    AslLogCallPrintf(
      1,
      "GetInventoryMatch::<lambda_257374e31fbb59fcfeb4011cad186f3a>::operator ()",
      245,
      "%s failed. [0x%x]",
      v25,
      v55);
    return 2147500037LL;
  }
  v26 = a1[8];
  v27 = *(_QWORD *)(v26 + 64);
  if ( v27 == *(_QWORD *)(v26 + 72) )
  {
    v28 = (_QWORD *)a1[9];
    if ( v28[3] > 7u )
      v28 = (_QWORD *)*v28;
    AslLogCallPrintf(
      3,
      "GetInventoryMatch::<lambda_257374e31fbb59fcfeb4011cad186f3a>::operator ()",
      253,
      "No items of asset type '%ls' were found in the Inventory.",
      v28);
  }
  else
  {
    for ( *(_QWORD *)a1[10] = v27; *(_QWORD *)a1[10] != *(_QWORD *)(v26 + 72); *(_QWORD *)a1[10] += 16LL )
    {
      *(_DWORD *)a1[11] = 0;
      for ( i = 0; i < *(_QWORD *)a1[12]; ++i )
      {
        v30 = 32 * i;
        v31 = *(_QWORD *)(*(_QWORD *)a1[14] + 32 * i + 8);
        v62 = 0;
        v63 = 0;
        v32 = -1;
        do
          ++v32;
        while ( *(_WORD *)(v31 + 2 * v32) );
        std::wstring::_Construct<1,unsigned short const *>(&v62, v31, v32);
        v33 = *(_QWORD *)(*(_QWORD *)a1[14] + v30 + 16);
        v60 = 0;
        v61 = 0;
        v34 = -1;
        do
          ++v34;
        while ( *(_WORD *)(v33 + 2 * v34) );
        std::wstring::_Construct<1,unsigned short const *>(&v60, v33, v34);
        v35 = *(_QWORD *)(*(_QWORD *)a1[14] + v30 + 24);
        v56 = 0;
        v57 = 0;
        v36 = -1;
        do
          ++v36;
        while ( *(_WORD *)(v35 + 2 * v36) );
        std::wstring::_Construct<1,unsigned short const *>(&v56, v35, v36);
        v37 = *(_QWORD *)a1[10];
        v38 = *(_QWORD *)(v30 + *(_QWORD *)a1[14]);
        Src = 0;
        v59 = 0;
        v39 = -1;
        do
          ++v39;
        while ( *(_WORD *)(v38 + 2 * v39) );
        std::wstring::_Construct<1,unsigned short const *>(&Src, v38, v39);
        v40 = std::map<std::wstring,std::wstring>::operator[](v37, &Src);
        v41 = (_DWORD *)a1[7];
        *v41 = AppCompatUtility::CompareStrEx(a1[13], v40, &v56, &v60, &v62);
        std::wstring::~wstring(&Src);
        std::wstring::~wstring(&v56);
        std::wstring::~wstring(&v60);
        std::wstring::~wstring(&v62);
        if ( *(_DWORD *)a1[7] )
          break;
        if ( !*(_DWORD *)a1[13] )
          break;
        ++*(_DWORD *)a1[11];
      }
      if ( *(_DWORD *)a1[11] == *(_QWORD *)a1[12] )
      {
        **(_DWORD **)a1[15] = 1;
        v42 = a1[16];
        if ( *(_QWORD *)(v42 + 24) <= 7u )
          v43 = (_WORD *)a1[16];
        else
          v43 = *(_WORD **)v42;
        *(_QWORD *)(v42 + 16) = 0;
        *v43 = 0;
        for ( j = 0; j < *(_QWORD *)a1[12]; ++j )
        {
          v45 = *(_QWORD *)a1[10];
          v46 = *(_QWORD *)(32 * j + *(_QWORD *)a1[14]);
          v60 = 0;
          v61 = 0;
          v47 = -1;
          do
            ++v47;
          while ( *(_WORD *)(v46 + 2 * v47) );
          std::wstring::_Construct<1,unsigned short const *>(&v60, v46, v47);
          std::map<std::wstring,std::wstring>::operator[](v45, &v60);
          v48 = *(_QWORD *)(32 * j + *(_QWORD *)a1[14]);
          v62 = 0;
          v63 = 0;
          v49 = -1;
          do
            ++v49;
          while ( *(_WORD *)(v48 + 2 * v49) );
          std::wstring::_Construct<1,unsigned short const *>(&v62, v48, v49);
          v50 = std::wstring::append(&v62, L": '");
          Src = 0;
          v59 = 0;
          Src = *(_OWORD *)v50;
          v59 = *(_OWORD *)(v50 + 16);
          *(_QWORD *)(v50 + 16) = 0;
          *(_QWORD *)(v50 + 24) = 7;
          *(_WORD *)v50 = 0;
          v51 = std::wstring::append(&Src);
          v56 = 0;
          v57 = 0;
          v56 = *(_OWORD *)v51;
          v57 = *(_OWORD *)(v51 + 16);
          *(_QWORD *)(v51 + 16) = 0;
          *(_QWORD *)(v51 + 24) = 7;
          *(_WORD *)v51 = 0;
          v52 = std::wstring::append(&v56, L"'\n");
          v64[0] = *(_OWORD *)v52;
          v64[1] = *(_OWORD *)(v52 + 16);
          *(_QWORD *)(v52 + 16) = 0;
          *(_QWORD *)(v52 + 24) = 7;
          *(_WORD *)v52 = 0;
          std::wstring::append((void *)a1[16]);
          std::wstring::~wstring(v64);
          std::wstring::~wstring(&v56);
          std::wstring::~wstring(&Src);
          std::wstring::~wstring(&v62);
          std::wstring::~wstring(&v60);
        }
        v53 = (_QWORD *)a1[16];
        if ( v53[3] > 7u )
          v53 = (_QWORD *)*v53;
        AslLogCallPrintf(
          3,
          "GetInventoryMatch::<lambda_257374e31fbb59fcfeb4011cad186f3a>::operator ()",
          292,
          "Found a match that meets all conditions:\n%ls",
          v53);
        return 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180020680  push    rbp
0x180020682  push    rbx
0x180020683  push    rsi
0x180020684  push    rdi
0x180020685  push    r12
0x180020687  push    r13
0x180020689  push    r14
0x18002068b  push    r15
0x18002068d  lea     rbp, [rsp-1Fh]
0x180020692  sub     rsp, 0F8h
0x180020699  mov     [rsp+130h+var_F8], 0FFFFFFFFFFFFFFFEh
0x1800206a2  mov     rax, cs:__security_cookie
0x1800206a9  xor     rax, rsp
0x1800206ac  mov     [rbp+57h+var_50], rax
0x1800206b0  mov     rdi, rcx
0x1800206b3  xor     r12d, r12d
0x1800206b6  xorps   xmm0, xmm0
0x1800206b9  mov     rax, [rcx]
0x1800206bc  movups  xmmword ptr [rax], xmm0
0x1800206bf  movups  xmmword ptr [rax+10h], xmm0
0x1800206c3  mov     rax, [rcx]
0x1800206c6  mov     qword ptr [rax], 20h ; ' '
0x1800206cd  mov     rax, [rcx+8]
0x1800206d1  mov     rcx, [rcx]
0x1800206d4  mov     eax, [rax]
0x1800206d6  mov     [rcx+10h], eax
0x1800206d9  mov     rdx, [rdi+10h]
0x1800206dd  lea     r13d, [r12+7]
0x1800206e2  cmp     [rdx+18h], r13
0x1800206e6  jbe     short loc_1800206EB
0x1800206e8  mov     rdx, [rdx]
0x1800206eb  lea     rcx, aApp; "App"
0x1800206f2  call    cs:__imp__o__wcsicmp
0x1800206f8  test    eax, eax
0x1800206fa  jnz     short loc_18002076D
0x1800206fc  lea     r14, [rdi+18h]
0x180020700  mov     rcx, [r14]
0x180020703  lea     edx, [rax+9]
0x180020706  cmp     [rcx+18h], rdx
0x18002070a  jb      short loc_18002072D
0x18002070c  mov     rbx, [rcx]
0x18002070f  mov     [rcx+10h], rdx
0x180020713  lea     r8d, [rax+12h]; Size
0x180020717  lea     rdx, aAeinvDll; "aeinv.dll"
0x18002071e  mov     rcx, rbx; void *
0x180020721  call    memmove_0
0x180020726  mov     [rbx+12h], r12w
0x18002072b  jmp     short loc_180020739
0x18002072d  lea     r9, aAeinvDll; "aeinv.dll"
0x180020734  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180020739  lea     rsi, [rdi+20h]
0x18002073d  mov     rcx, [rsi]
0x180020740  mov     ebx, 0Fh
0x180020745  cmp     [rcx+18h], rbx
0x180020749  jb      short loc_180020761
0x18002074b  jbe     short loc_180020752
0x18002074d  mov     r15, [rcx]
0x180020750  jmp     short loc_180020755
0x180020752  mov     r15, rcx
0x180020755  lea     rdx, aGetappinventor; "GetAppInventory"
0x18002075c  jmp     loc_1800207EF
0x180020761  lea     r9, aGetappinventor; "GetAppInventory"
0x180020768  jmp     loc_18002080B
0x18002076d  mov     rdx, [rdi+10h]
0x180020771  cmp     [rdx+18h], r13
0x180020775  jbe     short loc_18002077A
0x180020777  mov     rdx, [rdx]
0x18002077a  lea     rcx, aDevice; "Device"
0x180020781  call    cs:__imp__o__wcsicmp
0x180020787  test    eax, eax
0x180020789  jnz     loc_180020CD1
0x18002078f  lea     r14, [rdi+18h]
0x180020793  mov     rcx, [r14]
0x180020796  lea     edx, [rax+0Ah]
0x180020799  cmp     [rcx+18h], rdx
0x18002079d  jb      short loc_1800207C0
0x18002079f  mov     rbx, [rcx]
0x1800207a2  mov     [rcx+10h], rdx
0x1800207a6  lea     r8d, [rax+14h]; Size
0x1800207aa  lea     rdx, Src; "devinv.dll"
0x1800207b1  mov     rcx, rbx; void *
0x1800207b4  call    memmove_0
0x1800207b9  mov     [rbx+14h], r12w
0x1800207be  jmp     short loc_1800207CC
0x1800207c0  lea     r9, Src; "devinv.dll"
0x1800207c7  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800207cc  lea     rsi, [rdi+20h]
0x1800207d0  mov     rcx, [rsi]
0x1800207d3  mov     ebx, 0Fh
0x1800207d8  cmp     [rcx+18h], rbx
0x1800207dc  jb      short loc_180020804
0x1800207de  jbe     short loc_1800207E5
0x1800207e0  mov     r15, [rcx]
0x1800207e3  jmp     short loc_1800207E8
0x1800207e5  mov     r15, rcx
0x1800207e8  lea     rdx, aGetdevinventor_0; "GetDevInventory"
0x1800207ef  mov     r8, rbx; Size
0x1800207f2  mov     [rcx+10h], rbx
0x1800207f6  mov     rcx, r15; void *
0x1800207f9  call    memmove_0
0x1800207fe  mov     [r15+0Fh], r12b
0x180020802  jmp     short loc_180020813
0x180020804  lea     r9, aGetdevinventor_0; "GetDevInventory"
0x18002080b  mov     rdx, rbx
0x18002080e  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x180020813  mov     rcx, [r14]
0x180020816  cmp     [rcx+18h], r13
0x18002081a  jbe     short loc_18002081F
0x18002081c  mov     rcx, [rcx]; lpLibFileName
0x18002081f  xor     edx, edx; hFile
0x180020821  mov     r8d, 800h; dwFlags
0x180020827  call    cs:__imp_LoadLibraryExW
0x18002082d  mov     rcx, [rdi+28h]
0x180020831  mov     [rcx], rax
0x180020834  mov     rax, [rdi+28h]
0x180020838  mov     rcx, [rax]; hModule
0x18002083b  test    rcx, rcx
0x18002083e  jnz     short loc_180020883
0x180020840  call    cs:__imp_GetLastError
0x180020846  mov     rcx, [r14]
0x180020849  cmp     [rcx+18h], r13
0x18002084d  jbe     short loc_180020852
0x18002084f  mov     rcx, [rcx]
0x180020852  lea     r9, aWsCouldNotBeLo; "%ws could not be loaded. [0x%x]"
0x180020859  mov     r8d, 0E3h
0x18002085f  mov     [rsp+130h+var_108], eax
0x180020863  mov     [rsp+130h+var_110], rcx
0x180020868  lea     rdx, aGetinventoryma; "GetInventoryMatch::<lambda_257374e31fbb"...
0x18002086f  mov     ecx, 1
0x180020874  call    AslLogCallPrintf
0x180020879  mov     eax, 80004005h
0x18002087e  jmp     loc_180020CF4
0x180020883  mov     rdx, [rsi]
0x180020886  cmp     [rdx+18h], rbx
0x18002088a  jbe     short loc_18002088F
0x18002088c  mov     rdx, [rdx]; lpProcName
0x18002088f  call    cs:__imp_GetProcAddress
0x180020895  mov     rcx, [rdi+30h]
0x180020899  mov     [rcx], rax
0x18002089c  mov     rax, [rdi+30h]
0x1800208a0  mov     rax, [rax]
0x1800208a3  test    rax, rax
0x1800208a6  jnz     short loc_1800208C9
0x1800208a8  call    cs:__imp_GetLastError
0x1800208ae  mov     rcx, [rsi]
0x1800208b1  cmp     [rcx+18h], rbx
0x1800208b5  jbe     short loc_1800208BA
0x1800208b7  mov     rcx, [rcx]
0x1800208ba  lea     r9, aGetprocaddress_0; "GetProcAddress %s failed. [0x%x]"
0x1800208c1  mov     r8d, 0EBh
0x1800208c7  jmp     short loc_18002085F
0x1800208c9  xor     r8d, r8d
0x1800208cc  mov     rdx, [rdi]
0x1800208cf  mov     rcx, [rdi+40h]
0x1800208d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208d8  mov     rcx, [rdi+38h]
0x1800208dc  mov     [rcx], eax
0x1800208de  mov     rax, [rdi+38h]
0x1800208e2  mov     ecx, [rax]
0x1800208e4  test    ecx, ecx
0x1800208e6  jns     short loc_18002090F
0x1800208e8  mov     rax, [rsi]
0x1800208eb  cmp     [rax+18h], rbx
0x1800208ef  jbe     short loc_1800208F4
0x1800208f1  mov     rax, [rax]
0x1800208f4  mov     [rsp+130h+var_108], ecx
0x1800208f8  mov     [rsp+130h+var_110], rax
0x1800208fd  lea     r9, aSFailed0xX; "%s failed. [0x%x]"
0x180020904  mov     r8d, 0F5h
0x18002090a  jmp     loc_180020868
0x18002090f  mov     rsi, [rdi+40h]
0x180020913  mov     rcx, [rsi+40h]
0x180020917  cmp     rcx, [rsi+48h]
0x18002091b  jnz     short loc_180020954
0x18002091d  mov     rax, [rdi+48h]
0x180020921  cmp     [rax+18h], r13
0x180020925  jbe     short loc_18002092A
0x180020927  mov     rax, [rax]
0x18002092a  lea     r9, aNoItemsOfAsset; "No items of asset type '%ls' were found"...
0x180020931  mov     r8d, 0FDh
0x180020937  mov     [rsp+130h+var_110], rax
0x18002093c  lea     rdx, aGetinventoryma; "GetInventoryMatch::<lambda_257374e31fbb"...
0x180020943  mov     ecx, 3
0x180020948  call    AslLogCallPrintf
0x18002094d  xor     eax, eax
0x18002094f  jmp     loc_180020CF4
0x180020954  mov     rax, [rdi+50h]
0x180020958  mov     [rax], rcx
0x18002095b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002095f  mov     rcx, [rdi+50h]
0x180020963  mov     rax, [rsi+48h]
0x180020967  cmp     [rcx], rax
0x18002096a  jz      short loc_18002094D
0x18002096c  mov     rax, [rdi+58h]
0x180020970  mov     [rax], r12d
0x180020973  mov     r14, r12
0x180020976  mov     rax, [rdi+60h]
0x18002097a  cmp     [rax], r12
0x18002097d  jbe     loc_180020AE7
0x180020983  mov     rbx, r14
0x180020986  shl     rbx, 5
0x18002098a  mov     rax, [rdi+70h]
0x18002098e  mov     rcx, [rax]
0x180020991  mov     rdx, [rcx+rbx+8]
0x180020996  xorps   xmm0, xmm0
0x180020999  movups  [rbp+57h+var_90], xmm0
0x18002099d  xorps   xmm1, xmm1
0x1800209a0  movdqu  [rbp+57h+var_80], xmm1
0x1800209a5  mov     r8, r15
0x1800209a8  inc     r8
0x1800209ab  cmp     [rdx+r8*2], r12w
0x1800209b0  jnz     short loc_1800209A8
0x1800209b2  lea     rcx, [rbp+57h+var_90]
0x1800209b6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800209bb  nop
0x1800209bc  mov     rax, [rdi+70h]
0x1800209c0  mov     rcx, [rax]
0x1800209c3  mov     rdx, [rcx+rbx+10h]
0x1800209c8  xorps   xmm0, xmm0
0x1800209cb  movups  [rbp+57h+var_B0], xmm0
0x1800209cf  xorps   xmm1, xmm1
0x1800209d2  movdqu  [rbp+57h+var_A0], xmm1
0x1800209d7  mov     r8, r15
0x1800209da  inc     r8
0x1800209dd  cmp     [rdx+r8*2], r12w
0x1800209e2  jnz     short loc_1800209DA
0x1800209e4  lea     rcx, [rbp+57h+var_B0]
0x1800209e8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800209ed  nop
0x1800209ee  mov     rax, [rdi+70h]
0x1800209f2  mov     rcx, [rax]
0x1800209f5  mov     rdx, [rcx+rbx+18h]
0x1800209fa  xorps   xmm0, xmm0
0x1800209fd  movups  [rsp+130h+var_F0], xmm0
0x180020a02  xorps   xmm1, xmm1
0x180020a05  movdqu  [rsp+130h+var_E0], xmm1
0x180020a0b  mov     r8, r15
0x180020a0e  inc     r8
0x180020a11  cmp     [rdx+r8*2], r12w
0x180020a16  jnz     short loc_180020A0E
0x180020a18  lea     rcx, [rsp+130h+var_F0]
0x180020a1d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180020a22  nop
0x180020a23  mov     rax, [rdi+50h]
0x180020a27  mov     r15, [rax]
0x180020a2a  mov     rax, [rdi+70h]
0x180020a2e  mov     rcx, [rax]
0x180020a31  mov     rdx, [rbx+rcx]
0x180020a35  xorps   xmm0, xmm0
0x180020a38  movups  [rbp+57h+Src], xmm0
0x180020a3c  xorps   xmm1, xmm1
0x180020a3f  movdqu  [rbp+57h+var_C0], xmm1
0x180020a44  or      r8, 0FFFFFFFFFFFFFFFFh
0x180020a48  inc     r8
0x180020a4b  cmp     [rdx+r8*2], r12w
0x180020a50  jnz     short loc_180020A48
0x180020a52  lea     rcx, [rbp+57h+Src]
0x180020a56  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180020a5b  nop
0x180020a5c  lea     rdx, [rbp+57h+Src]
0x180020a60  mov     rcx, r15
0x180020a63  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180020a68  mov     rbx, [rdi+38h]
0x180020a6c  lea     rcx, [rbp+57h+var_90]
0x180020a70  mov     [rsp+130h+var_110], rcx
0x180020a75  lea     r9, [rbp+57h+var_B0]
0x180020a79  lea     r8, [rsp+130h+var_F0]
0x180020a7e  mov     rdx, rax
0x180020a81  mov     rcx, [rdi+68h]
0x180020a85  call    ?CompareStrEx@AppCompatUtility@@YAJPEAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; AppCompatUtility::CompareStrEx(int *,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x180020a8a  mov     [rbx], eax
0x180020a8c  lea     rcx, [rbp+57h+Src]; void *
0x180020a90  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020a95  nop
0x180020a96  lea     rcx, [rsp+130h+var_F0]; void *
0x180020a9b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020aa0  nop
0x180020aa1  lea     rcx, [rbp+57h+var_B0]; void *
0x180020aa5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020aaa  nop
0x180020aab  lea     rcx, [rbp+57h+var_90]; void *
0x180020aaf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020ab4  mov     rax, [rdi+38h]
0x180020ab8  cmp     [rax], r12d
0x180020abb  jnz     short loc_180020AE3
0x180020abd  mov     rax, [rdi+68h]
0x180020ac1  cmp     [rax], r12d
0x180020ac4  jz      short loc_180020AE3
0x180020ac6  mov     rax, [rdi+58h]
0x180020aca  inc     dword ptr [rax]
0x180020acc  inc     r14
0x180020acf  mov     rax, [rdi+60h]
0x180020ad3  cmp     r14, [rax]
0x180020ad6  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180020add  jb      loc_180020983
0x180020ae3  or      r15, 0FFFFFFFFFFFFFFFFh
0x180020ae7  mov     rax, [rdi+58h]
0x180020aeb  mov     ecx, [rax]
0x180020aed  mov     rax, [rdi+60h]
0x180020af1  cmp     rcx, [rax]
  ... truncated ...
```
