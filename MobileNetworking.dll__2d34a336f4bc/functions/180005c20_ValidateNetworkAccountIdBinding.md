# ValidateNetworkAccountIdBinding

- ea: `0x180005c20`
- end: `0x180005e26`
- name: `ValidateNetworkAccountIdBinding`
- size: `518`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180005c20`
- `0x180006000`
- `0x180006340`
- `0x180008ff0`
- `0x180009850`
- `0x18000b6f4`
- `0x18000efc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180005dc3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180005dc3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005d33`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005d33`

## string_xrefs

- `0x180005d01`: `BindingToken`

## pseudocode

```c
__int64 __fastcall ValidateNetworkAccountIdBinding(unsigned __int16 *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  PVOID *v6; // rcx
  signed int BindingRegistryPath; // ebx
  unsigned __int64 v8; // r8
  LSTATUS ValueW; // eax
  DWORD pcbData[4]; // [rsp+40h] [rbp-368h] BYREF
  unsigned __int16 v12[72]; // [rsp+50h] [rbp-358h] BYREF
  _BYTE pvData[144]; // [rsp+E0h] [rbp-2C8h] BYREF
  WCHAR SubKey[264]; // [rsp+170h] [rbp-238h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_07e8a800474135c1ead0ae2afd1c7d8b_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && a1 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x10) != 0 )
      WPP_SF_SS(
        (unsigned int)v6[2],
        12,
        (unsigned int)WPP_07e8a800474135c1ead0ae2afd1c7d8b_Traceguids,
        (_DWORD)a1,
        (__int64)a2);
    BindingRegistryPath = GetBindingRegistryPath(a2, (unsigned __int64)a2, SubKey);
    if ( BindingRegistryPath >= 0 )
    {
      pcbData[0] = 136;
      ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"BindingToken", 0x20000002u, 0, pvData, pcbData);
      BindingRegistryPath = ValueW;
      if ( !ValueW )
        goto LABEL_19;
      if ( ValueW > 0 )
        BindingRegistryPath = (unsigned __int16)ValueW | 0x80070000;
    }
    if ( BindingRegistryPath == -2147024894 )
    {
LABEL_21:
      BindingRegistryPath = -2147483636;
      goto LABEL_12;
    }
    if ( BindingRegistryPath < 0 )
    {
LABEL_12:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_07e8a800474135c1ead0ae2afd1c7d8b_Traceguids,
          (unsigned int)BindingRegistryPath);
      return (unsigned int)BindingRegistryPath;
    }
LABEL_19:
    BindingRegistryPath = CalculateBindingToken(a1, a3, v8, v12);
    if ( BindingRegistryPath < 0 || !(unsigned int)_o__wcsnicmp(pvData, v12, 68) )
      goto LABEL_12;
    goto LABEL_21;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
    WPP_SF_(v6[2], 11, WPP_07e8a800474135c1ead0ae2afd1c7d8b_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180005c20  mov     [rsp+arg_18], rbx
0x180005c25  push    rbp
0x180005c26  push    rsi
0x180005c27  push    rdi
0x180005c28  sub     rsp, 390h
0x180005c2f  mov     rax, cs:__security_cookie
0x180005c36  xor     rax, rsp
0x180005c39  mov     [rsp+3A8h+var_28], rax
0x180005c41  mov     rsi, r8
0x180005c44  mov     rbx, rdx
0x180005c47  mov     rdi, rcx
0x180005c4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c51  lea     rbp, WPP_GLOBAL_Control
0x180005c58  cmp     rcx, rbp
0x180005c5b  jz      short loc_180005C67
0x180005c5d  test    byte ptr [rcx+1Ch], 10h
0x180005c61  jnz     loc_180005D53
0x180005c67  test    rbx, rbx
0x180005c6a  jz      short loc_180005CDF
0x180005c6c  test    rdi, rdi
0x180005c6f  jz      short loc_180005CDF
0x180005c71  cmp     rcx, rbp
0x180005c74  jz      short loc_180005C80
0x180005c76  test    byte ptr [rcx+1Ch], 10h
0x180005c7a  jnz     loc_180005D74
0x180005c80  lea     r8, [rsp+3A8h+SubKey]; unsigned __int16 *
0x180005c88  mov     rcx, rbx; unsigned __int16 *
0x180005c8b  call    ?GetBindingRegistryPath@@YAJPEBG_KPEAG@Z; GetBindingRegistryPath(ushort const *,unsigned __int64,ushort *)
0x180005c90  mov     ebx, eax
0x180005c92  test    eax, eax
0x180005c94  jns     short loc_180005CEF
0x180005c96  cmp     ebx, 80070002h
0x180005c9c  jz      loc_180005DD1
0x180005ca2  test    ebx, ebx
0x180005ca4  jns     loc_180005D96
0x180005caa  mov     rcx, cs:WPP_GLOBAL_Control
0x180005cb1  cmp     rcx, rbp
0x180005cb4  jnz     loc_180005DDB
0x180005cba  mov     eax, ebx
0x180005cbc  mov     rcx, [rsp+3A8h+var_28]
0x180005cc4  xor     rcx, rsp; StackCookie
0x180005cc7  call    __security_check_cookie
0x180005ccc  mov     rbx, [rsp+3A8h+arg_18]
0x180005cd4  add     rsp, 390h
0x180005cdb  pop     rdi
0x180005cdc  pop     rsi
0x180005cdd  pop     rbp
0x180005cde  retn
0x180005cdf  cmp     rcx, rbp
0x180005ce2  jnz     loc_180005E02
0x180005ce8  mov     eax, 80070057h
0x180005ced  jmp     short loc_180005CBC
0x180005cef  lea     rax, [rsp+3A8h+var_368]
0x180005cf4  mov     [rsp+3A8h+var_368], 88h
0x180005cfc  mov     [rsp+3A8h+pcbData], rax; pcbData
0x180005d01  lea     r8, aBindingtoken; "BindingToken"
0x180005d08  lea     rax, [rsp+3A8h+var_2C8]
0x180005d10  mov     r9d, 20000002h; dwFlags
0x180005d16  mov     [rsp+3A8h+pvData], rax; pvData
0x180005d1b  lea     rdx, [rsp+3A8h+SubKey]; lpSubKey
0x180005d23  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180005d2a  mov     [rsp+3A8h+pdwType], 0; pdwType
0x180005d33  call    cs:__imp_RegGetValueW
0x180005d39  mov     ebx, eax
0x180005d3b  test    eax, eax
0x180005d3d  jz      short loc_180005D96
0x180005d3f  jle     loc_180005C96
0x180005d45  movzx   ebx, ax
0x180005d48  or      ebx, 80070000h
0x180005d4e  jmp     loc_180005C96
0x180005d53  mov     rcx, [rcx+10h]
0x180005d57  lea     r8, WPP_07e8a800474135c1ead0ae2afd1c7d8b_Traceguids
0x180005d5e  mov     edx, 0Ah
0x180005d63  call    WPP_SF_
0x180005d68  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d6f  jmp     loc_180005C67
0x180005d74  mov     rcx, [rcx+10h]
0x180005d78  lea     r8, WPP_07e8a800474135c1ead0ae2afd1c7d8b_Traceguids
0x180005d7f  mov     edx, 0Ch
0x180005d84  mov     [rsp+3A8h+pdwType], rbx
0x180005d89  mov     r9, rdi
0x180005d8c  call    WPP_SF_SS
0x180005d91  jmp     loc_180005C80
0x180005d96  lea     r9, [rsp+3A8h+var_358]; unsigned __int16 *
0x180005d9b  mov     rdx, rsi; unsigned __int16 *
0x180005d9e  mov     rcx, rdi; unsigned __int16 *
0x180005da1  call    ?CalculateBindingToken@@YAJPEBG0_KPEAG@Z; CalculateBindingToken(ushort const *,ushort const *,unsigned __int64,ushort *)
0x180005da6  mov     ebx, eax
0x180005da8  test    eax, eax
0x180005daa  js      loc_180005CAA
0x180005db0  mov     r8d, 44h ; 'D'
0x180005db6  lea     rdx, [rsp+3A8h+var_358]
0x180005dbb  lea     rcx, [rsp+3A8h+var_2C8]
0x180005dc3  call    cs:__imp__o__wcsnicmp
0x180005dc9  test    eax, eax
0x180005dcb  jz      loc_180005CAA
0x180005dd1  mov     ebx, 8000000Ch
0x180005dd6  jmp     loc_180005CAA
0x180005ddb  test    byte ptr [rcx+1Ch], 10h
0x180005ddf  jz      loc_180005CBA
0x180005de5  mov     rcx, [rcx+10h]
0x180005de9  lea     r8, WPP_07e8a800474135c1ead0ae2afd1c7d8b_Traceguids
0x180005df0  mov     edx, 0Dh
0x180005df5  mov     r9d, ebx
0x180005df8  call    WPP_SF_d
0x180005dfd  jmp     loc_180005CBA
0x180005e02  test    byte ptr [rcx+1Ch], 2
0x180005e06  jz      loc_180005CE8
0x180005e0c  mov     rcx, [rcx+10h]
0x180005e10  lea     r8, WPP_07e8a800474135c1ead0ae2afd1c7d8b_Traceguids
0x180005e17  mov     edx, 0Bh
0x180005e1c  call    WPP_SF_
0x180005e21  jmp     loc_180005CE8
```
