# Windows::Internal::AssignedAccess::AppLockdownDesktopApplistBuilder::AppListFilterWildcard_Windows::Internal::AssignedAccess::WstringAppData_Windows::Internal::AssignedAccess::HstringAppData__lambda_45ffc4f2b5c120630c5a92d6a69a94fe___

- ea: `0x180043c90`
- end: `0x180043fe8`
- name: `Windows::Internal::AssignedAccess::AppLockdownDesktopApplistBuilder::AppListFilterWildcard_Windows::Internal::AssignedAccess::WstringAppData_Windows::Internal::AssignedAccess::HstringAppData__lambda_45ffc4f2b5c120630c5a92d6a69a94fe___`
- size: `856`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180044aa8`

## callees

- `0x180006640`
- `0x180010c98`
- `0x180014a5c`
- `0x18002001c`
- `0x18003726c`
- `0x1800373e8`
- `0x1800377e8`
- `0x18003b8b4`
- `0x18003bc40`
- `0x180043c90`
- `0x1800440b8`
- `0x18004431c`
- `0x18004447c`
- `0x180044a04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043d6e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043d93`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043d6e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043d93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043d06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043d5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043d7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043da3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043d06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043d5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043d7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043da3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecExW` at `0x180043d4a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecExW` at `0x180043d4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Windows::Internal::AssignedAccess::AppLockdownDesktopApplistBuilder::AppListFilterWildcard_Windows::Internal::AssignedAccess::WstringAppData_Windows::Internal::AssignedAccess::HstringAppData__lambda_45ffc4f2b5c120630c5a92d6a69a94fe___(
        __int64 a1,
        __int64 *a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 v6; // rdi
  __int64 v7; // r12
  __m128i si128; // xmm6
  __int64 v9; // rbx
  __int64 v10; // r15
  PCWSTR StringRawBuffer; // rax
  __int64 v12; // rax
  const WCHAR *v13; // rax
  LPCWSTR v14; // rdx
  PCWSTR v15; // rax
  __int64 v16; // rax
  PCWSTR v17; // rax
  __m128i *v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rax
  __int128 v22; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-D0h]
  __int64 *v24; // [rsp+40h] [rbp-C8h] BYREF
  __int128 v25; // [rsp+48h] [rbp-C0h] BYREF
  __m128i v26; // [rsp+58h] [rbp-B0h]
  _QWORD v27[5]; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v28; // [rsp+90h] [rbp-78h]
  __int64 v29; // [rsp+A0h] [rbp-68h]
  __int64 v30; // [rsp+A8h] [rbp-60h]
  __int128 v31; // [rsp+B0h] [rbp-58h]
  __int64 v32; // [rsp+C0h] [rbp-48h]
  __int64 v33; // [rsp+C8h] [rbp-40h]
  __int128 v34; // [rsp+D0h] [rbp-38h]
  __int64 v35; // [rsp+E0h] [rbp-28h]
  __int64 v36; // [rsp+E8h] [rbp-20h]
  __int64 v37; // [rsp+F0h] [rbp-18h]
  __int128 v38; // [rsp+F8h] [rbp-10h]
  _BYTE v39[32]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v40[32]; // [rsp+128h] [rbp+20h] BYREF
  __int64 v41; // [rsp+148h] [rbp+40h] BYREF
  char v42[32]; // [rsp+150h] [rbp+48h] BYREF
  char v43[32]; // [rsp+170h] [rbp+68h] BYREF
  char v44[32]; // [rsp+190h] [rbp+88h] BYREF
  char v45[32]; // [rsp+1B0h] [rbp+A8h] BYREF
  __int64 v46; // [rsp+1D0h] [rbp+C8h] BYREF
  __int128 v47; // [rsp+1D8h] [rbp+D0h]

  v6 = *a2;
  v7 = a2[1];
  if ( *a2 != v7 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      v22 = 0;
      v23 = 0;
      v9 = *a3;
      v10 = a3[1];
      while ( v9 != v10 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(v9 + 8), 0);
        std::wstring::wstring(v40, StringRawBuffer);
        v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6 + 8);
        std::wstring::wstring(v39, v12);
        std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39);
        v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40);
        if ( !PathMatchSpecExW(v13, v14, 0) )
        {
          v15 = WindowsGetStringRawBuffer(*(HSTRING *)(v9 + 16), 0);
          if ( !(unsigned int)_o__wcsicmp(v15)
            || (WindowsGetStringRawBuffer(*(HSTRING *)(v9 + 16), 0),
                v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6 + 40),
                !(unsigned int)_o__wcsicmp(v16)) )
          {
            v17 = WindowsGetStringRawBuffer(*(HSTRING *)(v9 + 8), 0);
            std::wstring::wstring(&v25, v17);
            v18 = (__m128i *)*((_QWORD *)&v22 + 1);
            if ( *((_QWORD *)&v22 + 1) == v23 )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v22, *((_QWORD *)&v22 + 1), &v25);
            }
            else
            {
              **((_OWORD **)&v22 + 1) = v25;
              v18[1] = v26;
              v26 = si128;
              LOWORD(v25) = 0;
              *((_QWORD *)&v22 + 1) += 32LL;
            }
            std::wstring::_Tidy_deallocate(&v25);
          }
        }
        std::wstring::_Tidy_deallocate(v39);
        std::wstring::_Tidy_deallocate(v40);
        v9 += 64;
      }
      v41 = 3;
      v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6 + 8);
      std::wstring::wstring(v42, v19);
      v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6 + 40);
      std::wstring::wstring(v43, v20);
      std::wstring::wstring(v44, L"*");
      std::wstring::wstring(v45, L"*");
      v46 = 0;
      v47 = 0;
      if ( (__int64)(*((_QWORD *)&v22 + 1) - v22) >> 5 )
      {
        std::vector<std::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned short const *>>::_Buy_nonzero(&v46);
        v24 = &v46;
        *(_QWORD *)&v47 = std::_Uninitialized_copy<std::wstring const *,std::wstring const *,std::allocator<std::wstring>>(
                            v22,
                            *((__int64 *)&v22 + 1),
                            v46);
        v24 = 0;
        std::_Tidy_guard<std::vector<std::wstring>>::~_Tidy_guard<std::vector<std::wstring>>(&v24);
      }
      memset(&v27[1], 0, 24);
      v27[4] = 7;
      LOWORD(v27[1]) = 0;
      v28 = 0;
      v29 = 0;
      v30 = 7;
      LOWORD(v28) = 0;
      v31 = 0;
      v32 = 0;
      v33 = 7;
      LOWORD(v31) = 0;
      v34 = 0;
      v35 = 0;
      v36 = 7;
      LOWORD(v34) = 0;
      v37 = 0;
      v38 = 0;
      Windows::Internal::AssignedAccess::WstringAppDataException::operator=(v27, &v41);
      if ( a4[1] == a4[2] )
      {
        std::vector<Windows::Internal::AssignedAccess::AppData<Windows::Internal::AssignedAccess::WstringAppDataException>>::_Emplace_reallocate<Windows::Internal::AssignedAccess::AppData<Windows::Internal::AssignedAccess::WstringAppDataException>>(
          a4,
          a4[1],
          (__int64)v27);
      }
      else
      {
        std::_Construct_in_place<Windows::Internal::AssignedAccess::AppData<Windows::Internal::AssignedAccess::WstringAppDataException>,Windows::Internal::AssignedAccess::AppData<Windows::Internal::AssignedAccess::WstringAppDataException>>(
          a4[1],
          (__int64)v27);
        a4[1] += 160;
      }
      Windows::Internal::AssignedAccess::WstringAppDataException::~WstringAppDataException((Windows::Internal::AssignedAccess::WstringAppDataException *)v27);
      Windows::Internal::AssignedAccess::WstringAppDataException::~WstringAppDataException((Windows::Internal::AssignedAccess::WstringAppDataException *)&v41);
      std::vector<std::wstring>::_Tidy(&v22);
      v6 += 136;
    }
    while ( v6 != v7 );
  }
  return 0;
}

```

