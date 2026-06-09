# GetOemIhvSmsBindingDeviceInterfacePath

- ea: `0x18000dc90`
- end: `0x18000de2a`
- name: `GetOemIhvSmsBindingDeviceInterfacePath`
- size: `410`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, _WORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180006000`
- `0x180008ff0`
- `0x180009850`
- `0x18000b6f4`
- `0x18000dc90`
- `0x18000de30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000dd9a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000dd9a`

## string_xrefs

- `0x18000dd79`: `SmsDeviceBindingDeviceInterfacePath`

## pseudocode

```c
__int64 __fastcall GetOemIhvSmsBindingDeviceInterfacePath(unsigned __int16 *a1, __int64 a2, _WORD *a3)
{
  PVOID *v6; // rcx
  __int64 v7; // rdx
  int BindingRegistryPath; // ebx
  LSTATUS ValueW; // eax
  DWORD pcbData[4]; // [rsp+40h] [rbp-258h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-248h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_805f8623832e3be342dd4daabae23659_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 2) == 0 )
      return 2147942487LL;
    v7 = 18;
LABEL_27:
    WPP_SF_(v6[2], v7, WPP_805f8623832e3be342dd4daabae23659_Traceguids);
    return 2147942487LL;
  }
  if ( !a3 || !a2 )
  {
    if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 2) == 0 )
      return 2147942487LL;
    v7 = 19;
    goto LABEL_27;
  }
  *a3 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_805f8623832e3be342dd4daabae23659_Traceguids, a1);
  BindingRegistryPath = GetBindingRegistryPath(a1, a2, SubKey);
  if ( BindingRegistryPath < 0 )
    goto LABEL_18;
  *(_QWORD *)pcbData = 2 * a2;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"SmsDeviceBindingDeviceInterfacePath", 0x20000002u, 0, a3, pcbData);
  if ( ValueW )
  {
    if ( ValueW > 0 )
      BindingRegistryPath = (unsigned __int16)ValueW | 0x80070000;
    else
      BindingRegistryPath = ValueW;
LABEL_18:
    if ( BindingRegistryPath == -2147024894 )
      BindingRegistryPath = -2147023728;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_805f8623832e3be342dd4daabae23659_Traceguids,
      (unsigned int)BindingRegistryPath);
  return (unsigned int)BindingRegistryPath;
}

