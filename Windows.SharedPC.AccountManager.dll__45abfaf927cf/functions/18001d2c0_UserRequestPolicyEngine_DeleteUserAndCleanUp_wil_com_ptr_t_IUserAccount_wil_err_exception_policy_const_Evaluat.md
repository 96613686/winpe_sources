# UserRequestPolicyEngine::DeleteUserAndCleanUp(wil::com_ptr_t<IUserAccount,wil::err_exception_policy> const &,EvaluationTrigger,HKEY__ * const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001d2c0`
- end: `0x18001d30f`
- name: `?DeleteUserAndCleanUp@UserRequestPolicyEngine@@AEAAXAEBV?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@W4EvaluationTrigger@@AEBQEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `79`
- prototype: `char __fastcall(_QWORD **, __int64 *, int, HKEY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d480`

## callees

- `0x18000ccf4`
- `0x180013dcc`
- `0x18001d110`
- `0x18001d2c0`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001d2e5`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001d2e5`

## string_xrefs

- `0x18001d2f4`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\userrequestpolicyengine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall UserRequestPolicyEngine::DeleteUserAndCleanUp(_QWORD **a1, __int64 *a2, int a3, HKEY *a4)
{
  unsigned int v5; // eax
  const WCHAR *v6; // rax
  unsigned int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  LOBYTE(v5) = BasePolicyEngine::DeleteUserAccount(a1, *a2, a3);
  if ( (_BYTE)v5 )
  {
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v5 = RegDeleteKeyW(*a4, v6);
    if ( v5 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x20,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\userrequestpolicyengine.cpp",
        (const char *)v5,
        v8);
  }
  return v5;
}

```

## disassembly

```asm
0x18001d2c0  push    rbx; unsigned int
0x18001d2c2  sub     rsp, 20h
0x18001d2c6  mov     rdx, [rdx]
0x18001d2c9  mov     rbx, r9
0x18001d2cc  call    ?DeleteUserAccount@BasePolicyEngine@@IEAA_NPEAUIUserAccount@@W4EvaluationTrigger@@@Z; BasePolicyEngine::DeleteUserAccount(IUserAccount *,EvaluationTrigger)
0x18001d2d1  test    al, al
0x18001d2d3  jz      short loc_18001D309
0x18001d2d5  mov     rcx, [rsp+28h+arg_20]
0x18001d2da  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001d2df  mov     rcx, [rbx]; hKey
0x18001d2e2  mov     rdx, rax; lpSubKey
0x18001d2e5  call    cs:__imp_RegDeleteKeyW
0x18001d2eb  test    eax, eax
0x18001d2ed  jz      short loc_18001D309
0x18001d2ef  mov     rcx, [rsp+28h]; this
0x18001d2f4  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001d2fb  mov     r9d, eax; char *
0x18001d2fe  mov     edx, 20h ; ' '; void *
0x18001d303  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001d309  add     rsp, 20h
0x18001d30d  pop     rbx
0x18001d30e  retn
```
