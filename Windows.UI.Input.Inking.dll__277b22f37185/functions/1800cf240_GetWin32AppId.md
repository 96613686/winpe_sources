# GetWin32AppId

- ea: `0x1800cf240`
- end: `0x1800cf56a`
- name: `GetWin32AppId`
- size: `810`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800cee68`

## callees

- `0x1800062a0`
- `0x180006ec4`
- `0x18001330c`
- `0x18001332c`
- `0x180013ac8`
- `0x180014a5c`
- `0x1800cee48`
- `0x1800cf004`
- `0x1800cf240`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800cf338`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800cf369`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800cf4db`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800cf4fc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800cf506`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800cf537`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800cf546`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800cf338`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800cf369`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800cf4db`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800cf4fc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800cf506`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800cf537`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800cf546`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800cf281`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800cf2f3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800cf281`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800cf2f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cf29d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cf29d`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x1800cf314`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x1800cf314`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x1800cf2e1`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x1800cf2e1`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800cf35c`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800cf35c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800cf2af`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800cf2af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cf472`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cf472`

## string_xrefs

- `0x1800cf458`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800cf2bd`: `onecoreuap\windows\dwm\common\telemetryhelper\processinformation\processinformation.cpp`
- `0x1800cf322`: `onecoreuap\windows\dwm\common\telemetryhelper\processinformation\processinformation.cpp`
- `0x1800cf3d6`: `onecoreuap\windows\dwm\common\telemetryhelper\processinformation\processinformation.cpp`
- `0x1800cf4bb`: `onecoreuap\windows\dwm\common\telemetryhelper\processinformation\processinformation.cpp`
- `0x1800cf514`: `onecoreuap\windows\dwm\common\telemetryhelper\processinformation\processinformation.cpp`

## pseudocode

```c
__int64 __fastcall GetWin32AppId(unsigned __int16 **a1)
{
  HANDLE CurrentProcess; // rax
  const char *v4; // r9
  unsigned int LastError; // ebx
  void *v6; // rdi
  DWORD FileVersionInfoSizeW; // eax
  DWORD v8; // ebx
  void *v9; // rax
  void *v10; // rcx
  const char *v11; // r9
  int v12; // eax
  const char *v13; // r9
  unsigned __int16 *v14; // r15
  unsigned __int16 *v15; // rsi
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rbx
  __int64 v18; // r9
  int v19; // eax
  unsigned int v20; // esi
  int v21; // [rsp+20h] [rbp-79h]
  unsigned __int16 *v22; // [rsp+40h] [rbp-59h] BYREF
  LPCWSTR lptstrFilename; // [rsp+48h] [rbp-51h] BYREF
  DWORD dwSize; // [rsp+50h] [rbp-49h] BYREF
  unsigned int puLen; // [rsp+54h] [rbp-45h] BYREF
  LPVOID lpBuffer; // [rsp+58h] [rbp-41h] BYREF
  __int64 v27; // [rsp+68h] [rbp-31h] BYREF
  int v28; // [rsp+70h] [rbp-29h]
  int v29; // [rsp+74h] [rbp-25h]
  unsigned __int16 v30[8]; // [rsp+78h] [rbp-21h] BYREF
  __int128 v31; // [rsp+88h] [rbp-11h]
  __int128 v32; // [rsp+98h] [rbp-1h]
  __int16 v33; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  *a1 = 0;
  dwSize = 0x7FFF;
  lptstrFilename = (LPCWSTR)malloc(0xFFFEu);
  if ( !lptstrFilename )
    return 2147942414LL;
  CurrentProcess = GetCurrentProcess();
  if ( !QueryFullProcessImageNameW(CurrentProcess, 0, (LPWSTR)lptstrFilename, &dwSize) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA7,
                  (unsigned int)"onecoreuap\\windows\\dwm\\common\\telemetryhelper\\processinformation\\processinformation.cpp",
                  v4);
    goto LABEL_25;
  }
  v6 = 0;
  lpBuffer = 0;
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(lptstrFilename, 0);
  v8 = FileVersionInfoSizeW;
  if ( FileVersionInfoSizeW )
  {
    v9 = malloc(FileVersionInfoSizeW);
    v6 = v9;
    if ( !v9 )
    {
      v10 = 0;
LABEL_24:
      free(v10);
      LastError = -2147024882;
      goto LABEL_25;
    }
    if ( !GetFileVersionInfoW(lptstrFilename, 0, v8, v9) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xC0,
                    (unsigned int)"onecoreuap\\windows\\dwm\\common\\telemetryhelper\\processinformation\\processinformation.cpp",
                    v11);
LABEL_10:
      free(v6);
      goto LABEL_25;
    }
    puLen = 0;
    if ( !VerQueryValueW(v6, L"\\", &lpBuffer, &puLen) )
    {
      free(v6);
      LastError = -2147467259;
      goto LABEL_25;
    }
  }
  v33 = 0;
  *(_OWORD *)v30 = 0;
  v31 = 0;
  v32 = 0;
  if ( lpBuffer )
  {
    v21 = *((unsigned __int16 *)lpBuffer + 4);
    v12 = StringCchPrintfW(v30, 0x19u, L"%hu.%hu.%hu.%hu", *((unsigned __int16 *)lpBuffer + 5));
    LastError = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE0,
        (unsigned int)"onecoreuap\\windows\\dwm\\common\\telemetryhelper\\processinformation\\processinformation.cpp",
        (const char *)(unsigned int)v12,
        v21);
      goto LABEL_10;
    }
  }
  else
  {
    v27 = 0x2E0030002E0030LL;
    v28 = 3014704;
    v29 = 48;
    o_wcsncpy_s_0(v30, 25, &v27);
  }
  v22 = 0;
  v27 = (__int64)&dword_180112D8C;
  GetFileName(&lptstrFilename, &v27, &v22);
  v14 = v22;
  v15 = v22 + 13;
  if ( v22 == (unsigned __int16 *)-27LL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v13);
  v16 = (unsigned __int16 *)CoTaskMemAlloc(2LL * (_QWORD)v15 + 2);
  v22 = v16;
  v17 = v16;
  if ( !v16 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\telemetryhelper\\processinformation\\processinformation.cpp",
      (const char *)0x8007000ELL,
      v21);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
    v10 = v6;
    goto LABEL_24;
  }
  v18 = v27;
  *v16 = 0;
  v16[(_QWORD)v15] = 0;
  v19 = StringCchPrintfW(v16, (unsigned __int64)v14 + 27, aS, v18);
  v20 = v19;
  if ( v19 >= 0 )
  {
    v22 = 0;
    *a1 = v17;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
    free(v6);
    free((void *)lptstrFilename);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x106,
    (unsigned int)"onecoreuap\\windows\\dwm\\common\\telemetryhelper\\processinformation\\processinformation.cpp",
    (const char *)(unsigned int)v19,
    (int)v30);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
  free(v6);
  LastError = v20;
