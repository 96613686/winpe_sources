# RequiredLanguageFeaturesInstaller::DefaultIsMixedRealityConfigured(void)

- ea: `0x180015a60`
- end: `0x180015ae2`
- name: `?DefaultIsMixedRealityConfigured@RequiredLanguageFeaturesInstaller@@CA_NXZ`
- size: `130`
- prototype: `bool(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180003520`
- `0x180015a60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015abc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015abc`

## pseudocode

```c
bool RequiredLanguageFeaturesInstaller::DefaultIsMixedRealityConfigured(void)
{
  char v0; // bl
  int v2; // [rsp+40h] [rbp-18h] BYREF
  DWORD v3; // [rsp+44h] [rbp-14h] BYREF

  v2 = 0;
  v3 = 4;
  v0 = 0;
  if ( !RegGetValueW(
          HKEY_CURRENT_USER,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Holographic",
          L"FirstRunSucceeded",
          0x18u,
          0,
          &v2,
          &v3) )
    return v2 != 0;
  return v0;
}

```

## disassembly

```asm
0x180015a60  mov     r11, rsp
0x180015a63  push    rbx
0x180015a64  sub     rsp, 50h
0x180015a68  mov     rax, cs:__security_cookie
0x180015a6f  xor     rax, rsp
0x180015a72  mov     [rsp+58h+var_10], rax
0x180015a77  lea     rax, [r11-14h]
0x180015a7b  mov     [rsp+58h+var_18], 0
0x180015a83  mov     [r11-28h], rax
0x180015a87  lea     r8, Value; "FirstRunSucceeded"
0x180015a8e  lea     rax, [r11-18h]
0x180015a92  mov     [rsp+58h+var_14], 4
0x180015a9a  mov     [r11-30h], rax
0x180015a9e  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180015aa5  mov     r9d, 18h; dwFlags
0x180015aab  mov     qword ptr [r11-38h], 0
0x180015ab3  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180015aba  xor     bl, bl
0x180015abc  call    cs:__imp_RegGetValueW
0x180015ac2  test    eax, eax
0x180015ac4  jnz     short loc_180015ACD
0x180015ac6  cmp     [rsp+58h+var_18], eax
0x180015aca  setnz   bl
0x180015acd  mov     al, bl
0x180015acf  mov     rcx, [rsp+58h+var_10]
0x180015ad4  xor     rcx, rsp; StackCookie
0x180015ad7  call    __security_check_cookie
0x180015adc  add     rsp, 50h
0x180015ae0  pop     rbx
0x180015ae1  retn
```
