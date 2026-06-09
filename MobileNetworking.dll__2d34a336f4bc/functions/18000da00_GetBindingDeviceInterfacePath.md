# _GetBindingDeviceInterfacePath

- ea: `0x18000da00`
- end: `0x18000db9d`
- name: `_GetBindingDeviceInterfacePath`
- size: `413`
- prototype: `__int64 __fastcall(unsigned __int16 *, LPCWSTR lpValue, __int64, _WORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000dbb0`
- `0x18000dc20`

## callees

- `0x180005910`
- `0x180008ff0`
- `0x180009850`
- `0x18000b6f4`
- `0x18000da00`
- `0x18000de30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000db0b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000db0b`

## pseudocode

```c
__int64 __fastcall GetBindingDeviceInterfacePath(unsigned __int16 *a1, LPCWSTR lpValue, __int64 a3, _WORD *a4)
{
  PVOID *v8; // rcx
  __int64 v9; // rdx
  int AccountRegistryPath; // ebx
  LSTATUS ValueW; // eax
  DWORD pcbData[4]; // [rsp+40h] [rbp-268h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-258h] BYREF

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_805f8623832e3be342dd4daabae23659_Traceguids);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 2) == 0 )
      return 2147942487LL;
    v9 = 11;
LABEL_27:
    WPP_SF_(v8[2], v9, WPP_805f8623832e3be342dd4daabae23659_Traceguids);
    return 2147942487LL;
  }
  if ( !a4 || !a3 )
  {
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 2) == 0 )
      return 2147942487LL;
    v9 = 12;
    goto LABEL_27;
  }
  *a4 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_805f8623832e3be342dd4daabae23659_Traceguids, a1);
  AccountRegistryPath = GetAccountRegistryPath(a1, (__int64)lpValue, SubKey);
  if ( AccountRegistryPath < 0 )
    goto LABEL_18;
  *(_QWORD *)pcbData = 2 * a3;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, lpValue, 0x20000002u, 0, a4, pcbData);
  if ( ValueW )
  {
    if ( ValueW > 0 )
      AccountRegistryPath = (unsigned __int16)ValueW | 0x80070000;
    else
      AccountRegistryPath = ValueW;
LABEL_18:
    if ( AccountRegistryPath == -2147024894 )
      AccountRegistryPath = -2147023728;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_805f8623832e3be342dd4daabae23659_Traceguids,
      (unsigned int)AccountRegistryPath);
  return (unsigned int)AccountRegistryPath;
}

```

## disassembly

