# CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(HKEY__ *,ushort const *)

- ea: `0x14000b458`
- end: `0x14000b66d`
- name: `?DeleteKeyRecursively@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@CAJPEAUHKEY__@@PEBG@Z`
- size: `533`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000b33c`
- `0x14000b458`

## callees

- `0x1400076c8`
- `0x14000b458`
- `0x1400135b8`
- `0x140080d70`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000b4b7`
- `ADVAPI32!RegOpenKeyExW` at `0x14000b4b7`
- `ADVAPI32!RegDeleteKeyW` at `0x14000b62e`
- `ADVAPI32!RegDeleteKeyW` at `0x14000b62e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000b566`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000b566`
- `ADVAPI32!RegEnumKeyW` at `0x14000b5e6`
- `ADVAPI32!RegEnumKeyW` at `0x14000b5e6`
- `ADVAPI32!RegCloseKey` at `0x14000b502`
- `ADVAPI32!RegCloseKey` at `0x14000b59d`
- `ADVAPI32!RegCloseKey` at `0x14000b61a`
- `ADVAPI32!RegCloseKey` at `0x14000b502`
- `ADVAPI32!RegCloseKey` at `0x14000b59d`
- `ADVAPI32!RegCloseKey` at `0x14000b61a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(HKEY a1, const WCHAR *a2)
{
  HKEY v4; // rdi
  LSTATUS v5; // eax
  int InfoKeyW; // ebx
  int v7; // ecx
  int v9; // eax
  DWORD cSubKeys[2]; // [rsp+68h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-98h] BYREF
  HKEY v12; // [rsp+78h] [rbp-90h]
  __int64 v13; // [rsp+80h] [rbp-88h]
  WCHAR Name[264]; // [rsp+88h] [rbp-80h] BYREF

  v13 = -2;
  v4 = 0;
  v12 = 0;
  cSubKeys[0] = 0;
  hKey = 0;
  v5 = RegOpenKeyExW(a1, a2, 0, 0x2000000u, &hKey);
  InfoKeyW = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      InfoKeyW = (unsigned __int16)v5 | 0x80070000;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(InfoKeyW);
  }
  else
  {
    v4 = hKey;
    hKey = 0;
    v12 = v4;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)InfoKeyW);
  if ( hKey )
    RegCloseKey(hKey);
  if ( InfoKeyW < 0 )
  {
LABEL_12:
    v7 = InfoKeyW;
LABEL_13:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_14;
  }
  InfoKeyW = RegQueryInfoKeyW(v4, 0, 0, 0, cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( InfoKeyW )
  {
LABEL_10:
    if ( InfoKeyW > 0 )
      InfoKeyW = (unsigned __int16)InfoKeyW | 0x80070000;
    goto LABEL_12;
  }
  while ( cSubKeys[0] )
  {
    InfoKeyW = RegEnumKeyW(v4, --cSubKeys[0], Name, 0x105u);
    if ( InfoKeyW )
      goto LABEL_10;
    v9 = CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(v4, Name);
    InfoKeyW = v9;
    if ( v9 < 0 )
    {
      v7 = v9;
      goto LABEL_13;
    }
  }
  if ( v4 )
  {
    RegCloseKey(v4);
    v4 = 0;
  }
  InfoKeyW = RegDeleteKeyW(a1, a2);
  if ( InfoKeyW )
  {
    if ( InfoKeyW > 0 )
      InfoKeyW = (unsigned __int16)InfoKeyW | 0x80070000;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(InfoKeyW);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)InfoKeyW);
  if ( InfoKeyW < 0 )
    goto LABEL_12;
LABEL_14:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)InfoKeyW);
  if ( v4 )
    RegCloseKey(v4);
  return (unsigned int)InfoKeyW;
}

