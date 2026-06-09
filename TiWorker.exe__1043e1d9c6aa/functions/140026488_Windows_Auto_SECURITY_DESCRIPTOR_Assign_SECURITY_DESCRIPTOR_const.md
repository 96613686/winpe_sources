# Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)

- ea: `0x140026488`
- end: `0x14002669b`
- name: `?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `531`
- prototype: `__int64 __fastcall(_QWORD *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140026840`

## callees

- `0x140002310`
- `0x140006950`
- `0x140006b54`
- `0x140026488`
- `0x14002acf8`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140026545`
- `ntdll!RtlAllocateHeap` at `0x14002661a`
- `ntdll!RtlAllocateHeap` at `0x140026545`
- `ntdll!RtlAllocateHeap` at `0x14002661a`
- `ntdll!RtlLengthSecurityDescriptor` at `0x14002652b`
- `ntdll!RtlLengthSecurityDescriptor` at `0x14002652b`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1400264d4`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1400264d4`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1400265c1`
- `ntdll!RtlMakeSelfRelativeSD` at `0x14002664d`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1400265c1`
- `ntdll!RtlMakeSelfRelativeSD` at `0x14002664d`

## string_xrefs

- `0x1400264de`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x140026562`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1400265dd`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x14002665b`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1400264f1`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x140026577`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x1400265f0`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x14002666e`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x1400264fc`: `RtlGetControlSecurityDescriptor(pTempSd, &Control, &Revision)`
- `0x14002655b`: `m_pSD = RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, Size)`
- `0x140026633`: `m_pSD = ::RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, cbSecurityDescriptor)`
- `0x140026679`: `RtlMakeSelfRelativeSD( pTempSd, m_pSD, &cbSecurityDescriptor)`

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
0x140026488  mov     [rsp-18h+arg_10], rbx
0x14002648d  push    rbp
0x14002648e  push    rsi
0x14002648f  push    rdi
0x140026490  mov     rbp, rsp
0x140026493  sub     rsp, 60h
0x140026497  mov     rax, cs:__security_cookie
0x14002649e  xor     rax, rsp
0x1400264a1  mov     [rbp+var_10], rax
0x1400264a5  cmp     qword ptr [rcx], 0
0x1400264a9  mov     rbx, rdx
0x1400264ac  mov     rdi, rcx
0x1400264af  mov     [rbp+var_1C], 0
0x1400264b6  jnz     loc_140026685
0x1400264bc  xor     eax, eax
0x1400264be  mov     [rbp+Revision], 0
0x1400264c5  lea     r8, [rbp+Revision]; Revision
0x1400264c9  mov     [rbp+Control], ax
0x1400264cd  lea     rdx, [rbp+Control]; Control
0x1400264d1  mov     rcx, rbx; SecurityDescriptor
0x1400264d4  call    cs:__imp_RtlGetControlSecurityDescriptor
0x1400264da  test    eax, eax
0x1400264dc  jns     short loc_140026519
0x1400264de  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1400264e5  mov     [rbp+var_30], 335h
0x1400264ed  mov     [rbp+var_40], rcx
0x1400264f1  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x1400264f8  mov     [rbp+var_38], rcx
0x1400264fc  lea     rcx, aRtlgetcontrols; "RtlGetControlSecurityDescriptor(pTempSd"...
0x140026503  mov     [rbp+var_28], rcx
0x140026507  mov     r8d, eax
0x14002650a  lea     rdx, [rbp+var_40]
0x14002650e  lea     rcx, [rbp+var_1C]
0x140026512  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140026517  jmp     short loc_140026598
0x140026519  mov     eax, 8000h
0x14002651e  mov     rcx, rbx; AbsoluteSD
0x140026521  test    [rbp+Control], ax
0x140026525  jz      loc_1400265B4
0x14002652b  call    cs:__imp_RtlLengthSecurityDescriptor
0x140026531  mov     rcx, gs:60h
0x14002653a  xor     edx, edx; Flags
0x14002653c  mov     r8d, eax; Size
0x14002653f  mov     esi, eax
0x140026541  mov     rcx, [rcx+30h]; HeapHandle
0x140026545  call    cs:__imp_RtlAllocateHeap
0x14002654b  mov     [rdi], rax
0x14002654e  test    rax, rax
0x140026551  jnz     short loc_140026584
0x140026553  mov     [rbp+var_30], 33Bh
0x14002655b  lea     rax, aMPsdRtlallocat; "m_pSD = RtlAllocateHeap((((PPEB)__readg"...
0x140026562  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140026569  mov     [rbp+var_28], rax
0x14002656d  mov     [rbp+var_40], rcx
0x140026571  mov     r8d, 0C0000017h
0x140026577  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x14002657e  mov     [rbp+var_38], rcx
0x140026582  jmp     short loc_14002650A
0x140026584  mov     r8, rsi; Size
0x140026587  mov     rdx, rbx; Src
0x14002658a  mov     rcx, rax; void *
0x14002658d  call    memcpy_0
0x140026592  mov     [rdi+8], rsi
0x140026596  xor     eax, eax
0x140026598  mov     rcx, [rbp+var_10]
0x14002659c  xor     rcx, rsp; StackCookie
0x14002659f  call    __security_check_cookie
0x1400265a4  mov     rbx, [rsp+60h+arg_10]
0x1400265ac  add     rsp, 60h
0x1400265b0  pop     rdi
0x1400265b1  pop     rsi
0x1400265b2  pop     rbp
0x1400265b3  retn
0x1400265b4  lea     r8, [rbp+BufferLength]; BufferLength
0x1400265b8  mov     [rbp+BufferLength], 0
0x1400265bf  xor     edx, edx; SelfRelativeSD
0x1400265c1  call    cs:__imp_RtlMakeSelfRelativeSD
0x1400265c7  cmp     eax, 80000005h
0x1400265cc  jz      short loc_140026607
0x1400265ce  cmp     eax, 0C0000023h
0x1400265d3  jz      short loc_140026607
0x1400265d5  test    eax, eax
0x1400265d7  jns     loc_140026690
0x1400265dd  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1400265e4  mov     [rbp+var_30], 349h
0x1400265ec  mov     [rbp+var_40], rcx
0x1400265f0  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x1400265f7  mov     [rbp+var_38], rcx
0x1400265fb  lea     rcx, aTmpstatusNtsta; "((TmpStatus == ((NTSTATUS)0x80000005L))"...
0x140026602  jmp     loc_140026503
0x140026607  mov     rcx, gs:60h
0x140026610  xor     edx, edx; Flags
0x140026612  mov     r8d, [rbp+BufferLength]; Size
0x140026616  mov     rcx, [rcx+30h]; HeapHandle
0x14002661a  call    cs:__imp_RtlAllocateHeap
0x140026620  mov     [rdi], rax
0x140026623  mov     rdx, rax; SelfRelativeSD
0x140026626  test    rax, rax
0x140026629  jnz     short loc_14002663F
0x14002662b  mov     [rbp+var_30], 34Bh
0x140026633  lea     rax, aMPsdRtlallocat_0; "m_pSD = ::RtlAllocateHeap((((PPEB)__rea"...
0x14002663a  jmp     loc_140026562
0x14002663f  mov     eax, [rbp+BufferLength]
0x140026642  lea     r8, [rbp+BufferLength]; BufferLength
0x140026646  mov     rcx, rbx; AbsoluteSD
0x140026649  mov     [rdi+8], rax
0x14002664d  call    cs:__imp_RtlMakeSelfRelativeSD
0x140026653  test    eax, eax
0x140026655  jns     loc_140026596
0x14002665b  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140026662  mov     [rbp+var_30], 352h
0x14002666a  mov     [rbp+var_40], rcx
0x14002666e  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x140026675  mov     [rbp+var_38], rcx
0x140026679  lea     rcx, aRtlmakeselfrel; "RtlMakeSelfRelativeSD( pTempSd, m_pSD, "...
0x140026680  jmp     loc_140026503
0x140026685  mov     ecx, 0C00000E5h; int
0x14002668a  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x140026690  mov     ecx, 0C00000E5h; int
0x140026695  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
