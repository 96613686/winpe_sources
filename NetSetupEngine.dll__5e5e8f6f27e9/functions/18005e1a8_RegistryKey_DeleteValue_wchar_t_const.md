# RegistryKey::DeleteValue(wchar_t const *)

- ea: `0x18005e1a8`
- end: `0x18005e231`
- name: `?DeleteValue@RegistryKey@@QEBAXPEB_W@Z`
- size: `137`
- prototype: `void __fastcall(RegistryKey *__hidden this, const wchar_t *)`
- caller_count: `13`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001bd0c`
- `0x18002a0a0`
- `0x180042444`
- `0x180045174`
- `0x18004c830`
- `0x18005bb18`
- `0x18005e050`
- `0x18005e3d8`
- `0x1800623a0`
- `0x18006281c`
- `0x1800644a0`
- `0x18006a7d8`
- `0x18007bd74`

## callees

- `0x180052620`
- `0x180052698`
- `0x18005e1a8`
- `0x180065035`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005e1bb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005e1bb`

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
        (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
        v2,
        v4);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v4);
    throw (Win32Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18005e1a8  mov     [rsp+arg_0], rbx
0x18005e1ad  push    rdi
0x18005e1ae  sub     rsp, 100h
0x18005e1b5  mov     rcx, [rcx]; hKey
0x18005e1b8  mov     rdi, rdx
0x18005e1bb  call    cs:__imp_RegDeleteValueW
0x18005e1c1  xor     ebx, ebx
0x18005e1c3  cmp     eax, 2
0x18005e1c6  cmovnz  ebx, eax
0x18005e1c9  test    ebx, ebx
0x18005e1cb  jz      short loc_18005E220
0x18005e1cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e1d4  lea     rax, WPP_GLOBAL_Control
0x18005e1db  cmp     rcx, rax
0x18005e1de  jz      short loc_18005E202
0x18005e1e0  cmp     byte ptr [rcx+19h], 2
0x18005e1e4  jb      short loc_18005E202
0x18005e1e6  mov     rcx, [rcx+10h]
0x18005e1ea  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x18005e1f1  mov     edx, 2Eh ; '.'
0x18005e1f6  mov     [rsp+108h+var_E8], ebx
0x18005e1fa  mov     r9, rdi
0x18005e1fd  call    WPP_SF_Sd
0x18005e202  mov     edx, ebx; int
0x18005e204  lea     rcx, [rsp+108h+pExceptionObject]; this
0x18005e209  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18005e20e  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18005e215  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18005e21a  call    _CxxThrowException_0
0x18005e220  mov     rbx, [rsp+108h+arg_0]
0x18005e228  add     rsp, 100h
0x18005e22f  pop     rdi
0x18005e230  retn
```
