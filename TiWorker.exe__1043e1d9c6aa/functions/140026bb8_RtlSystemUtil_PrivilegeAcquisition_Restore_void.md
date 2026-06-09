# RtlSystemUtil::PrivilegeAcquisition::Restore(void)

- ea: `0x140026bb8`
- end: `0x140026c68`
- name: `?Restore@PrivilegeAcquisition@RtlSystemUtil@@QEAAJXZ`
- size: `176`
- prototype: `__int64 __fastcall(RtlSystemUtil::PrivilegeAcquisition *this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140025eec`

## callees

- `0x140002310`
- `0x140006b54`
- `0x14000e66c`
- `0x140026bb8`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x140026bfc`
- `ntdll!NtSetInformationThread` at `0x140026bfc`

## string_xrefs

- `0x140026c06`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x140026c20`: `RtlSystemUtil::PrivilegeAcquisition::Restore`
- `0x140026c2f`: `NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, &hToken, sizeof(hToken))`

## pseudocode

```c
__int64 __fastcall RtlSystemUtil::PrivilegeAcquisition::Restore(RtlSystemUtil::PrivilegeAcquisition *this, void *a2)
{
  bool v2; // zf
  NTSTATUS v4; // eax
  __int64 result; // rax
  _QWORD v6[4]; // [rsp+20h] [rbp-48h] BYREF
  __int64 ThreadInformation; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v8; // [rsp+48h] [rbp-20h] BYREF

  v2 = *((_BYTE *)this + 8) == 0;
  v8 = 0;
  if ( v2
    || (ThreadInformation = *(_QWORD *)this,
        v4 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u),
        v4 >= 0) )
  {
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(
      (Windows::Detail **)this,
      a2);
    result = 0;
    *((_BYTE *)this + 8) = 0;
  }
  else
  {
    v6[2] = 766;
    v6[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v6[1] = "RtlSystemUtil::PrivilegeAcquisition::Restore";
    v6[3] = "NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, &hToken, sizeof(hToken))";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
             &v8,
             (__int64)v6,
             v4);
  }
  return result;
}

```

## disassembly

```asm
0x140026bb8  push    rbx
0x140026bba  sub     rsp, 60h
0x140026bbe  mov     rax, cs:__security_cookie
0x140026bc5  xor     rax, rsp
0x140026bc8  mov     [rsp+68h+var_18], rax
0x140026bcd  cmp     byte ptr [rcx+8], 0
0x140026bd1  mov     rbx, rcx
0x140026bd4  mov     [rsp+68h+var_20], 0
0x140026bdc  jz      short loc_140026C47
0x140026bde  mov     rax, [rcx]
0x140026be1  lea     r8, [rsp+68h+ThreadInformation]; ThreadInformation
0x140026be6  mov     r9d, 8; ThreadInformationLength
0x140026bec  mov     [rsp+68h+ThreadInformation], rax
0x140026bf1  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140026bf8  lea     edx, [r9-3]; ThreadInformationClass
0x140026bfc  call    cs:__imp_NtSetInformationThread
0x140026c02  test    eax, eax
0x140026c04  jns     short loc_140026C47
0x140026c06  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140026c0d  mov     [rsp+68h+var_38], 2FEh
0x140026c16  mov     [rsp+68h+var_48], rcx
0x140026c1b  lea     rdx, [rsp+68h+var_48]
0x140026c20  lea     rcx, aRtlsystemutilP_1; "RtlSystemUtil::PrivilegeAcquisition::Re"...
0x140026c27  mov     r8d, eax
0x140026c2a  mov     [rsp+68h+var_40], rcx
0x140026c2f  lea     rcx, aNtsetinformati; "NtSetInformationThread( ( (HANDLE)(LONG"...
0x140026c36  mov     [rsp+68h+var_30], rcx
0x140026c3b  lea     rcx, [rsp+68h+var_20]
0x140026c40  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140026c45  jmp     short loc_140026C55
0x140026c47  mov     rcx, rbx
0x140026c4a  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x140026c4f  xor     eax, eax
0x140026c51  mov     byte ptr [rbx+8], 0
0x140026c55  mov     rcx, [rsp+68h+var_18]
0x140026c5a  xor     rcx, rsp; StackCookie
0x140026c5d  call    __security_check_cookie
0x140026c62  add     rsp, 60h
0x140026c66  pop     rbx
0x140026c67  retn
```
