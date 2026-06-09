# ReleaseUpdatePolicyValueWrapper(tagUpdatePolicyValue_V1 * *)

- ea: `0x1800195b4`
- end: `0x180019659`
- name: `?ReleaseUpdatePolicyValueWrapper@@YAJPEAPEAUtagUpdatePolicyValue_V1@@@Z`
- size: `165`
- prototype: `int(struct tagUpdatePolicyValue_V1 **)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180010630`
- `0x18001919c`
- `0x1800193b8`

## callees

- `0x18000efec`
- `0x1800191c4`
- `0x1800195b4`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019622`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019622`

## string_xrefs

- `0x1800195d3`: `onecore\enduser\windowsupdate\client\policy\wrapper\wrapper.cpp`
- `0x1800195fc`: `onecore\enduser\windowsupdate\client\policy\wrapper\wrapper.cpp`
- `0x18001961b`: `ReleaseUpdatePolicyValue`

## pseudocode

```c
__int64 __fastcall ReleaseUpdatePolicyValueWrapper(struct tagUpdatePolicyValue_V1 **a1)
{
  int v2; // ebx
  __int64 v3; // rdx
  int UpdatePolicyModule; // eax
  unsigned int v6; // edi
  FARPROC ProcAddress; // rax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a1 )
  {
    v2 = -2147467261;
    v3 = 77;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\enduser\\windowsupdate\\client\\policy\\wrapper\\wrapper.cpp",
      (const char *)(unsigned int)v2,
      v8);
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
        (void *)0x50,
        (unsigned int)"onecore\\enduser\\windowsupdate\\client\\policy\\wrapper\\wrapper.cpp",
        (const char *)(unsigned int)UpdatePolicyModule,
        v8);
      return v6;
    }
    ProcAddress = GetProcAddress(g_hUpdatePolicyModule, "ReleaseUpdatePolicyValue");
    if ( !ProcAddress )
    {
      v2 = -2147467263;
      v3 = 87;
      goto LABEL_3;
    }
    v2 = ((__int64 (__fastcall *)(struct tagUpdatePolicyValue_V1 **))ProcAddress)(a1);
    if ( v2 < 0 )
    {
      v3 = 89;
      goto LABEL_3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800195b4  mov     [rsp+arg_0], rbx
0x1800195b9  push    rdi; int
0x1800195ba  sub     rsp, 20h
0x1800195be  mov     rbx, rcx
0x1800195c1  test    rcx, rcx
0x1800195c4  jnz     short loc_1800195E6
0x1800195c6  mov     ebx, 80004003h
0x1800195cb  lea     edx, [rcx+4Dh]; void *
0x1800195ce  mov     rcx, [rsp+28h]; this
0x1800195d3  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\client"...
0x1800195da  mov     r9d, ebx; char *
0x1800195dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800195e2  mov     eax, ebx
0x1800195e4  jmp     short loc_18001964E
0x1800195e6  cmp     qword ptr [rcx], 0
0x1800195ea  jz      short loc_18001964C
0x1800195ec  call    LoadUpdatePolicyModule
0x1800195f1  mov     edi, eax
0x1800195f3  test    eax, eax
0x1800195f5  jns     short loc_180019614
0x1800195f7  mov     rcx, [rsp+28h]; this
0x1800195fc  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\client"...
0x180019603  mov     r9d, eax; char *
0x180019606  mov     edx, 50h ; 'P'; void *
0x18001960b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019610  mov     eax, edi
0x180019612  jmp     short loc_18001964E
0x180019614  mov     rcx, cs:?g_hUpdatePolicyModule@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x18001961b  lea     rdx, aReleaseupdatep; "ReleaseUpdatePolicyValue"
0x180019622  call    cs:__imp_GetProcAddress
0x180019628  test    rax, rax
0x18001962b  jnz     short loc_180019637
0x18001962d  mov     ebx, 80004001h
0x180019632  lea     edx, [rax+57h]
0x180019635  jmp     short loc_1800195CE
0x180019637  mov     rcx, rbx
0x18001963a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001963f  mov     ebx, eax
0x180019641  test    eax, eax
0x180019643  jns     short loc_18001964C
0x180019645  mov     edx, 59h ; 'Y'
0x18001964a  jmp     short loc_1800195CE
0x18001964c  xor     eax, eax
0x18001964e  mov     rbx, [rsp+28h+arg_0]
0x180019653  add     rsp, 20h
0x180019657  pop     rdi
0x180019658  retn
```
