# Windows::Auto<_SID>::Assign(_SID const *)

- ea: `0x1801160a4`
- end: `0x18011621b`
- name: `?Assign@?$Auto@U_SID@@@Windows@@QEAAJPEBU_SID@@@Z`
- size: `375`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180116538`
- `0x180264fc0`

## callees

- `0x1800aa134`
- `0x1800aa1a4`
- `0x1800aa1d4`
- `0x1800eb920`
- `0x1800ef360`
- `0x1801160a4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180116152`
- `ntdll!RtlAllocateHeap` at `0x180116152`
- `ntdll!RtlLengthSid` at `0x180116132`
- `ntdll!RtlLengthSid` at `0x180116132`
- `ntdll!RtlCopySid` at `0x1801161a6`
- `ntdll!RtlCopySid` at `0x1801161a6`
- `ntdll!RtlValidSid` at `0x1801160e4`
- `ntdll!RtlValidSid` at `0x1801160e4`

## string_xrefs

- `0x1801160f4`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180116166`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801161b9`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18011618c`: `m_pSID`
- `0x18011611a`: `pSid == 0 || ::RtlValidSid(pSid)`
- `0x18011610b`: `Windows::Auto<struct _SID>::Assign`
- `0x18011617d`: `Windows::Auto<struct _SID>::Assign`
- `0x1801161d0`: `Windows::Auto<struct _SID>::Assign`
- `0x1801161df`: `::RtlCopySid( ulLength, m_pSID, pSid)`

## pseudocode

```c
__int64 __fastcall Windows::Auto<_SID>::Assign(_QWORD *a1, void *a2)
{
  bool v2; // zf
  ULONG v6; // esi
  PVOID Heap; // rax
  NTSTATUS v8; // eax
  const char *v9; // [rsp+20h] [rbp-30h] BYREF
  const char *v10; // [rsp+28h] [rbp-28h]
  __int64 v11; // [rsp+30h] [rbp-20h]
  const char *v12; // [rsp+38h] [rbp-18h]
  int v13; // [rsp+40h] [rbp-10h] BYREF

  v2 = *a1 == 0;
  v13 = 0;
  if ( !v2 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18011621ALL);
  }
  if ( !a2 )
    return 0;
  if ( !RtlValidSid(a2) )
  {
    v11 = 904;
    v9 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v10 = "Windows::Auto<struct _SID>::Assign";
    v12 = "pSid == 0 || ::RtlValidSid(pSid)";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v13,
             &v9);
  }
  v6 = RtlLengthSid(a2);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  *a1 = Heap;
  if ( !Heap )
  {
    v11 = 911;
    v9 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v10 = "Windows::Auto<struct _SID>::Assign";
    v12 = "m_pSID";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
             &v13,
             &v9);
  }
  v8 = RtlCopySid(v6, Heap, a2);
  if ( v8 >= 0 )
    return 0;
  v11 = 916;
  v9 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
  v10 = "Windows::Auto<struct _SID>::Assign";
  v12 = "::RtlCopySid( ulLength, m_pSID, pSid)";
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
           &v13,
           &v9,
           (unsigned int)v8);
}

```

## disassembly

