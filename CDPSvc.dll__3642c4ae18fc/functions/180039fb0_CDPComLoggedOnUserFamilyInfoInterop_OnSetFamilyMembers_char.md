# CDPComLoggedOnUserFamilyInfoInterop::OnSetFamilyMembers(char *)

- ea: `0x180039fb0`
- end: `0x18003a01f`
- name: `?OnSetFamilyMembers@CDPComLoggedOnUserFamilyInfoInterop@@UEAAJPEAD@Z`
- size: `111`
- prototype: `__int64 __fastcall(CDPComLoggedOnUserFamilyInfoInterop *this, char *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800130ec`
- `0x180039f04`
- `0x180039fb0`
- `0x18006a010`

## import_xrefs

- `cdp!CDPCreateLoggedOnUserFamilyChangedNotifier` at `0x180039fcb`
- `cdp!CDPCreateLoggedOnUserFamilyChangedNotifier` at `0x180039fcb`

## string_xrefs

- `0x180039fdc`: `.\cdpcomloggedonuserfamilyinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDPComLoggedOnUserFamilyInfoInterop::OnSetFamilyMembers(
        CDPComLoggedOnUserFamilyInfoInterop *this,
        char *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  v3 = CDPCreateLoggedOnUserFamilyChangedNotifier(&v8);
  v4 = v3;
  if ( v3 >= 0 )
    v4 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v8 + 24LL))(v8, a2);
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF,
      (unsigned int)".\\cdpcomloggedonuserfamilyinfo.cpp",
      (const char *)(unsigned int)v3,
      v6);
  wil::com_ptr_t<ICDPLoggedOnUserChangedNotifier,wil::err_exception_policy>::~com_ptr_t<ICDPLoggedOnUserChangedNotifier,wil::err_exception_policy>(&v8);
  return v4;
}

```

## disassembly

```asm
0x180039fb0  mov     [rsp+arg_0], rbx
0x180039fb5  push    rdi; int
0x180039fb6  sub     rsp, 20h
0x180039fba  lea     rcx, [rsp+28h+arg_10]
0x180039fbf  mov     [rsp+28h+arg_10], 0
0x180039fc8  mov     rdi, rdx
0x180039fcb  call    cs:__imp_CDPCreateLoggedOnUserFamilyChangedNotifier
0x180039fd1  mov     ebx, eax
0x180039fd3  test    eax, eax
0x180039fd5  jns     short loc_180039FF2
0x180039fd7  mov     rcx, [rsp+28h]; this
0x180039fdc  lea     r8, aCdpcomloggedon_0; ".\\cdpcomloggedonuserfamilyinfo.cpp"
0x180039fe3  mov     r9d, eax; char *
0x180039fe6  mov     edx, 0Fh; void *
0x180039feb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039ff0  jmp     short loc_18003A008
0x180039ff2  mov     rcx, [rsp+28h+arg_10]
0x180039ff7  mov     rdx, rdi
0x180039ffa  mov     rax, [rcx]
0x180039ffd  mov     rax, [rax+18h]
0x18003a001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a006  mov     ebx, eax
0x18003a008  lea     rcx, [rsp+28h+arg_10]
0x18003a00d  call    ??1?$com_ptr_t@UICDPLoggedOnUserChangedNotifier@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICDPLoggedOnUserChangedNotifier,wil::err_exception_policy>::~com_ptr_t<ICDPLoggedOnUserChangedNotifier,wil::err_exception_policy>(void)
0x18003a012  mov     eax, ebx
0x18003a014  mov     rbx, [rsp+28h+arg_0]
0x18003a019  add     rsp, 20h
0x18003a01d  pop     rdi
0x18003a01e  retn
```
