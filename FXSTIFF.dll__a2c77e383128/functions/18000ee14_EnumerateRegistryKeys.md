# EnumerateRegistryKeys

- ea: `0x18000ee14`
- end: `0x18000efa8`
- name: `EnumerateRegistryKeys`
- size: `404`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int (__fastcall *)(__int64, WCHAR *, _QWORD, __int64), __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180017280`
- `0x18001795c`

## callees

- `0x18000ea18`
- `0x18000eac0`
- `0x18000ee14`
- `0x18000f1b4`
- `0x180016794`
- `0x180019010`

## import_xrefs

- `ADVAPI32!RegEnumKeyW` at `0x18000ef59`
- `ADVAPI32!RegEnumKeyW` at `0x18000ef59`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000ee9a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000ee9a`
- `ADVAPI32!RegCloseKey` at `0x18000ef41`
- `ADVAPI32!RegCloseKey` at `0x18000ef7b`
- `ADVAPI32!RegCloseKey` at `0x18000efa0`
- `ADVAPI32!RegCloseKey` at `0x18000ef41`
- `ADVAPI32!RegCloseKey` at `0x18000ef7b`
- `ADVAPI32!RegCloseKey` at `0x18000efa0`

## pseudocode

```c
__int64 __fastcall EnumerateRegistryKeys(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int (__fastcall *a4)(__int64, WCHAR *, _QWORD, __int64),
        __int64 a5)
{
  DWORD v6; // ebp
  WCHAR *v7; // rbx
  HKEY v8; // rax
  HKEY v9; // rdi
  unsigned int v10; // eax
  DWORD v11; // eax
  DWORD i; // edx
  __int64 v13; // rax
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
  v8 = (HKEY)OpenRegistryKey(a1, a2, 0, 131097);
  v9 = v8;
  if ( v8 )
  {
    v10 = RegQueryInfoKeyW(v8, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, cbMaxValueLen, 0, 0);
    if ( v10 )
    {
      fax_dprintf(L"RegQueryInfoKey() failed, ec=%d", v10);
    }
    else if ( a4((__int64)v9, 0, cSubKeys, a5) )
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
            v13 = OpenRegistryKey(v9, v7, 0, 131097);
            v14 = (HKEY)v13;
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
0x18000ee14  mov     rax, rsp
0x18000ee17  mov     [rax+8], rbx
0x18000ee1b  mov     [rax+10h], rbp
0x18000ee1f  mov     [rax+18h], r8d
0x18000ee23  push    rsi
0x18000ee24  push    rdi
0x18000ee25  push    r14
0x18000ee27  sub     rsp, 70h
0x18000ee2b  mov     r14, r9
0x18000ee2e  xor     ebp, ebp
0x18000ee30  xor     ebx, ebx
0x18000ee32  mov     [rax+18h], ebp
0x18000ee35  mov     r9d, 20019h
0x18000ee3b  mov     [rax-28h], ebp
0x18000ee3e  xor     r8d, r8d
0x18000ee41  mov     [rax-24h], ebx
0x18000ee44  call    OpenRegistryKey
0x18000ee49  mov     rdi, rax
0x18000ee4c  test    rax, rax
0x18000ee4f  jz      loc_18000EF81
0x18000ee55  mov     [rsp+88h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18000ee5a  lea     rax, [rsp+88h+cbMaxValueLen]
0x18000ee5f  mov     [rsp+88h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18000ee64  xor     r9d, r9d; lpReserved
0x18000ee67  mov     [rsp+88h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18000ee6c  xor     r8d, r8d; lpcchClass
0x18000ee6f  mov     [rsp+88h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x18000ee74  lea     rax, [rsp+88h+cbMaxSubKeyLen]
0x18000ee7c  mov     [rsp+88h+lpcValues], rbx; lpcValues
0x18000ee81  xor     edx, edx; lpClass
0x18000ee83  mov     [rsp+88h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x18000ee88  mov     rcx, rdi; hKey
0x18000ee8b  mov     [rsp+88h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000ee90  lea     rax, [rsp+88h+cSubKeys]
0x18000ee95  mov     [rsp+88h+lpcSubKeys], rax; lpcSubKeys
0x18000ee9a  call    cs:__imp_RegQueryInfoKeyW
0x18000eea0  test    eax, eax
0x18000eea2  jz      short loc_18000EEB0
0x18000eea4  lea     rcx, aRegqueryinfoke; "RegQueryInfoKey() failed, ec=%d"
0x18000eeab  jmp     loc_18000EF71
0x18000eeb0  mov     r9, [rsp+88h+arg_20]
0x18000eeb8  xor     edx, edx
0x18000eeba  mov     r8d, [rsp+88h+cSubKeys]
0x18000eebf  mov     rcx, rdi
0x18000eec2  mov     rax, r14
0x18000eec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eeca  test    eax, eax
0x18000eecc  jz      loc_18000EF78
0x18000eed2  mov     eax, [rsp+88h+cbMaxSubKeyLen]
0x18000eed9  add     eax, 4
0x18000eedc  mov     [rsp+88h+cbMaxSubKeyLen], eax
0x18000eee3  cmp     eax, 7FFFFFFEh
0x18000eee8  ja      loc_18000EF78
0x18000eeee  lea     ecx, [rax+1]
0x18000eef1  add     rcx, rcx; dwBytes
0x18000eef4  call    pMemAlloc
0x18000eef9  mov     rbx, rax
0x18000eefc  test    rax, rax
0x18000eeff  jz      short loc_18000EF78
0x18000ef01  xor     edx, edx
0x18000ef03  jmp     short loc_18000EF4B
0x18000ef05  mov     r9d, 20019h
0x18000ef0b  xor     r8d, r8d
0x18000ef0e  mov     rdx, rbx
0x18000ef11  mov     rcx, rdi
0x18000ef14  call    OpenRegistryKey
0x18000ef19  mov     rsi, rax
0x18000ef1c  test    rax, rax
0x18000ef1f  jz      short loc_18000EF49
0x18000ef21  mov     r9, [rsp+88h+arg_20]
0x18000ef29  mov     rcx, rax
0x18000ef2c  mov     rax, r14
0x18000ef2f  mov     r8d, ebp
0x18000ef32  mov     rdx, rbx
0x18000ef35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef3a  mov     rcx, rsi; hKey
0x18000ef3d  test    eax, eax
0x18000ef3f  jz      short loc_18000EFA0
0x18000ef41  call    cs:__imp_RegCloseKey
0x18000ef47  inc     ebp
0x18000ef49  mov     edx, ebp; dwIndex
0x18000ef4b  mov     r9d, [rsp+88h+cbMaxSubKeyLen]; cchName
0x18000ef53  mov     r8, rbx; lpName
0x18000ef56  mov     rcx, rdi; hKey
0x18000ef59  call    cs:__imp_RegEnumKeyW
0x18000ef5f  test    eax, eax
0x18000ef61  jz      short loc_18000EF05
0x18000ef63  cmp     eax, 103h
0x18000ef68  jz      short loc_18000EF78
0x18000ef6a  lea     rcx, aRegenumkeyFail; "RegEnumKey() failed, ec=%d"
0x18000ef71  mov     edx, eax
0x18000ef73  call    fax_dprintf
0x18000ef78  mov     rcx, rdi; hKey
0x18000ef7b  call    cs:__imp_RegCloseKey
0x18000ef81  mov     rcx, rbx; lpMem
0x18000ef84  call    pMemFree
0x18000ef89  lea     r11, [rsp+88h+var_18]
0x18000ef8e  mov     eax, ebp
0x18000ef90  mov     rbx, [r11+20h]
0x18000ef94  mov     rbp, [r11+28h]
0x18000ef98  mov     rsp, r11
0x18000ef9b  pop     r14
0x18000ef9d  pop     rdi
0x18000ef9e  pop     rsi
0x18000ef9f  retn
0x18000efa0  call    cs:__imp_RegCloseKey
0x18000efa6  jmp     short loc_18000EF78
```
