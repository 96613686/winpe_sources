# Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)

- ea: `0x1400272fc`
- end: `0x140027505`
- name: `?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400276a8`

## callees

- `0x140002360`
- `0x14000731c`
- `0x140026548`
- `0x1400272fc`
- `0x140029bf4`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x14002739f`
- `ntdll!RtlLengthSecurityDescriptor` at `0x14002739f`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x140027348`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x140027348`
- `ntdll!RtlMakeSelfRelativeSD` at `0x140027435`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1400274c1`
- `ntdll!RtlMakeSelfRelativeSD` at `0x140027435`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1400274c1`
- `ntdll!RtlAllocateHeap` at `0x1400273b9`
- `ntdll!RtlAllocateHeap` at `0x14002748e`
- `ntdll!RtlAllocateHeap` at `0x1400273b9`
- `ntdll!RtlAllocateHeap` at `0x14002748e`

## string_xrefs

- `0x140027352`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1400273d6`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x140027451`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1400274cf`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x140027365`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x1400273eb`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x140027464`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x1400274e2`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x140027370`: `RtlGetControlSecurityDescriptor(pTempSd, &Control, &Revision)`
- `0x1400273cf`: `m_pSD = RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, Size)`
- `0x1400274a7`: `m_pSD = ::RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, cbSecurityDescriptor)`
- `0x1400274ed`: `RtlMakeSelfRelativeSD( pTempSd, m_pSD, &cbSecurityDescriptor)`

## pseudocode

```c
__int64 __fastcall Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_QWORD *a1, void *a2)
{
  bool v2; // zf
  NTSTATUS ControlSecurityDescriptor; // eax
  const char *v6; // rcx
  __int64 v7; // r8
  SIZE_T v9; // rsi
  PVOID v10; // rax
  const char *v11; // rax
  int v12; // ecx
  PVOID Heap; // rax
  const char *v14; // [rsp+20h] [rbp-40h] BYREF
  const char *v15; // [rsp+28h] [rbp-38h]
  __int64 v16; // [rsp+30h] [rbp-30h]
  const char *v17; // [rsp+38h] [rbp-28h]
  WORD Control[2]; // [rsp+40h] [rbp-20h] BYREF
  int v19; // [rsp+44h] [rbp-1Ch] BYREF
  ULONG BufferLength; // [rsp+48h] [rbp-18h] BYREF
  ULONG Revision; // [rsp+4Ch] [rbp-14h] BYREF

  v2 = *a1 == 0;
  v19 = 0;
  if ( !v2 )
    INTERNAL_ERROR_ACTION((int)a1);
  Revision = 0;
  Control[0] = 0;
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(a2, Control, &Revision);
  if ( ControlSecurityDescriptor < 0 )
  {
    v16 = 821;
    v14 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v15 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
    v6 = "RtlGetControlSecurityDescriptor(pTempSd, &Control, &Revision)";
LABEL_4:
    v17 = v6;
    v7 = (unsigned int)ControlSecurityDescriptor;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v19,
             &v14,
             v7);
  }
  if ( (Control[0] & 0x8000u) == 0 )
  {
    BufferLength = 0;
    ControlSecurityDescriptor = RtlMakeSelfRelativeSD(a2, 0, &BufferLength);
    if ( ControlSecurityDescriptor != -2147483643 && ControlSecurityDescriptor != -1073741789 )
    {
      if ( ControlSecurityDescriptor >= 0 )
        INTERNAL_ERROR_ACTION(v12);
      v16 = 841;
      v14 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v15 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
      v6 = "((TmpStatus == ((NTSTATUS)0x80000005L)) || (TmpStatus == ((NTSTATUS)0xC0000023L)))";
      goto LABEL_4;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, BufferLength);
    *a1 = Heap;
    if ( !Heap )
    {
      v16 = 843;
      v11 = "m_pSD = ::RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->"
            "ProcessHeap), 0, cbSecurityDescriptor)";
      goto LABEL_9;
    }
    a1[1] = BufferLength;
    ControlSecurityDescriptor = RtlMakeSelfRelativeSD(a2, Heap, &BufferLength);
    if ( ControlSecurityDescriptor < 0 )
    {
      v16 = 850;
      v14 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v15 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
      v6 = "RtlMakeSelfRelativeSD( pTempSd, m_pSD, &cbSecurityDescriptor)";
      goto LABEL_4;
    }
  }
  else
  {
    v9 = RtlLengthSecurityDescriptor(a2);
    v10 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
    *a1 = v10;
    if ( !v10 )
    {
      v16 = 827;
      v11 = "m_pSD = RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->Pr"
            "ocessHeap), 0, Size)";
LABEL_9:
      v17 = v11;
      v14 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v7 = 3221225495LL;
      v15 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
               &v19,
               &v14,
               v7);
    }
    memcpy_0(v10, a2, v9);
    a1[1] = v9;
  }
  return 0;
}

