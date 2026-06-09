# RegistryKey::SetValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180045074`
- end: `0x18004513a`
- name: `?SetValue@RegistryKey@@QEBAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `198`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180042444`
- `0x180044f60`
- `0x18005bb18`
- `0x1800607e8`
- `0x1800740a4`
- `0x18007cb10`

## callees

- `0x180045074`
- `0x180052698`
- `0x180065035`
- `0x18007fd8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800450be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800450be`

## pseudocode

```c
LSTATUS __fastcall RegistryKey::SetValue(HKEY *a1, const WCHAR *a2, __int64 a3)
{
  int v3; // esi
  _QWORD *v4; // rbx
  const BYTE *lpData; // rax
  LSTATUS result; // eax
  int v7; // r8d
  signed int v8; // edi
  _BYTE pExceptionObject[208]; // [rsp+30h] [rbp-D8h] BYREF

  v3 = (int)a2;
  v4 = (_QWORD *)a3;
  if ( *(_QWORD *)(a3 + 24) < 8u )
    lpData = (const BYTE *)a3;
  else
    lpData = *(const BYTE **)a3;
  result = RegSetValueExW(*a1, a2, 0, 1u, lpData, 2 * *(_DWORD *)(a3 + 16) + 2);
  v8 = result;
  if ( result )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v4[3] >= 8u )
        v4 = (_QWORD *)*v4;
      WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, v7, v3, (__int64)v4, result);
    }
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v8);
    throw (Win32Exception *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180045074  mov     [rsp+arg_0], rbx
0x180045079  mov     [rsp+arg_8], rsi
0x18004507e  push    rdi
0x18004507f  sub     rsp, 100h
0x180045086  cmp     qword ptr [r8+18h], 8
0x18004508b  mov     rsi, rdx
0x18004508e  mov     eax, [r8+10h]
0x180045092  mov     rbx, r8
0x180045095  lea     edx, ds:2[rax*2]
0x18004509c  jb      short loc_1800450A3
0x18004509e  mov     rax, [r8]
0x1800450a1  jmp     short loc_1800450A6
0x1800450a3  mov     rax, rbx
0x1800450a6  mov     rcx, [rcx]; hKey
0x1800450a9  mov     r9d, 1; dwType
0x1800450af  mov     [rsp+108h+cbData], edx; cbData
0x1800450b3  xor     r8d, r8d; Reserved
0x1800450b6  mov     rdx, rsi; lpValueName
0x1800450b9  mov     [rsp+108h+lpData], rax; lpData
0x1800450be  call    cs:__imp_RegSetValueExW
0x1800450c4  mov     edi, eax
0x1800450c6  test    eax, eax
0x1800450c8  jz      short loc_180045125
0x1800450ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800450d1  lea     rax, WPP_GLOBAL_Control
0x1800450d8  cmp     rcx, rax
0x1800450db  jz      short loc_180045107
0x1800450dd  cmp     byte ptr [rcx+19h], 2
0x1800450e1  jb      short loc_180045107
0x1800450e3  cmp     qword ptr [rbx+18h], 8
0x1800450e8  jb      short loc_1800450ED
0x1800450ea  mov     rbx, [rbx]
0x1800450ed  mov     rcx, [rcx+10h]
0x1800450f1  mov     edx, 2Bh ; '+'
0x1800450f6  mov     [rsp+108h+cbData], edi
0x1800450fa  mov     r9, rsi
0x1800450fd  mov     [rsp+108h+lpData], rbx
0x180045102  call    WPP_SF_SSD
0x180045107  mov     edx, edi; int
0x180045109  lea     rcx, [rsp+108h+pExceptionObject]; this
0x18004510e  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180045113  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18004511a  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18004511f  call    _CxxThrowException_0
0x180045125  lea     r11, [rsp+108h+var_8]
0x18004512d  mov     rbx, [r11+10h]
0x180045131  mov     rsi, [r11+18h]
0x180045135  mov     rsp, r11
0x180045138  pop     rdi
0x180045139  retn
```
