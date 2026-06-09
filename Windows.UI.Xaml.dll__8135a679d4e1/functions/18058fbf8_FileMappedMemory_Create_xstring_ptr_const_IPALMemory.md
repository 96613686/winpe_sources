# FileMappedMemory::Create(xstring_ptr const &,IPALMemory * *)

- ea: `0x18058fbf8`
- end: `0x18058fe50`
- name: `?Create@FileMappedMemory@@SAJAEBVxstring_ptr@@PEAPEAUIPALMemory@@@Z`
- size: `600`
- prototype: `HRESULT __fastcall(const xstring_ptr *strFilePath, IPALMemory **ppMemory)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180286610`

## callees

- `0x180004bc0`
- `0x1800fe130`
- `0x180131190`
- `0x1801800b8`
- `0x18058fbf8`
- `0x180622c0c`
- `0x1806877a8`
- `0x180687890`
- `0x180687a78`
- `0x180688828`
- `0x1806c4ccc`
- `0x18080d0d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18058fd7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18058fd7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18058fcf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18058fcff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18058fcf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18058fcff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18058fc4e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18058fc4e`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18058fc79`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18058fc79`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18058fcb3`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18058fcb3`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18058fcdb`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18058fcdb`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18058fdfd`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18058fdfd`

## pseudocode

```c
__int64 __fastcall FileMappedMemory::Create(const xstring_ptr *strFilePath, IPALMemory **ppMemory)
{
  const WCHAR *Buffer; // rax
  IPALMemory_vtbl *FileW; // rax
  HRESULT v6; // ecx
  IPALMemory_vtbl *v7; // rdi
  signed int LastError; // ebx
  HRESULT v9; // ecx
  IPALMemory_vtbl *FileMappingW; // rax
  HRESULT v11; // ecx
  IPALMemory_vtbl *v12; // rsi
  int v13; // r15d
  HRESULT v14; // ecx
  IPALMemory_vtbl *v15; // r12
  IPALMemory *FailFast; // rax
  bool v18; // sf
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+40h] [rbp-10h] BYREF
  xstring_ptr c_strXamlExtension; // [rsp+48h] [rbp-8h] BYREF
  unsigned int cStowedExceptions; // [rsp+98h] [rbp+48h] BYREF
  xstring_ptr c_strXbfExtension; // [rsp+A0h] [rbp+50h] BYREF
  unsigned __int64 fileSize; // [rsp+A8h] [rbp+58h] BYREF

  fileSize = 0;
  if ( !ppMemory )
  {
    LastError = -2147467261;
    OnNewFailure_1172_((HRESULT)strFilePath);
    return (unsigned int)LastError;
  }
  Buffer = xstring_ptr_view::GetBuffer(&strFilePath->xstring_ptr_view);
  FileW = (IPALMemory_vtbl *)CreateFileW(Buffer, 0x80000000, 5u, 0, 3u, 0x80u, 0);
  v7 = FileW;
  if ( !FileW )
  {
    LastError = -2147467259;
    OnFailure_977_(v6);
    return (unsigned int)LastError;
  }
  if ( FileW != (IPALMemory_vtbl *)-1LL )
  {
    LastError = 0;
    goto LABEL_5;
  }
  LastError = GetLastError();
  if ( LastError == 5 )
  {
    c_strXbfExtension.m_encodedStorage.Storage = &sc_strXbfExtensionStorage;
    c_strXamlExtension.m_encodedStorage.Storage = &sc_strXamlExtensionStorage;
    if ( xstring_ptr_view::EndsWith(&strFilePath->xstring_ptr_view, &c_strXbfExtension, xstrCompareCaseInsensitive)
      || xstring_ptr_view::EndsWith(&strFilePath->xstring_ptr_view, &c_strXbfExtension, xstrCompareCaseInsensitive) )
    {
      OnFailure_2990_(-2147024891);
      ppStowedExceptions = 0;
      cStowedExceptions = 0;
      TraceForFailFast(-2147024891);
      GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
      RoFailFastWithErrorContextInternal2(-2147024891, cStowedExceptions, ppStowedExceptions);
    }
    xstring_ptr::~xstring_ptr(&c_strXamlExtension);
    xstring_ptr::~xstring_ptr(&c_strXbfExtension);
    goto LABEL_25;
  }
  v18 = LastError < 0;
  if ( LastError > 0 )
  {
LABEL_25:
    LastError = (unsigned __int16)LastError | 0x80070000;
    v18 = LastError < 0;
  }
  if ( v18 )
  {
    OnFailure_2990_(LastError);
    goto LABEL_10;
  }
LABEL_5:
  if ( !GetFileSizeEx(v7, (PLARGE_INTEGER)&fileSize) )
  {
    LastError = -2147467259;
    OnFailure_977_(v9);
    goto LABEL_10;
  }
  if ( fileSize > 0xFFFFFFFF )
  {
    LastError = -2147024882;
    OnFailure_2976_(v9);
    goto LABEL_10;
  }
  FileMappingW = (IPALMemory_vtbl *)CreateFileMappingW(v7, 0, 2u, 0, 0, 0);
  v12 = FileMappingW;
  if ( !FileMappingW )
  {
    LastError = -2147024882;
    OnNewFailure_3143_(v11);
    goto LABEL_10;
  }
  v13 = fileSize;
  v15 = (IPALMemory_vtbl *)MapViewOfFile(FileMappingW, 4u, 0, 0, (unsigned int)fileSize);
  if ( !v15 )
  {
    LastError = -2147024882;
    OnNewFailure_3143_(v14);
    CloseHandle(v12);
LABEL_10:
    CloseHandle(v7);
    return (unsigned int)LastError;
  }
  FailFast = (IPALMemory *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
  if ( FailFast )
  {
    LODWORD(FailFast[1].__vftable) = 1;
    FailFast->__vftable = (IPALMemory_vtbl *)&FileMappedMemory::`vftable';
  }
  FailFast[2].__vftable = v7;
  FailFast[3].__vftable = v12;
  FailFast[4].__vftable = v15;
  HIDWORD(FailFast[1].__vftable) = v13;
  *ppMemory = FailFast;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18058fbf8  push    rbp
