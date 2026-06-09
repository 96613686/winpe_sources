# ServiceControl::OnUnregister(void)

- ea: `0x140003f34`
- end: `0x1400040ab`
- name: `?OnUnregister@ServiceControl@@CAXXZ`
- size: `375`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140003b50`
- `0x140003c40`

## callees

- `0x1400023e4`
- `0x140003f34`
- `0x140004278`
- `0x1400137e0`

## import_xrefs

- `ole32!StringFromGUID2` at `0x140003f66`
- `ole32!StringFromGUID2` at `0x140003f66`
- `ADVAPI32!RegDeleteTreeW` at `0x140003ff1`
- `ADVAPI32!RegDeleteTreeW` at `0x140004071`
- `ADVAPI32!RegDeleteTreeW` at `0x140003ff1`
- `ADVAPI32!RegDeleteTreeW` at `0x140004071`

## string_xrefs

- `0x14000407e`: `SUCCESS: The service was uninstalled successfully\n`
- `0x140003f7b`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void ServiceControl::OnUnregister(void)
{
  __int64 v0; // rdx
  WCHAR *v1; // rcx
  WCHAR v2; // ax
  WCHAR *v3; // rax
  __int64 v4; // r8
  WCHAR *v5; // rcx
  WCHAR v6; // ax
  WCHAR *v7; // rax
  WCHAR SubKey[264]; // [rsp+20h] [rbp-278h] BYREF
  unsigned __int16 v9[40]; // [rsp+230h] [rbp-68h] BYREF

  if ( StringFromGUID2(&CLSID_StandardCollectorService, v9, 39) )
  {
    v0 = 260;
    v1 = SubKey;
    do
    {
      if ( v0 == -2147483386 )
        break;
      v2 = *(WCHAR *)((char *)v1 + (char *)L"CLSID\\" - (char *)SubKey);
      if ( !v2 )
        break;
      *v1++ = v2;
      --v0;
    }
    while ( v0 );
    v3 = v1 - 1;
    if ( v0 )
      v3 = v1;
    *v3 = 0;
    if ( v0
      && (int)StringCchCatW(SubKey, 0x104u, v9) >= 0
      && (RegDeleteTreeW(HKEY_CLASSES_ROOT, SubKey) & 0xFFFFFFFD) == 0 )
    {
      v4 = 260;
      v5 = SubKey;
      do
      {
        if ( v4 == -2147483386 )
          break;
        v6 = *(WCHAR *)((char *)v5 + (char *)L"AppID\\" - (char *)SubKey);
        if ( !v6 )
          break;
        *v5++ = v6;
        --v4;
      }
      while ( v4 );
      v7 = v5 - 1;
      if ( v4 )
        v7 = v5;
      *v7 = 0;
      if ( v4
        && (int)StringCchCatW(SubKey, 0x104u, v9) >= 0
        && (RegDeleteTreeW(HKEY_CLASSES_ROOT, SubKey) & 0xFFFFFFFD) == 0 )
      {
        wprintf(L"SUCCESS: The service was uninstalled successfully\n");
      }
    }
  }
}

```

## disassembly

```asm
0x140003f34  mov     r11, rsp
0x140003f37  mov     [r11+8], rbx
0x140003f3b  push    rdi
0x140003f3c  sub     rsp, 290h
0x140003f43  mov     rax, cs:__security_cookie
0x140003f4a  xor     rax, rsp
0x140003f4d  mov     [rsp+298h+var_18], rax
0x140003f55  mov     r8d, 27h ; '''; cchMax
0x140003f5b  lea     rdx, [r11-68h]; lpsz
0x140003f5f  lea     rcx, CLSID_StandardCollectorService; rguid
0x140003f66  call    cs:__imp_StringFromGUID2
0x140003f6c  xor     ebx, ebx
0x140003f6e  test    eax, eax
0x140003f70  jz      loc_14000408A
0x140003f76  mov     edi, 104h
0x140003f7b  lea     r8, aClsid; "CLSID\\"
0x140003f82  lea     rax, [rsp+298h+SubKey]
0x140003f87  mov     edx, edi
0x140003f89  sub     r8, rax
0x140003f8c  lea     rcx, [rsp+298h+SubKey]
0x140003f91  lea     rax, [rdx+7FFFFEFAh]
0x140003f98  test    rax, rax
0x140003f9b  jz      short loc_140003FB4
0x140003f9d  movzx   eax, word ptr [rcx+r8]
0x140003fa2  test    ax, ax
0x140003fa5  jz      short loc_140003FB4
0x140003fa7  mov     [rcx], ax
0x140003faa  add     rcx, 2
0x140003fae  sub     rdx, 1
0x140003fb2  jnz     short loc_140003F91
0x140003fb4  test    rdx, rdx
0x140003fb7  lea     rax, [rcx-2]
0x140003fbb  cmovnz  rax, rcx
0x140003fbf  mov     [rax], bx
0x140003fc2  jz      loc_14000408A
0x140003fc8  lea     r8, [rsp+298h+var_68]; unsigned __int16 *
0x140003fd0  mov     rdx, rdi; unsigned __int64
0x140003fd3  lea     rcx, [rsp+298h+SubKey]; unsigned __int16 *
0x140003fd8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003fdd  test    eax, eax
0x140003fdf  js      loc_14000408A
0x140003fe5  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x140003fea  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140003ff1  call    cs:__imp_RegDeleteTreeW
0x140003ff7  test    eax, 0FFFFFFFDh
0x140003ffc  jnz     loc_14000408A
0x140004002  lea     r9, aAppid; "AppID\\"
0x140004009  mov     r8, rdi
0x14000400c  lea     rax, [rsp+298h+SubKey]
0x140004011  sub     r9, rax
0x140004014  lea     rcx, [rsp+298h+SubKey]
0x140004019  lea     rax, [r8+7FFFFEFAh]
0x140004020  test    rax, rax
0x140004023  jz      short loc_14000403C
0x140004025  movzx   eax, word ptr [r9+rcx]
0x14000402a  test    ax, ax
0x14000402d  jz      short loc_14000403C
0x14000402f  mov     [rcx], ax
0x140004032  add     rcx, 2
0x140004036  sub     r8, 1
0x14000403a  jnz     short loc_140004019
0x14000403c  test    r8, r8
0x14000403f  lea     rax, [rcx-2]
0x140004043  cmovnz  rax, rcx
0x140004047  mov     [rax], bx
0x14000404a  jz      short loc_14000408A
0x14000404c  lea     r8, [rsp+298h+var_68]; unsigned __int16 *
0x140004054  mov     rdx, rdi; unsigned __int64
0x140004057  lea     rcx, [rsp+298h+SubKey]; unsigned __int16 *
0x14000405c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004061  test    eax, eax
0x140004063  js      short loc_14000408A
0x140004065  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x14000406a  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140004071  call    cs:__imp_RegDeleteTreeW
0x140004077  test    eax, 0FFFFFFFDh
0x14000407c  jnz     short loc_14000408A
0x14000407e  lea     rcx, aSuccessTheServ_2; "SUCCESS: The service was uninstalled su"...
0x140004085  call    wprintf
0x14000408a  mov     rcx, [rsp+298h+var_18]
0x140004092  xor     rcx, rsp; StackCookie
0x140004095  call    __security_check_cookie
0x14000409a  mov     rbx, [rsp+298h+arg_0]
0x1400040a2  add     rsp, 290h
0x1400040a9  pop     rdi
0x1400040aa  retn
```
