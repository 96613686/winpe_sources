# CGPOFileDownloader::GetEndpointFiles(ushort const *,ushort const *)

- ea: `0x18000d950`
- end: `0x18000da36`
- name: `?GetEndpointFiles@CGPOFileDownloader@@AEAAKPEBG0@Z`
- size: `230`
- prototype: `__int64 __fastcall(HANDLE *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000d864`

## callees

- `0x18000d950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da23`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d9ae`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d9ae`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000d966`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000d966`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000d9d5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000d9d5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d996`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000da13`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d996`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000da13`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d9c7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d9c7`

## pseudocode

```c
__int64 __fastcall CGPOFileDownloader::GetEndpointFiles(
        HANDLE *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  DWORD LastError; // ebx
  HANDLE FileW; // rax
  HANDLE v8; // rax

  if ( !ImpersonateLoggedOnUser(this[2]) )
    goto LABEL_5;
  LastError = 0;
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x40000020u, 0);
  this[3] = FileW;
  if ( FileW == (HANDLE)-1LL )
    LastError = GetLastError();
  if ( !RevertToSelf() )
LABEL_5:
    LastError = GetLastError();
  if ( !LastError && (GetFileAttributesW(a3) == -1 || DeleteFileW(a3) || (LastError = GetLastError()) == 0) )
  {
    v8 = CreateFileW(a3, 0x40000000u, 1u, 0, 1u, 0x20u, 0);
    this[4] = v8;
    if ( v8 == (HANDLE)-1LL )
      return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x18000d950  push    rbx
0x18000d952  push    rbp
0x18000d953  push    rsi
0x18000d954  push    rdi
0x18000d955  sub     rsp, 48h
0x18000d959  mov     rsi, rcx
0x18000d95c  mov     rdi, r8
0x18000d95f  mov     rcx, [rcx+10h]; hToken
0x18000d963  mov     rbp, rdx
0x18000d966  call    cs:__imp_ImpersonateLoggedOnUser
0x18000d96c  test    eax, eax
0x18000d96e  jz      short loc_18000D9B8
0x18000d970  xor     ebx, ebx
0x18000d972  xor     r9d, r9d; lpSecurityAttributes
0x18000d975  mov     [rsp+68h+hTemplateFile], rbx; hTemplateFile
0x18000d97a  mov     edx, 80000000h; dwDesiredAccess
0x18000d97f  mov     [rsp+68h+dwFlagsAndAttributes], 40000020h; dwFlagsAndAttributes
0x18000d987  mov     rcx, rbp; lpFileName
0x18000d98a  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18000d992  lea     r8d, [rbx+1]; dwShareMode
0x18000d996  call    cs:__imp_CreateFileW
0x18000d99c  mov     [rsi+18h], rax
0x18000d9a0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d9a4  jnz     short loc_18000D9AE
0x18000d9a6  call    cs:__imp_GetLastError
0x18000d9ac  mov     ebx, eax
0x18000d9ae  call    cs:__imp_RevertToSelf
0x18000d9b4  test    eax, eax
0x18000d9b6  jnz     short loc_18000D9C0
0x18000d9b8  call    cs:__imp_GetLastError
0x18000d9be  mov     ebx, eax
0x18000d9c0  test    ebx, ebx
0x18000d9c2  jnz     short loc_18000DA2B
0x18000d9c4  mov     rcx, rdi; lpFileName
0x18000d9c7  call    cs:__imp_GetFileAttributesW
0x18000d9cd  cmp     eax, 0FFFFFFFFh
0x18000d9d0  jz      short loc_18000D9EB
0x18000d9d2  mov     rcx, rdi; lpFileName
0x18000d9d5  call    cs:__imp_DeleteFileW
0x18000d9db  test    eax, eax
0x18000d9dd  jnz     short loc_18000D9EB
0x18000d9df  call    cs:__imp_GetLastError
0x18000d9e5  mov     ebx, eax
0x18000d9e7  test    eax, eax
0x18000d9e9  jnz     short loc_18000DA2B
0x18000d9eb  xor     r9d, r9d; lpSecurityAttributes
0x18000d9ee  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18000d9f7  mov     [rsp+68h+dwFlagsAndAttributes], 20h ; ' '; dwFlagsAndAttributes
0x18000d9ff  mov     edx, 40000000h; dwDesiredAccess
0x18000da04  mov     rcx, rdi; lpFileName
0x18000da07  mov     [rsp+68h+dwCreationDisposition], 1; dwCreationDisposition
0x18000da0f  lea     r8d, [r9+1]; dwShareMode
0x18000da13  call    cs:__imp_CreateFileW
0x18000da19  mov     [rsi+20h], rax
0x18000da1d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000da21  jnz     short loc_18000DA2B
0x18000da23  call    cs:__imp_GetLastError
0x18000da29  mov     ebx, eax
0x18000da2b  mov     eax, ebx
0x18000da2d  add     rsp, 48h
0x18000da31  pop     rdi
0x18000da32  pop     rsi
0x18000da33  pop     rbp
0x18000da34  pop     rbx
0x18000da35  retn
```
