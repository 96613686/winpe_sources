# UtilFileExists(wchar_t const *)

- ea: `0x14000fa08`
- end: `0x14000fb5a`
- name: `?UtilFileExists@@YA_NPEB_W@Z`
- size: `338`
- prototype: `bool __fastcall(const wchar_t *)`
- caller_count: `7`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140038790`
- `0x140038af0`
- `0x14003a0c0`
- `0x140040fc8`
- `0x140044018`
- `0x140047dbc`
- `0x140053360`

## callees

- `0x140002728`
- `0x14000be58`
- `0x14000fa08`
- `0x14001444c`
- `0x1400145e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fb0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fb0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fad2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fad2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000fabc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000fabc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000fa81`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000fa81`

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
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    }
    return 0;
  }
  FileAttributesW = GetFileAttributesW(v10);
  v3 = FileAttributesW;
  if ( (FileAttributesW & 0x10) != 0 || FileAttributesW == -1 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
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
0x14000fa08  mov     [rsp-8+arg_0], rbx
0x14000fa0d  mov     [rsp-8+arg_8], rdi
0x14000fa12  push    rbp
0x14000fa13  mov     rbp, rsp
0x14000fa16  sub     rsp, 60h
0x14000fa1a  lea     rax, [rbp+var_10]
0x14000fa1e  mov     rdi, rcx
0x14000fa21  mov     [rbp+lpFileName], rax
0x14000fa25  lea     rdx, [rbp+lpFileName]
0x14000fa29  lea     rax, [rbp+var_10]
0x14000fa2d  mov     [rbp+var_18], rax
0x14000fa31  xor     eax, eax
0x14000fa33  mov     [rbp+var_10], ax
0x14000fa37  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14000fa3c  test    eax, eax
0x14000fa3e  jns     short loc_14000FA7D
0x14000fa40  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fa47  lea     rax, WPP_GLOBAL_Control
0x14000fa4e  cmp     rcx, rax
0x14000fa51  jz      loc_14000FB2F
0x14000fa57  mov     ebx, 1
0x14000fa5c  test    [rcx+1Ch], bl
0x14000fa5f  jz      loc_14000FB2F
0x14000fa65  mov     rcx, [rcx+10h]
0x14000fa69  lea     edx, [rbx+2Eh]
0x14000fa6c  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x14000fa73  call    WPP_SF_
0x14000fa78  jmp     loc_14000FB2F
0x14000fa7d  mov     rcx, [rbp+lpFileName]; lpFileName
0x14000fa81  call    cs:__imp_GetFileAttributesW
0x14000fa87  mov     ebx, eax
0x14000fa89  test    al, 10h
0x14000fa8b  jnz     short loc_14000FAF5
0x14000fa8d  cmp     eax, 0FFFFFFFFh
0x14000fa90  jz      short loc_14000FAF5
0x14000fa92  mov     rcx, [rbp+lpFileName]; lpFileName
0x14000fa96  xor     r9d, r9d; lpSecurityAttributes
0x14000fa99  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x14000faa2  mov     [rsp+60h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x14000faaa  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x14000fab2  lea     ebx, [r9+1]
0x14000fab6  mov     edx, ebx; dwDesiredAccess
0x14000fab8  lea     r8d, [r9+7]; dwShareMode
0x14000fabc  call    cs:__imp_CreateFileW
0x14000fac2  lea     rcx, [rax+1]
0x14000fac6  cmp     rcx, rbx
0x14000fac9  ja      short loc_14000FACF
0x14000facb  xor     bl, bl
0x14000facd  jmp     short loc_14000FAD8
0x14000facf  mov     rcx, rax; hObject
0x14000fad2  call    cs:__imp_CloseHandle
0x14000fad8  mov     rcx, [rbp+lpFileName]; void *
0x14000fadc  lea     rax, [rbp+var_10]
0x14000fae0  cmp     rcx, rax
0x14000fae3  jz      short loc_14000FAF1
0x14000fae5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000faec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000faf1  mov     al, bl
0x14000faf3  jmp     short loc_14000FB4A
0x14000faf5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fafc  lea     rax, WPP_GLOBAL_Control
0x14000fb03  cmp     rcx, rax
0x14000fb06  jz      short loc_14000FB2F
0x14000fb08  test    byte ptr [rcx+1Ch], 8
0x14000fb0c  jz      short loc_14000FB2F
0x14000fb0e  call    cs:__imp_GetLastError
0x14000fb14  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fb1b  mov     r9, rdi
0x14000fb1e  mov     [rsp+60h+dwFlagsAndAttributes], eax
0x14000fb22  mov     [rsp+60h+dwCreationDisposition], ebx
0x14000fb26  mov     rcx, [rcx+10h]
0x14000fb2a  call    WPP_SF_SDd
0x14000fb2f  mov     rcx, [rbp+lpFileName]; void *
0x14000fb33  lea     rax, [rbp+var_10]
0x14000fb37  cmp     rcx, rax
0x14000fb3a  jz      short loc_14000FB48
0x14000fb3c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000fb43  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000fb48  xor     al, al
0x14000fb4a  mov     rbx, [rsp+60h+arg_0]
0x14000fb4f  mov     rdi, [rsp+60h+arg_8]
0x14000fb54  add     rsp, 60h
0x14000fb58  pop     rbp
0x14000fb59  retn
```
