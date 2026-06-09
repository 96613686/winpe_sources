# RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)

- ea: `0x140025fd8`
- end: `0x140026065`
- name: `?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001344c`

## callees

- `0x140002310`
- `0x140006b54`
- `0x140025fd8`
- `0x14002606c`

## string_xrefs

- `0x14002600d`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x140026027`: `RtlSystemUtil::PrivilegeAcquisition::Acquire`

## pseudocode

```c
__int64 __fastcall RtlSystemUtil::PrivilegeAcquisition::Acquire(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  _BYTE v3[8]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v4[4]; // [rsp+28h] [rbp-40h] BYREF
  int v5; // [rsp+48h] [rbp-20h] BYREF

  v5 = 0;
  v3[0] = 0;
  result = RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble(a1, a2, v3);
  if ( (int)result >= 0 )
  {
    if ( v3[0] )
    {
      return 0;
    }
    else
    {
      v4[2] = 747;
      v4[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v4[1] = "RtlSystemUtil::PrivilegeAcquisition::Acquire";
      v4[3] = "fAcquired";
      return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
               &v5,
               v4,
               3221225569LL);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140025fd8  sub     rsp, 68h
0x140025fdc  mov     rax, cs:__security_cookie
0x140025fe3  xor     rax, rsp
0x140025fe6  mov     [rsp+68h+var_18], rax
0x140025feb  lea     r8, [rsp+68h+var_48]
0x140025ff0  mov     [rsp+68h+var_20], 0
0x140025ff8  mov     [rsp+68h+var_48], 0
0x140025ffd  call    ?AcquireIfAble@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@PEA_N@Z; RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble(Windows::Vector<long const> const &,bool *)
0x140026002  test    eax, eax
0x140026004  js      short loc_140026053
0x140026006  cmp     [rsp+68h+var_48], 0
0x14002600b  jnz     short loc_140026051
0x14002600d  lea     rax, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140026014  mov     [rsp+68h+var_30], 2EBh
0x14002601d  mov     [rsp+68h+var_40], rax
0x140026022  lea     rdx, [rsp+68h+var_40]
0x140026027  lea     rax, aRtlsystemutilP_0; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x14002602e  mov     r8d, 0C0000061h
0x140026034  mov     [rsp+68h+var_38], rax
0x140026039  lea     rcx, [rsp+68h+var_20]
0x14002603e  lea     rax, aFacquired; "fAcquired"
0x140026045  mov     [rsp+68h+var_28], rax
0x14002604a  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x14002604f  jmp     short loc_140026053
0x140026051  xor     eax, eax
0x140026053  mov     rcx, [rsp+68h+var_18]
0x140026058  xor     rcx, rsp; StackCookie
0x14002605b  call    __security_check_cookie
0x140026060  add     rsp, 68h
0x140026064  retn
```
