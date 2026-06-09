# Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(ushort,ulong,_SID const *,_SID const *,_ACL const *,_ACL const *,Windows::Auto<_SECURITY_DESCRIPTOR> *)

- ea: `0x140026840`
- end: `0x1400269e8`
- name: `?CreateSecurityDescriptorFromParts@Rtl@Implementation@WCP@Windows@@YAJGKPEBU_SID@@0PEBU_ACL@@1PEAV?$Auto@U_SECURITY_DESCRIPTOR@@@4@@Z`
- size: `424`
- prototype: `__int64 __fastcall(__int64, __int64, void *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140025f24`

## callees

- `0x140002310`
- `0x140006b54`
- `0x140026488`
- `0x140026840`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140026984`
- `ntdll!RtlFreeHeap` at `0x1400269bf`
- `ntdll!RtlFreeHeap` at `0x140026984`
- `ntdll!RtlFreeHeap` at `0x1400269bf`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x140026915`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x140026915`
- `ntdll!RtlCreateSecurityDescriptor` at `0x140026888`
- `ntdll!RtlCreateSecurityDescriptor` at `0x140026888`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1400268da`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1400268da`

## string_xrefs

- `0x140026892`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1400268e4`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x14002691f`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1400268a5`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x1400268f7`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x140026932`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x1400268b0`: `RtlCreateSecurityDescriptor( &AbsoluteSD, (1))`
- `0x140026902`: `::RtlSetOwnerSecurityDescriptor( &AbsoluteSD, (PSID)Owner, 0)`
- `0x14002693d`: `::RtlSetGroupSecurityDescriptor( &AbsoluteSD, (PSID)Group, 0)`

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
0x140026840  mov     [rsp-8+arg_0], rbx
0x140026845  mov     [rsp-8+arg_8], rdi
0x14002684a  push    rbp
0x14002684b  mov     rbp, rsp
0x14002684e  sub     rsp, 80h
0x140026855  mov     rax, cs:__security_cookie
0x14002685c  xor     rax, rsp
0x14002685f  mov     [rbp+var_10], rax
0x140026863  xor     eax, eax
0x140026865  mov     [rbp+var_40], 0
0x14002686c  xorps   xmm0, xmm0
0x14002686f  mov     [rbp+var_18], rax
0x140026873  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140026877  mov     rdi, r9
0x14002687a  mov     rbx, r8
0x14002687d  lea     edx, [rax+1]; Revision
0x140026880  movups  [rbp+SecurityDescriptor], xmm0
0x140026884  movups  [rbp+var_28], xmm0
0x140026888  call    cs:__imp_RtlCreateSecurityDescriptor
0x14002688e  test    eax, eax
0x140026890  jns     short loc_1400268D0
0x140026892  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140026899  mov     [rbp+var_50], 15Ah
0x1400268a1  mov     qword ptr [rbp+P], rcx
0x1400268a5  lea     rcx, aWindowsWcpImpl_1; "Windows::WCP::Implementation::Rtl::Crea"...
0x1400268ac  mov     qword ptr [rbp+P+8], rcx
0x1400268b0  lea     rcx, aRtlcreatesecur; "RtlCreateSecurityDescriptor( &AbsoluteS"...
0x1400268b7  mov     [rbp+var_48], rcx
0x1400268bb  lea     rdx, [rbp+P]
0x1400268bf  lea     rcx, [rbp+var_40]
0x1400268c3  mov     r8d, eax
0x1400268c6  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1400268cb  jmp     loc_1400269C7
0x1400268d0  xor     r8d, r8d; OwnerDefaulted
0x1400268d3  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400268d7  mov     rdx, rbx; Owner
0x1400268da  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1400268e0  test    eax, eax
0x1400268e2  jns     short loc_14002690B
0x1400268e4  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1400268eb  mov     [rbp+var_50], 163h
0x1400268f3  mov     qword ptr [rbp+P], rcx
0x1400268f7  lea     rcx, aWindowsWcpImpl_1; "Windows::WCP::Implementation::Rtl::Crea"...
0x1400268fe  mov     qword ptr [rbp+P+8], rcx
0x140026902  lea     rcx, aRtlsetownersec; "::RtlSetOwnerSecurityDescriptor( &Absol"...
0x140026909  jmp     short loc_1400268B7
0x14002690b  xor     r8d, r8d; GroupDefaulted
0x14002690e  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140026912  mov     rdx, rdi; Group
0x140026915  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x14002691b  test    eax, eax
0x14002691d  jns     short loc_140026949
0x14002691f  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140026926  mov     [rbp+var_50], 16Bh
0x14002692e  mov     qword ptr [rbp+P], rcx
0x140026932  lea     rcx, aWindowsWcpImpl_1; "Windows::WCP::Implementation::Rtl::Crea"...
0x140026939  mov     qword ptr [rbp+P+8], rcx
0x14002693d  lea     rcx, aRtlsetgroupsec; "::RtlSetGroupSecurityDescriptor( &Absol"...
0x140026944  jmp     loc_1400268B7
0x140026949  lea     rdx, [rbp+SecurityDescriptor]
0x14002694d  mov     qword ptr [rbp+P], 0
0x140026955  lea     rcx, [rbp+P]
0x140026959  mov     qword ptr [rbp+P+8], 0
0x140026961  call    ?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z; Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)
0x140026966  mov     ebx, eax
0x140026968  test    eax, eax
0x14002696a  jns     short loc_14002698E
0x14002696c  mov     r8, qword ptr [rbp+P]; P
0x140026970  test    r8, r8
0x140026973  jz      short loc_14002698A
0x140026975  mov     rcx, gs:60h
0x14002697e  xor     edx, edx; Flags
0x140026980  mov     rcx, [rcx+30h]; HeapHandle
0x140026984  call    cs:__imp_RtlFreeHeap
0x14002698a  mov     eax, ebx
0x14002698c  jmp     short loc_1400269C7
0x14002698e  mov     rax, qword ptr [rbp+P]
0x140026992  mov     r8, qword ptr cs:P; P
0x140026999  mov     qword ptr cs:P, rax
0x1400269a0  mov     rax, qword ptr [rbp+P+8]
0x1400269a4  mov     qword ptr cs:P+8, rax
0x1400269ab  test    r8, r8
0x1400269ae  jz      short loc_1400269C5
0x1400269b0  mov     rcx, gs:60h
0x1400269b9  xor     edx, edx; Flags
0x1400269bb  mov     rcx, [rcx+30h]; HeapHandle
0x1400269bf  call    cs:__imp_RtlFreeHeap
0x1400269c5  xor     eax, eax
0x1400269c7  mov     rcx, [rbp+var_10]
0x1400269cb  xor     rcx, rsp; StackCookie
0x1400269ce  call    __security_check_cookie
0x1400269d3  lea     r11, [rsp+80h+var_s0]
0x1400269db  mov     rbx, [r11+10h]
0x1400269df  mov     rdi, [r11+18h]
0x1400269e3  mov     rsp, r11
0x1400269e6  pop     rbp
0x1400269e7  retn
```
