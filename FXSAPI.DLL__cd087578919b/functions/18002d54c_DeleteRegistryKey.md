# DeleteRegistryKey

- ea: `0x18002d54c`
- end: `0x18002d769`
- name: `DeleteRegistryKey`
- size: `541`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180028ef0`
- `0x18002d54c`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002d54c`
- `0x18003d510`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002d733`
- `KERNEL32!SetLastError` at `0x18002d733`
- `ADVAPI32!RegEnumKeyExW` at `0x18002d685`
- `ADVAPI32!RegEnumKeyExW` at `0x18002d685`
- `ADVAPI32!RegDeleteKeyW` at `0x18002d6b5`
- `ADVAPI32!RegDeleteKeyW` at `0x18002d6b5`
- `ADVAPI32!RegCloseKey` at `0x18002d6a3`
- `ADVAPI32!RegCloseKey` at `0x18002d725`
- `ADVAPI32!RegCloseKey` at `0x18002d6a3`
- `ADVAPI32!RegCloseKey` at `0x18002d725`
- `ADVAPI32!RegOpenKeyExW` at `0x18002d5de`
- `ADVAPI32!RegOpenKeyExW` at `0x18002d5de`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeleteRegistryKey(HKEY a1, const WCHAR *a2)
{
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  cchName = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids);
  }
  v4 = RegOpenKeyExW(a1, a2, 0, 0x3001Fu, &hKey);
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 11;
LABEL_10:
      WPP_SF_d(v5[2], v6, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids, v4);
    }
  }
  else
  {
    while ( 1 )
    {
      cchName = 260;
      v7 = RegEnumKeyExW(hKey, 0, SubKey, &cchName, 0, 0, 0, 0);
      v4 = v7;
      if ( v7 )
        break;
      if ( !(unsigned int)DeleteRegistryKey(hKey, SubKey) )
        return 0;
    }
    if ( v7 == 259 )
    {
      RegCloseKey(hKey);
      v4 = RegDeleteKeyW(a1, a2);
      if ( !v4 )
        return 1;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = 13;
        goto LABEL_10;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids, v7);
      }
      RegCloseKey(hKey);
    }
  }
  SetLastError(v4);
  return 0;
}

```

## disassembly

