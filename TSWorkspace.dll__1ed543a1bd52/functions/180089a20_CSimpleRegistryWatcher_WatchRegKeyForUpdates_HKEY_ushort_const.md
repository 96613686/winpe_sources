# CSimpleRegistryWatcher::WatchRegKeyForUpdates(HKEY__ *,ushort const *)

- ea: `0x180089a20`
- end: `0x180089b77`
- name: `?WatchRegKeyForUpdates@CSimpleRegistryWatcher@@IEAAJPEAUHKEY__@@PEBG@Z`
- size: `343`
- prototype: `int(CSimpleRegistryWatcher *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18003f414`
- `0x1800749c8`

## callees

- `0x1800105a4`
- `0x180088f8c`
- `0x180089380`
- `0x180089a20`
- `0x180089b80`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180089b11`
- `ADVAPI32!RegCloseKey` at `0x180089b11`
- `ADVAPI32!RegOpenKeyExW` at `0x180089a67`
- `ADVAPI32!RegOpenKeyExW` at `0x180089a67`
- `KERNEL32!RegNotifyChangeKeyValue` at `0x180089ab4`
- `KERNEL32!RegNotifyChangeKeyValue` at `0x180089ab4`

## string_xrefs

- `0x180089a91`: `RegOpenKeyEx failed`

## pseudocode

```c
__int64 __fastcall CSimpleRegistryWatcher::WatchRegKeyForUpdates(
        CSimpleRegistryWatcher *this,
        HKEY a2,
        const unsigned __int16 *a3)
{
  bool v3; // zf
  int v6; // ebx
  int v7; // r8d
  _QWORD *v8; // rcx
  int v9; // edx
  const wchar_t *v10; // r9
  bool v11; // sf
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = a2;
  v3 = *((_QWORD *)this + 1) == 0;
  hKey = 0;
  if ( v3 )
    CSimpleRegistryWatcher::StartUpdateWatcher(this);
  v6 = RegOpenKeyExW(HKEY_CURRENT_USER, a3, 0, 0x10u, &hKey);
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_12;
    v9 = 36;
    v10 = L"RegOpenKeyEx failed";
LABEL_11:
    WPP_SF_Sd(v8[2], v9, v7, (_DWORD)v10, v6);
LABEL_12:
    v11 = v6 < 0;
    if ( v6 > 0 )
    {
      v6 = (unsigned __int16)v6 | 0x80070000;
      v11 = v6 < 0;
    }
    if ( v11
      && hKey
      && RegCloseKey(hKey)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids);
    }
    return (unsigned int)v6;
  }
  v6 = RegNotifyChangeKeyValue(hKey, 1, 5u, *((HANDLE *)this + 2), 1);
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_12;
    v9 = 37;
    v10 = L"RegNotifyChangeKeyValue failed";
    goto LABEL_11;
  }
  v6 = 0;
  if ( (unsigned int)DynArray<HKEY__ *,unsigned long>::Grow((char *)this + 48, *((unsigned int *)this + 13)) )
    *(_QWORD *)(*((_QWORD *)this + 7) + 8LL * (unsigned int)(*((_DWORD *)this + 13))++) = hKey;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180089a20  mov     [rsp+arg_0], rbx
