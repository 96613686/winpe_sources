# Microsoft::Windows::Autopilot::AutoPilotStringFile::ReadFromFile(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x1801849dc`
- end: `0x180184d06`
- name: `?ReadFromFile@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `810`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800930a0`
- `0x180184750`
- `0x1801cd9f0`

## callees

- `0x180066c60`
- `0x180067e34`
- `0x180067e54`
- `0x18008e088`
- `0x180090810`
- `0x1800d238c`
- `0x180184004`
- `0x18018408c`
- `0x1801849dc`
- `0x180184e54`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180184b3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180184b3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180184bb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180184bb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180184c28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180184c28`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180184ac2`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180184ac2`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180184ae2`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180184ae2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180184a1c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180184a1c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180184a5f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180184c66`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180184a5f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180184c66`

## string_xrefs

- `0x180184a76`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x180184b19`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x180184b89`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x180184bd0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x180184c7a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStringFile::ReadFromFile(const WCHAR *a1, HSTRING *a2)
{
  HRESULT v2; // r12d
  char v4; // r15
  unsigned int v5; // edi
  wil::details *v6; // rcx
  HANDLE FileW; // rsi
  unsigned int LastError; // eax
  const char *v9; // r9
  __int64 v10; // rdx
  unsigned int v11; // ebx
  int v12; // r14d
  __int64 v13; // rdx
  __int64 v14; // r9
  DWORD v15; // ebx
  HRESULT String; // eax
  const CHAR *v17; // rdi
  __int64 v18; // rdx
  unsigned __int64 v19; // r9
  HRESULT v20; // eax
  WCHAR *v22; // rdx
  CHAR *v23; // rax
  const char *v24; // r9
  int hstring_from_buffer_nothrow; // eax
  int v26; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-50h]
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_BUFFER bufferHandle; // [rsp+48h] [rbp-28h] BYREF
  CHAR *v30; // [rsp+50h] [rbp-20h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+58h] [rbp-18h] BYREF
  WCHAR *charBuffer; // [rsp+60h] [rbp-10h] BYREF
  HANDLE v33; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int Buffer; // [rsp+C0h] [rbp+50h] BYREF
  DWORD v36; // [rsp+C8h] [rbp+58h] BYREF

  v2 = 0;
  v4 = 1;
  v5 = 3;
  FileW = CreateFileW(a1, 0x120089u, 1u, 0, 3u, 0, 0);
  v33 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    Buffer = 0;
    NumberOfBytesRead = 0;
    if ( !ReadFile(FileW, &Buffer, 4u, &NumberOfBytesRead, 0) )
    {
      v10 = 57;
LABEL_5:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v10,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
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
      v10 = 68;
      goto LABEL_5;
    }
    FileSize.QuadPart = 0;
    if ( !GetFileSizeEx(FileW, &FileSize) )
    {
      v10 = 71;
      goto LABEL_5;
    }
    if ( FileSize.QuadPart >= 0xFFFFFFFFLL )
    {
      v11 = -2147024362;
      v13 = 72;
      v14 = 2147942934LL;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
        (const char *)v14,
        dwCreationDisposition);
      goto LABEL_32;
    }
    v15 = FileSize.LowPart - v5;
    if ( FileSize.LowPart == v5 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        a2,
        0);
      String = WindowsCreateString(0, 0, a2);
      v11 = String;
      if ( String < 0 )
      {
        v14 = (unsigned int)String;
        v13 = 77;
        goto LABEL_18;
      }
