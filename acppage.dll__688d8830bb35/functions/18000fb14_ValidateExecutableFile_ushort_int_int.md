# ValidateExecutableFile(ushort *,int *,int *)

- ea: `0x18000fb14`
- end: `0x18000fc6b`
- name: `?ValidateExecutableFile@@YAHPEAGPEAH1@Z`
- size: `343`
- prototype: `__int64 __fastcall(wchar_t *String1, int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000e324`

## callees

- `0x18000fb14`
- `0x180016280`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000fbfa`
- `msvcrt!_wcsnicmp` at `0x18000fbfa`
- `msvcrt!_wcsicmp` at `0x18000fbb2`
- `msvcrt!_wcsicmp` at `0x18000fc2c`
- `msvcrt!_wcsicmp` at `0x18000fbb2`
- `msvcrt!_wcsicmp` at `0x18000fc2c`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000fbd5`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000fbd5`
- `SHLWAPI!PathFindExtensionW` at `0x18000fb8d`
- `SHLWAPI!PathFindExtensionW` at `0x18000fb8d`

## string_xrefs

- `0x18000fbce`: `%windir%\Installer\{`

## pseudocode

```c
__int64 __fastcall ValidateExecutableFile(wchar_t *String1, int *a2, int *a3)
{
  unsigned int v6; // edi
  LPWSTR ExtensionW; // rax
  LPWSTR v8; // rsi
  size_t v9; // r8
  int v10; // eax
  unsigned int v11; // ebx
  bool v12; // zf
  wchar_t *v14[4]; // [rsp+20h] [rbp-278h]
  wchar_t String2[8]; // [rsp+40h] [rbp-258h] BYREF
  wchar_t Dst[264]; // [rsp+50h] [rbp-248h] BYREF

  v14[0] = L"COM";
  *a2 = 0;
  v14[1] = L"EXE";
  *a3 = 0;
  v14[2] = L"MSI";
  v6 = 0;
  v14[3] = L"PIF";
  wcscpy(String2, L"LNK");
  ExtensionW = PathFindExtensionW(String1);
  v8 = ExtensionW;
  if ( ExtensionW && *ExtensionW )
  {
    *a2 = _wcsicmp(ExtensionW + 1, String2) == 0;
    if ( ExpandEnvironmentStringsW(L"%windir%\\Installer\\{", Dst, 0x104u) )
    {
      v9 = -1;
      do
        ++v9;
      while ( Dst[v9] );
      if ( !_wcsnicmp(String1, Dst, v9) )
        *a3 = 1;
    }
    if ( *a2 || *a3 )
      return 1;
    v10 = 1;
    v11 = 0;
    while ( 1 )
    {
      v12 = v10 == 0;
      if ( v10 <= 0 )
        break;
      v10 = _wcsicmp(v8 + 1, v14[v11++]);
      if ( v11 >= 4 )
      {
        v12 = v10 == 0;
        break;
      }
    }
    if ( v12 )
      return 1;
  }
  return v6;
}

```

## disassembly

```asm
0x18000fb14  mov     [rsp+arg_18], rbx
0x18000fb19  push    rbp
0x18000fb1a  push    rsi
0x18000fb1b  push    rdi
0x18000fb1c  push    r14
0x18000fb1e  push    r15
0x18000fb20  sub     rsp, 270h
0x18000fb27  mov     rax, cs:__security_cookie
0x18000fb2e  xor     rax, rsp
0x18000fb31  mov     [rsp+298h+var_38], rax
0x18000fb39  xor     r15d, r15d
0x18000fb3c  lea     rax, aCom; "COM"
0x18000fb43  mov     [rsp+298h+var_278], rax
0x18000fb48  mov     rbx, r8
0x18000fb4b  lea     rax, aExe; "EXE"
0x18000fb52  mov     [rdx], r15d
0x18000fb55  mov     [rsp+298h+var_270], rax
0x18000fb5a  mov     r14, rdx
0x18000fb5d  lea     rax, aMsi_0; "MSI"
0x18000fb64  mov     [r8], r15d
0x18000fb67  mov     [rsp+298h+var_268], rax
0x18000fb6c  mov     rbp, rcx
0x18000fb6f  lea     rax, aPif; "PIF"
0x18000fb76  mov     edi, r15d
0x18000fb79  mov     [rsp+298h+var_260], rax
0x18000fb7e  mov     rax, 4B004E004Ch
0x18000fb88  mov     qword ptr [rsp+298h+String2], rax
0x18000fb8d  call    cs:__imp_PathFindExtensionW
0x18000fb93  mov     rsi, rax
0x18000fb96  test    rax, rax
0x18000fb99  jz      loc_18000FC42
0x18000fb9f  cmp     [rax], r15w
0x18000fba3  jz      loc_18000FC42
0x18000fba9  lea     rdx, [rsp+298h+String2]; String2
0x18000fbae  lea     rcx, [rax+2]; String1
0x18000fbb2  call    cs:__imp__wcsicmp
0x18000fbb8  mov     ecx, r15d
0x18000fbbb  lea     rdx, [rsp+298h+Dst]; lpDst
0x18000fbc0  test    eax, eax
0x18000fbc2  mov     r8d, 104h; nSize
0x18000fbc8  setz    cl
0x18000fbcb  mov     [r14], ecx
0x18000fbce  lea     rcx, Src; "%windir%\\Installer\\{"
0x18000fbd5  call    cs:__imp_ExpandEnvironmentStringsW
0x18000fbdb  test    eax, eax
0x18000fbdd  jz      short loc_18000FC0A
0x18000fbdf  lea     rax, [rsp+298h+Dst]
0x18000fbe4  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000fbe8  inc     r8; MaxCount
0x18000fbeb  cmp     [rax+r8*2], r15w
0x18000fbf0  jnz     short loc_18000FBE8
0x18000fbf2  lea     rdx, [rsp+298h+Dst]; String2
0x18000fbf7  mov     rcx, rbp; String1
0x18000fbfa  call    cs:__imp__wcsnicmp
0x18000fc00  test    eax, eax
0x18000fc02  jnz     short loc_18000FC0A
0x18000fc04  mov     dword ptr [rbx], 1
0x18000fc0a  cmp     [r14], r15d
0x18000fc0d  jnz     short loc_18000FC3D
0x18000fc0f  cmp     [rbx], r15d
0x18000fc12  jnz     short loc_18000FC3D
0x18000fc14  mov     eax, 1
0x18000fc19  mov     ebx, r15d
0x18000fc1c  test    eax, eax
0x18000fc1e  jle     short loc_18000FC3B
0x18000fc20  movsxd  rdx, ebx
0x18000fc23  lea     rcx, [rsi+2]; String1
0x18000fc27  mov     rdx, [rsp+rdx*8+298h+var_278]; String2
0x18000fc2c  call    cs:__imp__wcsicmp
0x18000fc32  inc     ebx
0x18000fc34  cmp     ebx, 4
0x18000fc37  jb      short loc_18000FC1C
0x18000fc39  test    eax, eax
0x18000fc3b  jnz     short loc_18000FC42
0x18000fc3d  mov     edi, 1
0x18000fc42  mov     eax, edi
0x18000fc44  mov     rcx, [rsp+298h+var_38]
0x18000fc4c  xor     rcx, rsp; StackCookie
0x18000fc4f  call    __security_check_cookie
0x18000fc54  mov     rbx, [rsp+298h+arg_18]
0x18000fc5c  add     rsp, 270h
0x18000fc63  pop     r15
0x18000fc65  pop     r14
0x18000fc67  pop     rdi
0x18000fc68  pop     rsi
0x18000fc69  pop     rbp
0x18000fc6a  retn
```
