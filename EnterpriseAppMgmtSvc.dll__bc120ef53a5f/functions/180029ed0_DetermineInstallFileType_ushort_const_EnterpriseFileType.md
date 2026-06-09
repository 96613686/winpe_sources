# DetermineInstallFileType(ushort const *,EnterpriseFileType *)

- ea: `0x180029ed0`
- end: `0x180029f8a`
- name: `?DetermineInstallFileType@@YAJPEBGPEAW4EnterpriseFileType@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum EnterpriseFileType *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x1800180fc`
- `0x18001b9f4`

## callees

- `0x180029ed0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180029f1c`
- `msvcrt!_wcsicmp` at `0x180029f3e`
- `msvcrt!_wcsicmp` at `0x180029f60`
- `msvcrt!_wcsicmp` at `0x180029f1c`
- `msvcrt!_wcsicmp` at `0x180029f3e`
- `msvcrt!_wcsicmp` at `0x180029f60`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180029efc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180029efc`

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
0x180029ed0  mov     [rsp+arg_0], rbx
0x180029ed5  mov     [rsp+arg_8], rsi
0x180029eda  push    rdi
0x180029edb  sub     rsp, 20h
0x180029edf  mov     rdi, rdx
0x180029ee2  test    rcx, rcx
0x180029ee5  jnz     short loc_180029EF1
0x180029ee7  mov     ebx, 80070057h
0x180029eec  jmp     loc_180029F77
0x180029ef1  test    rdi, rdi
0x180029ef4  jz      short loc_180029EE7
0x180029ef6  mov     dword ptr [rdx], 0
0x180029efc  call    cs:__imp_PathFindExtensionW
0x180029f03  nop     dword ptr [rax+rax+00h]
0x180029f08  mov     rsi, rax
0x180029f0b  test    rax, rax
0x180029f0e  jz      short loc_180029EE7
0x180029f10  mov     rdx, rax; String2
0x180029f13  lea     rcx, ?XAP_EXTENSION@@3QBGB; ".XAP"
0x180029f1a  xor     ebx, ebx
0x180029f1c  call    cs:__imp__wcsicmp
0x180029f23  nop     dword ptr [rax+rax+00h]
0x180029f28  test    eax, eax
0x180029f2a  jnz     short loc_180029F34
0x180029f2c  mov     dword ptr [rdi], 1
0x180029f32  jmp     short loc_180029F77
0x180029f34  mov     rdx, rsi; String2
0x180029f37  lea     rcx, ?APPX_EXTENSION@@3QBGB; ".APPX"
0x180029f3e  call    cs:__imp__wcsicmp
0x180029f45  nop     dword ptr [rax+rax+00h]
0x180029f4a  test    eax, eax
0x180029f4c  jnz     short loc_180029F56
0x180029f4e  mov     dword ptr [rdi], 2
0x180029f54  jmp     short loc_180029F77
0x180029f56  mov     rdx, rsi; String2
0x180029f59  lea     rcx, ?APPXBUNDLE_EXTENSION@@3QBGB; ".APPXBUNDLE"
0x180029f60  call    cs:__imp__wcsicmp
0x180029f67  nop     dword ptr [rax+rax+00h]
0x180029f6c  neg     eax
0x180029f6e  sbb     ecx, ecx
0x180029f70  neg     ecx
0x180029f72  add     ecx, 3
0x180029f75  mov     [rdi], ecx
0x180029f77  mov     rsi, [rsp+28h+arg_8]
0x180029f7c  mov     eax, ebx
0x180029f7e  mov     rbx, [rsp+28h+arg_0]
0x180029f83  add     rsp, 20h
0x180029f87  pop     rdi
0x180029f88  retn
```
