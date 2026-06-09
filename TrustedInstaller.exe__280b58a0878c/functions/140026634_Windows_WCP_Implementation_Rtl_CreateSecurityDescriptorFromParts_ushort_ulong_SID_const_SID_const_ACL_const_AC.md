# Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(ushort,ulong,_SID const *,_SID const *,_ACL const *,_ACL const *,Windows::Auto<_SECURITY_DESCRIPTOR> *)

- ea: `0x140026634`
- end: `0x1400267dc`
- name: `?CreateSecurityDescriptorFromParts@Rtl@Implementation@WCP@Windows@@YAJGKPEBU_SID@@0PEBU_ACL@@1PEAV?$Auto@U_SECURITY_DESCRIPTOR@@@4@@Z`
- size: `424`
- prototype: `__int64 __fastcall(__int64, __int64, void *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400261c8`

## callees

- `0x1400023e0`
- `0x140008138`
- `0x14002627c`
- `0x140026634`

## import_xrefs

- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1400266ce`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1400266ce`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x140026709`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x140026709`
- `ntdll!RtlCreateSecurityDescriptor` at `0x14002667c`
- `ntdll!RtlCreateSecurityDescriptor` at `0x14002667c`
- `ntdll!RtlFreeHeap` at `0x140026778`
- `ntdll!RtlFreeHeap` at `0x1400267b3`
- `ntdll!RtlFreeHeap` at `0x140026778`
- `ntdll!RtlFreeHeap` at `0x1400267b3`

## string_xrefs

- `0x140026686`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1400266d8`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x140026713`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1400266a4`: `RtlCreateSecurityDescriptor( &AbsoluteSD, (1))`
- `0x140026699`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x1400266eb`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x140026726`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x140026731`: `::RtlSetGroupSecurityDescriptor( &AbsoluteSD, (PSID)Group, 0)`
- `0x1400266f6`: `::RtlSetOwnerSecurityDescriptor( &AbsoluteSD, (PSID)Owner, 0)`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(
        __int64 a1,
        __int64 a2,
        void *a3,
        void *a4)
{
  NTSTATUS v6; // eax
  const char *v7; // rcx
  int v9; // ebx
  PVOID v10; // r8
  __int128 P; // [rsp+20h] [rbp-60h] BYREF
  __int64 v12; // [rsp+30h] [rbp-50h]
  const char *v13; // [rsp+38h] [rbp-48h]
  int v14; // [rsp+40h] [rbp-40h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v16; // [rsp+68h] [rbp-18h]

  v14 = 0;
  v16 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v6 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v6 < 0 )
  {
    v12 = 346;
    *(_QWORD *)&P = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    *((_QWORD *)&P + 1) = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
    v7 = "RtlCreateSecurityDescriptor( &AbsoluteSD, (1))";
LABEL_3:
    v13 = v7;
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
             &v14,
             &P,
             (unsigned int)v6);
  }
  v6 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, a3, 0);
  if ( v6 < 0 )
  {
    v12 = 355;
    *(_QWORD *)&P = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    *((_QWORD *)&P + 1) = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
    v7 = "::RtlSetOwnerSecurityDescriptor( &AbsoluteSD, (PSID)Owner, 0)";
    goto LABEL_3;
  }
  v6 = RtlSetGroupSecurityDescriptor(SecurityDescriptor, a4, 0);
  if ( v6 < 0 )
  {
    v12 = 363;
    *(_QWORD *)&P = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    *((_QWORD *)&P + 1) = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
    v7 = "::RtlSetGroupSecurityDescriptor( &AbsoluteSD, (PSID)Group, 0)";
    goto LABEL_3;
  }
  P = 0u;
  v9 = Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(&P, SecurityDescriptor);
  if ( v9 >= 0 )
  {
    v10 = ::P;
    *(_OWORD *)&::P = P;
    if ( v10 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
    return 0;
  }
  else
  {
    if ( (_QWORD)P )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)P);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x140026634  mov     [rsp-8+arg_0], rbx
