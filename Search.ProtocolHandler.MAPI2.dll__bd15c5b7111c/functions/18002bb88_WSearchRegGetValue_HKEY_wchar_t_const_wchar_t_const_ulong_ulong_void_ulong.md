# WSearchRegGetValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong *,void *,ulong *)

- ea: `0x18002bb88`
- end: `0x18002bc34`
- name: `?WSearchRegGetValue@@YAJPEAUHKEY__@@PEB_W1KPEAKPEAX2@Z`
- size: `172`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, const wchar_t *, unsigned int, unsigned int *, PVOID, LPDWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029a98`

## callees

- `0x180002300`
- `0x18002b944`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002bc09`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002bc09`

## string_xrefs

- `0x18002bbfb`: `UseLowPriorityConfiguration`

## pseudocode

```c
LSTATUS __fastcall WSearchRegGetValue(
        const wchar_t *a1,
        const wchar_t *a2,
        const wchar_t *a3,
        __int64 a4,
        unsigned int *a5,
        PVOID pvData,
        LPDWORD pcbData)
{
  bool v7; // al
  wchar_t *v8; // rdx
  unsigned int pdwType; // [rsp+20h] [rbp-248h]
  wchar_t v11[264]; // [rsp+40h] [rbp-228h] BYREF

  v7 = MapRegistryKeyPath(a1, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search", v11, pdwType);
  v8 = v11;
  if ( !v7 )
    v8 = (wchar_t *)L"SOFTWARE\\Microsoft\\Windows Search";
  return RegGetValueW(HKEY_LOCAL_MACHINE, v8, L"UseLowPriorityConfiguration", 0x10u, 0, pvData, pcbData);
}

```

## disassembly

```asm
0x18002bb88  mov     [rsp+arg_0], rbx
0x18002bb8d  mov     [rsp+arg_8], rsi
0x18002bb92  push    rdi
0x18002bb93  sub     rsp, 260h
0x18002bb9a  mov     rax, cs:__security_cookie
0x18002bba1  xor     rax, rsp
0x18002bba4  mov     [rsp+268h+var_18], rax
0x18002bbac  mov     rdi, [rsp+268h+arg_28]
0x18002bbb4  lea     rsi, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows Search"
0x18002bbbb  mov     rbx, [rsp+268h+arg_30]
0x18002bbc3  lea     r9, [rsp+268h+var_228]; wchar_t *
0x18002bbc8  mov     r8, rsi; wchar_t *
0x18002bbcb  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18002bbd2  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x18002bbd7  test    al, al
0x18002bbd9  mov     [rsp+268h+pcbData], rbx; pcbData
0x18002bbde  lea     rdx, [rsp+268h+var_228]
0x18002bbe3  mov     [rsp+268h+pvData], rdi; pvData
0x18002bbe8  cmovz   rdx, rsi; lpSubKey
0x18002bbec  mov     [rsp+268h+pdwType], 0; pdwType
0x18002bbf5  mov     r9d, 10h; dwFlags
0x18002bbfb  lea     r8, Value; "UseLowPriorityConfiguration"
0x18002bc02  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002bc09  call    cs:__imp_RegGetValueW
0x18002bc0f  mov     rcx, [rsp+268h+var_18]
0x18002bc17  xor     rcx, rsp; StackCookie
0x18002bc1a  call    __security_check_cookie
0x18002bc1f  lea     r11, [rsp+268h+var_8]
0x18002bc27  mov     rbx, [r11+10h]
0x18002bc2b  mov     rsi, [r11+18h]
0x18002bc2f  mov     rsp, r11
0x18002bc32  pop     rdi
0x18002bc33  retn
```
