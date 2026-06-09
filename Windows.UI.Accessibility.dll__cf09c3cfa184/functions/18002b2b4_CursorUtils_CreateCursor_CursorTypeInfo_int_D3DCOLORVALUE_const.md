# CursorUtils::CreateCursor(CursorTypeInfo,int,_D3DCOLORVALUE const &)

- ea: `0x18002b2b4`
- end: `0x18002b5ee`
- name: `?CreateCursor@CursorUtils@@CAXVCursorTypeInfo@@HAEBU_D3DCOLORVALUE@@@Z`
- size: `826`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002b1e0`

## callees

- `0x180003980`
- `0x18000a6e0`
- `0x18000cf94`
- `0x18000df9c`
- `0x18000ea34`
- `0x180010dec`
- `0x1800126e4`
- `0x180012970`
- `0x1800166d4`
- `0x180016770`
- `0x18002a6a4`
- `0x18002a754`
- `0x18002a78c`
- `0x18002ab30`
- `0x18002b2b4`
- `0x18002b67c`
- `0x18002b994`
- `0x18002bdbc`
- `0x18002c008`
- `0x18002c060`
- `0x18002c448`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b316`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b316`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002b452`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002b452`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b4b1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b4b1`
- `d2d1!__imp_D2D1CreateFactory` at `0x18002b35a`
- `d2d1!__imp_D2D1CreateFactory` at `0x18002b35a`

## string_xrefs

- `0x18002b327`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`
- `0x18002b36b`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`
- `0x18002b4e3`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CursorUtils::CreateCursor(_OWORD *a1, int a2, _OWORD *a3)
{
  HRESULT v6; // eax
  HRESULT v7; // eax
  __int64 i; // rbx
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 CursorOutputPath; // rax
  const WCHAR *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  const WCHAR *v16; // rax
  HANDLE FileW; // rax
  const char *v18; // r9
  HANDLE v19; // rsi
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned __int8 IsInvertedColor; // al
  int v23; // r9d
  SvgToBitmapConverter *j; // rbx
  SvgToBitmapConverter *v25; // rdi
  int ppv; // [rsp+28h] [rbp-A9h]
  SvgToBitmapConverter *v28[2]; // [rsp+48h] [rbp-89h] BYREF
  SvgToBitmapConverter *v29; // [rsp+58h] [rbp-79h]
  void *ppIFactory; // [rsp+60h] [rbp-71h] BYREF
  LPVOID v31; // [rsp+68h] [rbp-69h] BYREF
  HANDLE hFile[3]; // [rsp+70h] [rbp-61h] BYREF
  int v33[4]; // [rsp+88h] [rbp-49h] BYREF
  __int128 v34; // [rsp+98h] [rbp-39h]
  _OWORD v35[2]; // [rsp+A8h] [rbp-29h] BYREF
  _BYTE v36[32]; // [rsp+C8h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+5Fh]

  v31 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  v6 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &v31);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x20D,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  ppIFactory = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppIFactory);
  v7 = D2D1CreateFactory(D2D1_FACTORY_TYPE_SINGLE_THREADED, &GUID_bb12d362_daee_4b9a_aa1d_14ba401cfa1f, 0, &ppIFactory);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x211,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      (const char *)(unsigned int)v7,
      ppv);
  std::vector<bond::blob>::vector<bond::blob>(v28);
  for ( i = 0; i != 5; ++i )
  {
    v9 = (int)((double)a2 * *(double *)&qword_18003B620[i]);
    if ( v9 <= 256 )
    {
      v35[0] = *a3;
      *(_OWORD *)v33 = *a1;
      v34 = a1[1];
      v10 = SvgToBitmapConverter::SvgToBitmapConverter(hFile, v33, v31, ppIFactory, v9, v35);
      if ( v28[1] == v29 )
      {
        std::vector<SvgToBitmapConverter>::_Emplace_reallocate<SvgToBitmapConverter>(v28, v28[1], v10);
      }
      else
      {
        std::_Construct_in_place<SvgToBitmapConverter,SvgToBitmapConverter>(v28[1], v10);
        v28[1] = (SvgToBitmapConverter *)((char *)v28[1] + 16);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(hFile);
    }
  }
  v11 = std::wstring::wstring(v33, &sz);
  CursorOutputPath = anonymous_namespace_::GetCursorOutputPath(v35, v11);
  v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(CursorOutputPath);
  CreateDirectoryW(v13, 0);
  std::wstring::_Tidy_deallocate(v35);
  hFile[0] = 0;
  v14 = std::wstring::wstring(v33, *((_QWORD *)a1 + 2));
  v15 = anonymous_namespace_::GetCursorOutputPath(v36, v14);
  v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
  FileW = CreateFileW(v16, 0xC0000000, 0, 0, 2u, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    hFile,
    FileW);
  std::wstring::_Tidy_deallocate(v36);
  v19 = hFile[0];
  if ( (unsigned __int64)hFile[0] - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x22D,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      v18);
  anonymous_namespace_::WriteCursorFileInfoBytes((v28[1] - v28[0]) >> 4, hFile[0]);
  v35[0] = *a3;
  *(_OWORD *)v33 = *a1;
  v34 = a1[1];
  IsInvertedColor = anonymous_namespace_::IsInvertedColor(v35, v20, v21, (v28[1] - v28[0]) >> 4);
  anonymous_namespace_::WriteCursorHeaderBytes((int)v33, a2, IsInvertedColor, v23, v19);
  v25 = v28[1];
  for ( j = v28[0]; j != v25; j = (SvgToBitmapConverter *)((char *)j + 16) )
    SvgToBitmapConverter::WriteBitmapBytes(j, v19);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hFile);
  if ( v28[0] )
  {
    std::_Destroy_range<std::allocator<SvgToBitmapConverter>>(v28[0], v28[1]);
    std::_Deallocate<16>(v28[0], (v29 - v28[0]) & 0xFFFFFFFFFFFFFFF0uLL);
    *(_OWORD *)v28 = 0;
    v29 = 0;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppIFactory);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
}

