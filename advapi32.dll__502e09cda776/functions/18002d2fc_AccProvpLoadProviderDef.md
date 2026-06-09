# AccProvpLoadProviderDef

- ea: `0x18002d2fc`
- end: `0x18002d3e3`
- name: `AccProvpLoadProviderDef`
- size: `231`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002d8a0`

## callees

- `0x18002d2fc`
- `0x18002d3ec`
- `0x18002db08`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18002d36f`
- `msvcrt!wcscpy_s` at `0x18002d36f`
- `KERNELBASE!LocalAlloc` at `0x18002d352`
- `KERNELBASE!LocalAlloc` at `0x18002d352`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d325`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d325`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d3a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d3a6`
- `KERNEL32!LocalFree` at `0x18002d3cf`
- `KERNEL32!LocalFree` at `0x18002d3cf`

## string_xrefs

- `0x18002d384`: `ProviderPath`

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
0x18002d2fc  push    rbx
0x18002d2fe  push    rbp
0x18002d2ff  push    rsi
0x18002d300  push    rdi
0x18002d301  sub     rsp, 38h
0x18002d305  mov     rbx, r8
0x18002d308  lea     rax, [rsp+58h+hKey]
0x18002d30d  xor     ebp, ebp
0x18002d30f  mov     [rsp+58h+phkResult], rax; phkResult
0x18002d314  xor     r8d, r8d; ulOptions
0x18002d317  mov     [rsp+58h+hKey], rbp
0x18002d31c  mov     r9d, 20019h; samDesired
0x18002d322  mov     rsi, rdx
0x18002d325  call    cs:__imp_RegOpenKeyExW
0x18002d32c  nop     dword ptr [rax+rax+00h]
0x18002d331  mov     edi, eax
0x18002d333  test    eax, eax
0x18002d335  jnz     loc_18002D3C0
0x18002d33b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d33f  inc     rax
0x18002d342  cmp     [rsi+rax*2], bp
0x18002d346  jnz     short loc_18002D33F
0x18002d348  lea     rdi, [rax+1]
0x18002d34c  xor     ecx, ecx; uFlags
0x18002d34e  lea     rdx, [rdi+rdi]; uBytes
0x18002d352  call    cs:__imp_LocalAlloc
0x18002d359  nop     dword ptr [rax+rax+00h]
0x18002d35e  mov     [rbx], rax
0x18002d361  test    rax, rax
0x18002d364  jz      short loc_18002D39C
0x18002d366  mov     r8, rsi; Source
0x18002d369  mov     rdx, rdi; SizeInWords
0x18002d36c  mov     rcx, rax; Destination
0x18002d36f  call    cs:__imp_wcscpy_s
0x18002d376  nop     dword ptr [rax+rax+00h]
0x18002d37b  mov     rcx, [rsp+58h+hKey]; hKey
0x18002d380  lea     r8, [rbx+8]
0x18002d384  lea     rdx, aProviderpath; "ProviderPath"
0x18002d38b  call    AccProvpGetStringFromRegistry
0x18002d390  mov     edi, eax
0x18002d392  test    eax, eax
0x18002d394  jnz     short loc_18002D3CC
0x18002d396  or      dword ptr [rbx+1Ch], 1
0x18002d39a  jmp     short loc_18002D3A1
0x18002d39c  mov     edi, 8
0x18002d3a1  mov     rcx, [rsp+58h+hKey]; hKey
0x18002d3a6  call    cs:__imp_RegCloseKey
0x18002d3ad  nop     dword ptr [rax+rax+00h]
0x18002d3b2  test    edi, edi
0x18002d3b4  jnz     short loc_18002D3C0
0x18002d3b6  mov     rcx, rbx
0x18002d3b9  call    AccProvpGetProviderCapabilities
0x18002d3be  mov     edi, eax
0x18002d3c0  mov     eax, edi
0x18002d3c2  add     rsp, 38h
0x18002d3c6  pop     rdi
0x18002d3c7  pop     rsi
0x18002d3c8  pop     rbp
0x18002d3c9  pop     rbx
0x18002d3ca  retn
0x18002d3cc  mov     rcx, [rbx]; hMem
0x18002d3cf  call    cs:__imp_LocalFree
0x18002d3d6  nop     dword ptr [rax+rax+00h]
0x18002d3db  mov     [rbx], rbp
0x18002d3de  mov     [rbx+1Ch], ebp
0x18002d3e1  jmp     short loc_18002D3A1
```
