# _copyFile

- ea: `0x1800a559c`
- end: `0x1800a591c`
- name: `_copyFile`
- size: `896`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800a5438`

## callees

- `0x1800085d0`
- `0x18000f138`
- `0x180012300`
- `0x180019f24`
- `0x180074758`
- `0x1800a559c`
- `0x1800c8520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a575a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a57df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a58ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a575a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a57df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a58ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5807`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a588a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5807`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a588a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a587d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a587d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a585f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a585f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a5737`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a57b8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a5737`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a57b8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a57f8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a57f8`
- `RPCRT4!RpcImpersonateClient` at `0x1800a56cb`
- `RPCRT4!RpcImpersonateClient` at `0x1800a56cb`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800a5767`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800a578c`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800a5767`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800a578c`
- `WwanPrfl!WwanProfileGetRootPath` at `0x1800a561a`
- `WwanPrfl!WwanProfileGetRootPath` at `0x1800a561a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800a58b1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800a58b1`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x1800a5906`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x1800a5906`

## string_xrefs

- `0x1800a5626`: `WwanProfileGetRootPath failed, errCode (0x%8x)`
- `0x1800a55d5`: `_copyFile`
- `0x1800a56da`: `RpcImpersonateClient failed, errCode (0x%8x)`
- `0x1800a5749`: `CreateFile failed, errCode (0x%8x)`
- `0x1800a57cb`: `CreateFile failed, errCode (0x%8x)`
- `0x1800a58be`: `File move failed, errCode (0x%8x)`
- `0x1800a5897`: `File copy failed, errCode (0x%8x)`
- `0x1800a58d9`: `File move failed even when the output file didn't exist, errCode (0x%8x)`

## pseudocode

