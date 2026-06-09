# GetPerfDllFileInfo(ushort const *,DLL_VALIDATION_DATA *)

- ea: `0x1800374bc`
- end: `0x1800375a2`
- name: `?GetPerfDllFileInfo@@YAJPEBGPEAUDLL_VALIDATION_DATA@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(const unsigned __int16 *, FILETIME *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180038fbc`

## callees

- `0x1800374bc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003757a`
- `KERNEL32!GetLastError` at `0x18003758d`
- `KERNEL32!GetLastError` at `0x18003757a`
- `KERNEL32!GetLastError` at `0x18003758d`
- `KERNEL32!CloseHandle` at `0x180037585`
- `KERNEL32!CloseHandle` at `0x180037585`
- `KERNEL32!CreateFileW` at `0x1800374f5`
- `KERNEL32!CreateFileW` at `0x1800374f5`
- `KERNEL32!GetFileSize` at `0x18003755e`
- `KERNEL32!GetFileSize` at `0x18003755e`
- `KERNEL32!DosDateTimeToFileTime` at `0x180037550`
- `KERNEL32!DosDateTimeToFileTime` at `0x180037550`
- `KERNEL32!FileTimeToDosDateTime` at `0x180037539`
- `KERNEL32!FileTimeToDosDateTime` at `0x180037539`
- `KERNEL32!GetFileTime` at `0x180037514`
- `KERNEL32!GetFileTime` at `0x180037514`

## pseudocode

```c
__int64 __fastcall GetPerfDllFileInfo(const unsigned __int16 *a1, FILETIME *a2)
{
  HANDLE FileW; // rax
  void *v4; // rdi
  DWORD LastError; // ebx
  FILETIME FileSizeHigh; // [rsp+40h] [rbp-18h] BYREF
  WORD FatTime; // [rsp+70h] [rbp+18h] BYREF
  WORD FatDate; // [rsp+78h] [rbp+20h] BYREF

  FileSizeHigh.dwHighDateTime = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    if ( !GetFileTime(FileW, a2, 0, 0) )
      goto LABEL_7;
    FatDate = 0;
    FatTime = 0;
    if ( FileTimeToDosDateTime(a2, &FatDate, &FatTime) )
      DosDateTimeToFileTime(FatDate, FatTime, a2);
    FileSizeHigh.dwLowDateTime = GetFileSize(v4, &FileSizeHigh.dwHighDateTime);
    if ( FileSizeHigh.dwLowDateTime == -1 )
    {
LABEL_7:
      LastError = GetLastError();
    }
    else
    {
      a2[1] = FileSizeHigh;
      LastError = 0;
    }
    CloseHandle(v4);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800374bc  mov     rax, rsp
0x1800374bf  mov     [rax+8], rbx
0x1800374c3  push    rdi
0x1800374c4  sub     rsp, 50h
0x1800374c8  mov     qword ptr [rax-28h], 0
0x1800374d0  xor     r9d, r9d; lpSecurityAttributes
0x1800374d3  mov     rbx, rdx
0x1800374d6  mov     dword ptr [rax-30h], 80h
0x1800374dd  mov     edx, 80000000h; dwDesiredAccess
0x1800374e2  mov     qword ptr [rax-18h], 0
0x1800374ea  mov     dword ptr [rax-38h], 3
0x1800374f1  lea     r8d, [r9+1]; dwShareMode
0x1800374f5  call    cs:__imp_CreateFileW
0x1800374fb  mov     rdi, rax
0x1800374fe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180037502  jz      loc_18003758D
0x180037508  xor     r9d, r9d; lpLastWriteTime
0x18003750b  xor     r8d, r8d; lpLastAccessTime
0x18003750e  mov     rdx, rbx; lpCreationTime
0x180037511  mov     rcx, rax; hFile
0x180037514  call    cs:__imp_GetFileTime
0x18003751a  test    eax, eax
0x18003751c  jz      short loc_18003757A
0x18003751e  xor     ecx, ecx
0x180037520  lea     r8, [rsp+58h+FatTime]; lpFatTime
0x180037525  mov     [rsp+58h+FatDate], cx
0x18003752a  lea     rdx, [rsp+58h+FatDate]; lpFatDate
0x18003752f  xor     eax, eax
0x180037531  mov     rcx, rbx; lpFileTime
0x180037534  mov     [rsp+58h+FatTime], ax
0x180037539  call    cs:__imp_FileTimeToDosDateTime
0x18003753f  test    eax, eax
0x180037541  jz      short loc_180037556
0x180037543  movzx   edx, [rsp+58h+FatTime]; wFatTime
0x180037548  mov     r8, rbx; lpFileTime
0x18003754b  movzx   ecx, [rsp+58h+FatDate]; wFatDate
0x180037550  call    cs:__imp_DosDateTimeToFileTime
0x180037556  lea     rdx, [rsp+58h+FileSizeHigh.dwHighDateTime]; lpFileSizeHigh
0x18003755b  mov     rcx, rdi; hFile
0x18003755e  call    cs:__imp_GetFileSize
0x180037564  mov     [rsp+58h+FileSizeHigh.dwLowDateTime], eax
0x180037568  cmp     eax, 0FFFFFFFFh
0x18003756b  jz      short loc_18003757A
0x18003756d  mov     rax, qword ptr [rsp+58h+FileSizeHigh.dwLowDateTime]
0x180037572  mov     [rbx+8], rax
0x180037576  xor     ebx, ebx
0x180037578  jmp     short loc_180037582
0x18003757a  call    cs:__imp_GetLastError
0x180037580  mov     ebx, eax
0x180037582  mov     rcx, rdi; hObject
0x180037585  call    cs:__imp_CloseHandle
0x18003758b  jmp     short loc_180037595
0x18003758d  call    cs:__imp_GetLastError
0x180037593  mov     ebx, eax
0x180037595  mov     eax, ebx
0x180037597  mov     rbx, [rsp+58h+arg_0]
0x18003759c  add     rsp, 50h
0x1800375a0  pop     rdi
0x1800375a1  retn
```
