# WindowsPerformanceRecorder::Impl::CFileKey::SetFileTime(void)

- ea: `0x1800226d0`
- end: `0x180022787`
- name: `?SetFileTime@CFileKey@Impl@WindowsPerformanceRecorder@@QEAAJXZ`
- size: `183`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::Impl::CFileKey *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800218a8`
- `0x180021b7c`
- `0x180022634`
- `0x180043378`
- `0x1800490b0`

## callees

- `0x1800226d0`
- `0x180037634`
- `0x18004b39c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022718`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022718`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18002274d`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18002274d`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::Impl::CFileKey::SetFileTime(_FILETIME *this)
{
  const WCHAR *v2; // rcx
  __int64 result; // rax
  void *v4; // rbx
  HANDLE FileW; // rax
  unsigned int Error; // ebx
  _FILETIME LastWriteTime; // [rsp+50h] [rbp+8h] BYREF
  HANDLE v8; // [rsp+58h] [rbp+10h] BYREF

  v2 = (const WCHAR *)*this;
  if ( !*((_DWORD *)v2 - 4) )
    return 2147942487LL;
  v4 = 0;
  v8 = 0;
  FileW = CreateFileW(v2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    result = ATL::AtlHresultFromLastError();
    if ( (int)result < 0 )
      return result;
  }
  else
  {
    v4 = FileW;
    v8 = FileW;
  }
  LastWriteTime = 0;
  if ( GetFileTime(v4, 0, 0, &LastWriteTime) )
  {
    Error = 0;
    this[1] = LastWriteTime;
  }
  else
  {
    Error = ATL::AtlHresultFromLastError();
  }
  ATL::CHandle::~CHandle((ATL::CHandle *)&v8);
  return Error;
}

```

## disassembly

```asm
0x1800226d0  mov     [rsp+arg_10], rbx
0x1800226d5  push    rdi
0x1800226d6  sub     rsp, 40h
0x1800226da  mov     rdi, rcx
0x1800226dd  mov     rcx, [rcx]; lpFileName
0x1800226e0  cmp     dword ptr [rcx-10h], 0
0x1800226e4  jnz     short loc_1800226F0
0x1800226e6  mov     eax, 80070057h
0x1800226eb  jmp     loc_18002277C
0x1800226f0  xor     ebx, ebx
0x1800226f2  xor     r9d, r9d; lpSecurityAttributes
0x1800226f5  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x1800226fa  mov     edx, 80000000h; dwDesiredAccess
0x1800226ff  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180022707  mov     [rsp+48h+arg_8], rbx
0x18002270c  lea     r8d, [rbx+1]; dwShareMode
0x180022710  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180022718  call    cs:__imp_CreateFileW
0x18002271e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022722  jnz     short loc_18002272F
0x180022724  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180022729  test    eax, eax
0x18002272b  jns     short loc_180022737
0x18002272d  jmp     short loc_18002277C
0x18002272f  mov     rbx, rax
0x180022732  mov     [rsp+48h+arg_8], rax
0x180022737  lea     r9, [rsp+48h+LastWriteTime]; lpLastWriteTime
0x18002273c  mov     qword ptr [rsp+48h+LastWriteTime.dwLowDateTime], 0
0x180022745  xor     r8d, r8d; lpLastAccessTime
0x180022748  xor     edx, edx; lpCreationTime
0x18002274a  mov     rcx, rbx; hFile
0x18002274d  call    cs:__imp_GetFileTime
0x180022753  test    eax, eax
0x180022755  jnz     short loc_180022760
0x180022757  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002275c  mov     ebx, eax
0x18002275e  jmp     short loc_180022770
0x180022760  mov     eax, [rsp+48h+LastWriteTime.dwLowDateTime]
0x180022764  xor     ebx, ebx
0x180022766  mov     [rdi+8], eax
0x180022769  mov     eax, [rsp+48h+LastWriteTime.dwHighDateTime]
0x18002276d  mov     [rdi+0Ch], eax
0x180022770  lea     rcx, [rsp+48h+arg_8]; this
0x180022775  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x18002277a  mov     eax, ebx
0x18002277c  mov     rbx, [rsp+48h+arg_10]
0x180022781  add     rsp, 40h
0x180022785  pop     rdi
0x180022786  retn
```
