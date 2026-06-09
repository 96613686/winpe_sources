# DeleteRegKeyRecursive(HKEY__ *,ushort const *)

- ea: `0x1800076a0`
- end: `0x1800078ee`
- name: `?DeleteRegKeyRecursive@@YAJPEAUHKEY__@@PEBG@Z`
- size: `590`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800076a0`
- `0x18000c734`

## callees

- `0x1800076a0`
- `0x18000a358`
- `0x18000a6a4`
- `0x18001f420`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800077f9`
- `ADVAPI32!RegCloseKey` at `0x1800077f9`
- `ADVAPI32!RegOpenKeyExW` at `0x180007701`
- `ADVAPI32!RegOpenKeyExW` at `0x180007701`
- `ADVAPI32!RegEnumKeyExW` at `0x1800077c6`
- `ADVAPI32!RegEnumKeyExW` at `0x1800077c6`
- `ADVAPI32!RegDeleteKeyExW` at `0x180007814`
- `ADVAPI32!RegDeleteKeyExW` at `0x180007814`
- `KERNEL32!GetLastError` at `0x180007778`
- `KERNEL32!GetLastError` at `0x180007891`
- `KERNEL32!GetLastError` at `0x180007778`
- `KERNEL32!GetLastError` at `0x180007891`

## pseudocode

