# RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)

- ea: `0x180006eb0`
- end: `0x180006ffb`
- name: `?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z`
- size: `331`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `27`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180003d70`
- `0x180004080`
- `0x18000442c`
- `0x180005020`
- `0x180006070`
- `0x18000e5f4`
- `0x1800163d0`
- `0x18001ba80`
- `0x18001bd0c`
- `0x180022010`
- `0x180027ac0`
- `0x180038b30`
- `0x1800418b4`
- `0x180048af8`
- `0x180052d50`
- `0x180052fc8`
- `0x180057d5c`
- `0x18005c988`
- `0x18005d880`
- `0x18005e3d8`
- `0x18005ea10`
- `0x1800607e8`
- `0x1800623a0`
- `0x18006281c`
- `0x180062a20`
- `0x18006e694`
- `0x180077004`

## callees

- `0x180006eb0`
- `0x18003ef08`
- `0x180052620`
- `0x180052698`
- `0x180065035`
- `0x180067750`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006f0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006f95`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006f0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006f95`

## pseudocode

```c
HKEY __fastcall RegistryKey::TryOpenSubKey(HKEY *a1, HKEY a2, const WCHAR *a3, REGSAM a4, HANDLE a5)
{
  HKEY v6; // rbp
  LSTATUS v9; // ebx
  LSTATUS v11; // eax
  _BYTE pExceptionObject[208]; // [rsp+38h] [rbp-120h] BYREF
  HKEY phkResult; // [rsp+108h] [rbp-50h] BYREF

  phkResult = a2;
  v6 = *a1;
  phkResult = 0;
  if ( a5 )
  {
    v11 = RegOpenKeyTransacted_Wrapper(v6, a3, &phkResult, a5);
  }
  else
  {
    v9 = RegOpenKeyExW(v6, a3, 0, a4, &phkResult);
    if ( v9 != 5 )
      goto LABEL_3;
    v11 = RegOpenKeyExW(v6, a3, 4u, a4, &phkResult);
  }
  v9 = v11;
LABEL_3:
  if ( v9 )
  {
    if ( v9 != 2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
          (_DWORD)a3,
          v9);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v9);
      throw (Win32Exception *)pExceptionObject;
    }
    *(_QWORD *)a2 = 0;
  }
  else
  {
    if ( !phkResult )
      Win32Exception::ThrowLastError();
    *(_QWORD *)a2 = phkResult;
  }
  return a2;
}

```

## disassembly

```asm
0x180006eb0  mov     r11, rsp
0x180006eb3  push    rbx
0x180006eb4  push    rbp
0x180006eb5  push    rsi
0x180006eb6  push    rdi
0x180006eb7  push    r14
0x180006eb9  push    r15
0x180006ebb  sub     rsp, 128h
0x180006ec2  mov     rax, cs:__security_cookie
0x180006ec9  xor     rax, rsp
0x180006ecc  mov     [rsp+158h+var_48], rax
0x180006ed4  mov     rax, [rsp+158h+arg_20]
0x180006edc  xor     r15d, r15d
0x180006edf  mov     [rsp+158h+var_50], rdx
0x180006ee7  mov     rdi, rdx
0x180006eea  mov     rbp, [rcx]
0x180006eed  mov     esi, r9d
0x180006ef0  mov     [r11-50h], r15
0x180006ef4  mov     rcx, rbp; hKey
0x180006ef7  mov     r14, r8
0x180006efa  mov     rdx, r8; lpSubKey
0x180006efd  test    rax, rax
0x180006f00  jnz     short loc_180006F60
0x180006f02  lea     rax, [r11-50h]
0x180006f06  xor     r8d, r8d; ulOptions
0x180006f09  mov     [rsp+158h+phkResult], rax; phkResult
0x180006f0e  call    cs:__imp_RegOpenKeyExW
0x180006f14  mov     ebx, eax
0x180006f16  cmp     eax, 5
0x180006f19  jz      short loc_180006F79
0x180006f1b  test    ebx, ebx
0x180006f1d  jnz     short loc_180006F56
0x180006f1f  mov     rax, [rsp+158h+var_50]
0x180006f27  test    rax, rax
0x180006f2a  jz      loc_180006FF5
0x180006f30  mov     [rdi], rax
0x180006f33  mov     rax, rdi
0x180006f36  mov     rcx, [rsp+158h+var_48]
0x180006f3e  xor     rcx, rsp; StackCookie
0x180006f41  call    __security_check_cookie
0x180006f46  add     rsp, 128h
0x180006f4d  pop     r15
0x180006f4f  pop     r14
0x180006f51  pop     rdi
0x180006f52  pop     rsi
0x180006f53  pop     rbp
0x180006f54  pop     rbx
0x180006f55  retn
0x180006f56  cmp     ebx, 2
0x180006f59  jnz     short loc_180006FA2
0x180006f5b  mov     [rdi], r15
0x180006f5e  jmp     short loc_180006F33
0x180006f60  mov     [rsp+158h+var_130], rax; HANDLE
0x180006f65  lea     rax, [rsp+158h+var_50]
0x180006f6d  mov     [rsp+158h+phkResult], rax; PHKEY
0x180006f72  call    RegOpenKeyTransacted_Wrapper
0x180006f77  jmp     short loc_180006F9B
0x180006f79  lea     rax, [rsp+158h+var_50]
0x180006f81  mov     r9d, esi; samDesired
0x180006f84  mov     r8d, 4; ulOptions
0x180006f8a  mov     [rsp+158h+phkResult], rax; phkResult
0x180006f8f  mov     rdx, r14; lpSubKey
0x180006f92  mov     rcx, rbp; hKey
0x180006f95  call    cs:__imp_RegOpenKeyExW
0x180006f9b  mov     ebx, eax
0x180006f9d  jmp     loc_180006F1B
0x180006fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fa9  lea     rax, WPP_GLOBAL_Control
0x180006fb0  cmp     rcx, rax
0x180006fb3  jz      short loc_180006FD7
0x180006fb5  cmp     byte ptr [rcx+19h], 2
0x180006fb9  jb      short loc_180006FD7
0x180006fbb  mov     rcx, [rcx+10h]
0x180006fbf  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x180006fc6  mov     edx, 0Ch
0x180006fcb  mov     dword ptr [rsp+158h+phkResult], ebx
0x180006fcf  mov     r9, r14
0x180006fd2  call    WPP_SF_Sd
0x180006fd7  mov     edx, ebx; int
0x180006fd9  lea     rcx, [rsp+158h+pExceptionObject]; this
0x180006fde  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180006fe3  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180006fea  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x180006fef  call    _CxxThrowException_0
0x180006ff5  call    ?ThrowLastError@Win32Exception@@SAXXZ; Win32Exception::ThrowLastError(void)
```
