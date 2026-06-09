# GetFileContent(ushort const *,uchar * const,ulong *)

- ea: `0x180036230`
- end: `0x180036312`
- name: `?GetFileContent@@YAJPEBGQEAEPEAK@Z`
- size: `226`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8 *const, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180037338`
- `0x18003a308`

## callees

- `0x180036230`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800362a2`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800362a2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003626f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003626f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800362eb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800362eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003627e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003627e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800362fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800362fa`

## pseudocode

```c
__int64 __fastcall GetFileContent(const unsigned __int16 *a1, unsigned __int8 *const a2, unsigned int *a3)
{
  HANDLE FileW; // rax
  void *v6; // rdi
  signed int v7; // eax
  unsigned int v8; // ebx
  signed int LastError; // eax
  union _LARGE_INTEGER FileSize; // [rsp+68h] [rbp+20h] BYREF

  FileSize.QuadPart = 0;
  FileW = CreateFileW(a1, 0x80000000, 0, 0, 3u, 0, 0);
  v6 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( a2 )
    {
      if ( !ReadFile(FileW, a2, *a3, 0, 0) )
      {
LABEL_6:
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_13;
      }
    }
    else
    {
      if ( !GetFileSizeEx(FileW, &FileSize) )
        goto LABEL_6;
      if ( FileSize.HighPart )
      {
        v8 = -2147418113;
LABEL_13:
        CloseHandle(v6);
        return v8;
      }
      *a3 = FileSize.LowPart;
    }
    v8 = 0;
    goto LABEL_13;
  }
  v7 = GetLastError();
  v8 = v7;
  if ( v7 > 0 )
    return (unsigned __int16)v7 | 0x80070000;
  return v8;
}

```

## disassembly

```asm
0x180036230  mov     rax, rsp
0x180036233  mov     [rax+8], rbx
0x180036237  mov     [rax+10h], rsi
0x18003623b  push    rdi
0x18003623c  sub     rsp, 40h
0x180036240  mov     qword ptr [rax-18h], 0
0x180036248  mov     rsi, r8
0x18003624b  mov     rbx, rdx
0x18003624e  mov     dword ptr [rax-20h], 0
0x180036255  xor     r8d, r8d; dwShareMode
0x180036258  mov     dword ptr [rax-28h], 3
0x18003625f  mov     edx, 80000000h; dwDesiredAccess
0x180036264  mov     qword ptr [rax+20h], 0
0x18003626c  xor     r9d, r9d; lpSecurityAttributes
0x18003626f  call    cs:__imp_CreateFileW
0x180036275  mov     rdi, rax
0x180036278  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003627c  jnz     short loc_180036295
0x18003627e  call    cs:__imp_GetLastError
0x180036284  mov     ebx, eax
0x180036286  test    eax, eax
0x180036288  jle     short loc_180036300
0x18003628a  movzx   ebx, ax
0x18003628d  or      ebx, 80070000h
0x180036293  jmp     short loc_180036300
0x180036295  mov     rcx, rdi; hFile
0x180036298  test    rbx, rbx
0x18003629b  jnz     short loc_1800362D9
0x18003629d  lea     rdx, [rsp+48h+FileSize]; lpFileSize
0x1800362a2  call    cs:__imp_GetFileSizeEx
0x1800362a8  test    eax, eax
0x1800362aa  jnz     short loc_1800362C3
0x1800362ac  call    cs:__imp_GetLastError
0x1800362b2  mov     ebx, eax
0x1800362b4  test    eax, eax
0x1800362b6  jle     short loc_1800362F7
0x1800362b8  movzx   ebx, ax
0x1800362bb  or      ebx, 80070000h
0x1800362c1  jmp     short loc_1800362F7
0x1800362c3  cmp     dword ptr [rsp+48h+FileSize+4], 0
0x1800362c8  jz      short loc_1800362D1
0x1800362ca  mov     ebx, 8000FFFFh
0x1800362cf  jmp     short loc_1800362F7
0x1800362d1  mov     eax, dword ptr [rsp+48h+FileSize]
0x1800362d5  mov     [rsi], eax
0x1800362d7  jmp     short loc_1800362F5
0x1800362d9  mov     r8d, [rsi]; nNumberOfBytesToRead
0x1800362dc  xor     r9d, r9d; lpNumberOfBytesRead
0x1800362df  mov     rdx, rbx; lpBuffer
0x1800362e2  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1800362eb  call    cs:__imp_ReadFile
0x1800362f1  test    eax, eax
0x1800362f3  jz      short loc_1800362AC
0x1800362f5  xor     ebx, ebx
0x1800362f7  mov     rcx, rdi; hObject
0x1800362fa  call    cs:__imp_CloseHandle
0x180036300  mov     rsi, [rsp+48h+arg_8]
0x180036305  mov     eax, ebx
0x180036307  mov     rbx, [rsp+48h+arg_0]
0x18003630c  add     rsp, 40h
0x180036310  pop     rdi
0x180036311  retn
```
