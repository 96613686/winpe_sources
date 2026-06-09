# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x14000d200`
- end: `0x14000d2a7`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x1400099c0`
- `0x140009c40`
- `0x140009eec`
- `0x14000e318`
- `0x14000e5cc`
- `0x14000e864`

## callees

- `0x1400090ec`
- `0x14000d200`
- `0x14000d2b0`
- `0x140018010`

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
0x14000d200  push    rbx
0x14000d202  sub     rsp, 0C0h
0x14000d209  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x14000d210  mov     rbx, rcx
0x14000d213  test    rax, rax
0x14000d216  jz      short loc_14000D21D
0x14000d218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d21d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000d224  test    rax, rax
0x14000d227  jz      short loc_14000D231
0x14000d229  mov     rcx, rbx
0x14000d22c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d231  xor     edx, edx; Val
0x14000d233  lea     rcx, [rsp+0C8h+var_A8]; void *
0x14000d238  mov     r8d, 98h; Size
0x14000d23e  call    memset_0
0x14000d243  mov     rcx, [rbx+88h]
0x14000d24a  mov     r8d, 1; struct _CONTEXT *
0x14000d250  mov     [rsp+0C8h+var_90], r8d
0x14000d255  mov     [rsp+0C8h+var_A8], 0C0000409h
0x14000d25d  mov     [rsp+0C8h+var_A4], r8d
0x14000d262  mov     [rsp+0C8h+var_88], 7
0x14000d26b  test    rcx, rcx
0x14000d26e  jnz     short loc_14000D27B
0x14000d270  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000d275  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x14000d27b  movsxd  rax, dword ptr [rbx+8]
0x14000d27f  xor     r8d, r8d; struct _CONTEXT *
0x14000d282  mov     [rsp+0C8h+var_80], rax
0x14000d287  mov     eax, [rbx+40h]
0x14000d28a  mov     [rsp+0C8h+var_98], rcx
0x14000d28f  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000d294  mov     [rsp+0C8h+var_78], rax
0x14000d299  mov     [rsp+0C8h+var_90], 3
0x14000d2a1  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
