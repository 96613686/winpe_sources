# DCFileUtils::ReadFromFile(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x1800a98cc`
- end: `0x1800a9c0b`
- name: `?ReadFromFile@DCFileUtils@@SAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `831`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800e0ef0`

## callees

- `0x18000df6c`
- `0x18000e5d0`
- `0x18000f598`
- `0x1800117bc`
- `0x1800117dc`
- `0x18001d070`
- `0x18004d200`
- `0x180058630`
- `0x1800a973c`
- `0x1800a975c`
- `0x1800a98cc`
- `0x1800a9c14`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a9a31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a9a31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800a9aa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800a9aa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9a18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9ba6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9a18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9ba6`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800a99c1`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800a99c1`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800a99a7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800a99a7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a994a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a9b53`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a994a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a9b53`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a990d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a990d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a9b10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a9b10`

## string_xrefs

- `0x1800a995b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcfileutils.cpp`
- `0x1800a99ef`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcfileutils.cpp`
- `0x1800a9a75`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcfileutils.cpp`
- `0x1800a9ab6`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcfileutils.cpp`
- `0x1800a9b61`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcfileutils.cpp`

## pseudocode

```c
__int64 __fastcall DCFileUtils::ReadFromFile(const WCHAR *a1, HSTRING *a2)
{
  HRESULT v2; // r13d
  char v4; // r12
  unsigned int v5; // edi
  wil::details *v6; // rcx
  HANDLE FileW; // rsi
  unsigned int LastError; // eax
  const char *v9; // r9
  __int64 v10; // rdx
  unsigned int v11; // ebx
  int v12; // r15d
  __int64 v13; // rdx
  __int64 v14; // r9
  DWORD v15; // ebx
  HSTRING v16; // rbx
  HRESULT String; // eax
  const CHAR *v18; // rdi
  __int64 v19; // rdx
  unsigned __int64 v20; // r9
  HRESULT v21; // eax
  void *v23; // rdx
  LPVOID v24; // rax
  const char *v25; // r9
  HSTRING v26; // rbx
  int hstring_from_buffer_nothrow; // eax
  int v28; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-60h]
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-40h] BYREF
  HSTRING_BUFFER bufferHandle; // [rsp+48h] [rbp-38h] BYREF
  LPVOID lpBuffer; // [rsp+50h] [rbp-30h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+58h] [rbp-28h] BYREF
  WCHAR *charBuffer; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v35[8]; // [rsp+68h] [rbp-18h] BYREF
  HANDLE v36[2]; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  int Buffer; // [rsp+D0h] [rbp+50h] BYREF
  DWORD v39; // [rsp+D8h] [rbp+58h] BYREF

  v2 = 0;
  v4 = 1;
  v5 = 3;
  FileW = CreateFileW(a1, 0x120089u, 1u, 0, 3u, 0, 0);
  v36[0] = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    Buffer = 0;
    NumberOfBytesRead = 0;
    if ( !ReadFile(FileW, &Buffer, 4u, &NumberOfBytesRead, 0) )
    {
      v10 = 87;
LABEL_5:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v10,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcfileutils.cpp",
                    v9);
      goto LABEL_6;
    }
    if ( (Buffer & 0xFFFFFF) == 0xBFBBEF )
    {
      v12 = 1;
    }
    else if ( (_WORD)Buffer == 0xFEFF )
    {
      v5 = 2;
      v12 = 2;
    }
    else
    {
      v5 = 0;
      v12 = 0;
    }
    if ( !SetFilePointerEx(FileW, (LARGE_INTEGER)v5, 0, 0) )
    {
      v10 = 98;
      goto LABEL_5;
    }
    FileSize.QuadPart = 0;
    if ( !GetFileSizeEx(FileW, &FileSize) )
    {
      v10 = 101;
      goto LABEL_5;
    }
    if ( FileSize.QuadPart >= 0xFFFFFFFFLL )
    {
      v11 = -2147024362;
      v13 = 102;
      v14 = 2147942934LL;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcfileutils.cpp",
        (const char *)v14,
        dwCreationDisposition);
      goto LABEL_34;
    }
    v15 = FileSize.LowPart - v5;
    if ( FileSize.LowPart == v5 )
    {
      v16 = *a2;
      if ( *a2 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&charBuffer);
        WindowsDeleteString(v16);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&charBuffer);
      }
      *a2 = 0;
      String = WindowsCreateString(0, 0, a2);
      v11 = String;
      if ( String < 0 )
      {
        v14 = (unsigned int)String;
        v13 = 107;
        goto LABEL_18;
      }
LABEL_33:
      v11 = v2;
      goto LABEL_34;
    }
    lpBuffer = 0;
    v18 = 0;
    bufferHandle = 0;
    if ( v12 == 2 )
    {
      if ( (v15 & 1) != 0 )
      {
        v11 = -2147024883;
        v19 = 124;
LABEL_27:
        v20 = v11;
LABEL_28:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcfileutils.cpp",
          (const char *)v20,
          dwCreationDisposition);
LABEL_29:
        wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&bufferHandle);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpBuffer);
        goto LABEL_34;
      }
      charBuffer = 0;
      v21 = WindowsPreallocateStringBuffer(v15 >> 1, &charBuffer, &bufferHandle);
      v2 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x81,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcfileutils.cpp",
          (const char *)(unsigned int)v21,
          dwCreationDisposition);
        goto LABEL_32;
      }
      v23 = charBuffer;
      v2 = 0;
    }
    else
    {
      v24 = CoTaskMemAlloc(v15);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &lpBuffer,
        v24);
      v18 = (const CHAR *)lpBuffer;
      if ( !lpBuffer )
      {
        v11 = -2147024882;
        v19 = 137;
        goto LABEL_27;
      }
      v4 = 0;
      v23 = lpBuffer;
    }
    v39 = 0;
    if ( !ReadFile(FileW, v23, v15, &v39, 0) )
    {
      v11 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x94,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcfileutils.cpp",
              v25);
      goto LABEL_29;
    }
    if ( v15 != v39 )
    {
      v11 = -2147418113;
      v19 = 152;
      goto LABEL_27;
    }
    if ( v4 )
    {
      v26 = *a2;
      if ( *a2 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v35);
        WindowsDeleteString(v26);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v35);
      }
      *a2 = 0;
      hstring_from_buffer_nothrow = wil::make_hstring_from_buffer_nothrow(&bufferHandle, a2);
      v11 = hstring_from_buffer_nothrow;
      if ( hstring_from_buffer_nothrow < 0 )
      {
        v20 = (unsigned int)hstring_from_buffer_nothrow;
        v19 = 156;
        goto LABEL_28;
      }
    }
    else
    {
      v28 = DCFileUtils::ConvertRawBytesToString(v12 != 0 ? 0xFDE9 : 0, v18, v15);
      v11 = v28;
      if ( v28 < 0 )
      {
        v20 = (unsigned int)v28;
        v19 = 161;
        goto LABEL_28;
      }
    }
LABEL_32:
    wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&bufferHandle);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpBuffer);
    goto LABEL_33;
  }
  LastError = wil::details::GetLastErrorFailHr(v6);
LABEL_6:
  v11 = LastError;
LABEL_34:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v36);
  return v11;
}

```