```asm
0x1801160a4  mov     [rsp-18h+arg_10], rbx
0x1801160a9  push    rbp
0x1801160aa  push    rsi
0x1801160ab  push    rdi
0x1801160ac  mov     rbp, rsp
0x1801160af  sub     rsp, 50h
0x1801160b3  mov     rax, cs:__security_cookie
0x1801160ba  xor     rax, rsp
0x1801160bd  mov     [rbp+var_8], rax
0x1801160c1  cmp     qword ptr [rcx], 0
0x1801160c5  mov     rbx, rdx
0x1801160c8  mov     rdi, rcx
0x1801160cb  mov     [rbp+var_10], 0
0x1801160d2  jnz     loc_180116210
0x1801160d8  test    rdx, rdx
0x1801160db  jz      loc_1801161F1
0x1801160e1  mov     rcx, rdx; Sid
0x1801160e4  call    cs:__imp_RtlValidSid
0x1801160eb  nop     dword ptr [rax+rax+00h]
0x1801160f0  test    al, al
0x1801160f2  jnz     short loc_18011612F
0x1801160f4  lea     rax, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801160fb  mov     [rbp+var_20], 388h
0x180116103  mov     [rbp+var_30], rax
0x180116107  lea     rdx, [rbp+var_30]
0x18011610b  lea     rax, aWindowsAutoStr; "Windows::Auto<struct _SID>::Assign"
0x180116112  mov     [rbp+var_28], rax
0x180116116  lea     rcx, [rbp+var_10]
0x18011611a  lea     rax, aPsid0Rtlvalids; "pSid == 0 || ::RtlValidSid(pSid)"
0x180116121  mov     [rbp+var_18], rax
0x180116125  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18011612a  jmp     loc_1801161F3
0x18011612f  mov     rcx, rbx; Sid
0x180116132  call    cs:__imp_RtlLengthSid
0x180116139  nop     dword ptr [rax+rax+00h]
0x18011613e  mov     rcx, gs:60h
0x180116147  xor     edx, edx; Flags
0x180116149  mov     r8d, eax; Size
0x18011614c  mov     esi, eax
0x18011614e  mov     rcx, [rcx+30h]; HeapHandle
0x180116152  call    cs:__imp_RtlAllocateHeap
0x180116159  nop     dword ptr [rax+rax+00h]
0x18011615e  mov     [rdi], rax
0x180116161  test    rax, rax
0x180116164  jnz     short loc_18011619E
0x180116166  lea     rax, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18011616d  mov     [rbp+var_20], 38Fh
0x180116175  mov     [rbp+var_30], rax
0x180116179  lea     rdx, [rbp+var_30]
0x18011617d  lea     rax, aWindowsAutoStr; "Windows::Auto<struct _SID>::Assign"
0x180116184  mov     [rbp+var_28], rax
0x180116188  lea     rcx, [rbp+var_10]
0x18011618c  lea     rax, aMPsid; "m_pSID"
0x180116193  mov     [rbp+var_18], rax
0x180116197  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18011619c  jmp     short loc_1801161F3
0x18011619e  mov     r8, rbx; SourceSid
0x1801161a1  mov     rdx, rax; DestinationSid
0x1801161a4  mov     ecx, esi; DestinationSidLength
0x1801161a6  call    cs:__imp_RtlCopySid
0x1801161ad  nop     dword ptr [rax+rax+00h]
0x1801161b2  mov     r8d, eax
0x1801161b5  test    eax, eax
0x1801161b7  jns     short loc_1801161F1
0x1801161b9  lea     rax, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801161c0  mov     [rbp+var_20], 394h
0x1801161c8  mov     [rbp+var_30], rax
0x1801161cc  lea     rdx, [rbp+var_30]
0x1801161d0  lea     rax, aWindowsAutoStr; "Windows::Auto<struct _SID>::Assign"
0x1801161d7  mov     [rbp+var_28], rax
0x1801161db  lea     rcx, [rbp+var_10]
0x1801161df  lea     rax, aRtlcopysidUlle; "::RtlCopySid( ulLength, m_pSID, pSid)"
0x1801161e6  mov     [rbp+var_18], rax
0x1801161ea  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1801161ef  jmp     short loc_1801161F3
0x1801161f1  xor     eax, eax
0x1801161f3  mov     rcx, [rbp+var_8]
0x1801161f7  xor     rcx, rsp; StackCookie
0x1801161fa  call    __security_check_cookie
0x1801161ff  mov     rbx, [rsp+50h+arg_10]
0x180116207  add     rsp, 50h
0x18011620b  pop     rdi
0x18011620c  pop     rsi
0x18011620d  pop     rbp
0x18011620e  retn
0x180116210  mov     ecx, 0C00000E5h; int
0x180116215  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
