# RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)

- ea: `0x180010ea4`
- end: `0x180010fda`
- name: `??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ`
- size: `310`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `15`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005ce4`
- `0x18000b344`
- `0x1800177f8`
- `0x18001a120`
- `0x18001aff0`
- `0x18001b8f0`
- `0x18001bd30`
- `0x18001c520`
- `0x180020778`
- `0x1800326d8`
- `0x1800328e5`
- `0x180032a02`
- `0x180032a65`
- `0x180032a9b`
- `0x180032bf4`

## callees

- `0x180003870`
- `0x180008140`
- `0x18000fafc`
- `0x18000fc10`
- `0x180010ea4`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x180010ef6`
- `ntdll!NtSetInformationThread` at `0x180010ef6`
- `ntdll!NtClose` at `0x180010f13`
- `ntdll!NtClose` at `0x180010f43`
- `ntdll!NtClose` at `0x180010f13`
- `ntdll!NtClose` at `0x180010f43`

## string_xrefs

- `0x180010f8a`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180010f95`: `RtlSystemUtil::PrivilegeAcquisition::Restore`
- `0x180010fa8`: `NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, &hToken, sizeof(hToken))`

## pseudocode

```c
void __fastcall RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(HANDLE *this)
{
  int v2; // eax
  NTSTATUS v3; // edi
  int v4; // eax
  int NtStatus; // eax
  _QWORD v6[5]; // [rsp+20h] [rbp-40h] BYREF
  HANDLE ThreadInformation; // [rsp+48h] [rbp-18h] BYREF
  NTSTATUS v8; // [rsp+50h] [rbp-10h] BYREF

  v6[4] = -2;
  v2 = 0;
  v8 = 0;
  if ( *((_BYTE *)this + 8) )
  {
    ThreadInformation = *this;
    v3 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    if ( v3 < 0 )
    {
      v6[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v6[1] = "RtlSystemUtil::PrivilegeAcquisition::Restore";
      v6[2] = 766;
      v6[3] = "NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, &hToken, sizeof(hToken))";
      RtlReportErrorOrigination(v6, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v3);
      v8 = v3;
      NtStatus = Windows::ErrorHandling::Rtl::CBaseNtStatusCarryingFrame<Windows::ErrorHandling::Rtl::CVoidRaiseFrame,void>::GetNtStatus(&v8);
      INTERNAL_ERROR_ACTION(NtStatus);
    }
    if ( (char *)*this - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(*this) < 0 )
        __fastfail(7u);
      *this = 0;
    }
    *((_BYTE *)this + 8) = 0;
    v2 = v8;
  }
  if ( v2 < 0 )
  {
    v4 = Windows::ErrorHandling::Rtl::CBaseNtStatusCarryingFrame<Windows::ErrorHandling::Rtl::CVoidRaiseFrame,void>::GetNtStatus(&v8);
    INTERNAL_ERROR_ACTION(v4);
  }
  if ( (char *)*this - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( NtClose(*this) < 0 )
      __fastfail(7u);
    *this = 0;
  }
}

