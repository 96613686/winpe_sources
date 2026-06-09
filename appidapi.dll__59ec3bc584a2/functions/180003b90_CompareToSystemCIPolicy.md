# CompareToSystemCIPolicy

- ea: `0x180003b90`
- end: `0x180003d1c`
- name: `CompareToSystemCIPolicy`
- size: `396`
- prototype: `__int64 __fastcall(void *Buf2, size_t Size)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180003534`
- `0x180003b90`
- `0x180009556`
- `0x1800095c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c75`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180003c96`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180003c96`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180003c42`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180003c42`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003c23`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003c23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cd3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ce1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ce1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003c67`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003c67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cc8`

## pseudocode

```c
__int64 __fastcall CompareToSystemCIPolicy(void *Buf2, size_t Size, _DWORD *a3)
{
  size_t v3; // r12
  DWORD SystemCIPolicyPath; // edi
  HANDLE FileW; // rax
  void *v8; // r14
  DWORD FileSize; // eax
  SIZE_T v10; // rbp
  void *v11; // rbx
  HANDLE ProcessHeap; // rax
  void *v13; // rax
  HANDLE v14; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-258h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-248h] BYREF

  v3 = (unsigned int)Size;
  NumberOfBytesRead = 0;
  if ( Buf2 && a3 )
  {
    *a3 = 0;
    SystemCIPolicyPath = GetSystemCIPolicyPath(FileName, Size);
    if ( !SystemCIPolicyPath )
    {
      FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
      v8 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        *a3 = 2;
      }
      else
      {
        FileSize = GetFileSize(FileW, 0);
        v10 = FileSize;
        if ( FileSize == (_DWORD)v3 )
        {
          ProcessHeap = GetProcessHeap();
          v13 = HeapAlloc(ProcessHeap, 0, v10);
          v11 = v13;
          if ( v13 && ReadFile(v8, v13, v10, &NumberOfBytesRead, 0) )
          {
            if ( NumberOfBytesRead == (_DWORD)v10 )
              *a3 = (memcmp_0(v11, Buf2, v3) != 0) + 1;
            else
              SystemCIPolicyPath = 38;
          }
          else
          {
            SystemCIPolicyPath = GetLastError();
          }
        }
        else
        {
          v11 = 0;
          *a3 = 2;
        }
        CloseHandle(v8);
        if ( v11 )
        {
          v14 = GetProcessHeap();
          HeapFree(v14, 0, v11);
        }
      }
    }
  }
  else
  {
    return 87;
  }
  return SystemCIPolicyPath;
}

