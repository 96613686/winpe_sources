# UtilFileExists(wchar_t const *)

- ea: `0x140017c8c`
- end: `0x140017dde`
- name: `?UtilFileExists@@YA_NPEB_W@Z`
- size: `338`
- prototype: `bool __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140007cf0`

## callees

- `0x140003224`
- `0x14000b280`
- `0x14000e318`
- `0x140017c8c`
- `0x140018ad8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017d92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017d92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017d56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017d56`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140017d40`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140017d40`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140017d05`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140017d05`

## pseudocode

```c
char __fastcall UtilFileExists(const wchar_t *a1)
{
  int v1; // edi
  DWORD FileAttributesW; // eax
  char v3; // bl
  char v4; // bl
  HANDLE FileW; // rax
  char LastError; // al
  int v8; // edx
  int v9; // r8d
  WCHAR v10[8]; // [rsp+50h] [rbp-10h] BYREF

  v1 = (int)a1;
  v10[0] = 0;
  if ( (int)UtilExpandEnvironmentStrings(a1) < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    return 0;
  }
  FileAttributesW = GetFileAttributesW(v10);
  v3 = FileAttributesW;
  if ( (FileAttributesW & 0x10) != 0 || FileAttributesW == -1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_SDd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, v1, v3, LastError);
    }
    return 0;
  }
  v4 = 1;
  FileW = CreateFileW(v10, 1u, 7u, 0, 3u, 0, 0);
  if ( (unsigned __int64)FileW + 1 <= 1 )
    return 0;
  CloseHandle(FileW);
  return v4;
}

```

## disassembly

```asm
0x140017c8c  mov     [rsp-8+arg_0], rbx
0x140017c91  mov     [rsp-8+arg_8], rdi
0x140017c96  push    rbp
0x140017c97  mov     rbp, rsp
0x140017c9a  sub     rsp, 60h
0x140017c9e  lea     rax, [rbp+var_10]
0x140017ca2  mov     rdi, rcx
0x140017ca5  mov     [rbp+lpFileName], rax
0x140017ca9  lea     rdx, [rbp+lpFileName]
0x140017cad  lea     rax, [rbp+var_10]
0x140017cb1  mov     [rbp+var_18], rax
0x140017cb5  xor     eax, eax
0x140017cb7  mov     [rbp+var_10], ax
0x140017cbb  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140017cc0  test    eax, eax
0x140017cc2  jns     short loc_140017D01
0x140017cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140017ccb  lea     rax, WPP_GLOBAL_Control
0x140017cd2  cmp     rcx, rax
0x140017cd5  jz      loc_140017DB3
0x140017cdb  mov     ebx, 1
0x140017ce0  test    [rcx+1Ch], bl
0x140017ce3  jz      loc_140017DB3
0x140017ce9  mov     rcx, [rcx+10h]
0x140017ced  lea     edx, [rbx+2Eh]
0x140017cf0  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x140017cf7  call    WPP_SF_
0x140017cfc  jmp     loc_140017DB3
0x140017d01  mov     rcx, [rbp+lpFileName]; lpFileName
0x140017d05  call    cs:__imp_GetFileAttributesW
0x140017d0b  mov     ebx, eax
0x140017d0d  test    al, 10h
0x140017d0f  jnz     short loc_140017D79
0x140017d11  cmp     eax, 0FFFFFFFFh
0x140017d14  jz      short loc_140017D79
0x140017d16  mov     rcx, [rbp+lpFileName]; lpFileName
0x140017d1a  xor     r9d, r9d; lpSecurityAttributes
0x140017d1d  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x140017d26  mov     [rsp+60h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x140017d2e  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x140017d36  lea     ebx, [r9+1]
0x140017d3a  mov     edx, ebx; dwDesiredAccess
0x140017d3c  lea     r8d, [r9+7]; dwShareMode
0x140017d40  call    cs:__imp_CreateFileW
0x140017d46  lea     rcx, [rax+1]
0x140017d4a  cmp     rcx, rbx
0x140017d4d  ja      short loc_140017D53
0x140017d4f  xor     bl, bl
0x140017d51  jmp     short loc_140017D5C
0x140017d53  mov     rcx, rax; hObject
0x140017d56  call    cs:__imp_CloseHandle
0x140017d5c  mov     rcx, [rbp+lpFileName]; void *
0x140017d60  lea     rax, [rbp+var_10]
0x140017d64  cmp     rcx, rax
0x140017d67  jz      short loc_140017D75
0x140017d69  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140017d70  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017d75  mov     al, bl
0x140017d77  jmp     short loc_140017DCE
0x140017d79  mov     rcx, cs:WPP_GLOBAL_Control
0x140017d80  lea     rax, WPP_GLOBAL_Control
0x140017d87  cmp     rcx, rax
0x140017d8a  jz      short loc_140017DB3
0x140017d8c  test    byte ptr [rcx+1Ch], 8
0x140017d90  jz      short loc_140017DB3
0x140017d92  call    cs:__imp_GetLastError
0x140017d98  mov     rcx, cs:WPP_GLOBAL_Control
0x140017d9f  mov     r9, rdi
0x140017da2  mov     [rsp+60h+dwFlagsAndAttributes], eax
0x140017da6  mov     [rsp+60h+dwCreationDisposition], ebx
0x140017daa  mov     rcx, [rcx+10h]
0x140017dae  call    WPP_SF_SDd
0x140017db3  mov     rcx, [rbp+lpFileName]; void *
0x140017db7  lea     rax, [rbp+var_10]
0x140017dbb  cmp     rcx, rax
0x140017dbe  jz      short loc_140017DCC
0x140017dc0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140017dc7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017dcc  xor     al, al
0x140017dce  mov     rbx, [rsp+60h+arg_0]
0x140017dd3  mov     rdi, [rsp+60h+arg_8]
0x140017dd8  add     rsp, 60h
0x140017ddc  pop     rbp
0x140017ddd  retn
```