0x180089a25  mov     [rsp+hKey], rdx
0x180089a2a  push    rdi
0x180089a2b  sub     rsp, 30h
0x180089a2f  cmp     qword ptr [rcx+8], 0
0x180089a34  mov     rbx, r8
0x180089a37  mov     rdi, rcx
0x180089a3a  mov     [rsp+38h+hKey], 0
0x180089a43  jnz     short loc_180089A4A
0x180089a45  call    ?StartUpdateWatcher@CSimpleRegistryWatcher@@IEAAJXZ; CSimpleRegistryWatcher::StartUpdateWatcher(void)
0x180089a4a  lea     rax, [rsp+38h+hKey]
0x180089a4f  mov     r9d, 10h; samDesired
0x180089a55  xor     r8d, r8d; ulOptions
0x180089a58  mov     [rsp+38h+phkResult], rax; phkResult
0x180089a5d  mov     rdx, rbx; lpSubKey
0x180089a60  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180089a67  call    cs:__imp_RegOpenKeyExW
0x180089a6d  mov     ebx, eax
0x180089a6f  test    eax, eax
0x180089a71  jz      short loc_180089A9A
0x180089a73  mov     rcx, cs:WPP_GLOBAL_Control
0x180089a7a  lea     rdi, WPP_GLOBAL_Control
0x180089a81  cmp     rcx, rdi
0x180089a84  jz      short loc_180089AF6
0x180089a86  cmp     byte ptr [rcx+19h], 2
0x180089a8a  jb      short loc_180089AF6
0x180089a8c  mov     edx, 24h ; '$'
0x180089a91  lea     r9, aRegopenkeyexFa; "RegOpenKeyEx failed"
0x180089a98  jmp     short loc_180089AE9
0x180089a9a  mov     r9, [rdi+10h]; hEvent
0x180089a9e  mov     edx, 1; bWatchSubtree
0x180089aa3  mov     rcx, [rsp+38h+hKey]; hKey
0x180089aa8  mov     dword ptr [rsp+38h+phkResult], 1; fAsynchronous
0x180089ab0  lea     r8d, [rdx+4]; dwNotifyFilter
0x180089ab4  call    cs:__imp_RegNotifyChangeKeyValue
0x180089aba  mov     ebx, eax
0x180089abc  test    eax, eax
0x180089abe  jz      loc_180089B44
0x180089ac4  mov     rcx, cs:WPP_GLOBAL_Control
0x180089acb  lea     rdi, WPP_GLOBAL_Control
0x180089ad2  cmp     rcx, rdi
0x180089ad5  jz      short loc_180089AF6
0x180089ad7  cmp     byte ptr [rcx+19h], 2
0x180089adb  jb      short loc_180089AF6
0x180089add  mov     edx, 25h ; '%'
0x180089ae2  lea     r9, aRegnotifychang; "RegNotifyChangeKeyValue failed"
0x180089ae9  mov     rcx, [rcx+10h]
0x180089aed  mov     dword ptr [rsp+38h+phkResult], ebx
0x180089af1  call    WPP_SF_Sd
0x180089af6  test    ebx, ebx
0x180089af8  jle     short loc_180089B05
0x180089afa  movzx   ebx, bx
0x180089afd  or      ebx, 80070000h
0x180089b03  test    ebx, ebx
0x180089b05  jns     short loc_180089B6A
0x180089b07  mov     rcx, [rsp+38h+hKey]; hKey
0x180089b0c  test    rcx, rcx
0x180089b0f  jz      short loc_180089B6A
0x180089b11  call    cs:__imp_RegCloseKey
0x180089b17  test    eax, eax
0x180089b19  jz      short loc_180089B6A
0x180089b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180089b22  cmp     rcx, rdi
0x180089b25  jz      short loc_180089B6A
0x180089b27  cmp     byte ptr [rcx+19h], 2
0x180089b2b  jb      short loc_180089B6A
0x180089b2d  mov     rcx, [rcx+10h]
0x180089b31  lea     r8, WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids
0x180089b38  mov     edx, 26h ; '&'
0x180089b3d  call    WPP_SF_
0x180089b42  jmp     short loc_180089B6A
0x180089b44  mov     edx, [rdi+34h]
0x180089b47  lea     rcx, [rdi+30h]
0x180089b4b  xor     ebx, ebx
0x180089b4d  call    ?Grow@?$DynArray@PEAUHKEY__@@K@@AEAAHK@Z; DynArray<HKEY__ *,ulong>::Grow(ulong)
0x180089b52  test    eax, eax
0x180089b54  jz      short loc_180089B6A
0x180089b56  mov     r8d, [rdi+34h]
0x180089b5a  mov     rdx, [rdi+38h]
0x180089b5e  mov     rcx, [rsp+38h+hKey]
0x180089b63  mov     [rdx+r8*8], rcx
0x180089b67  inc     dword ptr [rdi+34h]
0x180089b6a  mov     eax, ebx
0x180089b6c  mov     rbx, [rsp+38h+arg_0]
0x180089b71  add     rsp, 30h
0x180089b75  pop     rdi
0x180089b76  retn
```
