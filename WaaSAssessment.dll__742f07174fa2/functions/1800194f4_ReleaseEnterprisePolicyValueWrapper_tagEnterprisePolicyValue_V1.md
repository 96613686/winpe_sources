# ReleaseEnterprisePolicyValueWrapper(tagEnterprisePolicyValue_V1 * *)

- ea: `0x1800194f4`
- end: `0x1800195ac`
- name: `?ReleaseEnterprisePolicyValueWrapper@@YAJPEAPEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `184`
- prototype: `int(struct tagEnterprisePolicyValue_V1 **)`
- caller_count: `10`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000fa40`
- `0x18000faf0`
- `0x18000fb70`
- `0x18000ff20`
- `0x18000ffa0`
- `0x1800104c0`
- `0x180010540`
- `0x1800105b0`
- `0x180019174`
- `0x180019290`

## callees

- `0x18000efcc`
- `0x18000efec`
- `0x1800191c4`
- `0x1800194f4`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019564`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019564`

## string_xrefs

- `0x180019515`: `onecore\enduser\windowsupdate\client\policy\wrapper\wrapper.cpp`
- `0x18001953e`: `onecore\enduser\windowsupdate\client\policy\wrapper\wrapper.cpp`
- `0x180019574`: `onecore\enduser\windowsupdate\client\policy\wrapper\wrapper.cpp`

## pseudocode

```c
__int64 __fastcall ReleaseEnterprisePolicyValueWrapper(struct tagEnterprisePolicyValue_V1 **a1)
{
  int v2; // ebx
  __int64 v3; // rdx
  int UpdatePolicyModule; // eax
  unsigned int v6; // edi
  FARPROC ProcAddress; // rax
  const char *v8; // r9
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a1 )
  {
    v2 = -2147467261;
    v3 = 133;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\enduser\\windowsupdate\\client\\policy\\wrapper\\wrapper.cpp",
      (const char *)(unsigned int)v2,
      v9);
    return (unsigned int)v2;
  }
  if ( *a1 )
  {
    UpdatePolicyModule = LoadUpdatePolicyModule();
    v6 = UpdatePolicyModule;
    if ( UpdatePolicyModule < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecore\\enduser\\windowsupdate\\client\\policy\\wrapper\\wrapper.cpp",
        (const char *)(unsigned int)UpdatePolicyModule,
        v9);
      return v6;
    }
    ProcAddress = GetProcAddress(g_hUpdatePolicyModule, "ReleaseEnterprisePolicyValue");
    if ( !ProcAddress )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x8C,
               (unsigned int)"onecore\\enduser\\windowsupdate\\client\\policy\\wrapper\\wrapper.cpp",
               v8);
    v2 = ((__int64 (__fastcall *)(struct tagEnterprisePolicyValue_V1 **))ProcAddress)(a1);
    if ( v2 < 0 )
    {
      v3 = 142;
      goto LABEL_3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800194f4  mov     [rsp+arg_0], rbx
0x1800194f9  push    rdi; int
0x1800194fa  sub     rsp, 20h
0x1800194fe  mov     rbx, rcx
0x180019501  test    rcx, rcx
0x180019504  jnz     short loc_180019528
0x180019506  mov     ebx, 80004003h
0x18001950b  mov     edx, 85h; void *
0x180019510  mov     rcx, [rsp+28h]; this
0x180019515  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\client"...
0x18001951c  mov     r9d, ebx; char *
0x18001951f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019524  mov     eax, ebx
0x180019526  jmp     short loc_1800195A1
0x180019528  cmp     qword ptr [rcx], 0
0x18001952c  jz      short loc_18001959F
0x18001952e  call    LoadUpdatePolicyModule
0x180019533  mov     edi, eax
0x180019535  test    eax, eax
0x180019537  jns     short loc_180019556
0x180019539  mov     rcx, [rsp+28h]; this
0x18001953e  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\client"...
0x180019545  mov     r9d, eax; char *
0x180019548  mov     edx, 89h; void *
0x18001954d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019552  mov     eax, edi
0x180019554  jmp     short loc_1800195A1
0x180019556  mov     rcx, cs:?g_hUpdatePolicyModule@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x18001955d  lea     rdx, aReleaseenterpr; "ReleaseEnterprisePolicyValue"
0x180019564  call    cs:__imp_GetProcAddress
0x18001956a  test    rax, rax
0x18001956d  jnz     short loc_180019587
0x18001956f  mov     rcx, [rsp+28h]; this
0x180019574  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\client"...
0x18001957b  mov     edx, 8Ch; void *
0x180019580  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019585  jmp     short loc_1800195A1
0x180019587  mov     rcx, rbx
0x18001958a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001958f  mov     ebx, eax
0x180019591  test    eax, eax
0x180019593  jns     short loc_18001959F
0x180019595  mov     edx, 8Eh
0x18001959a  jmp     loc_180019510
0x18001959f  xor     eax, eax
0x1800195a1  mov     rbx, [rsp+28h+arg_0]
0x1800195a6  add     rsp, 20h
0x1800195aa  pop     rdi
0x1800195ab  retn
```