```c
__int64 __fastcall DeleteRegKeyRecursive(HKEY a1, const unsigned __int16 *a2)
{
  LSTATUS v4; // eax
  char v5; // di
  unsigned int v6; // ebx
  LPCWSTR v7; // rcx
  __int64 v8; // rdx
  char LastError; // al
  int v10; // edx
  LSTATUS v11; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[256]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  cchName = 256;
  ftLastWriteTime = 0;
  v4 = RegOpenKeyExW(a1, a2, 0, 0x2011Fu, &hKey);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v6 = (unsigned __int16)v4 | 0x80070000;
    else
      v6 = v4;
    if ( v6 == -2147024894 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return 0;
      v8 = 93;
LABEL_24:
      WPP_SF_S(*((_QWORD *)v7 + 2), v8, &WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids, a2);
      return 0;
    }
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      LastError = GetLastError();
      v10 = 94;
LABEL_29:
      WPP_SF_SdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        (unsigned int)&WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids,
        (_DWORD)a2,
        v5,
        LastError);
    }
  }
  else
  {
    v6 = 0;
    while ( !RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
    {
      v6 = DeleteRegKeyRecursive(hKey, Name);
      if ( (v6 & 0x80000000) != 0 )
        return v6;
      cchName = 256;
    }
    RegCloseKey(hKey);
    v11 = RegDeleteKeyExW(a1, a2, 0x100u, 0);
    v5 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
      else
        v6 = v11;
      if ( v6 == -2147024894 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          return 0;
        v8 = 95;
        goto LABEL_24;
      }
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        LastError = GetLastError();
        v10 = 96;
        goto LABEL_29;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800076a0  mov     [rsp-8+arg_10], rbx
0x1800076a5  mov     [rsp-8+arg_18], rsi
0x1800076aa  push    rbp
0x1800076ab  push    rdi
0x1800076ac  push    r14
0x1800076ae  lea     rbp, [rsp-170h]
0x1800076b6  sub     rsp, 270h
0x1800076bd  mov     rax, cs:__security_cookie
0x1800076c4  xor     rax, rsp
0x1800076c7  mov     [rbp+180h+var_20], rax
0x1800076ce  lea     rax, [rsp+280h+hKey]
0x1800076d3  mov     [rsp+280h+hKey], 0
0x1800076dc  mov     r9d, 2011Fh; samDesired
0x1800076e2  mov     [rsp+280h+phkResult], rax; phkResult
0x1800076e7  xor     r8d, r8d; ulOptions
0x1800076ea  mov     [rsp+280h+cchName], 100h
0x1800076f2  mov     rsi, rdx
0x1800076f5  mov     qword ptr [rsp+280h+ftLastWriteTime.dwLowDateTime], 0
0x1800076fe  mov     r14, rcx
0x180007701  call    cs:__imp_RegOpenKeyExW
0x180007708  nop     dword ptr [rax+rax+00h]
0x18000770d  mov     edi, eax
0x18000770f  test    eax, eax
0x180007711  jz      short loc_18000778E
0x180007713  test    eax, eax
0x180007715  jg      short loc_18000771B
0x180007717  mov     ebx, eax
0x180007719  jmp     short loc_180007724
0x18000771b  movzx   ebx, di
0x18000771e  or      ebx, 80070000h
0x180007724  cmp     ebx, 80070002h
0x18000772a  jnz     short loc_180007757
0x18000772c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007733  lea     rax, WPP_GLOBAL_Control
0x18000773a  cmp     rcx, rax
0x18000773d  jz      loc_180007874
0x180007743  test    byte ptr [rcx+1Ch], 1
0x180007747  jz      loc_180007874
0x18000774d  mov     edx, 5Dh ; ']'
0x180007752  jmp     loc_180007861
0x180007757  mov     rcx, cs:WPP_GLOBAL_Control
0x18000775e  lea     rax, WPP_GLOBAL_Control
0x180007765  cmp     rcx, rax
0x180007768  jz      loc_1800078C4
0x18000776e  test    byte ptr [rcx+1Ch], 4
0x180007772  jz      loc_1800078C4
0x180007778  call    cs:__imp_GetLastError
0x18000777f  nop     dword ptr [rax+rax+00h]
0x180007784  mov     edx, 5Eh ; '^'
0x180007789  jmp     loc_1800078A2
0x18000778e  xor     ebx, ebx
0x180007790  mov     rcx, [rsp+280h+hKey]; hKey
0x180007795  lea     rax, [rsp+280h+ftLastWriteTime]
0x18000779a  mov     [rsp+280h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000779f  lea     r9, [rsp+280h+cchName]; lpcchName
0x1800077a4  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x1800077ad  lea     r8, [rsp+280h+Name]; lpName
0x1800077b2  mov     [rsp+280h+lpClass], 0; lpClass
0x1800077bb  xor     edx, edx; dwIndex
0x1800077bd  mov     [rsp+280h+phkResult], 0; lpReserved
0x1800077c6  call    cs:__imp_RegEnumKeyExW
0x1800077cd  nop     dword ptr [rax+rax+00h]
0x1800077d2  mov     rcx, [rsp+280h+hKey]; HKEY
0x1800077d7  test    eax, eax
0x1800077d9  jnz     short loc_1800077F9
0x1800077db  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800077e0  call    ?DeleteRegKeyRecursive@@YAJPEAUHKEY__@@PEBG@Z; DeleteRegKeyRecursive(HKEY__ *,ushort const *)
0x1800077e5  mov     ebx, eax
0x1800077e7  test    eax, eax
0x1800077e9  js      loc_1800078C4
0x1800077ef  mov     [rsp+280h+cchName], 100h
0x1800077f7  jmp     short loc_180007790
0x1800077f9  call    cs:__imp_RegCloseKey
0x180007800  nop     dword ptr [rax+rax+00h]
0x180007805  xor     r9d, r9d; Reserved
0x180007808  mov     r8d, 100h; samDesired
0x18000780e  mov     rdx, rsi; lpSubKey
0x180007811  mov     rcx, r14; hKey
0x180007814  call    cs:__imp_RegDeleteKeyExW
0x18000781b  nop     dword ptr [rax+rax+00h]
0x180007820  mov     edi, eax
0x180007822  test    eax, eax
0x180007824  jz      loc_1800078C4
0x18000782a  test    eax, eax
0x18000782c  jg      short loc_180007832
0x18000782e  mov     ebx, eax
0x180007830  jmp     short loc_18000783B
0x180007832  movzx   ebx, di
0x180007835  or      ebx, 80070000h
0x18000783b  cmp     ebx, 80070002h
0x180007841  jnz     short loc_180007878
0x180007843  mov     rcx, cs:WPP_GLOBAL_Control
0x18000784a  lea     rax, WPP_GLOBAL_Control
0x180007851  cmp     rcx, rax
0x180007854  jz      short loc_180007874
0x180007856  test    byte ptr [rcx+1Ch], 1
0x18000785a  jz      short loc_180007874
0x18000785c  mov     edx, 5Fh ; '_'
0x180007861  mov     rcx, [rcx+10h]
0x180007865  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x18000786c  mov     r9, rsi
0x18000786f  call    WPP_SF_S
0x180007874  xor     ebx, ebx
0x180007876  jmp     short loc_1800078C4
0x180007878  mov     rcx, cs:WPP_GLOBAL_Control
0x18000787f  lea     rax, WPP_GLOBAL_Control
0x180007886  cmp     rcx, rax
0x180007889  jz      short loc_1800078C4
0x18000788b  test    byte ptr [rcx+1Ch], 4
0x18000788f  jz      short loc_1800078C4
0x180007891  call    cs:__imp_GetLastError
0x180007898  nop     dword ptr [rax+rax+00h]
0x18000789d  mov     edx, 60h ; '`'
0x1800078a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078a9  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x1800078b0  mov     dword ptr [rsp+280h+lpClass], eax
0x1800078b4  mov     r9, rsi
0x1800078b7  mov     dword ptr [rsp+280h+phkResult], edi
0x1800078bb  mov     rcx, [rcx+10h]
0x1800078bf  call    WPP_SF_SdD
0x1800078c4  mov     eax, ebx
0x1800078c6  mov     rcx, [rbp+180h+var_20]
0x1800078cd  xor     rcx, rsp; StackCookie
0x1800078d0  call    __security_check_cookie
0x1800078d5  lea     r11, [rsp+280h+var_10]
0x1800078dd  mov     rbx, [r11+30h]
0x1800078e1  mov     rsi, [r11+38h]
0x1800078e5  mov     rsp, r11
0x1800078e8  pop     r14
0x1800078ea  pop     rdi
0x1800078eb  pop     rbp
0x1800078ec  retn
```
