# WaasMedic::LoadDataFromFile(ushort const *,ushort * *)

- ea: `0x1800371c8`
- end: `0x18003742e`
- name: `?LoadDataFromFile@WaasMedic@@YAJPEBGPEAPEAG@Z`
- size: `614`
- prototype: `__int64 __fastcall(WaasMedic *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004ef58`
- `0x18004ff6c`

## callees

- `0x180005bbc`
- `0x18000bbb4`
- `0x18000bbd4`
- `0x18000f580`
- `0x180033204`
- `0x180035ba8`
- `0x1800371c8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037276`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800373e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037276`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800373e6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003732b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003737d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003732b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003737d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800372c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800373ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800373d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800372c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800373ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800373d7`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18003724a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18003724a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800372ed`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800372ed`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037217`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037217`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::LoadDataFromFile(const WCHAR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  WCHAR *FileW; // rax
  const char *v5; // r9
  WCHAR *v6; // rbx
  DWORD FileSize; // eax
  const char *v9; // r9
  size_t v10; // rdi
  unsigned int LastError; // edi
  void *v12; // rcx
  const char *v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  __int64 cchWideChar; // rdi
  unsigned int v17; // r8d
  const char *v18; // r9
  const char *v19; // r9
  LPWSTR v20; // rax
  void *v21; // rcx
  int lpOverlapped; // [rsp+20h] [rbp-30h]
  int lpOverlappeda; // [rsp+20h] [rbp-30h]
  LPWSTR lpWideCharStr[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+30h] BYREF
  int v27; // [rsp+90h] [rbp+40h]
  LPVOID pv; // [rsp+98h] [rbp+48h] BYREF

  v27 = 0;
  if ( !this || !*this )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
      (const char *)0x80070057LL,
      lpOverlapped);
    return 2147942487LL;
  }
  FileW = (WCHAR *)CreateFileW(this, 0x80000000, 0, 0, 3u, 0x80u, 0);
  v6 = FileW;
  lpWideCharStr[1] = FileW;
  if ( FileW == (WCHAR *)-1LL )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x19F,
             (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
             v5);
  FileSize = GetFileSize(FileW, 0);
  v10 = FileSize;
  if ( FileSize == -1 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1A2,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
                  v9);
LABEL_7:
    if ( v6 )
      CloseHandle(v6);
    return LastError;
  }
  wil::make_unique_cotaskmem<unsigned char [0]>(&pv, FileSize);
  if ( !pv )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A5,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
      (const char *)0x8007000ELL,
      lpOverlappeda);
    goto LABEL_12;
  }
  memset_0(pv, 0, v10);
  NumberOfBytesRead = 0;
  if ( !ReadFile(v6, pv, v10, &NumberOfBytesRead, 0) )
  {
    v14 = 424;
LABEL_16:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v14,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
                  v13);
LABEL_12:
    v12 = pv;
    pv = 0;
    if ( v12 )
      CoTaskMemFree(v12);
    goto LABEL_7;
  }
  v15 = MultiByteToWideChar(0xFDE9u, 0, (LPCCH)pv, NumberOfBytesRead, 0, 0);
  cchWideChar = v15;
  if ( !v15 )
  {
    v14 = 427;
    goto LABEL_16;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    lpWideCharStr,
    0,
    v15 + 1);
  v27 = 4;
  if ( !lpWideCharStr[0] )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0xFF8, v17, v18);
  if ( !MultiByteToWideChar(0xFDE9u, 0, (LPCCH)pv, NumberOfBytesRead, lpWideCharStr[0], cchWideChar) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1AF,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
                  v19);
    if ( lpWideCharStr[0] )
      CoTaskMemFree(lpWideCharStr[0]);
    goto LABEL_12;
  }
  lpWideCharStr[0][cchWideChar] = 0;
  v20 = lpWideCharStr[0];
  lpWideCharStr[0] = 0;
  *(_QWORD *)a2 = v20;
  v21 = pv;
  pv = 0;
  if ( v21 )
    CoTaskMemFree(v21);
  if ( v6 )
    CloseHandle(v6);
  return 0;
}

