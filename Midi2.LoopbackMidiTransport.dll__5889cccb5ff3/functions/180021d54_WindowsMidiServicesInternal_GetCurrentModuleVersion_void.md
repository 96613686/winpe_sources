# WindowsMidiServicesInternal::GetCurrentModuleVersion(void)

- ea: `0x180021d54`
- end: `0x180021f04`
- name: `?GetCurrentModuleVersion@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800220d0`

## callees

- `0x180004180`
- `0x18000500c`
- `0x18000b740`
- `0x18000e178`
- `0x18001c9e8`
- `0x180021c1c`
- `0x180021d54`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180021da6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180021da6`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180021dbb`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180021dbb`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180021dfb`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180021dfb`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180021e30`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180021e30`

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
0x180021d54  mov     [rsp-8+arg_8], rbx
0x180021d59  push    rbp
0x180021d5a  lea     rbp, [rsp-190h]
0x180021d62  sub     rsp, 290h
0x180021d69  mov     rax, cs:__security_cookie
0x180021d70  xor     rax, rsp
0x180021d73  mov     [rbp+190h+var_10], rax
0x180021d7a  mov     rbx, rcx
0x180021d7d  mov     [rsp+290h+lpBuffer], rcx
0x180021d82  xor     edx, edx; Val
0x180021d84  mov     r8d, 208h; Size
0x180021d8a  lea     rcx, [rsp+290h+Filename]; void *
0x180021d8f  call    memset_0
0x180021d94  mov     r8d, 104h; nSize
0x180021d9a  lea     rdx, [rsp+290h+Filename]; lpFilename
0x180021d9f  lea     rcx, cs:180000000h; hModule
0x180021da6  call    cs:__imp_GetModuleFileNameW
0x180021dac  test    eax, eax
0x180021dae  jz      loc_180021EB9
0x180021db4  xor     edx, edx; lpdwHandle
0x180021db6  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x180021dbb  call    cs:__imp_GetFileVersionInfoSizeW
0x180021dc1  test    eax, eax
0x180021dc3  jz      loc_180021EB9
0x180021dc9  xorps   xmm0, xmm0
0x180021dcc  movdqu  xmmword ptr [rsp+290h+lpData], xmm0
0x180021dd2  mov     [rsp+290h+var_250], 0
0x180021ddb  mov     edx, eax
0x180021ddd  lea     rcx, [rsp+290h+lpData]
0x180021de2  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180021de7  mov     r9, [rsp+290h+lpData]; lpData
0x180021dec  mov     r8d, dword ptr [rsp+290h+lpData+8]
0x180021df1  sub     r8d, r9d; dwLen
0x180021df4  xor     edx, edx; dwHandle
0x180021df6  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x180021dfb  call    cs:__imp_GetFileVersionInfoW
0x180021e01  test    eax, eax
0x180021e03  jz      loc_180021EAF
0x180021e09  mov     [rsp+290h+lpBuffer], 0
0x180021e12  mov     [rsp+290h+puLen], 0
0x180021e1a  lea     r9, [rsp+290h+puLen]; puLen
0x180021e1f  lea     r8, [rsp+290h+lpBuffer]; lplpBuffer
0x180021e24  lea     rdx, SubBlock; "\\StringFileInfo\\040904B0\\FileVersion"
0x180021e2b  mov     rcx, [rsp+290h+lpData]; pBlock
0x180021e30  call    cs:__imp_VerQueryValueW
0x180021e36  test    eax, eax
0x180021e38  jz      short loc_180021EAF
0x180021e3a  xorps   xmm0, xmm0
0x180021e3d  movups  [rsp+290h+var_240], xmm0
0x180021e42  xorps   xmm1, xmm1
0x180021e45  movdqu  [rsp+290h+var_230], xmm1
0x180021e4b  mov     r8d, [rsp+290h+puLen]
0x180021e50  dec     r8d
0x180021e53  mov     rdx, [rsp+290h+lpBuffer]
0x180021e58  lea     rcx, [rsp+290h+var_240]
0x180021e5d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180021e62  mov     qword ptr [rbx+10h], 0
0x180021e6a  mov     qword ptr [rbx+18h], 0
0x180021e72  movups  xmm0, [rsp+290h+var_240]
0x180021e77  movups  xmmword ptr [rbx], xmm0
0x180021e7a  movups  xmm1, [rsp+290h+var_230]
0x180021e7f  movups  xmmword ptr [rbx+10h], xmm1
0x180021e83  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180021e8b  movdqu  [rsp+290h+var_230], xmm0
0x180021e91  xor     ecx, ecx
0x180021e93  mov     word ptr [rsp+290h+var_240], cx
0x180021e98  lea     rcx, [rsp+290h+var_240]; void *
0x180021e9d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021ea2  nop
0x180021ea3  lea     rcx, [rsp+290h+lpData]
0x180021ea8  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x180021ead  jmp     short loc_180021EE1
0x180021eaf  lea     rcx, [rsp+290h+lpData]
0x180021eb4  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x180021eb9  xorps   xmm0, xmm0
0x180021ebc  movups  xmmword ptr [rbx], xmm0
0x180021ebf  mov     qword ptr [rbx+10h], 0
0x180021ec7  mov     qword ptr [rbx+18h], 0
0x180021ecf  xor     r8d, r8d
0x180021ed2  lea     rdx, S2
0x180021ed9  mov     rcx, rbx
0x180021edc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180021ee1  mov     rax, rbx
0x180021ee4  mov     rcx, [rbp+190h+var_10]
0x180021eeb  xor     rcx, rsp; StackCookie
0x180021eee  call    __security_check_cookie
0x180021ef3  mov     rbx, [rsp+290h+arg_8]
0x180021efb  add     rsp, 290h
0x180021f02  pop     rbp
0x180021f03  retn
```
