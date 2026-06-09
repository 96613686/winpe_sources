# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x1800114d8`
- end: `0x18001157f`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f51c`
- `0x18000f5d0`
- `0x18000f86c`

## callees

- `0x18000a19a`
- `0x1800114d8`
- `0x180011588`
- `0x180012010`

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
0x1800114d8  push    rbx
0x1800114da  sub     rsp, 0C0h
0x1800114e1  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x1800114e8  mov     rbx, rcx
0x1800114eb  test    rax, rax
0x1800114ee  jz      short loc_1800114F5
0x1800114f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114f5  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800114fc  test    rax, rax
0x1800114ff  jz      short loc_180011509
0x180011501  mov     rcx, rbx
0x180011504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011509  xor     edx, edx; Val
0x18001150b  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180011510  mov     r8d, 98h; Size
0x180011516  call    memset_0
0x18001151b  mov     rcx, [rbx+88h]
0x180011522  mov     r8d, 1; struct _CONTEXT *
0x180011528  mov     [rsp+0C8h+var_90], r8d
0x18001152d  mov     [rsp+0C8h+var_A8], 0C0000409h
0x180011535  mov     [rsp+0C8h+var_A4], r8d
0x18001153a  mov     [rsp+0C8h+var_88], 7
0x180011543  test    rcx, rcx
0x180011546  jnz     short loc_180011553
0x180011548  lea     rcx, [rsp+0C8h+var_A8]; this
0x18001154d  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x180011553  movsxd  rax, dword ptr [rbx+8]
0x180011557  xor     r8d, r8d; struct _CONTEXT *
0x18001155a  mov     [rsp+0C8h+var_80], rax
0x18001155f  mov     eax, [rbx+40h]
0x180011562  mov     [rsp+0C8h+var_98], rcx
0x180011567  lea     rcx, [rsp+0C8h+var_A8]; this
0x18001156c  mov     [rsp+0C8h+var_78], rax
0x180011571  mov     [rsp+0C8h+var_90], 3
0x180011579  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
