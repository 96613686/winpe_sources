# PuLoadDebugFlagsFromRegStr

- ea: `0x1800344ac`
- end: `0x180034550`
- name: `PuLoadDebugFlagsFromRegStr`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180034558`

## callees

- `0x1800344ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034541`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034541`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800344eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800344eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003452b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003452b`

## string_xrefs

- `0x1800344d8`: `System\CurrentControlSet\Services\W3SVC\Parameters\IisUtil`

## pseudocode

```c
__int64 __fastcall PuLoadDebugFlagsFromRegStr(__int64 a1, DWORD a2)
{
  unsigned int v2; // ebx
  __int64 Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  Type = a2;
  Data = a1;
  hKey = 0;
  v2 = 8;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\IisUtil",
          0,
          0x20019u,
          &hKey) )
  {
    LODWORD(Data) = 0;
    cbData = 4;
    Type = 0;
    if ( hKey && !RegQueryValueExA(hKey, "DebugFlags", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      v2 = Data;
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x1800344ac  mov     [rsp-10h+Type], edx
0x1800344b0  mov     [rsp-10h+Data], rcx
0x1800344b5  push    rbp
0x1800344b6  push    rbx
0x1800344b7  mov     rbp, rsp
0x1800344ba  sub     rsp, 38h
0x1800344be  lea     rax, [rbp+hKey]
0x1800344c2  mov     [rbp+hKey], 0
0x1800344ca  mov     r9d, 20019h; samDesired
0x1800344d0  mov     [rsp+38h+phkResult], rax; phkResult
0x1800344d5  xor     r8d, r8d; ulOptions
0x1800344d8  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\W3"...
0x1800344df  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800344e6  mov     ebx, 8
0x1800344eb  call    cs:__imp_RegOpenKeyExA
0x1800344f1  test    eax, eax
0x1800344f3  jnz     short loc_180034547
0x1800344f5  mov     rcx, [rbp+hKey]; hKey
0x1800344f9  mov     dword ptr [rbp+Data], eax
0x1800344fc  mov     [rbp+cbData], 4
0x180034503  mov     [rbp+Type], eax
0x180034506  test    rcx, rcx
0x180034509  jz      short loc_18003453D
0x18003450b  lea     rax, [rbp+cbData]
0x18003450f  xor     r8d, r8d; lpReserved
0x180034512  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180034517  lea     r9, [rbp+Type]; lpType
0x18003451b  lea     rax, [rbp+Data]
0x18003451f  lea     rdx, aDebugflags; "DebugFlags"
0x180034526  mov     [rsp+38h+phkResult], rax; lpData
0x18003452b  call    cs:__imp_RegQueryValueExA
0x180034531  test    eax, eax
0x180034533  jnz     short loc_18003453D
0x180034535  cmp     [rbp+Type], 4
0x180034539  cmovz   ebx, dword ptr [rbp+Data]
0x18003453d  mov     rcx, [rbp+hKey]; hKey
0x180034541  call    cs:__imp_RegCloseKey
0x180034547  mov     eax, ebx
0x180034549  add     rsp, 38h
0x18003454d  pop     rbx
0x18003454e  pop     rbp
0x18003454f  retn
```