```c
__int64 __fastcall copyFile(const WCHAR *a1, __int64 a2, void *a3)
{
  __int64 FileW; // rdi
  DWORD RootPath; // eax
  DWORD LastError; // ebx
  const unsigned __int16 *v9; // r8
  int v10; // eax
  int v11; // eax
  RPC_STATUS v12; // esi
  RPC_STATUS v13; // esi
  HANDLE v14; // rsi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE Buffer[1024]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR NewFileName[1024]; // [rsp+450h] [rbp+350h] BYREF
  WCHAR FileName[1024]; // [rsp+C50h] [rbp+B50h] BYREF

  WwanLog::Enter("_copyFile");
  NumberOfBytesWritten = 0;
  NewFileName[0] = 0;
  Buffer[0] = 0;
  FileW = -1;
  FileName[0] = 0;
  RootPath = WwanProfileGetRootPath(NewFileName, 1024, 0);
  LastError = RootPath;
  if ( !RootPath )
  {
    v10 = StringCchPrintfW(FileName, 0x104u, L"%s\\tmp.%s", NewFileName, L"bmp");
    LastError = v10;
    if ( v10 < 0 )
    {
      if ( (v10 & 0x1FFF0000) == 0x70000 )
        LastError = (unsigned __int16)v10;
      if ( LastError )
      {
        WwanLog::Error("_copyFile", 0, L"StringCchPrintf failed for tmpFile, errCode (0x%8x)", LastError);
        goto LABEL_26;
      }
    }
    v11 = StringCchPrintfW(NewFileName, 0x104u, L"%s\\%s.%s", NewFileName, a2, L"bmp");
    LastError = v11;
    if ( v11 < 0 )
    {
      if ( (v11 & 0x1FFF0000) == 0x70000 )
        LastError = (unsigned __int16)v11;
      if ( LastError )
      {
        WwanLog::Error("_copyFile", 0, L"StringCchPrintf failed for outFile, errCode (0x%8x)", LastError);
        goto LABEL_26;
      }
    }
    else
    {
      LastError = 0;
    }
    v12 = RpcImpersonateClient(a3);
    if ( v12 )
    {
      WwanLog::Error("_copyFile", 0, L"RpcImpersonateClient failed, errCode (0x%8x)", 0);
      LastError = v12;
      goto LABEL_26;
    }
    FileW = (__int64)CreateFileW(a1, 0x80000000, 0, 0, 3u, 0x80u, 0);
    if ( FileW == -1 )
    {
      WwanLog::Error("_copyFile", 0, L"CreateFile failed, errCode (0x%8x)", 0);
      LastError = GetLastError();
    }
    else
    {
      v13 = RpcRevertToSelfEx(a3);
      if ( !v13 )
      {
        v14 = CreateFileW(FileName, 0x40000000u, 0, 0, 2u, 2u, 0);
        if ( v14 == (HANDLE)-1LL )
        {
          WwanLog::Error("_copyFile", 0, L"CreateFile failed, errCode (0x%8x)", 0);
        }
        else
        {
          while ( ReadFile((HANDLE)FileW, Buffer, 0x400u, &NumberOfBytesWritten, 0) && NumberOfBytesWritten )
            WriteFile(v14, Buffer, NumberOfBytesWritten, &NumberOfBytesWritten, 0);
          CloseHandle(v14);
          if ( NumberOfBytesWritten )
          {
            WwanLog::Error("_copyFile", 0, L"File copy failed, errCode (0x%8x)", 0);
          }
          else
          {
            if ( MoveFileW(FileName, NewFileName) )
            {
              WwanLog::Error("_copyFile", 0, L"File move failed, errCode (0x%8x)", 0);
              goto LABEL_26;
            }
            RootPath = GetLastError();
            LastError = RootPath;
            if ( RootPath != 183 )
            {
              v9 = L"File move failed even when the output file didn't exist, errCode (0x%8x)";
              goto LABEL_3;
            }
            if ( ReplaceFileW(NewFileName, FileName, 0, 1u, 0, 0) )
            {
              LastError = 0;
              goto LABEL_26;
            }
          }
        }
        LastError = GetLastError();
        goto LABEL_26;
      }
      WwanLog::Error("_copyFile", 0, L"RpcRevertToSelfEx failed, errCode (0x%8x)", 0);
      LastError = v13;
    }
    RpcRevertToSelfEx(a3);
    goto LABEL_26;
  }
  v9 = L"WwanProfileGetRootPath failed, errCode (0x%8x)";
LABEL_3:
  WwanLog::Error("_copyFile", 0, v9, RootPath);
LABEL_26:
  if ( FileName[0] )
    DeleteFileW(FileName);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  WwanLog::ExitWithStatus("_copyFile", LastError);
  return LastError;
}

```

## disassembly