```

## disassembly

```asm
0x1400272fc  mov     [rsp-18h+arg_10], rbx
0x140027301  push    rbp
0x140027302  push    rsi
0x140027303  push    rdi
0x140027304  mov     rbp, rsp
0x140027307  sub     rsp, 60h
0x14002730b  mov     rax, cs:__security_cookie
0x140027312  xor     rax, rsp
0x140027315  mov     [rbp+var_10], rax
0x140027319  cmp     qword ptr [rcx], 0
0x14002731d  mov     rbx, rdx
0x140027320  mov     rdi, rcx
0x140027323  mov     [rbp+var_1C], 0
0x14002732a  jnz     loc_1400274F9
0x140027330  xor     eax, eax
0x140027332  mov     [rbp+Revision], 0
0x140027339  lea     r8, [rbp+Revision]; Revision
0x14002733d  mov     [rbp+Control], ax
0x140027341  lea     rdx, [rbp+Control]; Control
0x140027345  mov     rcx, rbx; SecurityDescriptor
0x140027348  call    cs:__imp_RtlGetControlSecurityDescriptor
0x14002734e  test    eax, eax
0x140027350  jns     short loc_14002738D
0x140027352  lea     rcx, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140027359  mov     [rbp+var_30], 335h
0x140027361  mov     [rbp+var_40], rcx
0x140027365  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x14002736c  mov     [rbp+var_38], rcx
0x140027370  lea     rcx, aRtlgetcontrols; "RtlGetControlSecurityDescriptor(pTempSd"...
0x140027377  mov     [rbp+var_28], rcx
0x14002737b  mov     r8d, eax
0x14002737e  lea     rdx, [rbp+var_40]
0x140027382  lea     rcx, [rbp+var_1C]
0x140027386  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x14002738b  jmp     short loc_14002740C
0x14002738d  mov     eax, 8000h
0x140027392  mov     rcx, rbx; AbsoluteSD
0x140027395  test    [rbp+Control], ax
0x140027399  jz      loc_140027428
0x14002739f  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400273a5  mov     rcx, gs:60h
0x1400273ae  xor     edx, edx; Flags
0x1400273b0  mov     r8d, eax; Size
0x1400273b3  mov     esi, eax
0x1400273b5  mov     rcx, [rcx+30h]; HeapHandle
0x1400273b9  call    cs:__imp_RtlAllocateHeap
0x1400273bf  mov     [rdi], rax
0x1400273c2  test    rax, rax
0x1400273c5  jnz     short loc_1400273F8
0x1400273c7  mov     [rbp+var_30], 33Bh
0x1400273cf  lea     rax, aMPsdRtlallocat; "m_pSD = RtlAllocateHeap((((PPEB)__readg"...
0x1400273d6  lea     rcx, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1400273dd  mov     [rbp+var_28], rax
0x1400273e1  mov     [rbp+var_40], rcx
0x1400273e5  mov     r8d, 0C0000017h
0x1400273eb  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x1400273f2  mov     [rbp+var_38], rcx
0x1400273f6  jmp     short loc_14002737E
0x1400273f8  mov     r8, rsi; Size
0x1400273fb  mov     rdx, rbx; Src
0x1400273fe  mov     rcx, rax; void *
0x140027401  call    memcpy_0
0x140027406  mov     [rdi+8], rsi
0x14002740a  xor     eax, eax
0x14002740c  mov     rcx, [rbp+var_10]
0x140027410  xor     rcx, rsp; StackCookie
0x140027413  call    __security_check_cookie
0x140027418  mov     rbx, [rsp+60h+arg_10]
0x140027420  add     rsp, 60h
0x140027424  pop     rdi
0x140027425  pop     rsi
0x140027426  pop     rbp
0x140027427  retn
0x140027428  lea     r8, [rbp+BufferLength]; BufferLength
0x14002742c  mov     [rbp+BufferLength], 0
0x140027433  xor     edx, edx; SelfRelativeSD
0x140027435  call    cs:__imp_RtlMakeSelfRelativeSD
0x14002743b  cmp     eax, 80000005h
0x140027440  jz      short loc_14002747B
0x140027442  cmp     eax, 0C0000023h
0x140027447  jz      short loc_14002747B
0x140027449  test    eax, eax
0x14002744b  jns     loc_1400274FF
0x140027451  lea     rcx, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140027458  mov     [rbp+var_30], 349h
0x140027460  mov     [rbp+var_40], rcx
0x140027464  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x14002746b  mov     [rbp+var_38], rcx
0x14002746f  lea     rcx, aTmpstatusNtsta; "((TmpStatus == ((NTSTATUS)0x80000005L))"...
0x140027476  jmp     loc_140027377
0x14002747b  mov     rcx, gs:60h
0x140027484  xor     edx, edx; Flags
0x140027486  mov     r8d, [rbp+BufferLength]; Size
0x14002748a  mov     rcx, [rcx+30h]; HeapHandle
0x14002748e  call    cs:__imp_RtlAllocateHeap
0x140027494  mov     [rdi], rax
0x140027497  mov     rdx, rax; SelfRelativeSD
0x14002749a  test    rax, rax
0x14002749d  jnz     short loc_1400274B3
0x14002749f  mov     [rbp+var_30], 34Bh
0x1400274a7  lea     rax, aMPsdRtlallocat_0; "m_pSD = ::RtlAllocateHeap((((PPEB)__rea"...
0x1400274ae  jmp     loc_1400273D6
0x1400274b3  mov     eax, [rbp+BufferLength]
0x1400274b6  lea     r8, [rbp+BufferLength]; BufferLength
0x1400274ba  mov     rcx, rbx; AbsoluteSD
0x1400274bd  mov     [rdi+8], rax
0x1400274c1  call    cs:__imp_RtlMakeSelfRelativeSD
0x1400274c7  test    eax, eax
0x1400274c9  jns     loc_14002740A
0x1400274cf  lea     rcx, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1400274d6  mov     [rbp+var_30], 352h
0x1400274de  mov     [rbp+var_40], rcx
0x1400274e2  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x1400274e9  mov     [rbp+var_38], rcx
0x1400274ed  lea     rcx, aRtlmakeselfrel; "RtlMakeSelfRelativeSD( pTempSd, m_pSD, "...
0x1400274f4  jmp     loc_140027377
0x1400274f9  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x1400274ff  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
