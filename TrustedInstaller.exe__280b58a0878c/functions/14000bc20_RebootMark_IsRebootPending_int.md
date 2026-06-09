# RebootMark::IsRebootPending(int *)

- ea: `0x14000bc20`
- end: `0x14000bce0`
- name: `?IsRebootPending@RebootMark@@QEAAJPEAH@Z`
- size: `192`
- prototype: `__int64 __fastcall(RebootMark *__hidden this, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140009650`

## callees

- `0x1400023e0`
- `0x14000bc20`
- `0x140017658`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bc75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bc75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000bcc0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000bcc0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000bc64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000bc64`

## string_xrefs

- `0x14000bc53`: `Software\Microsoft\Windows\CurrentVersion\Component Based Servicing\RebootPending`
- `0x14000bc8c`: `Failed to open RebootPending key.`

## pseudocode

```c
__int64 __fastcall RebootMark::IsRebootPending(RebootMark *this, int *a2)
{
  int v2; // edi
  LSTATUS v3; // eax
  signed int LastError; // eax
  unsigned int v5; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  hKey = 0;
  v2 = 1;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\RebootPending",
         0,
         1u,
         &hKey);
  if ( (unsigned int)(v3 - 2) <= 1 )
  {
    v2 = 0;
    goto LABEL_9;
  }
  if ( !v3 )
  {
LABEL_9:
    v5 = 0;
    vbRebootPending = v2;
    goto LABEL_10;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
    v5 = -2147467259;
  CBSWdsLogLight(0x4000000u, v5, (size_t *)1, "Failed to open RebootPending key.");
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x14000bc20  mov     r11, rsp
0x14000bc23  mov     [r11+8], rbx
0x14000bc27  push    rdi
0x14000bc28  sub     rsp, 40h
0x14000bc2c  mov     rax, cs:__security_cookie
0x14000bc33  xor     rax, rsp
0x14000bc36  mov     [rsp+48h+var_10], rax
0x14000bc3b  lea     rax, [r11-18h]
0x14000bc3f  mov     qword ptr [r11-18h], 0
0x14000bc47  mov     edi, 1
0x14000bc4c  mov     [r11-28h], rax
0x14000bc50  mov     r9d, edi; samDesired
0x14000bc53  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14000bc5a  xor     r8d, r8d; ulOptions
0x14000bc5d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000bc64  call    cs:__imp_RegOpenKeyExW
0x14000bc6a  lea     ecx, [rax-2]
0x14000bc6d  cmp     ecx, edi
0x14000bc6f  jbe     short loc_14000BCAC
0x14000bc71  test    eax, eax
0x14000bc73  jz      short loc_14000BCAE
0x14000bc75  call    cs:__imp_GetLastError
0x14000bc7b  mov     ebx, eax
0x14000bc7d  test    eax, eax
0x14000bc7f  jle     short loc_14000BC8A
0x14000bc81  movzx   ebx, ax
0x14000bc84  or      ebx, 80070000h
0x14000bc8a  test    ebx, ebx
0x14000bc8c  lea     r9, aFailedToOpenRe; "Failed to open RebootPending key."
0x14000bc93  mov     eax, 80004005h
0x14000bc98  mov     r8d, edi
0x14000bc9b  cmovns  ebx, eax
0x14000bc9e  mov     ecx, 4000000h
0x14000bca3  mov     edx, ebx
0x14000bca5  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000bcaa  jmp     short loc_14000BCB6
0x14000bcac  xor     edi, edi
0x14000bcae  xor     ebx, ebx
0x14000bcb0  mov     cs:?vbRebootPending@@3HA, edi; int vbRebootPending
0x14000bcb6  mov     rcx, [rsp+48h+hKey]; hKey
0x14000bcbb  test    rcx, rcx
0x14000bcbe  jz      short loc_14000BCC6
0x14000bcc0  call    cs:__imp_RegCloseKey
0x14000bcc6  mov     eax, ebx
0x14000bcc8  mov     rcx, [rsp+48h+var_10]
0x14000bccd  xor     rcx, rsp; StackCookie
0x14000bcd0  call    __security_check_cookie
0x14000bcd5  mov     rbx, [rsp+48h+arg_0]
0x14000bcda  add     rsp, 40h
0x14000bcde  pop     rdi
0x14000bcdf  retn
```
