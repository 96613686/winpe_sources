# WindowsMidiServicesInternal::GetCurrentModuleVersion(void)

- ea: `0x180011630`
- end: `0x1800117e0`
- name: `?GetCurrentModuleVersion@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800119a0`

## callees

- `0x1800033d0`
- `0x180004170`
- `0x18000b7fc`
- `0x18000c4c0`
- `0x18001148c`
- `0x1800115c4`
- `0x180011630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180011682`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180011682`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x1800116d7`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x1800116d7`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180011697`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180011697`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001170c`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001170c`

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
0x180011630  mov     [rsp-8+arg_8], rbx
0x180011635  push    rbp
0x180011636  lea     rbp, [rsp-190h]
0x18001163e  sub     rsp, 290h
0x180011645  mov     rax, cs:__security_cookie
0x18001164c  xor     rax, rsp
0x18001164f  mov     [rbp+190h+var_10], rax
0x180011656  mov     rbx, rcx
0x180011659  mov     [rsp+290h+lpBuffer], rcx
0x18001165e  xor     edx, edx; Val
0x180011660  mov     r8d, 208h; Size
0x180011666  lea     rcx, [rsp+290h+Filename]; void *
0x18001166b  call    memset_0
0x180011670  mov     r8d, 104h; nSize
0x180011676  lea     rdx, [rsp+290h+Filename]; lpFilename
0x18001167b  lea     rcx, cs:180000000h; hModule
0x180011682  call    cs:__imp_GetModuleFileNameW
0x180011688  test    eax, eax
0x18001168a  jz      loc_180011795
0x180011690  xor     edx, edx; lpdwHandle
0x180011692  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x180011697  call    cs:__imp_GetFileVersionInfoSizeW
0x18001169d  test    eax, eax
0x18001169f  jz      loc_180011795
0x1800116a5  xorps   xmm0, xmm0
0x1800116a8  movdqu  xmmword ptr [rsp+290h+lpData], xmm0
0x1800116ae  mov     [rsp+290h+var_250], 0
0x1800116b7  mov     edx, eax
0x1800116b9  lea     rcx, [rsp+290h+lpData]
0x1800116be  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800116c3  mov     r9, [rsp+290h+lpData]; lpData
0x1800116c8  mov     r8d, dword ptr [rsp+290h+lpData+8]
0x1800116cd  sub     r8d, r9d; dwLen
0x1800116d0  xor     edx, edx; dwHandle
0x1800116d2  lea     rcx, [rsp+290h+Filename]; lptstrFilename
0x1800116d7  call    cs:__imp_GetFileVersionInfoW
0x1800116dd  test    eax, eax
0x1800116df  jz      loc_18001178B
0x1800116e5  mov     [rsp+290h+lpBuffer], 0
0x1800116ee  mov     [rsp+290h+puLen], 0
0x1800116f6  lea     r9, [rsp+290h+puLen]; puLen
0x1800116fb  lea     r8, [rsp+290h+lpBuffer]; lplpBuffer
0x180011700  lea     rdx, SubBlock; "\\StringFileInfo\\040904B0\\FileVersion"
0x180011707  mov     rcx, [rsp+290h+lpData]; pBlock
0x18001170c  call    cs:__imp_VerQueryValueW
0x180011712  test    eax, eax
0x180011714  jz      short loc_18001178B
0x180011716  xorps   xmm0, xmm0
0x180011719  movups  [rsp+290h+var_240], xmm0
0x18001171e  xorps   xmm1, xmm1
0x180011721  movdqu  [rsp+290h+var_230], xmm1
0x180011727  mov     r8d, [rsp+290h+puLen]
0x18001172c  dec     r8d
0x18001172f  mov     rdx, [rsp+290h+lpBuffer]
0x180011734  lea     rcx, [rsp+290h+var_240]
0x180011739  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001173e  mov     qword ptr [rbx+10h], 0
0x180011746  mov     qword ptr [rbx+18h], 0
0x18001174e  movups  xmm0, [rsp+290h+var_240]
0x180011753  movups  xmmword ptr [rbx], xmm0
0x180011756  movups  xmm1, [rsp+290h+var_230]
0x18001175b  movups  xmmword ptr [rbx+10h], xmm1
0x18001175f  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180011767  movdqu  [rsp+290h+var_230], xmm0
0x18001176d  xor     ecx, ecx
0x18001176f  mov     word ptr [rsp+290h+var_240], cx
0x180011774  lea     rcx, [rsp+290h+var_240]
0x180011779  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001177e  nop
0x18001177f  lea     rcx, [rsp+290h+lpData]
0x180011784  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011789  jmp     short loc_1800117BD
0x18001178b  lea     rcx, [rsp+290h+lpData]
0x180011790  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011795  xorps   xmm0, xmm0
0x180011798  movups  xmmword ptr [rbx], xmm0
0x18001179b  mov     qword ptr [rbx+10h], 0
0x1800117a3  mov     qword ptr [rbx+18h], 0
0x1800117ab  xor     r8d, r8d
0x1800117ae  lea     rdx, qword_1800159A0
0x1800117b5  mov     rcx, rbx
0x1800117b8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800117bd  mov     rax, rbx
0x1800117c0  mov     rcx, [rbp+190h+var_10]
0x1800117c7  xor     rcx, rsp; StackCookie
0x1800117ca  call    __security_check_cookie
0x1800117cf  mov     rbx, [rsp+290h+arg_8]
0x1800117d7  add     rsp, 290h
0x1800117de  pop     rbp
0x1800117df  retn
```
