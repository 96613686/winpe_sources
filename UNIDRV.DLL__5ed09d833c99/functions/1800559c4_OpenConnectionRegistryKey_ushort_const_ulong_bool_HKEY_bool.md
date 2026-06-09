# OpenConnectionRegistryKey(ushort const *,ulong,bool,HKEY__ * *,bool *)

- ea: `0x1800559c4`
- end: `0x180055a6b`
- name: `?OpenConnectionRegistryKey@@YAJPEBGK_NPEAPEAUHKEY__@@PEA_N@Z`
- size: `167`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, __int64, __int64, HKEY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004866c`

## callees

- `0x180049d00`
- `0x18004a71c`
- `0x1800532a8`
- `0x1800559c4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180055a28`
- `ADVAPI32!RegOpenKeyExW` at `0x180055a28`

## pseudocode

```c
__int64 __fastcall OpenConnectionRegistryKey(STRSAFE_LPCWSTR pszSrc, __int64 a2, __int64 a3, HKEY *a4)
{
  int v6; // ebx
  LSTATUS v7; // eax
  WCHAR SubKey[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(SubKey, 0, 0x208u);
  v6 = AssembleRegistrySubkey(pszSrc, SubKey);
  if ( v6 >= 0 )
  {
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, a4);
    if ( v7 )
    {
      if ( v7 > 0 )
        return (unsigned __int16)v7 | 0x80070000;
      else
        return (unsigned int)v7;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800559c4  mov     [rsp+arg_8], rbx
0x1800559c9  push    rdi
0x1800559ca  sub     rsp, 250h
0x1800559d1  mov     rax, cs:__security_cookie
0x1800559d8  xor     rax, rsp
0x1800559db  mov     [rsp+258h+var_18], rax
0x1800559e3  mov     rbx, rcx
0x1800559e6  xor     edx, edx; Val
0x1800559e8  lea     rcx, [rsp+258h+SubKey]; void *
0x1800559ed  mov     r8d, 208h; Size
0x1800559f3  mov     rdi, r9
0x1800559f6  call    memset_0
0x1800559fb  lea     rdx, [rsp+258h+SubKey]; pszDest
0x180055a00  mov     rcx, rbx; pszSrc
0x180055a03  call    ?AssembleRegistrySubkey@@YAJPEBGPEAGK@Z; AssembleRegistrySubkey(ushort const *,ushort *,ulong)
0x180055a08  mov     ebx, eax
0x180055a0a  test    eax, eax
0x180055a0c  js      short loc_180055A47
0x180055a0e  mov     r9d, 20019h; samDesired
0x180055a14  mov     [rsp+258h+phkResult], rdi; phkResult
0x180055a19  xor     r8d, r8d; ulOptions
0x180055a1c  lea     rdx, [rsp+258h+SubKey]; lpSubKey
0x180055a21  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180055a28  call    cs:__imp_RegOpenKeyExW
0x180055a2f  nop     dword ptr [rax+rax+00h]
0x180055a34  test    eax, eax
0x180055a36  jz      short loc_180055A47
0x180055a38  jg      short loc_180055A3E
0x180055a3a  mov     ebx, eax
0x180055a3c  jmp     short loc_180055A47
0x180055a3e  movzx   ebx, ax
0x180055a41  or      ebx, 80070000h
0x180055a47  mov     eax, ebx
0x180055a49  mov     rcx, [rsp+258h+var_18]
0x180055a51  xor     rcx, rsp; StackCookie
0x180055a54  call    __security_check_cookie
0x180055a59  mov     rbx, [rsp+258h+arg_8]
0x180055a61  add     rsp, 250h
0x180055a68  pop     rdi
0x180055a69  retn
```
