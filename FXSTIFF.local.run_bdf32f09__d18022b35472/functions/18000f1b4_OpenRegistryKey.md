# OpenRegistryKey

- ea: `0x18000f1b4`
- end: `0x18000f287`
- name: `OpenRegistryKey`
- size: `211`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ee14`
- `0x180016f40`
- `0x1800175a8`
- `0x18001795c`

## callees

- `0x18000f1b4`
- `0x180016794`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000f22a`
- `KERNEL32!SetLastError` at `0x18000f24e`
- `KERNEL32!SetLastError` at `0x18000f22a`
- `KERNEL32!SetLastError` at `0x18000f24e`
- `ADVAPI32!RegCreateKeyExW` at `0x18000f20e`
- `ADVAPI32!RegCreateKeyExW` at `0x18000f20e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f272`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f272`

## string_xrefs

- `0x18000f21a`: `RegCreateKeyEx() failed, ec=%d`
- `0x18000f240`: `Created new fax registry key, ec=%d`
- `0x18000f27e`: `RegOpenKeyEx() failed, ec=%d`

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
0x18000f1b4  mov     r11, rsp
0x18000f1b7  push    rbx
0x18000f1b8  sub     rsp, 60h
0x18000f1bc  mov     qword ptr [r11-18h], 0
0x18000f1c4  mov     eax, r9d
0x18000f1c7  mov     dword ptr [r11+18h], 0
0x18000f1cf  mov     r9d, 2001Fh
0x18000f1d5  test    r8d, r8d
0x18000f1d8  jz      loc_18000F25F
0x18000f1de  test    eax, eax
0x18000f1e0  cmovnz  r9d, eax
0x18000f1e4  lea     rax, [r11+18h]
0x18000f1e8  mov     [r11-28h], rax
0x18000f1ec  xor     r8d, r8d; Reserved
0x18000f1ef  lea     rax, [r11-18h]
0x18000f1f3  mov     [r11-30h], rax
0x18000f1f7  mov     qword ptr [r11-38h], 0
0x18000f1ff  mov     [r11-40h], r9d
0x18000f203  xor     r9d, r9d; lpClass
0x18000f206  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18000f20e  call    cs:__imp_RegCreateKeyExW
0x18000f214  mov     ebx, eax
0x18000f216  test    eax, eax
0x18000f218  jz      short loc_18000F234
0x18000f21a  lea     rcx, aRegcreatekeyex; "RegCreateKeyEx() failed, ec=%d"
0x18000f221  mov     edx, ebx
0x18000f223  call    fax_dprintf
0x18000f228  mov     ecx, ebx; dwErrCode
0x18000f22a  call    cs:__imp_SetLastError
0x18000f230  xor     eax, eax
0x18000f232  jmp     short loc_18000F259
0x18000f234  cmp     [rsp+68h+arg_10], 1
0x18000f23c  jnz     short loc_18000F24C
0x18000f23e  xor     edx, edx
0x18000f240  lea     rcx, aCreatedNewFaxR; "Created new fax registry key, ec=%d"
0x18000f247  call    fax_dprintf
0x18000f24c  xor     ecx, ecx; dwErrCode
0x18000f24e  call    cs:__imp_SetLastError
0x18000f254  mov     rax, [rsp+68h+phkResult]
0x18000f259  add     rsp, 60h
0x18000f25d  pop     rbx
0x18000f25e  retn
0x18000f25f  test    eax, eax
0x18000f261  cmovnz  r9d, eax; samDesired
0x18000f265  lea     rax, [rsp+68h+phkResult]
0x18000f26a  xor     r8d, r8d; ulOptions
0x18000f26d  mov     qword ptr [rsp+68h+dwOptions], rax; phkResult
0x18000f272  call    cs:__imp_RegOpenKeyExW
0x18000f278  mov     ebx, eax
0x18000f27a  test    eax, eax
0x18000f27c  jz      short loc_18000F24C
0x18000f27e  lea     rcx, aRegopenkeyexFa; "RegOpenKeyEx() failed, ec=%d"
0x18000f285  jmp     short loc_18000F221
```
