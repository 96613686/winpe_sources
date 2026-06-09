# winrt::impl::produce<winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper,winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::CanUseWUAsRepairSource(bool *,uint *,winrt::hresult *)

- ea: `0x180006d70`
- end: `0x180006e1f`
- name: `?CanUseWUAsRepairSource@?$produce@VCBSHelper@implementation@WaasMedicDocked@Internal@Windows@winrt@@UICBSHelper@3456@@impl@winrt@@UEAAHPEA_NPEAIPEAUhresult@3@@Z`
- size: `175`
- prototype: `__int64 __fastcall(__int64, bool *, _DWORD *, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180006d70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006dd3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006dd3`

## string_xrefs

- `0x180006dbe`: `UseWindowsUpdate`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper,winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::CanUseWUAsRepairSource(
        __int64 a1,
        bool *a2,
        _DWORD *a3,
        int *a4)
{
  int ValueW; // eax
  bool v8; // sf
  int v9; // eax
  bool v10; // al
  int v12; // [rsp+50h] [rbp+8h] BYREF
  int v13; // [rsp+54h] [rbp+Ch]
  DWORD v14; // [rsp+58h] [rbp+10h] BYREF

  v13 = HIDWORD(a1);
  *a2 = 0;
  v12 = 0;
  v14 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\Servicing",
             L"UseWindowsUpdate",
             0x10u,
             0,
             &v12,
             &v14);
  v8 = ValueW < 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
    v8 = ValueW < 0;
  }
  if ( !v8 )
  {
    v9 = v12;
    *a3 = v12;
    v10 = v9 != 2;
LABEL_7:
    *a2 = v10;
    ValueW = 0;
    goto LABEL_8;
  }
  if ( ValueW == -2147024894 )
  {
    v10 = 1;
    goto LABEL_7;
  }
LABEL_8:
  *a4 = ValueW;
  return 0;
}

```

## disassembly

```asm
0x180006d70  mov     r11, rsp
0x180006d73  mov     [r11+18h], rbx
0x180006d77  mov     [r11+20h], rsi
0x180006d7b  mov     [r11+8], rcx
0x180006d7f  push    rdi
0x180006d80  sub     rsp, 40h
0x180006d84  mov     rdi, r9
0x180006d87  mov     rsi, r8
0x180006d8a  mov     rbx, rdx
0x180006d8d  mov     byte ptr [rdx], 0
0x180006d90  mov     [rsp+48h+arg_0], 0
0x180006d98  mov     [rsp+48h+arg_8], 4
0x180006da0  lea     rax, [r11+10h]
0x180006da4  mov     [r11-18h], rax
0x180006da8  lea     rax, [r11+8]
0x180006dac  mov     [r11-20h], rax
0x180006db0  mov     qword ptr [r11-28h], 0
0x180006db8  mov     r9d, 10h; dwFlags
0x180006dbe  lea     r8, Value; "UseWindowsUpdate"
0x180006dc5  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180006dcc  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180006dd3  call    cs:__imp_RegGetValueW
0x180006dd9  test    eax, eax
0x180006ddb  jle     short loc_180006DE7
0x180006ddd  movzx   eax, ax
0x180006de0  or      eax, 80070000h
0x180006de5  test    eax, eax
0x180006de7  js      short loc_180006DF7
0x180006de9  mov     eax, [rsp+48h+arg_0]
0x180006ded  mov     [rsi], eax
0x180006def  cmp     eax, 2
0x180006df2  setnz   al
0x180006df5  jmp     short loc_180006E00
0x180006df7  cmp     eax, 80070002h
0x180006dfc  jnz     short loc_180006E04
0x180006dfe  mov     al, 1
0x180006e00  mov     [rbx], al
0x180006e02  xor     eax, eax
0x180006e04  mov     [rdi], eax
0x180006e06  xor     eax, eax
0x180006e08  jmp     short loc_180006E0E
0x180006e0a  mov     eax, [rsp+48h+arg_0]
0x180006e0e  mov     rbx, [rsp+48h+arg_10]
0x180006e13  mov     rsi, [rsp+48h+arg_18]
0x180006e18  add     rsp, 40h
0x180006e1c  pop     rdi
0x180006e1d  retn
```