```

## disassembly

```asm
0x180003b90  mov     [rsp+arg_0], rbx
0x180003b95  mov     [rsp+arg_8], rbp
0x180003b9a  push    rsi
0x180003b9b  push    rdi
0x180003b9c  push    r12
0x180003b9e  push    r14
0x180003ba0  push    r15
0x180003ba2  sub     rsp, 270h
0x180003ba9  mov     rax, cs:__security_cookie
0x180003bb0  xor     rax, rsp
0x180003bb3  mov     [rsp+298h+var_38], rax
0x180003bbb  mov     r12d, edx
0x180003bbe  mov     rsi, r8
0x180003bc1  mov     [rsp+298h+NumberOfBytesRead], 0
0x180003bc9  mov     r15, rcx
0x180003bcc  test    rcx, rcx
0x180003bcf  jz      loc_180003CE9
0x180003bd5  test    r8, r8
0x180003bd8  jz      loc_180003CE9
0x180003bde  lea     rcx, [rsp+298h+FileName]; Destination
0x180003be3  mov     dword ptr [r8], 0
0x180003bea  call    ?GetSystemCIPolicyPath@@YAKPEAGI@Z; GetSystemCIPolicyPath(ushort *,uint)
0x180003bef  mov     edi, eax
0x180003bf1  test    eax, eax
0x180003bf3  jnz     loc_180003CEE
0x180003bf9  mov     [rsp+298h+hTemplateFile], 0; hTemplateFile
0x180003c02  lea     r8d, [rax+1]; dwShareMode
0x180003c06  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180003c0e  lea     rcx, [rsp+298h+FileName]; lpFileName
0x180003c13  xor     r9d, r9d; lpSecurityAttributes
0x180003c16  mov     [rsp+298h+dwCreationDisposition], 3; dwCreationDisposition
0x180003c1e  mov     edx, 80000000h; dwDesiredAccess
0x180003c23  call    cs:__imp_CreateFileW
0x180003c29  mov     r14, rax
0x180003c2c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003c30  jnz     short loc_180003C3D
0x180003c32  mov     dword ptr [rsi], 2
0x180003c38  jmp     loc_180003CEE
0x180003c3d  xor     edx, edx; lpFileSizeHigh
0x180003c3f  mov     rcx, r14; hFile
0x180003c42  call    cs:__imp_GetFileSize
0x180003c48  mov     ebp, eax
0x180003c4a  cmp     eax, r12d
0x180003c4d  jz      short loc_180003C59
0x180003c4f  xor     ebx, ebx
0x180003c51  mov     dword ptr [rsi], 2
0x180003c57  jmp     short loc_180003CC5
0x180003c59  call    cs:__imp_GetProcessHeap
0x180003c5f  mov     r8, rbp; dwBytes
0x180003c62  xor     edx, edx; dwFlags
0x180003c64  mov     rcx, rax; hHeap
0x180003c67  call    cs:__imp_HeapAlloc
0x180003c6d  mov     rbx, rax
0x180003c70  test    rax, rax
0x180003c73  jnz     short loc_180003C7F
0x180003c75  call    cs:__imp_GetLastError
0x180003c7b  mov     edi, eax
0x180003c7d  jmp     short loc_180003CC5
0x180003c7f  lea     r9, [rsp+298h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180003c84  mov     qword ptr [rsp+298h+dwCreationDisposition], 0; lpOverlapped
0x180003c8d  mov     r8d, ebp; nNumberOfBytesToRead
0x180003c90  mov     rdx, rbx; lpBuffer
0x180003c93  mov     rcx, r14; hFile
0x180003c96  call    cs:__imp_ReadFile
0x180003c9c  test    eax, eax
0x180003c9e  jz      short loc_180003C75
0x180003ca0  cmp     [rsp+298h+NumberOfBytesRead], ebp
0x180003ca4  jz      short loc_180003CAD
0x180003ca6  mov     edi, 26h ; '&'
0x180003cab  jmp     short loc_180003CC5
0x180003cad  mov     r8, r12; Size
0x180003cb0  mov     rdx, r15; Buf2
0x180003cb3  mov     rcx, rbx; Buf1
0x180003cb6  call    memcmp_0
0x180003cbb  neg     eax
0x180003cbd  sbb     ecx, ecx
0x180003cbf  neg     ecx
0x180003cc1  inc     ecx
0x180003cc3  mov     [rsi], ecx
0x180003cc5  mov     rcx, r14; hObject
0x180003cc8  call    cs:__imp_CloseHandle
0x180003cce  test    rbx, rbx
0x180003cd1  jz      short loc_180003CEE
0x180003cd3  call    cs:__imp_GetProcessHeap
0x180003cd9  mov     r8, rbx; lpMem
0x180003cdc  xor     edx, edx; dwFlags
0x180003cde  mov     rcx, rax; hHeap
0x180003ce1  call    cs:__imp_HeapFree
0x180003ce7  jmp     short loc_180003CEE
0x180003ce9  mov     edi, 57h ; 'W'
0x180003cee  mov     eax, edi
0x180003cf0  mov     rcx, [rsp+298h+var_38]
0x180003cf8  xor     rcx, rsp; StackCookie
0x180003cfb  call    __security_check_cookie
0x180003d00  lea     r11, [rsp+298h+var_28]
0x180003d08  mov     rbx, [r11+30h]
0x180003d0c  mov     rbp, [r11+38h]
0x180003d10  mov     rsp, r11
0x180003d13  pop     r15
0x180003d15  pop     r14
0x180003d17  pop     r12
0x180003d19  pop     rdi
0x180003d1a  pop     rsi
0x180003d1b  retn
```
