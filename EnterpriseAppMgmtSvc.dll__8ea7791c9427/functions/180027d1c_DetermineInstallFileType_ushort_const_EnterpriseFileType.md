# DetermineInstallFileType(ushort const *,EnterpriseFileType *)

- ea: `0x180027d1c`
- end: `0x180027dba`
- name: `?DetermineInstallFileType@@YAJPEBGPEAW4EnterpriseFileType@@@Z`
- size: `158`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum EnterpriseFileType *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180017368`
- `0x18001a704`

## callees

- `0x180027d1c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180027d5f`
- `msvcrt!_wcsicmp` at `0x180027d7b`
- `msvcrt!_wcsicmp` at `0x180027d97`
- `msvcrt!_wcsicmp` at `0x180027d5f`
- `msvcrt!_wcsicmp` at `0x180027d7b`
- `msvcrt!_wcsicmp` at `0x180027d97`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180027d45`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180027d45`

## pseudocode

```c
__int64 __fastcall DetermineInstallFileType(const unsigned __int16 *a1, enum EnterpriseFileType *a2)
{
  unsigned int v3; // ebx
  const wchar_t *ExtensionW; // rax
  const wchar_t *v5; // rsi

  if ( a1 && a2 && (*(_DWORD *)a2 = 0, ExtensionW = PathFindExtensionW(a1), (v5 = ExtensionW) != 0) )
  {
    v3 = 0;
    if ( _wcsicmp(L".XAP", ExtensionW) )
    {
      if ( _wcsicmp(L".APPX", v5) )
        *(_DWORD *)a2 = (_wcsicmp(L".APPXBUNDLE", v5) != 0) + 3;
      else
        *(_DWORD *)a2 = 2;
    }
    else
    {
      *(_DWORD *)a2 = 1;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x180027d1c  mov     [rsp+arg_0], rbx
0x180027d21  mov     [rsp+arg_8], rsi
0x180027d26  push    rdi
0x180027d27  sub     rsp, 20h
0x180027d2b  mov     rdi, rdx
0x180027d2e  test    rcx, rcx
0x180027d31  jnz     short loc_180027D3A
0x180027d33  mov     ebx, 80070057h
0x180027d38  jmp     short loc_180027DA8
0x180027d3a  test    rdi, rdi
0x180027d3d  jz      short loc_180027D33
0x180027d3f  mov     dword ptr [rdx], 0
0x180027d45  call    cs:__imp_PathFindExtensionW
0x180027d4b  mov     rsi, rax
0x180027d4e  test    rax, rax
0x180027d51  jz      short loc_180027D33
0x180027d53  mov     rdx, rax; String2
0x180027d56  lea     rcx, ?XAP_EXTENSION@@3QBGB; ".XAP"
0x180027d5d  xor     ebx, ebx
0x180027d5f  call    cs:__imp__wcsicmp
0x180027d65  test    eax, eax
0x180027d67  jnz     short loc_180027D71
0x180027d69  mov     dword ptr [rdi], 1
0x180027d6f  jmp     short loc_180027DA8
0x180027d71  mov     rdx, rsi; String2
0x180027d74  lea     rcx, ?APPX_EXTENSION@@3QBGB; ".APPX"
0x180027d7b  call    cs:__imp__wcsicmp
0x180027d81  test    eax, eax
0x180027d83  jnz     short loc_180027D8D
0x180027d85  mov     dword ptr [rdi], 2
0x180027d8b  jmp     short loc_180027DA8
0x180027d8d  mov     rdx, rsi; String2
0x180027d90  lea     rcx, ?APPXBUNDLE_EXTENSION@@3QBGB; ".APPXBUNDLE"
0x180027d97  call    cs:__imp__wcsicmp
0x180027d9d  neg     eax
0x180027d9f  sbb     ecx, ecx
0x180027da1  neg     ecx
0x180027da3  add     ecx, 3
0x180027da6  mov     [rdi], ecx
0x180027da8  mov     rsi, [rsp+28h+arg_8]
0x180027dad  mov     eax, ebx
0x180027daf  mov     rbx, [rsp+28h+arg_0]
0x180027db4  add     rsp, 20h
0x180027db8  pop     rdi
0x180027db9  retn
```