```

## disassembly

```asm
0x1800371c8  mov     rax, rsp
0x1800371cb  mov     [rax+10h], rbx
0x1800371cf  push    rbp
0x1800371d0  push    rsi
0x1800371d1  push    rdi
0x1800371d2  push    r14
0x1800371d4  push    r15
0x1800371d6  mov     rbp, rsp
0x1800371d9  sub     rsp, 50h
0x1800371dd  mov     r14, rdx
0x1800371e0  xor     r15d, r15d
0x1800371e3  mov     [rbp+arg_10], r15d
0x1800371e7  test    rcx, rcx
0x1800371ea  jz      loc_1800373F0
0x1800371f0  cmp     [rcx], r15w
0x1800371f4  jz      loc_1800373F0
0x1800371fa  mov     [rax-48h], r15
0x1800371fe  mov     dword ptr [rax-50h], 80h
0x180037205  mov     dword ptr [rax-58h], 3
0x18003720c  xor     r9d, r9d; lpSecurityAttributes
0x18003720f  xor     r8d, r8d; dwShareMode
0x180037212  mov     edx, 80000000h; dwDesiredAccess
0x180037217  call    cs:__imp_CreateFileW
0x18003721d  mov     rbx, rax
0x180037220  mov     [rbp+var_8], rax
0x180037224  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180037228  jnz     short loc_180037245
0x18003722a  mov     rcx, [rbp+28h]; this
0x18003722e  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180037235  mov     edx, 19Fh; void *
0x18003723a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003723f  nop
0x180037240  jmp     loc_18003740F
0x180037245  xor     edx, edx; lpFileSizeHigh
0x180037247  mov     rcx, rbx; hFile
0x18003724a  call    cs:__imp_GetFileSize
0x180037250  mov     edi, eax
0x180037252  cmp     eax, 0FFFFFFFFh
0x180037255  jnz     short loc_180037283
0x180037257  mov     rcx, [rbp+28h]; this
0x18003725b  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180037262  mov     edx, 1A2h; void *
0x180037267  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003726c  mov     edi, eax
0x18003726e  test    rbx, rbx
0x180037271  jz      short loc_18003727C
0x180037273  mov     rcx, rbx; hObject
0x180037276  call    cs:__imp_CloseHandle
0x18003727c  mov     eax, edi
0x18003727e  jmp     loc_18003740F
0x180037283  mov     rdx, rdi
0x180037286  lea     rcx, [rbp+pv]
0x18003728a  call    ??$make_unique_cotaskmem@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<uchar [0]>(unsigned __int64)
0x18003728f  nop
0x180037290  mov     rcx, [rbp+pv]; void *
0x180037294  test    rcx, rcx
0x180037297  jnz     short loc_1800372CC
0x180037299  mov     rcx, [rbp+28h]; this
0x18003729d  mov     edi, 8007000Eh
0x1800372a2  mov     r9d, edi; char *
0x1800372a5  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800372ac  mov     edx, 1A5h; void *
0x1800372b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800372b6  nop
0x1800372b7  mov     rcx, [rbp+pv]; pv
0x1800372bb  mov     [rbp+pv], r15
0x1800372bf  test    rcx, rcx
0x1800372c2  jz      short loc_18003726E
0x1800372c4  call    cs:__imp_CoTaskMemFree
0x1800372ca  jmp     short loc_18003726E
0x1800372cc  mov     r8, rdi; Size
0x1800372cf  xor     edx, edx; Val
0x1800372d1  call    memset_0
0x1800372d6  mov     [rbp+NumberOfBytesRead], r15d
0x1800372da  mov     [rsp+50h+lpOverlapped], r15; lpOverlapped
0x1800372df  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800372e3  mov     r8d, edi; nNumberOfBytesToRead
0x1800372e6  mov     rdx, [rbp+pv]; lpBuffer
0x1800372ea  mov     rcx, rbx; hFile
0x1800372ed  call    cs:__imp_ReadFile
0x1800372f3  test    eax, eax
0x1800372f5  jnz     short loc_180037310
0x1800372f7  mov     edx, 1A8h; void *
0x1800372fc  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180037303  mov     rcx, [rbp+28h]; this
0x180037307  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003730c  mov     edi, eax
0x18003730e  jmp     short loc_1800372B7
0x180037310  mov     [rsp+50h+cchWideChar], r15d; cchWideChar
0x180037315  mov     [rsp+50h+lpOverlapped], r15; lpWideCharStr
0x18003731a  mov     r9d, [rbp+NumberOfBytesRead]; cbMultiByte
0x18003731e  mov     r8, [rbp+pv]; lpMultiByteStr
0x180037322  xor     edx, edx; dwFlags
0x180037324  mov     esi, 0FDE9h
0x180037329  mov     ecx, esi; CodePage
0x18003732b  call    cs:__imp_MultiByteToWideChar
0x180037331  movsxd  rdi, eax
0x180037334  test    eax, eax
0x180037336  jnz     short loc_18003733F
0x180037338  mov     edx, 1ABh
0x18003733d  jmp     short loc_1800372FC
0x18003733f  lea     eax, [rdi+1]
0x180037342  movsxd  r8, eax
0x180037345  xor     edx, edx
0x180037347  lea     rcx, [rbp+lpWideCharStr]
0x18003734b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180037350  mov     [rbp+arg_10], 4
0x180037357  mov     rcx, [rbp+28h]; this
0x18003735b  mov     rax, [rbp+lpWideCharStr]
0x18003735f  test    rax, rax
0x180037362  jz      loc_180037423
0x180037368  mov     [rsp+50h+cchWideChar], edi; cchWideChar
0x18003736c  mov     [rsp+50h+lpOverlapped], rax; lpWideCharStr
0x180037371  mov     r9d, [rbp+NumberOfBytesRead]; cbMultiByte
0x180037375  mov     r8, [rbp+pv]; lpMultiByteStr
0x180037379  xor     edx, edx; dwFlags
0x18003737b  mov     ecx, esi; CodePage
0x18003737d  call    cs:__imp_MultiByteToWideChar
0x180037383  test    eax, eax
0x180037385  jnz     short loc_1800373B6
0x180037387  mov     rcx, [rbp+28h]; this
0x18003738b  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180037392  mov     edx, 1AFh; void *
0x180037397  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003739c  mov     edi, eax
0x18003739e  mov     rcx, [rbp+lpWideCharStr]; pv
0x1800373a2  test    rcx, rcx
0x1800373a5  jz      loc_1800372B7
0x1800373ab  call    cs:__imp_CoTaskMemFree
0x1800373b1  jmp     loc_1800372B7
0x1800373b6  mov     rax, [rbp+lpWideCharStr]
0x1800373ba  mov     [rax+rdi*2], r15w
0x1800373bf  mov     rax, [rbp+lpWideCharStr]
0x1800373c3  mov     [rbp+lpWideCharStr], r15
0x1800373c7  mov     [r14], rax
0x1800373ca  mov     rcx, [rbp+pv]; pv
0x1800373ce  mov     [rbp+pv], r15
0x1800373d2  test    rcx, rcx
0x1800373d5  jz      short loc_1800373DE
0x1800373d7  call    cs:__imp_CoTaskMemFree
0x1800373dd  nop
0x1800373de  test    rbx, rbx
0x1800373e1  jz      short loc_1800373EC
0x1800373e3  mov     rcx, rbx; hObject
0x1800373e6  call    cs:__imp_CloseHandle
0x1800373ec  xor     eax, eax
0x1800373ee  jmp     short loc_18003740F
0x1800373f0  mov     rcx, [rbp+28h]; this
0x1800373f4  mov     ebx, 80070057h
0x1800373f9  mov     r9d, ebx; char *
0x1800373fc  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180037403  mov     edx, 19Bh; void *
0x180037408  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003740d  mov     eax, ebx
0x18003740f  mov     rbx, [rsp+50h+arg_8]
0x180037417  add     rsp, 50h
0x18003741b  pop     r15
0x18003741d  pop     r14
0x18003741f  pop     rdi
0x180037420  pop     rsi
0x180037421  pop     rbp
0x180037422  retn
0x180037423  mov     edx, 0FF8h; void *
0x180037428  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
