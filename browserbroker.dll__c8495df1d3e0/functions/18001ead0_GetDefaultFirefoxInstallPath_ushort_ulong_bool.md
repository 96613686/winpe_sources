# GetDefaultFirefoxInstallPath(ushort *,ulong,bool *)

- ea: `0x18001ead0`
- end: `0x18001eb82`
- name: `?GetDefaultFirefoxInstallPath@@YAJPEAGKPEA_N@Z`
- size: `178`
- prototype: `__int64 __fastcall(wchar_t *Str, unsigned int, bool *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c3a0`
- `0x18001f30c`

## callees

- `0x18001ead0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001eb57`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001eb57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eb6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eb6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb27`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001eb1d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001eb1d`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001eb47`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001eb47`

## string_xrefs

- `0x18001eaf0`: `Software\Microsoft\Windows\CurrentVersion\App Paths\firefox.exe`

## pseudocode

```c
__int64 __fastcall GetDefaultFirefoxInstallPath(wchar_t *Str, __int64 a2, bool *a3)
{
  unsigned int v5; // ebx
  DWORD v7[6]; // [rsp+40h] [rbp-18h] BYREF
  PWSTR ppszPath; // [rsp+78h] [rbp+20h] BYREF

  v7[0] = 520;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\App Paths\\firefox.exe",
         L"Path",
         2u,
         0,
         Str,
         v7) )
  {
    GetLastError();
  }
  ppszPath = 0;
  v5 = SHGetKnownFolderPath(&FOLDERID_ProgramFilesX86, 0, 0, &ppszPath);
  *a3 = wcsstr(Str, ppszPath) != 0;
  CoTaskMemFree(ppszPath);
  return v5;
}

```

## disassembly

```asm
0x18001ead0  mov     r11, rsp
0x18001ead3  mov     [r11+8], rbx
0x18001ead7  mov     [r11+10h], rsi
0x18001eadb  push    rdi
0x18001eadc  sub     rsp, 50h
0x18001eae0  lea     rax, [r11-18h]
0x18001eae4  mov     [rsp+58h+var_18], 208h
0x18001eaec  mov     [r11-28h], rax
0x18001eaf0  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001eaf7  mov     [r11-30h], rcx
0x18001eafb  mov     rsi, r8
0x18001eafe  mov     rdi, rcx
0x18001eb01  mov     qword ptr [r11-38h], 0
0x18001eb09  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001eb10  lea     r8, KeyName; "Path"
0x18001eb17  mov     r9d, 2; dwFlags
0x18001eb1d  call    cs:__imp_RegGetValueW
0x18001eb23  test    eax, eax
0x18001eb25  jz      short loc_18001EB2D
0x18001eb27  call    cs:__imp_GetLastError
0x18001eb2d  lea     r9, [rsp+58h+ppszPath]; ppszPath
0x18001eb32  mov     [rsp+58h+ppszPath], 0
0x18001eb3b  xor     r8d, r8d; hToken
0x18001eb3e  lea     rcx, FOLDERID_ProgramFilesX86; rfid
0x18001eb45  xor     edx, edx; dwFlags
0x18001eb47  call    cs:__imp_SHGetKnownFolderPath
0x18001eb4d  mov     rdx, [rsp+58h+ppszPath]; SubStr
0x18001eb52  mov     rcx, rdi; Str
0x18001eb55  mov     ebx, eax
0x18001eb57  call    cs:__imp_wcsstr
0x18001eb5d  test    rax, rax
0x18001eb60  setnz   cl
0x18001eb63  mov     [rsi], cl
0x18001eb65  mov     rcx, [rsp+58h+ppszPath]; pv
0x18001eb6a  call    cs:__imp_CoTaskMemFree
0x18001eb70  mov     rsi, [rsp+58h+arg_8]
0x18001eb75  mov     eax, ebx
0x18001eb77  mov     rbx, [rsp+58h+arg_0]
0x18001eb7c  add     rsp, 50h
0x18001eb80  pop     rdi
0x18001eb81  retn
```