```

## disassembly

```asm
0x14000b458  mov     rax, rsp
0x14000b45b  push    rbp
0x14000b45c  push    rsi
0x14000b45d  push    rdi
0x14000b45e  push    r12
0x14000b460  push    r14
0x14000b462  lea     rbp, [rax-1C8h]
0x14000b469  sub     rsp, 2A0h
0x14000b470  mov     [rsp+2C0h+var_248], 0FFFFFFFFFFFFFFFEh
0x14000b479  mov     [rax+18h], rbx
0x14000b47d  mov     rax, cs:__security_cookie
0x14000b484  xor     rax, rsp
0x14000b487  mov     [rbp+1C0h+var_30], rax
0x14000b48e  mov     r14, rdx
0x14000b491  mov     rsi, rcx
0x14000b494  xor     edi, edi
0x14000b496  mov     [rsp+2C0h+var_250], rdi
0x14000b49b  mov     [rsp+2C0h+cSubKeys], edi
0x14000b49f  mov     [rsp+2C0h+hKey], rdi
0x14000b4a4  lea     rax, [rsp+2C0h+hKey]
0x14000b4a9  mov     [rsp+2C0h+phkResult], rax; phkResult
0x14000b4ae  mov     r9d, 2000000h; samDesired
0x14000b4b4  xor     r8d, r8d; ulOptions
0x14000b4b7  call    cs:__imp_RegOpenKeyExW
0x14000b4be  nop     dword ptr [rax+rax+00h]
0x14000b4c3  mov     ebx, eax
0x14000b4c5  mov     r12d, 80070000h
0x14000b4cb  test    eax, eax
0x14000b4cd  jnz     short loc_14000B4E0
0x14000b4cf  mov     rdi, [rsp+2C0h+hKey]
0x14000b4d4  mov     [rsp+2C0h+hKey], rbx
0x14000b4d9  mov     [rsp+2C0h+var_250], rdi
0x14000b4de  jmp     short loc_14000B4F1
0x14000b4e0  test    ebx, ebx
0x14000b4e2  jle     short loc_14000B4EA
0x14000b4e4  movzx   ebx, bx
0x14000b4e7  or      ebx, r12d
0x14000b4ea  mov     ecx, ebx
0x14000b4ec  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000b4f1  mov     ecx, ebx
0x14000b4f3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000b4f8  mov     rcx, [rsp+2C0h+hKey]; hKey
0x14000b4fd  test    rcx, rcx
0x14000b500  jz      short loc_14000B50E
0x14000b502  call    cs:__imp_RegCloseKey
0x14000b509  nop     dword ptr [rax+rax+00h]
0x14000b50e  test    ebx, ebx
0x14000b510  js      short loc_14000B586
0x14000b512  mov     [rsp+2C0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x14000b51b  mov     [rsp+2C0h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x14000b524  mov     [rsp+2C0h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x14000b52d  mov     [rsp+2C0h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x14000b536  mov     [rsp+2C0h+lpcValues], 0; lpcValues
0x14000b53f  mov     [rsp+2C0h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x14000b548  mov     [rsp+2C0h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x14000b551  lea     rax, [rsp+2C0h+cSubKeys]
0x14000b556  mov     [rsp+2C0h+phkResult], rax; lpcSubKeys
0x14000b55b  xor     r9d, r9d; lpReserved
0x14000b55e  xor     r8d, r8d; lpcchClass
0x14000b561  xor     edx, edx; lpClass
0x14000b563  mov     rcx, rdi; hKey
0x14000b566  call    cs:__imp_RegQueryInfoKeyW
0x14000b56d  nop     dword ptr [rax+rax+00h]
0x14000b572  mov     ebx, eax
0x14000b574  test    eax, eax
0x14000b576  jz      loc_14000B60A
0x14000b57c  test    ebx, ebx
0x14000b57e  jle     short loc_14000B586
0x14000b580  movzx   ebx, bx
0x14000b583  or      ebx, r12d
0x14000b586  mov     ecx, ebx
0x14000b588  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000b58d  mov     ecx, ebx
0x14000b58f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000b594  nop
0x14000b595  test    rdi, rdi
0x14000b598  jz      short loc_14000B5A9
0x14000b59a  mov     rcx, rdi; hKey
0x14000b59d  call    cs:__imp_RegCloseKey
0x14000b5a4  nop     dword ptr [rax+rax+00h]
0x14000b5a9  mov     eax, ebx
0x14000b5ab  mov     rcx, [rbp+1C0h+var_30]
0x14000b5b2  xor     rcx, rsp; StackCookie
0x14000b5b5  call    __security_check_cookie
0x14000b5ba  mov     rbx, [rsp+2C0h+arg_10]
0x14000b5c2  add     rsp, 2A0h
0x14000b5c9  pop     r14
0x14000b5cb  pop     r12
0x14000b5cd  pop     rdi
0x14000b5ce  pop     rsi
0x14000b5cf  pop     rbp
0x14000b5d0  retn
0x14000b5d2  lea     edx, [rax-1]; dwIndex
0x14000b5d5  mov     [rsp+2C0h+cSubKeys], edx
0x14000b5d9  mov     r9d, 105h; cchName
0x14000b5df  lea     r8, [rbp+1C0h+Name]; lpName
0x14000b5e3  mov     rcx, rdi; hKey
0x14000b5e6  call    cs:__imp_RegEnumKeyW
0x14000b5ed  nop     dword ptr [rax+rax+00h]
0x14000b5f2  mov     ebx, eax
0x14000b5f4  test    eax, eax
0x14000b5f6  jnz     short loc_14000B57C
0x14000b5f8  lea     rdx, [rbp+1C0h+Name]
0x14000b5fc  mov     rcx, rdi
0x14000b5ff  call    ?DeleteKeyRecursively@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@CAJPEAUHKEY__@@PEBG@Z; CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(HKEY__ *,ushort const *)
0x14000b604  mov     ebx, eax
0x14000b606  test    eax, eax
0x14000b608  js      short loc_14000B665
0x14000b60a  mov     eax, [rsp+2C0h+cSubKeys]
0x14000b60e  test    eax, eax
0x14000b610  jnz     short loc_14000B5D2
0x14000b612  test    rdi, rdi
0x14000b615  jz      short loc_14000B628
0x14000b617  mov     rcx, rdi; hKey
0x14000b61a  call    cs:__imp_RegCloseKey
0x14000b621  nop     dword ptr [rax+rax+00h]
0x14000b626  xor     edi, edi
0x14000b628  mov     rdx, r14; lpSubKey
0x14000b62b  mov     rcx, rsi; hKey
0x14000b62e  call    cs:__imp_RegDeleteKeyW
0x14000b635  nop     dword ptr [rax+rax+00h]
0x14000b63a  mov     ebx, eax
0x14000b63c  test    eax, eax
0x14000b63e  jz      short loc_14000B651
0x14000b640  test    ebx, ebx
0x14000b642  jle     short loc_14000B64A
0x14000b644  movzx   ebx, bx
0x14000b647  or      ebx, r12d
0x14000b64a  mov     ecx, ebx
0x14000b64c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000b651  mov     ecx, ebx
0x14000b653  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000b658  test    ebx, ebx
0x14000b65a  jns     loc_14000B58D
0x14000b660  jmp     loc_14000B586
0x14000b665  mov     ecx, eax
0x14000b667  jmp     loc_14000B588
```
