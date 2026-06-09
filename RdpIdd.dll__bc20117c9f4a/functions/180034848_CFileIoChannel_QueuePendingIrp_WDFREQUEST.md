# CFileIoChannel::QueuePendingIrp(WDFREQUEST__ *)

- ea: `0x180034848`
- end: `0x1800348fd`
- name: `?QueuePendingIrp@CFileIoChannel@@QEAAXPEAUWDFREQUEST__@@@Z`
- size: `181`
- prototype: `void __fastcall(CFileIoChannel *__hidden this, struct WDFREQUEST__ *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180032398`
- `0x1800342b0`

## callees

- `0x180010ff8`
- `0x180011584`
- `0x180034848`
- `0x18003f010`

## string_xrefs

- `0x180034893`: `Failed to queue request to pending Read queue`
- `0x1800348dc`: `Completing Read request with a failure status`

## pseudocode

```c
void __fastcall CFileIoChannel::QueuePendingIrp(CFileIoChannel *this, struct WDFREQUEST__ *a2)
{
  const char *v3; // rbx
  const char *v4; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  LODWORD(v3) = -1073741248;
  if ( !*((_QWORD *)this + 25)
    || (v3 = (const char *)(*(unsigned int (__fastcall **)(__int64))(WdfFunctions_02025 + 1392))(WdfDriverGlobals),
        wil::details::in1diag3::Log_IfNtStatusFailedMsg(
          retaddr,
          (void *)0x4C0,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
          v3,
          (int)"Failed to queue request to pending Read queue",
          v4),
        (int)v3 < 0) )
  {
    (*(void (__fastcall **)(__int64, struct WDFREQUEST__ *, _QWORD))(WdfFunctions_02025 + 1304))(
      WdfDriverGlobals,
      a2,
      (unsigned int)v3);
    wil::details::in1diag3::Throw_NtStatusMsg(
      retaddr,
      (void *)0x4C5,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
      (const char *)(unsigned int)v3,
      (int)"Completing Read request with a failure status",
      v4);
  }
}

```

## disassembly

```asm
0x180034848  mov     [rsp+arg_0], rbx
0x18003484d  push    rdi
0x18003484e  sub     rsp, 30h
0x180034852  mov     r8, [rcx+0C8h]
0x180034859  mov     rdi, rdx
0x18003485c  mov     ebx, 0C0000240h
0x180034861  test    r8, r8
0x180034864  jz      short loc_1800348B7
0x180034866  mov     rax, cs:WdfFunctions_02025
0x18003486d  mov     rcx, cs:WdfDriverGlobals
0x180034874  mov     rax, [rax+570h]
0x18003487b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034880  mov     rcx, [rsp+38h]; this
0x180034885  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18003488c  mov     ebx, eax
0x18003488e  mov     edx, 4C0h; void *
0x180034893  lea     rax, aFailedToQueueR; "Failed to queue request to pending Read"...
0x18003489a  mov     r9d, ebx; char *
0x18003489d  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800348a2  call    ?Log_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800348a7  test    ebx, ebx
0x1800348a9  js      short loc_1800348B7
0x1800348ab  mov     rbx, [rsp+38h+arg_0]
0x1800348b0  add     rsp, 30h
0x1800348b4  pop     rdi
0x1800348b5  retn
0x1800348b7  mov     rcx, cs:WdfFunctions_02025
0x1800348be  mov     r8d, ebx
0x1800348c1  mov     rdx, rdi
0x1800348c4  mov     rax, [rcx+518h]
0x1800348cb  mov     rcx, cs:WdfDriverGlobals
0x1800348d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348d7  mov     rcx, [rsp+38h]; this
0x1800348dc  lea     rax, aCompletingRead; "Completing Read request with a failure "...
0x1800348e3  mov     r9d, ebx; char *
0x1800348e6  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800348eb  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800348f2  mov     edx, 4C5h; void *
0x1800348f7  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
```
