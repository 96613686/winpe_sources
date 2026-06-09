# GetRegDword(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,ulong *)

- ea: `0x18003fa08`
- end: `0x18003fb59`
- name: `?GetRegDword@@YAJPEAUHKEY__@@PEBG111PEAK@Z`
- size: `337`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, LPCWSTR lpValue, PVOID)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003f914`

## callees

- `0x180003450`
- `0x180003fe4`
- `0x18000912c`
- `0x1800097f8`
- `0x180034bdc`
- `0x18003fa08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003fb1c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003fb1c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18003faac`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18003faac`

## string_xrefs

- `0x18003faa5`: `WindowsUpdateUXRoot`
- `0x18003fa9e`: `SOFTWARE\Microsoft\WindowsUpdate\UX`
- `0x18003fa63`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`

## pseudocode

```c
LSTATUS __fastcall GetRegDword(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        LPCWSTR lpValue,
        PVOID pvData)
{
  int v6; // ebx
  __int64 v7; // rdx
  LSTATUS result; // eax
  unsigned int PersistedRegistryLocationW; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  int pdwType; // [rsp+20h] [rbp-248h]
  DWORD pcbData; // [rsp+40h] [rbp-228h] BYREF
  DWORD v14[3]; // [rsp+44h] [rbp-224h] BYREF
  WCHAR SubKey[256]; // [rsp+50h] [rbp-218h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v14[0] = 0;
  pcbData = 4;
  if ( !pvData )
  {
    v6 = -2147024809;
    v7 = 147;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
      (const char *)(unsigned int)v6,
      pdwType);
    return v6;
  }
  memset_0(SubKey, 0, sizeof(SubKey));
  pdwType = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"WindowsUpdateUXRoot",
                                 L"SOFTWARE\\Microsoft\\WindowsUpdate\\UX",
                                 SubKey,
                                 512);
  if ( PersistedRegistryLocationW )
    return wil::details::in1diag3::Return_Win32(retaddr, v10, v11, (const char *)PersistedRegistryLocationW, 0);
  v6 = StringCchCatW(SubKey, 0x100u, L"\\Settings");
  if ( v6 < 0 )
  {
    v7 = 159;
    goto LABEL_3;
  }
  result = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, lpValue, 0x10u, v14, pvData, &pcbData);
  if ( !result )
    return 0;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18003fa08  mov     [rsp+arg_0], rbx
0x18003fa0d  mov     [rsp+arg_8], rsi
0x18003fa12  push    rdi
0x18003fa13  sub     rsp, 260h
0x18003fa1a  mov     rax, cs:__security_cookie
0x18003fa21  xor     rax, rsp
0x18003fa24  mov     [rsp+268h+var_18], rax
0x18003fa2c  mov     rdi, [rsp+268h+arg_28]
0x18003fa34  mov     rsi, [rsp+268h+lpValue]
0x18003fa3c  mov     [rsp+268h+var_224], 0
0x18003fa44  mov     [rsp+268h+var_228], 4
0x18003fa4c  test    rdi, rdi
0x18003fa4f  jnz     short loc_18003FA79
0x18003fa51  mov     ebx, 80070057h
0x18003fa56  mov     edx, 93h; void *
0x18003fa5b  mov     rcx, [rsp+268h]; this
0x18003fa63  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003fa6a  mov     r9d, ebx; char *
0x18003fa6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fa72  mov     eax, ebx
0x18003fa74  jmp     loc_18003FB34
0x18003fa79  mov     ebx, 200h
0x18003fa7e  lea     rcx, [rsp+268h+SubKey]; void *
0x18003fa83  mov     r8d, ebx; Size
0x18003fa86  xor     edx, edx; Val
0x18003fa88  call    memset_0
0x18003fa8d  mov     r9d, ebx
0x18003fa90  mov     [rsp+268h+pdwType], 0; unsigned int
0x18003fa99  lea     r8, [rsp+268h+SubKey]
0x18003fa9e  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\WindowsUpdate\\UX"
0x18003faa5  lea     rcx, aWindowsupdateu; "WindowsUpdateUXRoot"
0x18003faac  call    cs:__imp_GetPersistedRegistryLocationW
0x18003fab2  test    eax, eax
0x18003fab4  jz      short loc_18003FAC8
0x18003fab6  mov     rcx, [rsp+268h]; this
0x18003fabe  mov     r9d, eax; char *
0x18003fac1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003fac6  jmp     short loc_18003FB34
0x18003fac8  lea     r8, aSettings; "\\Settings"
0x18003facf  mov     edx, 100h; unsigned __int64
0x18003fad4  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x18003fad9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003fade  mov     ebx, eax
0x18003fae0  test    eax, eax
0x18003fae2  jns     short loc_18003FAEE
0x18003fae4  mov     edx, 9Fh
0x18003fae9  jmp     loc_18003FA5B
0x18003faee  lea     rax, [rsp+268h+var_228]
0x18003faf3  mov     r9d, 10h; dwFlags
0x18003faf9  mov     [rsp+268h+pcbData], rax; pcbData
0x18003fafe  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x18003fb03  lea     rax, [rsp+268h+var_224]
0x18003fb08  mov     [rsp+268h+pvData], rdi; pvData
0x18003fb0d  mov     r8, rsi; lpValue
0x18003fb10  mov     [rsp+268h+pdwType], rax; pdwType
0x18003fb15  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003fb1c  call    cs:__imp_RegGetValueW
0x18003fb22  test    eax, eax
0x18003fb24  jz      short loc_18003FB32
0x18003fb26  jle     short loc_18003FB34
0x18003fb28  movzx   eax, ax
0x18003fb2b  or      eax, 80070000h
0x18003fb30  jmp     short loc_18003FB34
0x18003fb32  xor     eax, eax
0x18003fb34  mov     rcx, [rsp+268h+var_18]
0x18003fb3c  xor     rcx, rsp; StackCookie
0x18003fb3f  call    __security_check_cookie
0x18003fb44  lea     r11, [rsp+268h+var_8]
0x18003fb4c  mov     rbx, [r11+10h]
0x18003fb50  mov     rsi, [r11+18h]
0x18003fb54  mov     rsp, r11
0x18003fb57  pop     rdi
0x18003fb58  retn
```
