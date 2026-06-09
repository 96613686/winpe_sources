# input_profile_settings::RegOpenSessionDataKey(ulong,ulong,HKEY__ * *)

- ea: `0x18009a68c`
- end: `0x18009a76d`
- name: `?RegOpenSessionDataKey@input_profile_settings@@YAJKKPEAPEAUHKEY__@@@Z`
- size: `225`
- prototype: `int(input_profile_settings *__hidden this, unsigned int, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180099420`

## callees

- `0x180004b70`
- `0x18006c000`
- `0x18009a68c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009a6de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009a72e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009a6de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009a72e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009a748`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009a748`

## pseudocode

```c
__int64 __fastcall input_profile_settings::RegOpenSessionDataKey(
        input_profile_settings *this,
        __int64 a2,
        HKEY *a3,
        HKEY *a4)
{
  unsigned int v5; // esi
  LSTATUS v6; // eax
  signed int v7; // ebx
  LSTATUS v8; // eax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  WCHAR SubKey[8]; // [rsp+38h] [rbp-20h] BYREF

  *a3 = 0;
  v5 = (unsigned int)this;
  hKey = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\SessionData",
         0,
         8u,
         &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    v7 = StringCchPrintfW(SubKey, 8u, L"%d", v5);
    if ( v7 >= 0 )
    {
      v8 = RegOpenKeyExW(hKey, SubKey, 0, 1u, a3);
      v7 = v8;
      if ( v8 > 0 )
        v7 = (unsigned __int16)v8 | 0x80070000;
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18009a68c  mov     r11, rsp
0x18009a68f  mov     [r11+10h], rbx
0x18009a693  mov     [r11+20h], rsi
0x18009a697  push    rdi
0x18009a698  sub     rsp, 50h
0x18009a69c  mov     rax, cs:__security_cookie
0x18009a6a3  xor     rax, rsp
0x18009a6a6  mov     [rsp+58h+var_10], rax
0x18009a6ab  mov     rdi, r8
0x18009a6ae  mov     qword ptr [r8], 0
0x18009a6b5  mov     esi, ecx
0x18009a6b7  mov     qword ptr [r11-28h], 0
0x18009a6bf  lea     rax, [r11-28h]
0x18009a6c3  xor     r8d, r8d; ulOptions
0x18009a6c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009a6cd  mov     [r11-38h], rax
0x18009a6d1  mov     r9d, 8; samDesired
0x18009a6d7  lea     rdx, aSoftwareMicros_26; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18009a6de  call    cs:__imp_RegOpenKeyExW
0x18009a6e4  mov     ebx, eax
0x18009a6e6  test    eax, eax
0x18009a6e8  jle     short loc_18009A6F3
0x18009a6ea  movzx   ebx, ax
0x18009a6ed  or      ebx, 80070000h
0x18009a6f3  test    ebx, ebx
0x18009a6f5  js      short loc_18009A74E
0x18009a6f7  mov     r9d, esi
0x18009a6fa  lea     r8, aD; "%d"
0x18009a701  mov     edx, 8; unsigned __int64
0x18009a706  lea     rcx, [rsp+58h+SubKey]; unsigned __int16 *
0x18009a70b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009a710  mov     ebx, eax
0x18009a712  test    eax, eax
0x18009a714  js      short loc_18009A743
0x18009a716  mov     rcx, [rsp+58h+hKey]; hKey
0x18009a71b  lea     rdx, [rsp+58h+SubKey]; lpSubKey
0x18009a720  mov     r9d, 1; samDesired
0x18009a726  mov     [rsp+58h+phkResult], rdi; phkResult
0x18009a72b  xor     r8d, r8d; ulOptions
0x18009a72e  call    cs:__imp_RegOpenKeyExW
0x18009a734  mov     ebx, eax
0x18009a736  test    eax, eax
0x18009a738  jle     short loc_18009A743
0x18009a73a  movzx   ebx, ax
0x18009a73d  or      ebx, 80070000h
0x18009a743  mov     rcx, [rsp+58h+hKey]; hKey
0x18009a748  call    cs:__imp_RegCloseKey
0x18009a74e  mov     eax, ebx
0x18009a750  mov     rcx, [rsp+58h+var_10]
0x18009a755  xor     rcx, rsp; StackCookie
0x18009a758  call    __security_check_cookie
0x18009a75d  mov     rbx, [rsp+58h+arg_8]
0x18009a762  mov     rsi, [rsp+58h+arg_18]
0x18009a767  add     rsp, 50h
0x18009a76b  pop     rdi
0x18009a76c  retn
```
