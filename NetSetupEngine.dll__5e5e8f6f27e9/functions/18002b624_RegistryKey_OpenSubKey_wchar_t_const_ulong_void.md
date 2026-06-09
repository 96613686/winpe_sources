# RegistryKey::OpenSubKey(wchar_t const *,ulong,void *)

- ea: `0x18002b624`
- end: `0x18002b803`
- name: `?OpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z`
- size: `479`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180010b5c`
- `0x1800163d0`
- `0x18002a0a0`
- `0x18002a348`
- `0x18002a84c`
- `0x18002aac0`
- `0x1800418b4`
- `0x1800612e0`
- `0x18006f470`
- `0x18007f894`

## callees

- `0x18002b624`
- `0x180052620`
- `0x180052698`
- `0x180065035`
- `0x180067750`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b683`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b79d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b683`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b79d`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18002b6e6`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18002b774`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18002b6e6`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18002b774`

## pseudocode

```c
HKEY __fastcall RegistryKey::OpenSubKey(HKEY *a1, HKEY a2, const WCHAR *a3, REGSAM a4, HANDLE hTransaction)
{
  HKEY v6; // r14
  LSTATUS v9; // ebx
  LSTATUS v11; // ebx
  _BYTE pExceptionObject[208]; // [rsp+48h] [rbp-120h] BYREF
  HKEY phkResult; // [rsp+118h] [rbp-50h] BYREF

  phkResult = a2;
  v6 = *a1;
  phkResult = 0;
  if ( hTransaction )
  {
    v11 = RegOpenKeyTransactedW(v6, a3, 0, a4, &phkResult, hTransaction, 0);
    if ( v11 == 5 )
      v11 = RegOpenKeyTransactedW(v6, a3, 4u, a4, &phkResult, hTransaction, 0);
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
          (_DWORD)a3,
          v11);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v11);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  else
  {
    v9 = RegOpenKeyExW(v6, a3, 0, a4, &phkResult);
    if ( v9 == 5 )
      v9 = RegOpenKeyExW(v6, a3, 4u, a4, &phkResult);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
          (_DWORD)a3,
          v9);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v9);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  if ( !phkResult )
    Win32Exception::ThrowLastError();
  *(_QWORD *)a2 = phkResult;
  return a2;
}

```

## disassembly

