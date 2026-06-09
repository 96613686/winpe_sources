# CitrixShellRestore(ushort const *,ushort const *,void *)

- ea: `0x18003a500`
- end: `0x18003a5b6`
- name: `?CitrixShellRestore@@YAJPEBG0PEAX@Z`
- size: `182`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18003a500`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18003a58b`
- `ADVAPI32!RegCloseKey` at `0x18003a58b`
- `ADVAPI32!RegSetValueExW` at `0x18003a57e`
- `ADVAPI32!RegSetValueExW` at `0x18003a57e`
- `ADVAPI32!RegOpenKeyExW` at `0x18003a54b`
- `ADVAPI32!RegOpenKeyExW` at `0x18003a54b`

## pseudocode

```c
__int64 __fastcall CitrixShellRestore(const unsigned __int16 *a1, const unsigned __int16 *a2, void *a3)
{
  __int64 v3; // rdi
  LSTATUS v4; // ebx
  bool v5; // cc
  LPCWSTR lpSubKey[3]; // [rsp+30h] [rbp-18h]
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  lpSubKey[0] = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\WinLogon";
  v3 = 0;
  lpSubKey[1] = L"Software\\Wow6432Node\\Microsoft\\Windows NT\\CurrentVersion\\WinLogon";
  do
  {
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[v3], 0, 0x20006u, &hKey);
    if ( v4 )
      break;
    v4 = RegSetValueExW(hKey, L"CtxBackupShell", 0, 1u, L"explorer.exe", 0x1Au);
    RegCloseKey(hKey);
    v5 = v4 <= 0;
    if ( v4 )
      goto LABEL_6;
    v3 = (unsigned int)(v3 + 1);
  }
  while ( (unsigned int)v3 < 2 );
  v5 = v4 <= 0;
LABEL_6:
  if ( !v5 )
    return (unsigned __int16)v4 | 0x80070000;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003a500  mov     r11, rsp
0x18003a503  mov     [r11+8], rbx
0x18003a507  push    rdi
0x18003a508  sub     rsp, 40h
0x18003a50c  lea     rax, aSoftwareMicros_10; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003a513  mov     qword ptr [r11+20h], 0
0x18003a51b  mov     [r11-18h], rax
0x18003a51f  xor     edi, edi
0x18003a521  lea     rax, aSoftwareWow643_1; "Software\\Wow6432Node\\Microsoft\\Windo"...
0x18003a528  mov     [r11-10h], rax
0x18003a52c  mov     rdx, [rsp+rdi*8+48h+lpSubKey]; lpSubKey
0x18003a531  lea     rax, [rsp+48h+hKey]
0x18003a536  mov     r9d, 20006h; samDesired
0x18003a53c  mov     [rsp+48h+phkResult], rax; phkResult
0x18003a541  xor     r8d, r8d; ulOptions
0x18003a544  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003a54b  call    cs:__imp_RegOpenKeyExW
0x18003a551  mov     ebx, eax
0x18003a553  test    eax, eax
0x18003a555  jnz     short loc_18003A59C
0x18003a557  mov     rcx, [rsp+48h+hKey]; hKey
0x18003a55c  lea     rax, Data; "explorer.exe"
0x18003a563  mov     [rsp+48h+cbData], 1Ah; cbData
0x18003a56b  lea     r9d, [rbx+1]; dwType
0x18003a56f  xor     r8d, r8d; Reserved
0x18003a572  mov     [rsp+48h+phkResult], rax; lpData
0x18003a577  lea     rdx, aCtxbackupshell; "CtxBackupShell"
0x18003a57e  call    cs:__imp_RegSetValueExW
0x18003a584  mov     rcx, [rsp+48h+hKey]; hKey
0x18003a589  mov     ebx, eax
0x18003a58b  call    cs:__imp_RegCloseKey
0x18003a591  test    ebx, ebx
0x18003a593  jnz     short loc_18003A59E
0x18003a595  inc     edi
0x18003a597  cmp     edi, 2
0x18003a59a  jb      short loc_18003A52C
0x18003a59c  test    ebx, ebx
0x18003a59e  jle     short loc_18003A5A9
0x18003a5a0  movzx   ebx, bx
0x18003a5a3  or      ebx, 80070000h
0x18003a5a9  mov     eax, ebx
0x18003a5ab  mov     rbx, [rsp+48h+arg_0]
0x18003a5b0  add     rsp, 40h
0x18003a5b4  pop     rdi
0x18003a5b5  retn
```
