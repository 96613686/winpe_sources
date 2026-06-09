# Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)

- ea: `0x180115e5c`
- end: `0x18011609e`
- name: `?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `578`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180116224`
- `0x180225b38`
- `0x180242010`
- `0x18027eecc`
- `0x18027f0d4`
- `0x18027f134`
- `0x18027f778`
- `0x18027fc04`

## callees

- `0x1800aa134`
- `0x1800aa1a4`
- `0x1800eb920`
- `0x1800ef360`
- `0x180115e5c`
- `0x1802cf7cc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180115f28`
- `ntdll!RtlAllocateHeap` at `0x180116011`
- `ntdll!RtlAllocateHeap` at `0x180115f28`
- `ntdll!RtlAllocateHeap` at `0x180116011`
- `ntdll!RtlMakeSelfRelativeSD` at `0x180115fb2`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18011604a`
- `ntdll!RtlMakeSelfRelativeSD` at `0x180115fb2`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18011604a`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x180115ea8`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x180115ea8`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180115f08`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180115f08`

## string_xrefs

- `0x180115eb8`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180115f4b`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180115fd4`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18011605e`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180115ecb`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x180115f5e`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x180115fe7`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x180116071`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x180116030`: `m_pSD = ::RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, cbSecurityDescriptor)`
- `0x180115f44`: `m_pSD = RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, Size)`
- `0x180115ed6`: `RtlGetControlSecurityDescriptor(pTempSd, &Control, &Revision)`
- `0x18011607c`: `RtlMakeSelfRelativeSD( pTempSd, m_pSD, &cbSecurityDescriptor)`

## pseudocode

```c
__int64 __fastcall Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_QWORD *a1, void *a2)
{
  bool v2; // zf
  NTSTATUS ControlSecurityDescriptor; // eax
  const char *v6; // rcx
  SIZE_T v8; // rsi
  PVOID v9; // rax
  const char *v10; // rax
  PVOID Heap; // rax
  const char *v12; // [rsp+20h] [rbp-40h] BYREF
  const char *v13; // [rsp+28h] [rbp-38h]
  __int64 v14; // [rsp+30h] [rbp-30h]
  const char *v15; // [rsp+38h] [rbp-28h]
  WORD Control[2]; // [rsp+40h] [rbp-20h] BYREF
  int v17; // [rsp+44h] [rbp-1Ch] BYREF
  ULONG BufferLength; // [rsp+48h] [rbp-18h] BYREF
  ULONG Revision; // [rsp+4Ch] [rbp-14h] BYREF

  v2 = *a1 == 0;
  v17 = 0;
  if ( !v2 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    __debugbreak();
  }
  Revision = 0;
  Control[0] = 0;
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(a2, Control, &Revision);
  if ( ControlSecurityDescriptor < 0 )
  {
    v14 = 821;
    v12 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v13 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
    v6 = "RtlGetControlSecurityDescriptor(pTempSd, &Control, &Revision)";
LABEL_4:
    v15 = v6;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v17,
             &v12,
             (unsigned int)ControlSecurityDescriptor);
  }
  if ( (Control[0] & 0x8000u) == 0 )
  {
    BufferLength = 0;
    ControlSecurityDescriptor = RtlMakeSelfRelativeSD(a2, 0, &BufferLength);
    if ( ControlSecurityDescriptor != -2147483643 && ControlSecurityDescriptor != -1073741789 )
    {
      if ( ControlSecurityDescriptor >= 0 )
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x18011609DLL);
      }
      v14 = 841;
      v12 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v13 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
      v6 = "((TmpStatus == ((NTSTATUS)0x80000005L)) || (TmpStatus == ((NTSTATUS)0xC0000023L)))";
      goto LABEL_4;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, BufferLength);
    *a1 = Heap;
    if ( !Heap )
    {
      v14 = 843;
      v10 = "m_pSD = ::RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->"
            "ProcessHeap), 0, cbSecurityDescriptor)";
      goto LABEL_8;
    }
    a1[1] = BufferLength;
    ControlSecurityDescriptor = RtlMakeSelfRelativeSD(a2, Heap, &BufferLength);
    if ( ControlSecurityDescriptor < 0 )
    {
      v14 = 850;
      v12 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v13 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
      v6 = "RtlMakeSelfRelativeSD( pTempSd, m_pSD, &cbSecurityDescriptor)";
      goto LABEL_4;
    }
  }
  else
  {
    v8 = RtlLengthSecurityDescriptor(a2);
    v9 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
    *a1 = v9;
    if ( !v9 )
    {
      v14 = 827;
      v10 = "m_pSD = RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->Pr"
            "ocessHeap), 0, Size)";
LABEL_8:
      v15 = v10;
      v12 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v13 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
               &v17,
               &v12);
    }
    memcpy_0(v9, a2, v8);
    a1[1] = v8;
  }
  return 0;
}

```

