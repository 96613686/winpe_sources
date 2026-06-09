# EnumerateRegistryKeys

- ea: `0x18000f550`
- end: `0x18000f707`
- name: `EnumerateRegistryKeys`
- size: `439`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180018000`
- `0x180018718`

## callees

- `0x18000f128`
- `0x18000f1c8`
- `0x18000f550`
- `0x18000f940`
- `0x1800174d8`
- `0x180019010`

## import_xrefs

- `ADVAPI32!RegEnumKeyW` at `0x18000f6a5`
- `ADVAPI32!RegEnumKeyW` at `0x18000f6a5`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000f5d6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000f5d6`
- `ADVAPI32!RegCloseKey` at `0x18000f687`
- `ADVAPI32!RegCloseKey` at `0x18000f6cd`
- `ADVAPI32!RegCloseKey` at `0x18000f6f9`
- `ADVAPI32!RegCloseKey` at `0x18000f687`
- `ADVAPI32!RegCloseKey` at `0x18000f6cd`
- `ADVAPI32!RegCloseKey` at `0x18000f6f9`

## pseudocode

```c
__int64 __fastcall EnumerateRegistryKeys(
        HKEY a1,
        const WCHAR *a2,
        __int64 a3,
        unsigned int (__fastcall *a4)(HKEY, WCHAR *, _QWORD, __int64),
        __int64 a5)
{
  DWORD v6; // ebp
  WCHAR *v7; // rbx
  HKEY v8; // rax
  HKEY v9; // rdi
  unsigned int v10; // eax
  DWORD v11; // eax
  DWORD i; // edx
  HKEY v13; // rax
  HKEY v14; // rsi
  unsigned int v15; // eax
  DWORD cSubKeys; // [rsp+60h] [rbp-28h] BYREF
  DWORD cbMaxValueLen[3]; // [rsp+64h] [rbp-24h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+A0h] [rbp+18h] BYREF

  v6 = 0;
  v7 = 0;
  cbMaxSubKeyLen = 0;
  cSubKeys = 0;
  cbMaxValueLen[0] = 0;
  v8 = OpenRegistryKey(a1, a2, 0, 0x20019u);
  v9 = v8;
  if ( v8 )
  {
    v10 = RegQueryInfoKeyW(v8, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, cbMaxValueLen, 0, 0);
    if ( v10 )
    {
      fax_dprintf(L"RegQueryInfoKey() failed, ec=%d", v10);
    }
    else if ( a4(v9, 0, cSubKeys, a5) )
    {
      v11 = cbMaxSubKeyLen + 4;
      cbMaxSubKeyLen = v11;
      if ( v11 <= 0x7FFFFFFE )
      {
        v7 = (WCHAR *)pMemAlloc(2LL * (v11 + 1));
        if ( v7 )
        {
          for ( i = 0; ; i = v6 )
          {
            v15 = RegEnumKeyW(v9, i, v7, cbMaxSubKeyLen);
            if ( v15 )
              break;
            v13 = OpenRegistryKey(v9, v7, 0, 0x20019u);
            v14 = v13;
            if ( v13 )
            {
              if ( !a4(v13, v7, v6, a5) )
              {
                RegCloseKey(v14);
                goto LABEL_15;
              }
              RegCloseKey(v14);
              ++v6;
            }
          }
          if ( v15 != 259 )
            fax_dprintf(L"RegEnumKey() failed, ec=%d", v15);
        }
      }
    }
LABEL_15:
    RegCloseKey(v9);
  }
  pMemFree(v7);
  return v6;
}

```

## disassembly

