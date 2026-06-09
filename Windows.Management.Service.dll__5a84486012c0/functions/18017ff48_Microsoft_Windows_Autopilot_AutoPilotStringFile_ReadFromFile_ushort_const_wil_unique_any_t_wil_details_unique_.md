# Microsoft::Windows::Autopilot::AutoPilotStringFile::ReadFromFile(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x18017ff48`
- end: `0x18018023e`
- name: `?ReadFromFile@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `758`
- prototype: `__int64 __fastcall(const WCHAR *, HSTRING *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180091e88`
- `0x18017fcd8`
- `0x1801c7c64`

## callees

- `0x180066918`
- `0x180067a34`
- `0x180067a54`
- `0x18008cfa4`
- `0x18008f6a8`
- `0x1800cff04`
- `0x18017f614`
- `0x18017f68c`
- `0x18017ff48`
- `0x180180378`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180180090`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180180090`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180180104`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180180104`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018016c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018016c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180180022`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180180022`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18018003c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18018003c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18017ff88`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18017ff88`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18017ffc5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801801a4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18017ffc5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801801a4`

## string_xrefs

- `0x18017ffd6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x18018006a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x1801800d4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x180180115`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x1801801b2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16 #try_helpers=1
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
0x18017ff48  mov     [rsp-38h+arg_0], rbx
0x18017ff4d  push    rbp
0x18017ff4e  push    rsi
0x18017ff4f  push    rdi
0x18017ff50  push    r12
0x18017ff52  push    r13
0x18017ff54  push    r14
0x18017ff56  push    r15
0x18017ff58  mov     rbp, rsp
0x18017ff5b  sub     rsp, 70h
0x18017ff5f  xor     r12d, r12d
0x18017ff62  mov     r13, rdx
0x18017ff65  mov     [rsp+70h+hTemplateFile], r12; hTemplateFile
0x18017ff6a  xor     r9d, r9d; lpSecurityAttributes
0x18017ff6d  mov     [rsp+70h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18017ff72  mov     edx, 120089h; dwDesiredAccess
0x18017ff77  lea     r15d, [r12+1]
0x18017ff7c  lea     edi, [r12+3]
0x18017ff81  mov     r8d, r15d; dwShareMode
0x18017ff84  mov     [rsp+70h+dwCreationDisposition], edi; dwCreationDisposition
0x18017ff88  call    cs:__imp_CreateFileW
0x18017ff8e  mov     rsi, rax
0x18017ff91  mov     [rbp+var_8], rax
0x18017ff95  inc     rax
0x18017ff98  test    rax, 0FFFFFFFFFFFFFFFEh
0x18017ff9e  jnz     short loc_18017FFA7
0x18017ffa0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18017ffa5  jmp     short loc_18017FFE2
0x18017ffa7  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18017ffab  mov     [rbp+Buffer], r12d
0x18017ffaf  mov     r8d, 4; nNumberOfBytesToRead
0x18017ffb5  mov     [rbp+NumberOfBytesRead], r12d
0x18017ffb9  lea     rdx, [rbp+Buffer]; lpBuffer
0x18017ffbd  mov     qword ptr [rsp+70h+dwCreationDisposition], r12; int
0x18017ffc2  mov     rcx, rsi; hFile
0x18017ffc5  call    cs:__imp_ReadFile
0x18017ffcb  test    eax, eax
0x18017ffcd  jnz     short loc_18017FFE9
0x18017ffcf  lea     edx, [rax+39h]; void *
0x18017ffd2  mov     rcx, [rbp+38h]; this
0x18017ffd6  lea     r8, aOnecoreuapAdmi_152; "onecoreuap\\admin\\moderndeployment\\au"...
0x18017ffdd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18017ffe2  mov     ebx, eax
0x18017ffe4  jmp     loc_18018013E
0x18017ffe9  mov     eax, [rbp+Buffer]
0x18017ffec  mov     ecx, 2
0x18017fff1  and     eax, 0FFFFFFh
0x18017fff6  cmp     eax, 0BFBBEFh
0x18017fffb  jnz     short loc_180180002
0x18017fffd  mov     r14d, r15d
0x180180000  jmp     short loc_180180017
0x180180002  cmp     word ptr [rbp+Buffer], 0FEFFh
0x180180008  jnz     short loc_180180011
0x18018000a  mov     edi, ecx
0x18018000c  mov     r14d, ecx
0x18018000f  jmp     short loc_180180017
0x180180011  mov     edi, r12d
0x180180014  mov     r14d, r12d
0x180180017  mov     edx, edi; liDistanceToMove
0x180180019  xor     r9d, r9d; dwMoveMethod
0x18018001c  xor     r8d, r8d; lpNewFilePointer
0x18018001f  mov     rcx, rsi; hFile
0x180180022  call    cs:__imp_SetFilePointerEx
0x180180028  test    eax, eax
0x18018002a  jnz     short loc_180180031
0x18018002c  lea     edx, [rax+44h]
0x18018002f  jmp     short loc_18017FFD2
0x180180031  lea     rdx, [rbp+FileSize]; lpFileSize
0x180180035  mov     qword ptr [rbp+FileSize], r12
0x180180039  mov     rcx, rsi; hFile
0x18018003c  call    cs:__imp_GetFileSizeEx
0x180180042  test    eax, eax
0x180180044  jnz     short loc_18018004B
0x180180046  lea     edx, [rax+47h]
0x180180049  jmp     short loc_18017FFD2
0x18018004b  mov     rbx, qword ptr [rbp+FileSize]
0x18018004f  mov     eax, 0FFFFFFFFh
0x180180054  cmp     rbx, rax
0x180180057  jl      short loc_18018007B
0x180180059  mov     ebx, 80070216h
0x18018005e  mov     edx, 48h ; 'H'; void *
0x180180063  mov     r9d, ebx; char *
0x180180066  mov     rcx, [rbp+38h]; this
0x18018006a  lea     r8, aOnecoreuapAdmi_152; "onecoreuap\\admin\\moderndeployment\\au"...
0x180180071  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180180076  jmp     loc_18018013E
0x18018007b  sub     ebx, edi
0x18018007d  jnz     short loc_1801800AA
0x18018007f  xor     edx, edx
0x180180081  mov     rcx, r13
0x180180084  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180180089  mov     r8, r13; string
0x18018008c  xor     edx, edx; length
0x18018008e  xor     ecx, ecx; sourceString
0x180180090  call    cs:__imp_WindowsCreateString
0x180180096  mov     ebx, eax
0x180180098  test    eax, eax
0x18018009a  jns     loc_18018013B
0x1801800a0  mov     r9d, eax
0x1801800a3  mov     edx, 4Dh ; 'M'
0x1801800a8  jmp     short loc_180180066
0x1801800aa  mov     [rbp+var_20], r12
0x1801800ae  mov     rdi, r12
0x1801800b1  mov     [rbp+bufferHandle], r12
0x1801800b5  cmp     r14d, 2
0x1801800b9  jnz     loc_18018016A
0x1801800bf  test    r15b, bl
0x1801800c2  jz      short loc_1801800F4
0x1801800c4  mov     ebx, 8007000Dh
0x1801800c9  lea     edx, [r14+5Ch]; void *
0x1801800cd  mov     r9d, ebx; char *
0x1801800d0  mov     rcx, [rbp+38h]; this
0x1801800d4  lea     r8, aOnecoreuapAdmi_152; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801800db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801800e0  lea     rcx, [rbp+bufferHandle]
0x1801800e4  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x1801800e9  lea     rcx, [rbp+var_20]
0x1801800ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801800f2  jmp     short loc_18018013E
0x1801800f4  mov     ecx, ebx
0x1801800f6  mov     [rbp+charBuffer], r12
0x1801800fa  shr     ecx, 1; length
0x1801800fc  lea     r8, [rbp+bufferHandle]; bufferHandle
0x180180100  lea     rdx, [rbp+charBuffer]; charBuffer
0x180180104  call    cs:__imp_WindowsPreallocateStringBuffer
0x18018010a  mov     r12d, eax
0x18018010d  test    eax, eax
0x18018010f  jns     short loc_180180161
0x180180111  mov     rcx, [rbp+38h]; this
0x180180115  lea     r8, aOnecoreuapAdmi_152; "onecoreuap\\admin\\moderndeployment\\au"...
0x18018011c  mov     r9d, eax; char *
0x18018011f  mov     edx, 63h ; 'c'; void *
0x180180124  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180180129  lea     rcx, [rbp+bufferHandle]
0x18018012d  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x180180132  lea     rcx, [rbp+var_20]
0x180180136  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18018013b  mov     ebx, r12d
0x18018013e  lea     rcx, [rbp+var_8]
0x180180142  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180180147  mov     eax, ebx
0x180180149  mov     rbx, [rsp+70h+arg_0]
0x180180151  add     rsp, 70h
0x180180155  pop     r15
0x180180157  pop     r14
0x180180159  pop     r13
0x18018015b  pop     r12
0x18018015d  pop     rdi
0x18018015e  pop     rsi
0x18018015f  pop     rbp
0x180180160  retn
0x180180161  mov     rdx, [rbp+charBuffer]
0x180180165  xor     r12d, r12d
0x180180168  jmp     short loc_180180191
0x18018016a  mov     ecx, ebx; cb
0x18018016c  call    cs:__imp_CoTaskMemAlloc
0x180180172  mov     [rbp+var_20], rax
0x180180176  mov     rdi, rax
0x180180179  test    rax, rax
0x18018017c  jnz     short loc_18018018B
0x18018017e  mov     ebx, 8007000Eh
0x180180183  lea     edx, [rax+6Bh]
0x180180186  jmp     loc_1801800CD
0x18018018b  mov     r15b, r12b
0x18018018e  mov     rdx, rax; lpBuffer
0x180180191  lea     r9, [rbp+arg_18]; lpNumberOfBytesRead
0x180180195  mov     [rbp+arg_18], r12d
0x180180199  mov     r8d, ebx; nNumberOfBytesToRead
0x18018019c  mov     qword ptr [rsp+70h+dwCreationDisposition], r12; lpOverlapped
0x1801801a1  mov     rcx, rsi; hFile
0x1801801a4  call    cs:__imp_ReadFile
0x1801801aa  test    eax, eax
0x1801801ac  jnz     short loc_1801801C8
0x1801801ae  mov     rcx, [rbp+38h]; this
0x1801801b2  lea     r8, aOnecoreuapAdmi_152; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801801b9  lea     edx, [rax+76h]; void *
0x1801801bc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801801c1  mov     ebx, eax
0x1801801c3  jmp     loc_1801800E0
0x1801801c8  cmp     ebx, [rbp+arg_18]
0x1801801cb  jz      short loc_1801801DC
0x1801801cd  mov     ebx, 8000FFFFh
0x1801801d2  mov     edx, 7Ah ; 'z'
0x1801801d7  jmp     loc_1801800CD
0x1801801dc  test    r15b, r15b
0x1801801df  jz      short loc_18018020E
0x1801801e1  xor     edx, edx
0x1801801e3  mov     rcx, r13
0x1801801e6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1801801eb  mov     rdx, r13
0x1801801ee  lea     rcx, [rbp+bufferHandle]
0x1801801f2  call    ?make_hstring_from_buffer_nothrow@wil@@YAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAPEAUHSTRING__@@@Z; wil::make_hstring_from_buffer_nothrow(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&,HSTRING__ * *)
0x1801801f7  mov     ebx, eax
0x1801801f9  test    eax, eax
0x1801801fb  jns     loc_180180129
0x180180201  mov     r9d, eax
0x180180204  mov     edx, 7Eh ; '~'
0x180180209  jmp     loc_1801800D0
0x18018020e  neg     r14d
0x180180211  mov     r9, r13
0x180180214  mov     r8d, ebx; cbMultiByte
0x180180217  mov     rdx, rdi; lpMultiByteStr
0x18018021a  sbb     ecx, ecx
0x18018021c  and     ecx, 0FDE9h; CodePage
0x180180222  call    ?ConvertRawBytesToString@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJIPEBDHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(uint,char const *,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x180180227  mov     ebx, eax
0x180180229  test    eax, eax
0x18018022b  jns     loc_180180129
0x180180231  mov     r9d, eax
0x180180234  mov     edx, 83h
0x180180239  jmp     loc_1801800D0
```