LABEL_31:
      v11 = v2;
      goto LABEL_32;
    }
    v30 = 0;
    v17 = 0;
    bufferHandle = 0;
    if ( v12 == 2 )
    {
      if ( (v15 & 1) != 0 )
      {
        v11 = -2147024883;
        v18 = 94;
LABEL_25:
        v19 = v11;
LABEL_26:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
          (const char *)v19,
          dwCreationDisposition);
LABEL_27:
        wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&bufferHandle);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v30);
        goto LABEL_32;
      }
      charBuffer = 0;
      v20 = WindowsPreallocateStringBuffer(v15 >> 1, &charBuffer, &bufferHandle);
      v2 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x63,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
          (const char *)(unsigned int)v20,
          dwCreationDisposition);
        goto LABEL_30;
      }
      v22 = charBuffer;
      v2 = 0;
    }
    else
    {
      v23 = (CHAR *)CoTaskMemAlloc(v15);
      v30 = v23;
      v17 = v23;
      if ( !v23 )
      {
        v11 = -2147024882;
        v18 = 107;
        goto LABEL_25;
      }
      v4 = 0;
      v22 = (WCHAR *)v23;
    }
    v36 = 0;
    if ( !ReadFile(FileW, v22, v15, &v36, 0) )
    {
      v11 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x76,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
              v24);
      goto LABEL_27;
    }
    if ( v15 != v36 )
    {
      v11 = -2147418113;
      v18 = 122;
      goto LABEL_25;
    }
    if ( v4 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        a2,
        0);
      hstring_from_buffer_nothrow = wil::make_hstring_from_buffer_nothrow(&bufferHandle, a2);
      v11 = hstring_from_buffer_nothrow;
      if ( hstring_from_buffer_nothrow < 0 )
      {
        v19 = (unsigned int)hstring_from_buffer_nothrow;
        v18 = 126;
        goto LABEL_26;
      }
    }
    else
    {
      v26 = Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(v12 != 0 ? 0xFDE9 : 0, v17, v15);
      v11 = v26;
      if ( v26 < 0 )
      {
        v19 = (unsigned int)v26;
        v18 = 131;
        goto LABEL_26;
      }
    }
LABEL_30:
    wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&bufferHandle);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v30);
    goto LABEL_31;
  }
  LastError = wil::details::GetLastErrorFailHr(v6);
LABEL_6:
  v11 = LastError;
LABEL_32:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
  return v11;
}

