# OpenRegistryKey

- ea: `0x140074f18`
- end: `0x140075004`
- name: `OpenRegistryKey`
- size: `236`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `54`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000d178`
- `0x14000e840`
- `0x1400200f0`
- `0x140021750`
- `0x1400240e0`
- `0x1400246b0`
- `0x140025934`
- `0x14003b300`
- `0x14004452c`
- `0x1400473f0`
- `0x140049f40`
- `0x1400513e4`
- `0x140053e5c`
- `0x140054728`
- `0x140054c5c`
- `0x140055090`
- `0x1400555f8`
- `0x14005fb50`
- `0x1400602d4`
- `0x140061e40`
- `0x140063690`
- `0x140064674`
- `0x140074084`
- `0x140074230`
- `0x140074808`
- `0x1400749a0`
- `0x140078b10`
- `0x1400791f0`
- `0x14007fb00`
- `0x1400801a4`
- `0x140080614`
- `0x1400808c0`
- `0x14008119c`
- `0x1400813e4`
- `0x1400815a0`
- `0x140081d0c`
- `0x140081de4`
- `0x140081f4c`
- `0x1400821e4`
- `0x140082538`
- `0x140082830`
- `0x140082be8`
- `0x140083048`
- `0x1400831c4`
- `0x140083420`
- `0x140083540`
- `0x140083774`
- `0x140083acc`
- `0x1400840c8`
- `0x140084350`

## callees

- `0x140074f18`
- `0x140076758`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140074fe9`
- `ADVAPI32!RegOpenKeyExW` at `0x140074fe9`
- `ADVAPI32!RegCreateKeyExW` at `0x140074f72`
- `ADVAPI32!RegCreateKeyExW` at `0x140074f72`
- `KERNEL32!SetLastError` at `0x140074f94`
- `KERNEL32!SetLastError` at `0x140074fbe`
- `KERNEL32!SetLastError` at `0x140074f94`
- `KERNEL32!SetLastError` at `0x140074fbe`

## string_xrefs

- `0x140074f84`: `RegCreateKeyEx() failed, ec=%d`
- `0x140074fb0`: `Created new fax registry key, ec=%d`
- `0x140074ffb`: `RegOpenKeyEx() failed, ec=%d`

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
0x140074f18  mov     r11, rsp
0x140074f1b  push    rbx
0x140074f1c  sub     rsp, 60h
0x140074f20  mov     qword ptr [r11-18h], 0
0x140074f28  mov     eax, r9d
0x140074f2b  mov     dword ptr [r11+18h], 0
0x140074f33  mov     r9d, 2001Fh
0x140074f39  test    r8d, r8d
0x140074f3c  jz      loc_140074FD6
0x140074f42  test    eax, eax
0x140074f44  cmovnz  r9d, eax
0x140074f48  lea     rax, [r11+18h]
0x140074f4c  mov     [r11-28h], rax
0x140074f50  xor     r8d, r8d; Reserved
0x140074f53  lea     rax, [r11-18h]
0x140074f57  mov     [r11-30h], rax
0x140074f5b  mov     qword ptr [r11-38h], 0
0x140074f63  mov     [r11-40h], r9d
0x140074f67  xor     r9d, r9d; lpClass
0x140074f6a  mov     [rsp+68h+dwOptions], 0; dwOptions
0x140074f72  call    cs:__imp_RegCreateKeyExW
0x140074f79  nop     dword ptr [rax+rax+00h]
0x140074f7e  mov     ebx, eax
0x140074f80  test    eax, eax
0x140074f82  jz      short loc_140074FA4
0x140074f84  lea     rcx, aRegcreatekeyex; "RegCreateKeyEx() failed, ec=%d"
0x140074f8b  mov     edx, ebx
0x140074f8d  call    fax_dprintf
0x140074f92  mov     ecx, ebx; dwErrCode
0x140074f94  call    cs:__imp_SetLastError
0x140074f9b  nop     dword ptr [rax+rax+00h]
0x140074fa0  xor     eax, eax
0x140074fa2  jmp     short loc_140074FCF
0x140074fa4  cmp     [rsp+68h+arg_10], 1
0x140074fac  jnz     short loc_140074FBC
0x140074fae  xor     edx, edx
0x140074fb0  lea     rcx, aCreatedNewFaxR; "Created new fax registry key, ec=%d"
0x140074fb7  call    fax_dprintf
0x140074fbc  xor     ecx, ecx; dwErrCode
0x140074fbe  call    cs:__imp_SetLastError
0x140074fc5  nop     dword ptr [rax+rax+00h]
0x140074fca  mov     rax, [rsp+68h+phkResult]
0x140074fcf  add     rsp, 60h
0x140074fd3  pop     rbx
0x140074fd4  retn
0x140074fd6  test    eax, eax
0x140074fd8  cmovnz  r9d, eax; samDesired
0x140074fdc  lea     rax, [rsp+68h+phkResult]
0x140074fe1  xor     r8d, r8d; ulOptions
0x140074fe4  mov     qword ptr [rsp+68h+dwOptions], rax; phkResult
0x140074fe9  call    cs:__imp_RegOpenKeyExW
0x140074ff0  nop     dword ptr [rax+rax+00h]
0x140074ff5  mov     ebx, eax
0x140074ff7  test    eax, eax
0x140074ff9  jz      short loc_140074FBC
0x140074ffb  lea     rcx, aRegopenkeyexFa; "RegOpenKeyEx() failed, ec=%d"
0x140075002  jmp     short loc_140074F8B
```
