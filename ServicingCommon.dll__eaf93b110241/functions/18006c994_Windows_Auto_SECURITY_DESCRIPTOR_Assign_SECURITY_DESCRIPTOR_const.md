# Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)

- ea: `0x18006c994`
- end: `0x18006cbd6`
- name: `?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `578`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006cd8c`
- `0x180098910`

## callees

- `0x18001f554`
- `0x18001f5d4`
- `0x18001fd10`
- `0x1800293a0`
- `0x18006c994`
- `0x18009a070`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x18006ca40`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18006ca40`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18006c9e0`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18006c9e0`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18006caea`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18006cb82`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18006caea`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18006cb82`
- `ntdll!RtlAllocateHeap` at `0x18006ca60`
- `ntdll!RtlAllocateHeap` at `0x18006cb49`
- `ntdll!RtlAllocateHeap` at `0x18006ca60`
- `ntdll!RtlAllocateHeap` at `0x18006cb49`

## string_xrefs

- `0x18006c9f0`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006ca83`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006cb0c`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006cb96`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006ca03`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x18006ca96`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x18006cb1f`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x18006cba9`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x18006ca7c`: `m_pSD = RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, Size)`
- `0x18006ca0e`: `RtlGetControlSecurityDescriptor(pTempSd, &Control, &Revision)`
- `0x18006cb68`: `m_pSD = ::RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, cbSecurityDescriptor)`
- `0x18006cbb4`: `RtlMakeSelfRelativeSD( pTempSd, m_pSD, &cbSecurityDescriptor)`

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
        JUMPOUT(0x18006CBD5LL);
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
    memmove(v9, a2, v8);
    a1[1] = v8;
  }
  return 0;
}

