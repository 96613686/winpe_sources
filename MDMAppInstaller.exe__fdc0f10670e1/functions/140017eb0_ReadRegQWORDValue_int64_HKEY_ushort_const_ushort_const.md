# ReadRegQWORDValue(__int64 *,HKEY__ *,ushort const *,ushort const *)

- ea: `0x140017eb0`
- end: `0x140017fb4`
- name: `?ReadRegQWORDValue@@YAJPEA_JPEAUHKEY__@@PEBG2@Z`
- size: `260`
- prototype: `__int64 __fastcall(LPBYTE lpData, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140019054`

## callees

- `0x1400074d4`
- `0x140017eb0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140017f17`
- `ADVAPI32!RegOpenKeyExW` at `0x140017f17`
- `ADVAPI32!RegCloseKey` at `0x140017f97`
- `ADVAPI32!RegCloseKey` at `0x140017f97`
- `ADVAPI32!RegQueryValueExW` at `0x140017f5d`
- `ADVAPI32!RegQueryValueExW` at `0x140017f5d`
- `KERNEL32!SetLastError` at `0x140017f9f`
- `KERNEL32!SetLastError` at `0x140017f9f`

## string_xrefs

- `0x140017f33`: `RegOpenKeyExW for subkey %1 failed with Status = %2!d!.`

## pseudocode

```c
__int64 __fastcall ReadRegQWORDValue(LPBYTE lpData, HKEY a2, const unsigned __int16 *a3, const unsigned __int16 *a4)
{
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  DWORD Type; // [rsp+60h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+10h] BYREF
  int v14; // [rsp+6Ch] [rbp+14h]

  v14 = HIDWORD(a2);
  hKey = 0;
  Type = 11;
  cbData = 8;
  if ( !lpData || !a3 || !a4 )
  {
    v7 = -2147024809;
    goto LABEL_17;
  }
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x101u, &hKey);
  if ( v8 )
  {
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    else
      v7 = v8;
    LogInfo(L"RegOpenKeyExW for subkey %1 failed with Status = %2!d!.", a3, (unsigned int)v8);
    goto LABEL_15;
  }
  v7 = 0;
  v9 = RegQueryValueExW(hKey, a4, 0, &Type, lpData, &cbData);
  if ( v9 )
  {
    if ( v9 > 0 )
    {
      v7 = (unsigned __int16)v9 | 0x80070000;
      if ( v9 == 2 )
        goto LABEL_15;
    }
    else
    {
      v7 = v9;
    }
    LogInfo(L"RegQueryValueExW for %1 failed with Status = %2!d!.", a4, (unsigned int)v9);
  }
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_17:
  SetLastError(0);
  return v7;
}

```

## disassembly

```asm
0x140017eb0  mov     rax, rsp
0x140017eb3  mov     [rax+18h], rbx
0x140017eb7  mov     [rax+10h], rdx
0x140017ebb  push    rbp
0x140017ebc  push    rsi
0x140017ebd  push    rdi
0x140017ebe  sub     rsp, 40h
0x140017ec2  mov     qword ptr [rax-28h], 0
0x140017eca  mov     rsi, r9
0x140017ecd  mov     dword ptr [rax+8], 0Bh
0x140017ed4  mov     rdi, r8
0x140017ed7  mov     dword ptr [rax+10h], 8
0x140017ede  mov     rbp, rcx
0x140017ee1  test    rcx, rcx
0x140017ee4  jnz     short loc_140017EF0
0x140017ee6  mov     ebx, 80070057h
0x140017eeb  jmp     loc_140017F9D
0x140017ef0  test    rdi, rdi
0x140017ef3  jz      short loc_140017EE6
0x140017ef5  test    rsi, rsi
0x140017ef8  jz      short loc_140017EE6
0x140017efa  lea     rax, [rsp+58h+hKey]
0x140017eff  mov     r9d, 101h; samDesired
0x140017f05  xor     r8d, r8d; ulOptions
0x140017f08  mov     [rsp+58h+phkResult], rax; phkResult
0x140017f0d  mov     rdx, rdi; lpSubKey
0x140017f10  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140017f17  call    cs:__imp_RegOpenKeyExW
0x140017f1d  test    eax, eax
0x140017f1f  jz      short loc_140017F3C
0x140017f21  jg      short loc_140017F27
0x140017f23  mov     ebx, eax
0x140017f25  jmp     short loc_140017F30
0x140017f27  movzx   ebx, ax
0x140017f2a  or      ebx, 80070000h
0x140017f30  mov     rdx, rdi
0x140017f33  lea     rcx, aRegopenkeyexwF; "RegOpenKeyExW for subkey %1 failed with"...
0x140017f3a  jmp     short loc_140017F85
0x140017f3c  mov     rcx, [rsp+58h+hKey]; hKey
0x140017f41  lea     rax, [rsp+58h+cbData]
0x140017f46  mov     [rsp+58h+lpcbData], rax; lpcbData
0x140017f4b  lea     r9, [rsp+58h+Type]; lpType
0x140017f50  xor     r8d, r8d; lpReserved
0x140017f53  mov     [rsp+58h+phkResult], rbp; lpData
0x140017f58  mov     rdx, rsi; lpValueName
0x140017f5b  xor     ebx, ebx
0x140017f5d  call    cs:__imp_RegQueryValueExW
0x140017f63  test    eax, eax
0x140017f65  jz      short loc_140017F8D
0x140017f67  jg      short loc_140017F6D
0x140017f69  mov     ebx, eax
0x140017f6b  jmp     short loc_140017F7B
0x140017f6d  movzx   ebx, ax
0x140017f70  or      ebx, 80070000h
0x140017f76  cmp     eax, 2
0x140017f79  jz      short loc_140017F8D
0x140017f7b  mov     rdx, rsi
0x140017f7e  lea     rcx, aRegqueryvaluee; "RegQueryValueExW for %1 failed with Sta"...
0x140017f85  mov     r8d, eax
0x140017f88  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140017f8d  mov     rcx, [rsp+58h+hKey]; hKey
0x140017f92  test    rcx, rcx
0x140017f95  jz      short loc_140017F9D
0x140017f97  call    cs:__imp_RegCloseKey
0x140017f9d  xor     ecx, ecx; dwErrCode
0x140017f9f  call    cs:__imp_SetLastError
0x140017fa5  mov     eax, ebx
0x140017fa7  mov     rbx, [rsp+58h+arg_10]
0x140017fac  add     rsp, 40h
0x140017fb0  pop     rdi
0x140017fb1  pop     rsi
0x140017fb2  pop     rbp
0x140017fb3  retn
```
