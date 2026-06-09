# RegistryKey::SetValue(wchar_t const *,uchar const *,unsigned __int64,ulong)

- ea: `0x180010bfc`
- end: `0x180010c94`
- name: `?SetValue@RegistryKey@@QEBAXPEB_WPEBE_KK@Z`
- size: `152`
- prototype: `void __fastcall(HKEY *this, const wchar_t *, const unsigned __int8 *lpData, DWORD cbData, DWORD dwType)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e0d8`

## callees

- `0x1800065d4`
- `0x18000895c`
- `0x18000fbfc`
- `0x180010bfc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010c24`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010c24`

## pseudocode

```c
void __fastcall RegistryKey::SetValue(
        HKEY *this,
        const wchar_t *a2,
        const unsigned __int8 *lpData,
        DWORD cbData,
        DWORD dwType)
{
  int v5; // edi
  LSTATUS v6; // ebx
  _BYTE pExceptionObject[216]; // [rsp+30h] [rbp-D8h] BYREF

  v5 = (int)a2;
  v6 = RegSetValueExW(*this, a2, 0, dwType, lpData, cbData);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
        v5,
        v6);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v6);
    throw (Win32Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180010bfc  mov     [rsp+arg_0], rbx
0x180010c01  push    rdi
0x180010c02  sub     rsp, 100h
0x180010c09  mov     rcx, [rcx]; hKey
0x180010c0c  mov     rdi, rdx
0x180010c0f  mov     [rsp+108h+cbData], r9d; cbData
0x180010c14  mov     r9d, [rsp+108h+dwType]; dwType
0x180010c1c  mov     [rsp+108h+lpData], r8; lpData
0x180010c21  xor     r8d, r8d; Reserved
0x180010c24  call    cs:__imp_RegSetValueExW
0x180010c2a  mov     ebx, eax
0x180010c2c  test    eax, eax
0x180010c2e  jz      short loc_180010C83
0x180010c30  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c37  lea     rax, WPP_GLOBAL_Control
0x180010c3e  cmp     rcx, rax
0x180010c41  jz      short loc_180010C65
0x180010c43  cmp     byte ptr [rcx+19h], 2
0x180010c47  jb      short loc_180010C65
0x180010c49  mov     rcx, [rcx+10h]
0x180010c4d  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x180010c54  mov     edx, 2Dh ; '-'
0x180010c59  mov     dword ptr [rsp+108h+lpData], ebx
0x180010c5d  mov     r9, rdi
0x180010c60  call    WPP_SF_SD
0x180010c65  mov     edx, ebx; int
0x180010c67  lea     rcx, [rsp+108h+pExceptionObject]; this
0x180010c6c  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180010c71  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180010c78  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180010c7d  call    _CxxThrowException_0
0x180010c83  mov     rbx, [rsp+108h+arg_0]
0x180010c8b  add     rsp, 100h
0x180010c92  pop     rdi
0x180010c93  retn
```
