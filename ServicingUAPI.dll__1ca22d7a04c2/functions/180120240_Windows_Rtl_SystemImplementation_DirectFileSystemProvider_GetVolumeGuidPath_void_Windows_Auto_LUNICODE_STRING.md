# Windows::Rtl::SystemImplementation::DirectFileSystemProvider::GetVolumeGuidPath(void *,Windows::Auto<_LUNICODE_STRING> *)

- ea: `0x180120240`
- end: `0x1801204ba`
- name: `?GetVolumeGuidPath@DirectFileSystemProvider@SystemImplementation@Rtl@Windows@@UEAAJPEAXPEAV?$Auto@U_LUNICODE_STRING@@@4@@Z`
- size: `634`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x18000aedc`
- `0x18000e098`
- `0x180049274`
- `0x1800497c0`
- `0x18004a468`
- `0x180050360`
- `0x180117e94`
- `0x180120240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120345`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801203c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120345`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801203c1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1801202af`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1801202ff`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1801202af`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1801202ff`

## string_xrefs

- `0x180120366`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::GetVolumeGuidPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Rtl::SystemImplementation::DirectFileSystemProvider::GetVolumeGuidPath(
        __int64 a1,
        void **a2,
        _QWORD *a3)
{
  void *v4; // rsi
  DWORD FinalPathNameByHandleW; // eax
  __int64 v6; // rcx
  DWORD v7; // edi
  int v8; // ebx
  WCHAR *v10; // rbx
  signed int LastError; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  WCHAR *v14; // rcx
  __int128 v15; // [rsp+28h] [rbp-E0h] BYREF
  LPWSTR lpszFilePath; // [rsp+38h] [rbp-D0h]
  LPWSTR lpszFilePath_8[2]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B8h]
  const char *v19; // [rsp+58h] [rbp-B0h]
  __int128 v20; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+70h] [rbp-98h]
  __int64 v22; // [rsp+78h] [rbp-90h]
  WCHAR szFilePath[1024]; // [rsp+88h] [rbp-80h] BYREF

  v22 = -2;
  v4 = *a2;
  memset_0(szFilePath, 0, sizeof(szFilePath));
  v15 = 0;
  lpszFilePath = 0;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(v4, szFilePath, 0x400u, 1u);
  v7 = FinalPathNameByHandleW;
  if ( FinalPathNameByHandleW <= 0x400 )
  {
    v10 = szFilePath;
  }
  else
  {
    v8 = RtlReallocateLUnicodeString(v6, 2LL * FinalPathNameByHandleW, &v15);
    if ( v8 < 0 )
    {
LABEL_3:
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v15);
      return (unsigned int)v8;
    }
    v10 = lpszFilePath;
    v7 = GetFinalPathNameByHandleW(v4, lpszFilePath, v7, 1u);
    if ( v10 && (*((_QWORD *)&v15 + 1) - (_QWORD)v15 < 2u || v10[(unsigned __int64)v15 >> 1]) )
      goto LABEL_27;
  }
  if ( !v7 )
  {
    if ( !GetLastError() )
    {
      LastError = 14077;
LABEL_13:
      lpszFilePath_8[0] = (LPWSTR)"onecore\\base\\wcp\\sil\\ntsystem.cpp";
      lpszFilePath_8[1] = (LPWSTR)"Windows::Rtl::SystemImplementation::DirectFileSystemProvider::GetVolumeGuidPath";
      v18 = 4886;
      v19 = "GetLastError";
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v8 = ConvertHResultToNtStatus((unsigned int)LastError);
      RtlReportErrorOrigination(lpszFilePath_8, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v8);
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v15);
      return (unsigned int)v8;
    }
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_13;
LABEL_27:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x1801204B9LL);
  }
  v12 = 0;
  v20 = 0;
  v21 = 0;
  if ( v10 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v10[v13] );
    v12 = 2 * v13;
    v14 = (WCHAR *)(v12 + 2);
  }
  else
  {
    v10 = 0;
    v14 = 0;
  }
  lpszFilePath_8[0] = (LPWSTR)v12;
  lpszFilePath_8[1] = v14;
  v18 = (__int64)v10;
  v8 = Windows::StringUtil::Rtl::SubStringByCharCount<_LUNICODE_STRING>(lpszFilePath_8, 0, 48, &v20);
  if ( v8 < 0 )
    goto LABEL_3;
  *(_OWORD *)lpszFilePath_8 = v20;
  v18 = v21;
  v8 = RtlConvertWin32FilePathToNtFilePath((unsigned __int64 *)lpszFilePath_8, a3);
  if ( v8 < 0 )
    goto LABEL_3;
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v15);
  return 0;
}

