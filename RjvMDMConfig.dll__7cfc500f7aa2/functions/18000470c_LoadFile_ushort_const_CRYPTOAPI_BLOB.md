# LoadFile(ushort const *,_CRYPTOAPI_BLOB *)

- ea: `0x18000470c`
- end: `0x180004874`
- name: `?LoadFile@@YAJPEBGPEAU_CRYPTOAPI_BLOB@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180004168`

## callees

- `0x1800038c0`
- `0x18000470c`
- `0x1800055f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004836`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004757`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004757`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800047ad`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800047ad`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180004826`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180004826`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800047f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800047f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047de`

## pseudocode

```c
__int64 __fastcall LoadFile(const unsigned __int16 *a1, struct _CRYPTOAPI_BLOB *a2)
{
  HANDLE FileW; // rax
  HANDLE v4; // rsi
  signed int v5; // eax
  unsigned int v6; // ebx
  DWORD FileSize; // eax
  SIZE_T v8; // rbx
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  BYTE *v11; // rax
  signed int v12; // eax
  HANDLE hFile[3]; // [rsp+40h] [rbp-18h] BYREF
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+18h] BYREF
  DWORD FileSizeHigh; // [rsp+78h] [rbp+20h] BYREF

  hFile[0] = (HANDLE)-1LL;
  FileSizeHigh = 0;
  NumberOfBytesRead = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    hFile,
    FileW);
  v4 = hFile[0];
  if ( (((unsigned __int64)hFile[0] + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    FileSize = GetFileSize(hFile[0], &FileSizeHigh);
    v8 = FileSize;
    a2->cbData = FileSize;
    if ( FileSize == -1 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v6 = LastError;
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v11 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v8);
      a2->pbData = v11;
      if ( v11 )
      {
        v6 = 0;
        if ( !ReadFile(v4, v11, a2->cbData, &NumberOfBytesRead, 0) )
        {
          v12 = GetLastError();
          v6 = v12;
          if ( v12 > 0 )
            v6 = (unsigned __int16)v12 | 0x80070000;
        }
        a2->cbData = NumberOfBytesRead;
      }
      else
      {
        v6 = -2147024882;
      }
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hFile);
  return v6;
}

```

## disassembly

```asm
0x18000470c  mov     rax, rsp
0x18000470f  mov     [rax+8], rbx
0x180004713  mov     [rax+10h], rsi
0x180004717  push    rdi
0x180004718  sub     rsp, 50h
0x18000471c  mov     qword ptr [rax-28h], 0
0x180004724  xor     r9d, r9d; lpSecurityAttributes
0x180004727  mov     rdi, rdx
0x18000472a  mov     dword ptr [rax-30h], 80h
0x180004731  mov     edx, 80000000h; dwDesiredAccess
0x180004736  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFFh
0x18000473e  mov     dword ptr [rax+20h], 0
0x180004745  lea     r8d, [r9+1]; dwShareMode
0x180004749  mov     dword ptr [rax+18h], 0
0x180004750  mov     dword ptr [rax-38h], 3
0x180004757  call    cs:__imp_CreateFileW
0x18000475e  nop     dword ptr [rax+rax+00h]
0x180004763  mov     rdx, rax
0x180004766  lea     rcx, [rsp+58h+hFile]
0x18000476b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180004770  mov     rsi, [rsp+58h+hFile]
0x180004775  lea     rax, [rsi+1]
0x180004779  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000477f  jnz     short loc_1800047A5
0x180004781  call    cs:__imp_GetLastError
0x180004788  nop     dword ptr [rax+rax+00h]
0x18000478d  mov     ebx, eax
0x18000478f  test    eax, eax
0x180004791  jle     loc_180004857
0x180004797  movzx   ebx, ax
0x18000479a  or      ebx, 80070000h
0x1800047a0  jmp     loc_180004857
0x1800047a5  lea     rdx, [rsp+58h+FileSizeHigh]; lpFileSizeHigh
0x1800047aa  mov     rcx, rsi; hFile
0x1800047ad  call    cs:__imp_GetFileSize
0x1800047b4  nop     dword ptr [rax+rax+00h]
0x1800047b9  mov     ebx, eax
0x1800047bb  mov     [rdi], ebx
0x1800047bd  cmp     eax, 0FFFFFFFFh
0x1800047c0  jnz     short loc_1800047DE
0x1800047c2  call    cs:__imp_GetLastError
0x1800047c9  nop     dword ptr [rax+rax+00h]
0x1800047ce  test    eax, eax
0x1800047d0  jle     short loc_1800047DA
0x1800047d2  movzx   eax, ax
0x1800047d5  or      eax, 80070000h
0x1800047da  mov     ebx, eax
0x1800047dc  jmp     short loc_180004857
0x1800047de  call    cs:__imp_GetProcessHeap
0x1800047e5  nop     dword ptr [rax+rax+00h]
0x1800047ea  mov     r8, rbx; dwBytes
0x1800047ed  mov     edx, 8; dwFlags
0x1800047f2  mov     rcx, rax; hHeap
0x1800047f5  call    cs:__imp_HeapAlloc
0x1800047fc  nop     dword ptr [rax+rax+00h]
0x180004801  mov     [rdi+8], rax
0x180004805  test    rax, rax
0x180004808  jnz     short loc_180004811
0x18000480a  mov     ebx, 8007000Eh
0x18000480f  jmp     short loc_180004857
0x180004811  mov     r8d, [rdi]; nNumberOfBytesToRead
0x180004814  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180004819  xor     ebx, ebx
0x18000481b  mov     rdx, rax; lpBuffer
0x18000481e  mov     rcx, rsi; hFile
0x180004821  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x180004826  call    cs:__imp_ReadFile
0x18000482d  nop     dword ptr [rax+rax+00h]
0x180004832  test    eax, eax
0x180004834  jnz     short loc_180004851
0x180004836  call    cs:__imp_GetLastError
0x18000483d  nop     dword ptr [rax+rax+00h]
0x180004842  mov     ebx, eax
0x180004844  test    eax, eax
0x180004846  jle     short loc_180004851
0x180004848  movzx   ebx, ax
0x18000484b  or      ebx, 80070000h
0x180004851  mov     eax, [rsp+58h+NumberOfBytesRead]
0x180004855  mov     [rdi], eax
0x180004857  lea     rcx, [rsp+58h+hFile]
0x18000485c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180004861  mov     rsi, [rsp+58h+arg_8]
0x180004866  mov     eax, ebx
0x180004868  mov     rbx, [rsp+58h+arg_0]
0x18000486d  add     rsp, 50h
0x180004871  pop     rdi
0x180004872  retn
```
