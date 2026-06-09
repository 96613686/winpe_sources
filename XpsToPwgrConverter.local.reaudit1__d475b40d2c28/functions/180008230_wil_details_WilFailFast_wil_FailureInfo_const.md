# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180008230`
- end: `0x1800082d7`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800026dc`
- `0x18000295c`
- `0x180002c08`
- `0x180008f08`

## callees

- `0x180002194`
- `0x180008230`
- `0x1800082e0`
- `0x180011010`

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
0x180008230  push    rbx
0x180008232  sub     rsp, 0C0h
0x180008239  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180008240  mov     rbx, rcx
0x180008243  test    rax, rax
0x180008246  jz      short loc_18000824D
0x180008248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000824d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008254  test    rax, rax
0x180008257  jz      short loc_180008261
0x180008259  mov     rcx, rbx
0x18000825c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008261  xor     edx, edx; Val
0x180008263  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180008268  mov     r8d, 98h; Size
0x18000826e  call    memset_0
0x180008273  mov     rcx, [rbx+88h]
0x18000827a  mov     r8d, 1; struct _CONTEXT *
0x180008280  mov     [rsp+0C8h+var_90], r8d
0x180008285  mov     [rsp+0C8h+var_A8], 0C0000409h
0x18000828d  mov     [rsp+0C8h+var_A4], r8d
0x180008292  mov     [rsp+0C8h+var_88], 7
0x18000829b  test    rcx, rcx
0x18000829e  jnz     short loc_1800082AB
0x1800082a0  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800082a5  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x1800082ab  movsxd  rax, dword ptr [rbx+8]
0x1800082af  xor     r8d, r8d; struct _CONTEXT *
0x1800082b2  mov     [rsp+0C8h+var_80], rax
0x1800082b7  mov     eax, [rbx+40h]
0x1800082ba  mov     [rsp+0C8h+var_98], rcx
0x1800082bf  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800082c4  mov     [rsp+0C8h+var_78], rax
0x1800082c9  mov     [rsp+0C8h+var_90], 3
0x1800082d1  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