```asm
0x18002b624  mov     r11, rsp
0x18002b627  push    rbx
0x18002b628  push    rbp
0x18002b629  push    rsi
0x18002b62a  push    rdi
0x18002b62b  push    r14
0x18002b62d  push    r15
0x18002b62f  sub     rsp, 138h
0x18002b636  mov     rax, cs:__security_cookie
0x18002b63d  xor     rax, rsp
0x18002b640  mov     [rsp+168h+var_48], rax
0x18002b648  mov     r15, [rsp+168h+arg_20]
0x18002b650  lea     rax, [r11-50h]
0x18002b654  mov     [rsp+168h+var_50], rdx
0x18002b65c  mov     rdi, r8
0x18002b65f  mov     r14, [rcx]
0x18002b662  xor     r8d, r8d; ulOptions
0x18002b665  mov     qword ptr [r11-50h], 0
0x18002b66d  mov     rsi, rdx
0x18002b670  mov     ebp, r9d
0x18002b673  mov     rdx, rdi; lpSubKey
0x18002b676  mov     rcx, r14; hKey
0x18002b679  test    r15, r15
0x18002b67c  jnz     short loc_18002B6D3
0x18002b67e  mov     [rsp+168h+phkResult], rax; phkResult
0x18002b683  call    cs:__imp_RegOpenKeyExW
0x18002b689  mov     ebx, eax
0x18002b68b  cmp     eax, 5
0x18002b68e  jz      loc_18002B781
0x18002b694  test    ebx, ebx
0x18002b696  jnz     loc_18002B7AA
0x18002b69c  mov     rax, [rsp+168h+var_50]
0x18002b6a4  test    rax, rax
0x18002b6a7  jz      loc_18002B7FD
0x18002b6ad  mov     [rsi], rax
0x18002b6b0  mov     rax, rsi
0x18002b6b3  mov     rcx, [rsp+168h+var_48]
0x18002b6bb  xor     rcx, rsp; StackCookie
0x18002b6be  call    __security_check_cookie
0x18002b6c3  add     rsp, 138h
0x18002b6ca  pop     r15
0x18002b6cc  pop     r14
0x18002b6ce  pop     rdi
0x18002b6cf  pop     rsi
0x18002b6d0  pop     rbp
0x18002b6d1  pop     rbx
0x18002b6d2  retn
0x18002b6d3  mov     [rsp+168h+pExtendedParemeter], 0; pExtendedParemeter
0x18002b6dc  mov     [rsp+168h+hTransaction], r15; hTransaction
0x18002b6e1  mov     [rsp+168h+phkResult], rax; phkResult
0x18002b6e6  call    cs:__imp_RegOpenKeyTransactedW
0x18002b6ec  mov     ebx, eax
0x18002b6ee  cmp     eax, 5
0x18002b6f1  jz      short loc_18002B74A
0x18002b6f3  test    ebx, ebx
0x18002b6f5  jz      short loc_18002B69C
0x18002b6f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b6fe  lea     rax, WPP_GLOBAL_Control
0x18002b705  cmp     rcx, rax
0x18002b708  jz      short loc_18002B72C
0x18002b70a  cmp     byte ptr [rcx+19h], 2
0x18002b70e  jb      short loc_18002B72C
0x18002b710  mov     rcx, [rcx+10h]
0x18002b714  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x18002b71b  mov     edx, 0Dh
0x18002b720  mov     dword ptr [rsp+168h+phkResult], ebx
0x18002b724  mov     r9, rdi
0x18002b727  call    WPP_SF_Sd
0x18002b72c  mov     edx, ebx; int
0x18002b72e  lea     rcx, [rsp+168h+pExceptionObject]; this
0x18002b733  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18002b738  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18002b73f  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x18002b744  call    _CxxThrowException_0
0x18002b74a  mov     [rsp+168h+pExtendedParemeter], 0; pExtendedParemeter
0x18002b753  lea     rax, [rsp+168h+var_50]
0x18002b75b  mov     [rsp+168h+hTransaction], r15; hTransaction
0x18002b760  mov     r9d, ebp; samDesired
0x18002b763  mov     r8d, 4; ulOptions
0x18002b769  mov     [rsp+168h+phkResult], rax; phkResult
0x18002b76e  mov     rdx, rdi; lpSubKey
0x18002b771  mov     rcx, r14; hKey
0x18002b774  call    cs:__imp_RegOpenKeyTransactedW
0x18002b77a  mov     ebx, eax
0x18002b77c  jmp     loc_18002B6F3
0x18002b781  lea     rax, [rsp+168h+var_50]
0x18002b789  mov     r9d, ebp; samDesired
0x18002b78c  mov     r8d, 4; ulOptions
0x18002b792  mov     [rsp+168h+phkResult], rax; phkResult
0x18002b797  mov     rdx, rdi; lpSubKey
0x18002b79a  mov     rcx, r14; hKey
0x18002b79d  call    cs:__imp_RegOpenKeyExW
0x18002b7a3  mov     ebx, eax
0x18002b7a5  jmp     loc_18002B694
0x18002b7aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b7b1  lea     rax, WPP_GLOBAL_Control
0x18002b7b8  cmp     rcx, rax
0x18002b7bb  jz      short loc_18002B7DF
0x18002b7bd  cmp     byte ptr [rcx+19h], 2
0x18002b7c1  jb      short loc_18002B7DF
0x18002b7c3  mov     rcx, [rcx+10h]
0x18002b7c7  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x18002b7ce  mov     edx, 0Eh
0x18002b7d3  mov     dword ptr [rsp+168h+phkResult], ebx
0x18002b7d7  mov     r9, rdi
0x18002b7da  call    WPP_SF_Sd
0x18002b7df  mov     edx, ebx; int
0x18002b7e1  lea     rcx, [rsp+168h+pExceptionObject]; this
0x18002b7e6  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18002b7eb  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18002b7f2  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x18002b7f7  call    _CxxThrowException_0
0x18002b7fd  call    ?ThrowLastError@Win32Exception@@SAXXZ; Win32Exception::ThrowLastError(void)
```
