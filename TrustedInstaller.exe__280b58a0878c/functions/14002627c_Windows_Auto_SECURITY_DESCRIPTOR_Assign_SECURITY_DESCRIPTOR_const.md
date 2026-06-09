# Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)

- ea: `0x14002627c`
- end: `0x14002648f`
- name: `?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `531`
- prototype: `__int64 __fastcall(_QWORD *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140026634`

## callees

- `0x1400023e0`
- `0x1400076ec`
- `0x140008138`
- `0x14002627c`
- `0x14002a958`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140026339`
- `ntdll!RtlAllocateHeap` at `0x14002640e`
- `ntdll!RtlAllocateHeap` at `0x140026339`
- `ntdll!RtlAllocateHeap` at `0x14002640e`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1400262c8`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1400262c8`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1400263b5`
- `ntdll!RtlMakeSelfRelativeSD` at `0x140026441`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1400263b5`
- `ntdll!RtlMakeSelfRelativeSD` at `0x140026441`
- `ntdll!RtlLengthSecurityDescriptor` at `0x14002631f`
- `ntdll!RtlLengthSecurityDescriptor` at `0x14002631f`

## string_xrefs

- `0x1400262d2`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x140026356`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1400263d1`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x14002644f`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1400262e5`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x14002636b`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x1400263e4`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x140026462`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x14002634f`: `m_pSD = RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, Size)`
- `0x1400262f0`: `RtlGetControlSecurityDescriptor(pTempSd, &Control, &Revision)`
- `0x140026427`: `m_pSD = ::RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, cbSecurityDescriptor)`
- `0x14002646d`: `RtlMakeSelfRelativeSD( pTempSd, m_pSD, &cbSecurityDescriptor)`

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
  PVOID Heap; // rax
  const char *v13; // [rsp+20h] [rbp-40h] BYREF
  const char *v14; // [rsp+28h] [rbp-38h]
  __int64 v15; // [rsp+30h] [rbp-30h]
  const char *v16; // [rsp+38h] [rbp-28h]
  WORD Control[2]; // [rsp+40h] [rbp-20h] BYREF
  int v18; // [rsp+44h] [rbp-1Ch] BYREF
  ULONG BufferLength; // [rsp+48h] [rbp-18h] BYREF
  ULONG Revision; // [rsp+4Ch] [rbp-14h] BYREF

  v2 = *a1 == 0;
  v18 = 0;
  if ( !v2 )
    INTERNAL_ERROR_ACTION(-1073741595);
  Revision = 0;
  Control[0] = 0;
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(a2, Control, &Revision);
  if ( ControlSecurityDescriptor < 0 )
  {
    v15 = 821;
    v13 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v14 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
    v6 = "RtlGetControlSecurityDescriptor(pTempSd, &Control, &Revision)";
LABEL_4:
    v16 = v6;
    v7 = (unsigned int)ControlSecurityDescriptor;
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
             &v18,
             &v13,
             v7);
  }
  if ( (Control[0] & 0x8000u) == 0 )
  {
    BufferLength = 0;
    ControlSecurityDescriptor = RtlMakeSelfRelativeSD(a2, 0, &BufferLength);
    if ( ControlSecurityDescriptor != -2147483643 && ControlSecurityDescriptor != -1073741789 )
    {
      if ( ControlSecurityDescriptor >= 0 )
        INTERNAL_ERROR_ACTION(-1073741595);
      v15 = 841;
      v13 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v14 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
      v6 = "((TmpStatus == ((NTSTATUS)0x80000005L)) || (TmpStatus == ((NTSTATUS)0xC0000023L)))";
      goto LABEL_4;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, BufferLength);
    *a1 = Heap;
    if ( !Heap )
    {
      v15 = 843;
      v11 = "m_pSD = ::RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->"
            "ProcessHeap), 0, cbSecurityDescriptor)";
      goto LABEL_9;
    }
    a1[1] = BufferLength;
    ControlSecurityDescriptor = RtlMakeSelfRelativeSD(a2, Heap, &BufferLength);
    if ( ControlSecurityDescriptor < 0 )
    {
      v15 = 850;
      v13 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v14 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
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
      v15 = 827;
      v11 = "m_pSD = RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->Pr"
            "ocessHeap), 0, Size)";
LABEL_9:
      v16 = v11;
      v13 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v7 = 3221225495LL;
      v14 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
      return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
               &v18,
               &v13,
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
0x14002627c  mov     [rsp-18h+arg_10], rbx
0x140026281  push    rbp
0x140026282  push    rsi
0x140026283  push    rdi
0x140026284  mov     rbp, rsp
0x140026287  sub     rsp, 60h
0x14002628b  mov     rax, cs:__security_cookie
0x140026292  xor     rax, rsp
0x140026295  mov     [rbp+var_10], rax
0x140026299  cmp     qword ptr [rcx], 0
0x14002629d  mov     rbx, rdx
0x1400262a0  mov     rdi, rcx
0x1400262a3  mov     [rbp+var_1C], 0
0x1400262aa  jnz     loc_140026479
0x1400262b0  xor     eax, eax
0x1400262b2  mov     [rbp+Revision], 0
0x1400262b9  lea     r8, [rbp+Revision]; Revision
0x1400262bd  mov     [rbp+Control], ax
0x1400262c1  lea     rdx, [rbp+Control]; Control
0x1400262c5  mov     rcx, rbx; SecurityDescriptor
0x1400262c8  call    cs:__imp_RtlGetControlSecurityDescriptor
0x1400262ce  test    eax, eax
0x1400262d0  jns     short loc_14002630D
0x1400262d2  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1400262d9  mov     [rbp+var_30], 335h
0x1400262e1  mov     [rbp+var_40], rcx
0x1400262e5  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x1400262ec  mov     [rbp+var_38], rcx
0x1400262f0  lea     rcx, aRtlgetcontrols; "RtlGetControlSecurityDescriptor(pTempSd"...
0x1400262f7  mov     [rbp+var_28], rcx
0x1400262fb  mov     r8d, eax
0x1400262fe  lea     rdx, [rbp+var_40]
0x140026302  lea     rcx, [rbp+var_1C]
0x140026306  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x14002630b  jmp     short loc_14002638C
0x14002630d  mov     eax, 8000h
0x140026312  mov     rcx, rbx; AbsoluteSD
0x140026315  test    [rbp+Control], ax
0x140026319  jz      loc_1400263A8
0x14002631f  call    cs:__imp_RtlLengthSecurityDescriptor
0x140026325  mov     rcx, gs:60h
0x14002632e  xor     edx, edx; Flags
0x140026330  mov     r8d, eax; Size
0x140026333  mov     esi, eax
0x140026335  mov     rcx, [rcx+30h]; HeapHandle
0x140026339  call    cs:__imp_RtlAllocateHeap
0x14002633f  mov     [rdi], rax
0x140026342  test    rax, rax
0x140026345  jnz     short loc_140026378
0x140026347  mov     [rbp+var_30], 33Bh
0x14002634f  lea     rax, aMPsdRtlallocat; "m_pSD = RtlAllocateHeap((((PPEB)__readg"...
0x140026356  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x14002635d  mov     [rbp+var_28], rax
0x140026361  mov     [rbp+var_40], rcx
0x140026365  mov     r8d, 0C0000017h
0x14002636b  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x140026372  mov     [rbp+var_38], rcx
0x140026376  jmp     short loc_1400262FE
0x140026378  mov     r8, rsi; Size
0x14002637b  mov     rdx, rbx; Src
0x14002637e  mov     rcx, rax; void *
0x140026381  call    memcpy_0
0x140026386  mov     [rdi+8], rsi
0x14002638a  xor     eax, eax
0x14002638c  mov     rcx, [rbp+var_10]
0x140026390  xor     rcx, rsp; StackCookie
0x140026393  call    __security_check_cookie
0x140026398  mov     rbx, [rsp+60h+arg_10]
0x1400263a0  add     rsp, 60h
0x1400263a4  pop     rdi
0x1400263a5  pop     rsi
0x1400263a6  pop     rbp
0x1400263a7  retn
0x1400263a8  lea     r8, [rbp+BufferLength]; BufferLength
0x1400263ac  mov     [rbp+BufferLength], 0
0x1400263b3  xor     edx, edx; SelfRelativeSD
0x1400263b5  call    cs:__imp_RtlMakeSelfRelativeSD
0x1400263bb  cmp     eax, 80000005h
0x1400263c0  jz      short loc_1400263FB
0x1400263c2  cmp     eax, 0C0000023h
0x1400263c7  jz      short loc_1400263FB
0x1400263c9  test    eax, eax
0x1400263cb  jns     loc_140026484
0x1400263d1  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1400263d8  mov     [rbp+var_30], 349h
0x1400263e0  mov     [rbp+var_40], rcx
0x1400263e4  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x1400263eb  mov     [rbp+var_38], rcx
0x1400263ef  lea     rcx, aTmpstatusNtsta; "((TmpStatus == ((NTSTATUS)0x80000005L))"...
0x1400263f6  jmp     loc_1400262F7
0x1400263fb  mov     rcx, gs:60h
0x140026404  xor     edx, edx; Flags
0x140026406  mov     r8d, [rbp+BufferLength]; Size
0x14002640a  mov     rcx, [rcx+30h]; HeapHandle
0x14002640e  call    cs:__imp_RtlAllocateHeap
0x140026414  mov     [rdi], rax
0x140026417  mov     rdx, rax; SelfRelativeSD
0x14002641a  test    rax, rax
0x14002641d  jnz     short loc_140026433
0x14002641f  mov     [rbp+var_30], 34Bh
0x140026427  lea     rax, aMPsdRtlallocat_0; "m_pSD = ::RtlAllocateHeap((((PPEB)__rea"...
0x14002642e  jmp     loc_140026356
0x140026433  mov     eax, [rbp+BufferLength]
0x140026436  lea     r8, [rbp+BufferLength]; BufferLength
0x14002643a  mov     rcx, rbx; AbsoluteSD
0x14002643d  mov     [rdi+8], rax
0x140026441  call    cs:__imp_RtlMakeSelfRelativeSD
0x140026447  test    eax, eax
0x140026449  jns     loc_14002638A
0x14002644f  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140026456  mov     [rbp+var_30], 352h
0x14002645e  mov     [rbp+var_40], rcx
0x140026462  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x140026469  mov     [rbp+var_38], rcx
0x14002646d  lea     rcx, aRtlmakeselfrel; "RtlMakeSelfRelativeSD( pTempSd, m_pSD, "...
0x140026474  jmp     loc_1400262F7
0x140026479  mov     ecx, 0C00000E5h; int
0x14002647e  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x140026484  mov     ecx, 0C00000E5h; int
0x140026489  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
