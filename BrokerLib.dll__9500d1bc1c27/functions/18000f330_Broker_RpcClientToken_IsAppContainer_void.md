# Broker::RpcClientToken::IsAppContainer(void)

- ea: `0x18000f330`
- end: `0x18000f3d5`
- name: `?IsAppContainer@RpcClientToken@Broker@@QEAA_NXZ`
- size: `165`
- prototype: `bool __fastcall(Broker::RpcClientToken *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001ab8c`

## callees

- `0x180009e94`
- `0x18000f330`
- `0x180014a40`
- `0x1800165da`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f364`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f364`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v3);
    Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
    throw (Broker::Win32Error *)pExceptionObject;
  }
  return v5 != 0;
}

```

## disassembly

```asm
0x18000f330  mov     r11, rsp
0x18000f333  sub     rsp, 88h
0x18000f33a  mov     dword ptr [r11+10h], 0
0x18000f342  mov     dword ptr [r11+8], 0
0x18000f34a  lea     rax, [r11+10h]
0x18000f34e  mov     [r11-68h], rax
0x18000f352  mov     r9d, 4; TokenInformationLength
0x18000f358  lea     r8, [r11+8]; TokenInformation
0x18000f35c  lea     edx, [r9+19h]; TokenInformationClass
0x18000f360  mov     rcx, [rcx+8]; TokenHandle
0x18000f364  call    cs:__imp_GetTokenInformation
0x18000f36a  test    eax, eax
0x18000f36c  jz      short loc_18000F381
0x18000f36e  cmp     [rsp+88h+arg_0], 0
0x18000f376  setnz   al
0x18000f379  add     rsp, 88h
0x18000f380  retn
0x18000f381  lea     rcx, [rsp+88h+var_58]; this
0x18000f386  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000f38b  nop
0x18000f38c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f393  test    byte ptr [rcx+1Ch], 8
0x18000f397  jz      short loc_18000F3B9
0x18000f399  cmp     byte ptr [rcx+19h], 2
0x18000f39d  jb      short loc_18000F3B9
0x18000f39f  mov     edx, 17h
0x18000f3a4  mov     r9d, [rsp+88h+var_38]
0x18000f3a9  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000f3b0  mov     rcx, [rcx+10h]
0x18000f3b4  call    WPP_SF_d
0x18000f3b9  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18000f3be  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000f3c3  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000f3ca  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18000f3cf  call    _CxxThrowException_0
```
