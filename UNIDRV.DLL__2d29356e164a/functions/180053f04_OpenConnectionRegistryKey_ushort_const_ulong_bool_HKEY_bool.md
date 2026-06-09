# OpenConnectionRegistryKey(ushort const *,ulong,bool,HKEY__ * *,bool *)

- ea: `0x180053f04`
- end: `0x180053fa4`
- name: `?OpenConnectionRegistryKey@@YAJPEBGK_NPEAPEAUHKEY__@@PEA_N@Z`
- size: `160`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, unsigned int, bool, HKEY *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004723c`

## callees

- `0x1800487e0`
- `0x1800491dc`
- `0x180051a40`
- `0x180053f04`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180053f68`
- `ADVAPI32!RegOpenKeyExW` at `0x180053f68`

## pseudocode

```c
__int64 __fastcall OpenConnectionRegistryKey(STRSAFE_LPCWSTR pszSrc, __int64 a2, __int64 a3, HKEY *a4)
{
  unsigned int v6; // r8d
  int v7; // ebx
  LSTATUS v8; // eax
  WCHAR SubKey[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(SubKey, 0, 0x208u);
  v7 = AssembleRegistrySubkey(pszSrc, SubKey, v6);
  if ( v7 >= 0 )
  {
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, a4);
    if ( v8 )
    {
      if ( v8 > 0 )
        return (unsigned __int16)v8 | 0x80070000;
      else
        return (unsigned int)v8;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180053f04  mov     [rsp+arg_8], rbx
0x180053f09  push    rdi
0x180053f0a  sub     rsp, 250h
0x180053f11  mov     rax, cs:__security_cookie
0x180053f18  xor     rax, rsp
0x180053f1b  mov     [rsp+258h+var_18], rax
0x180053f23  mov     rbx, rcx
0x180053f26  xor     edx, edx; Val
0x180053f28  lea     rcx, [rsp+258h+SubKey]; void *
0x180053f2d  mov     r8d, 208h; Size
0x180053f33  mov     rdi, r9
0x180053f36  call    memset_0
0x180053f3b  lea     rdx, [rsp+258h+SubKey]; pszDest
0x180053f40  mov     rcx, rbx; pszSrc
0x180053f43  call    ?AssembleRegistrySubkey@@YAJPEBGPEAGK@Z; AssembleRegistrySubkey(ushort const *,ushort *,ulong)
0x180053f48  mov     ebx, eax
0x180053f4a  test    eax, eax
0x180053f4c  js      short loc_180053F81
0x180053f4e  mov     r9d, 20019h; samDesired
0x180053f54  mov     [rsp+258h+phkResult], rdi; phkResult
0x180053f59  xor     r8d, r8d; ulOptions
0x180053f5c  lea     rdx, [rsp+258h+SubKey]; lpSubKey
0x180053f61  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180053f68  call    cs:__imp_RegOpenKeyExW
0x180053f6e  test    eax, eax
0x180053f70  jz      short loc_180053F81
0x180053f72  jg      short loc_180053F78
0x180053f74  mov     ebx, eax
0x180053f76  jmp     short loc_180053F81
0x180053f78  movzx   ebx, ax
0x180053f7b  or      ebx, 80070000h
0x180053f81  mov     eax, ebx
0x180053f83  mov     rcx, [rsp+258h+var_18]
0x180053f8b  xor     rcx, rsp; StackCookie
0x180053f8e  call    __security_check_cookie
0x180053f93  mov     rbx, [rsp+258h+arg_8]
0x180053f9b  add     rsp, 250h
0x180053fa2  pop     rdi
0x180053fa3  retn
```
