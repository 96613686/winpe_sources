# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x14000b668`
- end: `0x14000b70f`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140001f50`
- `0x140006e90`
- `0x140006f40`
- `0x1400071d4`

## callees

- `0x1400061b8`
- `0x14000b668`
- `0x14000b76c`
- `0x140010010`

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
0x14000b668  push    rbx
0x14000b66a  sub     rsp, 0C0h
0x14000b671  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x14000b678  mov     rbx, rcx
0x14000b67b  test    rax, rax
0x14000b67e  jz      short loc_14000B685
0x14000b680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b685  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000b68c  test    rax, rax
0x14000b68f  jz      short loc_14000B699
0x14000b691  mov     rcx, rbx
0x14000b694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b699  xor     edx, edx; Val
0x14000b69b  lea     rcx, [rsp+0C8h+var_A8]; void *
0x14000b6a0  mov     r8d, 98h; Size
0x14000b6a6  call    memset_0
0x14000b6ab  mov     rcx, [rbx+88h]
0x14000b6b2  mov     r8d, 1; struct _CONTEXT *
0x14000b6b8  mov     [rsp+0C8h+var_90], r8d
0x14000b6bd  mov     [rsp+0C8h+var_A8], 0C0000409h
0x14000b6c5  mov     [rsp+0C8h+var_A4], r8d
0x14000b6ca  mov     [rsp+0C8h+var_88], 7
0x14000b6d3  test    rcx, rcx
0x14000b6d6  jnz     short loc_14000B6E3
0x14000b6d8  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000b6dd  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x14000b6e3  movsxd  rax, dword ptr [rbx+8]
0x14000b6e7  xor     r8d, r8d; struct _CONTEXT *
0x14000b6ea  mov     [rsp+0C8h+var_80], rax
0x14000b6ef  mov     eax, [rbx+40h]
0x14000b6f2  mov     [rsp+0C8h+var_98], rcx
0x14000b6f7  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000b6fc  mov     [rsp+0C8h+var_78], rax
0x14000b701  mov     [rsp+0C8h+var_90], 3
0x14000b709  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
