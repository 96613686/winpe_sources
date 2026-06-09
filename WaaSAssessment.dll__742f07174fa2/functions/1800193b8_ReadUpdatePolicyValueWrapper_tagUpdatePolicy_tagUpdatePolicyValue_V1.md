# ReadUpdatePolicyValueWrapper(tagUpdatePolicy,tagUpdatePolicyValue_V1 * *)

- ea: `0x1800193b8`
- end: `0x1800194ed`
- name: `?ReadUpdatePolicyValueWrapper@@YAJW4tagUpdatePolicy@@PEAPEAUtagUpdatePolicyValue_V1@@@Z`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180010630`

## callees

- `0x18000efcc`
- `0x18000efec`
- `0x1800191c4`
- `0x1800193b8`
- `0x1800195b4`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001945b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001945b`

## string_xrefs

- `0x1800193e6`: `onecore\enduser\windowsupdate\client\policy\wrapper\wrapper.cpp`
- `0x180019423`: `onecore\enduser\windowsupdate\client\policy\wrapper\wrapper.cpp`
- `0x18001946a`: `onecore\enduser\windowsupdate\client\policy\wrapper\wrapper.cpp`
- `0x1800194ac`: `onecore\enduser\windowsupdate\client\policy\wrapper\wrapper.cpp`
- `0x18001944d`: `ReadPolicy`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ReadUpdatePolicyValueWrapper(__int64 a1, struct tagUpdatePolicyValue_V1 **a2)
{
  unsigned int LastError; // ebx
  int UpdatePolicyModule; // eax
  unsigned int v6; // edi
  FARPROC ProcAddress; // rax
  const char *v8; // r9
  int v9; // eax
  int v10; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  struct tagUpdatePolicyValue_V1 *v12; // [rsp+48h] [rbp+18h] BYREF

  v12 = 0;
  if ( !a2 )
  {
    LastError = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecore\\enduser\\windowsupdate\\client\\policy\\wrapper\\wrapper.cpp",
      (const char *)0x80004003LL,
      v10);
    return LastError;
  }
  *a2 = 0;
  UpdatePolicyModule = LoadUpdatePolicyModule();
  v6 = UpdatePolicyModule;
  if ( UpdatePolicyModule < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecore\\enduser\\windowsupdate\\client\\policy\\wrapper\\wrapper.cpp",
      (const char *)(unsigned int)UpdatePolicyModule,
      (int)&v12);
    if ( v12 )
      ReleaseUpdatePolicyValueWrapper(&v12);
    return v6;
  }
  ProcAddress = GetProcAddress(g_hUpdatePolicyModule, "ReadPolicy");
  if ( !ProcAddress )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x3D,
                  (unsigned int)"onecore\\enduser\\windowsupdate\\client\\policy\\wrapper\\wrapper.cpp",
                  v8);
    if ( v12 )
      ReleaseUpdatePolicyValueWrapper(&v12);
    return LastError;
  }
  v9 = ((__int64 (__fastcall *)(__int64, struct tagUpdatePolicyValue_V1 **))ProcAddress)(12, &v12);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\enduser\\windowsupdate\\client\\policy\\wrapper\\wrapper.cpp",
      (const char *)(unsigned int)v9,
      (int)&v12);
    if ( v12 )
      ReleaseUpdatePolicyValueWrapper(&v12);
    return v6;
  }
  *a2 = v12;
  return 0;
}

