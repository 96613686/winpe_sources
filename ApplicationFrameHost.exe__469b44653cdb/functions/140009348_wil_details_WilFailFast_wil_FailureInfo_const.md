# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x140009348`
- end: `0x1400093ef`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140004534`
- `0x1400045e4`
- `0x140004878`

## callees

- `0x140003de8`
- `0x140009348`
- `0x14000944c`
- `0x14000b010`

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
0x140009348  push    rbx
0x14000934a  sub     rsp, 0C0h
0x140009351  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x140009358  mov     rbx, rcx
0x14000935b  test    rax, rax
0x14000935e  jz      short loc_140009365
0x140009360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009365  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000936c  test    rax, rax
0x14000936f  jz      short loc_140009379
0x140009371  mov     rcx, rbx
0x140009374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009379  xor     edx, edx; Val
0x14000937b  lea     rcx, [rsp+0C8h+var_A8]; void *
0x140009380  mov     r8d, 98h; Size
0x140009386  call    memset_0
0x14000938b  mov     rcx, [rbx+88h]
0x140009392  mov     r8d, 1; struct _CONTEXT *
0x140009398  mov     [rsp+0C8h+var_90], r8d
0x14000939d  mov     [rsp+0C8h+var_A8], 0C0000409h
0x1400093a5  mov     [rsp+0C8h+var_A4], r8d
0x1400093aa  mov     [rsp+0C8h+var_88], 7
0x1400093b3  test    rcx, rcx
0x1400093b6  jnz     short loc_1400093C3
0x1400093b8  lea     rcx, [rsp+0C8h+var_A8]; this
0x1400093bd  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x1400093c3  movsxd  rax, dword ptr [rbx+8]
0x1400093c7  xor     r8d, r8d; struct _CONTEXT *
0x1400093ca  mov     [rsp+0C8h+var_80], rax
0x1400093cf  mov     eax, [rbx+40h]
0x1400093d2  mov     [rsp+0C8h+var_98], rcx
0x1400093d7  lea     rcx, [rsp+0C8h+var_A8]; this
0x1400093dc  mov     [rsp+0C8h+var_78], rax
0x1400093e1  mov     [rsp+0C8h+var_90], 3
0x1400093e9  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
