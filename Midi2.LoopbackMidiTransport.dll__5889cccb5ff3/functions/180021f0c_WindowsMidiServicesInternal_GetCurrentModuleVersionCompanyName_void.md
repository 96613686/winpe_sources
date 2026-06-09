# WindowsMidiServicesInternal::GetCurrentModuleVersionCompanyName(void)

- ea: `0x180021f0c`
- end: `0x1800220bc`
- name: `?GetCurrentModuleVersionCompanyName@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800220d0`

## callees

- `0x180004180`
- `0x18000500c`
- `0x18000b740`
- `0x18000e178`
- `0x18001c9e8`
- `0x180021c1c`
- `0x180021f0c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180021f5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180021f5e`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180021f73`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180021f73`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180021fb3`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180021fb3`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180021fe8`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180021fe8`

## string_xrefs

- `0x180021fdc`: `\StringFileInfo\040904B0\CompanyName`

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
    std::vector<enum std::byte>::~vector<enum std::byte>(lpData);
LABEL_7:
    *a1 = 0;
    a1[1].m128i_i64[0] = 0;
    a1[1].m128i_i64[1] = 0;
    std::wstring::_Construct<1,unsigned short const *>(a1, &S2);
    return a1;
  }
  v8 = 0;
  si128 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v8, lpBuffer);
  a1[1].m128i_i64[0] = 0;
  a1[1].m128i_i64[1] = 0;
  *a1 = v8;
  a1[1] = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v8.m128i_i16[0] = 0;
  std::wstring::~wstring(&v8);
  std::vector<enum std::byte>::~vector<enum std::byte>(lpData);
  return a1;
}

```

## disassembly

```asm
0x180021f0c  mov     [rsp-8+arg_8], rbx
0x180021f11  push    rbp
0x180021f12  lea     rbp, [rsp-190h]
0x180021f1a  sub     rsp, 290h
0x180021f21  mov     rax, cs:__security_cookie
0x180021f28  xor     rax, rsp
0x180021f2b  mov     [rbp+190h+var_10], rax
0x180021f32  mov     rbx, rcx
0x180021f35  mov     [rsp+290h+lpBuffer], rcx
0x180021f3a  xor     edx, edx; Val
0x180021f3c  mov     r8d, 208h; Size
0x180021f42  lea     rcx, [rsp+290h+Filename]; void *
0x180021f47  call    memset_0
0x180021f4c  mov     r8d, 104h; nSize
0x180021f52  lea     rdx, [rsp+290h+Filename]; lpFilename
0x180021f57  lea     rcx, cs:180000000h; hModule
0x180021f5e  call    cs:__imp_GetModuleFileNameW
0x180021f64  test    eax, eax
0x180021f66  jz      loc_180022071
0x180021f6c  xor     edx, edx; lpdwHandle
0x180021f6e  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x180021f73  call    cs:__imp_GetFileVersionInfoSizeW
0x180021f79  test    eax, eax
0x180021f7b  jz      loc_180022071
0x180021f81  xorps   xmm0, xmm0
0x180021f84  movdqu  xmmword ptr [rsp+290h+lpData], xmm0
0x180021f8a  mov     [rsp+290h+var_250], 0
0x180021f93  mov     edx, eax
0x180021f95  lea     rcx, [rsp+290h+lpData]
0x180021f9a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180021f9f  mov     r9, [rsp+290h+lpData]; lpData
0x180021fa4  mov     r8d, dword ptr [rsp+290h+lpData+8]
0x180021fa9  sub     r8d, r9d; dwLen
0x180021fac  xor     edx, edx; dwHandle
0x180021fae  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x180021fb3  call    cs:__imp_GetFileVersionInfoW
0x180021fb9  test    eax, eax
0x180021fbb  jz      loc_180022067
0x180021fc1  mov     [rsp+290h+lpBuffer], 0
0x180021fca  mov     [rsp+290h+puLen], 0
0x180021fd2  lea     r9, [rsp+290h+puLen]; puLen
0x180021fd7  lea     r8, [rsp+290h+lpBuffer]; lplpBuffer
0x180021fdc  lea     rdx, aStringfileinfo; "\\StringFileInfo\\040904B0\\CompanyName"
0x180021fe3  mov     rcx, [rsp+290h+lpData]; pBlock
0x180021fe8  call    cs:__imp_VerQueryValueW
0x180021fee  test    eax, eax
0x180021ff0  jz      short loc_180022067
0x180021ff2  xorps   xmm0, xmm0
0x180021ff5  movups  [rsp+290h+var_240], xmm0
0x180021ffa  xorps   xmm1, xmm1
0x180021ffd  movdqu  [rsp+290h+var_230], xmm1
0x180022003  mov     r8d, [rsp+290h+puLen]
0x180022008  dec     r8d
0x18002200b  mov     rdx, [rsp+290h+lpBuffer]
0x180022010  lea     rcx, [rsp+290h+var_240]
0x180022015  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002201a  mov     qword ptr [rbx+10h], 0
0x180022022  mov     qword ptr [rbx+18h], 0
0x18002202a  movups  xmm0, [rsp+290h+var_240]
0x18002202f  movups  xmmword ptr [rbx], xmm0
0x180022032  movups  xmm1, [rsp+290h+var_230]
0x180022037  movups  xmmword ptr [rbx+10h], xmm1
0x18002203b  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180022043  movdqu  [rsp+290h+var_230], xmm0
0x180022049  xor     ecx, ecx
0x18002204b  mov     word ptr [rsp+290h+var_240], cx
0x180022050  lea     rcx, [rsp+290h+var_240]; void *
0x180022055  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002205a  nop
0x18002205b  lea     rcx, [rsp+290h+lpData]
0x180022060  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x180022065  jmp     short loc_180022099
0x180022067  lea     rcx, [rsp+290h+lpData]
0x18002206c  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x180022071  xorps   xmm0, xmm0
0x180022074  movups  xmmword ptr [rbx], xmm0
0x180022077  mov     qword ptr [rbx+10h], 0
0x18002207f  mov     qword ptr [rbx+18h], 0
0x180022087  xor     r8d, r8d
0x18002208a  lea     rdx, S2
0x180022091  mov     rcx, rbx
0x180022094  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180022099  mov     rax, rbx
0x18002209c  mov     rcx, [rbp+190h+var_10]
0x1800220a3  xor     rcx, rsp; StackCookie
0x1800220a6  call    __security_check_cookie
0x1800220ab  mov     rbx, [rsp+290h+arg_8]
0x1800220b3  add     rsp, 290h
0x1800220ba  pop     rbp
0x1800220bb  retn
```
