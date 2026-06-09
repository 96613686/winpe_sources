# _lambda_3d4339235bd6cc8a0d7b01eadcfa1e41_::operator()

- ea: `0x180044190`
- end: `0x1800443d7`
- name: `_lambda_3d4339235bd6cc8a0d7b01eadcfa1e41_::operator()`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800453ac`

## callees

- `0x180003390`
- `0x180003e00`
- `0x18000649c`
- `0x18000c168`
- `0x18000db70`
- `0x18001092c`
- `0x180017108`
- `0x180033dc8`
- `0x1800438dc`
- `0x180043c9c`
- `0x1800440ec`
- `0x180044190`
- `0x18004cf54`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004439b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004439b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004438a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004438a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180044233`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180044233`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x1800441d6`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x1800441d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
HRESULT __fastcall lambda_3d4339235bd6cc8a0d7b01eadcfa1e41_::operator()(LPWSTR *a1, int a2)
{
  HRESULT result; // eax
  __int64 v4; // rax
  const WCHAR *v5; // rax
  HANDLE FirstFileW; // rdi
  __m128i si128; // xmm6
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  LPWSTR v13; // rbx
  __int64 v14; // rdx
  _OWORD v15[2]; // [rsp+38h] [rbp-D0h] BYREF
  _OWORD v16[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v17; // [rsp+78h] [rbp-90h]
  __m128i v18; // [rsp+88h] [rbp-80h]
  _OWORD v19[2]; // [rsp+98h] [rbp-70h] BYREF
  __int16 v20; // [rsp+B8h] [rbp-50h]
  __int64 v21; // [rsp+BCh] [rbp-4Ch]
  _BYTE v22[32]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v23[32]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v24[32]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v25[32]; // [rsp+128h] [rbp+20h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+148h] [rbp+40h] BYREF

  result = SHGetFolderPathW(0, a2, 0, 0, a1[1]);
  if ( result >= 0 )
  {
    v4 = std::wstring::wstring((__int64)v22, (__int64)a1[1]);
    std::operator+<unsigned short>(v23, v4, L"\\*.*");
    std::wstring::_Tidy_deallocate(v22);
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
    FirstFileW = FindFirstFileW(v5, &FindFileData);
    if ( FirstFileW != (HANDLE)-1LL )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0 && wcscmp_0(FindFileData.cFileName, L"desktop.ini") )
        {
          v15[0] = 0;
          v15[1] = si128;
          LOWORD(v15[0]) = 0;
          v16[0] = 0;
          v16[1] = si128;
          LOWORD(v16[0]) = 0;
          v17 = 0;
          v18 = si128;
          LOWORD(v17) = 0;
          v19[0] = 0;
          v19[1] = si128;
          LOWORD(v19[0]) = 0;
          v8 = -1;
          do
            ++v8;
          while ( FindFileData.cFileName[v8] );
          std::wstring::_Assign<unsigned short>(v15, FindFileData.cFileName, v8);
          v9 = std::wstring::wstring((__int64)v25, (__int64)a1[1]);
          v10 = std::operator+<unsigned short>(v24, v9, L"\\");
          v11 = std::operator+<unsigned short>(v22, v10, FindFileData.cFileName);
          std::wstring::operator=(v16, v11);
          std::wstring::_Tidy_deallocate(v22);
          std::wstring::_Tidy_deallocate(v24);
          std::wstring::_Tidy_deallocate(v25);
          std::wstring::_Assign<unsigned short>(v19, L"Win32-Folder", 12);
          v20 = 257;
          v21 = 0;
          v13 = *a1;
          v14 = *((_QWORD *)*a1 + 1);
          if ( v14 == *((_QWORD *)*a1 + 2) )
          {
            std::vector<RetailDemoStartup::StartupAppInfo>::_Emplace_reallocate<RetailDemoStartup::StartupAppInfo const &>(
              *a1,
              v14,
              v15);
          }
          else
          {
            std::_Default_allocator_traits<std::allocator<RetailDemoStartup::StartupAppInfo>>::construct<RetailDemoStartup::StartupAppInfo,RetailDemoStartup::StartupAppInfo const &>(
              v12,
              v14,
              v15);
            *((_QWORD *)v13 + 1) += 144LL;
          }
          RetailDemoStartup::StartupAppInfo::~StartupAppInfo((RetailDemoStartup::StartupAppInfo *)v15);
        }
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
      FindClose(FirstFileW);
    }
    return std::wstring::_Tidy_deallocate(v23);
  }
  return result;
}

