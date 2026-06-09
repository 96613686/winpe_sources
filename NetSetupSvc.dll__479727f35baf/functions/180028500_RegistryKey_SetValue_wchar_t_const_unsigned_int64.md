# RegistryKey::SetValue(wchar_t const *,unsigned __int64)

- ea: `0x180028500`
- end: `0x1800285c6`
- name: `?SetValue@RegistryKey@@QEBAXPEB_W_K@Z`
- size: `198`
- prototype: `void __fastcall(HKEY *this, const wchar_t *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180021650`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x180008c78`
- `0x180028500`
- `0x18002892c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028545`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028545`

## pseudocode

```c
void __fastcall RegistryKey::SetValue(HKEY *this, const wchar_t *a2, __int64 a3)
{
  int v3; // edi
  LSTATUS v4; // ebx
  int v5; // r8d
  _BYTE pExceptionObject[208]; // [rsp+30h] [rbp-E8h] BYREF
  __int64 lpData; // [rsp+100h] [rbp-18h] BYREF

  lpData = a3;
  v3 = (int)a2;
  v4 = RegSetValueExW(*this, a2, 0, 0xBu, (const BYTE *)&lpData, 8u);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SID(*((_QWORD *)WPP_GLOBAL_Control + 2), lpData, v5, v3, lpData, v4);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v4);
    throw (Win32Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180028500  mov     r11, rsp
0x180028503  mov     [r11+20h], rbx
0x180028507  push    rdi
0x180028508  sub     rsp, 110h
0x18002850f  mov     rax, cs:__security_cookie
0x180028516  xor     rax, rsp
0x180028519  mov     [rsp+118h+var_10], rax
0x180028521  mov     [r11-18h], r8
0x180028525  lea     rax, [r11-18h]
0x180028529  mov     rcx, [rcx]; hKey
0x18002852c  xor     r8d, r8d; Reserved
0x18002852f  mov     [rsp+118h+cbData], 8; cbData
0x180028537  mov     r9d, 0Bh; dwType
0x18002853d  mov     [rsp+118h+lpData], rax; lpData
0x180028542  mov     rdi, rdx
0x180028545  call    cs:__imp_RegSetValueExW
0x18002854b  mov     ebx, eax
0x18002854d  test    eax, eax
0x18002854f  jz      short loc_1800285A5
0x180028551  mov     rcx, cs:WPP_GLOBAL_Control
0x180028558  lea     rax, WPP_GLOBAL_Control
0x18002855f  cmp     rcx, rax
0x180028562  jz      short loc_180028587
0x180028564  cmp     byte ptr [rcx+19h], 2
0x180028568  jb      short loc_180028587
0x18002856a  mov     rdx, [rsp+118h+var_18]
0x180028572  mov     r9, rdi
0x180028575  mov     rcx, [rcx+10h]
0x180028579  mov     [rsp+118h+cbData], ebx
0x18002857d  mov     [rsp+118h+lpData], rdx
0x180028582  call    WPP_SF_SID
0x180028587  mov     edx, ebx; int
0x180028589  lea     rcx, [rsp+118h+pExceptionObject]; this
0x18002858e  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180028593  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18002859a  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18002859f  call    _CxxThrowException_0
0x1800285a5  mov     rcx, [rsp+118h+var_10]
0x1800285ad  xor     rcx, rsp; StackCookie
0x1800285b0  call    __security_check_cookie
0x1800285b5  mov     rbx, [rsp+118h+arg_18]
0x1800285bd  add     rsp, 110h
0x1800285c4  pop     rdi
0x1800285c5  retn
```
