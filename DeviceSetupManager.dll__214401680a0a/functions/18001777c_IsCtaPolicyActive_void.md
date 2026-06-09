# IsCtaPolicyActive(void)

- ea: `0x18001777c`
- end: `0x180017813`
- name: `?IsCtaPolicyActive@@YA_NXZ`
- size: `151`
- prototype: `bool(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f5f4`
- `0x1800238e8`
- `0x18002c5ec`
- `0x180034180`

## callees

- `0x18001777c`
- `0x18001af70`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800177f1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800177f1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800177cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800177cd`

## string_xrefs

- `0x1800177b7`: `Software\Microsoft\Windows\CurrentVersion\DeviceAccess`

## pseudocode

```c
bool IsCtaPolicyActive(void)
{
  DWORD v1; // [rsp+40h] [rbp-28h] BYREF
  WCHAR String1[6]; // [rsp+44h] [rbp-24h] BYREF

  v1 = 6;
  return !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\DeviceAccess",
            L"ActivePolicyCode",
            2u,
            0,
            String1,
            &v1)
      && CompareStringOrdinal(String1, -1, L"zh", -1, 1) == 2;
}

```

## disassembly

```asm
0x18001777c  mov     r11, rsp
0x18001777f  sub     rsp, 68h
0x180017783  mov     rax, cs:__security_cookie
0x18001778a  xor     rax, rsp
0x18001778d  mov     [rsp+68h+var_18], rax
0x180017792  lea     rax, [r11-28h]
0x180017796  mov     [rsp+68h+var_28], 6
0x18001779e  mov     [r11-38h], rax
0x1800177a2  lea     r8, aActivepolicyco; "ActivePolicyCode"
0x1800177a9  lea     rax, [r11-24h]
0x1800177ad  mov     r9d, 2; dwFlags
0x1800177b3  mov     [r11-40h], rax
0x1800177b7  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800177be  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800177c5  mov     qword ptr [r11-48h], 0
0x1800177cd  call    cs:__imp_RegGetValueW
0x1800177d3  test    eax, eax
0x1800177d5  jnz     short loc_1800177FF
0x1800177d7  or      edx, 0FFFFFFFFh; cchCount1
0x1800177da  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x1800177e2  mov     r9d, edx; cchCount2
0x1800177e5  lea     r8, aZh; "zh"
0x1800177ec  lea     rcx, [rsp+68h+String1]; lpString1
0x1800177f1  call    cs:__imp_CompareStringOrdinal
0x1800177f7  cmp     eax, 2
0x1800177fa  setz    al
0x1800177fd  jmp     short loc_180017801
0x1800177ff  xor     al, al
0x180017801  mov     rcx, [rsp+68h+var_18]
0x180017806  xor     rcx, rsp; StackCookie
0x180017809  call    __security_check_cookie
0x18001780e  add     rsp, 68h
0x180017812  retn
```
