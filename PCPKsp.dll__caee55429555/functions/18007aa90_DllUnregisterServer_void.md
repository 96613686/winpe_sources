# DllUnregisterServer(void)

- ea: `0x18007aa90`
- end: `0x18007ab19`
- name: `?DllUnregisterServer@@YAJXZ`
- size: `137`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180061bac`
- `0x18007aa90`
- `0x18007b0d0`

## import_xrefs

- `bcrypt!BCryptUnregisterProvider` at `0x18007aab1`
- `bcrypt!BCryptUnregisterProvider` at `0x18007aab1`

## string_xrefs

- `0x18007aa99`: `DllUnregisterServer`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  int v0; // eax
  HRESULT v1; // ebx
  int v2; // eax
  int *v4[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v4, L"DllUnregisterServer", 1);
  v0 = BCryptUnregisterProvider(L"Microsoft Platform Crypto Provider");
  if ( v0 >= 0 )
  {
    v2 = RemoveUserAccessACLs();
    v1 = v2;
    if ( v2 >= 0 )
      v1 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\registerkspprovider.cpp",
        (const char *)(unsigned int)v2,
        (int)v4[0]);
  }
  else
  {
    v1 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x1A5,
           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\registerkspprovider.cpp",
           (const char *)(unsigned int)v0,
           (int)v4[0]);
  }
  KspFunctionLogger::~KspFunctionLogger(v4);
  return v1;
}

```

## disassembly

```asm
0x18007aa90  push    rbx
0x18007aa92  sub     rsp, 40h
0x18007aa96  mov     r8b, 1; bool
0x18007aa99  lea     rdx, aDllunregisters_0; "DllUnregisterServer"
0x18007aaa0  lea     rcx, [rsp+48h+var_28]; this
0x18007aaa5  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18007aaaa  lea     rcx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x18007aab1  call    cs:__imp_BCryptUnregisterProvider
0x18007aab8  nop     dword ptr [rax+rax+00h]
0x18007aabd  test    eax, eax
0x18007aabf  jns     short loc_18007AADE
0x18007aac1  mov     rcx, [rsp+48h]; this
0x18007aac6  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007aacd  mov     r9d, eax; char *
0x18007aad0  mov     edx, 1A5h; void *
0x18007aad5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007aada  mov     ebx, eax
0x18007aadc  jmp     short loc_18007AB06
0x18007aade  call    ?RemoveUserAccessACLs@@YAJXZ; RemoveUserAccessACLs(void)
0x18007aae3  mov     ebx, eax
0x18007aae5  test    eax, eax
0x18007aae7  jns     short loc_18007AB04
0x18007aae9  mov     rcx, [rsp+48h]; this
0x18007aaee  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007aaf5  mov     r9d, eax; char *
0x18007aaf8  mov     edx, 1A6h; void *
0x18007aafd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ab02  jmp     short loc_18007AB06
0x18007ab04  xor     ebx, ebx
0x18007ab06  lea     rcx, [rsp+48h+var_28]; this
0x18007ab0b  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18007ab10  mov     eax, ebx
0x18007ab12  add     rsp, 40h
0x18007ab16  pop     rbx
0x18007ab17  retn
```
