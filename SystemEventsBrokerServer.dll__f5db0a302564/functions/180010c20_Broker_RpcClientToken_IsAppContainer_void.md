# Broker::RpcClientToken::IsAppContainer(void)

- ea: `0x180010c20`
- end: `0x180010cc5`
- name: `?IsAppContainer@RpcClientToken@Broker@@QEAA_NXZ`
- size: `165`
- prototype: `bool __fastcall(HANDLE *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001b78`
- `0x180010560`

## callees

- `0x1800030e0`
- `0x180010c20`
- `0x18001732c`
- `0x18001d9ac`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010c54`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010c54`

## pseudocode

```c
bool __fastcall Broker::RpcClientToken::IsAppContainer(HANDLE *this)
{
  _BYTE v2[32]; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v3; // [rsp+50h] [rbp-38h]
  _BYTE pExceptionObject[48]; // [rsp+58h] [rbp-30h] BYREF
  int v5; // [rsp+90h] [rbp+8h] BYREF
  DWORD v6; // [rsp+98h] [rbp+10h] BYREF

  v6 = 0;
  v5 = 0;
  if ( !GetTokenInformation(this[1], TokenIsAppContainer, &v5, 4u, &v6) )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)v2);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v3);
    Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
    throw (Broker::Win32Error *)pExceptionObject;
  }
  return v5 != 0;
}

```

## disassembly

```asm
0x180010c20  mov     r11, rsp
0x180010c23  sub     rsp, 88h
0x180010c2a  mov     dword ptr [r11+10h], 0
0x180010c32  mov     dword ptr [r11+8], 0
0x180010c3a  lea     rax, [r11+10h]
0x180010c3e  mov     [r11-68h], rax
0x180010c42  mov     r9d, 4; TokenInformationLength
0x180010c48  lea     r8, [r11+8]; TokenInformation
0x180010c4c  lea     edx, [r9+19h]; TokenInformationClass
0x180010c50  mov     rcx, [rcx+8]; TokenHandle
0x180010c54  call    cs:__imp_GetTokenInformation
0x180010c5a  test    eax, eax
0x180010c5c  jnz     short loc_180010CB2
0x180010c5e  lea     rcx, [rsp+88h+var_58]; this
0x180010c63  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180010c68  nop
0x180010c69  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c70  test    byte ptr [rcx+1Ch], 8
0x180010c74  jz      short loc_180010C96
0x180010c76  cmp     byte ptr [rcx+19h], 2
0x180010c7a  jb      short loc_180010C96
0x180010c7c  mov     edx, 17h
0x180010c81  mov     r9d, [rsp+88h+var_38]
0x180010c86  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180010c8d  mov     rcx, [rcx+10h]
0x180010c91  call    WPP_SF_d
0x180010c96  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180010c9b  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180010ca0  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180010ca7  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180010cac  call    _CxxThrowException_0
0x180010cb2  cmp     [rsp+88h+arg_0], 0
0x180010cba  setnz   al
0x180010cbd  add     rsp, 88h
0x180010cc4  retn
```
