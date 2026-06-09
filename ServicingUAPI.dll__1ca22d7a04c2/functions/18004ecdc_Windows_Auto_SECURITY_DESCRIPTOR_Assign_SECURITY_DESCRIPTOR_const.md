# Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)

- ea: `0x18004ecdc`
- end: `0x18004ef04`
- name: `?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `552`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004f398`
- `0x18012fa2c`
- `0x180150040`
- `0x1801a2980`
- `0x1801a2b58`
- `0x1801a2cc4`
- `0x1801a32e8`
- `0x1801a3884`

## callees

- `0x1800031d0`
- `0x18000693e`
- `0x18000aedc`
- `0x1800497c0`
- `0x18004ecdc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18004eda8`
- `ntdll!RtlAllocateHeap` at `0x18004ee8b`
- `ntdll!RtlAllocateHeap` at `0x18004eda8`
- `ntdll!RtlAllocateHeap` at `0x18004ee8b`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18004ee40`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18004eec4`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18004ee40`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18004eec4`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18004ed21`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18004ed21`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18004ed88`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18004ed88`

## string_xrefs

- `0x18004ed42`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004edcb`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004ed58`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x18004ede1`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x18004ed3b`: `RtlGetControlSecurityDescriptor(pTempSd, &Control, &Revision)`
- `0x18004eeaa`: `m_pSD = ::RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, cbSecurityDescriptor)`
- `0x18004eee2`: `RtlMakeSelfRelativeSD( pTempSd, m_pSD, &cbSecurityDescriptor)`
- `0x18004edc4`: `m_pSD = RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, Size)`

## pseudocode

```c
__int64 __fastcall Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_QWORD *a1, void *a2)
{
  NTSTATUS ControlSecurityDescriptor; // ebx
  const char *v5; // rax
  SIZE_T v7; // rbx
  PVOID v8; // rax
  const char *v9; // rax
  NTSTATUS SelfRelativeSD; // eax
  PVOID Heap; // rax
  const char *v12; // [rsp+20h] [rbp-40h] BYREF
  const char *v13; // [rsp+28h] [rbp-38h]
  __int64 v14; // [rsp+30h] [rbp-30h]
  const char *v15; // [rsp+38h] [rbp-28h]
  WORD Control[2]; // [rsp+40h] [rbp-20h] BYREF
  ULONG BufferLength; // [rsp+44h] [rbp-1Ch] BYREF
  ULONG Revision; // [rsp+48h] [rbp-18h] BYREF

  if ( *a1 )
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
    v5 = "RtlGetControlSecurityDescriptor(pTempSd, &Control, &Revision)";
LABEL_4:
    v15 = v5;
    v12 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v13 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
    RtlReportErrorOrigination(&v12, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)ControlSecurityDescriptor);
    return (unsigned int)ControlSecurityDescriptor;
  }
  if ( (Control[0] & 0x8000u) == 0 )
  {
    BufferLength = 0;
    SelfRelativeSD = RtlMakeSelfRelativeSD(a2, 0, &BufferLength);
    ControlSecurityDescriptor = SelfRelativeSD;
    if ( SelfRelativeSD != -2147483643 && SelfRelativeSD != -1073741789 )
    {
      if ( SelfRelativeSD >= 0 )
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x18004EF03LL);
      }
      v14 = 841;
      v5 = "((TmpStatus == ((NTSTATUS)0x80000005L)) || (TmpStatus == ((NTSTATUS)0xC0000023L)))";
      goto LABEL_4;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, BufferLength);
    *a1 = Heap;
    if ( !Heap )
    {
      v14 = 843;
      v9 = "m_pSD = ::RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->P"
           "rocessHeap), 0, cbSecurityDescriptor)";
      goto LABEL_8;
    }
    a1[1] = BufferLength;
    ControlSecurityDescriptor = RtlMakeSelfRelativeSD(a2, Heap, &BufferLength);
    if ( ControlSecurityDescriptor < 0 )
    {
      v14 = 850;
      v5 = "RtlMakeSelfRelativeSD( pTempSd, m_pSD, &cbSecurityDescriptor)";
      goto LABEL_4;
    }
  }
  else
  {
    v7 = RtlLengthSecurityDescriptor(a2);
    v8 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    *a1 = v8;
    if ( !v8 )
    {
      v14 = 827;
      v9 = "m_pSD = RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->Pro"
           "cessHeap), 0, Size)";
LABEL_8:
      v15 = v9;
      v12 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v13 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
      RtlReportErrorOrigination(&v12, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
      return 3221225495LL;
    }
    memcpy_0(v8, a2, v7);
    a1[1] = v7;
  }
  return 0;
}

```

