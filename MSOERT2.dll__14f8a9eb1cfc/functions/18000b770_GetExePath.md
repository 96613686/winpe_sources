# GetExePath

- ea: `0x18000b770`
- end: `0x18000b8d3`
- name: `GetExePath`
- size: `355`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004640`
- `0x18000470c`
- `0x18000b770`
- `0x180012fc0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000b8a5`
- `ADVAPI32!RegCloseKey` at `0x18000b8a5`
- `ADVAPI32!RegQueryValueExW` at `0x18000b855`
- `ADVAPI32!RegQueryValueExW` at `0x18000b855`
- `ADVAPI32!RegOpenKeyExW` at `0x18000b80e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000b80e`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000b877`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000b877`

## string_xrefs

- `0x18000b7aa`: `Software\Microsoft\Windows\CurrentVersion\App Paths`

## pseudocode

```c
_BOOL8 __fastcall GetExePath(__int64 a1, WCHAR *a2, unsigned int a3, int a4)
{
  unsigned __int64 v5; // rdi
  BOOL v7; // ebx
  DWORD v8; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Data[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+250h] [rbp+150h] BYREF

  v5 = a3;
  hKey = 0;
  Type = 0;
  cbData = 0;
  v7 = 0;
  if ( (int)StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"Software\\Microsoft\\Windows\\CurrentVersion\\App Paths", a1) >= 0
    && !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey) )
  {
    cbData = 520;
    if ( !RegQueryValueExW(
            hKey,
            (LPCWSTR)((unsigned __int64)L"Path" & -(__int64)(a4 != 0)),
            0,
            &Type,
            (LPBYTE)Data,
            &cbData)
      && cbData )
    {
      if ( Type == 2 )
      {
        v8 = ExpandEnvironmentStringsW(Data, a2, v5);
        if ( v8 )
          v7 = v8 <= (unsigned int)v5;
      }
      else
      {
        v7 = (int)StringCchCopyW(a2, v5, Data) >= 0;
      }
    }
    RegCloseKey(hKey);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b770  mov     [rsp-8+arg_18], rbx
0x18000b775  push    rbp
0x18000b776  push    rsi
0x18000b777  push    rdi
0x18000b778  push    r12
0x18000b77a  push    r14
0x18000b77c  lea     rbp, [rsp-370h]
0x18000b784  sub     rsp, 470h
0x18000b78b  mov     rax, cs:__security_cookie
0x18000b792  xor     rax, rsp
0x18000b795  mov     [rbp+390h+var_30], rax
0x18000b79c  mov     r14d, r9d
0x18000b79f  mov     edi, r8d
0x18000b7a2  mov     rsi, rdx
0x18000b7a5  mov     [rsp+490h+phkResult], rcx
0x18000b7aa  lea     r9, c_wszAppPaths; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000b7b1  mov     [rsp+490h+hKey], 0
0x18000b7ba  lea     r8, c_wszPathFileFmt; "%s\\%s"
0x18000b7c1  mov     [rsp+490h+Type], 0
0x18000b7c9  mov     edx, 104h; unsigned __int64
0x18000b7ce  mov     [rsp+490h+cbData], 0
0x18000b7d6  lea     rcx, [rbp+390h+SubKey]; unsigned __int16 *
0x18000b7dd  xor     ebx, ebx
0x18000b7df  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b7e4  test    eax, eax
0x18000b7e6  js      loc_18000B8AB
0x18000b7ec  lea     rax, [rsp+490h+hKey]
0x18000b7f1  xor     r8d, r8d; ulOptions
0x18000b7f4  lea     r12d, [rbx+1]
0x18000b7f8  mov     [rsp+490h+phkResult], rax; phkResult
0x18000b7fd  mov     r9d, r12d; samDesired
0x18000b800  lea     rdx, [rbp+390h+SubKey]; lpSubKey
0x18000b807  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b80e  call    cs:__imp_RegOpenKeyExW
0x18000b814  test    eax, eax
0x18000b816  jnz     loc_18000B8AB
0x18000b81c  mov     rcx, [rsp+490h+hKey]; hKey
0x18000b821  lea     rax, c_wszRegPath; "Path"
0x18000b828  neg     r14d
0x18000b82b  mov     [rsp+490h+cbData], 208h
0x18000b833  lea     r9, [rsp+490h+Type]; lpType
0x18000b838  sbb     rdx, rdx
0x18000b83b  xor     r8d, r8d; lpReserved
0x18000b83e  and     rdx, rax; lpValueName
0x18000b841  lea     rax, [rsp+490h+cbData]
0x18000b846  mov     [rsp+490h+lpcbData], rax; lpcbData
0x18000b84b  lea     rax, [rsp+490h+Data]
0x18000b850  mov     [rsp+490h+phkResult], rax; lpData
0x18000b855  call    cs:__imp_RegQueryValueExW
0x18000b85b  test    eax, eax
0x18000b85d  jnz     short loc_18000B8A0
0x18000b85f  cmp     [rsp+490h+cbData], ebx
0x18000b863  jz      short loc_18000B8A0
0x18000b865  cmp     [rsp+490h+Type], 2
0x18000b86a  jnz     short loc_18000B88A
0x18000b86c  mov     r8d, edi; nSize
0x18000b86f  lea     rcx, [rsp+490h+Data]; lpSrc
0x18000b874  mov     rdx, rsi; lpDst
0x18000b877  call    cs:__imp_ExpandEnvironmentStringsW
0x18000b87d  test    eax, eax
0x18000b87f  jz      short loc_18000B8A0
0x18000b881  cmp     eax, edi
0x18000b883  ja      short loc_18000B8A0
0x18000b885  mov     ebx, r12d
0x18000b888  jmp     short loc_18000B8A0
0x18000b88a  mov     rdx, rdi; unsigned __int64
0x18000b88d  lea     r8, [rsp+490h+Data]; unsigned __int16 *
0x18000b892  mov     rcx, rsi; unsigned __int16 *
0x18000b895  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b89a  test    eax, eax
0x18000b89c  cmovns  ebx, r12d
0x18000b8a0  mov     rcx, [rsp+490h+hKey]; hKey
0x18000b8a5  call    cs:__imp_RegCloseKey
0x18000b8ab  mov     eax, ebx
0x18000b8ad  mov     rcx, [rbp+390h+var_30]
0x18000b8b4  xor     rcx, rsp; StackCookie
0x18000b8b7  call    __security_check_cookie
0x18000b8bc  mov     rbx, [rsp+490h+arg_18]
0x18000b8c4  add     rsp, 470h
0x18000b8cb  pop     r14
0x18000b8cd  pop     r12
0x18000b8cf  pop     rdi
0x18000b8d0  pop     rsi
0x18000b8d1  pop     rbp
0x18000b8d2  retn
```
