# ReadEnterprisePolicyValueWrapper(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)

- ea: `0x180019290`
- end: `0x1800193b0`
- name: `?ReadEnterprisePolicyValueWrapper@@YAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `288`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
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

## callees

- `0x18000efcc`
- `0x18000efec`
- `0x1800191c4`
- `0x180019290`
- `0x1800194f4`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019328`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019328`

## string_xrefs

- `0x1800192ba`: `onecore\enduser\windowsupdate\client\policy\wrapper\wrapper.cpp`
- `0x1800192f5`: `onecore\enduser\windowsupdate\client\policy\wrapper\wrapper.cpp`
- `0x180019337`: `onecore\enduser\windowsupdate\client\policy\wrapper\wrapper.cpp`
- `0x180019376`: `onecore\enduser\windowsupdate\client\policy\wrapper\wrapper.cpp`
- `0x18001931a`: `ReadPolicyWithFallback`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ReadEnterprisePolicyValueWrapper(unsigned int a1, struct tagEnterprisePolicyValue_V1 **a2)
{
  unsigned int LastError; // ebx
  int UpdatePolicyModule; // eax
  FARPROC ProcAddress; // rax
  const char *v8; // r9
  int v9; // eax
  int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  struct tagEnterprisePolicyValue_V1 *v12; // [rsp+68h] [rbp+30h] BYREF

  v12 = 0;
  if ( !a2 )
  {
    LastError = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecore\\enduser\\windowsupdate\\client\\policy\\wrapper\\wrapper.cpp",
      (const char *)0x80004003LL,
      v10);
    return LastError;
  }
  *a2 = 0;
  UpdatePolicyModule = LoadUpdatePolicyModule();
  LastError = UpdatePolicyModule;
  if ( UpdatePolicyModule < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecore\\enduser\\windowsupdate\\client\\policy\\wrapper\\wrapper.cpp",
      (const char *)(unsigned int)UpdatePolicyModule,
      (int)&v12);
    if ( v12 )
      ReleaseEnterprisePolicyValueWrapper(&v12);
    return LastError;
  }
  ProcAddress = GetProcAddress(g_hUpdatePolicyModule, "ReadPolicyWithFallback");
  if ( !ProcAddress )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x75,
                  (unsigned int)"onecore\\enduser\\windowsupdate\\client\\policy\\wrapper\\wrapper.cpp",
                  v8);
    if ( v12 )
      ReleaseEnterprisePolicyValueWrapper(&v12);
    return LastError;
  }
  v9 = ((__int64 (__fastcall *)(_QWORD, struct tagEnterprisePolicyValue_V1 **))ProcAddress)(a1, &v12);
  LastError = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"onecore\\enduser\\windowsupdate\\client\\policy\\wrapper\\wrapper.cpp",
      (const char *)(unsigned int)v9,
      (int)&v12);
    if ( v12 )
      ReleaseEnterprisePolicyValueWrapper(&v12);
    return LastError;
  }
  *a2 = v12;
  return 0;
}

```

## disassembly

```asm
0x180019290  push    rbp
0x180019292  push    rbx
0x180019293  push    rsi
0x180019294  push    rdi
0x180019295  mov     rbp, rsp
0x180019298  sub     rsp, 38h
0x18001929c  mov     rdi, rdx
0x18001929f  mov     esi, ecx
0x1800192a1  mov     [rbp+arg_8], 0
0x1800192a9  test    rdx, rdx
0x1800192ac  jnz     short loc_1800192D0
0x1800192ae  mov     rcx, [rbp+20h]; this
0x1800192b2  mov     ebx, 80004003h
0x1800192b7  mov     r9d, ebx; char *
0x1800192ba  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\client"...
0x1800192c1  lea     edx, [rdi+66h]; void *
0x1800192c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800192c9  mov     eax, ebx
0x1800192cb  jmp     loc_1800193A7
0x1800192d0  mov     qword ptr [rdx], 0
0x1800192d7  lea     rax, [rbp+arg_8]
0x1800192db  mov     [rbp+var_18], rax
0x1800192df  mov     [rbp+var_10], 1
0x1800192e3  call    LoadUpdatePolicyModule
0x1800192e8  mov     ebx, eax
0x1800192ea  test    eax, eax
0x1800192ec  jns     short loc_18001931A
0x1800192ee  mov     rcx, [rbp+20h]; this
0x1800192f2  mov     r9d, eax; char *
0x1800192f5  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\client"...
0x1800192fc  mov     edx, 72h ; 'r'; void *
0x180019301  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019306  nop
0x180019307  cmp     [rbp+arg_8], 0
0x18001930c  jz      short loc_180019318
0x18001930e  lea     rcx, [rbp+arg_8]; struct tagEnterprisePolicyValue_V1 **
0x180019312  call    ?ReleaseEnterprisePolicyValueWrapper@@YAJPEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReleaseEnterprisePolicyValueWrapper(tagEnterprisePolicyValue_V1 * *)
0x180019317  nop
0x180019318  jmp     short loc_1800192C9
0x18001931a  lea     rdx, aReadpolicywith; "ReadPolicyWithFallback"
0x180019321  mov     rcx, cs:?g_hUpdatePolicyModule@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x180019328  call    cs:__imp_GetProcAddress
0x18001932e  test    rax, rax
0x180019331  jnz     short loc_18001935E
0x180019333  mov     rcx, [rbp+20h]; this
0x180019337  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\client"...
0x18001933e  lea     edx, [rax+75h]; void *
0x180019341  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019346  mov     ebx, eax
0x180019348  cmp     [rbp+arg_8], 0
0x18001934d  jz      short loc_180019359
0x18001934f  lea     rcx, [rbp+arg_8]; struct tagEnterprisePolicyValue_V1 **
0x180019353  call    ?ReleaseEnterprisePolicyValueWrapper@@YAJPEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReleaseEnterprisePolicyValueWrapper(tagEnterprisePolicyValue_V1 * *)
0x180019358  nop
0x180019359  jmp     loc_1800192C9
0x18001935e  lea     rdx, [rbp+arg_8]
0x180019362  mov     ecx, esi
0x180019364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019369  mov     ebx, eax
0x18001936b  test    eax, eax
0x18001936d  jns     short loc_18001939E
0x18001936f  mov     rcx, [rbp+20h]; this
0x180019373  mov     r9d, eax; char *
0x180019376  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\client"...
0x18001937d  mov     edx, 77h ; 'w'; void *
0x180019382  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019387  nop
0x180019388  cmp     [rbp+arg_8], 0
0x18001938d  jz      short loc_180019399
0x18001938f  lea     rcx, [rbp+arg_8]; struct tagEnterprisePolicyValue_V1 **
0x180019393  call    ?ReleaseEnterprisePolicyValueWrapper@@YAJPEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReleaseEnterprisePolicyValueWrapper(tagEnterprisePolicyValue_V1 * *)
0x180019398  nop
0x180019399  jmp     loc_1800192C9
0x18001939e  mov     rax, [rbp+arg_8]
0x1800193a2  mov     [rdi], rax
0x1800193a5  xor     eax, eax
0x1800193a7  add     rsp, 38h
0x1800193ab  pop     rdi
0x1800193ac  pop     rsi
0x1800193ad  pop     rbx
0x1800193ae  pop     rbp
0x1800193af  retn
```
