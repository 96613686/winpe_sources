# SetAnticipateShutdownProcessingNeeded

- ea: `0x14000c92c`
- end: `0x14000ca00`
- name: `SetAnticipateShutdownProcessingNeeded`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000c320`

## callees

- `0x1400023e0`
- `0x14000c92c`
- `0x140017658`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000c991`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000c991`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c9e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c9e5`

## string_xrefs

- `0x14000c953`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\AnticipateShutdownProcessingNeeded`
- `0x14000c9a8`: `Failed to create AnticipateShutdownProcessingNeeded key.`

## pseudocode

```c
__int64 SetAnticipateShutdownProcessingNeeded()
{
  LSTATUS v0; // eax
  unsigned int v1; // ebx
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF

  hKey = 0;
  vbAnticipateShutdownProcessingNeeded = 1;
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\AnticipateShutdownProcessingNeeded",
         0,
         0,
         1u,
         0x2001Fu,
         0,
         &hKey,
         0);
  v1 = v0;
  if ( v0 )
  {
    if ( v0 > 0 )
      v1 = (unsigned __int16)v0 | 0x80070000;
    CBSWdsLogLight(0x4000000u, v1, (size_t *)1, "Failed to create AnticipateShutdownProcessingNeeded key.");
  }
  else
  {
    v1 = 0;
    CBSWdsLogLight(0x4000000u, 0, 0, "TI: Anticipating that shutdown processing will be required.");
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x14000c92c  mov     r11, rsp
0x14000c92f  push    rbx
0x14000c930  sub     rsp, 60h
0x14000c934  mov     rax, cs:__security_cookie
0x14000c93b  xor     rax, rsp
0x14000c93e  mov     [rsp+68h+var_10], rax
0x14000c943  mov     qword ptr [r11-28h], 0
0x14000c94b  lea     rax, [r11-18h]
0x14000c94f  mov     [r11-30h], rax
0x14000c953  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14000c95a  mov     qword ptr [r11-38h], 0
0x14000c962  xor     r9d, r9d; lpClass
0x14000c965  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x14000c96d  xor     r8d, r8d; Reserved
0x14000c970  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000c977  mov     [rsp+68h+dwOptions], 1; dwOptions
0x14000c97f  mov     qword ptr [r11-18h], 0
0x14000c987  mov     cs:?vbAnticipateShutdownProcessingNeeded@@3HA, 1; int vbAnticipateShutdownProcessingNeeded
0x14000c991  call    cs:__imp_RegCreateKeyExW
0x14000c997  mov     ebx, eax
0x14000c999  test    eax, eax
0x14000c99b  jz      short loc_14000C9C3
0x14000c99d  jle     short loc_14000C9A8
0x14000c99f  movzx   ebx, ax
0x14000c9a2  or      ebx, 80070000h
0x14000c9a8  lea     r9, aFailedToCreate_1; "Failed to create AnticipateShutdownProc"...
0x14000c9af  mov     r8d, 1
0x14000c9b5  mov     edx, ebx
0x14000c9b7  mov     ecx, 4000000h
0x14000c9bc  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000c9c1  jmp     short loc_14000C9DB
0x14000c9c3  xor     ebx, ebx
0x14000c9c5  lea     r9, aTiAnticipating; "TI: Anticipating that shutdown processi"...
0x14000c9cc  xor     r8d, r8d
0x14000c9cf  xor     edx, edx
0x14000c9d1  mov     ecx, 4000000h
0x14000c9d6  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000c9db  mov     rcx, [rsp+68h+hKey]; hKey
0x14000c9e0  test    rcx, rcx
0x14000c9e3  jz      short loc_14000C9EB
0x14000c9e5  call    cs:__imp_RegCloseKey
0x14000c9eb  mov     eax, ebx
0x14000c9ed  mov     rcx, [rsp+68h+var_10]
0x14000c9f2  xor     rcx, rsp; StackCookie
0x14000c9f5  call    __security_check_cookie
0x14000c9fa  add     rsp, 60h
0x14000c9fe  pop     rbx
0x14000c9ff  retn
```
