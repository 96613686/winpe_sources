# Broker::IsAppContainer(void *)

- ea: `0x180019fa8`
- end: `0x18001a04c`
- name: `?IsAppContainer@Broker@@YA_NPEAX@Z`
- size: `164`
- prototype: `bool __fastcall(Broker *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016a30`

## callees

- `0x180009e94`
- `0x180014a40`
- `0x1800165da`
- `0x180019fa8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180019fd8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180019fd8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Broker::IsAppContainer(Broker *this, void *a2)
{
  _BYTE v3[32]; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v4; // [rsp+50h] [rbp-38h]
  _BYTE pExceptionObject[48]; // [rsp+58h] [rbp-30h] BYREF
  int v6; // [rsp+98h] [rbp+10h] BYREF
  DWORD v7; // [rsp+A0h] [rbp+18h] BYREF

  v7 = 0;
  v6 = 0;
  if ( !GetTokenInformation(this, TokenIsAppContainer, &v6, 4u, &v7) )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)v3);
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_a9458e0debc7300a47110d600cc51ede_Traceguids, v4);
    Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
    throw (Broker::Win32Error *)pExceptionObject;
  }
  return v6 != 0;
}

```

## disassembly

```asm
0x180019fa8  mov     r11, rsp
0x180019fab  sub     rsp, 88h
0x180019fb2  mov     dword ptr [r11+18h], 0
0x180019fba  mov     dword ptr [r11+10h], 0
0x180019fc2  lea     rax, [r11+18h]
0x180019fc6  mov     [r11-68h], rax
0x180019fca  mov     r9d, 4; TokenInformationLength
0x180019fd0  lea     r8, [r11+10h]; TokenInformation
0x180019fd4  lea     edx, [r9+19h]; TokenInformationClass
0x180019fd8  call    cs:__imp_GetTokenInformation
0x180019fde  test    eax, eax
0x180019fe0  jnz     short loc_18001A039
0x180019fe2  lea     rcx, [rsp+88h+var_58]; this
0x180019fe7  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180019fec  nop
0x180019fed  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ff4  test    dword ptr [rcx+1Ch], 400h
0x180019ffb  jz      short loc_18001A01D
0x180019ffd  cmp     byte ptr [rcx+19h], 2
0x18001a001  jb      short loc_18001A01D
0x18001a003  mov     edx, 0Dh
0x18001a008  mov     r9d, [rsp+88h+var_38]
0x18001a00d  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x18001a014  mov     rcx, [rcx+10h]
0x18001a018  call    WPP_SF_d
0x18001a01d  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18001a022  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18001a027  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001a02e  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18001a033  call    _CxxThrowException_0
0x18001a039  cmp     [rsp+88h+arg_8], 0
0x18001a041  setnz   al
0x18001a044  add     rsp, 88h
0x18001a04b  retn
```
