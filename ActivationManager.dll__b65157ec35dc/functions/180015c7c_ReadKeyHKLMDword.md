# ReadKeyHKLMDword

- ea: `0x180015c7c`
- end: `0x180015d26`
- name: `ReadKeyHKLMDword`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800153e0`

## callees

- `0x180015c7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015d13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015d13`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015d08`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015d08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015cd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015cd8`

## string_xrefs

- `0x180015cc8`: `System\ActivationBroker`

## pseudocode

```c
__int64 __fastcall ReadKeyHKLMDword(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  unsigned int v5; // ebx
  HKEY hkey; // [rsp+58h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp+18h] BYREF

  hkey = 0;
  pcbData = 4;
  if ( a4 )
  {
    *a4 = 5000;
    v5 = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\ActivationBroker", 0, 0x20019u, &hkey) )
    {
      RegGetValueW(hkey, 0, L"AsyncWaitTimeout", 0x10u, 0, a4, &pcbData);
      RegCloseKey(hkey);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x180015c7c  mov     rax, rsp
0x180015c7f  mov     [rax+8], rbx
0x180015c83  mov     [rax+18h], r8d
0x180015c87  mov     [rax+10h], rdx
0x180015c8b  push    rdi
0x180015c8c  sub     rsp, 40h
0x180015c90  mov     qword ptr [rax+10h], 0
0x180015c98  mov     rdi, r9
0x180015c9b  mov     dword ptr [rax+18h], 4
0x180015ca2  test    r9, r9
0x180015ca5  jnz     short loc_180015CAE
0x180015ca7  mov     ebx, 80070057h
0x180015cac  jmp     short loc_180015D19
0x180015cae  mov     dword ptr [r9], 1388h
0x180015cb5  lea     rax, [rsp+48h+hkey]
0x180015cba  mov     r9d, 20019h; samDesired
0x180015cc0  mov     [rsp+48h+phkResult], rax; phkResult
0x180015cc5  xor     r8d, r8d; ulOptions
0x180015cc8  lea     rdx, aSystemActivati_0; "System\\ActivationBroker"
0x180015ccf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015cd6  xor     ebx, ebx
0x180015cd8  call    cs:__imp_RegOpenKeyExW
0x180015cde  test    eax, eax
0x180015ce0  jnz     short loc_180015D19
0x180015ce2  mov     rcx, [rsp+48h+hkey]; hkey
0x180015ce7  lea     rax, [rsp+48h+arg_10]
0x180015cec  mov     [rsp+48h+pcbData], rax; pcbData
0x180015cf1  lea     r9d, [rbx+10h]; dwFlags
0x180015cf5  mov     [rsp+48h+pvData], rdi; pvData
0x180015cfa  lea     r8, aAsyncwaittimeo; "AsyncWaitTimeout"
0x180015d01  xor     edx, edx; lpSubKey
0x180015d03  mov     [rsp+48h+phkResult], rbx; pdwType
0x180015d08  call    cs:__imp_RegGetValueW
0x180015d0e  mov     rcx, [rsp+48h+hkey]; hKey
0x180015d13  call    cs:__imp_RegCloseKey
0x180015d19  mov     eax, ebx
0x180015d1b  mov     rbx, [rsp+48h+arg_0]
0x180015d20  add     rsp, 40h
0x180015d24  pop     rdi
0x180015d25  retn
```