```

## disassembly

```asm
0x180120240  mov     rax, rsp
0x180120243  push    rbp
0x180120244  push    rsi
0x180120245  push    rdi
0x180120246  push    r14
0x180120248  push    r15
0x18012024a  lea     rbp, [rax-7B8h]
0x180120251  sub     rsp, 890h
0x180120258  mov     [rsp+8B0h+var_840], 0FFFFFFFFFFFFFFFEh
0x180120261  mov     [rax+8], rbx
0x180120265  mov     rax, cs:__security_cookie
0x18012026c  xor     rax, rsp
0x18012026f  mov     [rbp+7B0h+var_30], rax
0x180120276  mov     r14, r8
0x180120279  mov     rsi, [rdx]
0x18012027c  xor     edx, edx; Val
0x18012027e  mov     r8d, 800h; Size
0x180120284  lea     rcx, [rbp+7B0h+szFilePath]; void *
0x180120288  call    memset_0
0x18012028d  xorps   xmm0, xmm0
0x180120290  xor     eax, eax
0x180120292  movups  [rsp+8B0h+var_898+8], xmm0
0x180120297  mov     [rsp+8B0h+lpszFilePath], rax
0x18012029c  mov     ebx, 400h
0x1801202a1  lea     r9d, [rax+1]; dwFlags
0x1801202a5  mov     r8d, ebx; cchFilePath
0x1801202a8  lea     rdx, [rbp+7B0h+szFilePath]; lpszFilePath
0x1801202ac  mov     rcx, rsi; hFile
0x1801202af  call    cs:__imp_GetFinalPathNameByHandleW
0x1801202b6  nop     dword ptr [rax+rax+00h]
0x1801202bb  mov     edi, eax
0x1801202bd  xor     r15d, r15d
0x1801202c0  cmp     eax, ebx
0x1801202c2  jbe     short loc_180120339
0x1801202c4  mov     edx, edi
0x1801202c6  add     rdx, rdx
0x1801202c9  lea     r8, [rsp+8B0h+var_898+8]
0x1801202ce  call    RtlReallocateLUnicodeString
0x1801202d3  mov     ebx, eax
0x1801202d5  test    eax, eax
0x1801202d7  jns     short loc_1801202EB
0x1801202d9  lea     rcx, [rsp+8B0h+var_898+8]
0x1801202de  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801202e3  nop
0x1801202e4  mov     eax, ebx
0x1801202e6  jmp     loc_180120488
0x1801202eb  mov     rbx, [rsp+8B0h+lpszFilePath]
0x1801202f0  mov     r9d, 1; dwFlags
0x1801202f6  mov     r8d, edi; cchFilePath
0x1801202f9  mov     rdx, rbx; lpszFilePath
0x1801202fc  mov     rcx, rsi; hFile
0x1801202ff  call    cs:__imp_GetFinalPathNameByHandleW
0x180120306  nop     dword ptr [rax+rax+00h]
0x18012030b  mov     edi, eax
0x18012030d  test    rbx, rbx
0x180120310  jz      short loc_18012033D
0x180120312  mov     rax, [rsp+8B0h+var_888]
0x180120317  mov     rcx, qword ptr [rsp+8B0h+var_898+8]
0x18012031c  sub     rax, rcx
0x18012031f  cmp     rax, 2
0x180120323  jb      loc_1801204AF
0x180120329  shr     rcx, 1
0x18012032c  cmp     [rbx+rcx*2], r15w
0x180120331  jnz     loc_1801204AF
0x180120337  jmp     short loc_18012033D
0x180120339  lea     rbx, [rbp+7B0h+szFilePath]
0x18012033d  test    edi, edi
0x18012033f  jnz     loc_1801203D7
0x180120345  call    cs:__imp_GetLastError
0x18012034c  nop     dword ptr [rax+rax+00h]
0x180120351  test    eax, eax
0x180120353  jnz     short loc_1801203C1
0x180120355  mov     eax, 36FDh
0x18012035a  lea     rcx, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x180120361  mov     [rsp+8B0h+lpszFilePath+8], rcx
0x180120366  lea     rcx, aWindowsRtlSyst_217; "Windows::Rtl::SystemImplementation::Dir"...
0x18012036d  mov     [rsp+8B0h+var_870], rcx
0x180120372  mov     [rsp+8B0h+var_868], 1316h
0x18012037b  lea     rcx, aGetlasterror; "GetLastError"
0x180120382  mov     qword ptr [rsp+8B0h+var_860], rcx
0x180120387  test    eax, eax
0x180120389  jle     short loc_180120393
0x18012038b  movzx   eax, ax
0x18012038e  or      eax, 80070000h
0x180120393  mov     ecx, eax
0x180120395  call    ConvertHResultToNtStatus
0x18012039a  mov     ebx, eax
0x18012039c  mov     r8d, eax
0x18012039f  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801203a6  lea     rcx, [rsp+8B0h+lpszFilePath+8]
0x1801203ab  call    RtlReportErrorOrigination
0x1801203b0  nop
0x1801203b1  lea     rcx, [rsp+8B0h+var_898+8]
0x1801203b6  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801203bb  nop
0x1801203bc  jmp     loc_1801202E4
0x1801203c1  call    cs:__imp_GetLastError
0x1801203c8  nop     dword ptr [rax+rax+00h]
0x1801203cd  test    eax, eax
0x1801203cf  jz      loc_1801204AF
0x1801203d5  jmp     short loc_18012035A
0x1801203d7  xorps   xmm0, xmm0
0x1801203da  xor     eax, eax
0x1801203dc  movups  [rsp+8B0h+var_860+8], xmm0
0x1801203e1  mov     [rsp+8B0h+var_848], rax
0x1801203e6  test    rbx, rbx
0x1801203e9  jz      short loc_180120402
0x1801203eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801203ef  inc     rax
0x1801203f2  cmp     [rbx+rax*2], r15w
0x1801203f7  jnz     short loc_1801203EF
0x1801203f9  add     rax, rax
0x1801203fc  lea     rcx, [rax+2]
0x180120400  jmp     short loc_180120408
0x180120402  mov     rbx, r15
0x180120405  mov     rcx, r15
0x180120408  mov     [rsp+8B0h+lpszFilePath+8], rax
0x18012040d  mov     [rsp+8B0h+var_870], rcx
0x180120412  mov     [rsp+8B0h+var_868], rbx
0x180120417  lea     r9, [rsp+8B0h+var_860+8]
0x18012041c  xor     edx, edx
0x18012041e  lea     r8d, [rdx+30h]
0x180120422  lea     rcx, [rsp+8B0h+lpszFilePath+8]
0x180120427  call    ??$SubStringByCharCount@U_LUNICODE_STRING@@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@_K1PEAU3@@Z; Windows::StringUtil::Rtl::SubStringByCharCount<_LUNICODE_STRING>(_LUNICODE_STRING const &,unsigned __int64,unsigned __int64,_LUNICODE_STRING *)
0x18012042c  mov     ebx, eax
0x18012042e  test    eax, eax
0x180120430  jns     short loc_180120442
0x180120432  lea     rcx, [rsp+8B0h+var_898+8]
0x180120437  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x18012043c  nop
0x18012043d  jmp     loc_1801202E4
0x180120442  movups  xmm0, [rsp+8B0h+var_860+8]
0x180120447  movups  xmmword ptr [rsp+8B0h+lpszFilePath+8], xmm0
0x18012044c  movsd   xmm1, [rsp+8B0h+var_848]
0x180120452  movsd   [rsp+8B0h+var_868], xmm1
0x180120458  mov     rdx, r14
0x18012045b  lea     rcx, [rsp+8B0h+lpszFilePath+8]
0x180120460  call    RtlConvertWin32FilePathToNtFilePath
0x180120465  mov     ebx, eax
0x180120467  test    eax, eax
0x180120469  jns     short loc_18012047B
0x18012046b  lea     rcx, [rsp+8B0h+var_898+8]
0x180120470  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180120475  nop
0x180120476  jmp     loc_1801202E4
0x18012047b  lea     rcx, [rsp+8B0h+var_898+8]
0x180120480  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180120485  nop
0x180120486  xor     eax, eax
0x180120488  mov     rcx, [rbp+7B0h+var_30]
0x18012048f  xor     rcx, rsp; StackCookie
0x180120492  call    __security_check_cookie
0x180120497  mov     rbx, [rsp+8B0h+arg_0]
0x18012049f  add     rsp, 890h
0x1801204a6  pop     r15
0x1801204a8  pop     r14
0x1801204aa  pop     rdi
0x1801204ab  pop     rsi
0x1801204ac  pop     rbp
0x1801204ad  retn
0x1801204af  mov     ecx, 0C00000E5h; int
0x1801204b4  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
