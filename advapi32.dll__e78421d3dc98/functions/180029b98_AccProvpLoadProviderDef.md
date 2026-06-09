# AccProvpLoadProviderDef

- ea: `0x180029b98`
- end: `0x180029c5c`
- name: `AccProvpLoadProviderDef`
- size: `196`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002a088`

## callees

- `0x180029b98`
- `0x180029c64`
- `0x18002a2f4`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180029bfb`
- `msvcrt!wcscpy_s` at `0x180029bfb`
- `KERNELBASE!LocalAlloc` at `0x180029be4`
- `KERNELBASE!LocalAlloc` at `0x180029be4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029bc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029bc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029c2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029c2c`
- `KERNEL32!LocalFree` at `0x180029c4e`
- `KERNEL32!LocalFree` at `0x180029c4e`

## string_xrefs

- `0x180029c0a`: `ProviderPath`

## pseudocode

```c
__int64 __fastcall AccProvpLoadProviderDef(HKEY a1, const WCHAR *a2, __int64 a3)
{
  unsigned int StringFromRegistry; // edi
  __int64 v6; // rax
  rsize_t v7; // rdi
  wchar_t *v8; // rax
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  StringFromRegistry = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  if ( !StringFromRegistry )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    v7 = v6 + 1;
    v8 = (wchar_t *)LocalAlloc(0, 2 * (v6 + 1));
    *(_QWORD *)a3 = v8;
    if ( v8 )
    {
      wcscpy_s(v8, v7, a2);
      StringFromRegistry = AccProvpGetStringFromRegistry(hKey, L"ProviderPath");
      if ( StringFromRegistry )
      {
        LocalFree(*(HLOCAL *)a3);
        *(_QWORD *)a3 = 0;
        *(_DWORD *)(a3 + 28) = 0;
      }
      else
      {
        *(_DWORD *)(a3 + 28) |= 1u;
      }
    }
    else
    {
      StringFromRegistry = 8;
    }
    RegCloseKey(hKey);
    if ( !StringFromRegistry )
      return (unsigned int)AccProvpGetProviderCapabilities(a3);
  }
  return StringFromRegistry;
}

```

## disassembly

```asm
0x180029b98  push    rbx
0x180029b9a  push    rbp
0x180029b9b  push    rsi
0x180029b9c  push    rdi
0x180029b9d  sub     rsp, 38h
0x180029ba1  mov     rbx, r8
0x180029ba4  lea     rax, [rsp+58h+hKey]
0x180029ba9  xor     ebp, ebp
0x180029bab  mov     [rsp+58h+phkResult], rax; phkResult
0x180029bb0  xor     r8d, r8d; ulOptions
0x180029bb3  mov     [rsp+58h+hKey], rbp
0x180029bb8  mov     r9d, 20019h; samDesired
0x180029bbe  mov     rsi, rdx
0x180029bc1  call    cs:__imp_RegOpenKeyExW
0x180029bc7  mov     edi, eax
0x180029bc9  test    eax, eax
0x180029bcb  jnz     short loc_180029C40
0x180029bcd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029bd1  inc     rax
0x180029bd4  cmp     [rsi+rax*2], bp
0x180029bd8  jnz     short loc_180029BD1
0x180029bda  lea     rdi, [rax+1]
0x180029bde  xor     ecx, ecx; uFlags
0x180029be0  lea     rdx, [rdi+rdi]; uBytes
0x180029be4  call    cs:__imp_LocalAlloc
0x180029bea  mov     [rbx], rax
0x180029bed  test    rax, rax
0x180029bf0  jz      short loc_180029C22
0x180029bf2  mov     r8, rsi; Source
0x180029bf5  mov     rdx, rdi; SizeInWords
0x180029bf8  mov     rcx, rax; Destination
0x180029bfb  call    cs:__imp_wcscpy_s
0x180029c01  mov     rcx, [rsp+58h+hKey]; hKey
0x180029c06  lea     r8, [rbx+8]
0x180029c0a  lea     rdx, aProviderpath; "ProviderPath"
0x180029c11  call    AccProvpGetStringFromRegistry
0x180029c16  mov     edi, eax
0x180029c18  test    eax, eax
0x180029c1a  jnz     short loc_180029C4B
0x180029c1c  or      dword ptr [rbx+1Ch], 1
0x180029c20  jmp     short loc_180029C27
0x180029c22  mov     edi, 8
0x180029c27  mov     rcx, [rsp+58h+hKey]; hKey
0x180029c2c  call    cs:__imp_RegCloseKey
0x180029c32  test    edi, edi
0x180029c34  jnz     short loc_180029C40
0x180029c36  mov     rcx, rbx
0x180029c39  call    AccProvpGetProviderCapabilities
0x180029c3e  mov     edi, eax
0x180029c40  mov     eax, edi
0x180029c42  add     rsp, 38h
0x180029c46  pop     rdi
0x180029c47  pop     rsi
0x180029c48  pop     rbp
0x180029c49  pop     rbx
0x180029c4a  retn
0x180029c4b  mov     rcx, [rbx]; hMem
0x180029c4e  call    cs:__imp_LocalFree
0x180029c54  mov     [rbx], rbp
0x180029c57  mov     [rbx+1Ch], ebp
0x180029c5a  jmp     short loc_180029C27
```
