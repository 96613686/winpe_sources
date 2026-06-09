# UpdateLastDetectedTime

- ea: `0x140084e04`
- end: `0x140084f55`
- name: `UpdateLastDetectedTime`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140082be8`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140074f18`
- `0x14007500c`
- `0x140084e04`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140084f21`
- `ADVAPI32!RegCloseKey` at `0x140084f21`
- `KERNEL32!SetLastError` at `0x140084ed0`
- `KERNEL32!SetLastError` at `0x140084ed0`

## string_xrefs

- `0x140084e66`: `Software\Microsoft\Fax\Devices Cache`

## pseudocode

```c
__int64 __fastcall UpdateLastDetectedTime(int a1, __int64 a2)
{
  int v3; // eax
  DWORD v4; // ebx
  unsigned int v6; // ebx
  HKEY v7; // rax
  HKEY v8; // rdi
  int v9; // [rsp+20h] [rbp-248h]
  BYTE v10[16]; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 v11[264]; // [rsp+40h] [rbp-228h] BYREF

  *(_QWORD *)v10 = a2;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v9 = a1;
  v3 = StringCchPrintfW(v11, 0x104u, L"%s\\%08lx", L"Software\\Microsoft\\Fax\\Devices Cache", v9);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v6 = 0;
    v7 = OpenRegistryKey(HKEY_LOCAL_MACHINE, v11, 0, 0x20006u);
    v8 = v7;
    if ( v7 )
    {
      v6 = SetRegistryBinary(v7, L"LastDetected", v10, 8u);
      RegCloseKey(v8);
    }
    return v6;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        169,
        &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
        (unsigned int)v3);
    }
    if ( (v4 & 0x1FFF0000) == 0x70000 )
      v4 = (unsigned __int16)v4;
    SetLastError(v4);
    return 0;
  }
}

```

## disassembly

```asm
0x140084e04  mov     [rsp+arg_10], rbx
0x140084e09  mov     [rsp+arg_18], rsi
0x140084e0e  push    rdi
0x140084e0f  sub     rsp, 260h
0x140084e16  mov     rax, cs:__security_cookie
0x140084e1d  xor     rax, rsp
0x140084e20  mov     [rsp+268h+var_18], rax
0x140084e28  mov     ebx, ecx
0x140084e2a  mov     qword ptr [rsp+268h+var_238], rdx
0x140084e2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140084e36  lea     rsi, WPP_GLOBAL_Control
0x140084e3d  mov     dil, 2
0x140084e40  cmp     rcx, rsi
0x140084e43  jz      short loc_140084E66
0x140084e45  test    [rcx+1Ch], dil
0x140084e49  jz      short loc_140084E66
0x140084e4b  cmp     byte ptr [rcx+19h], 5
0x140084e4f  jb      short loc_140084E66
0x140084e51  mov     rcx, [rcx+10h]
0x140084e55  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140084e5c  mov     edx, 0A8h
0x140084e61  call    WPP_SF_
0x140084e66  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x140084e6d  mov     [rsp+268h+var_248], ebx
0x140084e71  lea     r8, aS08lx; "%s\\%08lx"
0x140084e78  mov     edx, 104h; unsigned __int64
0x140084e7d  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x140084e82  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140084e87  mov     ebx, eax
0x140084e89  test    eax, eax
0x140084e8b  jns     short loc_140084EE0
0x140084e8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140084e94  cmp     rcx, rsi
0x140084e97  jz      short loc_140084EBD
0x140084e99  test    [rcx+1Ch], dil
0x140084e9d  jz      short loc_140084EBD
0x140084e9f  cmp     [rcx+19h], dil
0x140084ea3  jb      short loc_140084EBD
0x140084ea5  mov     rcx, [rcx+10h]
0x140084ea9  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140084eb0  mov     edx, 0A9h
0x140084eb5  mov     r9d, eax
0x140084eb8  call    WPP_SF_d
0x140084ebd  mov     eax, ebx
0x140084ebf  and     eax, 1FFF0000h
0x140084ec4  cmp     eax, 70000h
0x140084ec9  jnz     short loc_140084ECE
0x140084ecb  movzx   ebx, bx
0x140084ece  mov     ecx, ebx; dwErrCode
0x140084ed0  call    cs:__imp_SetLastError
0x140084ed7  nop     dword ptr [rax+rax+00h]
0x140084edc  xor     eax, eax
0x140084ede  jmp     short loc_140084F2F
0x140084ee0  mov     r9d, 20006h
0x140084ee6  lea     rdx, [rsp+268h+var_228]
0x140084eeb  xor     r8d, r8d
0x140084eee  mov     rcx, 0FFFFFFFF80000002h
0x140084ef5  xor     ebx, ebx
0x140084ef7  call    OpenRegistryKey
0x140084efc  mov     rdi, rax
0x140084eff  test    rax, rax
0x140084f02  jz      short loc_140084F2D
0x140084f04  lea     r9d, [rbx+8]
0x140084f08  mov     rcx, rax
0x140084f0b  lea     r8, [rsp+268h+var_238]
0x140084f10  lea     rdx, aLastdetected; "LastDetected"
0x140084f17  call    SetRegistryBinary
0x140084f1c  mov     rcx, rdi; hKey
0x140084f1f  mov     ebx, eax
0x140084f21  call    cs:__imp_RegCloseKey
0x140084f28  nop     dword ptr [rax+rax+00h]
0x140084f2d  mov     eax, ebx
0x140084f2f  mov     rcx, [rsp+268h+var_18]
0x140084f37  xor     rcx, rsp; StackCookie
0x140084f3a  call    __security_check_cookie
0x140084f3f  lea     r11, [rsp+268h+var_8]
0x140084f47  mov     rbx, [r11+20h]
0x140084f4b  mov     rsi, [r11+28h]
0x140084f4f  mov     rsp, r11
0x140084f52  pop     rdi
0x140084f53  retn
```
