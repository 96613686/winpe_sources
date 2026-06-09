# AfxOleUnregisterClass(_GUID const &,ushort const *)

- ea: `0x1800c5460`
- end: `0x1800c5625`
- name: `?AfxOleUnregisterClass@@YAHAEBU_GUID@@PEBG@Z`
- size: `453`
- prototype: `int(const struct _GUID *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800cade0`
- `0x1800cd180`
- `0x1800ce110`

## callees

- `0x1800c5460`
- `0x1800c59e8`
- `0x1800c5a24`
- `0x1800d1fe0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1800c54d1`
- `msvcrt!swprintf_s` at `0x1800c552d`
- `msvcrt!swprintf_s` at `0x1800c556d`
- `msvcrt!swprintf_s` at `0x1800c55b2`
- `msvcrt!swprintf_s` at `0x1800c54d1`
- `msvcrt!swprintf_s` at `0x1800c552d`
- `msvcrt!swprintf_s` at `0x1800c556d`
- `msvcrt!swprintf_s` at `0x1800c55b2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c5540`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c5580`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c5540`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c5580`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c55a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c55a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5501`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5501`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c549c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c549c`

## string_xrefs

- `0x1800c55ab`: `CLSID\%s`
- `0x1800c54c6`: `CLSID\%s\%s`
- `0x1800c5521`: `CLSID\%s\%s`
- `0x1800c555d`: `CLSID\%s\%s`

## pseudocode

```c
_BOOL8 __fastcall AfxOleUnregisterClass(const struct _GUID *a1, unsigned __int16 *a2)
{
  LSTATUS v4; // eax
  int v5; // ebx
  LSTATUS v6; // eax
  BOOL v7; // ebx
  int v8; // eax
  int v9; // esi
  int v10; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Buffer[264]; // [rsp+90h] [rbp-70h] BYREF

  if ( StringFromGUID2(a1, sz, 39) != 39 )
    return 0;
  swprintf_s(Buffer, 0x104u, L"CLSID\\%s\\%s", sz, L"InprocServer");
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, Buffer, 0, 0x2000000u, &hKey) )
  {
    swprintf_s(Buffer, 0x104u, L"CLSID\\%s", sz);
    v8 = _AfxRecursiveRegDeleteKey(HKEY_CLASSES_ROOT, Buffer);
    v9 = _AfxRegDeleteKeySucceeded(v8);
    v7 = v9 != 0;
    if ( a2 )
    {
      v10 = _AfxRecursiveRegDeleteKey(HKEY_CLASSES_ROOT, a2);
      return v9 && (unsigned int)_AfxRegDeleteKeySucceeded(v10);
    }
  }
  else
  {
    swprintf_s(Buffer, 0x104u, L"CLSID\\%s\\%s", sz, L"InprocServer32");
    v4 = RegDeleteKeyExW(HKEY_CLASSES_ROOT, Buffer, 0, 0);
    v5 = _AfxRegDeleteKeySucceeded(v4);
    swprintf_s(Buffer, 0x104u, L"CLSID\\%s\\%s", sz, L"ToolboxBitmap32");
    v6 = RegDeleteKeyExW(HKEY_CLASSES_ROOT, Buffer, 0, 0);
    v7 = v5 && (unsigned int)_AfxRegDeleteKeySucceeded(v6);
    RegCloseKey(hKey);
  }
  return v7;
}

```

## disassembly

