# IEFavResolver::IEFavResolver(void)

- ea: `0x1800169a0`
- end: `0x180016a6a`
- name: `??0IEFavResolver@@QEAA@XZ`
- size: `202`
- prototype: `IEFavResolver *__fastcall(IEFavResolver *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017ec4`

## callees

- `0x18000dc74`
- `0x180013ddc`
- `0x1800169a0`

## import_xrefs

- `iertutil!__imp_DPA_Create` at `0x180016a35`
- `iertutil!__imp_DPA_Create` at `0x180016a35`
- `edgeIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1800169b3`
- `edgeIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1800169b3`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x1800169ed`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x1800169ed`
- `ext-ms-win-shell-shell32-l1-2-1!ILCreateFromPathW` at `0x180016a26`
- `ext-ms-win-shell-shell32-l1-2-1!ILCreateFromPathW` at `0x180016a26`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetSpecialFolderLocation` at `0x1800169fe`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetSpecialFolderLocation` at `0x1800169fe`

## string_xrefs

- `0x180016a0d`: `onecoreuap\inetcore\spartan\desktopbroker\iefavresolver.cpp`
- `0x180016a4c`: `onecoreuap\inetcore\spartan\desktopbroker\iefavresolver.cpp`

## pseudocode

```c
IEFavResolver *__fastcall IEFavResolver::IEFavResolver(IEFavResolver *this)
{
  unsigned int CurrentProcessManager; // eax
  HRESULT v3; // eax
  HDPA v4; // rax
  const char *v5; // r9
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_DWORD *)this = 1;
  CurrentProcessManager = IsoGetCurrentProcessManager();
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 1) = CurrentProcessManager;
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 72) = 0;
  SHGetSpecialFolderPathW(0, (LPWSTR)this + 24, 6, 1);
  v3 = SHGetSpecialFolderLocation(0, 6, (LPITEMIDLIST *)this + 5);
  if ( v3 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\iefavresolver.cpp",
      (const char *)(unsigned int)v3,
      v7);
  *((_QWORD *)this + 4) = ILCreateFromPathW((PCWSTR)this + 24);
  v4 = DPA_Create(4);
  *((_QWORD *)this + 72) = v4;
  if ( !v4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\iefavresolver.cpp",
      v5);
  return this;
}

```

## disassembly

```asm
0x1800169a0  mov     [rsp+arg_0], rbx
0x1800169a5  push    rdi; int
0x1800169a6  sub     rsp, 20h
0x1800169aa  mov     rbx, rcx
0x1800169ad  mov     dword ptr [rcx], 1
0x1800169b3  call    cs:__imp_?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x1800169b9  mov     r9d, 1; fCreate
0x1800169bf  mov     dword ptr [rbx+8], 0
0x1800169c6  mov     [rbx+4], eax
0x1800169c9  lea     rdx, [rbx+30h]; pszPath
0x1800169cd  mov     dword ptr [rbx+10h], 0
0x1800169d4  xor     ecx, ecx; hwnd
0x1800169d6  mov     qword ptr [rbx+18h], 0
0x1800169de  lea     r8d, [r9+5]; csidl
0x1800169e2  mov     qword ptr [rbx+240h], 0
0x1800169ed  call    cs:__imp_SHGetSpecialFolderPathW
0x1800169f3  lea     r8, [rbx+28h]; ppidl
0x1800169f7  mov     edx, 6; csidl
0x1800169fc  xor     ecx, ecx; hwnd
0x1800169fe  call    cs:__imp_SHGetSpecialFolderLocation
0x180016a04  test    eax, eax
0x180016a06  jns     short loc_180016A22
0x180016a08  mov     rcx, [rsp+28h]; this
0x180016a0d  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180016a14  mov     r9d, eax; char *
0x180016a17  mov     edx, 4Bh ; 'K'; void *
0x180016a1c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180016a22  lea     rcx, [rbx+30h]; pszPath
0x180016a26  call    cs:__imp_ILCreateFromPathW
0x180016a2c  mov     ecx, 4; cItemGrow
0x180016a31  mov     [rbx+20h], rax
0x180016a35  call    cs:__imp_DPA_Create
0x180016a3b  mov     [rbx+240h], rax
0x180016a42  test    rax, rax
0x180016a45  jnz     short loc_180016A5C
0x180016a47  mov     rcx, [rsp+28h]; this
0x180016a4c  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180016a53  lea     edx, [rax+50h]; void *
0x180016a56  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180016a5c  mov     rax, rbx
0x180016a5f  mov     rbx, [rsp+28h+arg_0]
0x180016a64  add     rsp, 20h
0x180016a68  pop     rdi
0x180016a69  retn
```