```

## disassembly

```asm
0x1800193b8  mov     [rsp-8+arg_0], rbx
0x1800193bd  mov     [rsp-8+arg_10], rdi
0x1800193c2  push    rbp
0x1800193c3  mov     rbp, rsp
0x1800193c6  sub     rsp, 30h
0x1800193ca  mov     rbx, rdx
0x1800193cd  mov     [rbp+arg_8], 0
0x1800193d5  test    rdx, rdx
0x1800193d8  jnz     short loc_1800193FE
0x1800193da  mov     rcx, [rbp+8]; this
0x1800193de  mov     ebx, 80004003h
0x1800193e3  mov     r9d, ebx; char *
0x1800193e6  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\client"...
0x1800193ed  mov     edx, 2Eh ; '.'; void *
0x1800193f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800193f7  mov     eax, ebx
0x1800193f9  jmp     loc_1800194DD
0x1800193fe  lea     rax, [rbp+arg_8]
0x180019402  mov     [rbp+var_10], rax
0x180019406  mov     [rbp+var_8], 1
0x18001940a  mov     qword ptr [rdx], 0
0x180019411  call    LoadUpdatePolicyModule
0x180019416  mov     edi, eax
0x180019418  test    eax, eax
0x18001941a  jns     short loc_18001944D
0x18001941c  mov     rcx, [rbp+8]; this
0x180019420  mov     r9d, eax; char *
0x180019423  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\client"...
0x18001942a  mov     edx, 3Ah ; ':'; void *
0x18001942f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019434  nop
0x180019435  cmp     [rbp+arg_8], 0
0x18001943a  jz      short loc_180019446
0x18001943c  lea     rcx, [rbp+arg_8]; struct tagUpdatePolicyValue_V1 **
0x180019440  call    ?ReleaseUpdatePolicyValueWrapper@@YAJPEAPEAUtagUpdatePolicyValue_V1@@@Z; ReleaseUpdatePolicyValueWrapper(tagUpdatePolicyValue_V1 * *)
0x180019445  nop
0x180019446  mov     eax, edi
0x180019448  jmp     loc_1800194DD
0x18001944d  lea     rdx, aReadpolicy; "ReadPolicy"
0x180019454  mov     rcx, cs:?g_hUpdatePolicyModule@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x18001945b  call    cs:__imp_GetProcAddress
0x180019461  test    rax, rax
0x180019464  jnz     short loc_180019491
0x180019466  mov     rcx, [rbp+8]; this
0x18001946a  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\client"...
0x180019471  lea     edx, [rax+3Dh]; void *
0x180019474  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019479  mov     ebx, eax
0x18001947b  cmp     [rbp+arg_8], 0
0x180019480  jz      short loc_18001948C
0x180019482  lea     rcx, [rbp+arg_8]; struct tagUpdatePolicyValue_V1 **
0x180019486  call    ?ReleaseUpdatePolicyValueWrapper@@YAJPEAPEAUtagUpdatePolicyValue_V1@@@Z; ReleaseUpdatePolicyValueWrapper(tagUpdatePolicyValue_V1 * *)
0x18001948b  nop
0x18001948c  jmp     loc_1800193F7
0x180019491  lea     rdx, [rbp+arg_8]
0x180019495  mov     ecx, 0Ch
0x18001949a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001949f  mov     edi, eax
0x1800194a1  test    eax, eax
0x1800194a3  jns     short loc_1800194D4
0x1800194a5  mov     rcx, [rbp+8]; this
0x1800194a9  mov     r9d, eax; char *
0x1800194ac  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\client"...
0x1800194b3  mov     edx, 3Fh ; '?'; void *
0x1800194b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800194bd  nop
0x1800194be  cmp     [rbp+arg_8], 0
0x1800194c3  jz      short loc_1800194CF
0x1800194c5  lea     rcx, [rbp+arg_8]; struct tagUpdatePolicyValue_V1 **
0x1800194c9  call    ?ReleaseUpdatePolicyValueWrapper@@YAJPEAPEAUtagUpdatePolicyValue_V1@@@Z; ReleaseUpdatePolicyValueWrapper(tagUpdatePolicyValue_V1 * *)
0x1800194ce  nop
0x1800194cf  jmp     loc_180019446
0x1800194d4  mov     rax, [rbp+arg_8]
0x1800194d8  mov     [rbx], rax
0x1800194db  xor     eax, eax
0x1800194dd  mov     rbx, [rsp+30h+arg_0]
0x1800194e2  mov     rdi, [rsp+30h+arg_10]
0x1800194e7  add     rsp, 30h
0x1800194eb  pop     rbp
0x1800194ec  retn
```
