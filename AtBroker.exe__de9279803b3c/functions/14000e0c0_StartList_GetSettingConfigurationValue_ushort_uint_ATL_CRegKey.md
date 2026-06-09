# StartList::GetSettingConfigurationValue(ushort *,uint,ATL::CRegKey &)

- ea: `0x14000e0c0`
- end: `0x14000e1d6`
- name: `?GetSettingConfigurationValue@StartList@@AEAAXPEAGIAEAVCRegKey@ATL@@@Z`
- size: `278`
- prototype: `void __fastcall(StartList *this, unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ee8c`

## callees

- `0x140006a78`
- `0x140007708`
- `0x14000e0c0`
- `0x1400111c0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000e126`
- `ADVAPI32!RegOpenKeyExW` at `0x14000e126`
- `ADVAPI32!RegCloseKey` at `0x14000e13e`
- `ADVAPI32!RegCloseKey` at `0x14000e13e`

## string_xrefs

- `0x14000e18b`: `SettingConfiguration`
- `0x14000e118`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`
- `0x14000e108`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`

## pseudocode

```c
void __fastcall StartList::GetSettingConfigurationValue(
        StartList *this,
        unsigned __int16 *a2,
        unsigned int a3,
        HKEY *a4)
{
  int v6; // eax
  const WCHAR *v7; // rdx
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // eax
  __int64 v13; // r8
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v15; // [rsp+50h] [rbp+18h] BYREF

  v15 = a3;
  phkResult = (HKEY)this;
  *a2 = 0;
  v6 = IsInteractiveUser();
  phkResult = 0;
  if ( v6 )
  {
    v7 = StartList::_accessibilityKeyString;
    v8 = -2147483647;
  }
  else
  {
    v7 = StartList::_oobeAccessibilityKeyString;
    v8 = -2147483646;
  }
  v9 = RegOpenKeyExW((HKEY)v8, v7, 0, 0x2001Fu, &phkResult);
  v11 = v9;
  if ( !v9 )
  {
    v11 = 0;
    if ( *a4 )
      v11 = (unsigned int)RegCloseKey(*a4);
    *a4 = phkResult;
  }
  if ( (_DWORD)v11
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, v10, v11);
  }
  v15 = 1024;
  v12 = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)a4, StartList::_settingConfiguration, a2, &v15);
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, v13, v12);
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x14000e0c0  mov     rax, rsp
0x14000e0c3  mov     [rax+10h], rbx
0x14000e0c7  mov     [rax+20h], rsi
0x14000e0cb  mov     [rax+18h], r8d
0x14000e0cf  mov     [rax+8], rcx
0x14000e0d3  push    rdi
0x14000e0d4  sub     rsp, 30h
0x14000e0d8  xor     eax, eax
0x14000e0da  mov     rbx, r9
0x14000e0dd  mov     [rdx], ax
0x14000e0e0  mov     rdi, rdx
0x14000e0e3  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x14000e0e8  xor     r8d, r8d; ulOptions
0x14000e0eb  mov     [rsp+38h+arg_0], 0
0x14000e0f4  test    eax, eax
0x14000e0f6  mov     r9d, 2001Fh; samDesired
0x14000e0fc  lea     rax, [rsp+38h+arg_0]
0x14000e101  mov     [rsp+38h+phkResult], rax; phkResult
0x14000e106  jz      short loc_14000E118
0x14000e108  lea     rdx, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000e10f  mov     rcx, 0FFFFFFFF80000001h
0x14000e116  jmp     short loc_14000E126
0x14000e118  lea     rdx, ?_oobeAccessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000e11f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000e126  call    cs:__imp_RegOpenKeyExW
0x14000e12c  mov     r9d, eax
0x14000e12f  test    eax, eax
0x14000e131  jnz     short loc_14000E14F
0x14000e133  mov     rcx, [rbx]; hKey
0x14000e136  xor     r9d, r9d
0x14000e139  test    rcx, rcx
0x14000e13c  jz      short loc_14000E147
0x14000e13e  call    cs:__imp_RegCloseKey
0x14000e144  mov     r9d, eax
0x14000e147  mov     rax, [rsp+38h+arg_0]
0x14000e14c  mov     [rbx], rax
0x14000e14f  lea     rsi, WPP_GLOBAL_Control
0x14000e156  test    r9d, r9d
0x14000e159  jz      short loc_14000E17B
0x14000e15b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e162  cmp     rcx, rsi
0x14000e165  jz      short loc_14000E17B
0x14000e167  test    byte ptr [rcx+1Ch], 8
0x14000e16b  jz      short loc_14000E17B
0x14000e16d  mov     rcx, [rcx+10h]
0x14000e171  mov     edx, 22h ; '"'
0x14000e176  call    WPP_SF_d
0x14000e17b  lea     r9, [rsp+38h+arg_10]; unsigned int *
0x14000e180  mov     [rsp+38h+arg_10], 400h
0x14000e188  mov     r8, rdi; unsigned __int16 *
0x14000e18b  lea     rdx, ?_settingConfiguration@StartList@@0PAGA; "SettingConfiguration"
0x14000e192  mov     rcx, rbx; this
0x14000e195  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14000e19a  test    eax, eax
0x14000e19c  jz      short loc_14000E1C6
0x14000e19e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e1a5  cmp     rcx, rsi
0x14000e1a8  jz      short loc_14000E1C1
0x14000e1aa  test    byte ptr [rcx+1Ch], 8
0x14000e1ae  jz      short loc_14000E1C1
0x14000e1b0  mov     rcx, [rcx+10h]
0x14000e1b4  mov     edx, 23h ; '#'
0x14000e1b9  mov     r9d, eax
0x14000e1bc  call    WPP_SF_d
0x14000e1c1  xor     eax, eax
0x14000e1c3  mov     [rdi], ax
0x14000e1c6  mov     rbx, [rsp+38h+arg_8]
0x14000e1cb  mov     rsi, [rsp+38h+arg_18]
0x14000e1d0  add     rsp, 30h
0x14000e1d4  pop     rdi
0x14000e1d5  retn
```
