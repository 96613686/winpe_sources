# CWinSATTaskMangerTask::UpdateErrorCountRegKey(ulong)

- ea: `0x180021d84`
- end: `0x180021eb4`
- name: `?UpdateErrorCountRegKey@CWinSATTaskMangerTask@@AEAA_NK@Z`
- size: `304`
- prototype: `bool(CWinSATTaskMangerTask *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800213a4`
- `0x1800217fc`

## callees

- `0x18000ee1c`
- `0x1800161e0`
- `0x180019a38`
- `0x18001b790`
- `0x180021d84`
- `0x18002ed6c`
- `0x18002fb50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180021e59`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180021e59`

## string_xrefs

- `0x180021dde`: `cannot open the winast API registry key`
- `0x180021deb`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021e46`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021e78`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021e37`: `cannot write the task error count to the registry`
- `0x180021e69`: `cannot flush the task error count to the registry`
- `0x180021e0b`: `TaskErrorCount`

## pseudocode

```c
char __fastcall CWinSATTaskMangerTask::UpdateErrorCountRegKey(CWinSATTaskMangerTask *this, unsigned int a2)
{
  char v2; // bl
  unsigned int v4; // eax
  unsigned int v6; // eax
  unsigned int v7; // edi
  LSTATUS v8; // eax
  HKEY hKey[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 Buffer[32]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v11; // [rsp+140h] [rbp+40h]
  char v12; // [rsp+144h] [rbp+44h]
  __int64 v13; // [rsp+148h] [rbp+48h]

  v2 = 0;
  memset(hKey, 0, 24);
  v4 = ATL::CRegKey::Open(
         (ATL::CRegKey *)hKey,
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSATAPI",
         0xF003Fu);
  if ( v4 )
  {
    Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", 0x2Fu, v4, (char)hKey[0]);
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    return 0;
  }
  else
  {
    v6 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)hKey, L"TaskErrorCount", a2);
    v7 = v6;
    if ( v6 )
    {
      v11 = v6;
      v12 = 1;
      v13 = 0;
      mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
      Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", 0x35u, v7, (char)hKey[0]);
    }
    else
    {
      v8 = RegFlushKey(hKey[0]);
      if ( v8 )
        Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", 0x3Au, v8, (char)hKey[0]);
      v2 = 1;
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    return v2;
  }
}

```

## disassembly

```asm
0x180021d84  mov     [rsp-8+arg_0], rbx
0x180021d89  mov     [rsp-8+arg_10], rdi
0x180021d8e  push    rbp
0x180021d8f  lea     rbp, [rsp-60h]
0x180021d94  sub     rsp, 160h
0x180021d9b  mov     rax, cs:__security_cookie
0x180021da2  xor     rax, rsp
0x180021da5  mov     [rbp+60h+var_10], rax
0x180021da9  xor     ebx, ebx
0x180021dab  lea     r8, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180021db2  mov     edi, edx
0x180021db4  mov     [rsp+160h+hKey], rbx; char
0x180021db9  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180021dc0  mov     [rsp+160h+var_138], rbx
0x180021dc5  mov     r9d, 0F003Fh; unsigned int
0x180021dcb  mov     [rsp+160h+var_130], rbx
0x180021dd0  lea     rcx, [rsp+160h+hKey]; this
0x180021dd5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180021dda  test    eax, eax
0x180021ddc  jz      short loc_180021E08
0x180021dde  lea     r9, aCannotOpenTheW; "cannot open the winast API registry key"
0x180021de5  mov     r8d, eax; unsigned int
0x180021de8  lea     edx, [rbx+2Fh]; unsigned int
0x180021deb  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021df2  call    Record_Win32Error_w
0x180021df7  lea     rcx, [rsp+160h+hKey]; this
0x180021dfc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180021e01  xor     al, al
0x180021e03  jmp     loc_180021E92
0x180021e08  mov     r8d, edi; unsigned int
0x180021e0b  lea     rdx, aTaskerrorcount; "TaskErrorCount"
0x180021e12  lea     rcx, [rsp+160h+hKey]; this
0x180021e17  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180021e1c  mov     edi, eax
0x180021e1e  test    eax, eax
0x180021e20  jz      short loc_180021E54
0x180021e22  lea     rcx, [rsp+160h+Buffer]; lpBuffer
0x180021e27  mov     [rbp+60h+var_20], eax
0x180021e2a  mov     [rbp+60h+var_1C], 1
0x180021e2e  mov     [rbp+60h+var_18], rbx
0x180021e32  call    ?fmt_desc@?$WinErrorT@DU?$char_traits@D@std@@V?$m_traits@D@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(void)
0x180021e37  lea     r9, aCannotWriteThe; "cannot write the task error count to th"...
0x180021e3e  mov     r8d, edi; unsigned int
0x180021e41  mov     edx, 35h ; '5'; unsigned int
0x180021e46  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021e4d  call    Record_Win32Error_w
0x180021e52  jmp     short loc_180021E86
0x180021e54  mov     rcx, [rsp+160h+hKey]; hKey
0x180021e59  call    cs:__imp_RegFlushKey
0x180021e60  nop     dword ptr [rax+rax+00h]
0x180021e65  test    eax, eax
0x180021e67  jz      short loc_180021E84
0x180021e69  lea     r9, aCannotFlushThe; "cannot flush the task error count to th"...
0x180021e70  mov     r8d, eax; unsigned int
0x180021e73  mov     edx, 3Ah ; ':'; unsigned int
0x180021e78  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021e7f  call    Record_Win32Error_w
0x180021e84  mov     bl, 1
0x180021e86  lea     rcx, [rsp+160h+hKey]; this
0x180021e8b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180021e90  mov     al, bl
0x180021e92  mov     rcx, [rbp+60h+var_10]
0x180021e96  xor     rcx, rsp; StackCookie
0x180021e99  call    __security_check_cookie
0x180021e9e  lea     r11, [rsp+160h+var_s0]
0x180021ea6  mov     rbx, [r11+10h]
0x180021eaa  mov     rdi, [r11+20h]
0x180021eae  mov     rsp, r11
0x180021eb1  pop     rbp
0x180021eb2  retn
```