```asm
0x18002d54c  mov     [rsp-8+arg_10], rbx
0x18002d551  mov     [rsp-8+arg_18], rsi
0x18002d556  push    rbp
0x18002d557  push    rdi
0x18002d558  push    r12
0x18002d55a  lea     rbp, [rsp-170h]
0x18002d562  sub     rsp, 270h
0x18002d569  mov     rax, cs:__security_cookie
0x18002d570  xor     rax, rsp
0x18002d573  mov     [rbp+180h+var_20], rax
0x18002d57a  mov     rsi, rdx
0x18002d57d  mov     [rsp+280h+hKey], 0
0x18002d586  mov     rdi, rcx
0x18002d589  mov     [rsp+280h+cchName], 0
0x18002d591  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d598  lea     r12, WPP_GLOBAL_Control
0x18002d59f  cmp     rcx, r12
0x18002d5a2  jz      short loc_18002D5C5
0x18002d5a4  test    byte ptr [rcx+1Ch], 2
0x18002d5a8  jz      short loc_18002D5C5
0x18002d5aa  cmp     byte ptr [rcx+19h], 5
0x18002d5ae  jb      short loc_18002D5C5
0x18002d5b0  mov     rcx, [rcx+10h]
0x18002d5b4  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x18002d5bb  mov     edx, 0Ah
0x18002d5c0  call    WPP_SF_
0x18002d5c5  lea     rax, [rsp+280h+hKey]
0x18002d5ca  mov     r9d, 3001Fh; samDesired
0x18002d5d0  xor     r8d, r8d; ulOptions
0x18002d5d3  mov     [rsp+280h+phkResult], rax; phkResult
0x18002d5d8  mov     rdx, rsi; lpSubKey
0x18002d5db  mov     rcx, rdi; hKey
0x18002d5de  call    cs:__imp_RegOpenKeyExW
0x18002d5e5  nop     dword ptr [rax+rax+00h]
0x18002d5ea  mov     ebx, eax
0x18002d5ec  test    eax, eax
0x18002d5ee  jz      short loc_18002D648
0x18002d5f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d5f7  cmp     rcx, r12
0x18002d5fa  jz      loc_18002D731
0x18002d600  test    byte ptr [rcx+1Ch], 2
0x18002d604  jz      loc_18002D731
0x18002d60a  cmp     byte ptr [rcx+19h], 2
0x18002d60e  jb      loc_18002D731
0x18002d614  mov     edx, 0Bh
0x18002d619  mov     rcx, [rcx+10h]
0x18002d61d  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x18002d624  mov     r9d, ebx
0x18002d627  call    WPP_SF_d
0x18002d62c  jmp     loc_18002D731
0x18002d631  mov     rcx, [rsp+280h+hKey]
0x18002d636  lea     rdx, [rsp+280h+SubKey]
0x18002d63b  call    DeleteRegistryKey
0x18002d640  test    eax, eax
0x18002d642  jz      loc_18002D73F
0x18002d648  mov     rcx, [rsp+280h+hKey]; hKey
0x18002d64d  lea     r9, [rsp+280h+cchName]; lpcchName
0x18002d652  mov     [rsp+280h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18002d65b  lea     r8, [rsp+280h+SubKey]; lpName
0x18002d660  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x18002d669  xor     edx, edx; dwIndex
0x18002d66b  mov     [rsp+280h+lpClass], 0; lpClass
0x18002d674  mov     [rsp+280h+phkResult], 0; lpReserved
0x18002d67d  mov     [rsp+280h+cchName], 104h
0x18002d685  call    cs:__imp_RegEnumKeyExW
0x18002d68c  nop     dword ptr [rax+rax+00h]
0x18002d691  mov     ebx, eax
0x18002d693  test    eax, eax
0x18002d695  jz      short loc_18002D631
0x18002d697  cmp     eax, 103h
0x18002d69c  jnz     short loc_18002D6F0
0x18002d69e  mov     rcx, [rsp+280h+hKey]; hKey
0x18002d6a3  call    cs:__imp_RegCloseKey
0x18002d6aa  nop     dword ptr [rax+rax+00h]
0x18002d6af  mov     rdx, rsi; lpSubKey
0x18002d6b2  mov     rcx, rdi; hKey
0x18002d6b5  call    cs:__imp_RegDeleteKeyW
0x18002d6bc  nop     dword ptr [rax+rax+00h]
0x18002d6c1  mov     ebx, eax
0x18002d6c3  test    eax, eax
0x18002d6c5  jz      short loc_18002D6E9
0x18002d6c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d6ce  cmp     rcx, r12
0x18002d6d1  jz      short loc_18002D731
0x18002d6d3  test    byte ptr [rcx+1Ch], 2
0x18002d6d7  jz      short loc_18002D731
0x18002d6d9  cmp     byte ptr [rcx+19h], 2
0x18002d6dd  jb      short loc_18002D731
0x18002d6df  mov     edx, 0Dh
0x18002d6e4  jmp     loc_18002D619
0x18002d6e9  mov     eax, 1
0x18002d6ee  jmp     short loc_18002D741
0x18002d6f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d6f7  cmp     rcx, r12
0x18002d6fa  jz      short loc_18002D720
0x18002d6fc  test    byte ptr [rcx+1Ch], 2
0x18002d700  jz      short loc_18002D720
0x18002d702  cmp     byte ptr [rcx+19h], 2
0x18002d706  jb      short loc_18002D720
0x18002d708  mov     rcx, [rcx+10h]
0x18002d70c  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x18002d713  mov     edx, 0Ch
0x18002d718  mov     r9d, ebx
0x18002d71b  call    WPP_SF_d
0x18002d720  mov     rcx, [rsp+280h+hKey]; hKey
0x18002d725  call    cs:__imp_RegCloseKey
0x18002d72c  nop     dword ptr [rax+rax+00h]
0x18002d731  mov     ecx, ebx; dwErrCode
0x18002d733  call    cs:__imp_SetLastError
0x18002d73a  nop     dword ptr [rax+rax+00h]
0x18002d73f  xor     eax, eax
0x18002d741  mov     rcx, [rbp+180h+var_20]
0x18002d748  xor     rcx, rsp; StackCookie
0x18002d74b  call    __security_check_cookie
0x18002d750  lea     r11, [rsp+280h+var_10]
0x18002d758  mov     rbx, [r11+30h]
0x18002d75c  mov     rsi, [r11+38h]
0x18002d760  mov     rsp, r11
0x18002d763  pop     r12
0x18002d765  pop     rdi
0x18002d766  pop     rbp
0x18002d767  retn
```