```

## disassembly

```asm
0x180010ea4  mov     rax, rsp
0x180010ea7  push    rbp
0x180010ea8  mov     rbp, rsp
0x180010eab  sub     rsp, 60h
0x180010eaf  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x180010eb7  mov     [rax+10h], rbx
0x180010ebb  mov     [rax+18h], rdi
0x180010ebf  mov     rax, cs:__security_cookie
0x180010ec6  xor     rax, rsp
0x180010ec9  mov     [rbp+var_8], rax
0x180010ecd  mov     rbx, rcx
0x180010ed0  xor     eax, eax
0x180010ed2  mov     [rbp+var_10], eax
0x180010ed5  cmp     [rcx+8], al
0x180010ed8  jz      short loc_180010F32
0x180010eda  mov     rax, [rcx]
0x180010edd  mov     [rbp+ThreadInformation], rax
0x180010ee1  mov     r9d, 8; ThreadInformationLength
0x180010ee7  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x180010eeb  lea     edx, [r9-3]; ThreadInformationClass
0x180010eef  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180010ef6  call    cs:__imp_NtSetInformationThread
0x180010efc  mov     edi, eax
0x180010efe  test    eax, eax
0x180010f00  js      loc_180010F8A
0x180010f06  mov     rcx, [rbx]; Handle
0x180010f09  lea     rax, [rcx-1]
0x180010f0d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010f11  ja      short loc_180010F2B
0x180010f13  call    cs:__imp_NtClose
0x180010f19  test    eax, eax
0x180010f1b  jns     short loc_180010F24
0x180010f1d  mov     ecx, 7
0x180010f22  int     29h; Win8: RtlFailFast(ecx)
0x180010f24  mov     qword ptr [rbx], 0
0x180010f2b  mov     byte ptr [rbx+8], 0
0x180010f2f  mov     eax, [rbp+var_10]
0x180010f32  test    eax, eax
0x180010f34  js      short loc_180010F79
0x180010f36  mov     rcx, [rbx]; Handle
0x180010f39  lea     rax, [rcx-1]
0x180010f3d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010f41  ja      short loc_180010F5B
0x180010f43  call    cs:__imp_NtClose
0x180010f49  test    eax, eax
0x180010f4b  jns     short loc_180010F54
0x180010f4d  mov     ecx, 7
0x180010f52  int     29h; Win8: RtlFailFast(ecx)
0x180010f54  mov     qword ptr [rbx], 0
0x180010f5b  mov     rcx, [rbp+var_8]
0x180010f5f  xor     rcx, rsp; StackCookie
0x180010f62  call    __security_check_cookie
0x180010f67  lea     r11, [rsp+60h+var_s0]
0x180010f6c  mov     rbx, [r11+18h]
0x180010f70  mov     rdi, [r11+20h]
0x180010f74  mov     rsp, r11
0x180010f77  pop     rbp
0x180010f78  retn
0x180010f79  lea     rcx, [rbp+var_10]
0x180010f7d  call    ?GetNtStatus@?$CBaseNtStatusCarryingFrame@UCVoidRaiseFrame@Rtl@ErrorHandling@Windows@@X@Rtl@ErrorHandling@Windows@@QEBAJXZ; Windows::ErrorHandling::Rtl::CBaseNtStatusCarryingFrame<Windows::ErrorHandling::Rtl::CVoidRaiseFrame,void>::GetNtStatus(void)
0x180010f82  mov     ecx, eax; int
0x180010f84  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x180010f8a  lea     rax, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180010f91  mov     [rbp+var_40], rax
0x180010f95  lea     rax, aRtlsystemutilP_1; "RtlSystemUtil::PrivilegeAcquisition::Re"...
0x180010f9c  mov     [rbp+var_38], rax
0x180010fa0  mov     [rbp+var_30], 2FEh
0x180010fa8  lea     rax, aNtsetinformati_0; "NtSetInformationThread( ( (HANDLE)(LONG"...
0x180010faf  mov     [rbp+var_28], rax
0x180010fb3  mov     r8d, edi
0x180010fb6  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180010fbd  lea     rcx, [rbp+var_40]
0x180010fc1  call    RtlReportErrorOrigination
0x180010fc6  mov     [rbp+var_10], edi
0x180010fc9  lea     rcx, [rbp+var_10]
0x180010fcd  call    ?GetNtStatus@?$CBaseNtStatusCarryingFrame@UCVoidRaiseFrame@Rtl@ErrorHandling@Windows@@X@Rtl@ErrorHandling@Windows@@QEBAJXZ; Windows::ErrorHandling::Rtl::CBaseNtStatusCarryingFrame<Windows::ErrorHandling::Rtl::CVoidRaiseFrame,void>::GetNtStatus(void)
0x180010fd2  mov     ecx, eax; int
0x180010fd4  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