```asm
0x1800a559c  mov     [rsp-8+arg_18], rbx
0x1800a55a1  push    rbp
0x1800a55a2  push    rsi
0x1800a55a3  push    rdi
0x1800a55a4  push    r12
0x1800a55a6  push    r13
0x1800a55a8  push    r14
0x1800a55aa  push    r15
0x1800a55ac  lea     rbp, [rsp-1360h]
0x1800a55b4  mov     eax, 1460h
0x1800a55b9  call    _alloca_probe
0x1800a55be  sub     rsp, rax
0x1800a55c1  mov     rax, cs:__security_cookie
0x1800a55c8  xor     rax, rsp
0x1800a55cb  mov     [rbp+1390h+var_40], rax
0x1800a55d2  mov     r15, rcx
0x1800a55d5  lea     r13, aCopyfile; "_copyFile"
0x1800a55dc  mov     rcx, r13; char *
0x1800a55df  mov     r14, r8
0x1800a55e2  mov     rsi, rdx
0x1800a55e5  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800a55ea  xor     r12d, r12d
0x1800a55ed  lea     rcx, [rbp+1390h+NewFileName]
0x1800a55f4  xor     r8d, r8d
0x1800a55f7  mov     [rsp+1490h+NumberOfBytesWritten], r12d
0x1800a55fc  mov     edx, 400h
0x1800a5601  mov     [rbp+1390h+NewFileName], r12w
0x1800a5609  mov     [rsp+1490h+Buffer], r12b
0x1800a560e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a5612  mov     [rbp+1390h+FileName], r12w
0x1800a561a  call    cs:__imp_WwanProfileGetRootPath
0x1800a5620  mov     ebx, eax
0x1800a5622  test    eax, eax
0x1800a5624  jz      short loc_1800A563F
0x1800a5626  lea     r8, aWwanprofileget; "WwanProfileGetRootPath failed, errCode "...
0x1800a562d  mov     r9d, eax
0x1800a5630  xor     edx, edx; struct _GUID *
0x1800a5632  mov     rcx, r13; char *
0x1800a5635  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a563a  jmp     loc_1800A57E7
0x1800a563f  lea     rax, aBmp; "bmp"
0x1800a5646  mov     edx, 104h; unsigned __int64
0x1800a564b  lea     r9, [rbp+1390h+NewFileName]
0x1800a5652  mov     qword ptr [rsp+1490h+dwCreationDisposition], rax
0x1800a5657  lea     r8, aSTmpS; "%s\\tmp.%s"
0x1800a565e  lea     rcx, [rbp+1390h+FileName]; unsigned __int16 *
0x1800a5665  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a566a  mov     ebx, eax
0x1800a566c  test    eax, eax
0x1800a566e  jns     short loc_1800A568F
0x1800a5670  and     eax, 1FFF0000h
0x1800a5675  cmp     eax, 70000h
0x1800a567a  jnz     short loc_1800A567F
0x1800a567c  movzx   ebx, bx
0x1800a567f  test    ebx, ebx
0x1800a5681  jz      short loc_1800A568F
0x1800a5683  mov     r9d, ebx
0x1800a5686  lea     r8, aStringcchprint_3; "StringCchPrintf failed for tmpFile, err"...
0x1800a568d  jmp     short loc_1800A5630
0x1800a568f  lea     rax, aBmp; "bmp"
0x1800a5696  mov     edx, 104h; unsigned __int64
0x1800a569b  mov     qword ptr [rsp+1490h+dwFlagsAndAttributes], rax
0x1800a56a0  lea     r9, [rbp+1390h+NewFileName]
0x1800a56a7  lea     r8, aSSS; "%s\\%s.%s"
0x1800a56ae  mov     qword ptr [rsp+1490h+dwCreationDisposition], rsi
0x1800a56b3  lea     rcx, [rbp+1390h+NewFileName]; unsigned __int16 *
0x1800a56ba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a56bf  mov     ebx, eax
0x1800a56c1  test    eax, eax
0x1800a56c3  js      short loc_1800A56F2
0x1800a56c5  mov     ebx, r12d
0x1800a56c8  mov     rcx, r14; BindingHandle
0x1800a56cb  call    cs:__imp_RpcImpersonateClient
0x1800a56d1  mov     esi, eax
0x1800a56d3  test    eax, eax
0x1800a56d5  jz      short loc_1800A5714
0x1800a56d7  xor     r9d, r9d
0x1800a56da  lea     r8, aRpcimpersonate_0; "RpcImpersonateClient failed, errCode (0"...
0x1800a56e1  xor     edx, edx; struct _GUID *
0x1800a56e3  mov     rcx, r13; char *
0x1800a56e6  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a56eb  mov     ebx, esi
0x1800a56ed  jmp     loc_1800A57E7
0x1800a56f2  and     eax, 1FFF0000h
0x1800a56f7  cmp     eax, 70000h
0x1800a56fc  jnz     short loc_1800A5701
0x1800a56fe  movzx   ebx, bx
0x1800a5701  test    ebx, ebx
0x1800a5703  jz      short loc_1800A56C8
0x1800a5705  mov     r9d, ebx
0x1800a5708  lea     r8, aStringcchprint_2; "StringCchPrintf failed for outFile, err"...
0x1800a570f  jmp     loc_1800A5630
0x1800a5714  mov     [rsp+1490h+hTemplateFile], r12; hTemplateFile
0x1800a5719  xor     r9d, r9d; lpSecurityAttributes
0x1800a571c  mov     [rsp+1490h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a5724  xor     r8d, r8d; dwShareMode
0x1800a5727  mov     edx, 80000000h; dwDesiredAccess
0x1800a572c  mov     [rsp+1490h+dwCreationDisposition], 3; dwCreationDisposition
0x1800a5734  mov     rcx, r15; lpFileName
0x1800a5737  call    cs:__imp_CreateFileW
0x1800a573d  mov     rdi, rax
0x1800a5740  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a5744  jnz     short loc_1800A5764
0x1800a5746  xor     r9d, r9d
0x1800a5749  lea     r8, aCreatefileFail; "CreateFile failed, errCode (0x%8x)"
0x1800a5750  xor     edx, edx; struct _GUID *
0x1800a5752  mov     rcx, r13; char *
0x1800a5755  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a575a  call    cs:__imp_GetLastError
0x1800a5760  mov     ebx, eax
0x1800a5762  jmp     short loc_1800A5789
0x1800a5764  mov     rcx, r14; BindingHandle
0x1800a5767  call    cs:__imp_RpcRevertToSelfEx
0x1800a576d  mov     esi, eax
0x1800a576f  test    eax, eax
0x1800a5771  jz      short loc_1800A5794
0x1800a5773  xor     r9d, r9d
0x1800a5776  lea     r8, aRpcreverttosel; "RpcRevertToSelfEx failed, errCode (0x%8"...
0x1800a577d  xor     edx, edx; struct _GUID *
0x1800a577f  mov     rcx, r13; char *
0x1800a5782  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a5787  mov     ebx, esi
0x1800a5789  mov     rcx, r14; BindingHandle
0x1800a578c  call    cs:__imp_RpcRevertToSelfEx
0x1800a5792  jmp     short loc_1800A57E7
0x1800a5794  mov     eax, 2
0x1800a5799  mov     [rsp+1490h+hTemplateFile], r12; hTemplateFile
0x1800a579e  mov     [rsp+1490h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1800a57a2  lea     rcx, [rbp+1390h+FileName]; lpFileName
0x1800a57a9  xor     r9d, r9d; lpSecurityAttributes
0x1800a57ac  mov     [rsp+1490h+dwCreationDisposition], eax; dwCreationDisposition
0x1800a57b0  xor     r8d, r8d; dwShareMode
0x1800a57b3  mov     edx, 40000000h; dwDesiredAccess
0x1800a57b8  call    cs:__imp_CreateFileW
0x1800a57be  mov     rsi, rax
0x1800a57c1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a57c5  jnz     loc_1800A5865
0x1800a57cb  lea     r8, aCreatefileFail; "CreateFile failed, errCode (0x%8x)"
0x1800a57d2  xor     r9d, r9d
0x1800a57d5  xor     edx, edx; struct _GUID *
0x1800a57d7  mov     rcx, r13; char *
0x1800a57da  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a57df  call    cs:__imp_GetLastError
0x1800a57e5  mov     ebx, eax
0x1800a57e7  cmp     [rbp+1390h+FileName], r12w
0x1800a57ef  jz      short loc_1800A57FE
0x1800a57f1  lea     rcx, [rbp+1390h+FileName]; lpFileName
0x1800a57f8  call    cs:__imp_DeleteFileW
0x1800a57fe  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800a5802  jz      short loc_1800A580D
0x1800a5804  mov     rcx, rdi; hObject
0x1800a5807  call    cs:__imp_CloseHandle
0x1800a580d  mov     edx, ebx; unsigned int
0x1800a580f  mov     rcx, r13; char *
0x1800a5812  call    ?ExitWithStatus@WwanLog@@SAXPEBDK@Z; WwanLog::ExitWithStatus(char const *,ulong)
0x1800a5817  mov     eax, ebx
0x1800a5819  mov     rcx, [rbp+1390h+var_40]
0x1800a5820  xor     rcx, rsp; StackCookie
0x1800a5823  call    __security_check_cookie
0x1800a5828  mov     rbx, [rsp+1490h+arg_18]
0x1800a5830  add     rsp, 1460h
0x1800a5837  pop     r15
0x1800a5839  pop     r14
0x1800a583b  pop     r13
0x1800a583d  pop     r12
0x1800a583f  pop     rdi
0x1800a5840  pop     rsi
0x1800a5841  pop     rbp
0x1800a5842  retn
0x1800a5843  mov     r8d, [rsp+1490h+NumberOfBytesWritten]; nNumberOfBytesToWrite
0x1800a5848  test    r8d, r8d
0x1800a584b  jz      short loc_1800A5887
0x1800a584d  lea     r9, [rsp+1490h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a5852  mov     qword ptr [rsp+1490h+dwCreationDisposition], r12; lpOverlapped
0x1800a5857  lea     rdx, [rsp+1490h+Buffer]; lpBuffer
0x1800a585c  mov     rcx, rsi; hFile
0x1800a585f  call    cs:__imp_WriteFile
0x1800a5865  lea     r9, [rsp+1490h+NumberOfBytesWritten]; lpNumberOfBytesRead
0x1800a586a  mov     qword ptr [rsp+1490h+dwCreationDisposition], r12; lpOverlapped
0x1800a586f  mov     r8d, 400h; nNumberOfBytesToRead
0x1800a5875  lea     rdx, [rsp+1490h+Buffer]; lpBuffer
0x1800a587a  mov     rcx, rdi; hFile
0x1800a587d  call    cs:__imp_ReadFile
0x1800a5883  test    eax, eax
0x1800a5885  jnz     short loc_1800A5843
0x1800a5887  mov     rcx, rsi; hObject
0x1800a588a  call    cs:__imp_CloseHandle
0x1800a5890  cmp     [rsp+1490h+NumberOfBytesWritten], r12d
0x1800a5895  jz      short loc_1800A58A3
0x1800a5897  lea     r8, aFileCopyFailed; "File copy failed, errCode (0x%8x)"
0x1800a589e  jmp     loc_1800A57D2
0x1800a58a3  lea     rdx, [rbp+1390h+NewFileName]; lpNewFileName
0x1800a58aa  lea     rcx, [rbp+1390h+FileName]; lpExistingFileName
0x1800a58b1  call    cs:__imp_MoveFileW
0x1800a58b7  test    eax, eax
0x1800a58b9  jz      short loc_1800A58CA
0x1800a58bb  xor     r9d, r9d
0x1800a58be  lea     r8, aFileMoveFailed_0; "File move failed, errCode (0x%8x)"
0x1800a58c5  jmp     loc_1800A5630
0x1800a58ca  call    cs:__imp_GetLastError
0x1800a58d0  mov     ebx, eax
0x1800a58d2  cmp     eax, 0B7h
0x1800a58d7  jz      short loc_1800A58E5
0x1800a58d9  lea     r8, aFileMoveFailed; "File move failed even when the output f"...
0x1800a58e0  jmp     loc_1800A562D
0x1800a58e5  mov     qword ptr [rsp+1490h+dwFlagsAndAttributes], r12; lpReserved
0x1800a58ea  lea     rdx, [rbp+1390h+FileName]; lpReplacementFileName
0x1800a58f1  mov     r9d, 1; dwReplaceFlags
0x1800a58f7  mov     qword ptr [rsp+1490h+dwCreationDisposition], r12; lpExclude
0x1800a58fc  xor     r8d, r8d; lpBackupFileName
0x1800a58ff  lea     rcx, [rbp+1390h+NewFileName]; lpReplacedFileName
0x1800a5906  call    cs:__imp_ReplaceFileW
0x1800a590c  test    eax, eax
0x1800a590e  jz      loc_1800A57DF
0x1800a5914  mov     ebx, r12d
0x1800a5917  jmp     loc_1800A57E7
```
