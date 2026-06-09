# RebootMark::Mark(void)

- ea: `0x14000bdd0`
- end: `0x14000bea9`
- name: `?Mark@RebootMark@@SAJXZ`
- size: `217`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000d12c`

## callees

- `0x1400023e0`
- `0x14000bdd0`
- `0x140017658`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000be33`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000be33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000be8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000be8e`

## string_xrefs

- `0x14000bdf7`: `Software\Microsoft\Windows\CurrentVersion\Component Based Servicing\RebootPending`
- `0x14000be4a`: `Failed to create RebootPending key.`

## pseudocode

```c
__int64 RebootMark::Mark(void)
{
  LSTATUS v0; // eax
  unsigned int v1; // ebx
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  DWORD v4; // [rsp+58h] [rbp-20h] BYREF

  hKey = 0;
  v4 = 0;
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\RebootPending",
         0,
         0,
         1u,
         0x2001Fu,
         0,
         &hKey,
         &v4);
  v1 = v0;
  if ( v0 )
  {
    if ( v0 > 0 )
      v1 = (unsigned __int16)v0 | 0x80070000;
    CBSWdsLogLight(0x4000000u, v1, (size_t *)1, "Failed to create RebootPending key.");
  }
  else
  {
    v1 = 0;
    if ( v4 != 2 )
      CBSWdsLogLight(0x4000000u, 0, 0, "Reboot mark set");
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x14000bdd0  mov     r11, rsp
0x14000bdd3  push    rbx
0x14000bdd4  sub     rsp, 70h
0x14000bdd8  mov     rax, cs:__security_cookie
0x14000bddf  xor     rax, rsp
0x14000bde2  mov     [rsp+78h+var_18], rax
0x14000bde7  lea     rax, [r11-20h]
0x14000bdeb  mov     qword ptr [r11-28h], 0
0x14000bdf3  mov     [r11-38h], rax
0x14000bdf7  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14000bdfe  lea     rax, [r11-28h]
0x14000be02  mov     [rsp+78h+var_20], 0
0x14000be0a  mov     [r11-40h], rax
0x14000be0e  xor     r9d, r9d; lpClass
0x14000be11  mov     qword ptr [r11-48h], 0
0x14000be19  xor     r8d, r8d; Reserved
0x14000be1c  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x14000be24  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000be2b  mov     [rsp+78h+dwOptions], 1; dwOptions
0x14000be33  call    cs:__imp_RegCreateKeyExW
0x14000be39  mov     ebx, eax
0x14000be3b  test    eax, eax
0x14000be3d  jz      short loc_14000BE65
0x14000be3f  jle     short loc_14000BE4A
0x14000be41  movzx   ebx, ax
0x14000be44  or      ebx, 80070000h
0x14000be4a  lea     r9, aFailedToCreate_10; "Failed to create RebootPending key."
0x14000be51  mov     r8d, 1
0x14000be57  mov     edx, ebx
0x14000be59  mov     ecx, 4000000h
0x14000be5e  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000be63  jmp     short loc_14000BE84
0x14000be65  xor     ebx, ebx
0x14000be67  cmp     [rsp+78h+var_20], 2
0x14000be6c  jz      short loc_14000BE84
0x14000be6e  lea     r9, aRebootMarkSet; "Reboot mark set"
0x14000be75  xor     r8d, r8d
0x14000be78  xor     edx, edx
0x14000be7a  mov     ecx, 4000000h
0x14000be7f  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000be84  mov     rcx, [rsp+78h+hKey]; hKey
0x14000be89  test    rcx, rcx
0x14000be8c  jz      short loc_14000BE94
0x14000be8e  call    cs:__imp_RegCloseKey
0x14000be94  mov     eax, ebx
0x14000be96  mov     rcx, [rsp+78h+var_18]
0x14000be9b  xor     rcx, rsp; StackCookie
0x14000be9e  call    __security_check_cookie
0x14000bea3  add     rsp, 70h
0x14000bea7  pop     rbx
0x14000bea8  retn
```
