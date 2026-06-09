# CDPComLoggedOnUserChangedInterop::NotifyUserLoggedOn(CDPComLoggedOnUserInformation *)

- ea: `0x180039f30`
- end: `0x180039f9f`
- name: `?NotifyUserLoggedOn@CDPComLoggedOnUserChangedInterop@@UEAAJPEAUCDPComLoggedOnUserInformation@@@Z`
- size: `111`
- prototype: `__int64 __fastcall(CDPComLoggedOnUserChangedInterop *this, struct CDPComLoggedOnUserInformation *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800130ec`
- `0x180039f04`
- `0x180039f30`
- `0x18006a010`

## import_xrefs

- `cdp!CDPCreateLoggedOnUserChangedNotifier` at `0x180039f4b`
- `cdp!CDPCreateLoggedOnUserChangedNotifier` at `0x180039f4b`

## string_xrefs

- `0x180039f5c`: `.\cdpcomloggedonuserchanged.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDPComLoggedOnUserChangedInterop::NotifyUserLoggedOn(
        CDPComLoggedOnUserChangedInterop *this,
        struct CDPComLoggedOnUserInformation *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  v3 = CDPCreateLoggedOnUserChangedNotifier(&v8);
  v4 = v3;
  if ( v3 >= 0 )
    v4 = (*(__int64 (__fastcall **)(__int64, struct CDPComLoggedOnUserInformation *))(*(_QWORD *)v8 + 24LL))(v8, a2);
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE,
      (unsigned int)".\\cdpcomloggedonuserchanged.cpp",
      (const char *)(unsigned int)v3,
      v6);
  wil::com_ptr_t<ICDPLoggedOnUserChangedNotifier,wil::err_exception_policy>::~com_ptr_t<ICDPLoggedOnUserChangedNotifier,wil::err_exception_policy>(&v8);
  return v4;
}

```

## disassembly

```asm
0x180039f30  mov     [rsp+arg_0], rbx
0x180039f35  push    rdi; int
0x180039f36  sub     rsp, 20h
0x180039f3a  lea     rcx, [rsp+28h+arg_10]
0x180039f3f  mov     [rsp+28h+arg_10], 0
0x180039f48  mov     rdi, rdx
0x180039f4b  call    cs:__imp_CDPCreateLoggedOnUserChangedNotifier
0x180039f51  mov     ebx, eax
0x180039f53  test    eax, eax
0x180039f55  jns     short loc_180039F72
0x180039f57  mov     rcx, [rsp+28h]; this
0x180039f5c  lea     r8, aCdpcomloggedon; ".\\cdpcomloggedonuserchanged.cpp"
0x180039f63  mov     r9d, eax; char *
0x180039f66  mov     edx, 0Eh; void *
0x180039f6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039f70  jmp     short loc_180039F88
0x180039f72  mov     rcx, [rsp+28h+arg_10]
0x180039f77  mov     rdx, rdi
0x180039f7a  mov     rax, [rcx]
0x180039f7d  mov     rax, [rax+18h]
0x180039f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f86  mov     ebx, eax
0x180039f88  lea     rcx, [rsp+28h+arg_10]
0x180039f8d  call    ??1?$com_ptr_t@UICDPLoggedOnUserChangedNotifier@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICDPLoggedOnUserChangedNotifier,wil::err_exception_policy>::~com_ptr_t<ICDPLoggedOnUserChangedNotifier,wil::err_exception_policy>(void)
0x180039f92  mov     eax, ebx
0x180039f94  mov     rbx, [rsp+28h+arg_0]
0x180039f99  add     rsp, 20h
0x180039f9d  pop     rdi
0x180039f9e  retn
```
