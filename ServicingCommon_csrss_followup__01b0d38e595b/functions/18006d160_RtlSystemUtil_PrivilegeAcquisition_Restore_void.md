# RtlSystemUtil::PrivilegeAcquisition::Restore(void)

- ea: `0x18006d160`
- end: `0x18006d217`
- name: `?Restore@PrivilegeAcquisition@RtlSystemUtil@@QEAAJXZ`
- size: `183`
- prototype: `__int64 __fastcall(RtlSystemUtil::PrivilegeAcquisition *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006c2a0`

## callees

- `0x180018df0`
- `0x18001f840`
- `0x18002d2b0`
- `0x18006d160`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18006d1a4`
- `ntdll!NtSetInformationThread` at `0x18006d1a4`

## string_xrefs

- `0x18006d1b4`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006d1dd`: `NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, &hToken, sizeof(hToken))`
- `0x18006d1ce`: `RtlSystemUtil::PrivilegeAcquisition::Restore`

## pseudocode

```c
__int64 __fastcall RtlSystemUtil::PrivilegeAcquisition::Restore(RtlSystemUtil::PrivilegeAcquisition *this)
{
  bool v1; // zf
  NTSTATUS v3; // eax
  __int64 result; // rax
  _QWORD v5[4]; // [rsp+20h] [rbp-48h] BYREF
  __int64 ThreadInformation; // [rsp+40h] [rbp-28h] BYREF
  int v7; // [rsp+48h] [rbp-20h] BYREF

  v1 = *((_BYTE *)this + 8) == 0;
  v7 = 0;
  if ( v1
    || (ThreadInformation = *(_QWORD *)this,
        v3 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u),
        v3 >= 0) )
  {
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(this);
    result = 0;
    *((_BYTE *)this + 8) = 0;
  }
  else
  {
    v5[2] = 766;
    v5[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v5[1] = "RtlSystemUtil::PrivilegeAcquisition::Restore";
    v5[3] = "NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, &hToken, sizeof(hToken))";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v7,
             v5,
             (unsigned int)v3);
  }
  return result;
}

```

## disassembly

```asm
0x18006d160  push    rbx
0x18006d162  sub     rsp, 60h
0x18006d166  mov     rax, cs:__security_cookie
0x18006d16d  xor     rax, rsp
0x18006d170  mov     [rsp+68h+var_18], rax
0x18006d175  cmp     byte ptr [rcx+8], 0
0x18006d179  mov     rbx, rcx
0x18006d17c  mov     [rsp+68h+var_20], 0
0x18006d184  jz      short loc_18006D1F5
0x18006d186  mov     rax, [rcx]
0x18006d189  lea     r8, [rsp+68h+ThreadInformation]; ThreadInformation
0x18006d18e  mov     r9d, 8; ThreadInformationLength
0x18006d194  mov     [rsp+68h+ThreadInformation], rax
0x18006d199  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18006d1a0  lea     edx, [r9-3]; ThreadInformationClass
0x18006d1a4  call    cs:__imp_NtSetInformationThread
0x18006d1ab  nop     dword ptr [rax+rax+00h]
0x18006d1b0  test    eax, eax
0x18006d1b2  jns     short loc_18006D1F5
0x18006d1b4  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006d1bb  mov     [rsp+68h+var_38], 2FEh
0x18006d1c4  mov     [rsp+68h+var_48], rcx
0x18006d1c9  lea     rdx, [rsp+68h+var_48]
0x18006d1ce  lea     rcx, aRtlsystemutilP_1; "RtlSystemUtil::PrivilegeAcquisition::Re"...
0x18006d1d5  mov     r8d, eax
0x18006d1d8  mov     [rsp+68h+var_40], rcx
0x18006d1dd  lea     rcx, aNtsetinformati; "NtSetInformationThread( ( (HANDLE)(LONG"...
0x18006d1e4  mov     [rsp+68h+var_30], rcx
0x18006d1e9  lea     rcx, [rsp+68h+var_20]
0x18006d1ee  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006d1f3  jmp     short loc_18006D203
0x18006d1f5  mov     rcx, rbx
0x18006d1f8  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18006d1fd  xor     eax, eax
0x18006d1ff  mov     byte ptr [rbx+8], 0
0x18006d203  mov     rcx, [rsp+68h+var_18]
0x18006d208  xor     rcx, rsp; StackCookie
0x18006d20b  call    __security_check_cookie
0x18006d210  add     rsp, 60h
0x18006d214  pop     rbx
0x18006d215  retn
```
