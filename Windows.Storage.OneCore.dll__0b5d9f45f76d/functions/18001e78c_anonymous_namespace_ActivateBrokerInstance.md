# _anonymous_namespace_::ActivateBrokerInstance

- ea: `0x18001e78c`
- end: `0x18001e823`
- name: `_anonymous_namespace_::ActivateBrokerInstance`
- size: `151`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `11`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c8cc`
- `0x18001cb1c`
- `0x18001cd30`
- `0x18001cffc`
- `0x18001d224`
- `0x18001d438`
- `0x18001d790`
- `0x18001daa0`
- `0x18001dd30`
- `0x18001dfc0`
- `0x18001e210`

## callees

- `0x180012d88`
- `0x18001e78c`
- `0x18001ed04`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001e7e4`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001e7e4`

## string_xrefs

- `0x18001e7aa`: `Calling brokered APIs while impersonating is not allowed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::ActivateBrokerInstance(__int64 a1)
{
  int v3; // ebx
  const char *v4; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64); // [rsp+48h] [rbp+10h] BYREF

  if ( NtCurrentTeb()->IsImpersonating )
    return wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x45,
             (unsigned int)"onecore\\base\\windows.storage\\src\\win32proxy.cpp",
             (const char *)0x10DD,
             (unsigned int)"Calling brokered APIs while impersonating is not allowed",
             v4);
  v6 = 0;
  v3 = RoActivateInstance(qword_180033878, &v6);
  if ( v3 >= 0 )
    v3 = (**v6)(v6, &GUID_e5305f56_8174_43c2_a911_fdb7972e8709, a1);
  wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(&v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001e78c  mov     [rsp+arg_0], rbx
0x18001e791  push    rdi
0x18001e792  sub     rsp, 30h
0x18001e796  mov     rdi, rcx
0x18001e799  mov     eax, gs:179Ch
0x18001e7a1  test    eax, eax
0x18001e7a3  jz      short loc_18001E7CF
0x18001e7a5  mov     rcx, [rsp+38h]; this
0x18001e7aa  lea     rax, aCallingBrokere; "Calling brokered APIs while impersonati"...
0x18001e7b1  mov     qword ptr [rsp+38h+var_18], rax; unsigned int
0x18001e7b6  mov     r9d, 10DDh; char *
0x18001e7bc  lea     r8, aOnecoreBaseWin_4; "onecore\\base\\windows.storage\\src\\wi"...
0x18001e7c3  mov     edx, 45h ; 'E'; void *
0x18001e7c8  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001e7cd  jmp     short loc_18001E818
0x18001e7cf  mov     [rsp+38h+arg_8], 0
0x18001e7d8  lea     rdx, [rsp+38h+arg_8]
0x18001e7dd  mov     rcx, cs:qword_180033878
0x18001e7e4  call    cs:__imp_RoActivateInstance
0x18001e7ea  mov     ebx, eax
0x18001e7ec  test    eax, eax
0x18001e7ee  js      short loc_18001E80C
0x18001e7f0  mov     rcx, [rsp+38h+arg_8]
0x18001e7f5  mov     rax, [rcx]
0x18001e7f8  mov     r8, rdi
0x18001e7fb  lea     rdx, _GUID_e5305f56_8174_43c2_a911_fdb7972e8709
0x18001e802  mov     rax, [rax]
0x18001e805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e80a  mov     ebx, eax
0x18001e80c  lea     rcx, [rsp+38h+arg_8]
0x18001e811  call    ??1?$com_ptr_t@UIInspectable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(void)
0x18001e816  mov     eax, ebx
0x18001e818  mov     rbx, [rsp+38h+arg_0]
0x18001e81d  add     rsp, 30h
0x18001e821  pop     rdi
0x18001e822  retn
```
