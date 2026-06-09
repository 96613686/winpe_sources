# RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)

- ea: `0x180010c9c`
- end: `0x180010d8d`
- name: `?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z`
- size: `241`
- prototype: `RegistryKey *__fastcall(HKEY *, RegistryKey *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180003f40`

## callees

- `0x1800052b0`
- `0x180005328`
- `0x1800065d4`
- `0x18000895c`
- `0x18000fbfc`
- `0x180010c9c`
- `0x1800119f0`

## pseudocode

```c
RegistryKey *__fastcall RegistryKey::TryOpenSubKey(HKEY *a1, RegistryKey *a2, __int64 a3)
{
  HKEY v3; // rcx
  LSTATUS v5; // eax
  signed int v6; // edi
  _BYTE pExceptionObject[208]; // [rsp+38h] [rbp-F0h] BYREF
  HKEY v9; // [rsp+108h] [rbp-20h] BYREF

  v9 = (HKEY)a2;
  v3 = *a1;
  v9 = 0;
  v5 = RegOpenKeyEx_Wrapper(v3, L"SYSTEM\\CurrentControlSet\\Control\\NetworkSetup2\\Parameters", a3, 1u, &v9);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 != 2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
          (unsigned int)L"SYSTEM\\CurrentControlSet\\Control\\NetworkSetup2\\Parameters",
          v5);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v6);
      throw (Win32Exception *)pExceptionObject;
    }
    *(_QWORD *)a2 = 0;
  }
  else
  {
    RegistryKey::RegistryKey(a2, v9);
  }
  return a2;
}

```

## disassembly

```asm
0x180010c9c  mov     r11, rsp
0x180010c9f  mov     [r11+18h], rbx
0x180010ca3  push    rdi
0x180010ca4  sub     rsp, 120h
0x180010cab  mov     rax, cs:__security_cookie
0x180010cb2  xor     rax, rsp
0x180010cb5  mov     [rsp+128h+var_18], rax
0x180010cbd  mov     [rsp+128h+var_20], rdx
0x180010cc5  lea     rax, [r11-20h]
0x180010cc9  mov     rcx, [rcx]; hKey
0x180010ccc  mov     rbx, rdx
0x180010ccf  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Net"...
0x180010cd6  mov     [rsp+128h+var_108], rax; PHKEY
0x180010cdb  mov     r9d, 1
0x180010ce1  mov     qword ptr [r11-20h], 0
0x180010ce9  call    RegOpenKeyEx_Wrapper
0x180010cee  mov     edi, eax
0x180010cf0  test    eax, eax
0x180010cf2  jz      short loc_180010D59
0x180010cf4  cmp     eax, 2
0x180010cf7  jz      short loc_180010D50
0x180010cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d00  lea     rax, WPP_GLOBAL_Control
0x180010d07  cmp     rcx, rax
0x180010d0a  jz      short loc_180010D32
0x180010d0c  cmp     byte ptr [rcx+19h], 2
0x180010d10  jb      short loc_180010D32
0x180010d12  mov     rcx, [rcx+10h]
0x180010d16  lea     r9, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Net"...
0x180010d1d  mov     edx, 0Ch
0x180010d22  mov     dword ptr [rsp+128h+var_108], edi
0x180010d26  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x180010d2d  call    WPP_SF_SD
0x180010d32  mov     edx, edi; int
0x180010d34  lea     rcx, [rsp+128h+pExceptionObject]; this
0x180010d39  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180010d3e  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180010d45  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x180010d4a  call    _CxxThrowException_0
0x180010d50  mov     qword ptr [rbx], 0
0x180010d57  jmp     short loc_180010D69
0x180010d59  mov     rdx, [rsp+128h+var_20]; HKEY
0x180010d61  mov     rcx, rbx; this
0x180010d64  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x180010d69  mov     rax, rbx
0x180010d6c  mov     rcx, [rsp+128h+var_18]
0x180010d74  xor     rcx, rsp; StackCookie
0x180010d77  call    __security_check_cookie
0x180010d7c  mov     rbx, [rsp+128h+arg_10]
0x180010d84  add     rsp, 120h
0x180010d8b  pop     rdi
0x180010d8c  retn
```