0x18058fbfa  push    rbx
0x18058fbfb  push    rsi
0x18058fbfc  push    rdi
0x18058fbfd  push    r12
0x18058fbff  push    r14
0x18058fc01  push    r15
0x18058fc03  mov     rbp, rsp
0x18058fc06  sub     rsp, 50h
0x18058fc0a  mov     [rbp+fileSize], 0
0x18058fc12  mov     r14, ppMemory
0x18058fc15  mov     rsi, strFilePath
0x18058fc18  test    ppMemory, ppMemory
0x18058fc1b  jz      loc_18058FD4B
0x18058fc21  call    ?GetBuffer@xstring_ptr_view@@QEBAPEBGXZ; xstring_ptr_view::GetBuffer(void)
0x18058fc26  xor     r9d, r9d; lpSecurityAttributes
0x18058fc29  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x18058fc32  mov     strFilePath, rax; lpFileName
0x18058fc35  mov     [rsp+50h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18058fc3d  mov     edx, 80000000h; dwDesiredAccess
0x18058fc42  mov     [rsp+50h+dwCreationDisposition], 3; dwCreationDisposition
0x18058fc4a  lea     r8d, [r9+5]; dwShareMode
0x18058fc4e  call    cs:__imp_CreateFileW
0x18058fc54  mov     rdi, rax
0x18058fc57  test    rax, rax
0x18058fc5a  jz      loc_18058FD70
0x18058fc60  mov     r15d, 1
0x18058fc66  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18058fc6a  jz      loc_18058FD7C
0x18058fc70  xor     ebx, ebx
0x18058fc72  lea     ppMemory, [rbp+fileSize]; lpFileSize
0x18058fc76  mov     strFilePath, rdi; hFile
0x18058fc79  call    cs:__imp_GetFileSizeEx
0x18058fc7f  test    eax, eax
0x18058fc81  jz      loc_18058FE32
0x18058fc87  mov     eax, 0FFFFFFFFh
0x18058fc8c  cmp     [rbp+fileSize], rax
0x18058fc90  ja      loc_18058FE41
0x18058fc96  xor     r9d, r9d; dwMaximumSizeHigh
0x18058fc99  mov     qword ptr [rsp+50h+dwFlagsAndAttributes], 0; lpName
0x18058fca2  xor     edx, edx; lpFileMappingAttributes
0x18058fca4  mov     [rsp+50h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18058fcac  mov     strFilePath, rdi; hFile
0x18058fcaf  lea     r8d, [r9+2]; flProtect
0x18058fcb3  call    cs:__imp_CreateFileMappingW
0x18058fcb9  mov     rsi, rax
0x18058fcbc  test    rax, rax
0x18058fcbf  jz      loc_18058FD57
0x18058fcc5  mov     r15d, dword ptr [rbp+fileSize]
0x18058fcc9  xor     r9d, r9d; dwFileOffsetLow
0x18058fccc  xor     r8d, r8d; dwFileOffsetHigh
0x18058fccf  mov     qword ptr [rsp+50h+dwCreationDisposition], r15; dwNumberOfBytesToMap
0x18058fcd4  mov     strFilePath, rax; hFileMappingObject
0x18058fcd7  lea     edx, [r9+4]; dwDesiredAccess
0x18058fcdb  call    cs:__imp_MapViewOfFile
0x18058fce1  mov     r12, rax
0x18058fce4  test    rax, rax
0x18058fce7  jnz     short loc_18058FD16
0x18058fce9  mov     ebx, 8007000Eh
0x18058fcee  call    OnNewFailure_3143_
0x18058fcf3  mov     strFilePath, rsi; hObject
0x18058fcf6  call    cs:__imp_CloseHandle
0x18058fcfc  mov     strFilePath, rdi; hObject
0x18058fcff  call    cs:__imp_CloseHandle
0x18058fd05  mov     eax, ebx
0x18058fd07  add     rsp, 50h
0x18058fd0b  pop     r15
0x18058fd0d  pop     r14
0x18058fd0f  pop     r12
0x18058fd11  pop     rdi
0x18058fd12  pop     rsi
0x18058fd13  pop     rbx
0x18058fd14  pop     rbp
0x18058fd15  retn
0x18058fd16  mov     ecx, 28h ; '('; cSize
0x18058fd1b  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x18058fd20  test    rax, rax
0x18058fd23  jz      short loc_18058FD36
0x18058fd25  lea     strFilePath, ??_7FileMappedMemory@@6B@; failedFrameHR
0x18058fd2c  mov     dword ptr [rax+8], 1
0x18058fd33  mov     [rax], strFilePath
0x18058fd36  mov     [rax+10h], rdi
0x18058fd3a  mov     [rax+18h], rsi
0x18058fd3e  mov     [rax+20h], r12
0x18058fd42  mov     [rax+0Ch], r15d
0x18058fd46  mov     [r14], rax
0x18058fd49  jmp     short $Cleanup_4397
0x18058fd4b  mov     ebx, 80004003h
0x18058fd50  call    OnNewFailure_1172_
0x18058fd55  jmp     short $Cleanup_4397
0x18058fd57  mov     ebx, 8007000Eh
0x18058fd5c  call    OnNewFailure_3143_
0x18058fd61  jmp     short loc_18058FCFC
0x18058fd63  test    ebx, ebx
0x18058fd65  jg      loc_18058FE15
0x18058fd6b  jmp     loc_18058FE20
0x18058fd70  mov     ebx, 80004005h
0x18058fd75  call    OnFailure_977_
0x18058fd7a  jmp     short $Cleanup_4397
0x18058fd7c  call    cs:__imp_GetLastError
0x18058fd82  mov     ebx, eax
0x18058fd84  cmp     eax, 5
0x18058fd87  jnz     short loc_18058FD63
0x18058fd89  lea     rax, sc_strXbfExtensionStorage
0x18058fd90  mov     r8d, r15d; eCompareBehavior
0x18058fd93  mov     qword ptr [rbp+c_strXbfExtension.m_encodedStorage.___u0], rax
0x18058fd97  lea     ppMemory, [rbp+c_strXbfExtension]; strStringToFind
0x18058fd9b  lea     rax, sc_strXamlExtensionStorage
0x18058fda2  mov     strFilePath, rsi; this
0x18058fda5  mov     qword ptr [rbp+c_strXamlExtension.m_encodedStorage.___u0], rax
0x18058fda9  call    ?EndsWith@xstring_ptr_view@@QEBAIAEBV1@W4xstrCompareBehavior@@@Z; xstring_ptr_view::EndsWith(xstring_ptr_view const &,xstrCompareBehavior)
0x18058fdae  test    eax, eax
0x18058fdb0  jnz     short loc_18058FDC5
0x18058fdb2  mov     r8d, r15d; eCompareBehavior
0x18058fdb5  lea     ppMemory, [rbp+c_strXbfExtension]; strStringToFind
0x18058fdb9  mov     strFilePath, rsi; this
0x18058fdbc  call    ?EndsWith@xstring_ptr_view@@QEBAIAEBV1@W4xstrCompareBehavior@@@Z; xstring_ptr_view::EndsWith(xstring_ptr_view const &,xstrCompareBehavior)
0x18058fdc1  test    eax, eax
0x18058fdc3  jz      short loc_18058FE03
0x18058fdc5  mov     esi, 80070005h
0x18058fdca  mov     ecx, esi; failedFrameHR
0x18058fdcc  call    OnFailure_2990_
0x18058fdd1  mov     ecx, esi; errorCode
0x18058fdd3  mov     [rbp+ppStowedExceptions], 0
0x18058fddb  mov     [rbp+cStowedExceptions], 0
0x18058fde2  call    TraceForFailFast
0x18058fde7  lea     ppMemory, [rbp+cStowedExceptions]; pcStowedExceptions
0x18058fdeb  lea     strFilePath, [rbp+ppStowedExceptions]; pppStowedExceptions
0x18058fdef  call    GetStowedExceptionsForFailFast
0x18058fdf4  mov     r8, [rbp+ppStowedExceptions]
0x18058fdf8  mov     ecx, esi
0x18058fdfa  mov     edx, [rbp+cStowedExceptions]
0x18058fdfd  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x18058fe03  lea     strFilePath, [rbp+c_strXamlExtension]; this
0x18058fe07  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x18058fe0c  lea     strFilePath, [rbp+c_strXbfExtension]; this
0x18058fe10  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x18058fe15  movzx   ebx, bx
0x18058fe18  or      ebx, 80070000h
0x18058fe1e  test    ebx, ebx
0x18058fe20  jns     loc_18058FC72
0x18058fe26  mov     ecx, ebx; failedFrameHR
0x18058fe28  call    OnFailure_2990_
0x18058fe2d  jmp     loc_18058FCFC
0x18058fe32  mov     ebx, 80004005h
0x18058fe37  call    OnFailure_977_
0x18058fe3c  jmp     loc_18058FCFC
0x18058fe41  mov     ebx, 8007000Eh
0x18058fe46  call    OnFailure_2976_
0x18058fe4b  jmp     loc_18058FCFC
```
