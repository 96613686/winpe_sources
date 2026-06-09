# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x1800087f0`
- end: `0x180008897`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180002c80`
- `0x180002ef0`
- `0x180003184`
- `0x180009cf4`

## callees

- `0x180002958`
- `0x1800087f0`
- `0x1800088a0`
- `0x18000f010`

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
0x1800087f0  push    rbx
0x1800087f2  sub     rsp, 0C0h
0x1800087f9  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180008800  mov     rbx, rcx
0x180008803  test    rax, rax
0x180008806  jz      short loc_18000880D
0x180008808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000880d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008814  test    rax, rax
0x180008817  jz      short loc_180008821
0x180008819  mov     rcx, rbx
0x18000881c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008821  xor     edx, edx; Val
0x180008823  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180008828  mov     r8d, 98h; Size
0x18000882e  call    memset_0
0x180008833  mov     rcx, [rbx+88h]
0x18000883a  mov     r8d, 1; struct _CONTEXT *
0x180008840  mov     [rsp+0C8h+var_90], r8d
0x180008845  mov     [rsp+0C8h+var_A8], 0C0000409h
0x18000884d  mov     [rsp+0C8h+var_A4], r8d
0x180008852  mov     [rsp+0C8h+var_88], 7
0x18000885b  test    rcx, rcx
0x18000885e  jnz     short loc_18000886B
0x180008860  lea     rcx, [rsp+0C8h+var_A8]; this
0x180008865  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x18000886b  movsxd  rax, dword ptr [rbx+8]
0x18000886f  xor     r8d, r8d; struct _CONTEXT *
0x180008872  mov     [rsp+0C8h+var_80], rax
0x180008877  mov     eax, [rbx+40h]
0x18000887a  mov     [rsp+0C8h+var_98], rcx
0x18000887f  lea     rcx, [rsp+0C8h+var_A8]; this
0x180008884  mov     [rsp+0C8h+var_78], rax
0x180008889  mov     [rsp+0C8h+var_90], 3
0x180008891  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
