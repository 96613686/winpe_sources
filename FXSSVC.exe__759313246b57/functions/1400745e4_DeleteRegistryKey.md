# DeleteRegistryKey

- ea: `0x1400745e4`
- end: `0x140074801`
- name: `DeleteRegistryKey`
- size: `541`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000d178`
- `0x140022f30`
- `0x140074084`
- `0x140074230`
- `0x1400745e4`
- `0x140074808`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x1400745e4`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14007473b`
- `ADVAPI32!RegCloseKey` at `0x1400747bd`
- `ADVAPI32!RegCloseKey` at `0x14007473b`
- `ADVAPI32!RegCloseKey` at `0x1400747bd`
- `ADVAPI32!RegOpenKeyExW` at `0x140074676`
- `ADVAPI32!RegOpenKeyExW` at `0x140074676`
- `ADVAPI32!RegEnumKeyExW` at `0x14007471d`
- `ADVAPI32!RegEnumKeyExW` at `0x14007471d`
- `ADVAPI32!RegDeleteKeyW` at `0x14007474d`
- `ADVAPI32!RegDeleteKeyW` at `0x14007474d`
- `KERNEL32!SetLastError` at `0x1400747cb`
- `KERNEL32!SetLastError` at `0x1400747cb`

## pseudocode

```c
__int64 __fastcall DeleteRegistryKey(HKEY a1, const WCHAR *a2)
{
  unsigned int v4; // ebx
  CMapDeviceId *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  cchName = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids);
  }
  v4 = RegOpenKeyExW(a1, a2, 0, 0x3001Fu, &hKey);
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 11;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids, v4);
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
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = 13;
        goto LABEL_10;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
