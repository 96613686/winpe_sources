# Csl::OfflineHive::Open(Csl::Path const &)

- ea: `0x180028fd8`
- end: `0x18002906a`
- name: `?Open@OfflineHive@Csl@@QEAAJAEBVPath@2@@Z`
- size: `146`
- prototype: `__int64 __fastcall(Csl::OfflineHive *this, LPCWSTR *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180028afc`
- `0x180029070`
- `0x180029928`

## callees

- `0x180007b2c`
- `0x180028fd8`
- `0x18002ba38`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029050`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029050`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002900e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002900e`

## string_xrefs

- `0x180029028`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::OfflineHive::Open(Csl::OfflineHive *this, LPCWSTR *a2)
{
  HANDLE FileW; // rax
  bool v4; // r8
  const char *v5; // r9
  void *v6; // rbx
  unsigned int v7; // edi
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  FileW = CreateFileW(*a2, 1u, 0, 0, 3u, 0x80u, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    return (unsigned int)wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0x6E,
                           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
                           v5);
  }
  else
  {
    v7 = Csl::OfflineHive::Open(this, FileW, v4);
    if ( v6 )
      CloseHandle(v6);
  }
  return v7;
}

```

## disassembly

```asm
0x180028fd8  mov     [rsp+arg_0], rbx
0x180028fdd  push    rdi
0x180028fde  sub     rsp, 40h
0x180028fe2  mov     rax, rdx
0x180028fe5  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180028fee  xor     r9d, r9d; lpSecurityAttributes
0x180028ff1  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180028ff9  mov     rdi, rcx
0x180028ffc  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180029004  xor     r8d, r8d; dwShareMode
0x180029007  mov     rcx, [rax]; lpFileName
0x18002900a  lea     edx, [r9+1]; dwDesiredAccess
0x18002900e  call    cs:__imp_CreateFileW
0x180029015  nop     dword ptr [rax+rax+00h]
0x18002901a  mov     rbx, rax
0x18002901d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029021  jnz     short loc_18002903B
0x180029023  mov     rcx, [rsp+48h]; this
0x180029028  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002902f  lea     edx, [rax+6Fh]; void *
0x180029032  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180029037  mov     edi, eax
0x180029039  jmp     short loc_18002905C
0x18002903b  mov     rdx, rbx; void *
0x18002903e  mov     rcx, rdi; this
0x180029041  call    ?Open@OfflineHive@Csl@@QEAAJPEAX_N@Z; Csl::OfflineHive::Open(void *,bool)
0x180029046  mov     edi, eax
0x180029048  test    rbx, rbx
0x18002904b  jz      short loc_18002905C
0x18002904d  mov     rcx, rbx; hObject
0x180029050  call    cs:__imp_CloseHandle
0x180029057  nop     dword ptr [rax+rax+00h]
0x18002905c  mov     rbx, [rsp+48h+arg_0]
0x180029061  mov     eax, edi
0x180029063  add     rsp, 40h
0x180029067  pop     rdi
0x180029068  retn
```
