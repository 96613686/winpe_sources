# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180007428`
- end: `0x1800074cf`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800047c0`
- `0x180004880`
- `0x18000498c`
- `0x180004c38`

## callees

- `0x180004184`
- `0x180007428`
- `0x18000752c`
- `0x180018010`

## pseudocode

```c
void __fastcall __noreturn wil::details::WilFailFast(wil::details *this, const struct wil::FailureInfo *a2)
{
  struct _EXCEPTION_RECORD *v3; // rdx
  unsigned int v4; // r9d
  __int64 v5; // rcx
  __int64 v6; // rax
  _DWORD v7[4]; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v8; // [rsp+30h] [rbp-98h]
  int v9; // [rsp+38h] [rbp-90h]
  __int64 v10; // [rsp+40h] [rbp-88h]
  __int64 v11; // [rsp+48h] [rbp-80h]
  __int64 v12; // [rsp+50h] [rbp-78h]

  if ( wil::g_pfnWilFailFast )
    wil::g_pfnWilFailFast(this, a2);
  if ( wil::details::g_pfnFailfastWithContextCallback )
    wil::details::g_pfnFailfastWithContextCallback(this, a2);
  memset_0(v7, 0, 0x98u);
  v5 = *((_QWORD *)this + 17);
  v9 = 1;
  v7[0] = -1073740791;
  v7[1] = 1;
  v10 = 7;
  if ( !v5 )
    wil::details::WilRaiseFailFastException((wil::details *)v7, v3, (struct _CONTEXT *)1, v4);
  v11 = *((int *)this + 2);
  v6 = *((unsigned int *)this + 16);
  v8 = v5;
  v12 = v6;
  v9 = 3;
  wil::details::WilRaiseFailFastException((wil::details *)v7, v3, 0, v4);
}

```

## disassembly

```asm
0x180007428  push    rbx
0x18000742a  sub     rsp, 0C0h
0x180007431  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180007438  mov     rbx, rcx
0x18000743b  test    rax, rax
0x18000743e  jz      short loc_180007445
0x180007440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007445  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000744c  test    rax, rax
0x18000744f  jz      short loc_180007459
0x180007451  mov     rcx, rbx
0x180007454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007459  xor     edx, edx; Val
0x18000745b  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180007460  mov     r8d, 98h; Size
0x180007466  call    memset_0
0x18000746b  mov     rcx, [rbx+88h]
0x180007472  mov     r8d, 1; struct _CONTEXT *
0x180007478  mov     [rsp+0C8h+var_90], r8d
0x18000747d  mov     [rsp+0C8h+var_A8], 0C0000409h
0x180007485  mov     [rsp+0C8h+var_A4], r8d
0x18000748a  mov     [rsp+0C8h+var_88], 7
0x180007493  test    rcx, rcx
0x180007496  jnz     short loc_1800074A3
0x180007498  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000749d  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x1800074a3  movsxd  rax, dword ptr [rbx+8]
0x1800074a7  xor     r8d, r8d; struct _CONTEXT *
0x1800074aa  mov     [rsp+0C8h+var_80], rax
0x1800074af  mov     eax, [rbx+40h]
0x1800074b2  mov     [rsp+0C8h+var_98], rcx
0x1800074b7  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800074bc  mov     [rsp+0C8h+var_78], rax
0x1800074c1  mov     [rsp+0C8h+var_90], 3
0x1800074c9  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
