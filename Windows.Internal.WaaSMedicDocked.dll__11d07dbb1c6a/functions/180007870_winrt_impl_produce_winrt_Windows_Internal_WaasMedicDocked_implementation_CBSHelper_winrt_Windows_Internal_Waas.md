# winrt::impl::produce<winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper,winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::HasLocalRepairSource(bool *,winrt::hresult *)

- ea: `0x180007870`
- end: `0x180007942`
- name: `?HasLocalRepairSource@?$produce@VCBSHelper@implementation@WaasMedicDocked@Internal@Windows@winrt@@UICBSHelper@3456@@impl@winrt@@UEAAHPEA_NPEAUhresult@3@@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, _BYTE *, signed int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800048e4`
- `0x180007870`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800078fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800078fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800078b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800078b1`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper,winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::HasLocalRepairSource(
        __int64 a1,
        _BYTE *a2,
        signed int *a3)
{
  LSTATUS v5; // eax
  signed int v6; // ebx
  LSTATUS Value; // eax
  int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\Servicing",
         0,
         1u,
         &hKey);
  v6 = v5;
  if ( v5 >= 0 )
  {
    Value = RegQueryValueExW(hKey, L"LocalSource", 0, 0, 0, 0);
    v6 = Value;
    if ( Value > 0 )
      v6 = (unsigned __int16)Value | 0x80070000;
    if ( v6 >= 0 )
    {
      *a2 = 1;
    }
    else
    {
      if ( v6 != -2147024894 )
        goto LABEL_10;
      *a2 = 0;
    }
    v6 = 0;
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3A,
    (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
    (const char *)(unsigned int)v5,
    lpData);
LABEL_10:
  *a3 = v6;
  return 0;
}

```

## disassembly

```asm
0x180007870  mov     r11, rsp
0x180007873  mov     [r11+10h], rbx
0x180007877  mov     [r11+18h], rsi
0x18000787b  mov     [r11+8], rcx
0x18000787f  push    rdi
0x180007880  sub     rsp, 30h
0x180007884  mov     rsi, r8
0x180007887  mov     rdi, rdx
0x18000788a  mov     qword ptr [r11+8], 0
0x180007892  lea     rax, [r11+8]
0x180007896  mov     [r11-18h], rax
0x18000789a  mov     r9d, 1; samDesired
0x1800078a0  xor     r8d, r8d; ulOptions
0x1800078a3  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800078aa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800078b1  call    cs:__imp_RegOpenKeyExW
0x1800078b7  mov     ebx, eax
0x1800078b9  test    eax, eax
0x1800078bb  jns     short loc_1800078D8
0x1800078bd  mov     rcx, [rsp+38h]; this
0x1800078c2  mov     r9d, eax; char *
0x1800078c5  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x1800078cc  mov     edx, 3Ah ; ':'; void *
0x1800078d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800078d6  jmp     short loc_180007927
0x1800078d8  mov     [rsp+38h+lpcbData], 0; lpcbData
0x1800078e1  mov     [rsp+38h+lpData], 0; lpData
0x1800078ea  xor     r9d, r9d; lpType
0x1800078ed  xor     r8d, r8d; lpReserved
0x1800078f0  lea     rdx, ValueName; "LocalSource"
0x1800078f7  mov     rcx, [rsp+38h+hKey]; hKey
0x1800078fc  call    cs:__imp_RegQueryValueExW
0x180007902  mov     ebx, eax
0x180007904  test    eax, eax
0x180007906  jle     short loc_180007911
0x180007908  movzx   ebx, ax
0x18000790b  or      ebx, 80070000h
0x180007911  test    ebx, ebx
0x180007913  jns     short loc_180007922
0x180007915  cmp     ebx, 80070002h
0x18000791b  jnz     short loc_180007927
0x18000791d  mov     byte ptr [rdi], 0
0x180007920  jmp     short loc_180007925
0x180007922  mov     byte ptr [rdi], 1
0x180007925  xor     ebx, ebx
0x180007927  mov     [rsi], ebx
0x180007929  xor     eax, eax
0x18000792b  jmp     short loc_180007931
0x18000792d  mov     eax, dword ptr [rsp+38h+hKey]
0x180007931  mov     rbx, [rsp+38h+arg_8]
0x180007936  mov     rsi, [rsp+38h+arg_10]
0x18000793b  add     rsp, 30h
0x18000793f  pop     rdi
0x180007940  retn
```
