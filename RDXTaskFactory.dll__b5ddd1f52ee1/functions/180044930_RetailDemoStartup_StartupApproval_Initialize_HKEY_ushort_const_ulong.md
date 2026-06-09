# RetailDemoStartup::StartupApproval::Initialize(HKEY__ *,ushort const *,ulong)

- ea: `0x180044930`
- end: `0x180044a27`
- name: `?Initialize@StartupApproval@RetailDemoStartup@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `247`
- prototype: `int(RetailDemoStartup::StartupApproval *__hidden this, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800446f8`

## callees

- `0x180044930`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800449a1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800449f1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800449a1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800449f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800449fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800449fe`

## pseudocode

```c
LSTATUS __fastcall RetailDemoStartup::StartupApproval::Initialize(
        RetailDemoStartup::StartupApproval *this,
        HKEY a2,
        const unsigned __int16 *a3,
        DWORD a4)
{
  LSTATUS result; // eax
  LSTATUS v7; // ebx
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  DWORD dwDisposition; // [rsp+78h] [rbp+20h] BYREF

  dwDisposition = a4;
  if ( *(_BYTE *)this )
    return 0;
  *((_DWORD *)this + 4) = 2;
  hKey = 0;
  dwDisposition = 0;
  result = RegCreateKeyExW(
             a2,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\StartupApproved",
             0,
             0,
             0,
             0x2001Fu,
             0,
             &hKey,
             &dwDisposition);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v7 = RegCreateKeyExW(hKey, a3, 0, 0, 0, 0x2001Fu, 0, (PHKEY)this + 1, &dwDisposition);
  RegCloseKey(hKey);
  if ( !v7 )
  {
    *(_BYTE *)this = 1;
    return 0;
  }
  if ( v7 > 0 )
    return (unsigned __int16)v7 | 0x80070000;
  return v7;
}

```

## disassembly

```asm
0x180044930  mov     r11, rsp
0x180044933  mov     [r11+10h], rbx
0x180044937  mov     [r11+20h], r9d
0x18004493b  push    rdi
0x18004493c  sub     rsp, 50h
0x180044940  cmp     byte ptr [rcx], 0
0x180044943  mov     rbx, r8
0x180044946  mov     rax, rdx
0x180044949  mov     rdi, rcx
0x18004494c  jnz     loc_180044A1A
0x180044952  mov     dword ptr [rcx+10h], 2
0x180044959  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180044960  lea     rcx, [r11+20h]
0x180044964  mov     qword ptr [r11+8], 0
0x18004496c  mov     [r11-18h], rcx
0x180044970  xor     r9d, r9d; lpClass
0x180044973  lea     rcx, [r11+8]
0x180044977  mov     [rsp+58h+dwDisposition], 0
0x18004497f  mov     [r11-20h], rcx
0x180044983  xor     r8d, r8d; Reserved
0x180044986  mov     qword ptr [r11-28h], 0
0x18004498e  mov     rcx, rax; hKey
0x180044991  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180044999  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800449a1  call    cs:__imp_RegCreateKeyExW
0x1800449a7  test    eax, eax
0x1800449a9  jz      short loc_1800449B7
0x1800449ab  jle     short loc_180044A1C
0x1800449ad  movzx   eax, ax
0x1800449b0  or      eax, 80070000h
0x1800449b5  jmp     short loc_180044A1C
0x1800449b7  lea     rcx, [rsp+58h+dwDisposition]
0x1800449bc  xor     r9d, r9d; lpClass
0x1800449bf  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x1800449c4  lea     rax, [rdi+8]
0x1800449c8  mov     rcx, [rsp+58h+hKey]; hKey
0x1800449cd  xor     r8d, r8d; Reserved
0x1800449d0  mov     [rsp+58h+phkResult], rax; phkResult
0x1800449d5  mov     rdx, rbx; lpSubKey
0x1800449d8  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800449e1  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x1800449e9  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800449f1  call    cs:__imp_RegCreateKeyExW
0x1800449f7  mov     rcx, [rsp+58h+hKey]; hKey
0x1800449fc  mov     ebx, eax
0x1800449fe  call    cs:__imp_RegCloseKey
0x180044a04  test    ebx, ebx
0x180044a06  jz      short loc_180044A17
0x180044a08  jle     short loc_180044A13
0x180044a0a  movzx   ebx, bx
0x180044a0d  or      ebx, 80070000h
0x180044a13  mov     eax, ebx
0x180044a15  jmp     short loc_180044A1C
0x180044a17  mov     byte ptr [rdi], 1
0x180044a1a  xor     eax, eax
0x180044a1c  mov     rbx, [rsp+58h+arg_8]
0x180044a21  add     rsp, 50h
0x180044a25  pop     rdi
0x180044a26  retn
```
