# CmOpenKey(RegEntry const &,ulong)

- ea: `0x18000e800`
- end: `0x18000e87d`
- name: `?CmOpenKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z`
- size: `125`
- prototype: `HKEY(const struct RegEntry *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000e6e4`
- `0x18000ecf8`
- `0x18000edd0`

## callees

- `0x180001c0c`
- `0x18000e76c`
- `0x18000e800`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000e837`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e837`

## pseudocode

```c
HKEY __fastcall CmOpenKey(const struct RegEntry *a1, REGSAM a2)
{
  HKEY v3; // rcx
  int v4; // eax
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp+8h] BYREF

  phkResult = 0;
  v3 = hKey;
  if ( *((_QWORD *)a1 + 4) )
    v3 = (HKEY)*((_QWORD *)a1 + 4);
  v4 = RegOpenKeyExW(v3, *((LPCWSTR *)a1 + 1), 0, a2, &phkResult);
  if ( !v4 )
    return phkResult;
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  if ( *(_DWORD *)a1 == 1 )
  {
    registry_access_error::registry_access_error((registry_access_error *)pExceptionObject, v4);
    throw (registry_access_error *)pExceptionObject;
  }
  return 0;
}

```

## disassembly

```asm
0x18000e800  push    rbx
0x18000e802  sub     rsp, 50h
0x18000e806  mov     rbx, rcx
0x18000e809  mov     [rsp+58h+arg_0], 0
0x18000e812  mov     rcx, cs:hKey
0x18000e819  lea     rax, [rsp+58h+arg_0]
0x18000e81e  mov     r9d, edx; samDesired
0x18000e821  mov     [rsp+58h+phkResult], rax; phkResult
0x18000e826  cmp     qword ptr [rbx+20h], 0
0x18000e82b  mov     rdx, [rbx+8]; lpSubKey
0x18000e82f  cmovnz  rcx, [rbx+20h]; hKey
0x18000e834  xor     r8d, r8d; ulOptions
0x18000e837  call    cs:__imp_RegOpenKeyExW
0x18000e83d  test    eax, eax
0x18000e83f  jz      short loc_18000E854
0x18000e841  jle     short loc_18000E84B
0x18000e843  movzx   eax, ax
0x18000e846  or      eax, 80070000h
0x18000e84b  cmp     dword ptr [rbx], 1
0x18000e84e  jz      short loc_18000E85F
0x18000e850  xor     eax, eax
0x18000e852  jmp     short loc_18000E859
0x18000e854  mov     rax, [rsp+58h+arg_0]
0x18000e859  add     rsp, 50h
0x18000e85d  pop     rbx
0x18000e85e  retn
0x18000e85f  mov     edx, eax; int
0x18000e861  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18000e866  call    ??0registry_access_error@@QEAA@J@Z; registry_access_error::registry_access_error(long)
0x18000e86b  lea     rdx, _TI3?AVregistry_access_error@@; pThrowInfo
0x18000e872  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000e877  call    _CxxThrowException_0
```