0x140026639  mov     [rsp-8+arg_8], rdi
0x14002663e  push    rbp
0x14002663f  mov     rbp, rsp
0x140026642  sub     rsp, 80h
0x140026649  mov     rax, cs:__security_cookie
0x140026650  xor     rax, rsp
0x140026653  mov     [rbp+var_10], rax
0x140026657  xor     eax, eax
0x140026659  mov     [rbp+var_40], 0
0x140026660  xorps   xmm0, xmm0
0x140026663  mov     [rbp+var_18], rax
0x140026667  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14002666b  mov     rdi, r9
0x14002666e  mov     rbx, r8
0x140026671  lea     edx, [rax+1]; Revision
0x140026674  movups  [rbp+SecurityDescriptor], xmm0
0x140026678  movups  [rbp+var_28], xmm0
0x14002667c  call    cs:__imp_RtlCreateSecurityDescriptor
0x140026682  test    eax, eax
0x140026684  jns     short loc_1400266C4
0x140026686  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x14002668d  mov     [rbp+var_50], 15Ah
0x140026695  mov     qword ptr [rbp+P], rcx
0x140026699  lea     rcx, aWindowsWcpImpl_1; "Windows::WCP::Implementation::Rtl::Crea"...
0x1400266a0  mov     qword ptr [rbp+P+8], rcx
0x1400266a4  lea     rcx, aRtlcreatesecur; "RtlCreateSecurityDescriptor( &AbsoluteS"...
0x1400266ab  mov     [rbp+var_48], rcx
0x1400266af  lea     rdx, [rbp+P]
0x1400266b3  lea     rcx, [rbp+var_40]
0x1400266b7  mov     r8d, eax
0x1400266ba  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1400266bf  jmp     loc_1400267BB
0x1400266c4  xor     r8d, r8d; OwnerDefaulted
0x1400266c7  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400266cb  mov     rdx, rbx; Owner
0x1400266ce  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1400266d4  test    eax, eax
0x1400266d6  jns     short loc_1400266FF
0x1400266d8  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1400266df  mov     [rbp+var_50], 163h
0x1400266e7  mov     qword ptr [rbp+P], rcx
0x1400266eb  lea     rcx, aWindowsWcpImpl_1; "Windows::WCP::Implementation::Rtl::Crea"...
0x1400266f2  mov     qword ptr [rbp+P+8], rcx
0x1400266f6  lea     rcx, aRtlsetownersec; "::RtlSetOwnerSecurityDescriptor( &Absol"...
0x1400266fd  jmp     short loc_1400266AB
0x1400266ff  xor     r8d, r8d; GroupDefaulted
0x140026702  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140026706  mov     rdx, rdi; Group
0x140026709  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x14002670f  test    eax, eax
0x140026711  jns     short loc_14002673D
0x140026713  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x14002671a  mov     [rbp+var_50], 16Bh
0x140026722  mov     qword ptr [rbp+P], rcx
0x140026726  lea     rcx, aWindowsWcpImpl_1; "Windows::WCP::Implementation::Rtl::Crea"...
0x14002672d  mov     qword ptr [rbp+P+8], rcx
0x140026731  lea     rcx, aRtlsetgroupsec; "::RtlSetGroupSecurityDescriptor( &Absol"...
0x140026738  jmp     loc_1400266AB
0x14002673d  lea     rdx, [rbp+SecurityDescriptor]
0x140026741  mov     qword ptr [rbp+P], 0
0x140026749  lea     rcx, [rbp+P]
0x14002674d  mov     qword ptr [rbp+P+8], 0
0x140026755  call    ?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z; Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)
0x14002675a  mov     ebx, eax
0x14002675c  test    eax, eax
0x14002675e  jns     short loc_140026782
0x140026760  mov     r8, qword ptr [rbp+P]; P
0x140026764  test    r8, r8
0x140026767  jz      short loc_14002677E
0x140026769  mov     rcx, gs:60h
0x140026772  xor     edx, edx; Flags
0x140026774  mov     rcx, [rcx+30h]; HeapHandle
0x140026778  call    cs:__imp_RtlFreeHeap
0x14002677e  mov     eax, ebx
0x140026780  jmp     short loc_1400267BB
0x140026782  mov     rax, qword ptr [rbp+P]
0x140026786  mov     r8, qword ptr cs:P; P
0x14002678d  mov     qword ptr cs:P, rax
0x140026794  mov     rax, qword ptr [rbp+P+8]
0x140026798  mov     qword ptr cs:P+8, rax
0x14002679f  test    r8, r8
0x1400267a2  jz      short loc_1400267B9
0x1400267a4  mov     rcx, gs:60h
0x1400267ad  xor     edx, edx; Flags
0x1400267af  mov     rcx, [rcx+30h]; HeapHandle
0x1400267b3  call    cs:__imp_RtlFreeHeap
0x1400267b9  xor     eax, eax
0x1400267bb  mov     rcx, [rbp+var_10]
0x1400267bf  xor     rcx, rsp; StackCookie
0x1400267c2  call    __security_check_cookie
0x1400267c7  lea     r11, [rsp+80h+var_s0]
0x1400267cf  mov     rbx, [r11+10h]
0x1400267d3  mov     rdi, [r11+18h]
0x1400267d7  mov     rsp, r11
0x1400267da  pop     rbp
0x1400267db  retn
```
