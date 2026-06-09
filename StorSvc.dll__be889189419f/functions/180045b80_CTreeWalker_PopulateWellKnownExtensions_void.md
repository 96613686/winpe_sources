# CTreeWalker::PopulateWellKnownExtensions(void)

- ea: `0x180045b80`
- end: `0x180046176`
- name: `?PopulateWellKnownExtensions@CTreeWalker@@QEAAXXZ`
- size: `1526`
- prototype: `void __fastcall(CTreeWalker *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180040da4`

## callees

- `0x18000d030`
- `0x18000ddb0`
- `0x18001c208`
- `0x18001f634`
- `0x180043e38`
- `0x180045b80`
- `0x18007d4e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800460cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800460cd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180046145`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180046145`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180045faa`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180045faa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046101`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046101`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004602a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004602a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180045f8d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180045f8d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045fea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045fea`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180046134`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180046134`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTreeWalker::PopulateWellKnownExtensions(CTreeWalker *this)
{
  unsigned int v2; // edi
  char *v3; // rsi
  __int64 v4; // rax
  unsigned int i; // ebx
  __int64 v6; // rax
  unsigned int j; // ebx
  __int64 v8; // rax
  unsigned int k; // ebx
  __int64 v10; // rax
  unsigned int m; // ebx
  __int64 v12; // rax
  void *v13; // rbx
  int v14; // r14d
  DWORD n; // edx
  char v16; // dl
  __int16 v17; // r8
  int v18; // r9d
  int v19; // edi
  __int64 v20; // rax
  wchar_t lpcSubKeys; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v28[3]; // [rsp+78h] [rbp-88h]
  _QWORD v29[10]; // [rsp+90h] [rbp-70h]
  _QWORD v30[10]; // [rsp+E0h] [rbp-20h]
  _QWORD v31[14]; // [rsp+130h] [rbp+30h]
  _QWORD v32[14]; // [rsp+1A0h] [rbp+A0h]
  BYTE v33[32]; // [rsp+210h] [rbp+110h] BYREF
  wchar_t Data[264]; // [rsp+230h] [rbp+130h] BYREF

  cbMaxSubKeyLen = 0;
  cchName = 0;
  Type = 0;
  cbData = 0;
  memset_0(Data, 0, 0x208u);
  phkResult = 0;
  v29[0] = L".doc";
  v29[1] = L".docx";
  v29[2] = L".pdf";
  v29[3] = L".log";
  v29[4] = L".rtf";
  v29[5] = L".txt";
  v29[6] = L".ppt";
  v29[7] = L".pptx";
  v29[8] = L".xls";
  v29[9] = L".xlsx";
  v31[0] = L".avi";
  v31[1] = L".mov";
  v31[2] = L".mpg";
  v31[3] = L".swf";
  v31[4] = L".vob";
  v31[5] = L".wmv";
  v31[6] = L".mp4";
  v31[7] = L".mkv";
  v31[8] = L".asf";
  v31[9] = L".flv";
  v31[10] = L".m4v";
  v31[11] = L".vob";
  v31[12] = L".swf";
  v32[0] = L".jpg";
  v32[1] = L".gif";
  v32[2] = L".bmp";
  v32[3] = L".psd";
  v32[4] = L".tga";
  v32[5] = L".tif";
  v32[6] = L".tiff";
  v32[7] = L".png";
  v32[8] = L".jpeg";
  v32[9] = L".raw";
  v32[10] = L".ai";
  v32[11] = L".eps";
  v32[12] = L".svg";
  v30[0] = L".mp3";
  v30[1] = L".wma";
  v30[2] = L".flac";
  v30[3] = L".aac";
  v30[4] = L".m4a";
  v30[5] = L".wav";
  v30[6] = L".3gp";
  v30[7] = L".aiff";
  v30[8] = L".m4p";
  v30[9] = L".ogg";
  v28[0] = L".pst";
  v28[1] = L".eml";
  v2 = 0;
  v3 = (char *)this + 184;
  do
  {
    v4 = std::wstring::wstring((__int64)v33, v29[v2]);
    *(_DWORD *)std::unordered_map<std::wstring,int>::operator[](v3, v4) = 9;
    std::wstring::_Tidy_deallocate(v33);
    ++v2;
  }
  while ( v2 < 0xA );
  for ( i = 0; i < 0xD; ++i )
  {
    v6 = std::wstring::wstring((__int64)v33, v31[i]);
    *(_DWORD *)std::unordered_map<std::wstring,int>::operator[](v3, v6) = 4;
    std::wstring::_Tidy_deallocate(v33);
  }
  for ( j = 0; j < 0xD; ++j )
  {
    v8 = std::wstring::wstring((__int64)v33, v32[j]);
    *(_DWORD *)std::unordered_map<std::wstring,int>::operator[](v3, v8) = 3;
    std::wstring::_Tidy_deallocate(v33);
  }
  for ( k = 0; k < 0xA; ++k )
  {
    v10 = std::wstring::wstring((__int64)v33, v30[k]);
    *(_DWORD *)std::unordered_map<std::wstring,int>::operator[](v3, v10) = 2;
    std::wstring::_Tidy_deallocate(v33);
  }
  for ( m = 0; m < 2; ++m )
  {
    v12 = std::wstring::wstring((__int64)v33, v28[m]);
    *(_DWORD *)std::unordered_map<std::wstring,int>::operator[](v3, v12) = 12;
    std::wstring::_Tidy_deallocate(v33);
  }
  if ( !RegQueryInfoKeyW(HKEY_CLASSES_ROOT, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0) )
  {
    v13 = malloc(2LL * ++cbMaxSubKeyLen);
    if ( v13 )
    {
      cchName = cbMaxSubKeyLen;
      v14 = 1;
      for ( n = 0; ; n = v14++ )
      {
        if ( RegEnumKeyExW(HKEY_CLASSES_ROOT, n, (LPWSTR)v13, &cchName, 0, 0, 0, 0) )
        {
          free(v13);
          return;
        }
        if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, (LPCWSTR)v13, 0, 0x20019u, &phkResult) )
          break;
LABEL_28:
        cchName = cbMaxSubKeyLen;
      }
      cbData = 260;
      if ( !RegQueryValueExW(phkResult, L"PerceivedType", 0, &Type, (LPBYTE)Data, &cbData) && Type == 1 )
      {
        if ( !wcscmp_0(Data, L"text") )
          goto LABEL_25;
        if ( !wcscmp_0(Data, L"image") )
        {
          v19 = 3;
LABEL_26:
          o((wchar_t)v13, v16, v17, v18, lpcSubKeys, *(long double *)&lpcbMaxSubKeyLen);
          v20 = std::wstring::wstring((__int64)v33, (__int64)v13);
          *(_DWORD *)std::unordered_map<std::wstring,int>::operator[](v3, v20) = v19;
          std::wstring::_Tidy_deallocate(v33);
          goto LABEL_27;
        }
        if ( !wcscmp_0(Data, L"audio") )
        {
          v19 = 2;
          goto LABEL_26;
        }
        if ( !wcscmp_0(Data, L"video") )
        {
          v19 = 4;
          goto LABEL_26;
        }
        if ( !wcscmp_0(Data, L"document") )
        {
LABEL_25:
          v19 = 9;
          goto LABEL_26;
        }
      }
LABEL_27:
      RegCloseKey(phkResult);
      goto LABEL_28;
    }
  }
}

```

