# StartList::SetNarratorAfterSigninResetCompleted(void)

- ea: `0x1400100d8`
- end: `0x14001018e`
- name: `?SetNarratorAfterSigninResetCompleted@StartList@@SAXXZ`
- size: `182`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140009264`
- `0x14000c8b4`

## callees

- `0x14000ab98`
- `0x1400100d8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140010106`
- `ADVAPI32!RegOpenKeyExW` at `0x140010106`
- `ADVAPI32!RegCloseKey` at `0x140010182`
- `ADVAPI32!RegCloseKey` at `0x140010182`
- `KERNEL32!RegSetValueExW` at `0x14001013a`
- `KERNEL32!RegSetValueExW` at `0x14001013a`

## string_xrefs

- `0x14001012e`: `NarratorAfterSigninResetCompleted`
- `0x1400100f8`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`

## pseudocode

```c
void StartList::SetNarratorAfterSigninResetCompleted(void)
{
  LSTATUS v0; // eax
  int Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_CURRENT_USER, StartList::_accessibilityKeyString, 0, 0x2001Fu, &hKey);
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids,
        v0 | 0x10000000u);
  }
  else
  {
    Data = 1;
    RegSetValueExW(hKey, L"NarratorAfterSigninResetCompleted", 0, 4u, (const BYTE *)&Data, 4u);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1400100d8  sub     rsp, 38h
0x1400100dc  mov     [rsp+38h+hKey], 0
0x1400100e5  lea     rax, [rsp+38h+hKey]
0x1400100ea  mov     [rsp+38h+phkResult], rax; phkResult
0x1400100ef  mov     r9d, 2001Fh; samDesired
0x1400100f5  xor     r8d, r8d; ulOptions
0x1400100f8  lea     rdx, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400100ff  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140010106  call    cs:__imp_RegOpenKeyExW
0x14001010c  test    eax, eax
0x14001010e  jnz     short loc_140010142
0x140010110  mov     [rsp+38h+Data], 1
0x140010118  lea     r9d, [rax+4]; dwType
0x14001011c  mov     [rsp+38h+cbData], r9d; cbData
0x140010121  lea     rax, [rsp+38h+Data]
0x140010126  mov     [rsp+38h+phkResult], rax; lpData
0x14001012b  xor     r8d, r8d; Reserved
0x14001012e  lea     rdx, aNarratorafters; "NarratorAfterSigninResetCompleted"
0x140010135  mov     rcx, [rsp+38h+hKey]; hKey
0x14001013a  call    cs:__imp_RegSetValueExW
0x140010140  jmp     short loc_140010178
0x140010142  lea     rdx, WPP_GLOBAL_Control
0x140010149  mov     rcx, cs:WPP_GLOBAL_Control
0x140010150  cmp     rcx, rdx
0x140010153  jz      short loc_140010178
0x140010155  test    byte ptr [rcx+1Ch], 8
0x140010159  jz      short loc_140010178
0x14001015b  bts     eax, 1Ch
0x14001015f  mov     edx, 34h ; '4'
0x140010164  mov     r9d, eax
0x140010167  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14001016e  mov     rcx, [rcx+10h]
0x140010172  call    WPP_SF_D
0x140010177  nop
0x140010178  mov     rcx, [rsp+38h+hKey]; hKey
0x14001017d  test    rcx, rcx
0x140010180  jz      short loc_140010189
0x140010182  call    cs:__imp_RegCloseKey
0x140010188  nop
0x140010189  add     rsp, 38h
0x14001018d  retn
```
