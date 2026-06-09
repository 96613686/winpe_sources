# ReadRegDWORDValue(ulong *,HKEY__ *,ushort const *,ushort const *)

- ea: `0x140017b90`
- end: `0x140017c93`
- name: `?ReadRegDWORDValue@@YAJPEAKPEAUHKEY__@@PEBG2@Z`
- size: `259`
- prototype: `__int64 __fastcall(LPBYTE lpData, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140006dc8`
- `0x140019054`

## callees

- `0x1400074d4`
- `0x140017b90`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140017bf6`
- `ADVAPI32!RegOpenKeyExW` at `0x140017bf6`
- `ADVAPI32!RegCloseKey` at `0x140017c76`
- `ADVAPI32!RegCloseKey` at `0x140017c76`
- `ADVAPI32!RegQueryValueExW` at `0x140017c3c`
- `ADVAPI32!RegQueryValueExW` at `0x140017c3c`
- `KERNEL32!SetLastError` at `0x140017c7e`
- `KERNEL32!SetLastError` at `0x140017c7e`

## string_xrefs

- `0x140017c12`: `RegOpenKeyExW for subkey %1 failed with Status = %2!d!.`

## pseudocode

```c
__int64 __fastcall ReadRegDWORDValue(LPBYTE lpData, HKEY a2, const unsigned __int16 *a3, const unsigned __int16 *a4)
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
  Type = 4;
  cbData = 4;
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
0x140017b90  mov     [rsp+arg_10], rbx
0x140017b95  mov     qword ptr [rsp+cbData], rdx
0x140017b9a  push    rbp
0x140017b9b  push    rsi
0x140017b9c  push    rdi
0x140017b9d  sub     rsp, 40h
0x140017ba1  mov     [rsp+58h+hKey], 0
0x140017baa  mov     eax, 4
0x140017baf  mov     [rsp+58h+Type], eax
0x140017bb3  mov     rsi, r9
0x140017bb6  mov     [rsp+58h+cbData], eax
0x140017bba  mov     rdi, r8
0x140017bbd  mov     rbp, rcx
0x140017bc0  test    rcx, rcx
0x140017bc3  jnz     short loc_140017BCF
0x140017bc5  mov     ebx, 80070057h
0x140017bca  jmp     loc_140017C7C
0x140017bcf  test    rdi, rdi
0x140017bd2  jz      short loc_140017BC5
0x140017bd4  test    rsi, rsi
0x140017bd7  jz      short loc_140017BC5
0x140017bd9  lea     rax, [rsp+58h+hKey]
0x140017bde  mov     r9d, 101h; samDesired
0x140017be4  xor     r8d, r8d; ulOptions
0x140017be7  mov     [rsp+58h+phkResult], rax; phkResult
0x140017bec  mov     rdx, rdi; lpSubKey
0x140017bef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140017bf6  call    cs:__imp_RegOpenKeyExW
0x140017bfc  test    eax, eax
0x140017bfe  jz      short loc_140017C1B
0x140017c00  jg      short loc_140017C06
0x140017c02  mov     ebx, eax
0x140017c04  jmp     short loc_140017C0F
0x140017c06  movzx   ebx, ax
0x140017c09  or      ebx, 80070000h
0x140017c0f  mov     rdx, rdi
0x140017c12  lea     rcx, aRegopenkeyexwF; "RegOpenKeyExW for subkey %1 failed with"...
0x140017c19  jmp     short loc_140017C64
0x140017c1b  mov     rcx, [rsp+58h+hKey]; hKey
0x140017c20  lea     rax, [rsp+58h+cbData]
0x140017c25  mov     [rsp+58h+lpcbData], rax; lpcbData
0x140017c2a  lea     r9, [rsp+58h+Type]; lpType
0x140017c2f  xor     r8d, r8d; lpReserved
0x140017c32  mov     [rsp+58h+phkResult], rbp; lpData
0x140017c37  mov     rdx, rsi; lpValueName
0x140017c3a  xor     ebx, ebx
0x140017c3c  call    cs:__imp_RegQueryValueExW
0x140017c42  test    eax, eax
0x140017c44  jz      short loc_140017C6C
0x140017c46  jg      short loc_140017C4C
0x140017c48  mov     ebx, eax
0x140017c4a  jmp     short loc_140017C5A
0x140017c4c  movzx   ebx, ax
0x140017c4f  or      ebx, 80070000h
0x140017c55  cmp     eax, 2
0x140017c58  jz      short loc_140017C6C
0x140017c5a  mov     rdx, rsi
0x140017c5d  lea     rcx, aRegqueryvaluee; "RegQueryValueExW for %1 failed with Sta"...
0x140017c64  mov     r8d, eax
0x140017c67  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140017c6c  mov     rcx, [rsp+58h+hKey]; hKey
0x140017c71  test    rcx, rcx
0x140017c74  jz      short loc_140017C7C
0x140017c76  call    cs:__imp_RegCloseKey
0x140017c7c  xor     ecx, ecx; dwErrCode
0x140017c7e  call    cs:__imp_SetLastError
0x140017c84  mov     eax, ebx
0x140017c86  mov     rbx, [rsp+58h+arg_10]
0x140017c8b  add     rsp, 40h
0x140017c8f  pop     rdi
0x140017c90  pop     rsi
0x140017c91  pop     rbp
0x140017c92  retn
```
