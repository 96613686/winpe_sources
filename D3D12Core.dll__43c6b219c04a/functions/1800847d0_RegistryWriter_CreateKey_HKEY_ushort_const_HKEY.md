# RegistryWriter::CreateKey(HKEY__ *,ushort const *,HKEY__ * *)

- ea: `0x1800847d0`
- end: `0x180084876`
- name: `?CreateKey@RegistryWriter@@QEAAJPEAUHKEY__@@PEBGPEAPEAU2@@Z`
- size: `166`
- prototype: `int(RegistryWriter *__hidden this, HKEY, const unsigned __int16 *, HKEY *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180084fa4`
- `0x1800b6d10`
- `0x18012bd30`

## callees

- `0x1800847d0`
- `0x180085d84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180084852`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180084852`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180084817`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180084817`

## pseudocode

```c
__int64 __fastcall RegistryWriter::CreateKey(HANDLE *this, HKEY a2, const unsigned __int16 *a3, HKEY *phkResult)
{
  LSTATUS Key; // eax
  int v6; // ebx

  if ( *((_BYTE *)this + 8) )
  {
    RegCreateKeyTransactedW(a2, a3, 0, 0, 0, 0xC0030100, 0, phkResult, 0, *this, 0);
    return 0;
  }
  Key = RegCreateKeyExW(a2, a3, 0, 0, 0, 0xC0030100, 0, phkResult, 0);
  v6 = Key;
  if ( !Key )
    return 0;
  RegistryError(Key);
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800847d0  push    rbx
0x1800847d2  sub     rsp, 60h
0x1800847d6  mov     r10, r8
0x1800847d9  mov     r11, rdx
0x1800847dc  xor     r8d, r8d; Reserved
0x1800847df  mov     rdx, r10; lpSubKey
0x1800847e2  cmp     [rcx+8], r8b
0x1800847e6  jz      short loc_180084825
0x1800847e8  mov     rax, [rcx]
0x1800847eb  mov     rcx, r11; hKey
0x1800847ee  mov     [rsp+68h+pExtendedParemeter], r8; pExtendedParemeter
0x1800847f3  mov     [rsp+68h+hTransaction], rax; hTransaction
0x1800847f8  mov     [rsp+68h+lpdwDisposition], r8; lpdwDisposition
0x1800847fd  mov     [rsp+68h+phkResult], r9; phkResult
0x180084802  xor     r9d, r9d; lpClass
0x180084805  mov     [rsp+68h+lpSecurityAttributes], r8; lpSecurityAttributes
0x18008480a  mov     [rsp+68h+samDesired], 0C0030100h; samDesired
0x180084812  mov     [rsp+68h+dwOptions], r8d; dwOptions
0x180084817  call    cs:__imp_RegCreateKeyTransactedW
0x18008481d  xor     eax, eax
0x18008481f  add     rsp, 60h
0x180084823  pop     rbx
0x180084824  retn
0x180084825  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x18008482e  mov     rcx, r11; hKey
0x180084831  mov     [rsp+68h+phkResult], r9; phkResult
0x180084836  xor     r9d, r9d; lpClass
0x180084839  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180084842  mov     [rsp+68h+samDesired], 0C0030100h; samDesired
0x18008484a  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180084852  call    cs:__imp_RegCreateKeyExW
0x180084858  mov     ebx, eax
0x18008485a  test    eax, eax
0x18008485c  jz      short loc_18008481D
0x18008485e  mov     ecx, eax; int
0x180084860  call    ?RegistryError@@YAXJ@Z; RegistryError(long)
0x180084865  test    ebx, ebx
0x180084867  jle     short loc_180084872
0x180084869  movzx   ebx, bx
0x18008486c  or      ebx, 80070000h
0x180084872  mov     eax, ebx
0x180084874  jmp     short loc_18008481F
```
