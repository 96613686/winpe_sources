# NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180074ba0`
- end: `0x180074d05`
- name: `?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z`
- size: `357`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180075244`

## callees

- `0x18000d62c`
- `0x180069140`
- `0x180070bd4`
- `0x1800721d0`
- `0x18007373c`
- `0x180074ba0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074c89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074cf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074c89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074cf0`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180074bdf`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180074c5d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180074bdf`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180074c5d`

## string_xrefs

- `0x180074c08`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180074c6b`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180074cb1`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::GetNgcStateSeparatedRegistryLocation(
        NgcUtils *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  int PersistedRegistryLocationW; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HLOCAL v9; // rbx
  unsigned int v10; // eax
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // r8
  unsigned int v13; // edi
  int v14; // eax
  int v15; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  HLOCAL hMem; // [rsp+58h] [rbp+28h] BYREF
  unsigned __int16 *v18; // [rsp+60h] [rbp+30h] BYREF

  HIDWORD(v18) = HIDWORD(a3);
  hMem = a2;
  LODWORD(v18) = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"WinBio",
                                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WinBio\\",
                                 0,
                                 0);
  v6 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW != 234 )
  {
    if ( PersistedRegistryLocationW > 0 )
      v6 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( (v6 & 0x80000000) == 0 )
      return v6;
    v7 = 182;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
      (const char *)v6,
      (int)&v18);
    return v6;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, (unsigned int)v18);
  v9 = hMem;
  if ( !hMem )
  {
    v6 = -2147024882;
    v7 = 185;
    goto LABEL_6;
  }
  v10 = GetPersistedRegistryLocationW(
          L"WinBio",
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WinBio\\",
          hMem,
          (unsigned int)v18);
  if ( v10 )
  {
    v13 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xC0,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
            (const char *)v10,
            (unsigned int)&v18);
LABEL_12:
    if ( v9 )
      LocalFree(v9);
    return v13;
  }
  hMem = 0;
  v14 = NgcUtils::CombineSeparateStrings((NgcUtils *)v9, v11, v12, (const unsigned __int16 *)&hMem, &v18);
  v13 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
      (const char *)(unsigned int)v14,
      v15);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    goto LABEL_12;
  }
  *(_QWORD *)a4 = hMem;
  hMem = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
  if ( v9 )
    LocalFree(v9);
  return 0;
}

```

## disassembly

```asm
0x180074ba0  mov     r11, rsp
0x180074ba3  mov     [r11+8], rbx
0x180074ba7  mov     [r11+18h], r8
0x180074bab  mov     [r11+10h], rdx
0x180074baf  push    rbp
0x180074bb0  push    rsi
0x180074bb1  push    rdi
0x180074bb2  mov     rbp, rsp
0x180074bb5  sub     rsp, 30h
0x180074bb9  mov     rsi, r9
0x180074bbc  mov     dword ptr [rbp+arg_10], 0
0x180074bc3  lea     rax, [rbp+arg_10]
0x180074bc7  xor     r9d, r9d
0x180074bca  xor     r8d, r8d
0x180074bcd  mov     [r11-28h], rax
0x180074bd1  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180074bd8  lea     rcx, aWinbio; "WinBio"
0x180074bdf  call    cs:__imp_GetPersistedRegistryLocationW
0x180074be5  mov     ebx, eax
0x180074be7  cmp     eax, 0EAh
0x180074bec  jz      short loc_180074C1E
0x180074bee  test    eax, eax
0x180074bf0  jle     short loc_180074BFB
0x180074bf2  movzx   ebx, ax
0x180074bf5  or      ebx, 80070000h
0x180074bfb  test    ebx, ebx
0x180074bfd  jns     short loc_180074C17
0x180074bff  mov     edx, 0B6h; void *
0x180074c04  mov     rcx, [rbp+18h]; this
0x180074c08  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180074c0f  mov     r9d, ebx; char *
0x180074c12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074c17  mov     eax, ebx
0x180074c19  jmp     loc_180074CF8
0x180074c1e  mov     edx, dword ptr [rbp+arg_10]
0x180074c21  lea     rcx, [rbp+hMem]
0x180074c25  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180074c2a  mov     rbx, [rbp+hMem]
0x180074c2e  test    rbx, rbx
0x180074c31  jnz     short loc_180074C3F
0x180074c33  mov     ebx, 8007000Eh
0x180074c38  mov     edx, 0B9h
0x180074c3d  jmp     short loc_180074C04
0x180074c3f  mov     r9d, dword ptr [rbp+arg_10]
0x180074c43  lea     rax, [rbp+arg_10]
0x180074c47  mov     r8, rbx
0x180074c4a  mov     qword ptr [rsp+30h+var_10], rax; int
0x180074c4f  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180074c56  lea     rcx, aWinbio; "WinBio"
0x180074c5d  call    cs:__imp_GetPersistedRegistryLocationW
0x180074c63  test    eax, eax
0x180074c65  jz      short loc_180074C93
0x180074c67  mov     rcx, [rbp+18h]; this
0x180074c6b  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180074c72  mov     r9d, eax; char *
0x180074c75  mov     edx, 0C0h; void *
0x180074c7a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180074c7f  mov     edi, eax
0x180074c81  test    rbx, rbx
0x180074c84  jz      short loc_180074C8F
0x180074c86  mov     rcx, rbx; hMem
0x180074c89  call    cs:__imp_LocalFree
0x180074c8f  mov     eax, edi
0x180074c91  jmp     short loc_180074CF8
0x180074c93  lea     r9, [rbp+hMem]; unsigned __int16 *
0x180074c97  mov     [rbp+hMem], 0
0x180074c9f  mov     rcx, rbx; this
0x180074ca2  call    ?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)
0x180074ca7  mov     edi, eax
0x180074ca9  test    eax, eax
0x180074cab  jns     short loc_180074CD0
0x180074cad  mov     rcx, [rbp+18h]; this
0x180074cb1  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180074cb8  mov     r9d, eax; char *
0x180074cbb  mov     edx, 0C9h; void *
0x180074cc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074cc5  lea     rcx, [rbp+hMem]
0x180074cc9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180074cce  jmp     short loc_180074C81
0x180074cd0  mov     rax, [rbp+hMem]
0x180074cd4  lea     rcx, [rbp+hMem]
0x180074cd8  mov     [rsi], rax
0x180074cdb  mov     [rbp+hMem], 0
0x180074ce3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180074ce8  test    rbx, rbx
0x180074ceb  jz      short loc_180074CF6
0x180074ced  mov     rcx, rbx; hMem
0x180074cf0  call    cs:__imp_LocalFree
0x180074cf6  xor     eax, eax
0x180074cf8  mov     rbx, [rsp+30h+arg_0]
0x180074cfd  add     rsp, 30h
0x180074d01  pop     rdi
0x180074d02  pop     rsi
0x180074d03  pop     rbp
0x180074d04  retn
```
