# WindowsMidiServicesInternal::GetCurrentModuleVersionCompanyName(void)

- ea: `0x1800117e8`
- end: `0x180011998`
- name: `?GetCurrentModuleVersionCompanyName@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800119a0`

## callees

- `0x1800033d0`
- `0x180004170`
- `0x18000b7fc`
- `0x18000c4c0`
- `0x18001148c`
- `0x1800115c4`
- `0x1800117e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001183a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001183a`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18001188f`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18001188f`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18001184f`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18001184f`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800118c4`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800118c4`

## string_xrefs

- `0x1800118b8`: `\StringFileInfo\040904B0\CompanyName`

## pseudocode

```c
__m128i *__fastcall WindowsMidiServicesInternal::GetCurrentModuleVersionCompanyName(__m128i *a1)
{
  DWORD FileVersionInfoSizeW; // eax
  unsigned int puLen; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpBuffer; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID lpData[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v7; // [rsp+40h] [rbp-C0h]
  __m128i v8; // [rsp+50h] [rbp-B0h] BYREF
  __m128i si128; // [rsp+60h] [rbp-A0h]
  WCHAR Filename[264]; // [rsp+70h] [rbp-90h] BYREF

  lpBuffer = a1;
  memset_0(Filename, 0, 0x208u);
  if ( !GetModuleFileNameW((HMODULE)0x180000000LL, Filename, 0x104u) )
    goto LABEL_7;
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(Filename, 0);
  if ( !FileVersionInfoSizeW )
    goto LABEL_7;
  *(_OWORD *)lpData = 0;
  v7 = 0;
  std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(lpData, FileVersionInfoSizeW);
  if ( !GetFileVersionInfoW(Filename, 0, LODWORD(lpData[1]) - LODWORD(lpData[0]), lpData[0])
    || (lpBuffer = 0,
        puLen = 0,
        !VerQueryValueW(lpData[0], L"\\StringFileInfo\\040904B0\\CompanyName", &lpBuffer, &puLen)) )
  {
    std::vector<unsigned char>::~vector<unsigned char>(lpData);
LABEL_7:
    *a1 = 0;
    a1[1].m128i_i64[0] = 0;
    a1[1].m128i_i64[1] = 0;
    std::wstring::_Construct<1,unsigned short const *>(a1, qword_1800159A0, 0);
    return a1;
  }
  v8 = 0;
  si128 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v8, lpBuffer, puLen - 1);
  a1[1].m128i_i64[0] = 0;
  a1[1].m128i_i64[1] = 0;
  *a1 = v8;
  a1[1] = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v8.m128i_i16[0] = 0;
  std::wstring::~wstring(&v8);
  std::vector<unsigned char>::~vector<unsigned char>(lpData);
  return a1;
}

```

## disassembly

```asm
0x1800117e8  mov     [rsp-8+arg_8], rbx
0x1800117ed  push    rbp
0x1800117ee  lea     rbp, [rsp-190h]
0x1800117f6  sub     rsp, 290h
0x1800117fd  mov     rax, cs:__security_cookie
0x180011804  xor     rax, rsp
0x180011807  mov     [rbp+190h+var_10], rax
0x18001180e  mov     rbx, rcx
0x180011811  mov     [rsp+290h+lpBuffer], rcx
0x180011816  xor     edx, edx; Val
0x180011818  mov     r8d, 208h; Size
0x18001181e  lea     rcx, [rsp+290h+Filename]; void *
0x180011823  call    memset_0
0x180011828  mov     r8d, 104h; nSize
0x18001182e  lea     rdx, [rsp+290h+Filename]; lpFilename
0x180011833  lea     rcx, cs:180000000h; hModule
0x18001183a  call    cs:__imp_GetModuleFileNameW
0x180011840  test    eax, eax
0x180011842  jz      loc_18001194D
0x180011848  xor     edx, edx; lpdwHandle
0x18001184a  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x18001184f  call    cs:__imp_GetFileVersionInfoSizeW
0x180011855  test    eax, eax
0x180011857  jz      loc_18001194D
0x18001185d  xorps   xmm0, xmm0
0x180011860  movdqu  xmmword ptr [rsp+290h+lpData], xmm0
0x180011866  mov     [rsp+290h+var_250], 0
0x18001186f  mov     edx, eax
0x180011871  lea     rcx, [rsp+290h+lpData]
0x180011876  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001187b  mov     r9, [rsp+290h+lpData]; lpData
0x180011880  mov     r8d, dword ptr [rsp+290h+lpData+8]
0x180011885  sub     r8d, r9d; dwLen
0x180011888  xor     edx, edx; dwHandle
0x18001188a  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x18001188f  call    cs:__imp_GetFileVersionInfoW
0x180011895  test    eax, eax
0x180011897  jz      loc_180011943
0x18001189d  mov     [rsp+290h+lpBuffer], 0
0x1800118a6  mov     [rsp+290h+puLen], 0
0x1800118ae  lea     r9, [rsp+290h+puLen]; puLen
0x1800118b3  lea     r8, [rsp+290h+lpBuffer]; lplpBuffer
0x1800118b8  lea     rdx, aStringfileinfo; "\\StringFileInfo\\040904B0\\CompanyName"
0x1800118bf  mov     rcx, [rsp+290h+lpData]; pBlock
0x1800118c4  call    cs:__imp_VerQueryValueW
0x1800118ca  test    eax, eax
0x1800118cc  jz      short loc_180011943
0x1800118ce  xorps   xmm0, xmm0
0x1800118d1  movups  [rsp+290h+var_240], xmm0
0x1800118d6  xorps   xmm1, xmm1
0x1800118d9  movdqu  [rsp+290h+var_230], xmm1
0x1800118df  mov     r8d, [rsp+290h+puLen]
0x1800118e4  dec     r8d
0x1800118e7  mov     rdx, [rsp+290h+lpBuffer]
0x1800118ec  lea     rcx, [rsp+290h+var_240]
0x1800118f1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800118f6  mov     qword ptr [rbx+10h], 0
0x1800118fe  mov     qword ptr [rbx+18h], 0
0x180011906  movups  xmm0, [rsp+290h+var_240]
0x18001190b  movups  xmmword ptr [rbx], xmm0
0x18001190e  movups  xmm1, [rsp+290h+var_230]
0x180011913  movups  xmmword ptr [rbx+10h], xmm1
0x180011917  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001191f  movdqu  [rsp+290h+var_230], xmm0
0x180011925  xor     ecx, ecx
0x180011927  mov     word ptr [rsp+290h+var_240], cx
0x18001192c  lea     rcx, [rsp+290h+var_240]
0x180011931  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011936  nop
0x180011937  lea     rcx, [rsp+290h+lpData]
0x18001193c  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011941  jmp     short loc_180011975
0x180011943  lea     rcx, [rsp+290h+lpData]
0x180011948  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18001194d  xorps   xmm0, xmm0
0x180011950  movups  xmmword ptr [rbx], xmm0
0x180011953  mov     qword ptr [rbx+10h], 0
0x18001195b  mov     qword ptr [rbx+18h], 0
0x180011963  xor     r8d, r8d
0x180011966  lea     rdx, qword_1800159A0
0x18001196d  mov     rcx, rbx
0x180011970  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011975  mov     rax, rbx
0x180011978  mov     rcx, [rbp+190h+var_10]
0x18001197f  xor     rcx, rsp; StackCookie
0x180011982  call    __security_check_cookie
0x180011987  mov     rbx, [rsp+290h+arg_8]
0x18001198f  add     rsp, 290h
0x180011996  pop     rbp
0x180011997  retn
```