```asm
0x1800c5460  mov     [rsp-8+arg_10], rbx
0x1800c5465  mov     [rsp-8+arg_18], rsi
0x1800c546a  push    rbp
0x1800c546b  push    rdi
0x1800c546c  push    r14
0x1800c546e  lea     rbp, [rsp-1B0h]
0x1800c5476  sub     rsp, 2B0h
0x1800c547d  mov     rax, cs:__security_cookie
0x1800c5484  xor     rax, rsp
0x1800c5487  mov     [rbp+1C0h+var_20], rax
0x1800c548e  mov     rdi, rdx
0x1800c5491  mov     r8d, 27h ; '''; cchMax
0x1800c5497  lea     rdx, [rsp+2C0h+sz]; lpsz
0x1800c549c  call    cs:__imp_StringFromGUID2
0x1800c54a2  cmp     eax, 27h ; '''
0x1800c54a5  jz      short loc_1800C54AE
0x1800c54a7  xor     eax, eax
0x1800c54a9  jmp     loc_1800C55FE
0x1800c54ae  lea     rax, aInprocserver; "InprocServer"
0x1800c54b5  mov     esi, 104h
0x1800c54ba  mov     edx, esi; BufferCount
0x1800c54bc  mov     [rsp+2C0h+phkResult], rax
0x1800c54c1  lea     r9, [rsp+2C0h+sz]
0x1800c54c6  lea     r8, aClsidSS; "CLSID\\%s\\%s"
0x1800c54cd  lea     rcx, [rbp+1C0h+Buffer]; Buffer
0x1800c54d1  call    cs:__imp_swprintf_s
0x1800c54d7  lea     rax, [rsp+2C0h+hKey]
0x1800c54dc  mov     [rsp+2C0h+hKey], 0
0x1800c54e5  mov     r14, 0FFFFFFFF80000000h
0x1800c54ec  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1800c54f1  mov     rcx, r14; hKey
0x1800c54f4  lea     rdx, [rbp+1C0h+Buffer]; lpSubKey
0x1800c54f8  mov     r9d, 2000000h; samDesired
0x1800c54fe  xor     r8d, r8d; ulOptions
0x1800c5501  call    cs:__imp_RegOpenKeyExW
0x1800c5507  lea     r9, [rsp+2C0h+sz]
0x1800c550c  mov     edx, esi; BufferCount
0x1800c550e  lea     rcx, [rbp+1C0h+Buffer]; Buffer
0x1800c5512  test    eax, eax
0x1800c5514  jnz     loc_1800C55AB
0x1800c551a  lea     rax, aInprocserver32; "InprocServer32"
0x1800c5521  lea     r8, aClsidSS; "CLSID\\%s\\%s"
0x1800c5528  mov     [rsp+2C0h+phkResult], rax
0x1800c552d  call    cs:__imp_swprintf_s
0x1800c5533  xor     r9d, r9d; Reserved
0x1800c5536  lea     rdx, [rbp+1C0h+Buffer]; lpSubKey
0x1800c553a  xor     r8d, r8d; samDesired
0x1800c553d  mov     rcx, r14; hKey
0x1800c5540  call    cs:__imp_RegDeleteKeyExW
0x1800c5546  mov     ecx, eax; int
0x1800c5548  call    ?_AfxRegDeleteKeySucceeded@@YAHJ@Z; _AfxRegDeleteKeySucceeded(long)
0x1800c554d  mov     ebx, eax
0x1800c554f  lea     r9, [rsp+2C0h+sz]
0x1800c5554  lea     rax, aToolboxbitmap3; "ToolboxBitmap32"
0x1800c555b  mov     edx, esi; BufferCount
0x1800c555d  lea     r8, aClsidSS; "CLSID\\%s\\%s"
0x1800c5564  mov     [rsp+2C0h+phkResult], rax
0x1800c5569  lea     rcx, [rbp+1C0h+Buffer]; Buffer
0x1800c556d  call    cs:__imp_swprintf_s
0x1800c5573  xor     r9d, r9d; Reserved
0x1800c5576  lea     rdx, [rbp+1C0h+Buffer]; lpSubKey
0x1800c557a  xor     r8d, r8d; samDesired
0x1800c557d  mov     rcx, r14; hKey
0x1800c5580  call    cs:__imp_RegDeleteKeyExW
0x1800c5586  test    ebx, ebx
0x1800c5588  jz      short loc_1800C559C
0x1800c558a  mov     ecx, eax; int
0x1800c558c  call    ?_AfxRegDeleteKeySucceeded@@YAHJ@Z; _AfxRegDeleteKeySucceeded(long)
0x1800c5591  test    eax, eax
0x1800c5593  jz      short loc_1800C559C
0x1800c5595  mov     ebx, 1
0x1800c559a  jmp     short loc_1800C559E
0x1800c559c  xor     ebx, ebx
0x1800c559e  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800c55a3  call    cs:__imp_RegCloseKey
0x1800c55a9  jmp     short loc_1800C55FC
0x1800c55ab  lea     r8, aClsidS; "CLSID\\%s"
0x1800c55b2  call    cs:__imp_swprintf_s
0x1800c55b8  lea     rdx, [rbp+1C0h+Buffer]; unsigned __int16 *
0x1800c55bc  mov     rcx, r14; HKEY
0x1800c55bf  call    ?_AfxRecursiveRegDeleteKey@@YAJPEAUHKEY__@@PEAG@Z; _AfxRecursiveRegDeleteKey(HKEY__ *,ushort *)
0x1800c55c4  mov     ecx, eax; int
0x1800c55c6  call    ?_AfxRegDeleteKeySucceeded@@YAHJ@Z; _AfxRegDeleteKeySucceeded(long)
0x1800c55cb  xor     ebx, ebx
0x1800c55cd  mov     esi, eax
0x1800c55cf  test    eax, eax
0x1800c55d1  setnz   bl
0x1800c55d4  test    rdi, rdi
0x1800c55d7  jz      short loc_1800C55FC
0x1800c55d9  mov     rdx, rdi; unsigned __int16 *
0x1800c55dc  mov     rcx, r14; HKEY
0x1800c55df  call    ?_AfxRecursiveRegDeleteKey@@YAJPEAUHKEY__@@PEAG@Z; _AfxRecursiveRegDeleteKey(HKEY__ *,ushort *)
0x1800c55e4  test    esi, esi
0x1800c55e6  jz      short loc_1800C55FA
0x1800c55e8  mov     ecx, eax; int
0x1800c55ea  call    ?_AfxRegDeleteKeySucceeded@@YAHJ@Z; _AfxRegDeleteKeySucceeded(long)
0x1800c55ef  test    eax, eax
0x1800c55f1  jz      short loc_1800C55FA
0x1800c55f3  mov     ebx, 1
0x1800c55f8  jmp     short loc_1800C55FC
0x1800c55fa  xor     ebx, ebx
0x1800c55fc  mov     eax, ebx
0x1800c55fe  mov     rcx, [rbp+1C0h+var_20]
0x1800c5605  xor     rcx, rsp; StackCookie
0x1800c5608  call    __security_check_cookie
0x1800c560d  lea     r11, [rsp+2C0h+var_10]
0x1800c5615  mov     rbx, [r11+30h]
0x1800c5619  mov     rsi, [r11+38h]
0x1800c561d  mov     rsp, r11
0x1800c5620  pop     r14
0x1800c5622  pop     rdi
0x1800c5623  pop     rbp
0x1800c5624  retn
```
