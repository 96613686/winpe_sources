# WindowsMidiServicesInternal::GetCurrentModuleVersion(void)

- ea: `0x18001e714`
- end: `0x18001e8c4`
- name: `?GetCurrentModuleVersion@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18001ea90`

## callees

- `0x1800038f0`
- `0x1800046a0`
- `0x18000bf6c`
- `0x18000cb48`
- `0x18000d57c`
- `0x18001e5dc`
- `0x18001e714`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001e766`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001e766`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18001e77b`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18001e77b`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18001e7bb`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18001e7bb`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001e7f0`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001e7f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__m128i *__fastcall WindowsMidiServicesInternal::GetCurrentModuleVersion(__m128i *a1)
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
        !VerQueryValueW(lpData[0], L"\\StringFileInfo\\040904B0\\FileVersion", &lpBuffer, &puLen)) )
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
0x18001e714  mov     [rsp-8+arg_8], rbx
0x18001e719  push    rbp
0x18001e71a  lea     rbp, [rsp-190h]
0x18001e722  sub     rsp, 290h
0x18001e729  mov     rax, cs:__security_cookie
0x18001e730  xor     rax, rsp
0x18001e733  mov     [rbp+190h+var_10], rax
0x18001e73a  mov     rbx, rcx
0x18001e73d  mov     [rsp+290h+lpBuffer], rcx
0x18001e742  xor     edx, edx; Val
0x18001e744  mov     r8d, 208h; Size
0x18001e74a  lea     rcx, [rsp+290h+Filename]; void *
0x18001e74f  call    memset_0
0x18001e754  mov     r8d, 104h; nSize
0x18001e75a  lea     rdx, [rsp+290h+Filename]; lpFilename
0x18001e75f  lea     rcx, cs:180000000h; hModule
0x18001e766  call    cs:__imp_GetModuleFileNameW
0x18001e76c  test    eax, eax
0x18001e76e  jz      loc_18001E879
0x18001e774  xor     edx, edx; lpdwHandle
0x18001e776  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x18001e77b  call    cs:__imp_GetFileVersionInfoSizeW
0x18001e781  test    eax, eax
0x18001e783  jz      loc_18001E879
0x18001e789  xorps   xmm0, xmm0
0x18001e78c  movdqu  xmmword ptr [rsp+290h+lpData], xmm0
0x18001e792  mov     [rsp+290h+var_250], 0
0x18001e79b  mov     edx, eax
0x18001e79d  lea     rcx, [rsp+290h+lpData]
0x18001e7a2  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001e7a7  mov     r9, [rsp+290h+lpData]; lpData
0x18001e7ac  mov     r8d, dword ptr [rsp+290h+lpData+8]
0x18001e7b1  sub     r8d, r9d; dwLen
0x18001e7b4  xor     edx, edx; dwHandle
0x18001e7b6  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x18001e7bb  call    cs:__imp_GetFileVersionInfoW
0x18001e7c1  test    eax, eax
0x18001e7c3  jz      loc_18001E86F
0x18001e7c9  mov     [rsp+290h+lpBuffer], 0
0x18001e7d2  mov     [rsp+290h+puLen], 0
0x18001e7da  lea     r9, [rsp+290h+puLen]; puLen
0x18001e7df  lea     r8, [rsp+290h+lpBuffer]; lplpBuffer
0x18001e7e4  lea     rdx, SubBlock; "\\StringFileInfo\\040904B0\\FileVersion"
0x18001e7eb  mov     rcx, [rsp+290h+lpData]; pBlock
0x18001e7f0  call    cs:__imp_VerQueryValueW
0x18001e7f6  test    eax, eax
0x18001e7f8  jz      short loc_18001E86F
0x18001e7fa  xorps   xmm0, xmm0
0x18001e7fd  movups  [rsp+290h+var_240], xmm0
0x18001e802  xorps   xmm1, xmm1
0x18001e805  movdqu  [rsp+290h+var_230], xmm1
0x18001e80b  mov     r8d, [rsp+290h+puLen]
0x18001e810  dec     r8d
0x18001e813  mov     rdx, [rsp+290h+lpBuffer]
0x18001e818  lea     rcx, [rsp+290h+var_240]
0x18001e81d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001e822  mov     qword ptr [rbx+10h], 0
0x18001e82a  mov     qword ptr [rbx+18h], 0
0x18001e832  movups  xmm0, [rsp+290h+var_240]
0x18001e837  movups  xmmword ptr [rbx], xmm0
0x18001e83a  movups  xmm1, [rsp+290h+var_230]
0x18001e83f  movups  xmmword ptr [rbx+10h], xmm1
0x18001e843  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001e84b  movdqu  [rsp+290h+var_230], xmm0
0x18001e851  xor     ecx, ecx
0x18001e853  mov     word ptr [rsp+290h+var_240], cx
0x18001e858  lea     rcx, [rsp+290h+var_240]
0x18001e85d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001e862  nop
0x18001e863  lea     rcx, [rsp+290h+lpData]
0x18001e868  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x18001e86d  jmp     short loc_18001E8A1
0x18001e86f  lea     rcx, [rsp+290h+lpData]
0x18001e874  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x18001e879  xorps   xmm0, xmm0
0x18001e87c  movups  xmmword ptr [rbx], xmm0
0x18001e87f  mov     qword ptr [rbx+10h], 0
0x18001e887  mov     qword ptr [rbx+18h], 0
0x18001e88f  xor     r8d, r8d
0x18001e892  lea     rdx, S2
0x18001e899  mov     rcx, rbx
0x18001e89c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001e8a1  mov     rax, rbx
0x18001e8a4  mov     rcx, [rbp+190h+var_10]
0x18001e8ab  xor     rcx, rsp; StackCookie
0x18001e8ae  call    __security_check_cookie
0x18001e8b3  mov     rbx, [rsp+290h+arg_8]
0x18001e8bb  add     rsp, 290h
0x18001e8c2  pop     rbp
0x18001e8c3  retn
```
