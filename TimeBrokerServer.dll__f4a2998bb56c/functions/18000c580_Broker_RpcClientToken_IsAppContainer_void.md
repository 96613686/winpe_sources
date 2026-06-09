# Broker::RpcClientToken::IsAppContainer(void)

- ea: `0x18000c580`
- end: `0x18000c620`
- name: `?IsAppContainer@RpcClientToken@Broker@@QEAA_NXZ`
- size: `160`
- prototype: `bool __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ef50`

## callees

- `0x180003800`
- `0x18000c580`
- `0x18001181c`
- `0x180013978`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c5af`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c5af`

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
0x18000c580  mov     r11, rsp
0x18000c583  sub     rsp, 88h
0x18000c58a  xor     eax, eax
0x18000c58c  mov     [r11+10h], eax
0x18000c590  mov     [r11+8], eax
0x18000c594  lea     rax, [r11+10h]
0x18000c598  mov     [r11-68h], rax
0x18000c59c  mov     r9d, 4; TokenInformationLength
0x18000c5a2  lea     r8, [r11+8]; TokenInformation
0x18000c5a6  mov     edx, 1Dh; TokenInformationClass
0x18000c5ab  mov     rcx, [rcx+8]; TokenHandle
0x18000c5af  call    cs:__imp_GetTokenInformation
0x18000c5b5  test    eax, eax
0x18000c5b7  jz      short loc_18000C5CC
0x18000c5b9  cmp     [rsp+88h+arg_0], 0
0x18000c5c1  setnz   al
0x18000c5c4  add     rsp, 88h
0x18000c5cb  retn
0x18000c5cc  lea     rcx, [rsp+88h+var_58]; this
0x18000c5d1  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000c5d6  nop
0x18000c5d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5de  test    byte ptr [rcx+1Ch], 8
0x18000c5e2  jz      short loc_18000C604
0x18000c5e4  cmp     byte ptr [rcx+19h], 2
0x18000c5e8  jb      short loc_18000C604
0x18000c5ea  mov     edx, 17h
0x18000c5ef  mov     r9d, [rsp+88h+var_38]
0x18000c5f4  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000c5fb  mov     rcx, [rcx+10h]
0x18000c5ff  call    WPP_SF_d
0x18000c604  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18000c609  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000c60e  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000c615  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18000c61a  call    _CxxThrowException_0
```