## disassembly

```asm
0x180115e5c  mov     [rsp-18h+arg_10], rbx
0x180115e61  push    rbp
0x180115e62  push    rsi
0x180115e63  push    rdi
0x180115e64  mov     rbp, rsp
0x180115e67  sub     rsp, 60h
0x180115e6b  mov     rax, cs:__security_cookie
0x180115e72  xor     rax, rsp
0x180115e75  mov     [rbp+var_10], rax
0x180115e79  cmp     qword ptr [rcx], 0
0x180115e7d  mov     rbx, rdx
0x180115e80  mov     rdi, rcx
0x180115e83  mov     [rbp+var_1C], 0
0x180115e8a  jnz     loc_180116088
0x180115e90  xor     eax, eax
0x180115e92  mov     [rbp+Revision], 0
0x180115e99  lea     r8, [rbp+Revision]; Revision
0x180115e9d  mov     [rbp+Control], ax
0x180115ea1  lea     rdx, [rbp+Control]; Control
0x180115ea5  mov     rcx, rbx; SecurityDescriptor
0x180115ea8  call    cs:__imp_RtlGetControlSecurityDescriptor
0x180115eaf  nop     dword ptr [rax+rax+00h]
0x180115eb4  test    eax, eax
0x180115eb6  jns     short loc_180115EF6
0x180115eb8  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180115ebf  mov     [rbp+var_30], 335h
0x180115ec7  mov     [rbp+var_40], rcx
0x180115ecb  lea     rcx, aWindowsAutoStr_2; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x180115ed2  mov     [rbp+var_38], rcx
0x180115ed6  lea     rcx, aRtlgetcontrols_3; "RtlGetControlSecurityDescriptor(pTempSd"...
0x180115edd  mov     [rbp+var_28], rcx
0x180115ee1  lea     rdx, [rbp+var_40]
0x180115ee5  lea     rcx, [rbp+var_1C]
0x180115ee9  mov     r8d, eax
0x180115eec  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180115ef1  jmp     loc_180115F88
0x180115ef6  mov     eax, 8000h
0x180115efb  mov     rcx, rbx; AbsoluteSD
0x180115efe  test    [rbp+Control], ax
0x180115f02  jz      loc_180115FA5
0x180115f08  call    cs:__imp_RtlLengthSecurityDescriptor
0x180115f0f  nop     dword ptr [rax+rax+00h]
0x180115f14  mov     rcx, gs:60h
0x180115f1d  xor     edx, edx; Flags
0x180115f1f  mov     r8d, eax; Size
0x180115f22  mov     esi, eax
0x180115f24  mov     rcx, [rcx+30h]; HeapHandle
0x180115f28  call    cs:__imp_RtlAllocateHeap
0x180115f2f  nop     dword ptr [rax+rax+00h]
0x180115f34  mov     [rdi], rax
0x180115f37  test    rax, rax
0x180115f3a  jnz     short loc_180115F74
0x180115f3c  mov     [rbp+var_30], 33Bh
0x180115f44  lea     rax, aMPsdRtlallocat_0; "m_pSD = RtlAllocateHeap((((PPEB)__readg"...
0x180115f4b  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180115f52  mov     [rbp+var_28], rax
0x180115f56  mov     [rbp+var_40], rcx
0x180115f5a  lea     rdx, [rbp+var_40]
0x180115f5e  lea     rcx, aWindowsAutoStr_2; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x180115f65  mov     [rbp+var_38], rcx
0x180115f69  lea     rcx, [rbp+var_1C]
0x180115f6d  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180115f72  jmp     short loc_180115F88
0x180115f74  mov     r8, rsi; Size
0x180115f77  mov     rdx, rbx; Src
0x180115f7a  mov     rcx, rax; void *
0x180115f7d  call    memcpy_0
0x180115f82  mov     [rdi+8], rsi
0x180115f86  xor     eax, eax
0x180115f88  mov     rcx, [rbp+var_10]
0x180115f8c  xor     rcx, rsp; StackCookie
0x180115f8f  call    __security_check_cookie
0x180115f94  mov     rbx, [rsp+60h+arg_10]
0x180115f9c  add     rsp, 60h
0x180115fa0  pop     rdi
0x180115fa1  pop     rsi
0x180115fa2  pop     rbp
0x180115fa3  retn
0x180115fa5  lea     r8, [rbp+BufferLength]; BufferLength
0x180115fa9  mov     [rbp+BufferLength], 0
0x180115fb0  xor     edx, edx; SelfRelativeSD
0x180115fb2  call    cs:__imp_RtlMakeSelfRelativeSD
0x180115fb9  nop     dword ptr [rax+rax+00h]
0x180115fbe  cmp     eax, 80000005h
0x180115fc3  jz      short loc_180115FFE
0x180115fc5  cmp     eax, 0C0000023h
0x180115fca  jz      short loc_180115FFE
0x180115fcc  test    eax, eax
0x180115fce  jns     loc_180116093
0x180115fd4  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180115fdb  mov     [rbp+var_30], 349h
0x180115fe3  mov     [rbp+var_40], rcx
0x180115fe7  lea     rcx, aWindowsAutoStr_2; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x180115fee  mov     [rbp+var_38], rcx
0x180115ff2  lea     rcx, aTmpstatusNtsta; "((TmpStatus == ((NTSTATUS)0x80000005L))"...
0x180115ff9  jmp     loc_180115EDD
0x180115ffe  mov     rcx, gs:60h
0x180116007  xor     edx, edx; Flags
0x180116009  mov     r8d, [rbp+BufferLength]; Size
0x18011600d  mov     rcx, [rcx+30h]; HeapHandle
0x180116011  call    cs:__imp_RtlAllocateHeap
0x180116018  nop     dword ptr [rax+rax+00h]
0x18011601d  mov     [rdi], rax
0x180116020  mov     rdx, rax; SelfRelativeSD
0x180116023  test    rax, rax
0x180116026  jnz     short loc_18011603C
0x180116028  mov     [rbp+var_30], 34Bh
0x180116030  lea     rax, aMPsdRtlallocat_1; "m_pSD = ::RtlAllocateHeap((((PPEB)__rea"...
0x180116037  jmp     loc_180115F4B
0x18011603c  mov     eax, [rbp+BufferLength]
0x18011603f  lea     r8, [rbp+BufferLength]; BufferLength
0x180116043  mov     rcx, rbx; AbsoluteSD
0x180116046  mov     [rdi+8], rax
0x18011604a  call    cs:__imp_RtlMakeSelfRelativeSD
0x180116051  nop     dword ptr [rax+rax+00h]
0x180116056  test    eax, eax
0x180116058  jns     loc_180115F86
0x18011605e  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180116065  mov     [rbp+var_30], 352h
0x18011606d  mov     [rbp+var_40], rcx
0x180116071  lea     rcx, aWindowsAutoStr_2; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x180116078  mov     [rbp+var_38], rcx
0x18011607c  lea     rcx, aRtlmakeselfrel; "RtlMakeSelfRelativeSD( pTempSd, m_pSD, "...
0x180116083  jmp     loc_180115EDD
0x180116088  mov     ecx, 0C00000E5h; int
0x18011608d  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x180116092  int     3; Trap to Debugger
0x180116093  mov     ecx, 0C00000E5h; int
0x180116098  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
