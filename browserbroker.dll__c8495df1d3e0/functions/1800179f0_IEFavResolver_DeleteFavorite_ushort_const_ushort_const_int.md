# IEFavResolver::DeleteFavorite(ushort const *,ushort const *,int)

- ea: `0x1800179f0`
- end: `0x180017b9a`
- name: `?DeleteFavorite@IEFavResolver@@QEAAJPEBG0H@Z`
- size: `426`
- prototype: `__int64 __fastcall(WCHAR *this, const unsigned __int16 *, PCWSTR pszMore, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180019b8c`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x18000d17c`
- `0x180016700`
- `0x180016e70`
- `0x1800179f0`
- `0x180017ba0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017aa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017aa7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180017a99`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180017a99`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180017a91`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180017a91`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180017a3d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180017a3d`
- `ext-ms-win-shell-shell32-l1-2-1!SHFileOperationW` at `0x180017b48`
- `ext-ms-win-shell-shell32-l1-2-1!SHFileOperationW` at `0x180017b48`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IEFavResolver::DeleteFavorite(WCHAR *this, const unsigned __int16 *a2, PCWSTR pszMore, int a4)
{
  IEFavResolver *v7; // rcx
  int CompleteItemPathFromTitle; // ebx
  signed int LastError; // eax
  unsigned int v12; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v13; // [rsp+50h] [rbp-B0h] BYREF
  _SHFILEOPSTRUCTW FileOp; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR PathName[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v16[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  v13 = a2;
  CompleteItemPathFromTitle = PathCchCombine(pszPathOut, 0x104u, this + 24, pszMore);
  if ( CompleteItemPathFromTitle >= 0 )
  {
    CompleteItemPathFromTitle = IEFavResolver::GetCompleteItemPathFromTitle(v7, pszPathOut, a2, a4 != 0, PathName, v12);
    if ( CompleteItemPathFromTitle >= 0 )
    {
      IEFavResolver::AddToSyncList((HDPA *)this, PathName);
      if ( !(a4 ? RemoveDirectoryW(PathName) : DeleteFileW(PathName)) )
      {
        LastError = GetLastError();
        CompleteItemPathFromTitle = LastError;
        if ( LastError > 0 )
          CompleteItemPathFromTitle = (unsigned __int16)LastError | 0x80070000;
        if ( CompleteItemPathFromTitle == -2147024894 )
        {
LABEL_13:
          CompleteItemPathFromTitle = 0;
          goto LABEL_15;
        }
        if ( CompleteItemPathFromTitle == -2147024751 )
        {
          memset_0(v16, 0, 0x20Au);
          CompleteItemPathFromTitle = StringCchCopyW(v16, 0x104u, PathName);
          if ( CompleteItemPathFromTitle >= 0 )
          {
            FileOp.hwnd = 0;
            FileOp.pFrom = v16;
            *(_QWORD *)&FileOp.wFunc = 3;
            *(_OWORD *)&FileOp.hNameMappings = 0;
            FileOp.pTo = 0;
            *(_QWORD *)&FileOp.fFlags = 1556;
            if ( SHFileOperationW(&FileOp) )
            {
              CompleteItemPathFromTitle = -2147467259;
              goto LABEL_15;
            }
            goto LABEL_13;
          }
        }
      }
    }
  }
LABEL_15:
  BrowserTelemetry::HandleItemDeletedFromEdge<unsigned short const * &,unsigned short const * &,long &>((__int64)&v13);
  return (unsigned int)CompleteItemPathFromTitle;
}

```

## disassembly

