# ARI::DependencyMiniRepository::Writer::Save(ulong,void const *,ushort const *,ARI::DependencyMiniRepository::Writer::FlushOnWrite,_SECURITY_ATTRIBUTES *,ulong)

- ea: `0x180022e94`
- end: `0x18002305f`
- name: `?Save@Writer@DependencyMiniRepository@ARI@@QEAAJKPEBXPEBGW4FlushOnWrite@123@PEAU_SECURITY_ATTRIBUTES@@K@Z`
- size: `459`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180022b80`
- `0x180127584`

## callees

- `0x180022e94`
- `0x1800a021c`
- `0x1800a5970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ee4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ee4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002304e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002304e`
- `ntdll!ZwFlushBuffersFileEx` at `0x180023022`
- `ntdll!ZwFlushBuffersFileEx` at `0x180023022`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180022f51`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180022f51`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180022f1d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180022f1d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022ecc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022f82`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022ecc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022f82`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180022fe1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180022fe1`

## string_xrefs

- `0x180022ef9`: `onecore\private\base\inc\appmodel\runtime\DependencyMiniRepositoryWriter.inl`
- `0x180022ff0`: `onecore\private\base\inc\appmodel\runtime\DependencyMiniRepositoryWriter.inl`
- `0x180023031`: `onecore\private\base\inc\appmodel\runtime\DependencyMiniRepositoryWriter.inl`

## pseudocode

```c
__int64 __fastcall ARI::DependencyMiniRepository::Writer::Save(
        __int64 a1,
        DWORD a2,
        const void *a3,
        const WCHAR *a4,
        DWORD NumberOfBytesWritten)
{
  char *FileW; // rbx
  const char *v9; // r9
  __int64 v10; // rdx
  unsigned int LastError; // edi
  DWORD FileAttributesW; // eax
  char *v14; // rdi
  const char *v15; // r9
  unsigned int v16; // eax
  int v17; // eax
  int v18[4]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileW = (char *)CreateFileW(a4, 0x40000000u, 0, 0, 2u, 0x8000000u, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_18;
  if ( GetLastError() != 5 )
  {
    v10 = 133;
    goto LABEL_4;
  }
  FileAttributesW = GetFileAttributesW(a4);
  if ( FileAttributesW == -1 )
  {
LABEL_16:
    if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v10 = 155;
LABEL_4:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v10,
                    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\runtime\\DependencyMiniRepositoryWriter.inl",
                    v9);
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        return LastError;
      goto LABEL_24;
    }
LABEL_18:
    NumberOfBytesWritten = 0;
    if ( WriteFile(FileW, a3, a2, &NumberOfBytesWritten, 0) )
    {
      *(_OWORD *)v18 = 0;
      v17 = ZwFlushBuffersFileEx(FileW, 1, 0);
      if ( v17 >= 0 )
      {
        LastError = 0;
        goto LABEL_24;
      }
      v16 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0xB4,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\runtime\\DependencyMiniRepositoryWriter.inl",
              (const char *)(unsigned int)v17,
              (int)v18);
    }
    else
    {
      v16 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x9E,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\runtime\\DependencyMiniRepositoryWriter.inl",
              v15);
    }
    LastError = v16;
LABEL_24:
    CloseHandle(FileW);
    return LastError;
  }
  if ( (FileAttributesW & 6) != 0 )
  {
    if ( SetFileAttributesW(a4, FileAttributesW & 0xFFFFFFF9) )
    {
      v14 = (char *)CreateFileW(a4, 0x40000000u, 0, 0, 2u, 0x8000000u, 0);
      if ( FileW != v14 )
      {
        if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(FileW);
        FileW = v14;
      }
    }
    goto LABEL_16;
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return 2147942405LL;
}

```

## disassembly

