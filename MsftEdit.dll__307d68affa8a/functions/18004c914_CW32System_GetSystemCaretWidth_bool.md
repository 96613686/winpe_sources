# CW32System::GetSystemCaretWidth(bool)

- ea: `0x18004c914`
- end: `0x18004ca59`
- name: `?GetSystemCaretWidth@CW32System@@SAE_N@Z`
- size: `325`
- prototype: `unsigned __int8 __fastcall(bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18004be34`
- `0x18004c0e8`

## callees

- `0x18004c914`
- `0x18013bad0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004c967`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004c967`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18004c9a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18004c9d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18004c9a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18004c9d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c9fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c9fd`
- `ext-ms-win-ntuser-caret-l1-1-0!SetCaretBlinkTime` at `0x18004c9f3`
- `ext-ms-win-ntuser-caret-l1-1-0!SetCaretBlinkTime` at `0x18004c9f3`

## string_xrefs

- `0x18004c9ce`: `CursorBlinkRate`

## pseudocode

```c
__int64 __fastcall CW32System::GetSystemCaretWidth()
{
  unsigned int v0; // ebx
  UINT v1; // ecx
  __int64 v2; // r8
  __int64 result; // rax
  int v4; // r9d
  DWORD cbData; // [rsp+30h] [rbp-20h] BYREF
  DWORD Type; // [rsp+34h] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-10h] BYREF

  hKey = 0;
  v0 = 1;
  Type = 0;
  cbData = 0;
  if ( RegOpenKeyExA(HKEY_CURRENT_USER, "Control Panel\\Desktop", 0, 1u, &hKey) )
    return v0;
  cbData = 4;
  if ( !RegQueryValueExA(hKey, "CaretWidth", 0, &Type, Data, &cbData) && cbData <= 4 )
    v0 = *(_DWORD *)Data;
  cbData = 8;
  if ( !RegQueryValueExA(hKey, "CursorBlinkRate", 0, &Type, Data, &cbData) && cbData <= 8 )
  {
    v1 = 0;
    v2 = 0;
    if ( !cbData )
      goto LABEL_6;
    do
    {
      v4 = Data[v2];
      if ( (unsigned int)(v4 - 48) > 9 )
        break;
      v2 = (unsigned int)(v2 + 1);
      v1 = v4 + 2 * (5 * v1 - 24);
    }
    while ( (unsigned int)v2 < cbData );
    if ( !v1 )
LABEL_6:
      v1 = -1;
    SetCaretBlinkTime(v1);
  }
  RegCloseKey(hKey);
  result = 255;
  if ( v0 < 0xFF )
    return v0;
  return result;
}

```

## disassembly

```asm
0x18004c914  mov     [rsp-8+arg_0], rbx
0x18004c919  push    rbp
0x18004c91a  mov     rbp, rsp
0x18004c91d  sub     rsp, 50h
0x18004c921  mov     rax, cs:__security_cookie
0x18004c928  xor     rax, rsp
0x18004c92b  mov     [rbp+var_8], rax
0x18004c92f  lea     rax, [rbp+hKey]
0x18004c933  mov     [rbp+hKey], 0
0x18004c93b  mov     ebx, 1
0x18004c940  mov     [rbp+Type], 0
0x18004c947  mov     r9d, ebx; samDesired
0x18004c94a  mov     [rbp+cbData], 0
0x18004c951  xor     r8d, r8d; ulOptions
0x18004c954  mov     [rsp+50h+phkResult], rax; phkResult
0x18004c959  lea     rdx, aControlPanelDe; "Control Panel\\Desktop"
0x18004c960  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18004c967  call    cs:__imp_RegOpenKeyExA
0x18004c96d  test    eax, eax
0x18004c96f  jnz     loc_18004CA0C
0x18004c975  mov     rcx, [rbp+hKey]; hKey
0x18004c979  lea     rax, [rbp+cbData]
0x18004c97d  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18004c982  lea     r9, [rbp+Type]; lpType
0x18004c986  lea     rax, [rbp+Data]
0x18004c98a  mov     [rbp+cbData], 4
0x18004c991  xor     r8d, r8d; lpReserved
0x18004c994  mov     [rsp+50h+phkResult], rax; lpData
0x18004c999  lea     rdx, aCaretwidth; "CaretWidth"
0x18004c9a0  call    cs:__imp_RegQueryValueExA
0x18004c9a6  test    eax, eax
0x18004c9a8  jz      short loc_18004CA25
0x18004c9aa  mov     rcx, [rbp+hKey]; hKey
0x18004c9ae  lea     rax, [rbp+cbData]
0x18004c9b2  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18004c9b7  lea     r9, [rbp+Type]; lpType
0x18004c9bb  lea     rax, [rbp+Data]
0x18004c9bf  mov     [rbp+cbData], 8
0x18004c9c6  xor     r8d, r8d; lpReserved
0x18004c9c9  mov     [rsp+50h+phkResult], rax; lpData
0x18004c9ce  lea     rdx, aCursorblinkrat; "CursorBlinkRate"
0x18004c9d5  call    cs:__imp_RegQueryValueExA
0x18004c9db  test    eax, eax
0x18004c9dd  jnz     short loc_18004C9F9
0x18004c9df  mov     edx, [rbp+cbData]
0x18004c9e2  cmp     edx, 8
0x18004c9e5  ja      short loc_18004C9F9
0x18004c9e7  xor     ecx, ecx
0x18004c9e9  xor     r8d, r8d
0x18004c9ec  test    edx, edx
0x18004c9ee  jnz     short loc_18004CA32
0x18004c9f0  or      ecx, 0FFFFFFFFh; uMSeconds
0x18004c9f3  call    cs:__imp_SetCaretBlinkTime
0x18004c9f9  mov     rcx, [rbp+hKey]; hKey
0x18004c9fd  call    cs:__imp_RegCloseKey
0x18004ca03  mov     eax, 0FFh
0x18004ca08  cmp     ebx, eax
0x18004ca0a  jnb     short loc_18004CA0E
0x18004ca0c  mov     eax, ebx
0x18004ca0e  mov     rcx, [rbp+var_8]
0x18004ca12  xor     rcx, rsp; StackCookie
0x18004ca15  call    __security_check_cookie
0x18004ca1a  mov     rbx, [rsp+50h+arg_0]
0x18004ca1f  add     rsp, 50h
0x18004ca23  pop     rbp
0x18004ca24  retn
0x18004ca25  cmp     [rbp+cbData], 4
0x18004ca29  cmovbe  ebx, dword ptr [rbp+Data]
0x18004ca2d  jmp     loc_18004C9AA
0x18004ca32  movzx   r9d, [rbp+r8+Data]
0x18004ca38  lea     eax, [r9-30h]
0x18004ca3c  cmp     eax, 9
0x18004ca3f  ja      short loc_18004CA53
0x18004ca41  lea     ecx, [rcx+rcx*4]
0x18004ca44  inc     r8d
0x18004ca47  lea     ecx, [rcx-18h]
0x18004ca4a  lea     ecx, [r9+rcx*2]
0x18004ca4e  cmp     r8d, edx
0x18004ca51  jb      short loc_18004CA32
0x18004ca53  test    ecx, ecx
0x18004ca55  jnz     short loc_18004C9F3
0x18004ca57  jmp     short loc_18004C9F0
```
