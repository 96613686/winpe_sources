# OpenRegistryKey

- ea: `0x18000f940`
- end: `0x18000fa2c`
- name: `OpenRegistryKey`
- size: `236`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000f550`
- `0x180017cb0`
- `0x180018340`
- `0x180018718`

## callees

- `0x18000f940`
- `0x1800174d8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000f9bc`
- `KERNEL32!SetLastError` at `0x18000f9e6`
- `KERNEL32!SetLastError` at `0x18000f9bc`
- `KERNEL32!SetLastError` at `0x18000f9e6`
- `ADVAPI32!RegCreateKeyExW` at `0x18000f99a`
- `ADVAPI32!RegCreateKeyExW` at `0x18000f99a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fa11`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fa11`

## string_xrefs

- `0x18000f9ac`: `RegCreateKeyEx() failed, ec=%d`
- `0x18000f9d8`: `Created new fax registry key, ec=%d`
- `0x18000fa23`: `RegOpenKeyEx() failed, ec=%d`

## pseudocode

```c
HKEY __fastcall OpenRegistryKey(HKEY a1, const WCHAR *a2, int a3, REGSAM a4)
{
  REGSAM v5; // r9d
  unsigned int v6; // ebx
  HKEY phkResult[3]; // [rsp+50h] [rbp-18h] BYREF
  DWORD v9; // [rsp+80h] [rbp+18h] BYREF

  phkResult[0] = 0;
  v9 = 0;
  v5 = 131103;
  if ( a3 )
  {
    if ( a4 )
      v5 = a4;
    v6 = RegCreateKeyExW(a1, a2, 0, 0, 0, v5, 0, phkResult, &v9);
    if ( v6 )
    {
      fax_dprintf(L"RegCreateKeyEx() failed, ec=%d", v6);
LABEL_6:
      SetLastError(v6);
      return 0;
    }
    if ( v9 == 1 )
      fax_dprintf(L"Created new fax registry key, ec=%d", 0);
  }
  else
  {
    if ( a4 )
      v5 = a4;
    v6 = RegOpenKeyExW(a1, a2, 0, v5, phkResult);
    if ( v6 )
    {
      fax_dprintf(L"RegOpenKeyEx() failed, ec=%d", v6);
      goto LABEL_6;
    }
  }
  SetLastError(0);
  return phkResult[0];
}

```

## disassembly

```asm
0x18000f940  mov     r11, rsp
0x18000f943  push    rbx
0x18000f944  sub     rsp, 60h
0x18000f948  mov     qword ptr [r11-18h], 0
0x18000f950  mov     eax, r9d
0x18000f953  mov     dword ptr [r11+18h], 0
0x18000f95b  mov     r9d, 2001Fh
0x18000f961  test    r8d, r8d
0x18000f964  jz      loc_18000F9FE
0x18000f96a  test    eax, eax
0x18000f96c  cmovnz  r9d, eax
0x18000f970  lea     rax, [r11+18h]
0x18000f974  mov     [r11-28h], rax
0x18000f978  xor     r8d, r8d; Reserved
0x18000f97b  lea     rax, [r11-18h]
0x18000f97f  mov     [r11-30h], rax
0x18000f983  mov     qword ptr [r11-38h], 0
0x18000f98b  mov     [r11-40h], r9d
0x18000f98f  xor     r9d, r9d; lpClass
0x18000f992  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18000f99a  call    cs:__imp_RegCreateKeyExW
0x18000f9a1  nop     dword ptr [rax+rax+00h]
0x18000f9a6  mov     ebx, eax
0x18000f9a8  test    eax, eax
0x18000f9aa  jz      short loc_18000F9CC
0x18000f9ac  lea     rcx, aRegcreatekeyex; "RegCreateKeyEx() failed, ec=%d"
0x18000f9b3  mov     edx, ebx
0x18000f9b5  call    fax_dprintf
0x18000f9ba  mov     ecx, ebx; dwErrCode
0x18000f9bc  call    cs:__imp_SetLastError
0x18000f9c3  nop     dword ptr [rax+rax+00h]
0x18000f9c8  xor     eax, eax
0x18000f9ca  jmp     short loc_18000F9F7
0x18000f9cc  cmp     [rsp+68h+arg_10], 1
0x18000f9d4  jnz     short loc_18000F9E4
0x18000f9d6  xor     edx, edx
0x18000f9d8  lea     rcx, aCreatedNewFaxR; "Created new fax registry key, ec=%d"
0x18000f9df  call    fax_dprintf
0x18000f9e4  xor     ecx, ecx; dwErrCode
0x18000f9e6  call    cs:__imp_SetLastError
0x18000f9ed  nop     dword ptr [rax+rax+00h]
0x18000f9f2  mov     rax, [rsp+68h+phkResult]
0x18000f9f7  add     rsp, 60h
0x18000f9fb  pop     rbx
0x18000f9fc  retn
0x18000f9fe  test    eax, eax
0x18000fa00  cmovnz  r9d, eax; samDesired
0x18000fa04  lea     rax, [rsp+68h+phkResult]
0x18000fa09  xor     r8d, r8d; ulOptions
0x18000fa0c  mov     qword ptr [rsp+68h+dwOptions], rax; phkResult
0x18000fa11  call    cs:__imp_RegOpenKeyExW
0x18000fa18  nop     dword ptr [rax+rax+00h]
0x18000fa1d  mov     ebx, eax
0x18000fa1f  test    eax, eax
0x18000fa21  jz      short loc_18000F9E4
0x18000fa23  lea     rcx, aRegopenkeyexFa; "RegOpenKeyEx() failed, ec=%d"
0x18000fa2a  jmp     short loc_18000F9B3
```
