# WindowsMidiServicesInternal::GetCurrentModuleVersionCompanyName(void)

- ea: `0x180044f44`
- end: `0x1800450f4`
- name: `?GetCurrentModuleVersionCompanyName@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180045100`

## callees

- `0x180005020`
- `0x180005e9c`
- `0x18000d430`
- `0x18000d920`
- `0x180013118`
- `0x18002fbd8`
- `0x180044f44`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180044f96`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180044f96`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180044feb`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180044feb`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180044fab`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180044fab`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180045020`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180045020`

## string_xrefs

- `0x180045014`: `\StringFileInfo\040904B0\CompanyName`

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
0x180044f44  mov     [rsp-8+arg_8], rbx
0x180044f49  push    rbp
0x180044f4a  lea     rbp, [rsp-190h]
0x180044f52  sub     rsp, 290h
0x180044f59  mov     rax, cs:__security_cookie
0x180044f60  xor     rax, rsp
0x180044f63  mov     [rbp+190h+var_10], rax
0x180044f6a  mov     rbx, rcx
0x180044f6d  mov     [rsp+290h+lpBuffer], rcx
0x180044f72  xor     edx, edx; Val
0x180044f74  mov     r8d, 208h; Size
0x180044f7a  lea     rcx, [rsp+290h+Filename]; void *
0x180044f7f  call    memset_0
0x180044f84  mov     r8d, 104h; nSize
0x180044f8a  lea     rdx, [rsp+290h+Filename]; lpFilename
0x180044f8f  lea     rcx, cs:180000000h; hModule
0x180044f96  call    cs:__imp_GetModuleFileNameW
0x180044f9c  test    eax, eax
0x180044f9e  jz      loc_1800450A9
0x180044fa4  xor     edx, edx; lpdwHandle
0x180044fa6  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x180044fab  call    cs:__imp_GetFileVersionInfoSizeW
0x180044fb1  test    eax, eax
0x180044fb3  jz      loc_1800450A9
0x180044fb9  xorps   xmm0, xmm0
0x180044fbc  movdqu  xmmword ptr [rsp+290h+lpData], xmm0
0x180044fc2  mov     [rsp+290h+var_250], 0
0x180044fcb  mov     edx, eax
0x180044fcd  lea     rcx, [rsp+290h+lpData]
0x180044fd2  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180044fd7  mov     r9, [rsp+290h+lpData]; lpData
0x180044fdc  mov     r8d, dword ptr [rsp+290h+lpData+8]
0x180044fe1  sub     r8d, r9d; dwLen
0x180044fe4  xor     edx, edx; dwHandle
0x180044fe6  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x180044feb  call    cs:__imp_GetFileVersionInfoW
0x180044ff1  test    eax, eax
0x180044ff3  jz      loc_18004509F
0x180044ff9  mov     [rsp+290h+lpBuffer], 0
0x180045002  mov     [rsp+290h+puLen], 0
0x18004500a  lea     r9, [rsp+290h+puLen]; puLen
0x18004500f  lea     r8, [rsp+290h+lpBuffer]; lplpBuffer
0x180045014  lea     rdx, aStringfileinfo; "\\StringFileInfo\\040904B0\\CompanyName"
0x18004501b  mov     rcx, [rsp+290h+lpData]; pBlock
0x180045020  call    cs:__imp_VerQueryValueW
0x180045026  test    eax, eax
0x180045028  jz      short loc_18004509F
0x18004502a  xorps   xmm0, xmm0
0x18004502d  movups  [rsp+290h+var_240], xmm0
0x180045032  xorps   xmm1, xmm1
0x180045035  movdqu  [rsp+290h+var_230], xmm1
0x18004503b  mov     r8d, [rsp+290h+puLen]
0x180045040  dec     r8d
0x180045043  mov     rdx, [rsp+290h+lpBuffer]
0x180045048  lea     rcx, [rsp+290h+var_240]
0x18004504d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180045052  mov     qword ptr [rbx+10h], 0
0x18004505a  mov     qword ptr [rbx+18h], 0
0x180045062  movups  xmm0, [rsp+290h+var_240]
0x180045067  movups  xmmword ptr [rbx], xmm0
0x18004506a  movups  xmm1, [rsp+290h+var_230]
0x18004506f  movups  xmmword ptr [rbx+10h], xmm1
0x180045073  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18004507b  movdqu  [rsp+290h+var_230], xmm0
0x180045081  xor     ecx, ecx
0x180045083  mov     word ptr [rsp+290h+var_240], cx
0x180045088  lea     rcx, [rsp+290h+var_240]; void *
0x18004508d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180045092  nop
0x180045093  lea     rcx, [rsp+290h+lpData]
0x180045098  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x18004509d  jmp     short loc_1800450D1
0x18004509f  lea     rcx, [rsp+290h+lpData]
0x1800450a4  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x1800450a9  xorps   xmm0, xmm0
0x1800450ac  movups  xmmword ptr [rbx], xmm0
0x1800450af  mov     qword ptr [rbx+10h], 0
0x1800450b7  mov     qword ptr [rbx+18h], 0
0x1800450bf  xor     r8d, r8d
0x1800450c2  lea     rdx, S1
0x1800450c9  mov     rcx, rbx
0x1800450cc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800450d1  mov     rax, rbx
0x1800450d4  mov     rcx, [rbp+190h+var_10]
0x1800450db  xor     rcx, rsp; StackCookie
0x1800450de  call    __security_check_cookie
0x1800450e3  mov     rbx, [rsp+290h+arg_8]
0x1800450eb  add     rsp, 290h
0x1800450f2  pop     rbp
0x1800450f3  retn
```
