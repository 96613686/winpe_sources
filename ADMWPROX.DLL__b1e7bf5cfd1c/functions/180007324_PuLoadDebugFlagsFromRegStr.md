# PuLoadDebugFlagsFromRegStr

- ea: `0x180007324`
- end: `0x1800073c0`
- name: `PuLoadDebugFlagsFromRegStr`
- size: `156`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002400`
- `0x180006bcc`

## callees

- `0x180007324`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800073ad`
- `ADVAPI32!RegCloseKey` at `0x1800073ad`
- `ADVAPI32!RegQueryValueExA` at `0x180007397`
- `ADVAPI32!RegQueryValueExA` at `0x180007397`
- `ADVAPI32!RegOpenKeyExA` at `0x180007357`
- `ADVAPI32!RegOpenKeyExA` at `0x180007357`

## pseudocode

```c
__int64 __fastcall PuLoadDebugFlagsFromRegStr(LPCSTR lpSubKey, unsigned int a2)
{
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+58h] [rbp+18h] BYREF
  unsigned int Data; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey) )
  {
    Data = 0;
    cbData = 4;
    Type = 0;
    if ( hKey && !RegQueryValueExA(hKey, "DebugFlags", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      a2 = Data;
    RegCloseKey(hKey);
  }
  return a2;
}

```

## disassembly

```asm
0x180007324  mov     [rsp-8+arg_0], rbx
0x180007329  push    rbp
0x18000732a  mov     rbp, rsp
0x18000732d  sub     rsp, 40h
0x180007331  mov     ebx, edx
0x180007333  mov     [rbp+hKey], 0
0x18000733b  mov     rdx, rcx; lpSubKey
0x18000733e  lea     rax, [rbp+hKey]
0x180007342  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007349  mov     [rsp+40h+phkResult], rax; phkResult
0x18000734e  mov     r9d, 20019h; samDesired
0x180007354  xor     r8d, r8d; ulOptions
0x180007357  call    cs:__imp_RegOpenKeyExA
0x18000735d  test    eax, eax
0x18000735f  jnz     short loc_1800073B3
0x180007361  mov     rcx, [rbp+hKey]; hKey
0x180007365  mov     [rbp+Data], eax
0x180007368  mov     [rbp+cbData], 4
0x18000736f  mov     [rbp+Type], eax
0x180007372  test    rcx, rcx
0x180007375  jz      short loc_1800073A9
0x180007377  lea     rax, [rbp+cbData]
0x18000737b  xor     r8d, r8d; lpReserved
0x18000737e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180007383  lea     r9, [rbp+Type]; lpType
0x180007387  lea     rax, [rbp+Data]
0x18000738b  lea     rdx, aDebugflags; "DebugFlags"
0x180007392  mov     [rsp+40h+phkResult], rax; lpData
0x180007397  call    cs:__imp_RegQueryValueExA
0x18000739d  test    eax, eax
0x18000739f  jnz     short loc_1800073A9
0x1800073a1  cmp     [rbp+Type], 4
0x1800073a5  cmovz   ebx, [rbp+Data]
0x1800073a9  mov     rcx, [rbp+hKey]; hKey
0x1800073ad  call    cs:__imp_RegCloseKey
0x1800073b3  mov     eax, ebx
0x1800073b5  mov     rbx, [rsp+40h+arg_0]
0x1800073ba  add     rsp, 40h
0x1800073be  pop     rbp
0x1800073bf  retn
```
