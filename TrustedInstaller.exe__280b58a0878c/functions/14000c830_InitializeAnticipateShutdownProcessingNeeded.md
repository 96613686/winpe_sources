# InitializeAnticipateShutdownProcessingNeeded

- ea: `0x14000c830`
- end: `0x14000c8d9`
- name: `InitializeAnticipateShutdownProcessingNeeded`
- size: `169`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140009650`

## callees

- `0x1400023e0`
- `0x14000c320`
- `0x14000c830`
- `0x140017658`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c8be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c8be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000c86f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000c86f`

## string_xrefs

- `0x14000c861`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\AnticipateShutdownProcessingNeeded`
- `0x14000c88e`: `Failed to read AnticipateShutdownProcessingNeeded key.`

## pseudocode

```c
__int64 InitializeAnticipateShutdownProcessingNeeded()
{
  int v0; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\AnticipateShutdownProcessingNeeded",
         0,
         1u,
         &hKey);
  if ( (unsigned int)(v0 - 2) <= 1 )
  {
    v0 = 0;
  }
  else if ( v0 )
  {
    if ( v0 > 0 )
      v0 = (unsigned __int16)v0 | 0x80070000;
    CBSWdsLogLight(0x4000000u, (unsigned int)v0, (size_t *)1, "Failed to read AnticipateShutdownProcessingNeeded key.");
  }
  else
  {
    v0 = 0;
    TiCoreAnticipateShutdownProcessingNeeded();
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14000c830  push    rbx
0x14000c832  sub     rsp, 40h
0x14000c836  mov     rax, cs:__security_cookie
0x14000c83d  xor     rax, rsp
0x14000c840  mov     [rsp+48h+var_10], rax
0x14000c845  lea     rax, [rsp+48h+hKey]
0x14000c84a  mov     [rsp+48h+hKey], 0
0x14000c853  mov     r9d, 1; samDesired
0x14000c859  mov     [rsp+48h+phkResult], rax; phkResult
0x14000c85e  xor     r8d, r8d; ulOptions
0x14000c861  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14000c868  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000c86f  call    cs:__imp_RegOpenKeyExW
0x14000c875  mov     ebx, eax
0x14000c877  add     eax, 0FFFFFFFEh
0x14000c87a  cmp     eax, 1
0x14000c87d  jbe     short loc_14000C8B2
0x14000c87f  test    ebx, ebx
0x14000c881  jz      short loc_14000C8A9
0x14000c883  jle     short loc_14000C88E
0x14000c885  movzx   ebx, bx
0x14000c888  or      ebx, 80070000h
0x14000c88e  lea     r9, aFailedToReadAn; "Failed to read AnticipateShutdownProces"...
0x14000c895  mov     r8d, 1
0x14000c89b  mov     edx, ebx
0x14000c89d  mov     ecx, 4000000h
0x14000c8a2  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000c8a7  jmp     short loc_14000C8B4
0x14000c8a9  xor     ebx, ebx
0x14000c8ab  call    TiCoreAnticipateShutdownProcessingNeeded
0x14000c8b0  jmp     short loc_14000C8B4
0x14000c8b2  xor     ebx, ebx
0x14000c8b4  mov     rcx, [rsp+48h+hKey]; hKey
0x14000c8b9  test    rcx, rcx
0x14000c8bc  jz      short loc_14000C8C4
0x14000c8be  call    cs:__imp_RegCloseKey
0x14000c8c4  mov     eax, ebx
0x14000c8c6  mov     rcx, [rsp+48h+var_10]
0x14000c8cb  xor     rcx, rsp; StackCookie
0x14000c8ce  call    __security_check_cookie
0x14000c8d3  add     rsp, 40h
0x14000c8d7  pop     rbx
0x14000c8d8  retn
```
