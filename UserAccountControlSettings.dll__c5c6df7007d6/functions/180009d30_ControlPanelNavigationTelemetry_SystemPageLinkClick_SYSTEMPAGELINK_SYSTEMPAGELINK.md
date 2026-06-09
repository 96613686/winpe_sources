# ControlPanelNavigationTelemetry::SystemPageLinkClick<SYSTEMPAGELINK>(SYSTEMPAGELINK &&)

- ea: `0x180009d30`
- end: `0x180009df1`
- name: `??$SystemPageLinkClick@W4SYSTEMPAGELINK@@@ControlPanelNavigationTelemetry@@SAX$$QEAW4SYSTEMPAGELINK@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a4a0`

## callees

- `0x18000172c`
- `0x1800017f8`
- `0x180009d30`
- `0x18000ab40`
- `0x18000b710`

## pseudocode

```c
__int64 __fastcall ControlPanelNavigationTelemetry::SystemPageLinkClick<enum SYSTEMPAGELINK>(char *a1)
{
  unsigned int *v2; // r10
  __int64 result; // rax
  int v4; // r10d
  char v5; // [rsp+30h] [rbp-68h] BYREF
  __int64 v6; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v7[32]; // [rsp+40h] [rbp-58h] BYREF
  char *v8; // [rsp+60h] [rbp-38h]
  __int64 v9; // [rsp+68h] [rbp-30h]
  __int64 *v10; // [rsp+70h] [rbp-28h]
  __int64 v11; // [rsp+78h] [rbp-20h]

  v2 = *(unsigned int **)(wil::details::static_lazy<ControlPanelNavigationTelemetry>::get(
                            a1,
                            _lambda_0ca99fd8aeb53e91e15a05469392764c_::_lambda_invoker_cdecl_)
                        + 8);
  result = *v2;
  if ( (unsigned int)result > 5 )
  {
    result = tlgKeywordOn(v2, 0x400000000000LL);
    if ( (_BYTE)result )
    {
      v5 = *a1;
      v6 = 0x2000000;
      v10 = &v6;
      v11 = 8;
      v8 = &v5;
      v9 = 1;
      return tlgWriteTransfer_EtwEventWriteTransfer(v4, (unsigned int)&byte_18000FDE7, 0, 0, 4, (__int64)v7);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009d30  push    rbx
0x180009d32  sub     rsp, 90h
0x180009d39  mov     rax, cs:__security_cookie
0x180009d40  xor     rax, rsp
0x180009d43  mov     [rsp+98h+var_18], rax
0x180009d4b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_0ca99fd8aeb53e91e15a05469392764c_@@CA@XZ; _lambda_0ca99fd8aeb53e91e15a05469392764c_::_lambda_invoker_cdecl_(void)
0x180009d52  mov     rbx, rcx
0x180009d55  call    ?get@?$static_lazy@VControlPanelNavigationTelemetry@@@details@wil@@QEAAPEAVControlPanelNavigationTelemetry@@P6AXXZ@Z; wil::details::static_lazy<ControlPanelNavigationTelemetry>::get(void (*)(void))
0x180009d5a  mov     r10, [rax+8]
0x180009d5e  mov     eax, [r10]
0x180009d61  cmp     eax, 5
0x180009d64  jbe     short loc_180009DD8
0x180009d66  mov     rdx, 400000000000h
0x180009d70  mov     rcx, r10
0x180009d73  call    _tlgKeywordOn
0x180009d78  test    al, al
0x180009d7a  jz      short loc_180009DD8
0x180009d7c  mov     al, [rbx]
0x180009d7e  lea     rdx, byte_18000FDE7
0x180009d85  mov     [rsp+98h+var_68], al
0x180009d89  xor     r9d, r9d
0x180009d8c  lea     rax, [rsp+98h+var_60]
0x180009d91  mov     [rsp+98h+var_60], 2000000h
0x180009d9a  mov     [rsp+98h+var_28], rax
0x180009d9f  xor     r8d, r8d
0x180009da2  lea     rax, [rsp+98h+var_68]
0x180009da7  mov     [rsp+98h+var_20], 8
0x180009db0  mov     [rsp+98h+var_38], rax
0x180009db5  mov     rcx, r10
0x180009db8  lea     rax, [rsp+98h+var_58]
0x180009dbd  mov     [rsp+98h+var_30], 1
0x180009dc6  mov     [rsp+98h+var_70], rax
0x180009dcb  mov     [rsp+98h+var_78], 4
0x180009dd3  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180009dd8  mov     rcx, [rsp+98h+var_18]
0x180009de0  xor     rcx, rsp; StackCookie
0x180009de3  call    __security_check_cookie
0x180009de8  add     rsp, 90h
0x180009def  pop     rbx
0x180009df0  retn
```
