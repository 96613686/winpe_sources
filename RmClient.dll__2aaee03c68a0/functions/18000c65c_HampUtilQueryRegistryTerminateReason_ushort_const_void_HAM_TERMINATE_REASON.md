# HampUtilQueryRegistryTerminateReason(ushort const *,void *,_HAM_TERMINATE_REASON *)

- ea: `0x18000c65c`
- end: `0x18000c762`
- name: `?HampUtilQueryRegistryTerminateReason@@YAJPEBGPEAXPEAW4_HAM_TERMINATE_REASON@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *, enum _HAM_TERMINATE_REASON *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000c340`

## callees

- `0x18000c65c`
- `0x18000c768`
- `0x18001aec0`

## import_xrefs

- `api-ms-win-core-psm-key-l1-1-3!PsmGetAumidFromKey` at `0x18000c6ab`
- `api-ms-win-core-psm-key-l1-1-3!PsmGetAumidFromKey` at `0x18000c6ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c743`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c743`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c6f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c6f0`

## pseudocode

```c
__int64 __fastcall HampUtilQueryRegistryTerminateReason(
        const unsigned __int16 *a1,
        void *a2,
        enum _HAM_TERMINATE_REASON *a3)
{
  __int64 v5; // rdx
  int v6; // ebx
  LSTATUS v7; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  int v12[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ValueName[136]; // [rsp+50h] [rbp-B0h] BYREF

  cbData = 0;
  *(_DWORD *)Data = 0;
  hKey = 0;
  v12[0] = 130;
  PsmGetAumidFromKey(a1, v12, ValueName);
  v6 = HampUtilCreateVolatileUserRegKey(a2, v5, &hKey);
  if ( v6 >= 0 )
  {
    cbData = 4;
    v7 = RegQueryValueExW(hKey, ValueName, 0, 0, Data, &cbData);
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0xC0070000;
    if ( v6 < 0 )
    {
      if ( v6 != -1073283070 )
        goto LABEL_12;
      *(_DWORD *)a3 = 0;
      goto LABEL_10;
    }
    if ( *(_DWORD *)Data <= 0x1AFFu && cbData == 4 )
    {
      *(_DWORD *)a3 = *(_DWORD *)Data;
LABEL_10:
      v6 = 0;
      goto LABEL_12;
    }
    v6 = -1073739509;
  }
LABEL_12:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000c65c  push    rbp
0x18000c65e  push    rbx
0x18000c65f  push    rsi
0x18000c660  lea     rbp, [rsp-70h]
0x18000c665  sub     rsp, 170h
0x18000c66c  mov     rax, cs:__security_cookie
0x18000c673  xor     rax, rsp
0x18000c676  mov     [rbp+80h+var_20], rax
0x18000c67a  mov     rsi, r8
0x18000c67d  mov     [rsp+180h+cbData], 0
0x18000c685  mov     rbx, rdx
0x18000c688  mov     dword ptr [rsp+180h+Data], 0
0x18000c690  lea     r8, [rsp+180h+ValueName]
0x18000c695  mov     [rsp+180h+hKey], 0
0x18000c69e  lea     rdx, [rsp+180h+var_140]
0x18000c6a3  mov     [rsp+180h+var_140], 82h
0x18000c6ab  call    cs:__imp_PsmGetAumidFromKey
0x18000c6b1  lea     r8, [rsp+180h+hKey]; HKEY *
0x18000c6b6  mov     rcx, rbx; Sid
0x18000c6b9  call    ?HampUtilCreateVolatileUserRegKey@@YAJPEAXKPEAPEAUHKEY__@@@Z; HampUtilCreateVolatileUserRegKey(void *,ulong,HKEY__ * *)
0x18000c6be  mov     ebx, eax
0x18000c6c0  test    eax, eax
0x18000c6c2  js      short loc_18000C736
0x18000c6c4  mov     rcx, [rsp+180h+hKey]; hKey
0x18000c6c9  lea     rax, [rsp+180h+cbData]
0x18000c6ce  mov     [rsp+180h+lpcbData], rax; lpcbData
0x18000c6d3  lea     rdx, [rsp+180h+ValueName]; lpValueName
0x18000c6d8  lea     rax, [rsp+180h+Data]
0x18000c6dd  mov     [rsp+180h+cbData], 4
0x18000c6e5  xor     r9d, r9d; lpType
0x18000c6e8  mov     [rsp+180h+lpData], rax; lpData
0x18000c6ed  xor     r8d, r8d; lpReserved
0x18000c6f0  call    cs:__imp_RegQueryValueExW
0x18000c6f6  mov     ebx, eax
0x18000c6f8  test    eax, eax
0x18000c6fa  jle     short loc_18000C705
0x18000c6fc  movzx   ebx, ax
0x18000c6ff  or      ebx, 0C0070000h
0x18000c705  test    ebx, ebx
0x18000c707  jns     short loc_18000C719
0x18000c709  cmp     ebx, 0C0070002h
0x18000c70f  jnz     short loc_18000C736
0x18000c711  mov     dword ptr [rsi], 0
0x18000c717  jmp     short loc_18000C72D
0x18000c719  mov     eax, dword ptr [rsp+180h+Data]
0x18000c71d  cmp     eax, 1AFFh
0x18000c722  ja      short loc_18000C731
0x18000c724  cmp     [rsp+180h+cbData], 4
0x18000c729  jnz     short loc_18000C731
0x18000c72b  mov     [rsi], eax
0x18000c72d  xor     ebx, ebx
0x18000c72f  jmp     short loc_18000C736
0x18000c731  mov     ebx, 0C000090Bh
0x18000c736  cmp     [rsp+180h+hKey], 0
0x18000c73c  jz      short loc_18000C749
0x18000c73e  mov     rcx, [rsp+180h+hKey]; hKey
0x18000c743  call    cs:__imp_RegCloseKey
0x18000c749  mov     eax, ebx
0x18000c74b  mov     rcx, [rbp+80h+var_20]
0x18000c74f  xor     rcx, rsp; StackCookie
0x18000c752  call    __security_check_cookie
0x18000c757  add     rsp, 170h
0x18000c75e  pop     rsi
0x18000c75f  pop     rbx
0x18000c760  pop     rbp
0x18000c761  retn
```
