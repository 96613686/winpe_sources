# _GetAppDataSecurityDescriptor

- ea: `0x180010a00`
- end: `0x180010bd9`
- name: `_GetAppDataSecurityDescriptor`
- size: `473`
- prototype: `__int64 __fastcall(void **pSD, void *appContainerSid)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180007084`

## callees

- `0x18000737c`
- `0x180010a00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010aec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010aec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010bc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010bc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010bab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010bbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010bab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010bbb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010ad6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010ad6`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180010b54`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180010b54`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180010a2c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180010a2c`
- `USERENV!GetAppContainerFolderPath` at `0x180010a9d`
- `USERENV!GetAppContainerFolderPath` at `0x180010a9d`

## pseudocode

```c
__int64 __fastcall GetAppDataSecurityDescriptor(void **pSD, void *appContainerSid)
{
  void *v2; // rbp
  signed int LastError; // eax
  int AppContainerFolderPath; // ebx
  HANDLE FileW; // rax
  DWORD v7; // eax
  signed int SecurityInfo; // edi
  WPP_PROJECT_CONTROL_BLOCK *v9; // rcx
  wchar_t *appContainerStrSid; // [rsp+60h] [rbp+8h] BYREF
  wchar_t *appContainerRootFolderPath; // [rsp+70h] [rbp+18h] BYREF
  void *pSidOwner; // [rsp+78h] [rbp+20h] BYREF

  v2 = 0;
  *pSD = 0;
  pSidOwner = 0;
  appContainerStrSid = 0;
  appContainerRootFolderPath = 0;
  if ( !ConvertSidToStringSidW(appContainerSid, &appContainerStrSid) )
  {
    LastError = GetLastError();
    AppContainerFolderPath = LastError;
    if ( LastError > 0 )
      AppContainerFolderPath = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control[1].Control.Logger,
        0x35u,
        WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
        AppContainerFolderPath);
    }
    goto $Exit_10;
  }
  AppContainerFolderPath = GetAppContainerFolderPath(appContainerStrSid, &appContainerRootFolderPath);
  if ( AppContainerFolderPath < 0 )
    goto $Exit_10;
  FileW = CreateFileW(appContainerRootFolderPath, 0x80000000, 1u, 0, 3u, 0x2000000u, 0);
  v2 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v7 = GetLastError();
    SecurityInfo = v7;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 5u )
    {
      goto LABEL_16;
    }
    WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x36u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v7);
  }
  else
  {
    SecurityInfo = GetSecurityInfo(FileW, SE_FILE_OBJECT, 5u, &pSidOwner, 0, 0, 0, pSD);
  }
  v9 = WPP_GLOBAL_Control;
LABEL_16:
  if ( SecurityInfo > 0 )
    AppContainerFolderPath = (unsigned __int16)SecurityInfo | 0x80070000;
  else
    AppContainerFolderPath = SecurityInfo;
  if ( AppContainerFolderPath < 0
    && v9 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (v9[1].ReserveSpace[28] & 0x10) != 0
    && v9[1].Control.Level >= 5u )
  {
    WPP_SF_d(v9[1].Control.Logger, 0x37u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, SecurityInfo);
  }
$Exit_10:
  if ( appContainerStrSid )
    LocalFree(appContainerStrSid);
  if ( appContainerRootFolderPath )
    LocalFree(appContainerRootFolderPath);
  CloseHandle(v2);
  return (unsigned int)AppContainerFolderPath;
}

