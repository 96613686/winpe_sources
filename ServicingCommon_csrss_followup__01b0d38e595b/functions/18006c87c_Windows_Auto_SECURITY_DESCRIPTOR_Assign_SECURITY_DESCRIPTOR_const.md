# Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)

- ea: `0x18006c87c`
- end: `0x18006cac4`
- name: `?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `584`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006cc7c`
- `0x180096a60`

## callees

- `0x18001f840`
- `0x1800217cc`
- `0x18002d2b0`
- `0x18006c87c`
- `0x1800981e0`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x18006c936`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18006c936`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18006c8d6`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18006c8d6`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18006c9e0`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18006ca86`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18006c9e0`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18006ca86`
- `ntdll!RtlAllocateHeap` at `0x18006c956`
- `ntdll!RtlAllocateHeap` at `0x18006ca4d`
- `ntdll!RtlAllocateHeap` at `0x18006c956`
- `ntdll!RtlAllocateHeap` at `0x18006ca4d`
- `ntdll!RtlRaiseStatus` at `0x18006c8b1`
- `ntdll!RtlRaiseStatus` at `0x18006ca03`
- `ntdll!RtlRaiseStatus` at `0x18006c8b1`
- `ntdll!RtlRaiseStatus` at `0x18006ca03`

## string_xrefs

