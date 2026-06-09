# DeleteAllValuesInKey(HKEY__ *,ushort const *)

- ea: `0x1800185b4`
- end: `0x1800186e8`
- name: `?DeleteAllValuesInKey@@YAJPEAUHKEY__@@PEBG@Z`
- size: `308`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ccf0`

## callees

- `0x1800185b4`
- `0x180019760`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800186a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800186a0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180018639`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180018639`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018606`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018606`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180018682`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180018682`

## pseudocode

```c
LSTATUS __fastcall DeleteAllValuesInKey(HKEY a1, const unsigned __int16 *a2)
{
  LSTATUS result; // eax
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  int v6; // ebx
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR ValueName[264]; // [rsp+50h] [rbp-B0h] BYREF

  if ( !a2 )
    return -2147024809;
  hKey = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x2011Bu, &hKey);
  if ( result == 2 )
    return 0;
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    do
    {
      cchValueName = 260;
      v5 = RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, 0, 0, 0);
      v4 = v5;
      if ( v5 )
      {
        if ( v5 <= 0 )
          goto LABEL_12;
        v6 = (unsigned __int16)v5;
        goto LABEL_11;
      }
      v3 = RegDeleteValueW(hKey, ValueName);
      v4 = v3;
    }
    while ( !v3 );
    if ( v3 > 0 )
    {
      v6 = (unsigned __int16)v3;
LABEL_11:
      v4 = v6 | 0x80070000;
    }
LABEL_12:
    RegCloseKey(hKey);
    if ( v4 == -2147024637 || v4 == -2147024894 )
      return 0;
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800185b4  mov     [rsp-8+arg_0], rbx
0x1800185b9  push    rbp
0x1800185ba  lea     rbp, [rsp-170h]
0x1800185c2  sub     rsp, 270h
0x1800185c9  mov     rax, cs:__security_cookie
0x1800185d0  xor     rax, rsp
0x1800185d3  mov     [rbp+170h+var_10], rax
0x1800185da  test    rdx, rdx
0x1800185dd  jz      loc_1800186C3
0x1800185e3  lea     rax, [rsp+270h+hKey]
0x1800185e8  mov     [rsp+270h+hKey], 0
0x1800185f1  mov     r9d, 2011Bh; samDesired
0x1800185f7  mov     [rsp+270h+phkResult], rax; phkResult
0x1800185fc  xor     r8d, r8d; ulOptions
0x1800185ff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018606  call    cs:__imp_RegOpenKeyExW
0x18001860c  cmp     eax, 2
0x18001860f  jnz     short loc_180018618
0x180018611  xor     eax, eax
0x180018613  jmp     loc_1800186C8
0x180018618  test    eax, eax
0x18001861a  jz      short loc_180018645
0x18001861c  jle     loc_1800186C8
0x180018622  movzx   eax, ax
0x180018625  or      eax, 80070000h
0x18001862a  jmp     loc_1800186C8
0x18001862f  mov     rcx, [rsp+270h+hKey]; hKey
0x180018634  lea     rdx, [rsp+270h+ValueName]; lpValueName
0x180018639  call    cs:__imp_RegDeleteValueW
0x18001863f  mov     ebx, eax
0x180018641  test    eax, eax
0x180018643  jnz     short loc_1800186BC
0x180018645  mov     rcx, [rsp+270h+hKey]; hKey
0x18001864a  lea     r9, [rsp+270h+cchValueName]; lpcchValueName
0x18001864f  mov     [rsp+270h+lpcbData], 0; lpcbData
0x180018658  lea     r8, [rsp+270h+ValueName]; lpValueName
0x18001865d  mov     [rsp+270h+lpData], 0; lpData
0x180018666  xor     edx, edx; dwIndex
0x180018668  mov     [rsp+270h+lpType], 0; lpType
0x180018671  mov     [rsp+270h+phkResult], 0; lpReserved
0x18001867a  mov     [rsp+270h+cchValueName], 104h
0x180018682  call    cs:__imp_RegEnumValueW
0x180018688  mov     ebx, eax
0x18001868a  test    eax, eax
0x18001868c  jz      short loc_18001862F
0x18001868e  test    eax, eax
0x180018690  jle     short loc_18001869B
0x180018692  movzx   ebx, bx
0x180018695  or      ebx, 80070000h
0x18001869b  mov     rcx, [rsp+270h+hKey]; hKey
0x1800186a0  call    cs:__imp_RegCloseKey
0x1800186a6  cmp     ebx, 80070103h
0x1800186ac  jz      short loc_1800186B6
0x1800186ae  cmp     ebx, 80070002h
0x1800186b4  jnz     short loc_1800186B8
0x1800186b6  xor     ebx, ebx
0x1800186b8  mov     eax, ebx
0x1800186ba  jmp     short loc_1800186C8
0x1800186bc  jle     short loc_18001869B
0x1800186be  movzx   ebx, ax
0x1800186c1  jmp     short loc_180018695
0x1800186c3  mov     eax, 80070057h
0x1800186c8  mov     rcx, [rbp+170h+var_10]
0x1800186cf  xor     rcx, rsp; StackCookie
0x1800186d2  call    __security_check_cookie
0x1800186d7  mov     rbx, [rsp+270h+arg_0]
0x1800186df  add     rsp, 270h
0x1800186e6  pop     rbp
0x1800186e7  retn
```
