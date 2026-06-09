# RtlSystemUtil::PrivilegeAcquisition::Restore(void)

- ea: `0x18006d278`
- end: `0x18006d32f`
- name: `?Restore@PrivilegeAcquisition@RtlSystemUtil@@QEAAJXZ`
- size: `183`
- prototype: `__int64 __fastcall(RtlSystemUtil::PrivilegeAcquisition *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006c3bc`

## callees

- `0x18000ea3c`
- `0x18001f5d4`
- `0x1800293a0`
- `0x18006d278`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18006d2bc`
- `ntdll!NtSetInformationThread` at `0x18006d2bc`

## string_xrefs

- `0x18006d2cc`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006d2e6`: `RtlSystemUtil::PrivilegeAcquisition::Restore`
- `0x18006d2f5`: `NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, &hToken, sizeof(hToken))`

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
0x18006d278  push    rbx
0x18006d27a  sub     rsp, 60h
0x18006d27e  mov     rax, cs:__security_cookie
0x18006d285  xor     rax, rsp
0x18006d288  mov     [rsp+68h+var_18], rax
0x18006d28d  cmp     byte ptr [rcx+8], 0
0x18006d291  mov     rbx, rcx
0x18006d294  mov     [rsp+68h+var_20], 0
0x18006d29c  jz      short loc_18006D30D
0x18006d29e  mov     rax, [rcx]
0x18006d2a1  lea     r8, [rsp+68h+ThreadInformation]; ThreadInformation
0x18006d2a6  mov     r9d, 8; ThreadInformationLength
0x18006d2ac  mov     [rsp+68h+ThreadInformation], rax
0x18006d2b1  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18006d2b8  lea     edx, [r9-3]; ThreadInformationClass
0x18006d2bc  call    cs:__imp_NtSetInformationThread
0x18006d2c3  nop     dword ptr [rax+rax+00h]
0x18006d2c8  test    eax, eax
0x18006d2ca  jns     short loc_18006D30D
0x18006d2cc  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006d2d3  mov     [rsp+68h+var_38], 2FEh
0x18006d2dc  mov     [rsp+68h+var_48], rcx
0x18006d2e1  lea     rdx, [rsp+68h+var_48]
0x18006d2e6  lea     rcx, aRtlsystemutilP_1; "RtlSystemUtil::PrivilegeAcquisition::Re"...
0x18006d2ed  mov     r8d, eax
0x18006d2f0  mov     [rsp+68h+var_40], rcx
0x18006d2f5  lea     rcx, aNtsetinformati; "NtSetInformationThread( ( (HANDLE)(LONG"...
0x18006d2fc  mov     [rsp+68h+var_30], rcx
0x18006d301  lea     rcx, [rsp+68h+var_20]
0x18006d306  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006d30b  jmp     short loc_18006D31B
0x18006d30d  mov     rcx, rbx
0x18006d310  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18006d315  xor     eax, eax
0x18006d317  mov     byte ptr [rbx+8], 0
0x18006d31b  mov     rcx, [rsp+68h+var_18]
0x18006d320  xor     rcx, rsp; StackCookie
0x18006d323  call    __security_check_cookie
0x18006d328  add     rsp, 60h
0x18006d32c  pop     rbx
0x18006d32d  retn
```
