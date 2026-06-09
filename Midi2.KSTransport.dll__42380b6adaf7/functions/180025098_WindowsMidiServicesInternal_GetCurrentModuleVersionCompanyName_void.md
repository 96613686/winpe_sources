# WindowsMidiServicesInternal::GetCurrentModuleVersionCompanyName(void)

- ea: `0x180025098`
- end: `0x180025248`
- name: `?GetCurrentModuleVersionCompanyName@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025250`

## callees

- `0x180004410`
- `0x18000526c`
- `0x18000c250`
- `0x18000c73c`
- `0x18000f304`
- `0x180024da8`
- `0x180025098`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800250ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800250ea`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x1800250ff`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x1800250ff`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18002513f`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18002513f`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180025174`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180025174`

## string_xrefs

- `0x180025168`: `\StringFileInfo\040904B0\CompanyName`

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
    std::wstring::_Construct<1,unsigned short const *>(a1, &S1, 0);
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
  std::vector<enum std::byte>::~vector<enum std::byte>(lpData);
  return a1;
}

```

## disassembly

```asm
0x180025098  mov     [rsp-8+arg_8], rbx
0x18002509d  push    rbp
0x18002509e  lea     rbp, [rsp-190h]
0x1800250a6  sub     rsp, 290h
0x1800250ad  mov     rax, cs:__security_cookie
0x1800250b4  xor     rax, rsp
0x1800250b7  mov     [rbp+190h+var_10], rax
0x1800250be  mov     rbx, rcx
0x1800250c1  mov     [rsp+290h+lpBuffer], rcx
0x1800250c6  xor     edx, edx; Val
0x1800250c8  mov     r8d, 208h; Size
0x1800250ce  lea     rcx, [rsp+290h+Filename]; void *
0x1800250d3  call    memset_0
0x1800250d8  mov     r8d, 104h; nSize
0x1800250de  lea     rdx, [rsp+290h+Filename]; lpFilename
0x1800250e3  lea     rcx, cs:180000000h; hModule
0x1800250ea  call    cs:__imp_GetModuleFileNameW
0x1800250f0  test    eax, eax
0x1800250f2  jz      loc_1800251FD
0x1800250f8  xor     edx, edx; lpdwHandle
0x1800250fa  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x1800250ff  call    cs:__imp_GetFileVersionInfoSizeW
0x180025105  test    eax, eax
0x180025107  jz      loc_1800251FD
0x18002510d  xorps   xmm0, xmm0
0x180025110  movdqu  xmmword ptr [rsp+290h+lpData], xmm0
0x180025116  mov     [rsp+290h+var_250], 0
0x18002511f  mov     edx, eax
0x180025121  lea     rcx, [rsp+290h+lpData]
0x180025126  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002512b  mov     r9, [rsp+290h+lpData]; lpData
0x180025130  mov     r8d, dword ptr [rsp+290h+lpData+8]
0x180025135  sub     r8d, r9d; dwLen
0x180025138  xor     edx, edx; dwHandle
0x18002513a  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x18002513f  call    cs:__imp_GetFileVersionInfoW
0x180025145  test    eax, eax
0x180025147  jz      loc_1800251F3
0x18002514d  mov     [rsp+290h+lpBuffer], 0
0x180025156  mov     [rsp+290h+puLen], 0
0x18002515e  lea     r9, [rsp+290h+puLen]; puLen
0x180025163  lea     r8, [rsp+290h+lpBuffer]; lplpBuffer
0x180025168  lea     rdx, aStringfileinfo; "\\StringFileInfo\\040904B0\\CompanyName"
0x18002516f  mov     rcx, [rsp+290h+lpData]; pBlock
0x180025174  call    cs:__imp_VerQueryValueW
0x18002517a  test    eax, eax
0x18002517c  jz      short loc_1800251F3
0x18002517e  xorps   xmm0, xmm0
0x180025181  movups  [rsp+290h+var_240], xmm0
0x180025186  xorps   xmm1, xmm1
0x180025189  movdqu  [rsp+290h+var_230], xmm1
0x18002518f  mov     r8d, [rsp+290h+puLen]
0x180025194  dec     r8d
0x180025197  mov     rdx, [rsp+290h+lpBuffer]
0x18002519c  lea     rcx, [rsp+290h+var_240]
0x1800251a1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800251a6  mov     qword ptr [rbx+10h], 0
0x1800251ae  mov     qword ptr [rbx+18h], 0
0x1800251b6  movups  xmm0, [rsp+290h+var_240]
0x1800251bb  movups  xmmword ptr [rbx], xmm0
0x1800251be  movups  xmm1, [rsp+290h+var_230]
0x1800251c3  movups  xmmword ptr [rbx+10h], xmm1
0x1800251c7  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800251cf  movdqu  [rsp+290h+var_230], xmm0
0x1800251d5  xor     ecx, ecx
0x1800251d7  mov     word ptr [rsp+290h+var_240], cx
0x1800251dc  lea     rcx, [rsp+290h+var_240]; void *
0x1800251e1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800251e6  nop
0x1800251e7  lea     rcx, [rsp+290h+lpData]
0x1800251ec  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x1800251f1  jmp     short loc_180025225
0x1800251f3  lea     rcx, [rsp+290h+lpData]
0x1800251f8  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x1800251fd  xorps   xmm0, xmm0
0x180025200  movups  xmmword ptr [rbx], xmm0
0x180025203  mov     qword ptr [rbx+10h], 0
0x18002520b  mov     qword ptr [rbx+18h], 0
0x180025213  xor     r8d, r8d
0x180025216  lea     rdx, S1
0x18002521d  mov     rcx, rbx
0x180025220  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180025225  mov     rax, rbx
0x180025228  mov     rcx, [rbp+190h+var_10]
0x18002522f  xor     rcx, rsp; StackCookie
0x180025232  call    __security_check_cookie
0x180025237  mov     rbx, [rsp+290h+arg_8]
0x18002523f  add     rsp, 290h
0x180025246  pop     rbp
0x180025247  retn
```
