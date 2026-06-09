# Windows::Auto<_SID>::Assign(_SID const *)

- ea: `0x18004ef0c`
- end: `0x18004f082`
- name: `?Assign@?$Auto@U_SID@@@Windows@@QEAAJPEBU_SID@@@Z`
- size: `374`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004f6b0`
- `0x1801781a8`

## callees

- `0x18000aedc`
- `0x1800497c0`
- `0x18004ef0c`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18004ef93`
- `ntdll!RtlLengthSid` at `0x18004ef93`
- `ntdll!RtlAllocateHeap` at `0x18004efb3`
- `ntdll!RtlAllocateHeap` at `0x18004efb3`
- `ntdll!RtlCopySid` at `0x18004f015`
- `ntdll!RtlCopySid` at `0x18004f015`
- `ntdll!RtlValidSid` at `0x18004ef37`
- `ntdll!RtlValidSid` at `0x18004ef37`

## string_xrefs

- `0x18004ef47`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004efc7`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004f027`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004eff6`: `m_pSID`
- `0x18004f053`: `::RtlCopySid( ulLength, m_pSID, pSid)`
- `0x18004ef61`: `Windows::Auto<struct _SID>::Assign`
- `0x18004efe1`: `Windows::Auto<struct _SID>::Assign`
- `0x18004f041`: `Windows::Auto<struct _SID>::Assign`
- `0x18004ef76`: `pSid == 0 || ::RtlValidSid(pSid)`

## pseudocode

```c
__int64 __fastcall Windows::Auto<_SID>::Assign(_QWORD *a1, void *a2)
{
  ULONG v5; // esi
  PVOID Heap; // rax
  NTSTATUS v7; // eax
  unsigned int v8; // ebx
  const char *v9; // [rsp+20h] [rbp-20h] BYREF
  const char *v10; // [rsp+28h] [rbp-18h]
  __int64 v11; // [rsp+30h] [rbp-10h]
  const char *v12; // [rsp+38h] [rbp-8h]

  if ( *a1 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18004F081LL);
  }
  if ( !a2 )
    return 0;
  if ( !RtlValidSid(a2) )
  {
    v11 = 904;
    v9 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v10 = "Windows::Auto<struct _SID>::Assign";
    v12 = "pSid == 0 || ::RtlValidSid(pSid)";
    RtlReportErrorOrigination(&v9, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  v5 = RtlLengthSid(a2);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  *a1 = Heap;
  if ( !Heap )
  {
    v11 = 911;
    v9 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v10 = "Windows::Auto<struct _SID>::Assign";
    v12 = "m_pSID";
    RtlReportErrorOrigination(&v9, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
    return 3221225495LL;
  }
  v7 = RtlCopySid(v5, Heap, a2);
  v8 = v7;
  if ( v7 >= 0 )
    return 0;
  v11 = 916;
  v9 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
  v10 = "Windows::Auto<struct _SID>::Assign";
  v12 = "::RtlCopySid( ulLength, m_pSID, pSid)";
  RtlReportErrorOrigination(&v9, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v7);
  return v8;
}

```

## disassembly

```asm
0x18004ef0c  mov     [rsp-18h+arg_10], rbx
0x18004ef11  push    rbp
0x18004ef12  push    rsi
0x18004ef13  push    rdi
0x18004ef14  mov     rbp, rsp
0x18004ef17  sub     rsp, 40h
0x18004ef1b  cmp     qword ptr [rcx], 0
0x18004ef1f  mov     rbx, rdx
0x18004ef22  mov     rdi, rcx
0x18004ef25  jnz     loc_18004F077
0x18004ef2b  test    rdx, rdx
0x18004ef2e  jz      loc_18004F067
0x18004ef34  mov     rcx, rdx; Sid
0x18004ef37  call    cs:__imp_RtlValidSid
0x18004ef3e  nop     dword ptr [rax+rax+00h]
0x18004ef43  test    al, al
0x18004ef45  jnz     short loc_18004EF90
0x18004ef47  lea     rax, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004ef4e  mov     [rbp+var_10], 388h
0x18004ef56  mov     [rbp+var_20], rax
0x18004ef5a  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18004ef61  lea     rax, aWindowsAutoStr; "Windows::Auto<struct _SID>::Assign"
0x18004ef68  mov     r8d, 0C000000Dh
0x18004ef6e  mov     [rbp+var_18], rax
0x18004ef72  lea     rcx, [rbp+var_20]
0x18004ef76  lea     rax, aPsid0Rtlvalids; "pSid == 0 || ::RtlValidSid(pSid)"
0x18004ef7d  mov     [rbp+var_8], rax
0x18004ef81  call    RtlReportErrorOrigination
0x18004ef86  mov     eax, 0C000000Dh
0x18004ef8b  jmp     loc_18004F069
0x18004ef90  mov     rcx, rbx; Sid
0x18004ef93  call    cs:__imp_RtlLengthSid
0x18004ef9a  nop     dword ptr [rax+rax+00h]
0x18004ef9f  mov     rcx, gs:60h
0x18004efa8  xor     edx, edx; Flags
0x18004efaa  mov     r8d, eax; Size
0x18004efad  mov     esi, eax
0x18004efaf  mov     rcx, [rcx+30h]; HeapHandle
0x18004efb3  call    cs:__imp_RtlAllocateHeap
0x18004efba  nop     dword ptr [rax+rax+00h]
0x18004efbf  mov     [rdi], rax
0x18004efc2  test    rax, rax
0x18004efc5  jnz     short loc_18004F00D
0x18004efc7  lea     rax, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004efce  mov     [rbp+var_10], 38Fh
0x18004efd6  mov     [rbp+var_20], rax
0x18004efda  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18004efe1  lea     rax, aWindowsAutoStr; "Windows::Auto<struct _SID>::Assign"
0x18004efe8  mov     r8d, 0C0000017h
0x18004efee  mov     [rbp+var_18], rax
0x18004eff2  lea     rcx, [rbp+var_20]
0x18004eff6  lea     rax, aMPsid; "m_pSID"
0x18004effd  mov     [rbp+var_8], rax
0x18004f001  call    RtlReportErrorOrigination
0x18004f006  mov     eax, 0C0000017h
0x18004f00b  jmp     short loc_18004F069
0x18004f00d  mov     r8, rbx; SourceSid
0x18004f010  mov     rdx, rax; DestinationSid
0x18004f013  mov     ecx, esi; DestinationSidLength
0x18004f015  call    cs:__imp_RtlCopySid
0x18004f01c  nop     dword ptr [rax+rax+00h]
0x18004f021  mov     ebx, eax
0x18004f023  test    eax, eax
0x18004f025  jns     short loc_18004F067
0x18004f027  lea     rax, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004f02e  mov     [rbp+var_10], 394h
0x18004f036  mov     [rbp+var_20], rax
0x18004f03a  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18004f041  lea     rax, aWindowsAutoStr; "Windows::Auto<struct _SID>::Assign"
0x18004f048  mov     r8d, ebx
0x18004f04b  mov     [rbp+var_18], rax
0x18004f04f  lea     rcx, [rbp+var_20]
0x18004f053  lea     rax, aRtlcopysidUlle; "::RtlCopySid( ulLength, m_pSID, pSid)"
0x18004f05a  mov     [rbp+var_8], rax
0x18004f05e  call    RtlReportErrorOrigination
0x18004f063  mov     eax, ebx
0x18004f065  jmp     short loc_18004F069
0x18004f067  xor     eax, eax
0x18004f069  mov     rbx, [rsp+40h+arg_10]
0x18004f06e  add     rsp, 40h
0x18004f072  pop     rdi
0x18004f073  pop     rsi
0x18004f074  pop     rbp
0x18004f075  retn
0x18004f077  mov     ecx, 0C00000E5h; int
0x18004f07c  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