```

## disassembly

```asm
0x180044190  mov     rax, rsp
0x180044193  mov     [rax+18h], rbx
0x180044197  mov     [rax+20h], rsi
0x18004419b  push    rbp
0x18004419c  push    rdi
0x18004419d  push    r14
0x18004419f  lea     rbp, [rax-2C8h]
0x1800441a6  sub     rsp, 3B0h
0x1800441ad  movaps  xmmword ptr [rax-28h], xmm6
0x1800441b1  mov     rax, cs:__security_cookie
0x1800441b8  xor     rax, rsp
0x1800441bb  mov     [rbp+2C0h+var_30], rax
0x1800441c2  mov     rsi, rcx
0x1800441c5  mov     rax, [rcx+8]
0x1800441c9  mov     [rsp+3C0h+pszPath], rax; pszPath
0x1800441ce  xor     r9d, r9d; dwFlags
0x1800441d1  xor     r8d, r8d; hToken
0x1800441d4  xor     ecx, ecx; hwnd
0x1800441d6  call    cs:__imp_SHGetFolderPathW
0x1800441dc  xor     r14d, r14d
0x1800441df  test    eax, eax
0x1800441e1  js      loc_1800443AB
0x1800441e7  mov     rdx, [rsi+8]
0x1800441eb  lea     rcx, [rbp+2C0h+var_300]
0x1800441ef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800441f4  nop
0x1800441f5  lea     r8, asc_18005DF70; "\\*.*"
0x1800441fc  mov     rdx, rax
0x1800441ff  lea     rcx, [rbp+2C0h+var_2E0]
0x180044203  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180044208  nop
0x180044209  lea     rcx, [rbp+2C0h+var_300]
0x18004420d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044212  xor     edx, edx; Val
0x180044214  mov     r8d, 250h; Size
0x18004421a  lea     rcx, [rbp+2C0h+FindFileData]; void *
0x18004421e  call    memset_0
0x180044223  lea     rcx, [rbp+2C0h+var_2E0]
0x180044227  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004422c  mov     rcx, rax; lpFileName
0x18004422f  lea     rdx, [rbp+2C0h+FindFileData]; lpFindFileData
0x180044233  call    cs:__imp_FindFirstFileW
0x180044239  mov     rdi, rax
0x18004423c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180044240  jz      loc_1800443A2
0x180044246  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18004424e  test    byte ptr [rbp+2C0h+FindFileData.dwFileAttributes], 10h
0x180044252  jnz     loc_180044383
0x180044258  lea     rdx, aDesktopIni; "desktop.ini"
0x18004425f  lea     rcx, [rbp+2C0h+FindFileData.cFileName]; String1
0x180044263  call    wcscmp_0
0x180044268  test    eax, eax
0x18004426a  jz      loc_180044383
0x180044270  xorps   xmm0, xmm0
0x180044273  movups  [rsp+3C0h+var_398+8], xmm0
0x180044278  movdqa  [rsp+3C0h+var_388+8], xmm6
0x18004427e  mov     word ptr [rsp+3C0h+var_398+8], r14w
0x180044284  movups  [rsp+3C0h+var_378+8], xmm0
0x180044289  movdqa  [rsp+3C0h+var_368+8], xmm6
0x18004428f  mov     word ptr [rsp+3C0h+var_378+8], r14w
0x180044295  movups  xmmword ptr [rsp+3C0h+var_358+8], xmm0
0x18004429a  movdqa  [rbp+2C0h+var_340], xmm6
0x18004429f  mov     word ptr [rsp+3C0h+var_358+8], r14w
0x1800442a5  movups  [rbp+2C0h+var_330], xmm0
0x1800442a9  movdqa  [rbp+2C0h+var_320], xmm6
0x1800442ae  mov     word ptr [rbp+2C0h+var_330], r14w
0x1800442b3  lea     rax, [rbp+2C0h+FindFileData.cFileName]
0x1800442b7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800442bb  inc     r8
0x1800442be  cmp     [rax+r8*2], r14w
0x1800442c3  jnz     short loc_1800442BB
0x1800442c5  lea     rdx, [rbp+2C0h+FindFileData.cFileName]
0x1800442c9  lea     rcx, [rsp+3C0h+var_398+8]
0x1800442ce  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800442d3  mov     rdx, [rsi+8]
0x1800442d7  lea     rcx, [rbp+2C0h+var_2A0]
0x1800442db  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800442e0  nop
0x1800442e1  lea     r8, asc_180057BD8; "\\"
0x1800442e8  mov     rdx, rax
0x1800442eb  lea     rcx, [rbp+2C0h+var_2C0]
0x1800442ef  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800442f4  nop
0x1800442f5  lea     r8, [rbp+2C0h+FindFileData.cFileName]
0x1800442f9  mov     rdx, rax
0x1800442fc  lea     rcx, [rbp+2C0h+var_300]
0x180044300  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180044305  mov     rdx, rax
0x180044308  lea     rcx, [rsp+3C0h+var_378+8]
0x18004430d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180044312  lea     rcx, [rbp+2C0h+var_300]
0x180044316  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004431b  nop
0x18004431c  lea     rcx, [rbp+2C0h+var_2C0]
0x180044320  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044325  nop
0x180044326  lea     rcx, [rbp+2C0h+var_2A0]
0x18004432a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004432f  mov     r8d, 0Ch
0x180044335  lea     rdx, aWin32Folder; "Win32-Folder"
0x18004433c  lea     rcx, [rbp+2C0h+var_330]
0x180044340  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180044345  mov     [rbp+2C0h+var_310], 101h
0x18004434b  mov     [rbp+2C0h+var_30C], r14
0x18004434f  mov     rbx, [rsi]
0x180044352  mov     rdx, [rbx+8]
0x180044356  lea     r8, [rsp+3C0h+var_398+8]
0x18004435b  cmp     rdx, [rbx+10h]
0x18004435f  jz      short loc_180044370
0x180044361  call    ??$construct@UStartupAppInfo@RetailDemoStartup@@AEBU12@@?$_Default_allocator_traits@V?$allocator@UStartupAppInfo@RetailDemoStartup@@@std@@@std@@SAXAEAV?$allocator@UStartupAppInfo@RetailDemoStartup@@@1@QEAUStartupAppInfo@RetailDemoStartup@@AEBU34@@Z; std::_Default_allocator_traits<std::allocator<RetailDemoStartup::StartupAppInfo>>::construct<RetailDemoStartup::StartupAppInfo,RetailDemoStartup::StartupAppInfo const &>(std::allocator<RetailDemoStartup::StartupAppInfo> &,RetailDemoStartup::StartupAppInfo * const,RetailDemoStartup::StartupAppInfo const &)
0x180044366  add     qword ptr [rbx+8], 90h
0x18004436e  jmp     short loc_180044379
0x180044370  mov     rcx, rbx
0x180044373  call    ??$_Emplace_reallocate@AEBUStartupAppInfo@RetailDemoStartup@@@?$vector@UStartupAppInfo@RetailDemoStartup@@V?$allocator@UStartupAppInfo@RetailDemoStartup@@@std@@@std@@AEAAPEAUStartupAppInfo@RetailDemoStartup@@QEAU23@AEBU23@@Z; std::vector<RetailDemoStartup::StartupAppInfo>::_Emplace_reallocate<RetailDemoStartup::StartupAppInfo const &>(RetailDemoStartup::StartupAppInfo * const,RetailDemoStartup::StartupAppInfo const &)
0x180044378  nop
0x180044379  lea     rcx, [rsp+3C0h+var_398+8]; this
0x18004437e  call    ??1StartupAppInfo@RetailDemoStartup@@QEAA@XZ; RetailDemoStartup::StartupAppInfo::~StartupAppInfo(void)
0x180044383  lea     rdx, [rbp+2C0h+FindFileData]; lpFindFileData
0x180044387  mov     rcx, rdi; hFindFile
0x18004438a  call    cs:__imp_FindNextFileW
0x180044390  test    eax, eax
0x180044392  jnz     loc_18004424E
0x180044398  mov     rcx, rdi; hFindFile
0x18004439b  call    cs:__imp_FindClose
0x1800443a1  nop
0x1800443a2  lea     rcx, [rbp+2C0h+var_2E0]
0x1800443a6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800443ab  mov     rcx, [rbp+2C0h+var_30]
0x1800443b2  xor     rcx, rsp; StackCookie
0x1800443b5  call    __security_check_cookie
0x1800443ba  lea     r11, [rsp+3C0h+var_10]
0x1800443c2  mov     rbx, [r11+30h]
0x1800443c6  mov     rsi, [r11+38h]
0x1800443ca  movaps  xmm6, xmmword ptr [r11-10h]
0x1800443cf  mov     rsp, r11
0x1800443d2  pop     r14
0x1800443d4  pop     rdi
0x1800443d5  pop     rbp
0x1800443d6  retn
```
