# UtilFileExists(wchar_t const *)

- ea: `0x140010034`
- end: `0x14001019f`
- name: `?UtilFileExists@@YA_NPEB_W@Z`
- size: `363`
- prototype: `bool __fastcall(const wchar_t *)`
- caller_count: `7`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14003ad40`
- `0x14003b0a0`
- `0x14003c780`
- `0x140043cbc`
- `0x140046fdc`
- `0x14004b05c`
- `0x140056cbc`

## callees

- `0x140002748`
- `0x14000c060`
- `0x140010034`
- `0x140014ee4`
- `0x14001509c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001014c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001014c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001010a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001010a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400100ee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400100ee`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400100ad`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400100ad`

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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
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
0x140010034  mov     [rsp-8+arg_0], rbx
0x140010039  mov     [rsp-8+arg_8], rdi
0x14001003e  push    rbp
0x14001003f  mov     rbp, rsp
0x140010042  sub     rsp, 60h
0x140010046  lea     rax, [rbp+var_10]
0x14001004a  mov     rdi, rcx
0x14001004d  mov     [rbp+lpFileName], rax
0x140010051  lea     rdx, [rbp+lpFileName]
0x140010055  lea     rax, [rbp+var_10]
0x140010059  mov     [rbp+var_18], rax
0x14001005d  xor     eax, eax
0x14001005f  mov     [rbp+var_10], ax
0x140010063  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140010068  test    eax, eax
0x14001006a  jns     short loc_1400100A9
0x14001006c  mov     rcx, cs:WPP_GLOBAL_Control
0x140010073  lea     rax, WPP_GLOBAL_Control
0x14001007a  cmp     rcx, rax
0x14001007d  jz      loc_140010173
0x140010083  mov     ebx, 1
0x140010088  test    [rcx+1Ch], bl
0x14001008b  jz      loc_140010173
0x140010091  mov     rcx, [rcx+10h]
0x140010095  lea     edx, [rbx+2Eh]
0x140010098  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x14001009f  call    WPP_SF_
0x1400100a4  jmp     loc_140010173
0x1400100a9  mov     rcx, [rbp+lpFileName]; lpFileName
0x1400100ad  call    cs:__imp_GetFileAttributesW
0x1400100b4  nop     dword ptr [rax+rax+00h]
0x1400100b9  mov     ebx, eax
0x1400100bb  test    al, 10h
0x1400100bd  jnz     short loc_140010133
0x1400100bf  cmp     eax, 0FFFFFFFFh
0x1400100c2  jz      short loc_140010133
0x1400100c4  mov     rcx, [rbp+lpFileName]; lpFileName
0x1400100c8  xor     r9d, r9d; lpSecurityAttributes
0x1400100cb  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x1400100d4  mov     [rsp+60h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1400100dc  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x1400100e4  lea     ebx, [r9+1]
0x1400100e8  mov     edx, ebx; dwDesiredAccess
0x1400100ea  lea     r8d, [r9+7]; dwShareMode
0x1400100ee  call    cs:__imp_CreateFileW
0x1400100f5  nop     dword ptr [rax+rax+00h]
0x1400100fa  lea     rcx, [rax+1]
0x1400100fe  cmp     rcx, rbx
0x140010101  ja      short loc_140010107
0x140010103  xor     bl, bl
0x140010105  jmp     short loc_140010116
0x140010107  mov     rcx, rax; hObject
0x14001010a  call    cs:__imp_CloseHandle
0x140010111  nop     dword ptr [rax+rax+00h]
0x140010116  mov     rcx, [rbp+lpFileName]; void *
0x14001011a  lea     rax, [rbp+var_10]
0x14001011e  cmp     rcx, rax
0x140010121  jz      short loc_14001012F
0x140010123  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001012a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001012f  mov     al, bl
0x140010131  jmp     short loc_14001018E
0x140010133  mov     rcx, cs:WPP_GLOBAL_Control
0x14001013a  lea     rax, WPP_GLOBAL_Control
0x140010141  cmp     rcx, rax
0x140010144  jz      short loc_140010173
0x140010146  test    byte ptr [rcx+1Ch], 8
0x14001014a  jz      short loc_140010173
0x14001014c  call    cs:__imp_GetLastError
0x140010153  nop     dword ptr [rax+rax+00h]
0x140010158  mov     rcx, cs:WPP_GLOBAL_Control
0x14001015f  mov     r9, rdi
0x140010162  mov     [rsp+60h+dwFlagsAndAttributes], eax
0x140010166  mov     [rsp+60h+dwCreationDisposition], ebx
0x14001016a  mov     rcx, [rcx+10h]
0x14001016e  call    WPP_SF_SDd
0x140010173  mov     rcx, [rbp+lpFileName]; void *
0x140010177  lea     rax, [rbp+var_10]
0x14001017b  cmp     rcx, rax
0x14001017e  jz      short loc_14001018C
0x140010180  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140010187  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001018c  xor     al, al
0x14001018e  mov     rbx, [rsp+60h+arg_0]
0x140010193  mov     rdi, [rsp+60h+arg_8]
0x140010198  add     rsp, 60h
0x14001019c  pop     rbp
0x14001019d  retn
```
