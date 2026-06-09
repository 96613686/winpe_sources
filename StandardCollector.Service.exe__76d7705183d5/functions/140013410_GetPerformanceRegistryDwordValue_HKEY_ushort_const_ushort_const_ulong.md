# GetPerformanceRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong &)

- ea: `0x140013410`
- end: `0x1400134ac`
- name: `?GetPerformanceRegistryDwordValue@@YAJPEAUHKEY__@@PEBG1AEAK@Z`
- size: `156`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140013270`
- `0x1400134ac`

## callees

- `0x140013360`
- `0x140013410`
- `0x1400137e0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140013476`
- `ADVAPI32!RegQueryValueExW` at `0x140013476`
- `ADVAPI32!RegCloseKey` at `0x140013483`
- `ADVAPI32!RegCloseKey` at `0x140013483`

## pseudocode

```c
__int64 __fastcall GetPerformanceRegistryDwordValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *a4)
{
  __int64 result; // rax
  unsigned int v7; // ebx
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  DWORD Type; // [rsp+38h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-2Ch] BYREF

  hKey = 0;
  result = GetPerformanceRegKey(a1, a2, &hKey);
  if ( !(_DWORD)result )
  {
    if ( hKey )
    {
      Type = 0;
      cbData = 4;
      v7 = RegQueryValueExW(hKey, a3, 0, &Type, a4, &cbData);
      RegCloseKey(hKey);
      if ( Type != 4 )
        return 13;
      return v7;
    }
    else
    {
      return 2;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140013410  push    rbx
0x140013412  push    rdi
0x140013413  sub     rsp, 58h
0x140013417  mov     rax, cs:__security_cookie
0x14001341e  xor     rax, rsp
0x140013421  mov     [rsp+68h+var_28], rax
0x140013426  and     [rsp+68h+hKey], 0
0x14001342c  mov     rbx, r8
0x14001342f  lea     r8, [rsp+68h+hKey]
0x140013434  mov     rdi, r9
0x140013437  call    GetPerformanceRegKey
0x14001343c  test    eax, eax
0x14001343e  jnz     short loc_140013498
0x140013440  mov     rcx, [rsp+68h+hKey]; hKey
0x140013445  test    rcx, rcx
0x140013448  jnz     short loc_14001344F
0x14001344a  lea     eax, [rcx+2]
0x14001344d  jmp     short loc_140013498
0x14001344f  and     [rsp+68h+Type], 0
0x140013454  lea     rax, [rsp+68h+cbData]
0x140013459  mov     [rsp+68h+lpcbData], rax; lpcbData
0x14001345e  lea     r9, [rsp+68h+Type]; lpType
0x140013463  xor     r8d, r8d; lpReserved
0x140013466  mov     [rsp+68h+lpData], rdi; lpData
0x14001346b  mov     rdx, rbx; lpValueName
0x14001346e  mov     [rsp+68h+cbData], 4
0x140013476  call    cs:__imp_RegQueryValueExW
0x14001347c  mov     rcx, [rsp+68h+hKey]; hKey
0x140013481  mov     ebx, eax
0x140013483  call    cs:__imp_RegCloseKey
0x140013489  cmp     [rsp+68h+Type], 4
0x14001348e  mov     eax, 0Dh
0x140013493  cmovnz  ebx, eax
0x140013496  mov     eax, ebx
0x140013498  mov     rcx, [rsp+68h+var_28]
0x14001349d  xor     rcx, rsp; StackCookie
0x1400134a0  call    __security_check_cookie
0x1400134a5  add     rsp, 58h
0x1400134a9  pop     rdi
0x1400134aa  pop     rbx
0x1400134ab  retn
```
