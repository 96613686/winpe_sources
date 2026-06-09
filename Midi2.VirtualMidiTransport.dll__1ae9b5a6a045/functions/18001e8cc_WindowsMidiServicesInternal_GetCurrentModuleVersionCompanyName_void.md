# WindowsMidiServicesInternal::GetCurrentModuleVersionCompanyName(void)

- ea: `0x18001e8cc`
- end: `0x18001ea7c`
- name: `?GetCurrentModuleVersionCompanyName@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ea90`

## callees

- `0x1800038f0`
- `0x1800046a0`
- `0x18000bf6c`
- `0x18000cb48`
- `0x18000d57c`
- `0x18001e5dc`
- `0x18001e8cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001e91e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001e91e`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18001e933`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18001e933`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18001e973`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18001e973`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001e9a8`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001e9a8`

## string_xrefs

- `0x18001e99c`: `\StringFileInfo\040904B0\CompanyName`

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
0x18001e8cc  mov     [rsp-8+arg_8], rbx
0x18001e8d1  push    rbp
0x18001e8d2  lea     rbp, [rsp-190h]
0x18001e8da  sub     rsp, 290h
0x18001e8e1  mov     rax, cs:__security_cookie
0x18001e8e8  xor     rax, rsp
0x18001e8eb  mov     [rbp+190h+var_10], rax
0x18001e8f2  mov     rbx, rcx
0x18001e8f5  mov     [rsp+290h+lpBuffer], rcx
0x18001e8fa  xor     edx, edx; Val
0x18001e8fc  mov     r8d, 208h; Size
0x18001e902  lea     rcx, [rsp+290h+Filename]; void *
0x18001e907  call    memset_0
0x18001e90c  mov     r8d, 104h; nSize
0x18001e912  lea     rdx, [rsp+290h+Filename]; lpFilename
0x18001e917  lea     rcx, cs:180000000h; hModule
0x18001e91e  call    cs:__imp_GetModuleFileNameW
0x18001e924  test    eax, eax
0x18001e926  jz      loc_18001EA31
0x18001e92c  xor     edx, edx; lpdwHandle
0x18001e92e  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x18001e933  call    cs:__imp_GetFileVersionInfoSizeW
0x18001e939  test    eax, eax
0x18001e93b  jz      loc_18001EA31
0x18001e941  xorps   xmm0, xmm0
0x18001e944  movdqu  xmmword ptr [rsp+290h+lpData], xmm0
0x18001e94a  mov     [rsp+290h+var_250], 0
0x18001e953  mov     edx, eax
0x18001e955  lea     rcx, [rsp+290h+lpData]
0x18001e95a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001e95f  mov     r9, [rsp+290h+lpData]; lpData
0x18001e964  mov     r8d, dword ptr [rsp+290h+lpData+8]
0x18001e969  sub     r8d, r9d; dwLen
0x18001e96c  xor     edx, edx; dwHandle
0x18001e96e  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x18001e973  call    cs:__imp_GetFileVersionInfoW
0x18001e979  test    eax, eax
0x18001e97b  jz      loc_18001EA27
0x18001e981  mov     [rsp+290h+lpBuffer], 0
0x18001e98a  mov     [rsp+290h+puLen], 0
0x18001e992  lea     r9, [rsp+290h+puLen]; puLen
0x18001e997  lea     r8, [rsp+290h+lpBuffer]; lplpBuffer
0x18001e99c  lea     rdx, aStringfileinfo; "\\StringFileInfo\\040904B0\\CompanyName"
0x18001e9a3  mov     rcx, [rsp+290h+lpData]; pBlock
0x18001e9a8  call    cs:__imp_VerQueryValueW
0x18001e9ae  test    eax, eax
0x18001e9b0  jz      short loc_18001EA27
0x18001e9b2  xorps   xmm0, xmm0
0x18001e9b5  movups  [rsp+290h+var_240], xmm0
0x18001e9ba  xorps   xmm1, xmm1
0x18001e9bd  movdqu  [rsp+290h+var_230], xmm1
0x18001e9c3  mov     r8d, [rsp+290h+puLen]
0x18001e9c8  dec     r8d
0x18001e9cb  mov     rdx, [rsp+290h+lpBuffer]
0x18001e9d0  lea     rcx, [rsp+290h+var_240]
0x18001e9d5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001e9da  mov     qword ptr [rbx+10h], 0
0x18001e9e2  mov     qword ptr [rbx+18h], 0
0x18001e9ea  movups  xmm0, [rsp+290h+var_240]
0x18001e9ef  movups  xmmword ptr [rbx], xmm0
0x18001e9f2  movups  xmm1, [rsp+290h+var_230]
0x18001e9f7  movups  xmmword ptr [rbx+10h], xmm1
0x18001e9fb  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001ea03  movdqu  [rsp+290h+var_230], xmm0
0x18001ea09  xor     ecx, ecx
0x18001ea0b  mov     word ptr [rsp+290h+var_240], cx
0x18001ea10  lea     rcx, [rsp+290h+var_240]
0x18001ea15  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ea1a  nop
0x18001ea1b  lea     rcx, [rsp+290h+lpData]
0x18001ea20  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x18001ea25  jmp     short loc_18001EA59
0x18001ea27  lea     rcx, [rsp+290h+lpData]
0x18001ea2c  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x18001ea31  xorps   xmm0, xmm0
0x18001ea34  movups  xmmword ptr [rbx], xmm0
0x18001ea37  mov     qword ptr [rbx+10h], 0
0x18001ea3f  mov     qword ptr [rbx+18h], 0
0x18001ea47  xor     r8d, r8d
0x18001ea4a  lea     rdx, S2
0x18001ea51  mov     rcx, rbx
0x18001ea54  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001ea59  mov     rax, rbx
0x18001ea5c  mov     rcx, [rbp+190h+var_10]
0x18001ea63  xor     rcx, rsp; StackCookie
0x18001ea66  call    __security_check_cookie
0x18001ea6b  mov     rbx, [rsp+290h+arg_8]
0x18001ea73  add     rsp, 290h
0x18001ea7a  pop     rbp
0x18001ea7b  retn
```
