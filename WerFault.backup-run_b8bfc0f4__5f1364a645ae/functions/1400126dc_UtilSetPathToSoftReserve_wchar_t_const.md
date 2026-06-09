# UtilSetPathToSoftReserve(wchar_t const *)

- ea: `0x1400126dc`
- end: `0x140012803`
- name: `?UtilSetPathToSoftReserve@@YAJPEB_W@Z`
- size: `295`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x14003c398`
- `0x14003e7a0`

## callees

- `0x1400126dc`
- `0x140014474`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001272b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001272b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400127f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400127f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140012718`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140012718`
- `ntdll!NtSetInformationFile` at `0x1400127a8`
- `ntdll!NtSetInformationFile` at `0x1400127a8`

## pseudocode

```c
__int64 __fastcall UtilSetPathToSoftReserve(const wchar_t *a1)
{
  HANDLE FileW; // rax
  void *v2; // rdi
  signed int LastError; // eax
  unsigned int v4; // ebx
  NTSTATUS v5; // ebx
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-18h] BYREF
  int FileInformation; // [rsp+68h] [rbp+10h] BYREF

  FileInformation = 0;
  IoStatusBlock = 0;
  FileW = CreateFileW(a1, 0x180u, 7u, 0, 3u, 0x2000080u, 0);
  v2 = FileW;
  if ( (unsigned __int64)FileW + 1 > 1 )
  {
    FileInformation = 2;
    v5 = NtSetInformationFile(FileW, &IoStatusBlock, &FileInformation, 4u, FileRenameInformation|0x40);
    if ( v5 >= 0 )
    {
      v4 = 0;
    }
    else
    {
      v4 = v5 | 0x10000000;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 185, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v4);
      }
    }
    CloseHandle(v2);
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( (v4 & 0x80000000) == 0 )
      v4 = -2147467259;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v4);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1400126dc  mov     rax, rsp
0x1400126df  mov     [rax+8], rbx
0x1400126e3  push    rdi
0x1400126e4  sub     rsp, 50h
0x1400126e8  mov     qword ptr [rax-28h], 0
0x1400126f0  xor     r9d, r9d; lpSecurityAttributes
0x1400126f3  xorps   xmm0, xmm0
0x1400126f6  mov     dword ptr [rax-30h], 2000080h
0x1400126fd  mov     edx, 180h; dwDesiredAccess
0x140012702  mov     dword ptr [rax+10h], 0
0x140012709  movups  xmmword ptr [rax-18h], xmm0
0x14001270d  lea     r8d, [r9+7]; dwShareMode
0x140012711  mov     dword ptr [rax-38h], 3
0x140012718  call    cs:__imp_CreateFileW
0x14001271e  mov     rdi, rax
0x140012721  lea     rcx, [rax+1]
0x140012725  cmp     rcx, 1
0x140012729  ja      short loc_140012785
0x14001272b  call    cs:__imp_GetLastError
0x140012731  mov     ebx, eax
0x140012733  test    eax, eax
0x140012735  jle     short loc_140012740
0x140012737  movzx   ebx, ax
0x14001273a  or      ebx, 80070000h
0x140012740  test    ebx, ebx
0x140012742  mov     eax, 80004005h
0x140012747  cmovns  ebx, eax
0x14001274a  mov     rcx, cs:WPP_GLOBAL_Control
0x140012751  lea     rax, WPP_GLOBAL_Control
0x140012758  cmp     rcx, rax
0x14001275b  jz      loc_1400127F6
0x140012761  test    byte ptr [rcx+1Ch], 2
0x140012765  jz      loc_1400127F6
0x14001276b  mov     rcx, [rcx+10h]
0x14001276f  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x140012776  mov     edx, 0B8h
0x14001277b  mov     r9d, ebx
0x14001277e  call    WPP_SF_d
0x140012783  jmp     short loc_1400127F6
0x140012785  mov     r9d, 4; Length
0x14001278b  mov     [rsp+58h+FileInformation], 2
0x140012793  lea     r8, [rsp+58h+FileInformation]; FileInformation
0x140012798  mov     [rsp+58h+FileInformationClass], 4Ah ; 'J'; FileInformationClass
0x1400127a0  lea     rdx, [rsp+58h+IoStatusBlock]; IoStatusBlock
0x1400127a5  mov     rcx, rdi; FileHandle
0x1400127a8  call    cs:__imp_NtSetInformationFile
0x1400127ae  mov     ebx, eax
0x1400127b0  test    eax, eax
0x1400127b2  jns     short loc_1400127EB
0x1400127b4  bts     ebx, 1Ch
0x1400127b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400127bf  lea     rax, WPP_GLOBAL_Control
0x1400127c6  cmp     rcx, rax
0x1400127c9  jz      short loc_1400127ED
0x1400127cb  test    byte ptr [rcx+1Ch], 2
0x1400127cf  jz      short loc_1400127ED
0x1400127d1  mov     rcx, [rcx+10h]
0x1400127d5  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1400127dc  mov     edx, 0B9h
0x1400127e1  mov     r9d, ebx
0x1400127e4  call    WPP_SF_d
0x1400127e9  jmp     short loc_1400127ED
0x1400127eb  xor     ebx, ebx
0x1400127ed  mov     rcx, rdi; hObject
0x1400127f0  call    cs:__imp_CloseHandle
0x1400127f6  mov     eax, ebx
0x1400127f8  mov     rbx, [rsp+58h+arg_0]
0x1400127fd  add     rsp, 50h
0x140012801  pop     rdi
0x140012802  retn
```
