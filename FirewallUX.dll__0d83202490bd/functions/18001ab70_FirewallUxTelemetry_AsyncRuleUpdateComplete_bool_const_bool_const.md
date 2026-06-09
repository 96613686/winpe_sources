# FirewallUxTelemetry::AsyncRuleUpdateComplete<bool const &>(bool const &)

- ea: `0x18001ab70`
- end: `0x18001abe7`
- name: `??$AsyncRuleUpdateComplete@AEB_N@FirewallUxTelemetry@@SAXAEB_N@Z`
- size: `119`
- prototype: `const struct _tlgProvider_t *__fastcall(char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001cdc0`

## callees

- `0x1800019dc`
- `0x1800021c0`
- `0x180008820`
- `0x18001ab70`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
const struct _tlgProvider_t *__fastcall FirewallUxTelemetry::AsyncRuleUpdateComplete<bool const &>(char *a1)
{
  const struct _tlgProvider_t *result; // rax
  char v3; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v4[32]; // [rsp+38h] [rbp-40h] BYREF
  char *v5; // [rsp+58h] [rbp-20h]
  __int64 v6; // [rsp+60h] [rbp-18h]

  result = FirewallUxTraceLoggingProvider::Provider();
  if ( *(_DWORD *)result > 5u )
  {
    v3 = *a1;
    v6 = 1;
    v5 = &v3;
    return (const struct _tlgProvider_t *)tlgWriteTransfer_EventWriteTransfer(result, &unk_18003323C, 0, 0, 3, v4);
  }
  return result;
}

```

## disassembly

```asm
0x18001ab70  push    rbx
0x18001ab72  sub     rsp, 70h
0x18001ab76  mov     rax, cs:__security_cookie
0x18001ab7d  xor     rax, rsp
0x18001ab80  mov     [rsp+78h+var_10], rax
0x18001ab85  mov     rbx, rcx
0x18001ab88  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x18001ab8d  mov     edx, [rax]
0x18001ab8f  cmp     edx, 5
0x18001ab92  jbe     short loc_18001ABD4
0x18001ab94  mov     cl, [rbx]
0x18001ab96  lea     rdx, unk_18003323C
0x18001ab9d  mov     [rsp+78h+var_48], cl
0x18001aba1  xor     r9d, r9d
0x18001aba4  lea     rcx, [rsp+78h+var_48]
0x18001aba9  mov     [rsp+78h+var_18], 1
0x18001abb2  mov     [rsp+78h+var_20], rcx
0x18001abb7  xor     r8d, r8d
0x18001abba  lea     rcx, [rsp+78h+var_40]
0x18001abbf  mov     [rsp+78h+var_50], rcx
0x18001abc4  mov     rcx, rax
0x18001abc7  mov     [rsp+78h+var_58], 3
0x18001abcf  call    _tlgWriteTransfer_EventWriteTransfer
0x18001abd4  mov     rcx, [rsp+78h+var_10]
0x18001abd9  xor     rcx, rsp; StackCookie
0x18001abdc  call    __security_check_cookie
0x18001abe1  add     rsp, 70h
0x18001abe5  pop     rbx
0x18001abe6  retn
```