```

## disassembly

```asm
0x18006c994  mov     [rsp-18h+arg_10], rbx
0x18006c999  push    rbp
0x18006c99a  push    rsi
0x18006c99b  push    rdi
0x18006c99c  mov     rbp, rsp
0x18006c99f  sub     rsp, 60h
0x18006c9a3  mov     rax, cs:__security_cookie
0x18006c9aa  xor     rax, rsp
0x18006c9ad  mov     [rbp+var_10], rax
0x18006c9b1  cmp     qword ptr [rcx], 0
0x18006c9b5  mov     rbx, rdx
0x18006c9b8  mov     rdi, rcx
0x18006c9bb  mov     [rbp+var_1C], 0
0x18006c9c2  jnz     loc_18006CBC0
0x18006c9c8  xor     eax, eax
0x18006c9ca  mov     [rbp+Revision], 0
0x18006c9d1  lea     r8, [rbp+Revision]; Revision
0x18006c9d5  mov     [rbp+Control], ax
0x18006c9d9  lea     rdx, [rbp+Control]; Control
0x18006c9dd  mov     rcx, rbx; SecurityDescriptor
0x18006c9e0  call    cs:__imp_RtlGetControlSecurityDescriptor
0x18006c9e7  nop     dword ptr [rax+rax+00h]
0x18006c9ec  test    eax, eax
0x18006c9ee  jns     short loc_18006CA2E
0x18006c9f0  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006c9f7  mov     [rbp+var_30], 335h
0x18006c9ff  mov     [rbp+var_40], rcx
0x18006ca03  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x18006ca0a  mov     [rbp+var_38], rcx
0x18006ca0e  lea     rcx, aRtlgetcontrols; "RtlGetControlSecurityDescriptor(pTempSd"...
0x18006ca15  mov     [rbp+var_28], rcx
0x18006ca19  lea     rdx, [rbp+var_40]
0x18006ca1d  lea     rcx, [rbp+var_1C]
0x18006ca21  mov     r8d, eax
0x18006ca24  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006ca29  jmp     loc_18006CAC0
0x18006ca2e  mov     eax, 8000h
0x18006ca33  mov     rcx, rbx; AbsoluteSD
0x18006ca36  test    [rbp+Control], ax
0x18006ca3a  jz      loc_18006CADD
0x18006ca40  call    cs:__imp_RtlLengthSecurityDescriptor
0x18006ca47  nop     dword ptr [rax+rax+00h]
0x18006ca4c  mov     rcx, gs:60h
0x18006ca55  xor     edx, edx; Flags
0x18006ca57  mov     r8d, eax; Size
0x18006ca5a  mov     esi, eax
0x18006ca5c  mov     rcx, [rcx+30h]; HeapHandle
0x18006ca60  call    cs:__imp_RtlAllocateHeap
0x18006ca67  nop     dword ptr [rax+rax+00h]
0x18006ca6c  mov     [rdi], rax
0x18006ca6f  test    rax, rax
0x18006ca72  jnz     short loc_18006CAAC
0x18006ca74  mov     [rbp+var_30], 33Bh
0x18006ca7c  lea     rax, aMPsdRtlallocat; "m_pSD = RtlAllocateHeap((((PPEB)__readg"...
0x18006ca83  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006ca8a  mov     [rbp+var_28], rax
0x18006ca8e  mov     [rbp+var_40], rcx
0x18006ca92  lea     rdx, [rbp+var_40]
0x18006ca96  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x18006ca9d  mov     [rbp+var_38], rcx
0x18006caa1  lea     rcx, [rbp+var_1C]
0x18006caa5  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18006caaa  jmp     short loc_18006CAC0
0x18006caac  mov     r8, rsi; Size
0x18006caaf  mov     rdx, rbx; Src
0x18006cab2  mov     rcx, rax; void *
0x18006cab5  call    memmove
0x18006caba  mov     [rdi+8], rsi
0x18006cabe  xor     eax, eax
0x18006cac0  mov     rcx, [rbp+var_10]
0x18006cac4  xor     rcx, rsp; StackCookie
0x18006cac7  call    __security_check_cookie
0x18006cacc  mov     rbx, [rsp+60h+arg_10]
0x18006cad4  add     rsp, 60h
0x18006cad8  pop     rdi
0x18006cad9  pop     rsi
0x18006cada  pop     rbp
0x18006cadb  retn
0x18006cadd  lea     r8, [rbp+BufferLength]; BufferLength
0x18006cae1  mov     [rbp+BufferLength], 0
0x18006cae8  xor     edx, edx; SelfRelativeSD
0x18006caea  call    cs:__imp_RtlMakeSelfRelativeSD
0x18006caf1  nop     dword ptr [rax+rax+00h]
0x18006caf6  cmp     eax, 80000005h
0x18006cafb  jz      short loc_18006CB36
0x18006cafd  cmp     eax, 0C0000023h
0x18006cb02  jz      short loc_18006CB36
0x18006cb04  test    eax, eax
0x18006cb06  jns     loc_18006CBCB
0x18006cb0c  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006cb13  mov     [rbp+var_30], 349h
0x18006cb1b  mov     [rbp+var_40], rcx
0x18006cb1f  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x18006cb26  mov     [rbp+var_38], rcx
0x18006cb2a  lea     rcx, aTmpstatusNtsta; "((TmpStatus == ((NTSTATUS)0x80000005L))"...
0x18006cb31  jmp     loc_18006CA15
0x18006cb36  mov     rcx, gs:60h
0x18006cb3f  xor     edx, edx; Flags
0x18006cb41  mov     r8d, [rbp+BufferLength]; Size
0x18006cb45  mov     rcx, [rcx+30h]; HeapHandle
0x18006cb49  call    cs:__imp_RtlAllocateHeap
0x18006cb50  nop     dword ptr [rax+rax+00h]
0x18006cb55  mov     [rdi], rax
0x18006cb58  mov     rdx, rax; SelfRelativeSD
0x18006cb5b  test    rax, rax
0x18006cb5e  jnz     short loc_18006CB74
0x18006cb60  mov     [rbp+var_30], 34Bh
0x18006cb68  lea     rax, aMPsdRtlallocat_0; "m_pSD = ::RtlAllocateHeap((((PPEB)__rea"...
0x18006cb6f  jmp     loc_18006CA83
0x18006cb74  mov     eax, [rbp+BufferLength]
0x18006cb77  lea     r8, [rbp+BufferLength]; BufferLength
0x18006cb7b  mov     rcx, rbx; AbsoluteSD
0x18006cb7e  mov     [rdi+8], rax
0x18006cb82  call    cs:__imp_RtlMakeSelfRelativeSD
0x18006cb89  nop     dword ptr [rax+rax+00h]
0x18006cb8e  test    eax, eax
0x18006cb90  jns     loc_18006CABE
0x18006cb96  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006cb9d  mov     [rbp+var_30], 352h
0x18006cba5  mov     [rbp+var_40], rcx
0x18006cba9  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x18006cbb0  mov     [rbp+var_38], rcx
0x18006cbb4  lea     rcx, aRtlmakeselfrel; "RtlMakeSelfRelativeSD( pTempSd, m_pSD, "...
0x18006cbbb  jmp     loc_18006CA15
0x18006cbc0  mov     ecx, 0C00000E5h; int
0x18006cbc5  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x18006cbca  int     3; Trap to Debugger
0x18006cbcb  mov     ecx, 0C00000E5h; int
0x18006cbd0  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
