# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x140005648`
- end: `0x1400056ef`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1400019b0`
- `0x140002a5c`
- `0x140002b1c`
- `0x140002dc8`
- `0x140007050`

## callees

- `0x14000252f`
- `0x140005648`
- `0x140005784`
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
0x140005648  push    rbx
0x14000564a  sub     rsp, 0C0h
0x140005651  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x140005658  mov     rbx, rcx
0x14000565b  test    rax, rax
0x14000565e  jz      short loc_140005665
0x140005660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005665  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000566c  test    rax, rax
0x14000566f  jz      short loc_140005679
0x140005671  mov     rcx, rbx
0x140005674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005679  xor     edx, edx; Val
0x14000567b  lea     rcx, [rsp+0C8h+var_A8]; void *
0x140005680  mov     r8d, 98h; Size
0x140005686  call    memset_0
0x14000568b  mov     rcx, [rbx+88h]
0x140005692  mov     r8d, 1; struct _CONTEXT *
0x140005698  mov     [rsp+0C8h+var_90], r8d
0x14000569d  mov     [rsp+0C8h+var_A8], 0C0000409h
0x1400056a5  mov     [rsp+0C8h+var_A4], r8d
0x1400056aa  mov     [rsp+0C8h+var_88], 7
0x1400056b3  test    rcx, rcx
0x1400056b6  jnz     short loc_1400056C3
0x1400056b8  lea     rcx, [rsp+0C8h+var_A8]; this
0x1400056bd  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x1400056c3  movsxd  rax, dword ptr [rbx+8]
0x1400056c7  xor     r8d, r8d; struct _CONTEXT *
0x1400056ca  mov     [rsp+0C8h+var_80], rax
0x1400056cf  mov     eax, [rbx+40h]
0x1400056d2  mov     [rsp+0C8h+var_98], rcx
0x1400056d7  lea     rcx, [rsp+0C8h+var_A8]; this
0x1400056dc  mov     [rsp+0C8h+var_78], rax
0x1400056e1  mov     [rsp+0C8h+var_90], 3
0x1400056e9  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