LABEL_25:
  free((void *)lptstrFilename);
  return LastError;
}

```

## disassembly

```asm
0x1800cf240  push    rbp
0x1800cf242  push    rbx
0x1800cf243  push    rsi
0x1800cf244  push    rdi
0x1800cf245  push    r14
0x1800cf247  push    r15
0x1800cf249  lea     rbp, [rsp-2Fh]
0x1800cf24e  sub     rsp, 0C8h
0x1800cf255  mov     rax, cs:__security_cookie
0x1800cf25c  xor     rax, rsp
0x1800cf25f  mov     [rbp+57h+var_40], rax
0x1800cf263  mov     r14, rcx
0x1800cf266  mov     qword ptr [rcx], 0
0x1800cf26d  mov     ecx, 0FFFEh; Size
0x1800cf272  mov     [rbp+57h+lptstrFilename], 0
0x1800cf27a  mov     [rbp+57h+dwSize], 7FFFh
0x1800cf281  call    cs:__imp_malloc
0x1800cf287  mov     [rbp+57h+lptstrFilename], rax
0x1800cf28b  mov     rbx, rax
0x1800cf28e  test    rax, rax
0x1800cf291  jnz     short loc_1800CF29D
0x1800cf293  mov     eax, 8007000Eh
0x1800cf298  jmp     loc_1800CF54E
0x1800cf29d  call    cs:__imp_GetCurrentProcess
0x1800cf2a3  lea     r9, [rbp+57h+dwSize]; lpdwSize
0x1800cf2a7  mov     r8, rbx; lpExeName
0x1800cf2aa  mov     rcx, rax; hProcess
0x1800cf2ad  xor     edx, edx; dwFlags
0x1800cf2af  call    cs:__imp_QueryFullProcessImageNameW
0x1800cf2b5  test    eax, eax
0x1800cf2b7  jnz     short loc_1800CF2D5
0x1800cf2b9  mov     rcx, [rbp+5Fh]; this
0x1800cf2bd  lea     r8, aOnecoreuapWind_8; "onecoreuap\\windows\\dwm\\common\\telem"...
0x1800cf2c4  mov     edx, 0A7h; void *
0x1800cf2c9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cf2ce  mov     ebx, eax
0x1800cf2d0  jmp     loc_1800CF542
0x1800cf2d5  mov     rcx, [rbp+57h+lptstrFilename]; lptstrFilename
0x1800cf2d9  xor     edi, edi
0x1800cf2db  xor     edx, edx; lpdwHandle
0x1800cf2dd  mov     [rbp+57h+lpBuffer], rdi
0x1800cf2e1  call    cs:__imp_GetFileVersionInfoSizeW
0x1800cf2e7  mov     ebx, eax
0x1800cf2e9  test    eax, eax
0x1800cf2eb  jz      loc_1800CF379
0x1800cf2f1  mov     ecx, ebx; Size
0x1800cf2f3  call    cs:__imp_malloc
0x1800cf2f9  mov     rdi, rax
0x1800cf2fc  test    rax, rax
0x1800cf2ff  jnz     short loc_1800CF308
0x1800cf301  xor     ecx, ecx
0x1800cf303  jmp     loc_1800CF537
0x1800cf308  mov     rcx, [rbp+57h+lptstrFilename]; lptstrFilename
0x1800cf30c  mov     r9, rdi; lpData
0x1800cf30f  mov     r8d, ebx; dwLen
0x1800cf312  xor     edx, edx; dwHandle
0x1800cf314  call    cs:__imp_GetFileVersionInfoW
0x1800cf31a  test    eax, eax
0x1800cf31c  jnz     short loc_1800CF343
0x1800cf31e  mov     rcx, [rbp+5Fh]; this
0x1800cf322  lea     r8, aOnecoreuapWind_8; "onecoreuap\\windows\\dwm\\common\\telem"...
0x1800cf329  mov     edx, 0C0h; void *
0x1800cf32e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cf333  mov     ebx, eax
0x1800cf335  mov     rcx, rdi; Block
0x1800cf338  call    cs:__imp_free
0x1800cf33e  jmp     loc_1800CF542
0x1800cf343  lea     r9, [rbp+57h+puLen]; puLen
0x1800cf347  mov     [rbp+57h+puLen], 0
0x1800cf34e  lea     r8, [rbp+57h+lpBuffer]; lplpBuffer
0x1800cf352  mov     rcx, rdi; pBlock
0x1800cf355  lea     rdx, SubBlock; "\\"
0x1800cf35c  call    cs:__imp_VerQueryValueW
0x1800cf362  test    eax, eax
0x1800cf364  jnz     short loc_1800CF379
0x1800cf366  mov     rcx, rdi; Block
0x1800cf369  call    cs:__imp_free
0x1800cf36f  mov     ebx, 80004005h
0x1800cf374  jmp     loc_1800CF542
0x1800cf379  mov     r8, [rbp+57h+lpBuffer]
0x1800cf37d  xorps   xmm0, xmm0
0x1800cf380  xor     eax, eax
0x1800cf382  mov     [rbp+57h+var_48], ax
0x1800cf386  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x1800cf38a  movups  [rbp+57h+var_68], xmm0
0x1800cf38e  movups  [rbp+57h+var_58], xmm0
0x1800cf392  test    r8, r8
0x1800cf395  jz      short loc_1800CF3EF
0x1800cf397  movzx   ecx, word ptr [r8+0Eh]
0x1800cf39c  movzx   edx, word ptr [r8+8]
0x1800cf3a1  movzx   eax, word ptr [r8+0Ch]
0x1800cf3a6  movzx   r9d, word ptr [r8+0Ah]
0x1800cf3ab  lea     r8, aHuHuHuHu; "%hu.%hu.%hu.%hu"
0x1800cf3b2  mov     [rsp+0F0h+var_C0], eax
0x1800cf3b6  mov     [rsp+0F0h+var_C8], ecx
0x1800cf3ba  lea     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x1800cf3be  mov     [rsp+0F0h+var_D0], edx; int
0x1800cf3c2  mov     edx, 19h; unsigned __int64
0x1800cf3c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800cf3cc  mov     ebx, eax
0x1800cf3ce  test    eax, eax
0x1800cf3d0  jns     short loc_1800CF422
0x1800cf3d2  mov     rcx, [rbp+5Fh]; this
0x1800cf3d6  lea     r8, aOnecoreuapWind_8; "onecoreuap\\windows\\dwm\\common\\telem"...
0x1800cf3dd  mov     r9d, eax; char *
0x1800cf3e0  mov     edx, 0E0h; void *
0x1800cf3e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cf3ea  jmp     loc_1800CF335
0x1800cf3ef  mov     r9d, 7
0x1800cf3f5  mov     dword ptr [rbp+57h+var_88], 2E0030h
0x1800cf3fc  lea     r8, [rbp+57h+var_88]
0x1800cf400  mov     dword ptr [rbp+57h+var_88+4], 2E0030h
0x1800cf407  lea     rcx, [rbp+57h+var_78]
0x1800cf40b  mov     [rbp+57h+var_80], 2E0030h
0x1800cf412  mov     [rbp+57h+var_7C], 30h ; '0'
0x1800cf419  lea     edx, [r9+12h]
0x1800cf41d  call    _o_wcsncpy_s_0
0x1800cf422  lea     rax, dword_180112D8C
0x1800cf429  mov     [rbp+57h+var_B0], 0
0x1800cf431  lea     r8, [rbp+57h+var_B0]
0x1800cf435  mov     [rbp+57h+var_88], rax
0x1800cf439  lea     rdx, [rbp+57h+var_88]
0x1800cf43d  lea     rcx, [rbp+57h+lptstrFilename]
0x1800cf441  call    GetFileName
0x1800cf446  mov     r15, [rbp+57h+var_B0]
0x1800cf44a  lea     rsi, [r15+1Ah]
0x1800cf44e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800cf452  jnz     short loc_1800CF46A
0x1800cf454  mov     rcx, [rbp+5Fh]; this
0x1800cf458  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800cf45f  mov     edx, 0F89h; void *
0x1800cf464  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800cf46a  lea     rcx, ds:2[rsi*2]; cb
0x1800cf472  call    cs:__imp_CoTaskMemAlloc
0x1800cf478  mov     [rbp+57h+var_B0], rax
0x1800cf47c  mov     rbx, rax
0x1800cf47f  test    rax, rax
0x1800cf482  jz      loc_1800CF510
0x1800cf488  mov     r9, [rbp+57h+var_88]
0x1800cf48c  lea     r8, aS; "%s"
0x1800cf493  xor     ecx, ecx
0x1800cf495  lea     rdx, [r15+1Bh]; unsigned __int64
0x1800cf499  mov     [rax], cx
0x1800cf49c  mov     [rax+rsi*2], cx
0x1800cf4a0  lea     rax, [rbp+57h+var_78]
0x1800cf4a4  mov     rcx, rbx; unsigned __int16 *
0x1800cf4a7  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x1800cf4ac  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800cf4b1  mov     esi, eax
0x1800cf4b3  test    eax, eax
0x1800cf4b5  jns     short loc_1800CF4E5
0x1800cf4b7  mov     rcx, [rbp+5Fh]; this
0x1800cf4bb  lea     r8, aOnecoreuapWind_8; "onecoreuap\\windows\\dwm\\common\\telem"...
0x1800cf4c2  mov     r9d, eax; char *
0x1800cf4c5  mov     edx, 106h; void *
0x1800cf4ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cf4cf  lea     rcx, [rbp+57h+var_B0]
0x1800cf4d3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800cf4d8  mov     rcx, rdi; Block
0x1800cf4db  call    cs:__imp_free
0x1800cf4e1  mov     ebx, esi
0x1800cf4e3  jmp     short loc_1800CF542
0x1800cf4e5  lea     rcx, [rbp+57h+var_B0]
0x1800cf4e9  mov     [rbp+57h+var_B0], 0
0x1800cf4f1  mov     [r14], rbx
0x1800cf4f4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800cf4f9  mov     rcx, rdi; Block
0x1800cf4fc  call    cs:__imp_free
0x1800cf502  mov     rcx, [rbp+57h+lptstrFilename]; Block
0x1800cf506  call    cs:__imp_free
0x1800cf50c  xor     eax, eax
0x1800cf50e  jmp     short loc_1800CF54E
0x1800cf510  mov     rcx, [rbp+5Fh]; this
0x1800cf514  lea     r8, aOnecoreuapWind_8; "onecoreuap\\windows\\dwm\\common\\telem"...
0x1800cf51b  mov     r9d, 8007000Eh; char *
0x1800cf521  mov     edx, 0FBh; void *
0x1800cf526  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cf52b  lea     rcx, [rbp+57h+var_B0]
0x1800cf52f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800cf534  mov     rcx, rdi; Block
0x1800cf537  call    cs:__imp_free
0x1800cf53d  mov     ebx, 8007000Eh
0x1800cf542  mov     rcx, [rbp+57h+lptstrFilename]; Block
0x1800cf546  call    cs:__imp_free
0x1800cf54c  mov     eax, ebx
0x1800cf54e  mov     rcx, [rbp+57h+var_40]
0x1800cf552  xor     rcx, rsp; StackCookie
0x1800cf555  call    __security_check_cookie
0x1800cf55a  add     rsp, 0C8h
0x1800cf561  pop     r15
0x1800cf563  pop     r14
0x1800cf565  pop     rdi
0x1800cf566  pop     rsi
0x1800cf567  pop     rbx
0x1800cf568  pop     rbp
0x1800cf569  retn
```