- `0x18006c8e6`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006c979`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006ca10`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006ca9a`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006c904`: `RtlGetControlSecurityDescriptor(pTempSd, &Control, &Revision)`
- `0x18006c8f9`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x18006c98c`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x18006ca23`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x18006caad`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x18006c972`: `m_pSD = RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, Size)`
- `0x18006cab8`: `RtlMakeSelfRelativeSD( pTempSd, m_pSD, &cbSecurityDescriptor)`
- `0x18006ca6c`: `m_pSD = ::RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, cbSecurityDescriptor)`

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
    RtlRaiseStatus(-1073741595);
  Revision = 0;
  Control[0] = 0;
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(a2, Control, &Revision);
  if ( ControlSecurityDescriptor < 0 )
  {
    v14 = 821;
    v12 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v13 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
    v6 = "RtlGetControlSecurityDescriptor(pTempSd, &Control, &Revision)";
LABEL_5:
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
        RtlRaiseStatus(-1073741595);
      v14 = 841;
      v12 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v13 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
      v6 = "((TmpStatus == ((NTSTATUS)0x80000005L)) || (TmpStatus == ((NTSTATUS)0xC0000023L)))";
      goto LABEL_5;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, BufferLength);
    *a1 = Heap;
    if ( !Heap )
    {
      v14 = 843;
      v10 = "m_pSD = ::RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->"
            "ProcessHeap), 0, cbSecurityDescriptor)";
      goto LABEL_9;
    }
    a1[1] = BufferLength;
    ControlSecurityDescriptor = RtlMakeSelfRelativeSD(a2, Heap, &BufferLength);
    if ( ControlSecurityDescriptor < 0 )
    {
      v14 = 850;
      v12 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v13 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
      v6 = "RtlMakeSelfRelativeSD( pTempSd, m_pSD, &cbSecurityDescriptor)";
      goto LABEL_5;
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
LABEL_9:
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
0x18006c87c  mov     [rsp-18h+arg_10], rbx
0x18006c881  push    rbp
0x18006c882  push    rsi
0x18006c883  push    rdi
0x18006c884  mov     rbp, rsp
0x18006c887  sub     rsp, 60h
0x18006c88b  mov     rax, cs:__security_cookie
0x18006c892  xor     rax, rsp
0x18006c895  mov     [rbp+var_10], rax
0x18006c899  cmp     qword ptr [rcx], 0
0x18006c89d  mov     rbx, rdx
0x18006c8a0  mov     rdi, rcx
0x18006c8a3  mov     [rbp+var_1C], 0
0x18006c8aa  jz      short loc_18006C8BE
0x18006c8ac  mov     ecx, 0C00000E5h; Status
0x18006c8b1  call    cs:__imp_RtlRaiseStatus
0x18006c8b8  nop     dword ptr [rax+rax+00h]
0x18006c8bd  int     3; Trap to Debugger
0x18006c8be  xor     eax, eax
0x18006c8c0  mov     [rbp+Revision], 0
0x18006c8c7  lea     r8, [rbp+Revision]; Revision
0x18006c8cb  mov     [rbp+Control], ax
0x18006c8cf  lea     rdx, [rbp+Control]; Control
0x18006c8d3  mov     rcx, rbx; SecurityDescriptor
0x18006c8d6  call    cs:__imp_RtlGetControlSecurityDescriptor
0x18006c8dd  nop     dword ptr [rax+rax+00h]
0x18006c8e2  test    eax, eax
0x18006c8e4  jns     short loc_18006C924
0x18006c8e6  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006c8ed  mov     [rbp+var_30], 335h
0x18006c8f5  mov     [rbp+var_40], rcx
0x18006c8f9  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x18006c900  mov     [rbp+var_38], rcx
0x18006c904  lea     rcx, aRtlgetcontrols; "RtlGetControlSecurityDescriptor(pTempSd"...
0x18006c90b  mov     [rbp+var_28], rcx
0x18006c90f  lea     rdx, [rbp+var_40]
0x18006c913  lea     rcx, [rbp+var_1C]
0x18006c917  mov     r8d, eax
0x18006c91a  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006c91f  jmp     loc_18006C9B6
0x18006c924  mov     eax, 8000h
0x18006c929  mov     rcx, rbx; AbsoluteSD
0x18006c92c  test    [rbp+Control], ax
0x18006c930  jz      loc_18006C9D3
0x18006c936  call    cs:__imp_RtlLengthSecurityDescriptor
0x18006c93d  nop     dword ptr [rax+rax+00h]
0x18006c942  mov     rcx, gs:60h
0x18006c94b  xor     edx, edx; Flags
0x18006c94d  mov     r8d, eax; Size
0x18006c950  mov     esi, eax
0x18006c952  mov     rcx, [rcx+30h]; HeapHandle
0x18006c956  call    cs:__imp_RtlAllocateHeap
0x18006c95d  nop     dword ptr [rax+rax+00h]
0x18006c962  mov     [rdi], rax
0x18006c965  test    rax, rax
0x18006c968  jnz     short loc_18006C9A2
0x18006c96a  mov     [rbp+var_30], 33Bh
0x18006c972  lea     rax, aMPsdRtlallocat; "m_pSD = RtlAllocateHeap((((PPEB)__readg"...
0x18006c979  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006c980  mov     [rbp+var_28], rax
0x18006c984  mov     [rbp+var_40], rcx
0x18006c988  lea     rdx, [rbp+var_40]
0x18006c98c  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x18006c993  mov     [rbp+var_38], rcx
0x18006c997  lea     rcx, [rbp+var_1C]
0x18006c99b  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18006c9a0  jmp     short loc_18006C9B6
0x18006c9a2  mov     r8, rsi; Size
0x18006c9a5  mov     rdx, rbx; Src
0x18006c9a8  mov     rcx, rax; void *
0x18006c9ab  call    memmove
0x18006c9b0  mov     [rdi+8], rsi
0x18006c9b4  xor     eax, eax
0x18006c9b6  mov     rcx, [rbp+var_10]
0x18006c9ba  xor     rcx, rsp; StackCookie
0x18006c9bd  call    __security_check_cookie
0x18006c9c2  mov     rbx, [rsp+60h+arg_10]
0x18006c9ca  add     rsp, 60h
0x18006c9ce  pop     rdi
0x18006c9cf  pop     rsi
0x18006c9d0  pop     rbp
0x18006c9d1  retn
0x18006c9d3  lea     r8, [rbp+BufferLength]; BufferLength
0x18006c9d7  mov     [rbp+BufferLength], 0
0x18006c9de  xor     edx, edx; SelfRelativeSD
0x18006c9e0  call    cs:__imp_RtlMakeSelfRelativeSD
0x18006c9e7  nop     dword ptr [rax+rax+00h]
0x18006c9ec  cmp     eax, 80000005h
0x18006c9f1  jz      short loc_18006CA3A
0x18006c9f3  cmp     eax, 0C0000023h
0x18006c9f8  jz      short loc_18006CA3A
0x18006c9fa  test    eax, eax
0x18006c9fc  js      short loc_18006CA10
0x18006c9fe  mov     ecx, 0C00000E5h; Status
0x18006ca03  call    cs:__imp_RtlRaiseStatus
0x18006ca0a  nop     dword ptr [rax+rax+00h]
0x18006ca0f  int     3; Trap to Debugger
0x18006ca10  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006ca17  mov     [rbp+var_30], 349h
0x18006ca1f  mov     [rbp+var_40], rcx
0x18006ca23  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x18006ca2a  mov     [rbp+var_38], rcx
0x18006ca2e  lea     rcx, aTmpstatusNtsta; "((TmpStatus == ((NTSTATUS)0x80000005L))"...
0x18006ca35  jmp     loc_18006C90B
0x18006ca3a  mov     rcx, gs:60h
0x18006ca43  xor     edx, edx; Flags
0x18006ca45  mov     r8d, [rbp+BufferLength]; Size
0x18006ca49  mov     rcx, [rcx+30h]; HeapHandle
0x18006ca4d  call    cs:__imp_RtlAllocateHeap
0x18006ca54  nop     dword ptr [rax+rax+00h]
0x18006ca59  mov     [rdi], rax
0x18006ca5c  mov     rdx, rax; SelfRelativeSD
0x18006ca5f  test    rax, rax
0x18006ca62  jnz     short loc_18006CA78
0x18006ca64  mov     [rbp+var_30], 34Bh
0x18006ca6c  lea     rax, aMPsdRtlallocat_0; "m_pSD = ::RtlAllocateHeap((((PPEB)__rea"...
0x18006ca73  jmp     loc_18006C979
0x18006ca78  mov     eax, [rbp+BufferLength]
0x18006ca7b  lea     r8, [rbp+BufferLength]; BufferLength
0x18006ca7f  mov     rcx, rbx; AbsoluteSD
0x18006ca82  mov     [rdi+8], rax
0x18006ca86  call    cs:__imp_RtlMakeSelfRelativeSD
0x18006ca8d  nop     dword ptr [rax+rax+00h]
0x18006ca92  test    eax, eax
0x18006ca94  jns     loc_18006C9B4
0x18006ca9a  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006caa1  mov     [rbp+var_30], 352h
0x18006caa9  mov     [rbp+var_40], rcx
0x18006caad  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x18006cab4  mov     [rbp+var_38], rcx
0x18006cab8  lea     rcx, aRtlmakeselfrel; "RtlMakeSelfRelativeSD( pTempSd, m_pSD, "...
0x18006cabf  jmp     loc_18006C90B
```
