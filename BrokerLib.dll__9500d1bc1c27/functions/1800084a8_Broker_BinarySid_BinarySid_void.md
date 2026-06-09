# Broker::BinarySid::BinarySid(void *)

- ea: `0x1800084a8`
- end: `0x18000854c`
- name: `??0BinarySid@Broker@@QEAA@PEAX@Z`
- size: `164`
- prototype: `__int64 __fastcall(LPWSTR *StringSid, PSID Sid)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006540`

## callees

- `0x1800084a8`
- `0x180009e94`
- `0x1800139f8`
- `0x180014a40`
- `0x1800165da`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800084c1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800084c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPWSTR *__fastcall Broker::BinarySid::BinarySid(LPWSTR *StringSid, PSID Sid)
{
  _BYTE v4[24]; // [rsp+20h] [rbp-58h] BYREF
  int v5; // [rsp+38h] [rbp-40h]
  unsigned int v6; // [rsp+40h] [rbp-38h]
  _QWORD pExceptionObject[3]; // [rsp+48h] [rbp-30h] BYREF
  int v8; // [rsp+60h] [rbp-18h]
  unsigned int v9; // [rsp+68h] [rbp-10h]

  *StringSid = 0;
  if ( !ConvertSidToStringSidW(Sid, StringSid) )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)v4);
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_a9458e0debc7300a47110d600cc51ede_Traceguids, v6);
    std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)v4);
    v8 = v5;
    pExceptionObject[0] = &Broker::Win32Error::`vftable';
    v9 = v6;
    throw (Broker::Win32Error *)pExceptionObject;
  }
  return StringSid;
}

```

## disassembly

```asm
0x1800084a8  push    rbx
0x1800084aa  sub     rsp, 70h
0x1800084ae  mov     rax, rdx
0x1800084b1  mov     rbx, rcx
0x1800084b4  mov     qword ptr [rcx], 0
0x1800084bb  mov     rdx, rcx; StringSid
0x1800084be  mov     rcx, rax; Sid
0x1800084c1  call    cs:__imp_ConvertSidToStringSidW
0x1800084c7  test    eax, eax
0x1800084c9  jz      short loc_1800084D4
0x1800084cb  mov     rax, rbx
0x1800084ce  add     rsp, 70h
0x1800084d2  pop     rbx
0x1800084d3  retn
0x1800084d4  lea     rcx, [rsp+78h+var_58]; this
0x1800084d9  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x1800084de  nop
0x1800084df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084e6  test    dword ptr [rcx+1Ch], 400h
0x1800084ed  jz      short loc_18000850F
0x1800084ef  cmp     byte ptr [rcx+19h], 2
0x1800084f3  jb      short loc_18000850F
0x1800084f5  mov     edx, 0Ch
0x1800084fa  mov     r9d, [rsp+78h+var_38]
0x1800084ff  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x180008506  mov     rcx, [rcx+10h]
0x18000850a  call    WPP_SF_d
0x18000850f  lea     rdx, [rsp+78h+var_58]; struct std::exception *
0x180008514  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180008519  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x18000851e  mov     eax, [rsp+78h+var_40]
0x180008522  mov     [rsp+78h+var_18], eax
0x180008526  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000852d  mov     [rsp+78h+pExceptionObject], rax
0x180008532  mov     eax, [rsp+78h+var_38]
0x180008536  mov     [rsp+78h+var_10], eax
0x18000853a  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180008541  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180008546  call    _CxxThrowException_0
```