## disassembly

```asm
0x180045b80  mov     [rsp-8+arg_8], rbx
0x180045b85  mov     [rsp-8+arg_10], rsi
0x180045b8a  push    rbp
0x180045b8b  push    rdi
0x180045b8c  push    r13
0x180045b8e  push    r14
0x180045b90  push    r15
0x180045b92  lea     rbp, [rsp-350h]
0x180045b9a  sub     rsp, 450h
0x180045ba1  mov     rax, cs:__security_cookie
0x180045ba8  xor     rax, rsp
0x180045bab  mov     [rbp+370h+var_30], rax
0x180045bb2  mov     rsi, rcx
0x180045bb5  xor     r15d, r15d
0x180045bb8  mov     [rsp+470h+cbMaxSubKeyLen], r15d
0x180045bbd  mov     [rsp+470h+cchName], r15d
0x180045bc2  mov     [rsp+470h+Type], r15d
0x180045bc7  mov     [rsp+470h+cbData], r15d
0x180045bcc  xor     edx, edx; Val
0x180045bce  mov     r8d, 208h; Size
0x180045bd4  lea     rcx, [rbp+370h+Data]; void *
0x180045bdb  call    memset_0
0x180045be0  mov     [rsp+470h+phkResult], r15
0x180045be5  lea     rax, aDoc; ".doc"
0x180045bec  mov     [rbp+370h+var_3E0], rax
0x180045bf0  lea     rax, aDocx; ".docx"
0x180045bf7  mov     [rbp+370h+var_3D8], rax
0x180045bfb  lea     rax, aPdf; ".pdf"
0x180045c02  mov     [rbp+370h+var_3D0], rax
0x180045c06  lea     rax, aLog; ".log"
0x180045c0d  mov     [rbp+370h+var_3C8], rax
0x180045c11  lea     rax, aRtf; ".rtf"
0x180045c18  mov     [rbp+370h+var_3C0], rax
0x180045c1c  lea     rax, aTxt; ".txt"
0x180045c23  mov     [rbp+370h+var_3B8], rax
0x180045c27  lea     rax, aPpt; ".ppt"
0x180045c2e  mov     [rbp+370h+var_3B0], rax
0x180045c32  lea     rax, aPptx; ".pptx"
0x180045c39  mov     [rbp+370h+var_3A8], rax
0x180045c3d  lea     rax, aXls; ".xls"
0x180045c44  mov     [rbp+370h+var_3A0], rax
0x180045c48  lea     rax, aXlsx; ".xlsx"
0x180045c4f  mov     [rbp+370h+var_398], rax
0x180045c53  lea     rax, aAvi; ".avi"
0x180045c5a  mov     [rbp+370h+var_340], rax
0x180045c5e  lea     rax, aMov; ".mov"
0x180045c65  mov     [rbp+370h+var_338], rax
0x180045c69  lea     rax, aMpg; ".mpg"
0x180045c70  mov     [rbp+370h+var_330], rax
0x180045c74  lea     rdx, aSwf; ".swf"
0x180045c7b  mov     [rbp+370h+var_328], rdx
0x180045c7f  lea     rcx, aVob; ".vob"
0x180045c86  mov     [rbp+370h+var_320], rcx
0x180045c8a  lea     rax, aWmv; ".wmv"
0x180045c91  mov     [rbp+370h+var_318], rax
0x180045c95  lea     rax, aMp4; ".mp4"
0x180045c9c  mov     [rbp+370h+var_310], rax
0x180045ca0  lea     rax, aMkv; ".mkv"
0x180045ca7  mov     [rbp+370h+var_308], rax
0x180045cab  lea     rax, aAsf; ".asf"
0x180045cb2  mov     [rbp+370h+var_300], rax
0x180045cb6  lea     rax, aFlv; ".flv"
0x180045cbd  mov     [rbp+370h+var_2F8], rax
0x180045cc1  lea     rax, aM4v; ".m4v"
0x180045cc8  mov     [rbp+370h+var_2F0], rax
0x180045ccf  mov     [rbp+370h+var_2E8], rcx
0x180045cd6  mov     [rbp+370h+var_2E0], rdx
0x180045cdd  lea     rax, aJpg; ".jpg"
0x180045ce4  mov     [rbp+370h+var_2D0], rax
0x180045ceb  lea     rax, aGif; ".gif"
0x180045cf2  mov     [rbp+370h+var_2C8], rax
0x180045cf9  lea     rax, aBmp; ".bmp"
0x180045d00  mov     [rbp+370h+var_2C0], rax
0x180045d07  lea     rax, aPsd; ".psd"
0x180045d0e  mov     [rbp+370h+var_2B8], rax
0x180045d15  lea     rax, aTga; ".tga"
0x180045d1c  mov     [rbp+370h+var_2B0], rax
0x180045d23  lea     rax, aTif; ".tif"
0x180045d2a  mov     [rbp+370h+var_2A8], rax
0x180045d31  lea     rax, aTiff; ".tiff"
0x180045d38  mov     [rbp+370h+var_2A0], rax
0x180045d3f  lea     rax, aPng; ".png"
0x180045d46  mov     [rbp+370h+var_298], rax
0x180045d4d  lea     rax, aJpeg; ".jpeg"
0x180045d54  mov     [rbp+370h+var_290], rax
0x180045d5b  lea     rax, aRaw_0; ".raw"
0x180045d62  mov     [rbp+370h+var_288], rax
0x180045d69  lea     rax, aAi; ".ai"
0x180045d70  mov     [rbp+370h+var_280], rax
0x180045d77  lea     rax, aEps; ".eps"
0x180045d7e  mov     [rbp+370h+var_278], rax
0x180045d85  lea     rax, aSvg; ".svg"
0x180045d8c  mov     [rbp+370h+var_270], rax
0x180045d93  lea     rax, aMp3; ".mp3"
0x180045d9a  mov     [rbp+370h+var_390], rax
0x180045d9e  lea     rax, aWma; ".wma"
0x180045da5  mov     [rbp+370h+var_388], rax
0x180045da9  lea     rax, aFlac; ".flac"
0x180045db0  mov     [rbp+370h+var_380], rax
0x180045db4  lea     rax, aAac; ".aac"
0x180045dbb  mov     [rbp+370h+var_378], rax
0x180045dbf  lea     rax, aM4a; ".m4a"
0x180045dc6  mov     [rbp+370h+var_370], rax
0x180045dca  lea     rax, aWav; ".wav"
0x180045dd1  mov     [rbp+370h+var_368], rax
0x180045dd5  lea     rax, a3gp; ".3gp"
0x180045ddc  mov     [rbp+370h+var_360], rax
0x180045de0  lea     rax, aAiff; ".aiff"
0x180045de7  mov     [rbp+370h+var_358], rax
0x180045deb  lea     rax, aM4p; ".m4p"
0x180045df2  mov     [rbp+370h+var_350], rax
0x180045df6  lea     rax, aOgg; ".ogg"
0x180045dfd  mov     [rbp+370h+var_348], rax
0x180045e01  lea     rax, aPst; ".pst"
0x180045e08  mov     [rsp+470h+var_3F8], rax
0x180045e0d  lea     rax, aEml; ".eml"
0x180045e14  mov     [rbp+370h+var_3F0], rax
0x180045e18  mov     edi, r15d
0x180045e1b  add     rsi, 0B8h
0x180045e22  movsxd  rdx, edi
0x180045e25  mov     rdx, [rbp+rdx*8+370h+var_3E0]
0x180045e2a  lea     rcx, [rbp+370h+var_260]
0x180045e31  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180045e36  nop
0x180045e37  mov     rdx, rax
0x180045e3a  mov     rcx, rsi
0x180045e3d  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HU?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@@std@@QEAAAEAH$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,int>::operator[](std::wstring &&)
0x180045e42  mov     dword ptr [rax], 9
0x180045e48  lea     rcx, [rbp+370h+var_260]
0x180045e4f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180045e54  inc     edi
0x180045e56  cmp     edi, 0Ah
0x180045e59  jb      short loc_180045E22
0x180045e5b  mov     ebx, r15d
0x180045e5e  movsxd  rdx, ebx
0x180045e61  mov     rdx, [rbp+rdx*8+370h+var_340]
0x180045e66  lea     rcx, [rbp+370h+var_260]
0x180045e6d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180045e72  nop
0x180045e73  mov     rdx, rax
0x180045e76  mov     rcx, rsi
0x180045e79  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HU?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@@std@@QEAAAEAH$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,int>::operator[](std::wstring &&)
0x180045e7e  mov     dword ptr [rax], 4
0x180045e84  lea     rcx, [rbp+370h+var_260]
0x180045e8b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180045e90  inc     ebx
0x180045e92  cmp     ebx, 0Dh
0x180045e95  jb      short loc_180045E5E
0x180045e97  mov     ebx, r15d
0x180045e9a  movsxd  rdx, ebx
0x180045e9d  mov     rdx, [rbp+rdx*8+370h+var_2D0]
0x180045ea5  lea     rcx, [rbp+370h+var_260]
0x180045eac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180045eb1  nop
0x180045eb2  mov     rdx, rax
0x180045eb5  mov     rcx, rsi
0x180045eb8  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HU?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@@std@@QEAAAEAH$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,int>::operator[](std::wstring &&)
0x180045ebd  mov     dword ptr [rax], 3
0x180045ec3  lea     rcx, [rbp+370h+var_260]
0x180045eca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180045ecf  inc     ebx
0x180045ed1  cmp     ebx, 0Dh
0x180045ed4  jb      short loc_180045E9A
0x180045ed6  mov     ebx, r15d
0x180045ed9  movsxd  rdx, ebx
0x180045edc  mov     rdx, [rbp+rdx*8+370h+var_390]
0x180045ee1  lea     rcx, [rbp+370h+var_260]
0x180045ee8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180045eed  nop
0x180045eee  mov     rdx, rax
0x180045ef1  mov     rcx, rsi
0x180045ef4  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HU?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@@std@@QEAAAEAH$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,int>::operator[](std::wstring &&)
0x180045ef9  mov     dword ptr [rax], 2
0x180045eff  lea     rcx, [rbp+370h+var_260]
0x180045f06  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180045f0b  inc     ebx
0x180045f0d  cmp     ebx, 0Ah
0x180045f10  jb      short loc_180045ED9
0x180045f12  mov     ebx, r15d
0x180045f15  movsxd  rdx, ebx
0x180045f18  mov     rdx, [rsp+rdx*8+470h+var_3F8]
0x180045f1d  lea     rcx, [rbp+370h+var_260]
0x180045f24  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180045f29  nop
0x180045f2a  mov     rdx, rax
0x180045f2d  mov     rcx, rsi
0x180045f30  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HU?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@@std@@QEAAAEAH$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,int>::operator[](std::wstring &&)
0x180045f35  mov     dword ptr [rax], 0Ch
0x180045f3b  lea     rcx, [rbp+370h+var_260]
0x180045f42  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180045f47  inc     ebx
0x180045f49  cmp     ebx, 2
0x180045f4c  jb      short loc_180045F15
0x180045f4e  mov     [rsp+470h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180045f53  mov     [rsp+470h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180045f58  mov     [rsp+470h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180045f5d  mov     [rsp+470h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180045f62  mov     [rsp+470h+lpcValues], r15; lpcValues
0x180045f67  mov     [rsp+470h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180045f6c  lea     rax, [rsp+470h+cbMaxSubKeyLen]
0x180045f71  mov     [rsp+470h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180045f76  mov     [rsp+470h+lpcSubKeys], r15; lpcSubKeys
0x180045f7b  xor     r9d, r9d; lpReserved
0x180045f7e  xor     r8d, r8d; lpcchClass
0x180045f81  xor     edx, edx; lpClass
0x180045f83  mov     r13, 0FFFFFFFF80000000h
0x180045f8a  mov     rcx, r13; hKey
0x180045f8d  call    cs:__imp_RegQueryInfoKeyW
0x180045f93  test    eax, eax
0x180045f95  jnz     loc_18004614B
0x180045f9b  mov     eax, [rsp+470h+cbMaxSubKeyLen]
0x180045f9f  inc     eax
0x180045fa1  mov     [rsp+470h+cbMaxSubKeyLen], eax
0x180045fa5  mov     ecx, eax
0x180045fa7  add     rcx, rcx; Size
0x180045faa  call    cs:__imp_malloc
0x180045fb0  mov     rbx, rax
0x180045fb3  test    rax, rax
0x180045fb6  jz      loc_18004614B
0x180045fbc  mov     ecx, [rsp+470h+cbMaxSubKeyLen]
0x180045fc0  mov     [rsp+470h+cchName], ecx
0x180045fc4  mov     r14d, 1
0x180045fca  xor     edx, edx
0x180045fcc  jmp     loc_180046115
0x180045fd1  lea     rax, [rsp+470h+phkResult]
0x180045fd6  mov     [rsp+470h+lpcSubKeys], rax; phkResult
0x180045fdb  mov     r9d, 20019h; samDesired
0x180045fe1  xor     r8d, r8d; ulOptions
0x180045fe4  mov     rdx, rbx; lpSubKey
0x180045fe7  mov     rcx, r13; hKey
0x180045fea  call    cs:__imp_RegOpenKeyExW
0x180045ff0  test    eax, eax
0x180045ff2  jnz     loc_180046107
0x180045ff8  mov     [rsp+470h+cbData], 104h
0x180046000  lea     rax, [rsp+470h+cbData]
0x180046005  mov     [rsp+470h+lpcbMaxSubKeyLen], rax; lpcbData
0x18004600a  lea     rax, [rbp+370h+Data]
0x180046011  mov     [rsp+470h+lpcSubKeys], rax; lpData
0x180046016  lea     r9, [rsp+470h+Type]; lpType
0x18004601b  xor     r8d, r8d; lpReserved
0x18004601e  lea     rdx, aPerceivedtype; "PerceivedType"
0x180046025  mov     rcx, [rsp+470h+phkResult]; hKey
0x18004602a  call    cs:__imp_RegQueryValueExW
0x180046030  test    eax, eax
0x180046032  jnz     loc_1800460FC
0x180046038  cmp     [rsp+470h+Type], 1
0x18004603d  jnz     loc_1800460FC
0x180046043  lea     rdx, aText; "text"
0x18004604a  lea     rcx, [rbp+370h+Data]; String1
0x180046051  call    wcscmp_0
0x180046056  test    eax, eax
0x180046058  jz      short loc_1800460C5
0x18004605a  lea     rdx, aImage; "image"
0x180046061  lea     rcx, [rbp+370h+Data]; String1
0x180046068  call    wcscmp_0
0x18004606d  test    eax, eax
0x18004606f  jnz     short loc_180046076
0x180046071  lea     edi, [rax+3]
0x180046074  jmp     short loc_1800460CA
0x180046076  lea     rdx, aAudio; "audio"
0x18004607d  lea     rcx, [rbp+370h+Data]; String1
0x180046084  call    wcscmp_0
0x180046089  test    eax, eax
0x18004608b  jnz     short loc_180046092
0x18004608d  lea     edi, [rax+2]
0x180046090  jmp     short loc_1800460CA
0x180046092  lea     rdx, aVideo; "video"
0x180046099  lea     rcx, [rbp+370h+Data]; String1
0x1800460a0  call    wcscmp_0
0x1800460a5  test    eax, eax
0x1800460a7  jnz     short loc_1800460AE
0x1800460a9  lea     edi, [rax+4]
0x1800460ac  jmp     short loc_1800460CA
0x1800460ae  lea     rdx, aDocument; "document"
0x1800460b5  lea     rcx, [rbp+370h+Data]; String1
0x1800460bc  call    wcscmp_0
0x1800460c1  test    eax, eax
0x1800460c3  jnz     short loc_1800460FC
0x1800460c5  mov     edi, 9
0x1800460ca  mov     rcx, rbx
0x1800460cd  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800460d3  mov     rdx, rbx
0x1800460d6  lea     rcx, [rbp+370h+var_260]
0x1800460dd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800460e2  nop
0x1800460e3  mov     rdx, rax
0x1800460e6  mov     rcx, rsi
0x1800460e9  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HU?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@@std@@QEAAAEAH$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,int>::operator[](std::wstring &&)
0x1800460ee  mov     [rax], edi
0x1800460f0  lea     rcx, [rbp+370h+var_260]
0x1800460f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800460fc  mov     rcx, [rsp+470h+phkResult]; hKey
0x180046101  call    cs:__imp_RegCloseKey
0x180046107  mov     eax, [rsp+470h+cbMaxSubKeyLen]
0x18004610b  mov     [rsp+470h+cchName], eax
0x18004610f  mov     edx, r14d; dwIndex
0x180046112  inc     r14d
0x180046115  mov     [rsp+470h+lpcValues], r15; lpftLastWriteTime
0x18004611a  mov     [rsp+470h+lpcbMaxClassLen], r15; lpcchClass
0x18004611f  mov     [rsp+470h+lpcbMaxSubKeyLen], r15; lpClass
  ... truncated ...
```
