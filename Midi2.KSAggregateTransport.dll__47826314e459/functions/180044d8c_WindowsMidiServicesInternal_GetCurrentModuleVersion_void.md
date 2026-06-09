# WindowsMidiServicesInternal::GetCurrentModuleVersion(void)

- ea: `0x180044d8c`
- end: `0x180044f3c`
- name: `?GetCurrentModuleVersion@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180045100`

## callees

- `0x180005020`
- `0x180005e9c`
- `0x18000d430`
- `0x18000d920`
- `0x180013118`
- `0x18002fbd8`
- `0x180044d8c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180044dde`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180044dde`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180044e33`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180044e33`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180044df3`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180044df3`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180044e68`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180044e68`

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
    std::wstring::_Construct<1,unsigned short const *>(a1);
    return a1;
  }
  v8 = 0;
  si128 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v8);
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
0x180044d8c  mov     [rsp-8+arg_8], rbx
0x180044d91  push    rbp
0x180044d92  lea     rbp, [rsp-190h]
0x180044d9a  sub     rsp, 290h
0x180044da1  mov     rax, cs:__security_cookie
0x180044da8  xor     rax, rsp
0x180044dab  mov     [rbp+190h+var_10], rax
0x180044db2  mov     rbx, rcx
0x180044db5  mov     [rsp+290h+lpBuffer], rcx
0x180044dba  xor     edx, edx; Val
0x180044dbc  mov     r8d, 208h; Size
0x180044dc2  lea     rcx, [rsp+290h+Filename]; void *
0x180044dc7  call    memset_0
0x180044dcc  mov     r8d, 104h; nSize
0x180044dd2  lea     rdx, [rsp+290h+Filename]; lpFilename
0x180044dd7  lea     rcx, cs:180000000h; hModule
0x180044dde  call    cs:__imp_GetModuleFileNameW
0x180044de4  test    eax, eax
0x180044de6  jz      loc_180044EF1
0x180044dec  xor     edx, edx; lpdwHandle
0x180044dee  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x180044df3  call    cs:__imp_GetFileVersionInfoSizeW
0x180044df9  test    eax, eax
0x180044dfb  jz      loc_180044EF1
0x180044e01  xorps   xmm0, xmm0
0x180044e04  movdqu  xmmword ptr [rsp+290h+lpData], xmm0
0x180044e0a  mov     [rsp+290h+var_250], 0
0x180044e13  mov     edx, eax
0x180044e15  lea     rcx, [rsp+290h+lpData]
0x180044e1a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180044e1f  mov     r9, [rsp+290h+lpData]; lpData
0x180044e24  mov     r8d, dword ptr [rsp+290h+lpData+8]
0x180044e29  sub     r8d, r9d; dwLen
0x180044e2c  xor     edx, edx; dwHandle
0x180044e2e  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x180044e33  call    cs:__imp_GetFileVersionInfoW
0x180044e39  test    eax, eax
0x180044e3b  jz      loc_180044EE7
0x180044e41  mov     [rsp+290h+lpBuffer], 0
0x180044e4a  mov     [rsp+290h+puLen], 0
0x180044e52  lea     r9, [rsp+290h+puLen]; puLen
0x180044e57  lea     r8, [rsp+290h+lpBuffer]; lplpBuffer
0x180044e5c  lea     rdx, SubBlock; "\\StringFileInfo\\040904B0\\FileVersion"
0x180044e63  mov     rcx, [rsp+290h+lpData]; pBlock
0x180044e68  call    cs:__imp_VerQueryValueW
0x180044e6e  test    eax, eax
0x180044e70  jz      short loc_180044EE7
0x180044e72  xorps   xmm0, xmm0
0x180044e75  movups  [rsp+290h+var_240], xmm0
0x180044e7a  xorps   xmm1, xmm1
0x180044e7d  movdqu  [rsp+290h+var_230], xmm1
0x180044e83  mov     r8d, [rsp+290h+puLen]
0x180044e88  dec     r8d
0x180044e8b  mov     rdx, [rsp+290h+lpBuffer]
0x180044e90  lea     rcx, [rsp+290h+var_240]
0x180044e95  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180044e9a  mov     qword ptr [rbx+10h], 0
0x180044ea2  mov     qword ptr [rbx+18h], 0
0x180044eaa  movups  xmm0, [rsp+290h+var_240]
0x180044eaf  movups  xmmword ptr [rbx], xmm0
0x180044eb2  movups  xmm1, [rsp+290h+var_230]
0x180044eb7  movups  xmmword ptr [rbx+10h], xmm1
0x180044ebb  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180044ec3  movdqu  [rsp+290h+var_230], xmm0
0x180044ec9  xor     ecx, ecx
0x180044ecb  mov     word ptr [rsp+290h+var_240], cx
0x180044ed0  lea     rcx, [rsp+290h+var_240]; void *
0x180044ed5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044eda  nop
0x180044edb  lea     rcx, [rsp+290h+lpData]
0x180044ee0  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x180044ee5  jmp     short loc_180044F19
0x180044ee7  lea     rcx, [rsp+290h+lpData]
0x180044eec  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x180044ef1  xorps   xmm0, xmm0
0x180044ef4  movups  xmmword ptr [rbx], xmm0
0x180044ef7  mov     qword ptr [rbx+10h], 0
0x180044eff  mov     qword ptr [rbx+18h], 0
0x180044f07  xor     r8d, r8d
0x180044f0a  lea     rdx, S1
0x180044f11  mov     rcx, rbx
0x180044f14  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180044f19  mov     rax, rbx
0x180044f1c  mov     rcx, [rbp+190h+var_10]
0x180044f23  xor     rcx, rsp; StackCookie
0x180044f26  call    __security_check_cookie
0x180044f2b  mov     rbx, [rsp+290h+arg_8]
0x180044f33  add     rsp, 290h
0x180044f3a  pop     rbp
0x180044f3b  retn
```