```asm
0x18000f550  mov     rax, rsp
0x18000f553  mov     [rax+8], rbx
0x18000f557  mov     [rax+10h], rbp
0x18000f55b  mov     [rax+18h], r8d
0x18000f55f  push    rsi
0x18000f560  push    rdi
0x18000f561  push    r14
0x18000f563  sub     rsp, 70h
0x18000f567  mov     r14, r9
0x18000f56a  xor     ebp, ebp
0x18000f56c  xor     ebx, ebx
0x18000f56e  mov     [rax+18h], ebp
0x18000f571  mov     r9d, 20019h
0x18000f577  mov     [rax-28h], ebp
0x18000f57a  xor     r8d, r8d
0x18000f57d  mov     [rax-24h], ebx
0x18000f580  call    OpenRegistryKey
0x18000f585  mov     rdi, rax
0x18000f588  test    rax, rax
0x18000f58b  jz      loc_18000F6D9
0x18000f591  mov     [rsp+88h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18000f596  lea     rax, [rsp+88h+cbMaxValueLen]
0x18000f59b  mov     [rsp+88h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18000f5a0  xor     r9d, r9d; lpReserved
0x18000f5a3  mov     [rsp+88h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18000f5a8  xor     r8d, r8d; lpcchClass
0x18000f5ab  mov     [rsp+88h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x18000f5b0  lea     rax, [rsp+88h+cbMaxSubKeyLen]
0x18000f5b8  mov     [rsp+88h+lpcValues], rbx; lpcValues
0x18000f5bd  xor     edx, edx; lpClass
0x18000f5bf  mov     [rsp+88h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x18000f5c4  mov     rcx, rdi; hKey
0x18000f5c7  mov     [rsp+88h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000f5cc  lea     rax, [rsp+88h+cSubKeys]
0x18000f5d1  mov     [rsp+88h+lpcSubKeys], rax; lpcSubKeys
0x18000f5d6  call    cs:__imp_RegQueryInfoKeyW
0x18000f5dd  nop     dword ptr [rax+rax+00h]
0x18000f5e2  test    eax, eax
0x18000f5e4  jz      short loc_18000F5F2
0x18000f5e6  lea     rcx, aRegqueryinfoke; "RegQueryInfoKey() failed, ec=%d"
0x18000f5ed  jmp     loc_18000F6C3
0x18000f5f2  mov     r9, [rsp+88h+arg_20]
0x18000f5fa  xor     edx, edx
0x18000f5fc  mov     r8d, [rsp+88h+cSubKeys]
0x18000f601  mov     rcx, rdi
0x18000f604  mov     rax, r14
0x18000f607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f60c  test    eax, eax
0x18000f60e  jz      loc_18000F6CA
0x18000f614  mov     eax, [rsp+88h+cbMaxSubKeyLen]
0x18000f61b  add     eax, 4
0x18000f61e  mov     [rsp+88h+cbMaxSubKeyLen], eax
0x18000f625  cmp     eax, 7FFFFFFEh
0x18000f62a  ja      loc_18000F6CA
0x18000f630  lea     ecx, [rax+1]
0x18000f633  add     rcx, rcx; dwBytes
0x18000f636  call    pMemAlloc
0x18000f63b  mov     rbx, rax
0x18000f63e  test    rax, rax
0x18000f641  jz      loc_18000F6CA
0x18000f647  xor     edx, edx
0x18000f649  jmp     short loc_18000F697
0x18000f64b  mov     r9d, 20019h
0x18000f651  xor     r8d, r8d
0x18000f654  mov     rdx, rbx
0x18000f657  mov     rcx, rdi
0x18000f65a  call    OpenRegistryKey
0x18000f65f  mov     rsi, rax
0x18000f662  test    rax, rax
0x18000f665  jz      short loc_18000F695
0x18000f667  mov     r9, [rsp+88h+arg_20]
0x18000f66f  mov     rcx, rax
0x18000f672  mov     rax, r14
0x18000f675  mov     r8d, ebp
0x18000f678  mov     rdx, rbx
0x18000f67b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f680  mov     rcx, rsi; hKey
0x18000f683  test    eax, eax
0x18000f685  jz      short loc_18000F6F9
0x18000f687  call    cs:__imp_RegCloseKey
0x18000f68e  nop     dword ptr [rax+rax+00h]
0x18000f693  inc     ebp
0x18000f695  mov     edx, ebp; dwIndex
0x18000f697  mov     r9d, [rsp+88h+cbMaxSubKeyLen]; cchName
0x18000f69f  mov     r8, rbx; lpName
0x18000f6a2  mov     rcx, rdi; hKey
0x18000f6a5  call    cs:__imp_RegEnumKeyW
0x18000f6ac  nop     dword ptr [rax+rax+00h]
0x18000f6b1  test    eax, eax
0x18000f6b3  jz      short loc_18000F64B
0x18000f6b5  cmp     eax, 103h
0x18000f6ba  jz      short loc_18000F6CA
0x18000f6bc  lea     rcx, aRegenumkeyFail; "RegEnumKey() failed, ec=%d"
0x18000f6c3  mov     edx, eax
0x18000f6c5  call    fax_dprintf
0x18000f6ca  mov     rcx, rdi; hKey
0x18000f6cd  call    cs:__imp_RegCloseKey
0x18000f6d4  nop     dword ptr [rax+rax+00h]
0x18000f6d9  mov     rcx, rbx; lpMem
0x18000f6dc  call    pMemFree
0x18000f6e1  lea     r11, [rsp+88h+var_18]
0x18000f6e6  mov     eax, ebp
0x18000f6e8  mov     rbx, [r11+20h]
0x18000f6ec  mov     rbp, [r11+28h]
0x18000f6f0  mov     rsp, r11
0x18000f6f3  pop     r14
0x18000f6f5  pop     rdi
0x18000f6f6  pop     rsi
0x18000f6f7  retn
0x18000f6f9  call    cs:__imp_RegCloseKey
0x18000f700  nop     dword ptr [rax+rax+00h]
0x18000f705  jmp     short loc_18000F6CA
```