## disassembly

```asm
0x18004ecdc  mov     [rsp-18h+arg_10], rbx
0x18004ece1  push    rbp
0x18004ece2  push    rsi
0x18004ece3  push    rdi
0x18004ece4  mov     rbp, rsp
0x18004ece7  sub     rsp, 60h
0x18004eceb  mov     rax, cs:__security_cookie
0x18004ecf2  xor     rax, rsp
0x18004ecf5  mov     [rbp+var_10], rax
0x18004ecf9  cmp     qword ptr [rcx], 0
0x18004ecfd  mov     rdi, rdx
0x18004ed00  mov     rsi, rcx
0x18004ed03  jnz     loc_18004EEEE
0x18004ed09  xor     eax, eax
0x18004ed0b  mov     [rbp+Revision], 0
0x18004ed12  lea     r8, [rbp+Revision]; Revision
0x18004ed16  mov     [rbp+Control], ax
0x18004ed1a  lea     rdx, [rbp+Control]; Control
0x18004ed1e  mov     rcx, rdi; SecurityDescriptor
0x18004ed21  call    cs:__imp_RtlGetControlSecurityDescriptor
0x18004ed28  nop     dword ptr [rax+rax+00h]
0x18004ed2d  mov     ebx, eax
0x18004ed2f  test    eax, eax
0x18004ed31  jns     short loc_18004ED76
0x18004ed33  mov     [rbp+var_30], 335h
0x18004ed3b  lea     rax, aRtlgetcontrols_2; "RtlGetControlSecurityDescriptor(pTempSd"...
0x18004ed42  lea     rcx, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004ed49  mov     [rbp+var_28], rax
0x18004ed4d  mov     [rbp+var_40], rcx
0x18004ed51  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18004ed58  lea     rcx, aWindowsAutoStr_2; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x18004ed5f  mov     r8d, ebx
0x18004ed62  mov     [rbp+var_38], rcx
0x18004ed66  lea     rcx, [rbp+var_40]
0x18004ed6a  call    RtlReportErrorOrigination
0x18004ed6f  mov     eax, ebx
0x18004ed71  jmp     loc_18004EE16
0x18004ed76  mov     eax, 8000h
0x18004ed7b  mov     rcx, rdi; AbsoluteSD
0x18004ed7e  test    [rbp+Control], ax
0x18004ed82  jz      loc_18004EE33
0x18004ed88  call    cs:__imp_RtlLengthSecurityDescriptor
0x18004ed8f  nop     dword ptr [rax+rax+00h]
0x18004ed94  mov     rcx, gs:60h
0x18004ed9d  xor     edx, edx; Flags
0x18004ed9f  mov     r8d, eax; Size
0x18004eda2  mov     ebx, eax
0x18004eda4  mov     rcx, [rcx+30h]; HeapHandle
0x18004eda8  call    cs:__imp_RtlAllocateHeap
0x18004edaf  nop     dword ptr [rax+rax+00h]
0x18004edb4  mov     [rsi], rax
0x18004edb7  test    rax, rax
0x18004edba  jnz     short loc_18004EE02
0x18004edbc  mov     [rbp+var_30], 33Bh
0x18004edc4  lea     rax, aMPsdRtlallocat_0; "m_pSD = RtlAllocateHeap((((PPEB)__readg"...
0x18004edcb  lea     rcx, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004edd2  mov     [rbp+var_28], rax
0x18004edd6  mov     [rbp+var_40], rcx
0x18004edda  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18004ede1  lea     rcx, aWindowsAutoStr_2; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x18004ede8  mov     r8d, 0C0000017h
0x18004edee  mov     [rbp+var_38], rcx
0x18004edf2  lea     rcx, [rbp+var_40]
0x18004edf6  call    RtlReportErrorOrigination
0x18004edfb  mov     eax, 0C0000017h
0x18004ee00  jmp     short loc_18004EE16
0x18004ee02  mov     r8, rbx; Size
0x18004ee05  mov     rdx, rdi; Src
0x18004ee08  mov     rcx, rax; void *
0x18004ee0b  call    memcpy_0
0x18004ee10  mov     [rsi+8], rbx
0x18004ee14  xor     eax, eax
0x18004ee16  mov     rcx, [rbp+var_10]
0x18004ee1a  xor     rcx, rsp; StackCookie
0x18004ee1d  call    __security_check_cookie
0x18004ee22  mov     rbx, [rsp+60h+arg_10]
0x18004ee2a  add     rsp, 60h
0x18004ee2e  pop     rdi
0x18004ee2f  pop     rsi
0x18004ee30  pop     rbp
0x18004ee31  retn
0x18004ee33  lea     r8, [rbp+BufferLength]; BufferLength
0x18004ee37  mov     [rbp+BufferLength], 0
0x18004ee3e  xor     edx, edx; SelfRelativeSD
0x18004ee40  call    cs:__imp_RtlMakeSelfRelativeSD
0x18004ee47  nop     dword ptr [rax+rax+00h]
0x18004ee4c  mov     ebx, eax
0x18004ee4e  cmp     eax, 80000005h
0x18004ee53  jz      short loc_18004EE78
0x18004ee55  cmp     eax, 0C0000023h
0x18004ee5a  jz      short loc_18004EE78
0x18004ee5c  test    eax, eax
0x18004ee5e  jns     loc_18004EEF9
0x18004ee64  mov     [rbp+var_30], 349h
0x18004ee6c  lea     rax, aTmpstatusNtsta; "((TmpStatus == ((NTSTATUS)0x80000005L))"...
0x18004ee73  jmp     loc_18004ED42
0x18004ee78  mov     rcx, gs:60h
0x18004ee81  xor     edx, edx; Flags
0x18004ee83  mov     r8d, [rbp+BufferLength]; Size
0x18004ee87  mov     rcx, [rcx+30h]; HeapHandle
0x18004ee8b  call    cs:__imp_RtlAllocateHeap
0x18004ee92  nop     dword ptr [rax+rax+00h]
0x18004ee97  mov     [rsi], rax
0x18004ee9a  mov     rdx, rax; SelfRelativeSD
0x18004ee9d  test    rax, rax
0x18004eea0  jnz     short loc_18004EEB6
0x18004eea2  mov     [rbp+var_30], 34Bh
0x18004eeaa  lea     rax, aMPsdRtlallocat_1; "m_pSD = ::RtlAllocateHeap((((PPEB)__rea"...
0x18004eeb1  jmp     loc_18004EDCB
0x18004eeb6  mov     eax, [rbp+BufferLength]
0x18004eeb9  lea     r8, [rbp+BufferLength]; BufferLength
0x18004eebd  mov     rcx, rdi; AbsoluteSD
0x18004eec0  mov     [rsi+8], rax
0x18004eec4  call    cs:__imp_RtlMakeSelfRelativeSD
0x18004eecb  nop     dword ptr [rax+rax+00h]
0x18004eed0  mov     ebx, eax
0x18004eed2  test    eax, eax
0x18004eed4  jns     loc_18004EE14
0x18004eeda  mov     [rbp+var_30], 352h
0x18004eee2  lea     rax, aRtlmakeselfrel; "RtlMakeSelfRelativeSD( pTempSd, m_pSD, "...
0x18004eee9  jmp     loc_18004ED42
0x18004eeee  mov     ecx, 0C00000E5h; int
0x18004eef3  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x18004eef8  int     3; Trap to Debugger
0x18004eef9  mov     ecx, 0C00000E5h; int
0x18004eefe  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