```asm
0x18000da00  push    rbx
0x18000da02  push    rbp
0x18000da03  push    rsi
0x18000da04  push    rdi
0x18000da05  push    r14
0x18000da07  push    r15
0x18000da09  sub     rsp, 278h
0x18000da10  mov     rax, cs:__security_cookie
0x18000da17  xor     rax, rsp
0x18000da1a  mov     [rsp+2A8h+var_48], rax
0x18000da22  mov     rdi, r9
0x18000da25  mov     rsi, r8
0x18000da28  mov     rbp, rdx
0x18000da2b  mov     rbx, rcx
0x18000da2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da35  lea     r14, WPP_GLOBAL_Control
0x18000da3c  lea     r15, WPP_805f8623832e3be342dd4daabae23659_Traceguids
0x18000da43  cmp     rcx, r14
0x18000da46  jz      short loc_18000DA66
0x18000da48  test    byte ptr [rcx+1Ch], 10h
0x18000da4c  jz      short loc_18000DA66
0x18000da4e  mov     rcx, [rcx+10h]
0x18000da52  mov     edx, 0Ah
0x18000da57  mov     r8, r15
0x18000da5a  call    WPP_SF_
0x18000da5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da66  test    rbx, rbx
0x18000da69  jnz     short loc_18000DA86
0x18000da6b  cmp     rcx, r14
0x18000da6e  jz      loc_18000DB78
0x18000da74  test    byte ptr [rcx+1Ch], 2
0x18000da78  jz      loc_18000DB78
0x18000da7e  lea     edx, [rbx+0Bh]
0x18000da81  jmp     loc_18000DB6C
0x18000da86  test    rdi, rdi
0x18000da89  jz      loc_18000DB5C
0x18000da8f  cmp     rsi, 1
0x18000da93  jb      loc_18000DB5C
0x18000da99  xor     eax, eax
0x18000da9b  mov     [rdi], ax
0x18000da9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000daa5  cmp     rcx, r14
0x18000daa8  jz      short loc_18000DAC2
0x18000daaa  test    byte ptr [rcx+1Ch], 10h
0x18000daae  jz      short loc_18000DAC2
0x18000dab0  mov     rcx, [rcx+10h]
0x18000dab4  lea     edx, [rax+0Dh]
0x18000dab7  mov     r9, rbx
0x18000daba  mov     r8, r15
0x18000dabd  call    WPP_SF_S
0x18000dac2  lea     r8, [rsp+2A8h+SubKey]; unsigned __int16 *
0x18000dac7  mov     rcx, rbx; unsigned __int16 *
0x18000daca  call    ?GetAccountRegistryPath@@YAJPEBG_KPEAG@Z; GetAccountRegistryPath(ushort const *,unsigned __int64,ushort *)
0x18000dacf  mov     ebx, eax
0x18000dad1  test    eax, eax
0x18000dad3  js      short loc_18000DB24
0x18000dad5  lea     rcx, [rsi+rsi]
0x18000dad9  mov     r9d, 20000002h; dwFlags
0x18000dadf  lea     rax, [rsp+2A8h+var_268]
0x18000dae4  mov     qword ptr [rsp+2A8h+var_268], rcx
0x18000dae9  mov     [rsp+2A8h+pcbData], rax; pcbData
0x18000daee  lea     rdx, [rsp+2A8h+SubKey]; lpSubKey
0x18000daf3  mov     [rsp+2A8h+pvData], rdi; pvData
0x18000daf8  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000daff  mov     r8, rbp; lpValue
0x18000db02  mov     [rsp+2A8h+pdwType], 0; pdwType
0x18000db0b  call    cs:__imp_RegGetValueW
0x18000db11  test    eax, eax
0x18000db13  jz      short loc_18000DB32
0x18000db15  jg      short loc_18000DB1B
0x18000db17  mov     ebx, eax
0x18000db19  jmp     short loc_18000DB24
0x18000db1b  movzx   ebx, ax
0x18000db1e  or      ebx, 80070000h
0x18000db24  cmp     ebx, 80070002h
0x18000db2a  mov     eax, 80070490h
0x18000db2f  cmovz   ebx, eax
0x18000db32  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db39  cmp     rcx, r14
0x18000db3c  jz      short loc_18000DB58
0x18000db3e  test    byte ptr [rcx+1Ch], 10h
0x18000db42  jz      short loc_18000DB58
0x18000db44  mov     rcx, [rcx+10h]
0x18000db48  mov     edx, 0Eh
0x18000db4d  mov     r9d, ebx
0x18000db50  mov     r8, r15
0x18000db53  call    WPP_SF_d
0x18000db58  mov     eax, ebx
0x18000db5a  jmp     short loc_18000DB7D
0x18000db5c  cmp     rcx, r14
0x18000db5f  jz      short loc_18000DB78
0x18000db61  test    byte ptr [rcx+1Ch], 2
0x18000db65  jz      short loc_18000DB78
0x18000db67  mov     edx, 0Ch
0x18000db6c  mov     rcx, [rcx+10h]
0x18000db70  mov     r8, r15
0x18000db73  call    WPP_SF_
0x18000db78  mov     eax, 80070057h
0x18000db7d  mov     rcx, [rsp+2A8h+var_48]
0x18000db85  xor     rcx, rsp; StackCookie
0x18000db88  call    __security_check_cookie
0x18000db8d  add     rsp, 278h
0x18000db94  pop     r15
0x18000db96  pop     r14
0x18000db98  pop     rdi
0x18000db99  pop     rsi
0x18000db9a  pop     rbp
0x18000db9b  pop     rbx
0x18000db9c  retn
```
