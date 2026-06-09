# ToastAction::Run(void)

- ea: `0x18003d3d0`
- end: `0x18003d4a4`
- name: `?Run@ToastAction@@UEAAXXZ`
- size: `212`
- prototype: `void __fastcall(ToastAction *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000a6e0`
- `0x180017c84`
- `0x180035818`
- `0x18003c1ac`
- `0x18003d3d0`
- `0x180042edc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003d433`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003d433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d41a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d41a`

## string_xrefs

- `0x18003d473`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\toastaction.cpp`

## pseudocode

```c
void __fastcall ToastAction::Run(ToastAction *this)
{
  const unsigned __int16 *v2; // rsi
  struct MitigationContext *MitigationContext; // rbx
  int v4; // eax
  HSTRING string; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = *(const unsigned __int16 **)(*((_QWORD *)this + 7) + 40LL);
  MitigationContext = MitigationExecutionContext::GetMitigationContext(v2);
  if ( WindowsCreateStringReference(L"PostSuccessfulExecution", 0x17u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( !(unsigned int)Windows::Internal::String::CompareOrdinal(
                        (ToastAction *)((char *)this + 64),
                        (const struct Windows::Internal::String *)&string)
    && *((_BYTE *)MitigationContext + 344)
    && *((_BYTE *)MitigationContext + 345) )
  {
    v4 = MitigationToastNotification::DispatchToast(3, v2, *((unsigned int *)MitigationContext + 30));
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\toastaction.cpp",
        (const char *)(unsigned int)v4,
        (int)string);
  }
}

```

## disassembly

```asm
0x18003d3d0  mov     [rsp+arg_8], rbx
0x18003d3d5  mov     [rsp+arg_10], rsi
0x18003d3da  push    rdi
0x18003d3db  sub     rsp, 50h
0x18003d3df  mov     rax, cs:__security_cookie
0x18003d3e6  xor     rax, rsp
0x18003d3e9  mov     [rsp+58h+var_18], rax
0x18003d3ee  mov     rax, [rcx+38h]
0x18003d3f2  mov     rdi, rcx
0x18003d3f5  mov     rsi, [rax+28h]
0x18003d3f9  mov     rcx, rsi; unsigned __int16 *
0x18003d3fc  call    ?GetMitigationContext@MitigationExecutionContext@@SAAEAVMitigationContext@@PEBG@Z; MitigationExecutionContext::GetMitigationContext(ushort const *)
0x18003d401  lea     r9, [rsp+58h+string]; string
0x18003d406  mov     edx, 17h; length
0x18003d40b  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x18003d410  mov     rbx, rax
0x18003d413  lea     rcx, aPostsuccessful; "PostSuccessfulExecution"
0x18003d41a  call    cs:__imp_WindowsCreateStringReference
0x18003d420  test    eax, eax
0x18003d422  jns     short loc_18003D439
0x18003d424  xor     r9d, r9d; lpArguments
0x18003d427  xor     r8d, r8d; nNumberOfArguments
0x18003d42a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003d42f  lea     edx, [r9+1]; dwExceptionFlags
0x18003d433  call    cs:__imp_RaiseException
0x18003d439  lea     rcx, [rdi+40h]; this
0x18003d43d  lea     rdx, [rsp+58h+string]; struct Windows::Internal::String *
0x18003d442  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x18003d447  test    eax, eax
0x18003d449  jnz     short loc_18003D487
0x18003d44b  cmp     [rbx+158h], al
0x18003d451  jz      short loc_18003D487
0x18003d453  cmp     [rbx+159h], al
0x18003d459  jz      short loc_18003D487
0x18003d45b  mov     r8d, [rbx+78h]
0x18003d45f  lea     ecx, [rax+3]
0x18003d462  mov     rdx, rsi
0x18003d465  call    ?DispatchToast@MitigationToastNotification@@SAJW4ToastType@@QEBGW4MitigationCategory@@@Z; MitigationToastNotification::DispatchToast(ToastType,ushort const * const,MitigationCategory)
0x18003d46a  test    eax, eax
0x18003d46c  jns     short loc_18003D487
0x18003d46e  mov     rcx, [rsp+58h]; this
0x18003d473  lea     r8, aOnecoreBaseDia_15; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003d47a  mov     r9d, eax; char *
0x18003d47d  mov     edx, 41h ; 'A'; void *
0x18003d482  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003d487  mov     rcx, [rsp+58h+var_18]
0x18003d48c  xor     rcx, rsp; StackCookie
0x18003d48f  call    __security_check_cookie
0x18003d494  mov     rbx, [rsp+58h+arg_8]
0x18003d499  mov     rsi, [rsp+58h+arg_10]
0x18003d49e  add     rsp, 50h
0x18003d4a2  pop     rdi
0x18003d4a3  retn
```
