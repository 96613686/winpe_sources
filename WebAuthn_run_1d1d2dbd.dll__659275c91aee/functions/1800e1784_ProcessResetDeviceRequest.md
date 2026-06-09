# ProcessResetDeviceRequest

- ea: `0x1800e1784`
- end: `0x1800e1845`
- name: `ProcessResetDeviceRequest`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e2880`

## callees

- `0x1800dff80`
- `0x1800e1784`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800e17d4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800e17ef`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800e180a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800e17d4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800e17ef`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800e180a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e17b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e17b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e1825`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e1825`

## pseudocode

```c
__int64 ProcessResetDeviceRequest()
{
  LSTATUS v0; // eax
  unsigned int v1; // ebx
  LSTATUS v2; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\CtapTest", 0, 0x2011Fu, &hKey);
  if ( v0 )
  {
    v1 = 0;
    if ( v0 != 2 )
      v1 = v0;
  }
  else
  {
    v1 = RegDeleteValueA(hKey, "ClientPin");
    if ( (v1 & 0xFFFFFFFD) == 0 )
    {
      v1 = RegDeleteValueA(hKey, "InvalidCount");
      if ( (v1 & 0xFFFFFFFD) == 0 )
      {
        v2 = RegDeleteValueA(hKey, "SignCount");
        v1 = (v2 & 0xFFFFFFFD) != 0 ? v2 : 0;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v1 )
    PrintError("ProcessResetDeviceRequest", v1);
  return v1;
}

```

## disassembly

```asm
0x1800e1784  push    rbx
0x1800e1786  sub     rsp, 30h
0x1800e178a  lea     rax, [rsp+38h+hKey]
0x1800e178f  mov     [rsp+38h+hKey], 0
0x1800e1798  mov     r9d, 2011Fh; samDesired
0x1800e179e  mov     [rsp+38h+phkResult], rax; phkResult
0x1800e17a3  xor     r8d, r8d; ulOptions
0x1800e17a6  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\CtapTest"
0x1800e17ad  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800e17b4  call    cs:__imp_RegOpenKeyExW
0x1800e17ba  test    eax, eax
0x1800e17bc  jz      short loc_1800E17C8
0x1800e17be  xor     ebx, ebx
0x1800e17c0  cmp     eax, 2
0x1800e17c3  cmovnz  ebx, eax
0x1800e17c6  jmp     short loc_1800E181B
0x1800e17c8  mov     rcx, [rsp+38h+hKey]; hKey
0x1800e17cd  lea     rdx, aClientpin; "ClientPin"
0x1800e17d4  call    cs:__imp_RegDeleteValueA
0x1800e17da  mov     ebx, eax
0x1800e17dc  test    eax, 0FFFFFFFDh
0x1800e17e1  jnz     short loc_1800E181B
0x1800e17e3  mov     rcx, [rsp+38h+hKey]; hKey
0x1800e17e8  lea     rdx, aInvalidcount; "InvalidCount"
0x1800e17ef  call    cs:__imp_RegDeleteValueA
0x1800e17f5  mov     ebx, eax
0x1800e17f7  test    eax, 0FFFFFFFDh
0x1800e17fc  jnz     short loc_1800E181B
0x1800e17fe  mov     rcx, [rsp+38h+hKey]; hKey
0x1800e1803  lea     rdx, aSigncount; "SignCount"
0x1800e180a  call    cs:__imp_RegDeleteValueA
0x1800e1810  mov     ecx, eax
0x1800e1812  and     ecx, 0FFFFFFFDh
0x1800e1815  neg     ecx
0x1800e1817  sbb     ebx, ebx
0x1800e1819  and     ebx, eax
0x1800e181b  mov     rcx, [rsp+38h+hKey]; hKey
0x1800e1820  test    rcx, rcx
0x1800e1823  jz      short loc_1800E182B
0x1800e1825  call    cs:__imp_RegCloseKey
0x1800e182b  test    ebx, ebx
0x1800e182d  jz      short loc_1800E183D
0x1800e182f  mov     edx, ebx; dwErrId
0x1800e1831  lea     rcx, aProcessresetde; "ProcessResetDeviceRequest"
0x1800e1838  call    PrintError
0x1800e183d  mov     eax, ebx
0x1800e183f  add     rsp, 30h
0x1800e1843  pop     rbx
0x1800e1844  retn
```
