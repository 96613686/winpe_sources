# UtilSetPathToSoftReserve(wchar_t const *)

- ea: `0x180098fa0`
- end: `0x1800990a8`
- name: `?UtilSetPathToSoftReserve@@YAJPEB_W@Z`
- size: `264`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18001d128`
- `0x180076938`

## callees

- `0x18000716c`
- `0x180007e10`
- `0x180007e34`
- `0x18001fe24`
- `0x180098fa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099002`
- `ntdll!NtSetInformationFile` at `0x180099051`
- `ntdll!NtSetInformationFile` at `0x180099051`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180098fe0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180098fe0`

## pseudocode

```c
__int64 __fastcall UtilSetPathToSoftReserve(const wchar_t *a1)
{
  HANDLE FileW; // rax
  DWORD LastError; // eax
  unsigned int v3; // ebx
  wchar_t *v4; // rcx
  __int64 v5; // rdx
  NTSTATUS v6; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-18h] BYREF
  int FileInformation; // [rsp+68h] [rbp+10h] BYREF
  HANDLE FileHandle; // [rsp+70h] [rbp+18h] BYREF

  FileHandle = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  FileW = CreateFileW(a1, 0x180u, 7u, 0, 3u, 0x2000080u, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&FileHandle, FileW);
  if ( (unsigned __int64)FileHandle + 1 > 1 )
  {
    FileInformation = 2;
    v6 = NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 4u, FileRenameInformation|0x40);
    if ( v6 >= 0 )
    {
      v3 = 0;
      goto LABEL_11;
    }
    v3 = v6 | 0x10000000;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
    {
      v5 = 185;
      goto LABEL_9;
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = ERROR_HR_FROM_WIN32(LastError);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
    {
      v5 = 184;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v3);
    }
  }
LABEL_11:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&FileHandle);
  return v3;
}

```

## disassembly

```asm
0x180098fa0  mov     rax, rsp
0x180098fa3  push    rbx
0x180098fa4  sub     rsp, 50h
0x180098fa8  mov     qword ptr [rax-28h], 0
0x180098fb0  xor     r9d, r9d; lpSecurityAttributes
0x180098fb3  xorps   xmm0, xmm0
0x180098fb6  mov     dword ptr [rax-30h], 2000080h
0x180098fbd  mov     edx, 180h; dwDesiredAccess
0x180098fc2  mov     qword ptr [rax+18h], 0
0x180098fca  movups  xmmword ptr [rax-18h], xmm0
0x180098fce  lea     r8d, [r9+7]; dwShareMode
0x180098fd2  mov     dword ptr [rax+10h], 0
0x180098fd9  mov     dword ptr [rax-38h], 3
0x180098fe0  call    cs:__imp_CreateFileW
0x180098fe6  mov     rdx, rax
0x180098fe9  lea     rcx, [rsp+58h+FileHandle]
0x180098fee  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180098ff3  mov     rcx, [rsp+58h+FileHandle]; FileHandle
0x180098ff8  lea     rax, [rcx+1]
0x180098ffc  cmp     rax, 1
0x180099000  ja      short loc_180099031
0x180099002  call    cs:__imp_GetLastError
0x180099008  mov     ecx, eax; unsigned int
0x18009900a  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009900f  mov     ebx, eax
0x180099011  mov     rcx, cs:WPP_GLOBAL_Control
0x180099018  lea     rax, WPP_GLOBAL_Control
0x18009901f  cmp     rcx, rax
0x180099022  jz      short loc_180099096
0x180099024  test    byte ptr [rcx+1Ch], 2
0x180099028  jz      short loc_180099096
0x18009902a  mov     edx, 0B8h
0x18009902f  jmp     short loc_18009907F
0x180099031  mov     r9d, 4; Length
0x180099037  mov     [rsp+58h+FileInformation], 2
0x18009903f  lea     r8, [rsp+58h+FileInformation]; FileInformation
0x180099044  mov     [rsp+58h+FileInformationClass], 4Ah ; 'J'; FileInformationClass
0x18009904c  lea     rdx, [rsp+58h+IoStatusBlock]; IoStatusBlock
0x180099051  call    cs:__imp_NtSetInformationFile
0x180099057  mov     ebx, eax
0x180099059  test    eax, eax
0x18009905b  jns     short loc_180099094
0x18009905d  bts     ebx, 1Ch
0x180099061  mov     rcx, cs:WPP_GLOBAL_Control
0x180099068  lea     rax, WPP_GLOBAL_Control
0x18009906f  cmp     rcx, rax
0x180099072  jz      short loc_180099096
0x180099074  test    byte ptr [rcx+1Ch], 2
0x180099078  jz      short loc_180099096
0x18009907a  mov     edx, 0B9h
0x18009907f  mov     rcx, [rcx+10h]
0x180099083  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18009908a  mov     r9d, ebx
0x18009908d  call    WPP_SF_d
0x180099092  jmp     short loc_180099096
0x180099094  xor     ebx, ebx
0x180099096  lea     rcx, [rsp+58h+FileHandle]
0x18009909b  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800990a0  mov     eax, ebx
0x1800990a2  add     rsp, 50h
0x1800990a6  pop     rbx
0x1800990a7  retn
```
