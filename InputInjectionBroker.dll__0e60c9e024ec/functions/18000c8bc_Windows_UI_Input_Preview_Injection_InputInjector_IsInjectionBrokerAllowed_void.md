# Windows::UI::Input::Preview::Injection::InputInjector::IsInjectionBrokerAllowed(void)

- ea: `0x18000c8bc`
- end: `0x18000c97c`
- name: `?IsInjectionBrokerAllowed@InputInjector@Injection@Preview@Input@UI@Windows@@SAJXZ`
- size: `192`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800062f0`
- `0x180007b30`
- `0x180007c78`

## callees

- `0x180004a34`
- `0x18000c8bc`
- `0x18000dec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000c8c8`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000c8c8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000c934`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000c969`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000c934`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000c969`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000c917`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000c917`

## string_xrefs

- `0x18000c909`: `inputInjectionBrokered`
- `0x18000c8e5`: `onecore\windows\advcore\winrt\inputinjectionbroker\common\lib\inputinjector.cpp`
- `0x18000c94a`: `onecore\windows\advcore\winrt\inputinjectionbroker\common\lib\inputinjector.cpp`

## pseudocode

```c
__int64 Windows::UI::Input::Preview::Injection::InputInjector::IsInjectionBrokerAllowed(void)
{
  char v0; // bl
  HRESULT v1; // eax
  int v2; // ebx
  int v4; // eax
  void *v5; // rdx
  unsigned int v6; // r8d
  unsigned int v7; // edi
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v10; // [rsp+30h] [rbp+8h] BYREF

  v0 = 1;
  v1 = CoImpersonateClient();
  if ( v1 < 0 )
  {
    v2 = 0;
    if ( v1 != -2147417833 )
      v2 = v1;
    if ( v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65D,
        (unsigned int)"onecore\\windows\\advcore\\winrt\\inputinjectionbroker\\common\\lib\\inputinjector.cpp",
        (const char *)(unsigned int)v2,
        v8);
      return (unsigned int)v2;
    }
    v0 = 0;
  }
  v10 = 0;
  v4 = CapabilityCheck(-6, L"inputInjectionBrokered", &v10);
  if ( v4 < 0 )
  {
    v7 = wil::details::in1diag3::Return_NtStatus(retaddr, v5, v6, (const char *)(unsigned int)v4, v8);
LABEL_9:
    if ( v0 )
      CoRevertToSelf();
    return v7;
  }
  if ( !v10 )
  {
    v7 = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x664,
      (unsigned int)"onecore\\windows\\advcore\\winrt\\inputinjectionbroker\\common\\lib\\inputinjector.cpp",
      (const char *)0x80070005LL,
      v8);
    goto LABEL_9;
  }
  if ( v0 )
    CoRevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x18000c8bc  mov     [rsp+arg_8], rbx
0x18000c8c1  push    rdi; int
0x18000c8c2  sub     rsp, 20h
0x18000c8c6  mov     bl, 1
0x18000c8c8  call    cs:__imp_CoImpersonateClient
0x18000c8ce  test    eax, eax
0x18000c8d0  jns     short loc_18000C8FF
0x18000c8d2  xor     ebx, ebx
0x18000c8d4  cmp     eax, 80010117h
0x18000c8d9  cmovnz  ebx, eax
0x18000c8dc  test    ebx, ebx
0x18000c8de  jns     short loc_18000C8FD
0x18000c8e0  mov     rcx, [rsp+28h]; this
0x18000c8e5  lea     r8, aOnecoreWindows; "onecore\\windows\\advcore\\winrt\\input"...
0x18000c8ec  mov     r9d, ebx; char *
0x18000c8ef  mov     edx, 65Dh; void *
0x18000c8f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c8f9  mov     eax, ebx
0x18000c8fb  jmp     short loc_18000C971
0x18000c8fd  xor     bl, bl
0x18000c8ff  lea     r8, [rsp+28h+arg_0]
0x18000c904  mov     [rsp+28h+arg_0], 0
0x18000c909  lea     rdx, aInputinjection_0; "inputInjectionBrokered"
0x18000c910  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x18000c917  call    cs:__imp_CapabilityCheck
0x18000c91d  test    eax, eax
0x18000c91f  jns     short loc_18000C93E
0x18000c921  mov     rcx, [rsp+28h]; this
0x18000c926  mov     r9d, eax; char *
0x18000c929  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000c92e  mov     edi, eax
0x18000c930  test    bl, bl
0x18000c932  jz      short loc_18000C93A
0x18000c934  call    cs:__imp_CoRevertToSelf
0x18000c93a  mov     eax, edi
0x18000c93c  jmp     short loc_18000C971
0x18000c93e  cmp     [rsp+28h+arg_0], 0
0x18000c943  jnz     short loc_18000C965
0x18000c945  mov     rcx, [rsp+28h]; this
0x18000c94a  lea     r8, aOnecoreWindows; "onecore\\windows\\advcore\\winrt\\input"...
0x18000c951  mov     edi, 80070005h
0x18000c956  mov     edx, 664h; void *
0x18000c95b  mov     r9d, edi; char *
0x18000c95e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c963  jmp     short loc_18000C930
0x18000c965  test    bl, bl
0x18000c967  jz      short loc_18000C96F
0x18000c969  call    cs:__imp_CoRevertToSelf
0x18000c96f  xor     eax, eax
0x18000c971  mov     rbx, [rsp+28h+arg_8]
0x18000c976  add     rsp, 20h
0x18000c97a  pop     rdi
0x18000c97b  retn
```
