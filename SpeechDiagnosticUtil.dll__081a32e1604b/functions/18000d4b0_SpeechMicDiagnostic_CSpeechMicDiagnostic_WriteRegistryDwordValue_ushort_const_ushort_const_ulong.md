# SpeechMicDiagnostic::CSpeechMicDiagnostic::WriteRegistryDwordValue(ushort const *,ushort const *,ulong)

- ea: `0x18000d4b0`
- end: `0x18000d577`
- name: `?WriteRegistryDwordValue@CSpeechMicDiagnostic@SpeechMicDiagnostic@@AEAAJPEBG0K@Z`
- size: `199`
- prototype: `int(SpeechMicDiagnostic::CSpeechMicDiagnostic *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d3f8`

## callees

- `0x18000989c`
- `0x18000d4b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d541`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d541`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d4e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d4e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d511`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d562`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d511`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d562`

## pseudocode

```c
__int64 __fastcall SpeechMicDiagnostic::CSpeechMicDiagnostic::WriteRegistryDwordValue(
        SpeechMicDiagnostic::CSpeechMicDiagnostic *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  unsigned int v5; // eax
  unsigned int v6; // r8d
  __int64 v7; // rdx
  unsigned int v8; // ebx
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+58h] [rbp+20h] BYREF

  Data = a4;
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x2001Fu, &hKey);
  if ( v5 )
  {
    v7 = 468;
LABEL_3:
    v8 = wil::details::in1diag3::Return_Win32(retaddr, (void *)v7, v6, (const char *)v5, lpData);
    if ( hKey )
      RegCloseKey(hKey);
    return v8;
  }
  v5 = RegSetValueExW(hKey, a3, 0, 4u, (const BYTE *)&Data, 4u);
  if ( v5 )
  {
    v7 = 472;
    goto LABEL_3;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18000d4b0  mov     r11, rsp
0x18000d4b3  mov     [r11+20h], r9d
0x18000d4b7  mov     [r11+8], rcx
0x18000d4bb  push    rbx
0x18000d4bc  sub     rsp, 30h
0x18000d4c0  mov     rbx, r8
0x18000d4c3  mov     qword ptr [r11+8], 0
0x18000d4cb  lea     rax, [r11+8]
0x18000d4cf  xor     r8d, r8d; ulOptions
0x18000d4d2  mov     r9d, 2001Fh; samDesired
0x18000d4d8  mov     [r11-18h], rax
0x18000d4dc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d4e3  call    cs:__imp_RegOpenKeyExW
0x18000d4ea  nop     dword ptr [rax+rax+00h]
0x18000d4ef  test    eax, eax
0x18000d4f1  jz      short loc_18000D521
0x18000d4f3  mov     edx, 1D4h; void *
0x18000d4f8  mov     rcx, [rsp+38h]; this
0x18000d4fd  mov     r9d, eax; char *
0x18000d500  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000d505  mov     rcx, [rsp+38h+hKey]; hKey
0x18000d50a  mov     ebx, eax
0x18000d50c  test    rcx, rcx
0x18000d50f  jz      short loc_18000D51D
0x18000d511  call    cs:__imp_RegCloseKey
0x18000d518  nop     dword ptr [rax+rax+00h]
0x18000d51d  mov     eax, ebx
0x18000d51f  jmp     short loc_18000D570
0x18000d521  mov     rcx, [rsp+38h+hKey]; hKey
0x18000d526  lea     rax, [rsp+38h+Data]
0x18000d52b  mov     r9d, 4; dwType
0x18000d531  xor     r8d, r8d; Reserved
0x18000d534  mov     [rsp+38h+cbData], r9d; cbData
0x18000d539  mov     rdx, rbx; lpValueName
0x18000d53c  mov     [rsp+38h+lpData], rax; lpData
0x18000d541  call    cs:__imp_RegSetValueExW
0x18000d548  nop     dword ptr [rax+rax+00h]
0x18000d54d  test    eax, eax
0x18000d54f  jz      short loc_18000D558
0x18000d551  mov     edx, 1D8h
0x18000d556  jmp     short loc_18000D4F8
0x18000d558  mov     rcx, [rsp+38h+hKey]; hKey
0x18000d55d  test    rcx, rcx
0x18000d560  jz      short loc_18000D56E
0x18000d562  call    cs:__imp_RegCloseKey
0x18000d569  nop     dword ptr [rax+rax+00h]
0x18000d56e  xor     eax, eax
0x18000d570  add     rsp, 30h
0x18000d574  pop     rbx
0x18000d575  retn
```
