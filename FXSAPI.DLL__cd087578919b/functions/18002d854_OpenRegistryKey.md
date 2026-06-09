# OpenRegistryKey

- ea: `0x18002d854`
- end: `0x18002d92b`
- name: `OpenRegistryKey`
- size: `215`
- prototype: `HKEY __fastcall(HKEY, const WCHAR *, int, REGSAM)`
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180028c8c`
- `0x180028ef0`
- `0x18002a650`
- `0x18002aa90`
- `0x18002c064`
- `0x18002f480`
- `0x18002f7b0`
- `0x180032688`
- `0x180032d88`
- `0x1800366d0`

## callees

- `0x18002d0e4`
- `0x18002d854`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002d8c1`
- `KERNEL32!SetLastError` at `0x18002d8eb`
- `KERNEL32!SetLastError` at `0x18002d8c1`
- `KERNEL32!SetLastError` at `0x18002d8eb`
- `ADVAPI32!RegCreateKeyExW` at `0x18002d89f`
- `ADVAPI32!RegCreateKeyExW` at `0x18002d89f`
- `ADVAPI32!RegOpenKeyExW` at `0x18002d910`
- `ADVAPI32!RegOpenKeyExW` at `0x18002d910`

## string_xrefs

- `0x18002d8b1`: `RegCreateKeyEx() failed, ec=%d`
- `0x18002d8dd`: `Created new fax registry key, ec=%d`
- `0x18002d922`: `RegOpenKeyEx() failed, ec=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HKEY __fastcall OpenRegistryKey(HKEY a1, const WCHAR *a2, int a3, REGSAM a4)
{
  unsigned int v4; // ebx
  HKEY phkResult[3]; // [rsp+50h] [rbp-18h] BYREF
  DWORD v7; // [rsp+80h] [rbp+18h] BYREF

  phkResult[0] = 0;
  v7 = 0;
  if ( a3 )
  {
    v4 = RegCreateKeyExW(a1, a2, 0, 0, 0, a4, 0, phkResult, &v7);
    if ( v4 )
    {
      fax_dprintf(L"RegCreateKeyEx() failed, ec=%d", v4);
LABEL_4:
      SetLastError(v4);
      return 0;
    }
    if ( v7 == 1 )
      fax_dprintf(L"Created new fax registry key, ec=%d", 0);
  }
  else
  {
    v4 = RegOpenKeyExW(a1, a2, 0, a4, phkResult);
    if ( v4 )
    {
      fax_dprintf(L"RegOpenKeyEx() failed, ec=%d", v4);
      goto LABEL_4;
    }
  }
  SetLastError(0);
  return phkResult[0];
}

```

## disassembly

```asm
0x18002d854  mov     r11, rsp
0x18002d857  push    rbx
0x18002d858  sub     rsp, 60h
0x18002d85c  mov     qword ptr [r11-18h], 0
0x18002d864  mov     dword ptr [r11+18h], 0
0x18002d86c  test    r8d, r8d
0x18002d86f  jz      loc_18002D903
0x18002d875  lea     rax, [r11+18h]
0x18002d879  xor     r8d, r8d; Reserved
0x18002d87c  mov     [r11-28h], rax
0x18002d880  lea     rax, [r11-18h]
0x18002d884  mov     [r11-30h], rax
0x18002d888  mov     qword ptr [r11-38h], 0
0x18002d890  mov     [r11-40h], r9d
0x18002d894  xor     r9d, r9d; lpClass
0x18002d897  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18002d89f  call    cs:__imp_RegCreateKeyExW
0x18002d8a6  nop     dword ptr [rax+rax+00h]
0x18002d8ab  mov     ebx, eax
0x18002d8ad  test    eax, eax
0x18002d8af  jz      short loc_18002D8D1
0x18002d8b1  lea     rcx, aRegcreatekeyex; "RegCreateKeyEx() failed, ec=%d"
0x18002d8b8  mov     edx, ebx
0x18002d8ba  call    fax_dprintf
0x18002d8bf  mov     ecx, ebx; dwErrCode
0x18002d8c1  call    cs:__imp_SetLastError
0x18002d8c8  nop     dword ptr [rax+rax+00h]
0x18002d8cd  xor     eax, eax
0x18002d8cf  jmp     short loc_18002D8FC
0x18002d8d1  cmp     [rsp+68h+arg_10], 1
0x18002d8d9  jnz     short loc_18002D8E9
0x18002d8db  xor     edx, edx
0x18002d8dd  lea     rcx, aCreatedNewFaxR; "Created new fax registry key, ec=%d"
0x18002d8e4  call    fax_dprintf
0x18002d8e9  xor     ecx, ecx; dwErrCode
0x18002d8eb  call    cs:__imp_SetLastError
0x18002d8f2  nop     dword ptr [rax+rax+00h]
0x18002d8f7  mov     rax, [rsp+68h+phkResult]
0x18002d8fc  add     rsp, 60h
0x18002d900  pop     rbx
0x18002d901  retn
0x18002d903  lea     rax, [rsp+68h+phkResult]
0x18002d908  xor     r8d, r8d; ulOptions
0x18002d90b  mov     qword ptr [rsp+68h+dwOptions], rax; phkResult
0x18002d910  call    cs:__imp_RegOpenKeyExW
0x18002d917  nop     dword ptr [rax+rax+00h]
0x18002d91c  mov     ebx, eax
0x18002d91e  test    eax, eax
0x18002d920  jz      short loc_18002D8E9
0x18002d922  lea     rcx, aRegopenkeyexFa; "RegOpenKeyEx() failed, ec=%d"
0x18002d929  jmp     short loc_18002D8B8
```
