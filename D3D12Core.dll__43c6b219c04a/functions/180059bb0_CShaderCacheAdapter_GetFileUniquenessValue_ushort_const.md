# CShaderCacheAdapter::GetFileUniquenessValue(ushort const *)

- ea: `0x180059bb0`
- end: `0x180059c2e`
- name: `?GetFileUniquenessValue@CShaderCacheAdapter@@SA_KPEBG@Z`
- size: `126`
- prototype: `unsigned __int64 __fastcall(LPCWSTR lpwstrFilename)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18005996c`
- `0x18008d1ec`

## callees

- `0x18000b920`
- `0x18000bfd8`
- `0x180059bb0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059c13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059c13`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180059be1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180059be1`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180059c0a`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180059c0a`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x1802356b8`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x1802356b8`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180235714`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180235714`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1802356ed`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1802356ed`

## pseudocode

```c
struct _FILETIME __fastcall CShaderCacheAdapter::GetFileUniquenessValue(LPCWSTR lpwstrFilename)
{
  HANDLE FileW; // rax
  void *v3; // rbx
  DWORD FileVersionInfoSize; // eax
  void *lpData; // rbx
  __int64 v7; // [rsp+40h] [rbp-18h]
  _QWORD v8[2]; // [rsp+48h] [rbp-10h] BYREF
  DWORD dwLen; // [rsp+68h] [rbp+10h] BYREF
  struct _FILETIME LastWriteTime; // [rsp+70h] [rbp+18h] BYREF
  LPVOID lpBuffer; // [rsp+78h] [rbp+20h] BYREF

  FileW = CreateFileW(lpwstrFilename, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v3 = FileW;
  LastWriteTime = 0;
  if ( FileW != (HANDLE)-1LL )
  {
    GetFileTime(FileW, 0, 0, &LastWriteTime);
    CloseHandle(v3);
    return LastWriteTime;
  }
  FileVersionInfoSize = GetFileVersionInfoSizeExW(1u, lpwstrFilename, 0);
  dwLen = FileVersionInfoSize;
  if ( FileVersionInfoSize )
  {
    lpData = operator new(FileVersionInfoSize);
    v8[0] = lpData;
    if ( GetFileVersionInfoExW(3u, lpwstrFilename, 0, dwLen, lpData) )
    {
      lpBuffer = 0;
      if ( VerQueryValueW(lpData, L"\\", &lpBuffer, &dwLen) )
      {
        HIDWORD(v7) = *((_DWORD *)lpBuffer + 2);
        LODWORD(v7) = *((_DWORD *)lpBuffer + 3);
        Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(v8);
        return (struct _FILETIME)v7;
      }
    }
    Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180059bb0  mov     rax, rsp
0x180059bb3  mov     [rax+8], rbx
0x180059bb7  push    rdi
0x180059bb8  sub     rsp, 50h
0x180059bbc  mov     rdi, rcx
0x180059bbf  mov     qword ptr [rax-28h], 0
0x180059bc7  mov     dword ptr [rax-30h], 80h
0x180059bce  mov     dword ptr [rax-38h], 3
0x180059bd5  xor     r9d, r9d; lpSecurityAttributes
0x180059bd8  mov     edx, 80000000h; dwDesiredAccess
0x180059bdd  lea     r8d, [r9+1]; dwShareMode
0x180059be1  call    cs:__imp_CreateFileW
0x180059be7  mov     rbx, rax
0x180059bea  mov     qword ptr [rsp+58h+LastWriteTime.dwLowDateTime], 0
0x180059bf3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180059bf7  jz      loc_1802356AE
0x180059bfd  lea     r9, [rsp+58h+LastWriteTime]; lpLastWriteTime
0x180059c02  xor     r8d, r8d; lpLastAccessTime
0x180059c05  xor     edx, edx; lpCreationTime
0x180059c07  mov     rcx, rax; hFile
0x180059c0a  call    cs:__imp_GetFileTime
0x180059c10  mov     rcx, rbx; hObject
0x180059c13  call    cs:__imp_CloseHandle
0x180059c19  mov     rax, qword ptr [rsp+58h+LastWriteTime.dwLowDateTime]
0x180059c1e  mov     rbx, [rsp+58h+arg_0]
0x180059c23  add     rsp, 50h
0x180059c27  pop     rdi
0x180059c28  retn
0x180059c29  jmp     loc_180235750
0x1802356ae  xor     r8d, r8d; lpdwHandle
0x1802356b1  mov     rdx, rdi; lpwstrFilename
0x1802356b4  lea     ecx, [r8+1]; dwFlags
0x1802356b8  call    cs:__imp_GetFileVersionInfoSizeExW
0x1802356be  mov     [rsp+58h+dwLen], eax
0x1802356c2  test    eax, eax
0x1802356c4  jz      loc_180235750
0x1802356ca  mov     ecx, eax; dwBytes
0x1802356cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802356d1  mov     rbx, rax
0x1802356d4  mov     [rsp+58h+var_10], rax
0x1802356d9  mov     [rsp+58h+lpData], rax; lpData
0x1802356de  mov     r9d, [rsp+58h+dwLen]; dwLen
0x1802356e3  xor     r8d, r8d; dwHandle
0x1802356e6  mov     rdx, rdi; lpwstrFilename
0x1802356e9  lea     ecx, [r8+3]; dwFlags
0x1802356ed  call    cs:__imp_GetFileVersionInfoExW
0x1802356f3  test    eax, eax
0x1802356f5  jz      short loc_180235745
0x1802356f7  mov     [rsp+58h+lpBuffer], 0
0x180235700  lea     r9, [rsp+58h+dwLen]; puLen
0x180235705  lea     r8, [rsp+58h+lpBuffer]; lplpBuffer
0x18023570a  lea     rdx, SubBlock; "\\"
0x180235711  mov     rcx, rbx; pBlock
0x180235714  call    cs:__imp_VerQueryValueW
0x18023571a  test    eax, eax
0x18023571c  jz      short loc_180235745
0x18023571e  mov     rcx, [rsp+58h+lpBuffer]
0x180235723  mov     eax, [rcx+8]
0x180235726  mov     dword ptr [rsp+58h+var_18+4], eax
0x18023572a  mov     eax, [rcx+0Ch]
0x18023572d  mov     dword ptr [rsp+58h+var_18], eax
0x180235731  lea     rcx, [rsp+58h+var_10]
0x180235736  call    ??1?$MakeAllocator@UCD3DShaderCacheInstallerFactory@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(void)
0x18023573b  mov     rax, [rsp+58h+var_18]
0x180235740  jmp     loc_180059C1E
0x180235745  lea     rcx, [rsp+58h+var_10]
0x18023574a  call    ??1?$MakeAllocator@UCD3DShaderCacheInstallerFactory@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(void)
0x18023574f  nop
0x180235750  xor     eax, eax
0x180235752  jmp     loc_180059C1E
```