```

## disassembly

```asm
0x1801849dc  mov     [rsp-38h+arg_0], rbx
0x1801849e1  push    rbp
0x1801849e2  push    rsi
0x1801849e3  push    rdi
0x1801849e4  push    r12
0x1801849e6  push    r13
0x1801849e8  push    r14
0x1801849ea  push    r15
0x1801849ec  mov     rbp, rsp
0x1801849ef  sub     rsp, 70h
0x1801849f3  xor     r12d, r12d
0x1801849f6  mov     r13, rdx
0x1801849f9  mov     [rsp+70h+hTemplateFile], r12; hTemplateFile
0x1801849fe  xor     r9d, r9d; lpSecurityAttributes
0x180184a01  mov     [rsp+70h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180184a06  mov     edx, 120089h; dwDesiredAccess
0x180184a0b  lea     r15d, [r12+1]
0x180184a10  lea     edi, [r12+3]
0x180184a15  mov     r8d, r15d; dwShareMode
0x180184a18  mov     [rsp+70h+dwCreationDisposition], edi; dwCreationDisposition
0x180184a1c  call    cs:__imp_CreateFileW
0x180184a23  nop     dword ptr [rax+rax+00h]
0x180184a28  mov     rsi, rax
0x180184a2b  mov     [rbp+var_8], rax
0x180184a2f  inc     rax
0x180184a32  test    rax, 0FFFFFFFFFFFFFFFEh
0x180184a38  jnz     short loc_180184A41
0x180184a3a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180184a3f  jmp     short loc_180184A82
0x180184a41  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180184a45  mov     [rbp+Buffer], r12d
0x180184a49  mov     r8d, 4; nNumberOfBytesToRead
0x180184a4f  mov     [rbp+NumberOfBytesRead], r12d
0x180184a53  lea     rdx, [rbp+Buffer]; lpBuffer
0x180184a57  mov     qword ptr [rsp+70h+dwCreationDisposition], r12; int
0x180184a5c  mov     rcx, rsi; hFile
0x180184a5f  call    cs:__imp_ReadFile
0x180184a66  nop     dword ptr [rax+rax+00h]
0x180184a6b  test    eax, eax
0x180184a6d  jnz     short loc_180184A89
0x180184a6f  lea     edx, [rax+39h]; void *
0x180184a72  mov     rcx, [rbp+38h]; this
0x180184a76  lea     r8, aOnecoreuapAdmi_152; "onecoreuap\\admin\\moderndeployment\\au"...
0x180184a7d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180184a82  mov     ebx, eax
0x180184a84  jmp     loc_180184BF9
0x180184a89  mov     eax, [rbp+Buffer]
0x180184a8c  mov     ecx, 2
0x180184a91  and     eax, 0FFFFFFh
0x180184a96  cmp     eax, 0BFBBEFh
0x180184a9b  jnz     short loc_180184AA2
0x180184a9d  mov     r14d, r15d
0x180184aa0  jmp     short loc_180184AB7
0x180184aa2  cmp     word ptr [rbp+Buffer], 0FEFFh
0x180184aa8  jnz     short loc_180184AB1
0x180184aaa  mov     edi, ecx
0x180184aac  mov     r14d, ecx
0x180184aaf  jmp     short loc_180184AB7
0x180184ab1  mov     edi, r12d
0x180184ab4  mov     r14d, r12d
0x180184ab7  mov     edx, edi; liDistanceToMove
0x180184ab9  xor     r9d, r9d; dwMoveMethod
0x180184abc  xor     r8d, r8d; lpNewFilePointer
0x180184abf  mov     rcx, rsi; hFile
0x180184ac2  call    cs:__imp_SetFilePointerEx
0x180184ac9  nop     dword ptr [rax+rax+00h]
0x180184ace  test    eax, eax
0x180184ad0  jnz     short loc_180184AD7
0x180184ad2  lea     edx, [rax+44h]
0x180184ad5  jmp     short loc_180184A72
0x180184ad7  lea     rdx, [rbp+FileSize]; lpFileSize
0x180184adb  mov     qword ptr [rbp+FileSize], r12
0x180184adf  mov     rcx, rsi; hFile
0x180184ae2  call    cs:__imp_GetFileSizeEx
0x180184ae9  nop     dword ptr [rax+rax+00h]
0x180184aee  test    eax, eax
0x180184af0  jnz     short loc_180184AFA
0x180184af2  lea     edx, [rax+47h]
0x180184af5  jmp     loc_180184A72
0x180184afa  mov     rbx, qword ptr [rbp+FileSize]
0x180184afe  mov     eax, 0FFFFFFFFh
0x180184b03  cmp     rbx, rax
0x180184b06  jl      short loc_180184B2A
0x180184b08  mov     ebx, 80070216h
0x180184b0d  mov     edx, 48h ; 'H'; void *
0x180184b12  mov     r9d, ebx; char *
0x180184b15  mov     rcx, [rbp+38h]; this
0x180184b19  lea     r8, aOnecoreuapAdmi_152; "onecoreuap\\admin\\moderndeployment\\au"...
0x180184b20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180184b25  jmp     loc_180184BF9
0x180184b2a  sub     ebx, edi
0x180184b2c  jnz     short loc_180184B5F
0x180184b2e  xor     edx, edx
0x180184b30  mov     rcx, r13
0x180184b33  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180184b38  mov     r8, r13; string
0x180184b3b  xor     edx, edx; length
0x180184b3d  xor     ecx, ecx; sourceString
0x180184b3f  call    cs:__imp_WindowsCreateString
0x180184b46  nop     dword ptr [rax+rax+00h]
0x180184b4b  mov     ebx, eax
0x180184b4d  test    eax, eax
0x180184b4f  jns     loc_180184BF6
0x180184b55  mov     r9d, eax
0x180184b58  mov     edx, 4Dh ; 'M'
0x180184b5d  jmp     short loc_180184B15
0x180184b5f  mov     [rbp+var_20], r12
0x180184b63  mov     rdi, r12
0x180184b66  mov     [rbp+bufferHandle], r12
0x180184b6a  cmp     r14d, 2
0x180184b6e  jnz     loc_180184C26
0x180184b74  test    r15b, bl
0x180184b77  jz      short loc_180184BA9
0x180184b79  mov     ebx, 8007000Dh
0x180184b7e  lea     edx, [r14+5Ch]; void *
0x180184b82  mov     r9d, ebx; char *
0x180184b85  mov     rcx, [rbp+38h]; this
0x180184b89  lea     r8, aOnecoreuapAdmi_152; "onecoreuap\\admin\\moderndeployment\\au"...
0x180184b90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180184b95  lea     rcx, [rbp+bufferHandle]
0x180184b99  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x180184b9e  lea     rcx, [rbp+var_20]
0x180184ba2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180184ba7  jmp     short loc_180184BF9
0x180184ba9  mov     ecx, ebx
0x180184bab  mov     [rbp+charBuffer], r12
0x180184baf  shr     ecx, 1; length
0x180184bb1  lea     r8, [rbp+bufferHandle]; bufferHandle
0x180184bb5  lea     rdx, [rbp+charBuffer]; charBuffer
0x180184bb9  call    cs:__imp_WindowsPreallocateStringBuffer
0x180184bc0  nop     dword ptr [rax+rax+00h]
0x180184bc5  mov     r12d, eax
0x180184bc8  test    eax, eax
0x180184bca  jns     short loc_180184C1D
0x180184bcc  mov     rcx, [rbp+38h]; this
0x180184bd0  lea     r8, aOnecoreuapAdmi_152; "onecoreuap\\admin\\moderndeployment\\au"...
0x180184bd7  mov     r9d, eax; char *
0x180184bda  mov     edx, 63h ; 'c'; void *
0x180184bdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180184be4  lea     rcx, [rbp+bufferHandle]
0x180184be8  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x180184bed  lea     rcx, [rbp+var_20]
0x180184bf1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180184bf6  mov     ebx, r12d
0x180184bf9  lea     rcx, [rbp+var_8]
0x180184bfd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180184c02  mov     eax, ebx
0x180184c04  mov     rbx, [rsp+70h+arg_0]
0x180184c0c  add     rsp, 70h
0x180184c10  pop     r15
0x180184c12  pop     r14
0x180184c14  pop     r13
0x180184c16  pop     r12
0x180184c18  pop     rdi
0x180184c19  pop     rsi
0x180184c1a  pop     rbp
0x180184c1b  retn
0x180184c1d  mov     rdx, [rbp+charBuffer]
0x180184c21  xor     r12d, r12d
0x180184c24  jmp     short loc_180184C53
0x180184c26  mov     ecx, ebx; cb
0x180184c28  call    cs:__imp_CoTaskMemAlloc
0x180184c2f  nop     dword ptr [rax+rax+00h]
0x180184c34  mov     [rbp+var_20], rax
0x180184c38  mov     rdi, rax
0x180184c3b  test    rax, rax
0x180184c3e  jnz     short loc_180184C4D
0x180184c40  mov     ebx, 8007000Eh
0x180184c45  lea     edx, [rax+6Bh]
0x180184c48  jmp     loc_180184B82
0x180184c4d  mov     r15b, r12b
0x180184c50  mov     rdx, rax; lpBuffer
0x180184c53  lea     r9, [rbp+arg_18]; lpNumberOfBytesRead
0x180184c57  mov     [rbp+arg_18], r12d
0x180184c5b  mov     r8d, ebx; nNumberOfBytesToRead
0x180184c5e  mov     qword ptr [rsp+70h+dwCreationDisposition], r12; lpOverlapped
0x180184c63  mov     rcx, rsi; hFile
0x180184c66  call    cs:__imp_ReadFile
0x180184c6d  nop     dword ptr [rax+rax+00h]
0x180184c72  test    eax, eax
0x180184c74  jnz     short loc_180184C90
0x180184c76  mov     rcx, [rbp+38h]; this
0x180184c7a  lea     r8, aOnecoreuapAdmi_152; "onecoreuap\\admin\\moderndeployment\\au"...
0x180184c81  lea     edx, [rax+76h]; void *
0x180184c84  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180184c89  mov     ebx, eax
0x180184c8b  jmp     loc_180184B95
0x180184c90  cmp     ebx, [rbp+arg_18]
0x180184c93  jz      short loc_180184CA4
0x180184c95  mov     ebx, 8000FFFFh
0x180184c9a  mov     edx, 7Ah ; 'z'
0x180184c9f  jmp     loc_180184B82
0x180184ca4  test    r15b, r15b
0x180184ca7  jz      short loc_180184CD6
0x180184ca9  xor     edx, edx
0x180184cab  mov     rcx, r13
0x180184cae  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180184cb3  mov     rdx, r13
0x180184cb6  lea     rcx, [rbp+bufferHandle]
0x180184cba  call    ?make_hstring_from_buffer_nothrow@wil@@YAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAPEAUHSTRING__@@@Z; wil::make_hstring_from_buffer_nothrow(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&,HSTRING__ * *)
0x180184cbf  mov     ebx, eax
0x180184cc1  test    eax, eax
0x180184cc3  jns     loc_180184BE4
0x180184cc9  mov     r9d, eax
0x180184ccc  mov     edx, 7Eh ; '~'
0x180184cd1  jmp     loc_180184B85
0x180184cd6  neg     r14d
0x180184cd9  mov     r9, r13
0x180184cdc  mov     r8d, ebx; cbMultiByte
0x180184cdf  mov     rdx, rdi; lpMultiByteStr
0x180184ce2  sbb     ecx, ecx
0x180184ce4  and     ecx, 0FDE9h; CodePage
0x180184cea  call    ?ConvertRawBytesToString@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJIPEBDHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(uint,char const *,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x180184cef  mov     ebx, eax
0x180184cf1  test    eax, eax
0x180184cf3  jns     loc_180184BE4
0x180184cf9  mov     r9d, eax
0x180184cfc  mov     edx, 83h
0x180184d01  jmp     loc_180184B85
```