```asm
0x180022e94  push    rbx
0x180022e96  push    rbp
0x180022e97  push    rsi
0x180022e98  push    rdi
0x180022e99  sub     rsp, 58h
0x180022e9d  mov     rdi, r9
0x180022ea0  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180022ea9  mov     rsi, r8
0x180022eac  mov     [rsp+78h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180022eb4  mov     ebp, edx
0x180022eb6  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x180022ebe  mov     rcx, rdi; lpFileName
0x180022ec1  xor     r9d, r9d; lpSecurityAttributes
0x180022ec4  xor     r8d, r8d; dwShareMode
0x180022ec7  mov     edx, 40000000h; dwDesiredAccess
0x180022ecc  call    cs:__imp_CreateFileW
0x180022ed2  mov     rbx, rax
0x180022ed5  inc     rax
0x180022ed8  test    rax, 0FFFFFFFFFFFFFFFEh
0x180022ede  jnz     loc_180022FBC
0x180022ee4  call    cs:__imp_GetLastError
0x180022eea  cmp     eax, 5
0x180022eed  jz      short loc_180022F1A
0x180022eef  mov     edx, 85h; void *
0x180022ef4  mov     rcx, [rsp+78h]; this
0x180022ef9  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180022f00  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180022f05  lea     rcx, [rbx-1]
0x180022f09  mov     edi, eax
0x180022f0b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180022f0f  jbe     loc_18002304B
0x180022f15  jmp     loc_180023054
0x180022f1a  mov     rcx, rdi; lpFileName
0x180022f1d  call    cs:__imp_GetFileAttributesW
0x180022f23  cmp     eax, 0FFFFFFFFh
0x180022f26  jz      short loc_180022FA6
0x180022f28  test    al, 6
0x180022f2a  jnz     short loc_180022F49
0x180022f2c  lea     rax, [rbx-1]
0x180022f30  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180022f34  ja      short loc_180022F3F
0x180022f36  mov     rcx, rbx; hObject
0x180022f39  call    cs:__imp_CloseHandle
0x180022f3f  mov     eax, 80070005h
0x180022f44  jmp     loc_180023056
0x180022f49  and     eax, 0FFFFFFF9h
0x180022f4c  mov     rcx, rdi; lpFileName
0x180022f4f  mov     edx, eax; dwFileAttributes
0x180022f51  call    cs:__imp_SetFileAttributesW
0x180022f57  test    eax, eax
0x180022f59  jz      short loc_180022FA6
0x180022f5b  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180022f64  xor     r9d, r9d; lpSecurityAttributes
0x180022f67  mov     [rsp+78h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180022f6f  xor     r8d, r8d; dwShareMode
0x180022f72  mov     edx, 40000000h; dwDesiredAccess
0x180022f77  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x180022f7f  mov     rcx, rdi; lpFileName
0x180022f82  call    cs:__imp_CreateFileW
0x180022f88  mov     rdi, rax
0x180022f8b  cmp     rbx, rax
0x180022f8e  jz      short loc_180022FA6
0x180022f90  lea     rcx, [rbx-1]
0x180022f94  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180022f98  ja      short loc_180022FA3
0x180022f9a  mov     rcx, rbx; hObject
0x180022f9d  call    cs:__imp_CloseHandle
0x180022fa3  mov     rbx, rdi
0x180022fa6  lea     rax, [rbx+1]
0x180022faa  test    rax, 0FFFFFFFFFFFFFFFEh
0x180022fb0  jnz     short loc_180022FBC
0x180022fb2  mov     edx, 9Bh
0x180022fb7  jmp     loc_180022EF4
0x180022fbc  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180022fc4  mov     [rsp+78h+NumberOfBytesWritten], 0
0x180022fcf  mov     r8d, ebp; nNumberOfBytesToWrite
0x180022fd2  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOverlapped
0x180022fdb  mov     rdx, rsi; lpBuffer
0x180022fde  mov     rcx, rbx; hFile
0x180022fe1  call    cs:__imp_WriteFile
0x180022fe7  test    eax, eax
0x180022fe9  jnz     short loc_180023003
0x180022feb  mov     rcx, [rsp+78h]; this
0x180022ff0  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180022ff7  mov     edx, 9Eh; void *
0x180022ffc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023001  jmp     short loc_180023045
0x180023003  xor     r9d, r9d
0x180023006  lea     rax, [rsp+78h+var_38]
0x18002300b  xorps   xmm0, xmm0
0x18002300e  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; int
0x180023013  xor     r8d, r8d
0x180023016  mov     rcx, rbx
0x180023019  movups  xmmword ptr [rsp+78h+var_38], xmm0
0x18002301e  lea     edx, [r9+1]
0x180023022  call    cs:__imp_ZwFlushBuffersFileEx
0x180023028  test    eax, eax
0x18002302a  jns     short loc_180023049
0x18002302c  mov     rcx, [rsp+78h]; this
0x180023031  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180023038  mov     r9d, eax; char *
0x18002303b  mov     edx, 0B4h; void *
0x180023040  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180023045  mov     edi, eax
0x180023047  jmp     short loc_18002304B
0x180023049  xor     edi, edi
0x18002304b  mov     rcx, rbx; hObject
0x18002304e  call    cs:__imp_CloseHandle
0x180023054  mov     eax, edi
0x180023056  add     rsp, 58h
0x18002305a  pop     rdi
0x18002305b  pop     rsi
0x18002305c  pop     rbp
0x18002305d  pop     rbx
0x18002305e  retn
```
