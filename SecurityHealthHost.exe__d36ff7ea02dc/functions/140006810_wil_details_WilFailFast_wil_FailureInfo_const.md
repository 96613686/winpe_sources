# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x140006810`
- end: `0x1400068b7`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x14000581c`
- `0x140005ab0`
- `0x140006c28`

## callees

- `0x1400022ec`
- `0x140006810`
- `0x1400068c0`
- `0x140011010`

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
0x140006810  push    rbx
0x140006812  sub     rsp, 0C0h
0x140006819  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x140006820  mov     rbx, rcx
0x140006823  test    rax, rax
0x140006826  jz      short loc_14000682D
0x140006828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000682d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006834  test    rax, rax
0x140006837  jz      short loc_140006841
0x140006839  mov     rcx, rbx
0x14000683c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006841  xor     edx, edx; Val
0x140006843  lea     rcx, [rsp+0C8h+var_A8]; void *
0x140006848  mov     r8d, 98h; Size
0x14000684e  call    memset_0
0x140006853  mov     rcx, [rbx+88h]
0x14000685a  mov     r8d, 1; struct _CONTEXT *
0x140006860  mov     [rsp+0C8h+var_90], r8d
0x140006865  mov     [rsp+0C8h+var_A8], 0C0000409h
0x14000686d  mov     [rsp+0C8h+var_A4], r8d
0x140006872  mov     [rsp+0C8h+var_88], 7
0x14000687b  test    rcx, rcx
0x14000687e  jnz     short loc_14000688B
0x140006880  lea     rcx, [rsp+0C8h+var_A8]; this
0x140006885  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x14000688b  movsxd  rax, dword ptr [rbx+8]
0x14000688f  xor     r8d, r8d; struct _CONTEXT *
0x140006892  mov     [rsp+0C8h+var_80], rax
0x140006897  mov     eax, [rbx+40h]
0x14000689a  mov     [rsp+0C8h+var_98], rcx
0x14000689f  lea     rcx, [rsp+0C8h+var_A8]; this
0x1400068a4  mov     [rsp+0C8h+var_78], rax
0x1400068a9  mov     [rsp+0C8h+var_90], 3
0x1400068b1  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