0x1400745e4  mov     [rsp-8+arg_10], rbx
0x1400745e9  mov     [rsp-8+arg_18], rsi
0x1400745ee  push    rbp
0x1400745ef  push    rdi
0x1400745f0  push    r12
0x1400745f2  lea     rbp, [rsp-170h]
0x1400745fa  sub     rsp, 270h
0x140074601  mov     rax, cs:__security_cookie
0x140074608  xor     rax, rsp
0x14007460b  mov     [rbp+180h+var_20], rax
0x140074612  mov     rsi, rdx
0x140074615  mov     [rsp+280h+hKey], 0
0x14007461e  mov     rdi, rcx
0x140074621  mov     [rsp+280h+cchName], 0
0x140074629  mov     rcx, cs:WPP_GLOBAL_Control
0x140074630  lea     r12, WPP_GLOBAL_Control
0x140074637  cmp     rcx, r12
0x14007463a  jz      short loc_14007465D
0x14007463c  test    byte ptr [rcx+1Ch], 2
0x140074640  jz      short loc_14007465D
0x140074642  cmp     byte ptr [rcx+19h], 5
0x140074646  jb      short loc_14007465D
0x140074648  mov     rcx, [rcx+10h]
0x14007464c  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x140074653  mov     edx, 0Ah
0x140074658  call    WPP_SF_
0x14007465d  lea     rax, [rsp+280h+hKey]
0x140074662  mov     r9d, 3001Fh; samDesired
0x140074668  xor     r8d, r8d; ulOptions
0x14007466b  mov     [rsp+280h+phkResult], rax; phkResult
0x140074670  mov     rdx, rsi; lpSubKey
0x140074673  mov     rcx, rdi; hKey
0x140074676  call    cs:__imp_RegOpenKeyExW
0x14007467d  nop     dword ptr [rax+rax+00h]
0x140074682  mov     ebx, eax
0x140074684  test    eax, eax
0x140074686  jz      short loc_1400746E0
0x140074688  mov     rcx, cs:WPP_GLOBAL_Control
0x14007468f  cmp     rcx, r12
0x140074692  jz      loc_1400747C9
0x140074698  test    byte ptr [rcx+1Ch], 2
0x14007469c  jz      loc_1400747C9
0x1400746a2  cmp     byte ptr [rcx+19h], 2
0x1400746a6  jb      loc_1400747C9
0x1400746ac  mov     edx, 0Bh
0x1400746b1  mov     rcx, [rcx+10h]
0x1400746b5  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x1400746bc  mov     r9d, ebx
0x1400746bf  call    WPP_SF_d
0x1400746c4  jmp     loc_1400747C9
0x1400746c9  mov     rcx, [rsp+280h+hKey]
0x1400746ce  lea     rdx, [rsp+280h+SubKey]
0x1400746d3  call    DeleteRegistryKey
0x1400746d8  test    eax, eax
0x1400746da  jz      loc_1400747D7
0x1400746e0  mov     rcx, [rsp+280h+hKey]; hKey
0x1400746e5  lea     r9, [rsp+280h+cchName]; lpcchName
0x1400746ea  mov     [rsp+280h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1400746f3  lea     r8, [rsp+280h+SubKey]; lpName
0x1400746f8  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x140074701  xor     edx, edx; dwIndex
0x140074703  mov     [rsp+280h+lpClass], 0; lpClass
0x14007470c  mov     [rsp+280h+phkResult], 0; lpReserved
0x140074715  mov     [rsp+280h+cchName], 104h
0x14007471d  call    cs:__imp_RegEnumKeyExW
0x140074724  nop     dword ptr [rax+rax+00h]
0x140074729  mov     ebx, eax
0x14007472b  test    eax, eax
0x14007472d  jz      short loc_1400746C9
0x14007472f  cmp     eax, 103h
0x140074734  jnz     short loc_140074788
0x140074736  mov     rcx, [rsp+280h+hKey]; hKey
0x14007473b  call    cs:__imp_RegCloseKey
0x140074742  nop     dword ptr [rax+rax+00h]
0x140074747  mov     rdx, rsi; lpSubKey
0x14007474a  mov     rcx, rdi; hKey
0x14007474d  call    cs:__imp_RegDeleteKeyW
0x140074754  nop     dword ptr [rax+rax+00h]
0x140074759  mov     ebx, eax
0x14007475b  test    eax, eax
0x14007475d  jz      short loc_140074781
0x14007475f  mov     rcx, cs:WPP_GLOBAL_Control
0x140074766  cmp     rcx, r12
0x140074769  jz      short loc_1400747C9
0x14007476b  test    byte ptr [rcx+1Ch], 2
0x14007476f  jz      short loc_1400747C9
0x140074771  cmp     byte ptr [rcx+19h], 2
0x140074775  jb      short loc_1400747C9
0x140074777  mov     edx, 0Dh
0x14007477c  jmp     loc_1400746B1
0x140074781  mov     eax, 1
0x140074786  jmp     short loc_1400747D9
0x140074788  mov     rcx, cs:WPP_GLOBAL_Control
0x14007478f  cmp     rcx, r12
0x140074792  jz      short loc_1400747B8
0x140074794  test    byte ptr [rcx+1Ch], 2
0x140074798  jz      short loc_1400747B8
0x14007479a  cmp     byte ptr [rcx+19h], 2
0x14007479e  jb      short loc_1400747B8
0x1400747a0  mov     rcx, [rcx+10h]
0x1400747a4  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x1400747ab  mov     edx, 0Ch
0x1400747b0  mov     r9d, ebx
0x1400747b3  call    WPP_SF_d
0x1400747b8  mov     rcx, [rsp+280h+hKey]; hKey
0x1400747bd  call    cs:__imp_RegCloseKey
0x1400747c4  nop     dword ptr [rax+rax+00h]
0x1400747c9  mov     ecx, ebx; dwErrCode
0x1400747cb  call    cs:__imp_SetLastError
0x1400747d2  nop     dword ptr [rax+rax+00h]
0x1400747d7  xor     eax, eax
0x1400747d9  mov     rcx, [rbp+180h+var_20]
0x1400747e0  xor     rcx, rsp; StackCookie
0x1400747e3  call    __security_check_cookie
0x1400747e8  lea     r11, [rsp+280h+var_10]
0x1400747f0  mov     rbx, [r11+30h]
0x1400747f4  mov     rsi, [r11+38h]
0x1400747f8  mov     rsp, r11
0x1400747fb  pop     r12
0x1400747fd  pop     rdi
0x1400747fe  pop     rbp
0x1400747ff  retn
```
