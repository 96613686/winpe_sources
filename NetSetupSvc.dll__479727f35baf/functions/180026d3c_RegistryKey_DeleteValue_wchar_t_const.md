# RegistryKey::DeleteValue(wchar_t const *)

- ea: `0x180026d3c`
- end: `0x180026dc5`
- name: `?DeleteValue@RegistryKey@@QEBAXPEB_W@Z`
- size: `137`
- prototype: `void __fastcall(HKEY *this, const wchar_t *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001b140`
- `0x18001f2e4`
- `0x18001fe58`
- `0x180021650`
- `0x18002ff33`

## callees

- `0x1800032e4`
- `0x180008c78`
- `0x18002498c`
- `0x180026d3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180026d4f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180026d4f`

## pseudocode

```c
void __fastcall RegistryKey::DeleteValue(HKEY *this, const wchar_t *a2)
{
  int v2; // edi
  LSTATUS v3; // eax
  signed int v4; // ebx
  _BYTE pExceptionObject[216]; // [rsp+30h] [rbp-D8h] BYREF

  v2 = (int)a2;
  v3 = RegDeleteValueW(*this, a2);
  v4 = 0;
  if ( v3 != 2 )
    v4 = v3;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        (unsigned int)WPP_419802ccba213757c01acb0d7aa84d96_Traceguids,
        v2,
        v4);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v4);
    throw (Win32Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180026d3c  mov     [rsp+arg_0], rbx
0x180026d41  push    rdi
0x180026d42  sub     rsp, 100h
0x180026d49  mov     rcx, [rcx]; hKey
0x180026d4c  mov     rdi, rdx
0x180026d4f  call    cs:__imp_RegDeleteValueW
0x180026d55  xor     ebx, ebx
0x180026d57  cmp     eax, 2
0x180026d5a  cmovnz  ebx, eax
0x180026d5d  test    ebx, ebx
0x180026d5f  jz      short loc_180026DB4
0x180026d61  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d68  lea     rax, WPP_GLOBAL_Control
0x180026d6f  cmp     rcx, rax
0x180026d72  jz      short loc_180026D96
0x180026d74  cmp     byte ptr [rcx+19h], 2
0x180026d78  jb      short loc_180026D96
0x180026d7a  mov     rcx, [rcx+10h]
0x180026d7e  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x180026d85  mov     edx, 2Eh ; '.'
0x180026d8a  mov     [rsp+108h+var_E8], ebx
0x180026d8e  mov     r9, rdi
0x180026d91  call    WPP_SF_Sd
0x180026d96  mov     edx, ebx; int
0x180026d98  lea     rcx, [rsp+108h+pExceptionObject]; this
0x180026d9d  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180026da2  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180026da9  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180026dae  call    _CxxThrowException_0
0x180026db4  mov     rbx, [rsp+108h+arg_0]
0x180026dbc  add     rsp, 100h
0x180026dc3  pop     rdi
0x180026dc4  retn
```
