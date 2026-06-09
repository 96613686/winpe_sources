# winreRegisterOfflineScanningCommand(ushort const *)

- ea: `0x18001fc48`
- end: `0x18001fd73`
- name: `?winreRegisterOfflineScanningCommand@@YAKPEBG@Z`
- size: `299`
- prototype: `unsigned int __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180023b50`

## callees

- `0x1800059fc`
- `0x18001fc48`
- `0x18005cf30`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18001fcef`
- `ADVAPI32!RegSetValueExW` at `0x18001fcef`
- `ADVAPI32!RegCreateKeyExW` at `0x18001fca0`
- `ADVAPI32!RegCreateKeyExW` at `0x18001fca0`
- `ADVAPI32!RegCloseKey` at `0x18001fd34`
- `ADVAPI32!RegCloseKey` at `0x18001fd34`

## string_xrefs

- `0x18001fcb4`: `failed to open recovery environment key`
- `0x18001fd0a`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x18001fd14`: `winreRegisterOfflineScanningCommand %s (0x%x) in file %S line %d`
- `0x18001fd03`: `failed to set offline scanning command`
- `0x18001fd41`: `failed to set offline scanning command to registry key: 0x%x`

## pseudocode

```c
__int64 __fastcall winreRegisterOfflineScanningCommand(BYTE *lpData)
{
  unsigned int v2; // ebx
  const wchar_t *v3; // r8
  __int64 v4; // rax
  __int64 samDesired; // [rsp+28h] [rbp-40h]
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF

  hKey = 0;
  v2 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\RecoveryEnvironment", 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v2 )
  {
    LODWORD(samDesired) = 6188;
    v3 = L"failed to open recovery environment key";
LABEL_7:
    UnattendLogW(
      2,
      L"winreRegisterOfflineScanningCommand %s (0x%x) in file %S line %d",
      v3,
      v2,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      samDesired);
    goto LABEL_8;
  }
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)&lpData[2 * v4] );
  v2 = RegSetValueExW(hKey, L"OfflineScanningCmdLine", 0, 1u, lpData, 2 * v4 + 2);
  if ( v2 )
  {
    LODWORD(samDesired) = 6198;
    v3 = L"failed to set offline scanning command";
    goto LABEL_7;
  }
LABEL_8:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v2 )
    UnattendLogW(2, L"failed to set offline scanning command to registry key: 0x%x", v2);
  return v2;
}

```

## disassembly

```asm
0x18001fc48  mov     r11, rsp
0x18001fc4b  mov     [r11+10h], rbx
0x18001fc4f  mov     [r11+18h], rsi
0x18001fc53  push    rdi
0x18001fc54  sub     rsp, 60h
0x18001fc58  mov     rax, cs:__security_cookie
0x18001fc5f  xor     rax, rsp
0x18001fc62  mov     [rsp+68h+var_10], rax
0x18001fc67  xor     esi, esi
0x18001fc69  lea     rax, [r11-18h]
0x18001fc6d  mov     [r11-28h], rsi
0x18001fc71  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\RecoveryEnvironmen"...
0x18001fc78  mov     [r11-30h], rax
0x18001fc7c  mov     rdi, rcx
0x18001fc7f  mov     [r11-38h], rsi
0x18001fc83  xor     r9d, r9d; lpClass
0x18001fc86  mov     dword ptr [rsp+68h+samDesired], 20006h; samDesired
0x18001fc8e  xor     r8d, r8d; Reserved
0x18001fc91  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001fc98  mov     [rsp+68h+dwOptions], esi; dwOptions
0x18001fc9c  mov     [r11-18h], rsi
0x18001fca0  call    cs:__imp_RegCreateKeyExW
0x18001fca6  mov     ebx, eax
0x18001fca8  test    eax, eax
0x18001fcaa  jz      short loc_18001FCBD
0x18001fcac  mov     dword ptr [rsp+68h+samDesired], 182Ch
0x18001fcb4  lea     r8, aFailedToOpenRe_1; "failed to open recovery environment key"
0x18001fcbb  jmp     short loc_18001FD0A
0x18001fcbd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fcc1  inc     rax
0x18001fcc4  cmp     [rdi+rax*2], si
0x18001fcc8  jnz     short loc_18001FCC1
0x18001fcca  mov     rcx, [rsp+68h+hKey]; hKey
0x18001fccf  lea     eax, ds:2[rax*2]
0x18001fcd6  mov     dword ptr [rsp+68h+samDesired], eax; cbData
0x18001fcda  lea     rdx, aOfflinescannin; "OfflineScanningCmdLine"
0x18001fce1  mov     r9d, 1; dwType
0x18001fce7  mov     qword ptr [rsp+68h+dwOptions], rdi; lpData
0x18001fcec  xor     r8d, r8d; Reserved
0x18001fcef  call    cs:__imp_RegSetValueExW
0x18001fcf5  mov     ebx, eax
0x18001fcf7  test    eax, eax
0x18001fcf9  jz      short loc_18001FD2A
0x18001fcfb  mov     dword ptr [rsp+68h+samDesired], 1836h
0x18001fd03  lea     r8, aFailedToSetOff; "failed to set offline scanning command"
0x18001fd0a  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18001fd11  mov     r9d, ebx
0x18001fd14  lea     rdx, aWinreregistero; "winreRegisterOfflineScanningCommand %s "...
0x18001fd1b  mov     qword ptr [rsp+68h+dwOptions], rax
0x18001fd20  mov     ecx, 2
0x18001fd25  call    UnattendLogW
0x18001fd2a  mov     rcx, [rsp+68h+hKey]; hKey
0x18001fd2f  test    rcx, rcx
0x18001fd32  jz      short loc_18001FD3A
0x18001fd34  call    cs:__imp_RegCloseKey
0x18001fd3a  test    ebx, ebx
0x18001fd3c  jz      short loc_18001FD52
0x18001fd3e  mov     r8d, ebx
0x18001fd41  lea     rdx, aFailedToSetOff_0; "failed to set offline scanning command "...
0x18001fd48  mov     ecx, 2
0x18001fd4d  call    UnattendLogW
0x18001fd52  mov     eax, ebx
0x18001fd54  mov     rcx, [rsp+68h+var_10]
0x18001fd59  xor     rcx, rsp; StackCookie
0x18001fd5c  call    __security_check_cookie
0x18001fd61  lea     r11, [rsp+68h+var_8]
0x18001fd66  mov     rbx, [r11+18h]
0x18001fd6a  mov     rsi, [r11+20h]
0x18001fd6e  mov     rsp, r11
0x18001fd71  pop     rdi
0x18001fd72  retn
```