```

## disassembly

```asm
0x18000dc90  push    rbx
0x18000dc92  push    rbp
0x18000dc93  push    rsi
0x18000dc94  push    rdi
0x18000dc95  push    r14
0x18000dc97  sub     rsp, 270h
0x18000dc9e  mov     rax, cs:__security_cookie
0x18000dca5  xor     rax, rsp
0x18000dca8  mov     [rsp+298h+var_38], rax
0x18000dcb0  mov     rdi, r8
0x18000dcb3  mov     rsi, rdx
0x18000dcb6  mov     rbx, rcx
0x18000dcb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcc0  lea     rbp, WPP_GLOBAL_Control
0x18000dcc7  lea     r14, WPP_805f8623832e3be342dd4daabae23659_Traceguids
0x18000dcce  cmp     rcx, rbp
0x18000dcd1  jz      short loc_18000DCF1
0x18000dcd3  test    byte ptr [rcx+1Ch], 10h
0x18000dcd7  jz      short loc_18000DCF1
0x18000dcd9  mov     rcx, [rcx+10h]
0x18000dcdd  mov     edx, 11h
0x18000dce2  mov     r8, r14
0x18000dce5  call    WPP_SF_
0x18000dcea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcf1  test    rbx, rbx
0x18000dcf4  jnz     short loc_18000DD11
0x18000dcf6  cmp     rcx, rbp
0x18000dcf9  jz      loc_18000DE07
0x18000dcff  test    byte ptr [rcx+1Ch], 2
0x18000dd03  jz      loc_18000DE07
0x18000dd09  lea     edx, [rbx+12h]
0x18000dd0c  jmp     loc_18000DDFB
0x18000dd11  test    rdi, rdi
0x18000dd14  jz      loc_18000DDEB
0x18000dd1a  cmp     rsi, 1
0x18000dd1e  jb      loc_18000DDEB
0x18000dd24  xor     eax, eax
0x18000dd26  mov     [rdi], ax
0x18000dd29  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd30  cmp     rcx, rbp
0x18000dd33  jz      short loc_18000DD4D
0x18000dd35  test    byte ptr [rcx+1Ch], 10h
0x18000dd39  jz      short loc_18000DD4D
0x18000dd3b  mov     rcx, [rcx+10h]
0x18000dd3f  lea     edx, [rax+14h]
0x18000dd42  mov     r9, rbx
0x18000dd45  mov     r8, r14
0x18000dd48  call    WPP_SF_S
0x18000dd4d  lea     r8, [rsp+298h+SubKey]; unsigned __int16 *
0x18000dd52  mov     rcx, rbx; unsigned __int16 *
0x18000dd55  call    ?GetBindingRegistryPath@@YAJPEBG_KPEAG@Z; GetBindingRegistryPath(ushort const *,unsigned __int64,ushort *)
0x18000dd5a  mov     ebx, eax
0x18000dd5c  test    eax, eax
0x18000dd5e  js      short loc_18000DDB3
0x18000dd60  lea     rcx, [rsi+rsi]
0x18000dd64  mov     r9d, 20000002h; dwFlags
0x18000dd6a  lea     rax, [rsp+298h+var_258]
0x18000dd6f  mov     qword ptr [rsp+298h+var_258], rcx
0x18000dd74  mov     [rsp+298h+pcbData], rax; pcbData
0x18000dd79  lea     r8, aSmsdevicebindi; "SmsDeviceBindingDeviceInterfacePath"
0x18000dd80  mov     [rsp+298h+pvData], rdi; pvData
0x18000dd85  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x18000dd8a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000dd91  mov     [rsp+298h+pdwType], 0; pdwType
0x18000dd9a  call    cs:__imp_RegGetValueW
0x18000dda0  test    eax, eax
0x18000dda2  jz      short loc_18000DDC1
0x18000dda4  jg      short loc_18000DDAA
0x18000dda6  mov     ebx, eax
0x18000dda8  jmp     short loc_18000DDB3
0x18000ddaa  movzx   ebx, ax
0x18000ddad  or      ebx, 80070000h
0x18000ddb3  cmp     ebx, 80070002h
0x18000ddb9  mov     eax, 80070490h
0x18000ddbe  cmovz   ebx, eax
0x18000ddc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddc8  cmp     rcx, rbp
0x18000ddcb  jz      short loc_18000DDE7
0x18000ddcd  test    byte ptr [rcx+1Ch], 10h
0x18000ddd1  jz      short loc_18000DDE7
0x18000ddd3  mov     rcx, [rcx+10h]
0x18000ddd7  mov     edx, 15h
0x18000dddc  mov     r9d, ebx
0x18000dddf  mov     r8, r14
0x18000dde2  call    WPP_SF_d
0x18000dde7  mov     eax, ebx
0x18000dde9  jmp     short loc_18000DE0C
0x18000ddeb  cmp     rcx, rbp
0x18000ddee  jz      short loc_18000DE07
0x18000ddf0  test    byte ptr [rcx+1Ch], 2
0x18000ddf4  jz      short loc_18000DE07
0x18000ddf6  mov     edx, 13h
0x18000ddfb  mov     rcx, [rcx+10h]
0x18000ddff  mov     r8, r14
0x18000de02  call    WPP_SF_
0x18000de07  mov     eax, 80070057h
0x18000de0c  mov     rcx, [rsp+298h+var_38]
0x18000de14  xor     rcx, rsp; StackCookie
0x18000de17  call    __security_check_cookie
0x18000de1c  add     rsp, 270h
0x18000de23  pop     r14
0x18000de25  pop     rdi
0x18000de26  pop     rsi
0x18000de27  pop     rbp
0x18000de28  pop     rbx
0x18000de29  retn
```
