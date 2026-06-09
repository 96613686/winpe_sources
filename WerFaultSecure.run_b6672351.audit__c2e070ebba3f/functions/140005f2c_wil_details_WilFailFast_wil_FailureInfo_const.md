# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x140005f2c`
- end: `0x140005fd3`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140004c40`
- `0x140007634`
- `0x1400080f4`
- `0x14000835c`

## callees

- `0x140002fcc`
- `0x140005f2c`
- `0x140005fdc`
- `0x140012010`

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
0x140005f2c  push    rbx
0x140005f2e  sub     rsp, 0C0h
0x140005f35  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x140005f3c  mov     rbx, rcx
0x140005f3f  test    rax, rax
0x140005f42  jz      short loc_140005F49
0x140005f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f49  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005f50  test    rax, rax
0x140005f53  jz      short loc_140005F5D
0x140005f55  mov     rcx, rbx
0x140005f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f5d  xor     edx, edx; Val
0x140005f5f  lea     rcx, [rsp+0C8h+var_A8]; void *
0x140005f64  mov     r8d, 98h; Size
0x140005f6a  call    memset_0
0x140005f6f  mov     rcx, [rbx+88h]
0x140005f76  mov     r8d, 1; struct _CONTEXT *
0x140005f7c  mov     [rsp+0C8h+var_90], r8d
0x140005f81  mov     [rsp+0C8h+var_A8], 0C0000409h
0x140005f89  mov     [rsp+0C8h+var_A4], r8d
0x140005f8e  mov     [rsp+0C8h+var_88], 7
0x140005f97  test    rcx, rcx
0x140005f9a  jnz     short loc_140005FA7
0x140005f9c  lea     rcx, [rsp+0C8h+var_A8]; this
0x140005fa1  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x140005fa7  movsxd  rax, dword ptr [rbx+8]
0x140005fab  xor     r8d, r8d; struct _CONTEXT *
0x140005fae  mov     [rsp+0C8h+var_80], rax
0x140005fb3  mov     eax, [rbx+40h]
0x140005fb6  mov     [rsp+0C8h+var_98], rcx
0x140005fbb  lea     rcx, [rsp+0C8h+var_A8]; this
0x140005fc0  mov     [rsp+0C8h+var_78], rax
0x140005fc5  mov     [rsp+0C8h+var_90], 3
0x140005fcd  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
