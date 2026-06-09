# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x140004898`
- end: `0x14000493f`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400022b4`
- `0x140002364`
- `0x140002600`

## callees

- `0x140001fa2`
- `0x140004898`
- `0x1400049d4`
- `0x140006010`

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
0x140004898  push    rbx
0x14000489a  sub     rsp, 0C0h
0x1400048a1  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x1400048a8  mov     rbx, rcx
0x1400048ab  test    rax, rax
0x1400048ae  jz      short loc_1400048B5
0x1400048b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048b5  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400048bc  test    rax, rax
0x1400048bf  jz      short loc_1400048C9
0x1400048c1  mov     rcx, rbx
0x1400048c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048c9  xor     edx, edx; Val
0x1400048cb  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1400048d0  mov     r8d, 98h; Size
0x1400048d6  call    memset_0
0x1400048db  mov     rcx, [rbx+88h]
0x1400048e2  mov     r8d, 1; struct _CONTEXT *
0x1400048e8  mov     [rsp+0C8h+var_90], r8d
0x1400048ed  mov     [rsp+0C8h+var_A8], 0C0000409h
0x1400048f5  mov     [rsp+0C8h+var_A4], r8d
0x1400048fa  mov     [rsp+0C8h+var_88], 7
0x140004903  test    rcx, rcx
0x140004906  jnz     short loc_140004913
0x140004908  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000490d  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x140004913  movsxd  rax, dword ptr [rbx+8]
0x140004917  xor     r8d, r8d; struct _CONTEXT *
0x14000491a  mov     [rsp+0C8h+var_80], rax
0x14000491f  mov     eax, [rbx+40h]
0x140004922  mov     [rsp+0C8h+var_98], rcx
0x140004927  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000492c  mov     [rsp+0C8h+var_78], rax
0x140004931  mov     [rsp+0C8h+var_90], 3
0x140004939  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
