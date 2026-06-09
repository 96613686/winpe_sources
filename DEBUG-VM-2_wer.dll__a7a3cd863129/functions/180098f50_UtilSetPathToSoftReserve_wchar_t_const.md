# UtilSetPathToSoftReserve(wchar_t const *)

- ea: `0x180098f50`
- end: `0x180099058`
- name: `?UtilSetPathToSoftReserve@@YAJPEB_W@Z`
- size: `264`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18001d128`
- `0x1800768e8`

## callees

- `0x18000716c`
- `0x180007e10`
- `0x180007e34`
- `0x18001fe24`
- `0x180098f50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098fb2`
- `ntdll!NtSetInformationFile` at `0x180099001`
- `ntdll!NtSetInformationFile` at `0x180099001`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180098f90`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180098f90`

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
0x180098f50  mov     rax, rsp
0x180098f53  push    rbx
0x180098f54  sub     rsp, 50h
0x180098f58  mov     qword ptr [rax-28h], 0
0x180098f60  xor     r9d, r9d; lpSecurityAttributes
0x180098f63  xorps   xmm0, xmm0
0x180098f66  mov     dword ptr [rax-30h], 2000080h
0x180098f6d  mov     edx, 180h; dwDesiredAccess
0x180098f72  mov     qword ptr [rax+18h], 0
0x180098f7a  movups  xmmword ptr [rax-18h], xmm0
0x180098f7e  lea     r8d, [r9+7]; dwShareMode
0x180098f82  mov     dword ptr [rax+10h], 0
0x180098f89  mov     dword ptr [rax-38h], 3
0x180098f90  call    cs:__imp_CreateFileW
0x180098f96  mov     rdx, rax
0x180098f99  lea     rcx, [rsp+58h+FileHandle]
0x180098f9e  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180098fa3  mov     rcx, [rsp+58h+FileHandle]; FileHandle
0x180098fa8  lea     rax, [rcx+1]
0x180098fac  cmp     rax, 1
0x180098fb0  ja      short loc_180098FE1
0x180098fb2  call    cs:__imp_GetLastError
0x180098fb8  mov     ecx, eax; unsigned int
0x180098fba  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180098fbf  mov     ebx, eax
0x180098fc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180098fc8  lea     rax, WPP_GLOBAL_Control
0x180098fcf  cmp     rcx, rax
0x180098fd2  jz      short loc_180099046
0x180098fd4  test    byte ptr [rcx+1Ch], 2
0x180098fd8  jz      short loc_180099046
0x180098fda  mov     edx, 0B8h
0x180098fdf  jmp     short loc_18009902F
0x180098fe1  mov     r9d, 4; Length
0x180098fe7  mov     [rsp+58h+FileInformation], 2
0x180098fef  lea     r8, [rsp+58h+FileInformation]; FileInformation
0x180098ff4  mov     [rsp+58h+FileInformationClass], 4Ah ; 'J'; FileInformationClass
0x180098ffc  lea     rdx, [rsp+58h+IoStatusBlock]; IoStatusBlock
0x180099001  call    cs:__imp_NtSetInformationFile
0x180099007  mov     ebx, eax
0x180099009  test    eax, eax
0x18009900b  jns     short loc_180099044
0x18009900d  bts     ebx, 1Ch
0x180099011  mov     rcx, cs:WPP_GLOBAL_Control
0x180099018  lea     rax, WPP_GLOBAL_Control
0x18009901f  cmp     rcx, rax
0x180099022  jz      short loc_180099046
0x180099024  test    byte ptr [rcx+1Ch], 2
0x180099028  jz      short loc_180099046
0x18009902a  mov     edx, 0B9h
0x18009902f  mov     rcx, [rcx+10h]
0x180099033  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18009903a  mov     r9d, ebx
0x18009903d  call    WPP_SF_d
0x180099042  jmp     short loc_180099046
0x180099044  xor     ebx, ebx
0x180099046  lea     rcx, [rsp+58h+FileHandle]
0x18009904b  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180099050  mov     eax, ebx
0x180099052  add     rsp, 50h
0x180099056  pop     rbx
0x180099057  retn
```
