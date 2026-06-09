# RemoteAppUtil::DeleteCookie(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180019b64`
- end: `0x180019c3e`
- name: `?DeleteCookie@RemoteAppUtil@@SAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019d2c`
- `0x18001a3d8`

## callees

- `0x1800062ac`
- `0x18000a2c0`
- `0x180019b64`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x180019be0`
- `ADVAPI32!RegDeleteValueW` at `0x180019be0`
- `ADVAPI32!RegOpenKeyExW` at `0x180019b9a`
- `ADVAPI32!RegOpenKeyExW` at `0x180019b9a`

## pseudocode

```c
__int64 __fastcall RemoteAppUtil::DeleteCookie(const WCHAR *lpValueName)
{
  __int64 v2; // rdx
  LSTATUS v3; // ebx
  LPCWSTR v4; // rcx
  __int64 v5; // rdx
  const WCHAR *v6; // rdx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  hKey = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM\\RemoteAppUserCookie",
         0,
         0xF003Fu,
         &hKey);
  if ( v3 >= 0 )
  {
    if ( *((_QWORD *)lpValueName + 3) < 8u )
      v6 = lpValueName;
    else
      v6 = *(const WCHAR **)lpValueName;
    v3 = RegDeleteValueW(hKey, v6);
    if ( v3 < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        v5 = 46;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      v5 = 45;
LABEL_12:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids, (unsigned int)v3);
    }
  }
  LOBYTE(v2) = 1;
  std::wstring::_Tidy(lpValueName, v2, 0);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180019b64  mov     r11, rsp
0x180019b67  mov     [r11+10h], rbx
0x180019b6b  push    rdi
0x180019b6c  sub     rsp, 40h
0x180019b70  mov     rdi, rcx
0x180019b73  mov     qword ptr [r11-18h], 0
0x180019b7b  lea     rax, [r11-18h]
0x180019b7f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019b86  mov     r9d, 0F003Fh; samDesired
0x180019b8c  mov     [r11-28h], rax
0x180019b90  xor     r8d, r8d; ulOptions
0x180019b93  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180019b9a  call    cs:__imp_RegOpenKeyExW
0x180019ba1  nop     dword ptr [rax+rax+00h]
0x180019ba6  mov     ebx, eax
0x180019ba8  test    eax, eax
0x180019baa  jns     short loc_180019BCC
0x180019bac  mov     rcx, cs:WPP_GLOBAL_Control
0x180019bb3  lea     rax, WPP_GLOBAL_Control
0x180019bba  cmp     rcx, rax
0x180019bbd  jz      short loc_180019C23
0x180019bbf  test    byte ptr [rcx+1Ch], 4
0x180019bc3  jz      short loc_180019C23
0x180019bc5  mov     edx, 2Dh ; '-'
0x180019bca  jmp     short loc_180019C10
0x180019bcc  cmp     qword ptr [rdi+18h], 8
0x180019bd1  jb      short loc_180019BD8
0x180019bd3  mov     rdx, [rdi]
0x180019bd6  jmp     short loc_180019BDB
0x180019bd8  mov     rdx, rdi; lpValueName
0x180019bdb  mov     rcx, [rsp+48h+hKey]; hKey
0x180019be0  call    cs:__imp_RegDeleteValueW
0x180019be7  nop     dword ptr [rax+rax+00h]
0x180019bec  mov     ebx, eax
0x180019bee  test    eax, eax
0x180019bf0  jns     short loc_180019C23
0x180019bf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180019bf9  lea     rax, WPP_GLOBAL_Control
0x180019c00  cmp     rcx, rax
0x180019c03  jz      short loc_180019C23
0x180019c05  test    byte ptr [rcx+1Ch], 4
0x180019c09  jz      short loc_180019C23
0x180019c0b  mov     edx, 2Eh ; '.'
0x180019c10  mov     rcx, [rcx+10h]
0x180019c14  lea     r8, WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids
0x180019c1b  mov     r9d, ebx
0x180019c1e  call    WPP_SF_d
0x180019c23  xor     r8d, r8d
0x180019c26  mov     dl, 1
0x180019c28  mov     rcx, rdi
0x180019c2b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180019c30  mov     eax, ebx
0x180019c32  mov     rbx, [rsp+48h+arg_8]
0x180019c37  add     rsp, 40h
0x180019c3b  pop     rdi
0x180019c3c  retn
```
