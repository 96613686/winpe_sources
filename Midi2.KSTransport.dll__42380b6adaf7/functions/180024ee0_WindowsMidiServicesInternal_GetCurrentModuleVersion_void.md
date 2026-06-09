# WindowsMidiServicesInternal::GetCurrentModuleVersion(void)

- ea: `0x180024ee0`
- end: `0x180025090`
- name: `?GetCurrentModuleVersion@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180025250`

## callees

- `0x180004410`
- `0x18000526c`
- `0x18000c250`
- `0x18000c73c`
- `0x18000f304`
- `0x180024da8`
- `0x180024ee0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180024f32`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180024f32`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180024f47`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180024f47`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180024f87`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180024f87`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180024fbc`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180024fbc`

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
0x180024ee0  mov     [rsp-8+arg_8], rbx
0x180024ee5  push    rbp
0x180024ee6  lea     rbp, [rsp-190h]
0x180024eee  sub     rsp, 290h
0x180024ef5  mov     rax, cs:__security_cookie
0x180024efc  xor     rax, rsp
0x180024eff  mov     [rbp+190h+var_10], rax
0x180024f06  mov     rbx, rcx
0x180024f09  mov     [rsp+290h+lpBuffer], rcx
0x180024f0e  xor     edx, edx; Val
0x180024f10  mov     r8d, 208h; Size
0x180024f16  lea     rcx, [rsp+290h+Filename]; void *
0x180024f1b  call    memset_0
0x180024f20  mov     r8d, 104h; nSize
0x180024f26  lea     rdx, [rsp+290h+Filename]; lpFilename
0x180024f2b  lea     rcx, cs:180000000h; hModule
0x180024f32  call    cs:__imp_GetModuleFileNameW
0x180024f38  test    eax, eax
0x180024f3a  jz      loc_180025045
0x180024f40  xor     edx, edx; lpdwHandle
0x180024f42  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x180024f47  call    cs:__imp_GetFileVersionInfoSizeW
0x180024f4d  test    eax, eax
0x180024f4f  jz      loc_180025045
0x180024f55  xorps   xmm0, xmm0
0x180024f58  movdqu  xmmword ptr [rsp+290h+lpData], xmm0
0x180024f5e  mov     [rsp+290h+var_250], 0
0x180024f67  mov     edx, eax
0x180024f69  lea     rcx, [rsp+290h+lpData]
0x180024f6e  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180024f73  mov     r9, [rsp+290h+lpData]; lpData
0x180024f78  mov     r8d, dword ptr [rsp+290h+lpData+8]
0x180024f7d  sub     r8d, r9d; dwLen
0x180024f80  xor     edx, edx; dwHandle
0x180024f82  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x180024f87  call    cs:__imp_GetFileVersionInfoW
0x180024f8d  test    eax, eax
0x180024f8f  jz      loc_18002503B
0x180024f95  mov     [rsp+290h+lpBuffer], 0
0x180024f9e  mov     [rsp+290h+puLen], 0
0x180024fa6  lea     r9, [rsp+290h+puLen]; puLen
0x180024fab  lea     r8, [rsp+290h+lpBuffer]; lplpBuffer
0x180024fb0  lea     rdx, SubBlock; "\\StringFileInfo\\040904B0\\FileVersion"
0x180024fb7  mov     rcx, [rsp+290h+lpData]; pBlock
0x180024fbc  call    cs:__imp_VerQueryValueW
0x180024fc2  test    eax, eax
0x180024fc4  jz      short loc_18002503B
0x180024fc6  xorps   xmm0, xmm0
0x180024fc9  movups  [rsp+290h+var_240], xmm0
0x180024fce  xorps   xmm1, xmm1
0x180024fd1  movdqu  [rsp+290h+var_230], xmm1
0x180024fd7  mov     r8d, [rsp+290h+puLen]
0x180024fdc  dec     r8d
0x180024fdf  mov     rdx, [rsp+290h+lpBuffer]
0x180024fe4  lea     rcx, [rsp+290h+var_240]
0x180024fe9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180024fee  mov     qword ptr [rbx+10h], 0
0x180024ff6  mov     qword ptr [rbx+18h], 0
0x180024ffe  movups  xmm0, [rsp+290h+var_240]
0x180025003  movups  xmmword ptr [rbx], xmm0
0x180025006  movups  xmm1, [rsp+290h+var_230]
0x18002500b  movups  xmmword ptr [rbx+10h], xmm1
0x18002500f  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180025017  movdqu  [rsp+290h+var_230], xmm0
0x18002501d  xor     ecx, ecx
0x18002501f  mov     word ptr [rsp+290h+var_240], cx
0x180025024  lea     rcx, [rsp+290h+var_240]; void *
0x180025029  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002502e  nop
0x18002502f  lea     rcx, [rsp+290h+lpData]
0x180025034  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x180025039  jmp     short loc_18002506D
0x18002503b  lea     rcx, [rsp+290h+lpData]
0x180025040  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x180025045  xorps   xmm0, xmm0
0x180025048  movups  xmmword ptr [rbx], xmm0
0x18002504b  mov     qword ptr [rbx+10h], 0
0x180025053  mov     qword ptr [rbx+18h], 0
0x18002505b  xor     r8d, r8d
0x18002505e  lea     rdx, S1
0x180025065  mov     rcx, rbx
0x180025068  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002506d  mov     rax, rbx
0x180025070  mov     rcx, [rbp+190h+var_10]
0x180025077  xor     rcx, rsp; StackCookie
0x18002507a  call    __security_check_cookie
0x18002507f  mov     rbx, [rsp+290h+arg_8]
0x180025087  add     rsp, 290h
0x18002508e  pop     rbp
0x18002508f  retn
```