```

## disassembly

```asm
0x180010a00  mov     r11, rsp
0x180010a03  mov     [r11+10h], rbx
0x180010a07  push    rbp
0x180010a08  push    rsi
0x180010a09  push    rdi
0x180010a0a  sub     rsp, 40h
0x180010a0e  xor     ebp, ebp
0x180010a10  mov     rax, appContainerSid
0x180010a13  mov     [pSD], rbp
0x180010a16  lea     appContainerSid, [r11+8]; StringSid
0x180010a1a  mov     rdi, pSD
0x180010a1d  mov     [r11+20h], rbp
0x180010a21  mov     pSD, rax; Sid
0x180010a24  mov     [r11+8], rbp
0x180010a28  mov     [r11+18h], rbp
0x180010a2c  call    cs:__imp_ConvertSidToStringSidW
0x180010a32  test    eax, eax
0x180010a34  jnz     short loc_180010A93
0x180010a36  call    cs:__imp_GetLastError
0x180010a3c  mov     ebx, eax
0x180010a3e  test    eax, eax
0x180010a40  jle     short loc_180010A4B
0x180010a42  movzx   ebx, ax
0x180010a45  or      ebx, 80070000h
0x180010a4b  mov     pSD, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180010a52  lea     rsi, WPP_GLOBAL_Control
0x180010a59  cmp     pSD, rsi
0x180010a5c  jz      $Exit_10
0x180010a62  test    byte ptr [pSD+44h], 10h
0x180010a66  jz      $Exit_10
0x180010a6c  cmp     byte ptr [pSD+41h], 2
0x180010a70  jb      $Exit_10
0x180010a76  mov     pSD, [pSD+38h]; Logger
0x180010a7a  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180010a81  mov     edx, 35h ; '5'; id
0x180010a86  mov     r9d, ebx; _a1
0x180010a89  call    WPP_SF_d
0x180010a8e  jmp     $Exit_10
0x180010a93  mov     pSD, [rsp+58h+appContainerStrSid]
0x180010a98  lea     appContainerSid, [rsp+58h+appContainerRootFolderPath]
0x180010a9d  call    cs:__imp_GetAppContainerFolderPath
0x180010aa3  mov     ebx, eax
0x180010aa5  test    eax, eax
0x180010aa7  js      $Exit_10
0x180010aad  mov     pSD, [rsp+58h+appContainerRootFolderPath]; lpFileName
0x180010ab2  xor     r9d, r9d; lpSecurityAttributes
0x180010ab5  mov     [rsp+58h+hTemplateFile], rbp; hTemplateFile
0x180010aba  mov     edx, 80000000h; dwDesiredAccess
0x180010abf  mov     [rsp+58h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180010ac7  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x180010acf  lea     ebx, [r9+1]
0x180010ad3  mov     r8d, ebx; dwShareMode
0x180010ad6  call    cs:__imp_CreateFileW
0x180010adc  lea     rsi, WPP_GLOBAL_Control
0x180010ae3  mov     rbp, rax
0x180010ae6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010aea  jnz     short loc_180010B24
0x180010aec  call    cs:__imp_GetLastError
0x180010af2  mov     edi, eax
0x180010af4  mov     pSD, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180010afb  cmp     pSD, rsi
0x180010afe  jz      short loc_180010B63
0x180010b00  test    byte ptr [pSD+44h], 10h
0x180010b04  jz      short loc_180010B63
0x180010b06  cmp     byte ptr [pSD+41h], 5
0x180010b0a  jb      short loc_180010B63
0x180010b0c  mov     pSD, [pSD+38h]; Logger
0x180010b10  lea     edx, [rbx+35h]; id
0x180010b13  mov     r9d, eax; _a1
0x180010b16  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180010b1d  call    WPP_SF_d
0x180010b22  jmp     short loc_180010B5C
0x180010b24  mov     [rsp+58h+ppSecurityDescriptor], rdi; ppSecurityDescriptor
0x180010b29  lea     r9, [rsp+58h+pSidOwner]; ppsidOwner
0x180010b2e  mov     [rsp+58h+hTemplateFile], 0; ppSacl
0x180010b37  mov     r8d, 5; SecurityInfo
0x180010b3d  mov     qword ptr [rsp+58h+dwFlagsAndAttributes], 0; ppDacl
0x180010b46  mov     edx, ebx; ObjectType
0x180010b48  mov     pSD, rax; handle
0x180010b4b  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; ppsidGroup
0x180010b54  call    cs:__imp_GetSecurityInfo
0x180010b5a  mov     edi, eax
0x180010b5c  mov     pSD, cs:WPP_GLOBAL_Control
0x180010b63  test    edi, edi
0x180010b65  jg      short loc_180010B6B
0x180010b67  mov     ebx, edi
0x180010b69  jmp     short loc_180010B74
0x180010b6b  movzx   ebx, di
0x180010b6e  or      ebx, 80070000h
0x180010b74  test    ebx, ebx
0x180010b76  jns     short $Exit_10
0x180010b78  cmp     pSD, rsi; __annotation("TMF:",
0x180010b7b  jz      short $Exit_10
0x180010b7d  test    byte ptr [pSD+44h], 10h
0x180010b81  jz      short $Exit_10
0x180010b83  cmp     byte ptr [pSD+41h], 5
0x180010b87  jb      short $Exit_10
0x180010b89  mov     pSD, [pSD+38h]; Logger
0x180010b8d  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180010b94  mov     edx, 37h ; '7'; id
0x180010b99  mov     r9d, edi; _a1
0x180010b9c  call    WPP_SF_d
0x180010ba1  mov     pSD, [rsp+58h+appContainerStrSid]; hMem
0x180010ba6  test    pSD, pSD
0x180010ba9  jz      short loc_180010BB1
0x180010bab  call    cs:__imp_LocalFree
0x180010bb1  mov     pSD, [rsp+58h+appContainerRootFolderPath]; hMem
0x180010bb6  test    pSD, pSD
0x180010bb9  jz      short loc_180010BC1
0x180010bbb  call    cs:__imp_LocalFree
0x180010bc1  mov     pSD, rbp; hObject
0x180010bc4  call    cs:__imp_CloseHandle
0x180010bca  mov     eax, ebx
0x180010bcc  mov     rbx, [rsp+58h+arg_8]
0x180010bd1  add     rsp, 40h
0x180010bd5  pop     rdi
0x180010bd6  pop     rsi
0x180010bd7  pop     rbp
0x180010bd8  retn
```
