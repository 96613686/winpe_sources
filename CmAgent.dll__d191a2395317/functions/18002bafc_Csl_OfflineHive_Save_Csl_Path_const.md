# Csl::OfflineHive::Save(Csl::Path const &)

- ea: `0x18002bafc`
- end: `0x18002bbc2`
- name: `?Save@OfflineHive@Csl@@QEBAJAEBVPath@2@@Z`
- size: `198`
- prototype: `__int64 __fastcall(Csl::OfflineHive *this, LPCWSTR *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180028afc`
- `0x180029070`
- `0x180029928`

## callees

- `0x180007b2c`
- `0x180007b4c`
- `0x18002bafc`
- `0x18002c4e8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bba8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bba8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002bb32`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002bb32`

## string_xrefs

- `0x18002bb4c`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002bb89`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::OfflineHive::Save(Csl::OfflineHive *this, LPCWSTR *a2)
{
  HANDLE FileW; // rbx
  const char *v4; // r9
  unsigned int v6; // eax
  unsigned int v7; // edi
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  FileW = CreateFileW(*a2, 2u, 0, 0, 1u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xD7,
             (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
             v4);
  v6 = ORSaveHiveToHandle(*((_QWORD *)this + 1), (_DWORD)FileW, 10, 0, *(_BYTE *)this != 0);
  if ( v6 )
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xFE,
           (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
           (const char *)v6);
  else
    v7 = 0;
  if ( FileW )
    CloseHandle(FileW);
  return v7;
}

```

## disassembly

```asm
0x18002bafc  mov     [rsp+arg_0], rbx
0x18002bb01  push    rdi
0x18002bb02  sub     rsp, 40h
0x18002bb06  mov     rax, rdx
0x18002bb09  mov     rdi, rcx
0x18002bb0c  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18002bb15  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002bb1d  mov     [rsp+48h+dwCreationDisposition], 1; dwCreationDisposition
0x18002bb25  xor     r9d, r9d; lpSecurityAttributes
0x18002bb28  xor     r8d, r8d; dwShareMode
0x18002bb2b  lea     edx, [r9+2]; dwDesiredAccess
0x18002bb2f  mov     rcx, [rax]; lpFileName
0x18002bb32  call    cs:__imp_CreateFileW
0x18002bb39  nop     dword ptr [rax+rax+00h]
0x18002bb3e  mov     rbx, rax
0x18002bb41  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002bb45  jnz     short loc_18002BB5F
0x18002bb47  mov     rcx, [rsp+48h]; this
0x18002bb4c  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002bb53  mov     edx, 0D7h; void *
0x18002bb58  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002bb5d  jmp     short loc_18002BBB6
0x18002bb5f  xor     eax, eax
0x18002bb61  cmp     [rdi], al
0x18002bb63  setnz   al
0x18002bb66  mov     [rsp+48h+dwCreationDisposition], eax; unsigned int
0x18002bb6a  xor     r9d, r9d
0x18002bb6d  lea     r8d, [r9+0Ah]
0x18002bb71  mov     rdx, rbx
0x18002bb74  mov     rcx, [rdi+8]
0x18002bb78  call    ORSaveHiveToHandle
0x18002bb7d  test    eax, eax
0x18002bb7f  jz      short loc_18002BB9E
0x18002bb81  mov     rcx, [rsp+48h]; this
0x18002bb86  mov     r9d, eax; char *
0x18002bb89  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002bb90  mov     edx, 0FEh; void *
0x18002bb95  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002bb9a  mov     edi, eax
0x18002bb9c  jmp     short loc_18002BBA0
0x18002bb9e  xor     edi, edi
0x18002bba0  test    rbx, rbx
0x18002bba3  jz      short loc_18002BBB4
0x18002bba5  mov     rcx, rbx; hObject
0x18002bba8  call    cs:__imp_CloseHandle
0x18002bbaf  nop     dword ptr [rax+rax+00h]
0x18002bbb4  mov     eax, edi
0x18002bbb6  mov     rbx, [rsp+48h+arg_0]
0x18002bbbb  add     rsp, 40h
0x18002bbbf  pop     rdi
0x18002bbc0  retn
```
