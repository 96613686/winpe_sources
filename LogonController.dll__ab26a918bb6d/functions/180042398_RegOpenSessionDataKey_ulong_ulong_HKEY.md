# RegOpenSessionDataKey(ulong,ulong,HKEY__ * *)

- ea: `0x180042398`
- end: `0x180042476`
- name: `?RegOpenSessionDataKey@@YAJKKPEAPEAUHKEY__@@@Z`
- size: `222`
- prototype: `int(unsigned int, unsigned int, HKEY *)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005c3e0`
- `0x18005ebf0`
- `0x1800606d8`
- `0x18007f4e0`
- `0x18008523c`

## callees

- `0x180004b70`
- `0x180042398`
- `0x18006c000`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800423ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042437`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800423ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042437`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042451`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042451`

## pseudocode

```c
__int64 __fastcall RegOpenSessionDataKey(unsigned int a1, REGSAM a2, HKEY *a3)
{
  LSTATUS v6; // eax
  signed int v7; // ebx
  LSTATUS v8; // eax
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  WCHAR SubKey[8]; // [rsp+38h] [rbp-30h] BYREF

  *a3 = 0;
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
    v7 = StringCchPrintfW(SubKey, 8u, L"%d", a1);
    if ( v7 >= 0 )
    {
      v8 = RegOpenKeyExW(hKey, SubKey, 0, a2, a3);
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
0x180042398  mov     r11, rsp
0x18004239b  mov     [r11+20h], rbx
0x18004239f  push    rbp
0x1800423a0  push    rsi
0x1800423a1  push    rdi
0x1800423a2  sub     rsp, 50h
0x1800423a6  mov     rax, cs:__security_cookie
0x1800423ad  xor     rax, rsp
0x1800423b0  mov     [rsp+68h+var_20], rax
0x1800423b5  mov     rdi, r8
0x1800423b8  mov     qword ptr [r8], 0
0x1800423bf  mov     esi, edx
0x1800423c1  mov     qword ptr [r11-38h], 0
0x1800423c9  mov     ebp, ecx
0x1800423cb  lea     rax, [r11-38h]
0x1800423cf  xor     r8d, r8d; ulOptions
0x1800423d2  mov     [r11-48h], rax
0x1800423d6  lea     rdx, aSoftwareMicros_26; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800423dd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800423e4  mov     r9d, 8; samDesired
0x1800423ea  call    cs:__imp_RegOpenKeyExW
0x1800423f0  mov     ebx, eax
0x1800423f2  test    eax, eax
0x1800423f4  jle     short loc_1800423FF
0x1800423f6  movzx   ebx, ax
0x1800423f9  or      ebx, 80070000h
0x1800423ff  test    ebx, ebx
0x180042401  js      short loc_180042457
0x180042403  mov     r9d, ebp
0x180042406  lea     r8, aD; "%d"
0x18004240d  mov     edx, 8; unsigned __int64
0x180042412  lea     rcx, [rsp+68h+SubKey]; unsigned __int16 *
0x180042417  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004241c  mov     ebx, eax
0x18004241e  test    eax, eax
0x180042420  js      short loc_18004244C
0x180042422  mov     rcx, [rsp+68h+hKey]; hKey
0x180042427  lea     rdx, [rsp+68h+SubKey]; lpSubKey
0x18004242c  mov     r9d, esi; samDesired
0x18004242f  mov     [rsp+68h+phkResult], rdi; phkResult
0x180042434  xor     r8d, r8d; ulOptions
0x180042437  call    cs:__imp_RegOpenKeyExW
0x18004243d  mov     ebx, eax
0x18004243f  test    eax, eax
0x180042441  jle     short loc_18004244C
0x180042443  movzx   ebx, ax
0x180042446  or      ebx, 80070000h
0x18004244c  mov     rcx, [rsp+68h+hKey]; hKey
0x180042451  call    cs:__imp_RegCloseKey
0x180042457  mov     eax, ebx
0x180042459  mov     rcx, [rsp+68h+var_20]
0x18004245e  xor     rcx, rsp; StackCookie
0x180042461  call    __security_check_cookie
0x180042466  mov     rbx, [rsp+68h+arg_18]
0x18004246e  add     rsp, 50h
0x180042472  pop     rdi
0x180042473  pop     rsi
0x180042474  pop     rbp
0x180042475  retn
```