```

## disassembly

```asm
0x18002b2b4  mov     rax, rsp
0x18002b2b7  mov     [rax+20h], rbx
0x18002b2bb  push    rbp
0x18002b2bc  push    rsi
0x18002b2bd  push    rdi
0x18002b2be  push    r14
0x18002b2c0  push    r15
0x18002b2c2  lea     rbp, [rax-5Fh]
0x18002b2c6  sub     rsp, 100h
0x18002b2cd  movaps  xmmword ptr [rax-38h], xmm6
0x18002b2d1  mov     rax, cs:__security_cookie
0x18002b2d8  xor     rax, rsp
0x18002b2db  mov     [rbp+57h+var_40], rax
0x18002b2df  mov     r15, r8
0x18002b2e2  mov     r14d, edx
0x18002b2e5  mov     rdi, rcx
0x18002b2e8  mov     [rbp+57h+var_C0], 0
0x18002b2f0  lea     rcx, [rbp+57h+var_C0]
0x18002b2f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b2f9  lea     rax, [rbp+57h+var_C0]
0x18002b2fd  mov     [rsp+120h+ppv], rax; int
0x18002b302  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18002b309  xor     edx, edx; pUnkOuter
0x18002b30b  lea     r8d, [rdx+1]; dwClsContext
0x18002b30f  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18002b316  call    cs:__imp_CoCreateInstance
0x18002b31c  mov     rcx, [rbp+5Fh]; this
0x18002b320  test    eax, eax
0x18002b322  jns     short loc_18002B339
0x18002b324  mov     r9d, eax; char *
0x18002b327  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002b32e  mov     edx, 20Dh; void *
0x18002b333  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002b339  mov     [rbp+57h+ppIFactory], 0
0x18002b341  lea     rcx, [rbp+57h+ppIFactory]
0x18002b345  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b34a  lea     r9, [rbp+57h+ppIFactory]; ppIFactory
0x18002b34e  xor     r8d, r8d; pFactoryOptions
0x18002b351  lea     rdx, _GUID_bb12d362_daee_4b9a_aa1d_14ba401cfa1f; riid
0x18002b358  xor     ecx, ecx; factoryType
0x18002b35a  call    cs:__imp_D2D1CreateFactory
0x18002b360  mov     rcx, [rbp+5Fh]; this
0x18002b364  test    eax, eax
0x18002b366  jns     short loc_18002B37D
0x18002b368  mov     r9d, eax; char *
0x18002b36b  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002b372  mov     edx, 211h; void *
0x18002b377  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002b37d  lea     rcx, [rsp+120h+var_E8+8]
0x18002b382  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x18002b387  nop
0x18002b388  movd    xmm6, r14d
0x18002b38d  cvtdq2pd xmm6, xmm6
0x18002b391  xor     ebx, ebx
0x18002b393  lea     rax, qword_18003B620
0x18002b39a  movaps  xmm0, xmm6
0x18002b39d  mulsd   xmm0, qword ptr [rax+rbx*8]
0x18002b3a2  cvttsd2si eax, xmm0
0x18002b3a6  cmp     eax, 100h
0x18002b3ab  jg      short loc_18002B41C
0x18002b3ad  movups  xmm0, xmmword ptr [r15]
0x18002b3b1  movdqu  [rbp+57h+var_80], xmm0
0x18002b3b6  movaps  xmm1, xmmword ptr [rdi]
0x18002b3b9  movaps  xmmword ptr [rbp+57h+var_A0], xmm1
0x18002b3bd  movaps  xmm0, xmmword ptr [rdi+10h]
0x18002b3c1  movaps  [rbp+57h+var_90], xmm0
0x18002b3c5  lea     rcx, [rbp+57h+var_80]
0x18002b3c9  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rcx
0x18002b3ce  mov     dword ptr [rsp+120h+ppv], eax
0x18002b3d2  mov     r9, [rbp+57h+ppIFactory]
0x18002b3d6  mov     r8, [rbp+57h+var_C0]
0x18002b3da  lea     rdx, [rbp+57h+var_A0]
0x18002b3de  lea     rcx, [rbp+57h+hFile]
0x18002b3e2  call    ??0SvgToBitmapConverter@@QEAA@VCursorTypeInfo@@PEAUIWICImagingFactory@@PEAUID2D1Factory1@@HU_D3DCOLORVALUE@@@Z; SvgToBitmapConverter::SvgToBitmapConverter(CursorTypeInfo,IWICImagingFactory *,ID2D1Factory1 *,int,_D3DCOLORVALUE)
0x18002b3e7  mov     rdx, rax
0x18002b3ea  mov     rcx, [rsp+120h+var_D8]
0x18002b3ef  cmp     rcx, [rbp+57h+var_D0]
0x18002b3f3  jz      short loc_18002B402
0x18002b3f5  call    ??$_Construct_in_place@VSvgToBitmapConverter@@V1@@std@@YAXAEAVSvgToBitmapConverter@@$$QEAV1@@Z; std::_Construct_in_place<SvgToBitmapConverter,SvgToBitmapConverter>(SvgToBitmapConverter &,SvgToBitmapConverter &&)
0x18002b3fa  add     [rsp+120h+var_D8], 10h
0x18002b400  jmp     short loc_18002B413
0x18002b402  mov     r8, rdx
0x18002b405  mov     rdx, rcx
0x18002b408  lea     rcx, [rsp+120h+var_E8+8]
0x18002b40d  call    ??$_Emplace_reallocate@VSvgToBitmapConverter@@@?$vector@VSvgToBitmapConverter@@V?$allocator@VSvgToBitmapConverter@@@std@@@std@@AEAAPEAVSvgToBitmapConverter@@QEAV2@$$QEAV2@@Z; std::vector<SvgToBitmapConverter>::_Emplace_reallocate<SvgToBitmapConverter>(SvgToBitmapConverter * const,SvgToBitmapConverter &&)
0x18002b412  nop
0x18002b413  lea     rcx, [rbp+57h+hFile]
0x18002b417  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b41c  inc     rbx
0x18002b41f  cmp     rbx, 5
0x18002b423  jnz     loc_18002B393
0x18002b429  lea     rdx, sz
0x18002b430  lea     rcx, [rbp+57h+var_A0]
0x18002b434  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002b439  mov     rdx, rax
0x18002b43c  lea     rcx, [rbp+57h+var_80]
0x18002b440  call    _anonymous_namespace___GetCursorOutputPath
0x18002b445  mov     rcx, rax
0x18002b448  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b44d  xor     edx, edx; lpSecurityAttributes
0x18002b44f  mov     rcx, rax; lpPathName
0x18002b452  call    cs:__imp_CreateDirectoryW
0x18002b458  lea     rcx, [rbp+57h+var_80]
0x18002b45c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b461  mov     [rbp+57h+hFile], 0
0x18002b469  mov     rdx, [rdi+10h]
0x18002b46d  lea     rcx, [rbp+57h+var_A0]
0x18002b471  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002b476  mov     rdx, rax
0x18002b479  lea     rcx, [rbp+57h+var_60]
0x18002b47d  call    _anonymous_namespace___GetCursorOutputPath
0x18002b482  mov     rcx, rax
0x18002b485  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b48a  mov     [rsp+120h+hTemplateFile], 0; hTemplateFile
0x18002b493  mov     [rsp+120h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18002b49b  mov     dword ptr [rsp+120h+ppv], 2; dwCreationDisposition
0x18002b4a3  xor     r9d, r9d; lpSecurityAttributes
0x18002b4a6  xor     r8d, r8d; dwShareMode
0x18002b4a9  mov     edx, 0C0000000h; dwDesiredAccess
0x18002b4ae  mov     rcx, rax; lpFileName
0x18002b4b1  call    cs:__imp_CreateFileW
0x18002b4b7  mov     rdx, rax
0x18002b4ba  lea     rcx, [rbp+57h+hFile]
0x18002b4be  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002b4c3  lea     rcx, [rbp+57h+var_60]
0x18002b4c7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b4cc  mov     rsi, [rbp+57h+hFile]
0x18002b4d0  lea     rax, [rsi-1]
0x18002b4d4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002b4d8  setnbe  al
0x18002b4db  mov     rcx, [rbp+5Fh]; this
0x18002b4df  test    al, al
0x18002b4e1  jz      short loc_18002B4F5
0x18002b4e3  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002b4ea  mov     edx, 22Dh; void *
0x18002b4ef  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002b4f5  mov     rcx, [rsp+120h+var_D8]
0x18002b4fa  sub     rcx, [rsp+120h+var_E8+8]
0x18002b4ff  sar     rcx, 4
0x18002b503  mov     rdx, rsi
0x18002b506  call    _anonymous_namespace___WriteCursorFileInfoBytes
0x18002b50b  movups  xmm0, xmmword ptr [r15]
0x18002b50f  movdqu  [rbp+57h+var_80], xmm0
0x18002b514  movaps  xmm1, xmmword ptr [rdi]
0x18002b517  movaps  xmmword ptr [rbp+57h+var_A0], xmm1
0x18002b51b  movaps  xmm0, xmmword ptr [rdi+10h]
0x18002b51f  movaps  [rbp+57h+var_90], xmm0
0x18002b523  mov     r9, [rsp+120h+var_D8]
0x18002b528  sub     r9, [rsp+120h+var_E8+8]
0x18002b52d  sar     r9, 4
0x18002b531  lea     rcx, [rbp+57h+var_80]
0x18002b535  call    _anonymous_namespace___IsInvertedColor
0x18002b53a  movzx   r8d, al; int
0x18002b53e  mov     [rsp+120h+ppv], rsi; hFile
0x18002b543  mov     edx, r14d; int
0x18002b546  lea     rcx, [rbp+57h+var_A0]; int
0x18002b54a  call    _anonymous_namespace___WriteCursorHeaderBytes
0x18002b54f  mov     rbx, [rsp+120h+var_E8+8]
0x18002b554  mov     rdi, [rsp+120h+var_D8]
0x18002b559  jmp     short loc_18002B56A
0x18002b55b  mov     rdx, rsi; void *
0x18002b55e  mov     rcx, rbx; this
0x18002b561  call    ?WriteBitmapBytes@SvgToBitmapConverter@@QEAAXPEAX@Z; SvgToBitmapConverter::WriteBitmapBytes(void *)
0x18002b566  add     rbx, 10h
0x18002b56a  cmp     rbx, rdi
0x18002b56d  jnz     short loc_18002B55B
0x18002b56f  lea     rcx, [rbp+57h+hFile]
0x18002b573  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002b578  nop
0x18002b579  mov     rcx, [rsp+120h+var_E8+8]
0x18002b57e  test    rcx, rcx
0x18002b581  jz      short loc_18002B5B3
0x18002b583  mov     rdx, [rsp+120h+var_D8]
0x18002b588  call    ??$_Destroy_range@V?$allocator@VSvgToBitmapConverter@@@std@@@std@@YAXPEAVSvgToBitmapConverter@@QEAV1@AEAV?$allocator@VSvgToBitmapConverter@@@0@@Z; std::_Destroy_range<std::allocator<SvgToBitmapConverter>>(SvgToBitmapConverter *,SvgToBitmapConverter * const,std::allocator<SvgToBitmapConverter> &)
0x18002b58d  mov     rcx, [rsp+120h+var_E8+8]
0x18002b592  mov     rdx, [rbp+57h+var_D0]
0x18002b596  sub     rdx, rcx
0x18002b599  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18002b59d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002b5a2  xorps   xmm0, xmm0
0x18002b5a5  movdqu  xmmword ptr [rsp+120h+var_E8+8], xmm0
0x18002b5ab  mov     [rbp+57h+var_D0], 0
0x18002b5b3  lea     rcx, [rbp+57h+ppIFactory]
0x18002b5b7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b5bc  nop
0x18002b5bd  lea     rcx, [rbp+57h+var_C0]
0x18002b5c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b5c6  mov     rcx, [rbp+57h+var_40]
0x18002b5ca  xor     rcx, rsp; StackCookie
0x18002b5cd  call    __security_check_cookie
0x18002b5d2  lea     r11, [rsp+120h+var_20]
0x18002b5da  mov     rbx, [r11+48h]
0x18002b5de  movaps  xmm6, xmmword ptr [r11-10h]
0x18002b5e3  mov     rsp, r11
0x18002b5e6  pop     r15
0x18002b5e8  pop     r14
0x18002b5ea  pop     rdi
0x18002b5eb  pop     rsi
0x18002b5ec  pop     rbp
0x18002b5ed  retn
```
