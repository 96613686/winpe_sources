# Microsoft::Windows::Autopilot::AutoPilotStringFile::ReadFromFile(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x180026358`
- end: `0x180026723`
- name: `?ReadFromFile@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `971`
- prototype: `__int64 __fastcall(const WCHAR *, HSTRING *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18001a510`
- `0x18001a8b4`
- `0x18001c958`

## callees

- `0x18000d5c0`
- `0x180010744`
- `0x180010764`
- `0x1800261a8`
- `0x180026358`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002660c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800266ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002660c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800266ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026590`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026590`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800264bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800264bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026650`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800264da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002666f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800264da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002666f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x180026685`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x180026685`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180026569`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180026569`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180026548`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800265f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800266d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180026548`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800265f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800266d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800264f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800264f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800264cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026661`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800264cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026661`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800266fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800266fc`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002646a`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002646a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800263e7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800265ca`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800263e7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800265ca`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180026435`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180026435`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026395`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026395`

## string_xrefs

- `0x18002644c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x18002649e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x18002652f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x1800265de`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x180026632`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStringFile::ReadFromFile(const WCHAR *a1, HSTRING *a2)
{
  char v3; // r12
  unsigned int v4; // ebx
  wil::details *v5; // rcx
  char *FileW; // rsi
  unsigned int LastError; // ebx
  const char *v8; // r9
  __int64 v9; // rdx
  int v10; // r15d
  __int64 v11; // rdx
  __int64 v12; // r9
  DWORD v13; // edi
  HSTRING v14; // rdi
  DWORD v15; // ebx
  HRESULT String; // eax
  __int64 v17; // rdx
  unsigned __int64 v18; // r9
  HRESULT v19; // eax
  WCHAR *v20; // rdx
  void *v21; // rbx
  LPVOID v22; // rax
  const char *v23; // r9
  HRESULT v24; // edi
  __int64 v25; // rdx
  HSTRING v26; // r15
  DWORD v27; // edi
  HSTRING_BUFFER v28; // rcx
  int lpOverlapped; // [rsp+20h] [rbp-40h]
  int lpOverlappeda; // [rsp+20h] [rbp-40h]
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-20h] BYREF
  HSTRING_BUFFER bufferHandle; // [rsp+48h] [rbp-18h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp-10h] BYREF
  WCHAR *charBuffer; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  int Buffer; // [rsp+B0h] [rbp+50h] BYREF
  DWORD v38; // [rsp+B8h] [rbp+58h] BYREF

  v3 = 1;
  v4 = 3;
  FileW = (char *)CreateFileW(a1, 0x120089u, 1u, 0, 3u, 0, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    Buffer = 0;
    NumberOfBytesRead = 0;
    if ( !ReadFile(FileW, &Buffer, 4u, &NumberOfBytesRead, 0) )
    {
      v9 = 57;
LABEL_13:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v9,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
                    v8);
LABEL_59:
      CloseHandle(FileW);
      return LastError;
    }
    if ( (Buffer & 0xFFFFFF) == 0xBFBBEF )
    {
      v10 = 1;
    }
    else if ( (_WORD)Buffer == 0xFEFF )
    {
      v4 = 2;
      v10 = 2;
    }
    else
    {
      v4 = 0;
      v10 = 0;
    }
    if ( !SetFilePointerEx(FileW, (LARGE_INTEGER)v4, 0, 0) )
    {
      v9 = 68;
      goto LABEL_13;
    }
    FileSize.QuadPart = 0;
    if ( !GetFileSizeEx(FileW, &FileSize) )
    {
      v9 = 71;
      goto LABEL_13;
    }
    if ( FileSize.QuadPart >= 0xFFFFFFFFLL )
    {
      LastError = -2147024362;
      v11 = 72;
      v12 = 2147942934LL;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
        (const char *)v12,
        lpOverlapped);
      goto LABEL_59;
    }
    v13 = FileSize.LowPart - v4;
    if ( FileSize.LowPart == v4 )
    {
      v14 = *a2;
      if ( *a2 )
      {
        v15 = GetLastError();
        WindowsDeleteString(v14);
        SetLastError(v15);
      }
      *a2 = 0;
      String = WindowsCreateString(0, 0, a2);
      LastError = String;
      if ( String < 0 )
      {
        v12 = (unsigned int)String;
        v11 = 77;
        goto LABEL_18;
      }
LABEL_58:
      LastError = 0;
      goto LABEL_59;
    }
    bufferHandle = 0;
    if ( v10 == 2 )
    {
      if ( (v13 & 1) != 0 )
      {
        LastError = -2147024883;
        v17 = 94;
LABEL_27:
        v18 = LastError;
        goto LABEL_28;
      }
      charBuffer = 0;
      v19 = WindowsPreallocateStringBuffer(v13 >> 1, &charBuffer, &bufferHandle);
      LastError = v19;
      if ( v19 < 0 )
      {
        v18 = (unsigned int)v19;
        v17 = 99;
LABEL_28:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
          (const char *)v18,
          lpOverlapped);
        if ( bufferHandle )
          WindowsDeleteStringBuffer(bufferHandle);
        goto LABEL_59;
      }
      v20 = charBuffer;
      v21 = 0;
    }
    else
    {
      v22 = CoTaskMemAlloc(v13);
      v21 = v22;
      if ( !v22 )
      {
        LastError = -2147024882;
        v17 = 107;
        goto LABEL_27;
      }
      v3 = 0;
      v20 = (WCHAR *)v22;
    }
    v38 = 0;
    if ( !ReadFile(FileW, v20, v13, &v38, 0) )
    {
      v24 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x76,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
              v23);
LABEL_38:
      if ( bufferHandle )
        WindowsDeleteStringBuffer(bufferHandle);
      if ( v21 )
        CoTaskMemFree(v21);
      LastError = v24;
      goto LABEL_59;
    }
    if ( v13 != v38 )
    {
      v24 = -2147418113;
      v25 = 122;
LABEL_45:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
        (const char *)(unsigned int)v24,
        lpOverlappeda);
      goto LABEL_38;
    }
    if ( v3 )
    {
      v26 = *a2;
      if ( *a2 )
      {
        v27 = GetLastError();
        WindowsDeleteString(v26);
        SetLastError(v27);
      }
      v28 = bufferHandle;
      *a2 = 0;
      v24 = WindowsPromoteStringBuffer(v28, a2);
      if ( v24 < 0 )
      {
        v25 = 126;
        goto LABEL_45;
      }
      bufferHandle = 0;
    }
    else
    {
      v24 = Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(
              v10 != 0 ? 0xFDE9 : 0,
              (LPCCH)v21,
              v13,
              a2);
      if ( v24 < 0 )
      {
        v25 = 131;
        goto LABEL_45;
      }
      if ( bufferHandle )
        WindowsDeleteStringBuffer(bufferHandle);
    }
    if ( v21 )
      CoTaskMemFree(v21);
    goto LABEL_58;
  }
  LastError = wil::details::GetLastErrorFailHr(v5);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_59;
  return LastError;
}

```

## disassembly

```asm
0x180026358  mov     rax, rsp
0x18002635b  mov     [rax+8], rbx
0x18002635f  push    rbp
0x180026360  push    rsi
0x180026361  push    rdi
0x180026362  push    r12
0x180026364  push    r13
0x180026366  push    r14
0x180026368  push    r15
0x18002636a  mov     rbp, rsp
0x18002636d  sub     rsp, 60h
0x180026371  xor     r13d, r13d
0x180026374  mov     r14, rdx
0x180026377  mov     [rax-68h], r13
0x18002637b  xor     r9d, r9d; lpSecurityAttributes
0x18002637e  mov     [rax-70h], r13d
0x180026382  mov     edx, 120089h; dwDesiredAccess
0x180026387  lea     r12d, [r13+1]
0x18002638b  lea     ebx, [r13+3]
0x18002638f  mov     r8d, r12d; dwShareMode
0x180026392  mov     [rax-78h], ebx
0x180026395  call    cs:__imp_CreateFileW
0x18002639c  nop     dword ptr [rax+rax+00h]
0x1800263a1  mov     rsi, rax
0x1800263a4  inc     rax
0x1800263a7  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800263ad  jnz     short loc_1800263C9
0x1800263af  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800263b4  lea     rcx, [rsi-1]
0x1800263b8  mov     ebx, eax
0x1800263ba  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800263be  ja      loc_180026708
0x1800263c4  jmp     loc_1800266F9
0x1800263c9  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800263cd  mov     [rbp+Buffer], r13d
0x1800263d1  mov     r8d, 4; nNumberOfBytesToRead
0x1800263d7  mov     [rbp+NumberOfBytesRead], r13d
0x1800263db  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800263df  mov     qword ptr [rsp+60h+lpOverlapped], r13; int
0x1800263e4  mov     rcx, rsi; hFile
0x1800263e7  call    cs:__imp_ReadFile
0x1800263ee  nop     dword ptr [rax+rax+00h]
0x1800263f3  test    eax, eax
0x1800263f5  jnz     short loc_1800263FC
0x1800263f7  lea     edx, [rax+39h]
0x1800263fa  jmp     short loc_180026448
0x1800263fc  mov     eax, [rbp+Buffer]
0x1800263ff  mov     ecx, 2
0x180026404  and     eax, 0FFFFFFh
0x180026409  cmp     eax, 0BFBBEFh
0x18002640e  jnz     short loc_180026415
0x180026410  mov     r15d, r12d
0x180026413  jmp     short loc_18002642A
0x180026415  cmp     word ptr [rbp+Buffer], 0FEFFh
0x18002641b  jnz     short loc_180026424
0x18002641d  mov     ebx, ecx
0x18002641f  mov     r15d, ecx
0x180026422  jmp     short loc_18002642A
0x180026424  mov     ebx, r13d
0x180026427  mov     r15d, r13d
0x18002642a  mov     edx, ebx; liDistanceToMove
0x18002642c  xor     r9d, r9d; dwMoveMethod
0x18002642f  xor     r8d, r8d; lpNewFilePointer
0x180026432  mov     rcx, rsi; hFile
0x180026435  call    cs:__imp_SetFilePointerEx
0x18002643c  nop     dword ptr [rax+rax+00h]
0x180026441  test    eax, eax
0x180026443  jnz     short loc_18002645F
0x180026445  lea     edx, [rax+44h]; void *
0x180026448  mov     rcx, [rbp+38h]; this
0x18002644c  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026453  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026458  mov     ebx, eax
0x18002645a  jmp     loc_1800266F9
0x18002645f  lea     rdx, [rbp+FileSize]; lpFileSize
0x180026463  mov     qword ptr [rbp+FileSize], r13
0x180026467  mov     rcx, rsi; hFile
0x18002646a  call    cs:__imp_GetFileSizeEx
0x180026471  nop     dword ptr [rax+rax+00h]
0x180026476  test    eax, eax
0x180026478  jnz     short loc_18002647F
0x18002647a  lea     edx, [rax+47h]
0x18002647d  jmp     short loc_180026448
0x18002647f  mov     rdi, qword ptr [rbp+FileSize]
0x180026483  mov     eax, 0FFFFFFFFh
0x180026488  cmp     rdi, rax
0x18002648b  jl      short loc_1800264AF
0x18002648d  mov     ebx, 80070216h
0x180026492  mov     edx, 48h ; 'H'; void *
0x180026497  mov     r9d, ebx; char *
0x18002649a  mov     rcx, [rbp+38h]; this
0x18002649e  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800264a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800264aa  jmp     loc_1800266F9
0x1800264af  sub     edi, ebx
0x1800264b1  jnz     short loc_180026510
0x1800264b3  mov     rdi, [r14]
0x1800264b6  test    rdi, rdi
0x1800264b9  jz      short loc_1800264E6
0x1800264bb  call    cs:__imp_GetLastError
0x1800264c2  nop     dword ptr [rax+rax+00h]
0x1800264c7  mov     rcx, rdi; string
0x1800264ca  mov     ebx, eax
0x1800264cc  call    cs:__imp_WindowsDeleteString
0x1800264d3  nop     dword ptr [rax+rax+00h]
0x1800264d8  mov     ecx, ebx; dwErrCode
0x1800264da  call    cs:__imp_SetLastError
0x1800264e1  nop     dword ptr [rax+rax+00h]
0x1800264e6  mov     r8, r14; string
0x1800264e9  mov     [r14], r13
0x1800264ec  xor     edx, edx; length
0x1800264ee  xor     ecx, ecx; sourceString
0x1800264f0  call    cs:__imp_WindowsCreateString
0x1800264f7  nop     dword ptr [rax+rax+00h]
0x1800264fc  mov     ebx, eax
0x1800264fe  test    eax, eax
0x180026500  jns     loc_1800266F6
0x180026506  mov     r9d, eax
0x180026509  mov     edx, 4Dh ; 'M'
0x18002650e  jmp     short loc_18002649A
0x180026510  mov     [rbp+bufferHandle], r13
0x180026514  cmp     r15d, 2
0x180026518  jnz     short loc_18002658E
0x18002651a  test    r12b, dil
0x18002651d  jz      short loc_180026559
0x18002651f  mov     ebx, 8007000Dh
0x180026524  lea     edx, [r15+5Ch]; void *
0x180026528  mov     r9d, ebx; char *
0x18002652b  mov     rcx, [rbp+38h]; this
0x18002652f  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026536  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002653b  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x18002653f  test    rcx, rcx
0x180026542  jz      loc_1800266F9
0x180026548  call    cs:__imp_WindowsDeleteStringBuffer
0x18002654f  nop     dword ptr [rax+rax+00h]
0x180026554  jmp     loc_1800266F9
0x180026559  mov     ecx, edi
0x18002655b  mov     [rbp+charBuffer], r13
0x18002655f  shr     ecx, 1; length
0x180026561  lea     r8, [rbp+bufferHandle]; bufferHandle
0x180026565  lea     rdx, [rbp+charBuffer]; charBuffer
0x180026569  call    cs:__imp_WindowsPreallocateStringBuffer
0x180026570  nop     dword ptr [rax+rax+00h]
0x180026575  mov     ebx, eax
0x180026577  test    eax, eax
0x180026579  jns     short loc_180026585
0x18002657b  mov     r9d, eax
0x18002657e  mov     edx, 63h ; 'c'
0x180026583  jmp     short loc_18002652B
0x180026585  mov     rdx, [rbp+charBuffer]
0x180026589  mov     rbx, r13
0x18002658c  jmp     short loc_1800265B7
0x18002658e  mov     ecx, edi; cb
0x180026590  call    cs:__imp_CoTaskMemAlloc
0x180026597  nop     dword ptr [rax+rax+00h]
0x18002659c  mov     rbx, rax
0x18002659f  test    rax, rax
0x1800265a2  jnz     short loc_1800265B1
0x1800265a4  mov     ebx, 8007000Eh
0x1800265a9  lea     edx, [rax+6Bh]
0x1800265ac  jmp     loc_180026528
0x1800265b1  mov     r12b, r13b
0x1800265b4  mov     rdx, rax; lpBuffer
0x1800265b7  lea     r9, [rbp+arg_18]; lpNumberOfBytesRead
0x1800265bb  mov     [rbp+arg_18], r13d
0x1800265bf  mov     r8d, edi; nNumberOfBytesToRead
0x1800265c2  mov     qword ptr [rsp+60h+lpOverlapped], r13; int
0x1800265c7  mov     rcx, rsi; hFile
0x1800265ca  call    cs:__imp_ReadFile
0x1800265d1  nop     dword ptr [rax+rax+00h]
0x1800265d6  test    eax, eax
0x1800265d8  jnz     short loc_18002661F
0x1800265da  mov     rcx, [rbp+38h]; this
0x1800265de  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800265e5  lea     edx, [rax+76h]; void *
0x1800265e8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800265ed  mov     edi, eax
0x1800265ef  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x1800265f3  test    rcx, rcx
0x1800265f6  jz      short loc_180026604
0x1800265f8  call    cs:__imp_WindowsDeleteStringBuffer
0x1800265ff  nop     dword ptr [rax+rax+00h]
0x180026604  test    rbx, rbx
0x180026607  jz      short loc_180026618
0x180026609  mov     rcx, rbx; pv
0x18002660c  call    cs:__imp_CoTaskMemFree
0x180026613  nop     dword ptr [rax+rax+00h]
0x180026618  mov     ebx, edi
0x18002661a  jmp     loc_1800266F9
0x18002661f  cmp     edi, [rbp+arg_18]
0x180026622  jz      short loc_180026643
0x180026624  mov     edi, 8000FFFFh
0x180026629  mov     edx, 7Ah ; 'z'; void *
0x18002662e  mov     rcx, [rbp+38h]; this
0x180026632  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026639  mov     r9d, edi; char *
0x18002663c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026641  jmp     short loc_1800265EF
0x180026643  test    r12b, r12b
0x180026646  jz      short loc_1800266A4
0x180026648  mov     r15, [r14]
0x18002664b  test    r15, r15
0x18002664e  jz      short loc_18002667B
0x180026650  call    cs:__imp_GetLastError
0x180026657  nop     dword ptr [rax+rax+00h]
0x18002665c  mov     rcx, r15; string
0x18002665f  mov     edi, eax
0x180026661  call    cs:__imp_WindowsDeleteString
0x180026668  nop     dword ptr [rax+rax+00h]
0x18002666d  mov     ecx, edi; dwErrCode
0x18002666f  call    cs:__imp_SetLastError
0x180026676  nop     dword ptr [rax+rax+00h]
0x18002667b  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x18002667f  mov     rdx, r14; string
0x180026682  mov     [r14], r13
0x180026685  call    cs:__imp_WindowsPromoteStringBuffer
0x18002668c  nop     dword ptr [rax+rax+00h]
0x180026691  mov     edi, eax
0x180026693  test    eax, eax
0x180026695  js      short loc_18002669D
0x180026697  mov     [rbp+bufferHandle], r13
0x18002669b  jmp     short loc_1800266E2
0x18002669d  mov     edx, 7Eh ; '~'
0x1800266a2  jmp     short loc_18002662E
0x1800266a4  neg     r15d
0x1800266a7  mov     r9, r14; string
0x1800266aa  mov     r8d, edi; cbMultiByte
0x1800266ad  mov     rdx, rbx; lpMultiByteStr
0x1800266b0  sbb     ecx, ecx
0x1800266b2  and     ecx, 0FDE9h; CodePage
0x1800266b8  call    ?ConvertRawBytesToString@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJIPEBDHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(uint,char const *,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x1800266bd  mov     edi, eax
0x1800266bf  test    eax, eax
0x1800266c1  jns     short loc_1800266CD
0x1800266c3  mov     edx, 83h
0x1800266c8  jmp     loc_18002662E
0x1800266cd  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x1800266d1  test    rcx, rcx
0x1800266d4  jz      short loc_1800266E2
0x1800266d6  call    cs:__imp_WindowsDeleteStringBuffer
0x1800266dd  nop     dword ptr [rax+rax+00h]
0x1800266e2  test    rbx, rbx
0x1800266e5  jz      short loc_1800266F6
0x1800266e7  mov     rcx, rbx; pv
0x1800266ea  call    cs:__imp_CoTaskMemFree
0x1800266f1  nop     dword ptr [rax+rax+00h]
0x1800266f6  mov     ebx, r13d
0x1800266f9  mov     rcx, rsi; hObject
0x1800266fc  call    cs:__imp_CloseHandle
0x180026703  nop     dword ptr [rax+rax+00h]
0x180026708  mov     eax, ebx
0x18002670a  mov     rbx, [rsp+60h+arg_0]
0x180026712  add     rsp, 60h
0x180026716  pop     r15
0x180026718  pop     r14
0x18002671a  pop     r13
0x18002671c  pop     r12
0x18002671e  pop     rdi
0x18002671f  pop     rsi
0x180026720  pop     rbp
0x180026721  retn
```
