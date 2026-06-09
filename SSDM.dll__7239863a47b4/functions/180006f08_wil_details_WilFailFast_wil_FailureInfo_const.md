# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180006f08`
- end: `0x180006faf`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x1800035fc`
- `0x18000387c`
- `0x180003b30`
- `0x180003ddc`
- `0x1800062cc`
- `0x18000a6f4`

## callees

- `0x180006f08`
- `0x180006fb8`
- `0x18000e962`
- `0x180010010`

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
0x180006f08  push    rbx
0x180006f0a  sub     rsp, 0C0h
0x180006f11  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180006f18  mov     rbx, rcx
0x180006f1b  test    rax, rax
0x180006f1e  jz      short loc_180006F25
0x180006f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f25  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006f2c  test    rax, rax
0x180006f2f  jz      short loc_180006F39
0x180006f31  mov     rcx, rbx
0x180006f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f39  xor     edx, edx; Val
0x180006f3b  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180006f40  mov     r8d, 98h; Size
0x180006f46  call    memset_0
0x180006f4b  mov     rcx, [rbx+88h]
0x180006f52  mov     r8d, 1; struct _CONTEXT *
0x180006f58  mov     [rsp+0C8h+var_90], r8d
0x180006f5d  mov     [rsp+0C8h+var_A8], 0C0000409h
0x180006f65  mov     [rsp+0C8h+var_A4], r8d
0x180006f6a  mov     [rsp+0C8h+var_88], 7
0x180006f73  test    rcx, rcx
0x180006f76  jnz     short loc_180006F83
0x180006f78  lea     rcx, [rsp+0C8h+var_A8]; this
0x180006f7d  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x180006f83  movsxd  rax, dword ptr [rbx+8]
0x180006f87  xor     r8d, r8d; struct _CONTEXT *
0x180006f8a  mov     [rsp+0C8h+var_80], rax
0x180006f8f  mov     eax, [rbx+40h]
0x180006f92  mov     [rsp+0C8h+var_98], rcx
0x180006f97  lea     rcx, [rsp+0C8h+var_A8]; this
0x180006f9c  mov     [rsp+0C8h+var_78], rax
0x180006fa1  mov     [rsp+0C8h+var_90], 3
0x180006fa9  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