## disassembly

```asm
0x180043c90  mov     rax, rsp
0x180043c93  mov     [rax+8], rbx
0x180043c97  push    rbp
0x180043c98  push    rsi
0x180043c99  push    rdi
0x180043c9a  push    r12
0x180043c9c  push    r13
0x180043c9e  push    r14
0x180043ca0  push    r15
0x180043ca2  lea     rbp, [rax-138h]
0x180043ca9  sub     rsp, 200h
0x180043cb0  movaps  xmmword ptr [rax-48h], xmm6
0x180043cb4  mov     rax, cs:__security_cookie
0x180043cbb  xor     rax, rsp
0x180043cbe  mov     [rbp+130h+var_50], rax
0x180043cc5  mov     rsi, r9
0x180043cc8  mov     r13, r8
0x180043ccb  mov     rdi, [rdx]
0x180043cce  mov     r12, [rdx+8]
0x180043cd2  cmp     rdi, r12
0x180043cd5  jz      loc_180043FB7
0x180043cdb  xor     ebx, ebx
0x180043cdd  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180043ce5  xorps   xmm0, xmm0
0x180043ce8  movdqu  [rsp+230h+var_218+8], xmm0
0x180043cee  mov     [rsp+230h+var_200], rbx
0x180043cf3  mov     rbx, [r13+0]
0x180043cf7  mov     r15, [r13+8]
0x180043cfb  jmp     loc_180043E1B
0x180043d00  xor     edx, edx; length
0x180043d02  mov     rcx, [rbx+8]; string
0x180043d06  call    cs:__imp_WindowsGetStringRawBuffer
0x180043d0c  mov     rdx, rax
0x180043d0f  lea     rcx, [rbp+130h+var_110]
0x180043d13  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043d18  nop
0x180043d19  lea     rcx, [rdi+8]
0x180043d1d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043d22  mov     rdx, rax
0x180043d25  lea     rcx, [rbp+130h+var_130]
0x180043d29  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043d2e  nop
0x180043d2f  lea     rcx, [rbp+130h+var_130]
0x180043d33  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043d38  mov     rdx, rax
0x180043d3b  lea     rcx, [rbp+130h+var_110]
0x180043d3f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043d44  mov     rcx, rax; pszFile
0x180043d47  xor     r8d, r8d; dwFlags
0x180043d4a  call    cs:__imp_PathMatchSpecExW
0x180043d50  test    eax, eax
0x180043d52  jnz     loc_180043E04
0x180043d58  xor     edx, edx; length
0x180043d5a  mov     rcx, [rbx+10h]; string
0x180043d5e  call    cs:__imp_WindowsGetStringRawBuffer
0x180043d64  lea     rdx, asc_1800A7204; "*"
0x180043d6b  mov     rcx, rax
0x180043d6e  call    cs:__imp__o__wcsicmp
0x180043d74  test    eax, eax
0x180043d76  jz      short loc_180043D9D
0x180043d78  xor     edx, edx; length
0x180043d7a  mov     rcx, [rbx+10h]; string
0x180043d7e  call    cs:__imp_WindowsGetStringRawBuffer
0x180043d84  mov     rdx, rax
0x180043d87  lea     rcx, [rdi+28h]
0x180043d8b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043d90  mov     rcx, rax
0x180043d93  call    cs:__imp__o__wcsicmp
0x180043d99  test    eax, eax
0x180043d9b  jnz     short loc_180043E04
0x180043d9d  xor     edx, edx; length
0x180043d9f  mov     rcx, [rbx+8]; string
0x180043da3  call    cs:__imp_WindowsGetStringRawBuffer
0x180043da9  mov     rdx, rax
0x180043dac  lea     rcx, [rsp+230h+var_1F8+8]
0x180043db1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043db6  nop
0x180043db7  mov     rdx, [rsp+230h+var_208]
0x180043dbc  cmp     rdx, [rsp+230h+var_200]
0x180043dc1  jz      short loc_180043DE9
0x180043dc3  movups  xmm0, [rsp+230h+var_1F8+8]
0x180043dc8  movups  xmmword ptr [rdx], xmm0
0x180043dcb  movups  xmm1, xmmword ptr [rsp+230h+var_1E8+8]
0x180043dd0  movups  xmmword ptr [rdx+10h], xmm1
0x180043dd4  movdqu  xmmword ptr [rsp+230h+var_1E8+8], xmm6
0x180043dda  xor     eax, eax
0x180043ddc  mov     word ptr [rsp+230h+var_1F8+8], ax
0x180043de1  add     [rsp+230h+var_208], 20h ; ' '
0x180043de7  jmp     short loc_180043DF9
0x180043de9  lea     r8, [rsp+230h+var_1F8+8]
0x180043dee  lea     rcx, [rsp+230h+var_218+8]
0x180043df3  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180043df8  nop
0x180043df9  lea     rcx, [rsp+230h+var_1F8+8]
0x180043dfe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043e03  nop
0x180043e04  lea     rcx, [rbp+130h+var_130]
0x180043e08  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043e0d  nop
0x180043e0e  lea     rcx, [rbp+130h+var_110]
0x180043e12  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043e17  add     rbx, 40h ; '@'
0x180043e1b  cmp     rbx, r15
0x180043e1e  jnz     loc_180043D00
0x180043e24  mov     [rbp+130h+var_F0], 3
0x180043e2c  lea     rcx, [rdi+8]
0x180043e30  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043e35  mov     rdx, rax
0x180043e38  lea     rcx, [rbp+130h+var_E8]
0x180043e3c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043e41  nop
0x180043e42  lea     rcx, [rdi+28h]
0x180043e46  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043e4b  mov     rdx, rax
0x180043e4e  lea     rcx, [rbp+130h+var_C8]
0x180043e52  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043e57  nop
0x180043e58  lea     rdx, asc_1800A7204; "*"
0x180043e5f  lea     rcx, [rbp+130h+var_A8]
0x180043e66  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043e6b  nop
0x180043e6c  lea     rdx, asc_1800A7204; "*"
0x180043e73  lea     rcx, [rbp+130h+var_88]
0x180043e7a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043e7f  nop
0x180043e80  xor     ebx, ebx
0x180043e82  mov     [rbp+130h+var_68], rbx
0x180043e89  xorps   xmm0, xmm0
0x180043e8c  movdqa  [rbp+130h+var_60], xmm0
0x180043e94  mov     rdx, [rsp+230h+var_208]
0x180043e99  sub     rdx, qword ptr [rsp+230h+var_218+8]
0x180043e9e  sar     rdx, 5
0x180043ea2  test    rdx, rdx
0x180043ea5  jz      short loc_180043EF3
0x180043ea7  lea     rcx, [rbp+130h+var_68]
0x180043eae  call    ?_Buy_nonzero@?$vector@V?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@PEBG@std@@V?$allocator@V?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@PEBG@std@@@2@@std@@AEAAX_K@Z; std::vector<std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ushort const *>>::_Buy_nonzero(unsigned __int64)
0x180043eb3  lea     rax, [rbp+130h+var_68]
0x180043eba  mov     qword ptr [rsp+230h+var_1F8], rax
0x180043ebf  lea     r9, [rbp+130h+var_68]
0x180043ec6  mov     r8, [rbp+130h+var_68]
0x180043ecd  mov     rdx, [rsp+230h+var_208]
0x180043ed2  mov     rcx, qword ptr [rsp+230h+var_218+8]
0x180043ed7  call    ??$_Uninitialized_copy@PEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBV12@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBV10@0PEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Uninitialized_copy<std::wstring const *,std::wstring const *,std::allocator<std::wstring>>(std::wstring const *,std::wstring const *,std::wstring *,std::allocator<std::wstring> &)
0x180043edc  mov     qword ptr [rbp+130h+var_60], rax
0x180043ee3  mov     qword ptr [rsp+230h+var_1F8], rbx
0x180043ee8  lea     rcx, [rsp+230h+var_1F8]
0x180043eed  call    ??1?$_Tidy_guard@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<std::wstring>>::~_Tidy_guard<std::vector<std::wstring>>(void)
0x180043ef2  nop
0x180043ef3  xorps   xmm0, xmm0
0x180043ef6  movups  xmmword ptr [rsp+230h+var_1D0+8], xmm0
0x180043efb  mov     [rsp+230h+var_1B8], rbx
0x180043f00  mov     ecx, 7
0x180043f05  mov     [rbp+130h+var_1B0], rcx
0x180043f09  mov     word ptr [rsp+230h+var_1D0+8], bx
0x180043f0e  movups  [rbp+130h+var_1A8], xmm0
0x180043f12  mov     [rbp+130h+var_198], rbx
0x180043f16  mov     [rbp+130h+var_190], rcx
0x180043f1a  mov     word ptr [rbp+130h+var_1A8], bx
0x180043f1e  movups  [rbp+130h+var_188], xmm0
0x180043f22  mov     [rbp+130h+var_178], rbx
0x180043f26  mov     [rbp+130h+var_170], rcx
0x180043f2a  mov     word ptr [rbp+130h+var_188], bx
0x180043f2e  movups  [rbp+130h+var_168], xmm0
0x180043f32  mov     [rbp+130h+var_158], rbx
0x180043f36  mov     [rbp+130h+var_150], rcx
0x180043f3a  mov     word ptr [rbp+130h+var_168], bx
0x180043f3e  mov     [rbp+130h+var_148], rbx
0x180043f42  movdqa  [rbp+130h+var_140], xmm0
0x180043f47  lea     rdx, [rbp+130h+var_F0]
0x180043f4b  lea     rcx, [rsp+230h+var_1D0]
0x180043f50  call    ??4WstringAppDataException@AssignedAccess@Internal@Windows@@QEAAAEAU0123@$$QEAU0123@@Z; Windows::Internal::AssignedAccess::WstringAppDataException::operator=(Windows::Internal::AssignedAccess::WstringAppDataException &&)
0x180043f55  nop
0x180043f56  mov     rax, [rsi+8]
0x180043f5a  cmp     rax, [rsi+10h]
0x180043f5e  jz      short loc_180043F77
0x180043f60  lea     rdx, [rsp+230h+var_1D0]
0x180043f65  mov     rcx, rax
0x180043f68  call    ??$_Construct_in_place@V?$AppData@UWstringAppDataException@AssignedAccess@Internal@Windows@@@AssignedAccess@Internal@Windows@@V1234@@std@@YAXAEAV?$AppData@UWstringAppDataException@AssignedAccess@Internal@Windows@@@AssignedAccess@Internal@Windows@@$$QEAV1234@@Z; std::_Construct_in_place<Windows::Internal::AssignedAccess::AppData<Windows::Internal::AssignedAccess::WstringAppDataException>,Windows::Internal::AssignedAccess::AppData<Windows::Internal::AssignedAccess::WstringAppDataException>>(Windows::Internal::AssignedAccess::AppData<Windows::Internal::AssignedAccess::WstringAppDataException> &,Windows::Internal::AssignedAccess::AppData<Windows::Internal::AssignedAccess::WstringAppDataException> &&)
0x180043f6d  add     qword ptr [rsi+8], 0A0h
0x180043f75  jmp     short loc_180043F88
0x180043f77  lea     r8, [rsp+230h+var_1D0]
0x180043f7c  mov     rdx, rax
0x180043f7f  mov     rcx, rsi
0x180043f82  call    ??$_Emplace_reallocate@V?$AppData@UWstringAppDataException@AssignedAccess@Internal@Windows@@@AssignedAccess@Internal@Windows@@@?$vector@V?$AppData@UWstringAppDataException@AssignedAccess@Internal@Windows@@@AssignedAccess@Internal@Windows@@V?$allocator@V?$AppData@UWstringAppDataException@AssignedAccess@Internal@Windows@@@AssignedAccess@Internal@Windows@@@std@@@std@@AEAAPEAV?$AppData@UWstringAppDataException@AssignedAccess@Internal@Windows@@@AssignedAccess@Internal@Windows@@QEAV2345@$$QEAV2345@@Z; std::vector<Windows::Internal::AssignedAccess::AppData<Windows::Internal::AssignedAccess::WstringAppDataException>>::_Emplace_reallocate<Windows::Internal::AssignedAccess::AppData<Windows::Internal::AssignedAccess::WstringAppDataException>>(Windows::Internal::AssignedAccess::AppData<Windows::Internal::AssignedAccess::WstringAppDataException> * const,Windows::Internal::AssignedAccess::AppData<Windows::Internal::AssignedAccess::WstringAppDataException> &&)
0x180043f87  nop
0x180043f88  lea     rcx, [rsp+230h+var_1D0]; this
0x180043f8d  call    ??1WstringAppDataException@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::WstringAppDataException::~WstringAppDataException(void)
0x180043f92  nop
0x180043f93  lea     rcx, [rbp+130h+var_F0]; this
0x180043f97  call    ??1WstringAppDataException@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::WstringAppDataException::~WstringAppDataException(void)
0x180043f9c  nop
0x180043f9d  lea     rcx, [rsp+230h+var_218+8]
0x180043fa2  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180043fa7  add     rdi, 88h
0x180043fae  cmp     rdi, r12
0x180043fb1  jnz     loc_180043CE5
0x180043fb7  xor     eax, eax
0x180043fb9  mov     rcx, [rbp+130h+var_50]
0x180043fc0  xor     rcx, rsp; StackCookie
0x180043fc3  call    __security_check_cookie
0x180043fc8  lea     r11, [rsp+230h+var_30]
0x180043fd0  mov     rbx, [r11+40h]
0x180043fd4  movaps  xmm6, xmmword ptr [r11-10h]
0x180043fd9  mov     rsp, r11
0x180043fdc  pop     r15
0x180043fde  pop     r14
0x180043fe0  pop     r13
0x180043fe2  pop     r12
0x180043fe4  pop     rdi
0x180043fe5  pop     rsi
0x180043fe6  pop     rbp
0x180043fe7  retn
```