```asm
0x1800179f0  push    rbp
0x1800179f2  push    rbx
0x1800179f3  push    rsi
0x1800179f4  push    rdi
0x1800179f5  push    r14
0x1800179f7  lea     rbp, [rsp-5D0h]
0x1800179ff  sub     rsp, 6D0h
0x180017a06  mov     rax, cs:__security_cookie
0x180017a0d  xor     rax, rsp
0x180017a10  mov     [rbp+5F0h+var_30], rax
0x180017a17  mov     edi, r9d
0x180017a1a  mov     [rsp+6F0h+var_6B0], r8
0x180017a1f  mov     r9, r8; pszMore
0x180017a22  mov     [rsp+6F0h+var_6A0], rdx
0x180017a27  lea     r8, [rcx+30h]; pszPathIn
0x180017a2b  mov     r14, rdx
0x180017a2e  mov     rsi, rcx
0x180017a31  mov     edx, 104h; cchPathOut
0x180017a36  lea     rcx, [rbp+5F0h+pszPathOut]; pszPathOut
0x180017a3d  call    cs:__imp_PathCchCombine
0x180017a43  mov     [rsp+6F0h+var_6C0], eax
0x180017a47  mov     ebx, eax
0x180017a49  test    eax, eax
0x180017a4b  js      loc_180017B67
0x180017a51  lea     rax, [rbp+5F0h+PathName]
0x180017a55  test    edi, edi
0x180017a57  mov     r8, r14; unsigned __int16 *
0x180017a5a  mov     [rsp+6F0h+var_6D0], rax; unsigned __int16 *
0x180017a5f  setnz   r9b; bool
0x180017a63  lea     rdx, [rbp+5F0h+pszPathOut]; unsigned __int16 *
0x180017a6a  call    ?GetCompleteItemPathFromTitle@IEFavResolver@@AEAAJPEBG0_NPEAGI@Z; IEFavResolver::GetCompleteItemPathFromTitle(ushort const *,ushort const *,bool,ushort *,uint)
0x180017a6f  mov     [rsp+6F0h+var_6C0], eax
0x180017a73  mov     ebx, eax
0x180017a75  test    eax, eax
0x180017a77  js      loc_180017B67
0x180017a7d  lea     rdx, [rbp+5F0h+PathName]; unsigned __int16 *
0x180017a81  mov     rcx, rsi; this
0x180017a84  call    ?AddToSyncList@IEFavResolver@@AEAAJPEAG@Z; IEFavResolver::AddToSyncList(ushort *)
0x180017a89  lea     rcx, [rbp+5F0h+PathName]; lpFileName
0x180017a8d  test    edi, edi
0x180017a8f  jz      short loc_180017A99
0x180017a91  call    cs:__imp_RemoveDirectoryW
0x180017a97  jmp     short loc_180017A9F
0x180017a99  call    cs:__imp_DeleteFileW
0x180017a9f  test    eax, eax
0x180017aa1  jnz     loc_180017B67
0x180017aa7  call    cs:__imp_GetLastError
0x180017aad  mov     ebx, eax
0x180017aaf  test    eax, eax
0x180017ab1  jle     short loc_180017ABC
0x180017ab3  movzx   ebx, ax
0x180017ab6  or      ebx, 80070000h
0x180017abc  mov     [rsp+6F0h+var_6C0], ebx
0x180017ac0  cmp     ebx, 80070002h
0x180017ac6  jz      loc_180017B52
0x180017acc  cmp     ebx, 80070091h
0x180017ad2  jnz     loc_180017B67
0x180017ad8  xor     edx, edx; Val
0x180017ada  lea     rcx, [rbp+5F0h+var_450]; void *
0x180017ae1  mov     r8d, 20Ah; Size
0x180017ae7  call    memset_0
0x180017aec  lea     r8, [rbp+5F0h+PathName]; unsigned __int16 *
0x180017af0  mov     edx, 104h; unsigned __int64
0x180017af5  lea     rcx, [rbp+5F0h+var_450]; unsigned __int16 *
0x180017afc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017b01  mov     [rsp+6F0h+var_6C0], eax
0x180017b05  mov     ebx, eax
0x180017b07  test    eax, eax
0x180017b09  js      short loc_180017B67
0x180017b0b  lea     rax, [rbp+5F0h+var_450]
0x180017b12  mov     [rsp+6F0h+FileOp.hwnd], 0
0x180017b1b  xorps   xmm0, xmm0
0x180017b1e  mov     [rsp+6F0h+FileOp.pFrom], rax
0x180017b23  lea     rcx, [rsp+6F0h+FileOp]; lpFileOp
0x180017b28  mov     qword ptr [rsp+6F0h+FileOp.wFunc], 3
0x180017b31  movdqu  xmmword ptr [rbp+5F0h+FileOp.hNameMappings], xmm0
0x180017b36  mov     [rsp+6F0h+FileOp.pTo], 0
0x180017b3f  mov     qword ptr [rsp+6F0h+FileOp.fFlags], 614h
0x180017b48  call    cs:__imp_SHFileOperationW
0x180017b4e  test    eax, eax
0x180017b50  jnz     short loc_180017B5E
0x180017b52  mov     [rsp+6F0h+var_6C0], 0
0x180017b5a  xor     ebx, ebx
0x180017b5c  jmp     short loc_180017B67
0x180017b5e  mov     ebx, 80004005h
0x180017b63  mov     [rsp+6F0h+var_6C0], ebx
0x180017b67  lea     r8, [rsp+6F0h+var_6C0]
0x180017b6c  lea     rdx, [rsp+6F0h+var_6B0]
0x180017b71  lea     rcx, [rsp+6F0h+var_6A0]
0x180017b76  call    ??$HandleItemDeletedFromEdge@AEAPEBGAEAPEBGAEAJ@BrowserTelemetry@@SAXAEAPEBG0AEAJ@Z; BrowserTelemetry::HandleItemDeletedFromEdge<ushort const * &,ushort const * &,long &>(ushort const * &,ushort const * &,long &)
0x180017b7b  mov     eax, ebx
0x180017b7d  mov     rcx, [rbp+5F0h+var_30]
0x180017b84  xor     rcx, rsp; StackCookie
0x180017b87  call    __security_check_cookie
0x180017b8c  add     rsp, 6D0h
0x180017b93  pop     r14
0x180017b95  pop     rdi
0x180017b96  pop     rsi
0x180017b97  pop     rbx
0x180017b98  pop     rbp
0x180017b99  retn
```
