# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x140006c38`
- end: `0x140006cdf`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140002684`
- `0x140002734`
- `0x140002840`
- `0x140002ad4`

## callees

- `0x140006c38`
- `0x140006d74`
- `0x140009696`
- `0x14000a010`

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
0x140006c38  push    rbx
0x140006c3a  sub     rsp, 0C0h
0x140006c41  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x140006c48  mov     rbx, rcx
0x140006c4b  test    rax, rax
0x140006c4e  jz      short loc_140006C55
0x140006c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c55  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006c5c  test    rax, rax
0x140006c5f  jz      short loc_140006C69
0x140006c61  mov     rcx, rbx
0x140006c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c69  xor     edx, edx; Val
0x140006c6b  lea     rcx, [rsp+0C8h+var_A8]; void *
0x140006c70  mov     r8d, 98h; Size
0x140006c76  call    memset_0
0x140006c7b  mov     rcx, [rbx+88h]
0x140006c82  mov     r8d, 1; struct _CONTEXT *
0x140006c88  mov     [rsp+0C8h+var_90], r8d
0x140006c8d  mov     [rsp+0C8h+var_A8], 0C0000409h
0x140006c95  mov     [rsp+0C8h+var_A4], r8d
0x140006c9a  mov     [rsp+0C8h+var_88], 7
0x140006ca3  test    rcx, rcx
0x140006ca6  jnz     short loc_140006CB3
0x140006ca8  lea     rcx, [rsp+0C8h+var_A8]; this
0x140006cad  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x140006cb3  movsxd  rax, dword ptr [rbx+8]
0x140006cb7  xor     r8d, r8d; struct _CONTEXT *
0x140006cba  mov     [rsp+0C8h+var_80], rax
0x140006cbf  mov     eax, [rbx+40h]
0x140006cc2  mov     [rsp+0C8h+var_98], rcx
0x140006cc7  lea     rcx, [rsp+0C8h+var_A8]; this
0x140006ccc  mov     [rsp+0C8h+var_78], rax
0x140006cd1  mov     [rsp+0C8h+var_90], 3
0x140006cd9  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
