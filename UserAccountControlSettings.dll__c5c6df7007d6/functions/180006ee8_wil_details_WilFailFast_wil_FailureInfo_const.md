# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180006ee8`
- end: `0x180006f8f`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180004520`
- `0x1800045d4`
- `0x180004870`

## callees

- `0x180006ee8`
- `0x180007024`
- `0x18000b6de`
- `0x18000c010`

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
0x180006ee8  push    rbx
0x180006eea  sub     rsp, 0C0h
0x180006ef1  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180006ef8  mov     rbx, rcx
0x180006efb  test    rax, rax
0x180006efe  jz      short loc_180006F05
0x180006f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f05  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006f0c  test    rax, rax
0x180006f0f  jz      short loc_180006F19
0x180006f11  mov     rcx, rbx
0x180006f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f19  xor     edx, edx; Val
0x180006f1b  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180006f20  mov     r8d, 98h; Size
0x180006f26  call    memset_0
0x180006f2b  mov     rcx, [rbx+88h]
0x180006f32  mov     r8d, 1; struct _CONTEXT *
0x180006f38  mov     [rsp+0C8h+var_90], r8d
0x180006f3d  mov     [rsp+0C8h+var_A8], 0C0000409h
0x180006f45  mov     [rsp+0C8h+var_A4], r8d
0x180006f4a  mov     [rsp+0C8h+var_88], 7
0x180006f53  test    rcx, rcx
0x180006f56  jnz     short loc_180006F63
0x180006f58  lea     rcx, [rsp+0C8h+var_A8]; this
0x180006f5d  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x180006f63  movsxd  rax, dword ptr [rbx+8]
0x180006f67  xor     r8d, r8d; struct _CONTEXT *
0x180006f6a  mov     [rsp+0C8h+var_80], rax
0x180006f6f  mov     eax, [rbx+40h]
0x180006f72  mov     [rsp+0C8h+var_98], rcx
0x180006f77  lea     rcx, [rsp+0C8h+var_A8]; this
0x180006f7c  mov     [rsp+0C8h+var_78], rax
0x180006f81  mov     [rsp+0C8h+var_90], 3
0x180006f89  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