## disassembly

```asm
0x1800a98cc  mov     [rsp-38h+arg_0], rbx
0x1800a98d1  push    rbp
0x1800a98d2  push    rsi
0x1800a98d3  push    rdi
0x1800a98d4  push    r12
0x1800a98d6  push    r13
0x1800a98d8  push    r14
0x1800a98da  push    r15
0x1800a98dc  mov     rbp, rsp
0x1800a98df  sub     rsp, 80h
0x1800a98e6  xor     r13d, r13d
0x1800a98e9  mov     r14, rdx
0x1800a98ec  mov     [rsp+80h+hTemplateFile], r13; hTemplateFile
0x1800a98f1  xor     r9d, r9d; lpSecurityAttributes
0x1800a98f4  mov     [rsp+80h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x1800a98f9  mov     edx, 120089h; dwDesiredAccess
0x1800a98fe  lea     r12d, [r13+1]
0x1800a9902  lea     edi, [r13+3]
0x1800a9906  mov     r8d, r12d; dwShareMode
0x1800a9909  mov     [rsp+80h+dwCreationDisposition], edi; dwCreationDisposition
0x1800a990d  call    cs:__imp_CreateFileW
0x1800a9913  mov     rsi, rax
0x1800a9916  mov     [rbp+var_10], rax
0x1800a991a  inc     rax
0x1800a991d  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800a9923  jnz     short loc_1800A992C
0x1800a9925  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800a992a  jmp     short loc_1800A9967
0x1800a992c  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800a9930  mov     [rbp+Buffer], r13d
0x1800a9934  mov     r8d, 4; nNumberOfBytesToRead
0x1800a993a  mov     [rbp+NumberOfBytesRead], r13d
0x1800a993e  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800a9942  mov     qword ptr [rsp+80h+dwCreationDisposition], r13; int
0x1800a9947  mov     rcx, rsi; hFile
0x1800a994a  call    cs:__imp_ReadFile
0x1800a9950  test    eax, eax
0x1800a9952  jnz     short loc_1800A996E
0x1800a9954  lea     edx, [rax+57h]; void *
0x1800a9957  mov     rcx, [rbp+38h]; this
0x1800a995b  lea     r8, aOnecoreuapAdmi_44; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a9962  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a9967  mov     ebx, eax
0x1800a9969  jmp     loc_1800A9ADF
0x1800a996e  mov     eax, [rbp+Buffer]
0x1800a9971  mov     ecx, 2
0x1800a9976  and     eax, 0FFFFFFh
0x1800a997b  cmp     eax, 0BFBBEFh
0x1800a9980  jnz     short loc_1800A9987
0x1800a9982  mov     r15d, r12d
0x1800a9985  jmp     short loc_1800A999C
0x1800a9987  cmp     word ptr [rbp+Buffer], 0FEFFh
0x1800a998d  jnz     short loc_1800A9996
0x1800a998f  mov     edi, ecx
0x1800a9991  mov     r15d, ecx
0x1800a9994  jmp     short loc_1800A999C
0x1800a9996  mov     edi, r13d
0x1800a9999  mov     r15d, r13d
0x1800a999c  mov     edx, edi; liDistanceToMove
0x1800a999e  xor     r9d, r9d; dwMoveMethod
0x1800a99a1  xor     r8d, r8d; lpNewFilePointer
0x1800a99a4  mov     rcx, rsi; hFile
0x1800a99a7  call    cs:__imp_SetFilePointerEx
0x1800a99ad  test    eax, eax
0x1800a99af  jnz     short loc_1800A99B6
0x1800a99b1  lea     edx, [rax+62h]
0x1800a99b4  jmp     short loc_1800A9957
0x1800a99b6  lea     rdx, [rbp+FileSize]; lpFileSize
0x1800a99ba  mov     qword ptr [rbp+FileSize], r13
0x1800a99be  mov     rcx, rsi; hFile
0x1800a99c1  call    cs:__imp_GetFileSizeEx
0x1800a99c7  test    eax, eax
0x1800a99c9  jnz     short loc_1800A99D0
0x1800a99cb  lea     edx, [rax+65h]
0x1800a99ce  jmp     short loc_1800A9957
0x1800a99d0  mov     rbx, qword ptr [rbp+FileSize]
0x1800a99d4  mov     eax, 0FFFFFFFFh
0x1800a99d9  cmp     rbx, rax
0x1800a99dc  jl      short loc_1800A9A00
0x1800a99de  mov     ebx, 80070216h
0x1800a99e3  mov     edx, 66h ; 'f'; void *
0x1800a99e8  mov     r9d, ebx; char *
0x1800a99eb  mov     rcx, [rbp+38h]; this
0x1800a99ef  lea     r8, aOnecoreuapAdmi_44; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a99f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a99fb  jmp     loc_1800A9ADF
0x1800a9a00  sub     ebx, edi
0x1800a9a02  jnz     short loc_1800A9A4B
0x1800a9a04  mov     rbx, [r14]
0x1800a9a07  test    rbx, rbx
0x1800a9a0a  jz      short loc_1800A9A27
0x1800a9a0c  lea     rcx, [rbp+charBuffer]; this
0x1800a9a10  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800a9a15  mov     rcx, rbx; string
0x1800a9a18  call    cs:__imp_WindowsDeleteString
0x1800a9a1e  lea     rcx, [rbp+charBuffer]; this
0x1800a9a22  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800a9a27  mov     r8, r14; string
0x1800a9a2a  mov     [r14], r13
0x1800a9a2d  xor     edx, edx; length
0x1800a9a2f  xor     ecx, ecx; sourceString
0x1800a9a31  call    cs:__imp_WindowsCreateString
0x1800a9a37  mov     ebx, eax
0x1800a9a39  test    eax, eax
0x1800a9a3b  jns     loc_1800A9ADC
0x1800a9a41  mov     r9d, eax
0x1800a9a44  mov     edx, 6Bh ; 'k'
0x1800a9a49  jmp     short loc_1800A99EB
0x1800a9a4b  mov     [rbp+lpBuffer], r13
0x1800a9a4f  mov     rdi, r13
0x1800a9a52  mov     [rbp+bufferHandle], r13
0x1800a9a56  cmp     r15d, 2
0x1800a9a5a  jnz     loc_1800A9B0E
0x1800a9a60  test    r12b, bl
0x1800a9a63  jz      short loc_1800A9A95
0x1800a9a65  mov     ebx, 8007000Dh
0x1800a9a6a  lea     edx, [r15+7Ah]; void *
0x1800a9a6e  mov     r9d, ebx; char *
0x1800a9a71  mov     rcx, [rbp+38h]; this
0x1800a9a75  lea     r8, aOnecoreuapAdmi_44; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a9a7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9a81  lea     rcx, [rbp+bufferHandle]
0x1800a9a85  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x1800a9a8a  lea     rcx, [rbp+lpBuffer]
0x1800a9a8e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a9a93  jmp     short loc_1800A9ADF
0x1800a9a95  mov     ecx, ebx
0x1800a9a97  mov     [rbp+charBuffer], r13
0x1800a9a9b  shr     ecx, 1; length
0x1800a9a9d  lea     r8, [rbp+bufferHandle]; bufferHandle
0x1800a9aa1  lea     rdx, [rbp+charBuffer]; charBuffer
0x1800a9aa5  call    cs:__imp_WindowsPreallocateStringBuffer
0x1800a9aab  mov     r13d, eax
0x1800a9aae  test    eax, eax
0x1800a9ab0  jns     short loc_1800A9B05
0x1800a9ab2  mov     rcx, [rbp+38h]; this
0x1800a9ab6  lea     r8, aOnecoreuapAdmi_44; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a9abd  mov     r9d, eax; char *
0x1800a9ac0  mov     edx, 81h; void *
0x1800a9ac5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9aca  lea     rcx, [rbp+bufferHandle]
0x1800a9ace  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x1800a9ad3  lea     rcx, [rbp+lpBuffer]
0x1800a9ad7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a9adc  mov     ebx, r13d
0x1800a9adf  lea     rcx, [rbp+var_10]
0x1800a9ae3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a9ae8  mov     eax, ebx
0x1800a9aea  mov     rbx, [rsp+80h+arg_0]
0x1800a9af2  add     rsp, 80h
0x1800a9af9  pop     r15
0x1800a9afb  pop     r14
0x1800a9afd  pop     r13
0x1800a9aff  pop     r12
0x1800a9b01  pop     rdi
0x1800a9b02  pop     rsi
0x1800a9b03  pop     rbp
0x1800a9b04  retn
0x1800a9b05  mov     rdx, [rbp+charBuffer]
0x1800a9b09  xor     r13d, r13d
0x1800a9b0c  jmp     short loc_1800A9B40
0x1800a9b0e  mov     ecx, ebx; cb
0x1800a9b10  call    cs:__imp_CoTaskMemAlloc
0x1800a9b16  mov     rdx, rax
0x1800a9b19  lea     rcx, [rbp+lpBuffer]
0x1800a9b1d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800a9b22  mov     rdi, [rbp+lpBuffer]
0x1800a9b26  test    rdi, rdi
0x1800a9b29  jnz     short loc_1800A9B3A
0x1800a9b2b  mov     ebx, 8007000Eh
0x1800a9b30  mov     edx, 89h
0x1800a9b35  jmp     loc_1800A9A6E
0x1800a9b3a  mov     r12b, r13b
0x1800a9b3d  mov     rdx, rdi; lpBuffer
0x1800a9b40  lea     r9, [rbp+arg_18]; lpNumberOfBytesRead
0x1800a9b44  mov     [rbp+arg_18], r13d
0x1800a9b48  mov     r8d, ebx; nNumberOfBytesToRead
0x1800a9b4b  mov     qword ptr [rsp+80h+dwCreationDisposition], r13; lpOverlapped
0x1800a9b50  mov     rcx, rsi; hFile
0x1800a9b53  call    cs:__imp_ReadFile
0x1800a9b59  test    eax, eax
0x1800a9b5b  jnz     short loc_1800A9B79
0x1800a9b5d  mov     rcx, [rbp+38h]; this
0x1800a9b61  lea     r8, aOnecoreuapAdmi_44; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a9b68  mov     edx, 94h; void *
0x1800a9b6d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a9b72  mov     ebx, eax
0x1800a9b74  jmp     loc_1800A9A81
0x1800a9b79  cmp     ebx, [rbp+arg_18]
0x1800a9b7c  jz      short loc_1800A9B8D
0x1800a9b7e  mov     ebx, 8000FFFFh
0x1800a9b83  mov     edx, 98h
0x1800a9b88  jmp     loc_1800A9A6E
0x1800a9b8d  test    r12b, r12b
0x1800a9b90  jz      short loc_1800A9BDB
0x1800a9b92  mov     rbx, [r14]
0x1800a9b95  test    rbx, rbx
0x1800a9b98  jz      short loc_1800A9BB5
0x1800a9b9a  lea     rcx, [rbp+var_18]; this
0x1800a9b9e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800a9ba3  mov     rcx, rbx; string
0x1800a9ba6  call    cs:__imp_WindowsDeleteString
0x1800a9bac  lea     rcx, [rbp+var_18]; this
0x1800a9bb0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800a9bb5  mov     rdx, r14
0x1800a9bb8  mov     [r14], r13
0x1800a9bbb  lea     rcx, [rbp+bufferHandle]
0x1800a9bbf  call    ?make_hstring_from_buffer_nothrow@wil@@YAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAPEAUHSTRING__@@@Z; wil::make_hstring_from_buffer_nothrow(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&,HSTRING__ * *)
0x1800a9bc4  mov     ebx, eax
0x1800a9bc6  test    eax, eax
0x1800a9bc8  jns     loc_1800A9ACA
0x1800a9bce  mov     r9d, eax
0x1800a9bd1  mov     edx, 9Ch
0x1800a9bd6  jmp     loc_1800A9A71
0x1800a9bdb  neg     r15d
0x1800a9bde  mov     r9, r14
0x1800a9be1  mov     r8d, ebx; cbMultiByte
0x1800a9be4  mov     rdx, rdi; lpMultiByteStr
0x1800a9be7  sbb     ecx, ecx
0x1800a9be9  and     ecx, 0FDE9h; CodePage
0x1800a9bef  call    ?ConvertRawBytesToString@DCFileUtils@@SAJIPEBDHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; DCFileUtils::ConvertRawBytesToString(uint,char const *,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x1800a9bf4  mov     ebx, eax
0x1800a9bf6  test    eax, eax
0x1800a9bf8  jns     loc_1800A9ACA
0x1800a9bfe  mov     r9d, eax
0x1800a9c01  mov     edx, 0A1h
0x1800a9c06  jmp     loc_1800A9A71
```
