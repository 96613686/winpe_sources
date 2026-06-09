# RegistryKey::OpenSubKey(wchar_t const *,ulong,void *)

- ea: `0x180027ef4`
- end: `0x180028045`
- name: `?OpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z`
- size: `337`
- prototype: `RegistryKey *__fastcall(HKEY *, RegistryKey *, const WCHAR *, __int64, HANDLE)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001de84`
- `0x18001e3a8`
- `0x1800207bc`
- `0x180026bdc`
- `0x180028104`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x180008c78`
- `0x18002498c`
- `0x180026958`
- `0x180027ef4`
- `0x1800281b4`
- `0x180028208`

## pseudocode

```c
RegistryKey *__fastcall RegistryKey::OpenSubKey(HKEY *a1, RegistryKey *a2, const WCHAR *a3, __int64 a4, HANDLE a5)
{
  int v6; // esi
  HKEY v7; // rcx
  signed int v8; // edi
  signed int v9; // edi
  _BYTE pExceptionObject[208]; // [rsp+38h] [rbp-100h] BYREF
  HKEY v12; // [rsp+108h] [rbp-30h] BYREF

  v12 = (HKEY)a2;
  v6 = (int)a3;
  v7 = *a1;
  v12 = 0;
  if ( a5 )
  {
    v8 = RegOpenKeyTransacted_Wrapper(v7, a3, &v12, a5);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)WPP_419802ccba213757c01acb0d7aa84d96_Traceguids,
          v6,
          v8);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v8);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  else
  {
    v9 = RegOpenKeyEx_Wrapper(v7, a3, &v12);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_419802ccba213757c01acb0d7aa84d96_Traceguids,
          v6,
          v9);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v9);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  RegistryKey::RegistryKey(a2, v12);
  return a2;
}

```

## disassembly

```asm
0x180027ef4  mov     r11, rsp
0x180027ef7  push    rbx
0x180027ef8  push    rsi
0x180027ef9  push    rdi
0x180027efa  sub     rsp, 120h
0x180027f01  mov     rax, cs:__security_cookie
0x180027f08  xor     rax, rsp
0x180027f0b  mov     [rsp+138h+var_28], rax
0x180027f13  mov     rax, [rsp+138h+arg_20]
0x180027f1b  mov     rbx, rdx
0x180027f1e  mov     [rsp+138h+var_30], rdx
0x180027f26  mov     rsi, r8
0x180027f29  mov     rcx, [rcx]; hKey
0x180027f2c  mov     rdx, r8; lpSubKey
0x180027f2f  mov     qword ptr [r11-30h], 0
0x180027f37  test    rax, rax
0x180027f3a  jz      short loc_180027FAC
0x180027f3c  mov     [rsp+138h+var_110], rax; HANDLE
0x180027f41  lea     rax, [r11-30h]
0x180027f45  mov     [rsp+138h+var_118], rax; PHKEY
0x180027f4a  call    RegOpenKeyTransacted_Wrapper
0x180027f4f  mov     edi, eax
0x180027f51  test    eax, eax
0x180027f53  jz      loc_180028017
0x180027f59  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f60  lea     rax, WPP_GLOBAL_Control
0x180027f67  cmp     rcx, rax
0x180027f6a  jz      short loc_180027F8E
0x180027f6c  cmp     byte ptr [rcx+19h], 2
0x180027f70  jb      short loc_180027F8E
0x180027f72  mov     rcx, [rcx+10h]
0x180027f76  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x180027f7d  mov     edx, 0Dh
0x180027f82  mov     dword ptr [rsp+138h+var_118], edi
0x180027f86  mov     r9, rsi
0x180027f89  call    WPP_SF_Sd
0x180027f8e  mov     edx, edi; int
0x180027f90  lea     rcx, [rsp+138h+pExceptionObject]; this
0x180027f95  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180027f9a  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180027fa1  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x180027fa6  call    _CxxThrowException_0
0x180027fac  lea     rax, [rsp+138h+var_30]
0x180027fb4  mov     [rsp+138h+var_118], rax; PHKEY
0x180027fb9  call    RegOpenKeyEx_Wrapper
0x180027fbe  mov     edi, eax
0x180027fc0  test    eax, eax
0x180027fc2  jz      short loc_180028017
0x180027fc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fcb  lea     rax, WPP_GLOBAL_Control
0x180027fd2  cmp     rcx, rax
0x180027fd5  jz      short loc_180027FF9
0x180027fd7  cmp     byte ptr [rcx+19h], 2
0x180027fdb  jb      short loc_180027FF9
0x180027fdd  mov     rcx, [rcx+10h]
0x180027fe1  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x180027fe8  mov     edx, 0Eh
0x180027fed  mov     dword ptr [rsp+138h+var_118], edi
0x180027ff1  mov     r9, rsi
0x180027ff4  call    WPP_SF_Sd
0x180027ff9  mov     edx, edi; int
0x180027ffb  lea     rcx, [rsp+138h+pExceptionObject]; this
0x180028000  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180028005  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18002800c  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x180028011  call    _CxxThrowException_0
0x180028017  mov     rdx, [rsp+138h+var_30]; HKEY
0x18002801f  mov     rcx, rbx; this
0x180028022  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x180028027  mov     rax, rbx
0x18002802a  mov     rcx, [rsp+138h+var_28]
0x180028032  xor     rcx, rsp; StackCookie
0x180028035  call    __security_check_cookie
0x18002803a  add     rsp, 120h
0x180028041  pop     rdi
0x180028042  pop     rsi
0x180028043  pop     rbx
0x180028044  retn
```
