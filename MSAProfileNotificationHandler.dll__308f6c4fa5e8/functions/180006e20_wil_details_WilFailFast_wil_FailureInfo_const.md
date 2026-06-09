# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180006e20`
- end: `0x180006ec7`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000335c`
- `0x1800035cc`
- `0x180003868`

## callees

- `0x1800028f0`
- `0x180006e20`
- `0x180006ed0`
- `0x180009010`

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
0x180006e20  push    rbx
0x180006e22  sub     rsp, 0C0h
0x180006e29  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180006e30  mov     rbx, rcx
0x180006e33  test    rax, rax
0x180006e36  jz      short loc_180006E3D
0x180006e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e3d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006e44  test    rax, rax
0x180006e47  jz      short loc_180006E51
0x180006e49  mov     rcx, rbx
0x180006e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e51  xor     edx, edx; Val
0x180006e53  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180006e58  mov     r8d, 98h; Size
0x180006e5e  call    memset_0
0x180006e63  mov     rcx, [rbx+88h]
0x180006e6a  mov     r8d, 1; struct _CONTEXT *
0x180006e70  mov     [rsp+0C8h+var_90], r8d
0x180006e75  mov     [rsp+0C8h+var_A8], 0C0000409h
0x180006e7d  mov     [rsp+0C8h+var_A4], r8d
0x180006e82  mov     [rsp+0C8h+var_88], 7
0x180006e8b  test    rcx, rcx
0x180006e8e  jnz     short loc_180006E9B
0x180006e90  lea     rcx, [rsp+0C8h+var_A8]; this
0x180006e95  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x180006e9b  movsxd  rax, dword ptr [rbx+8]
0x180006e9f  xor     r8d, r8d; struct _CONTEXT *
0x180006ea2  mov     [rsp+0C8h+var_80], rax
0x180006ea7  mov     eax, [rbx+40h]
0x180006eaa  mov     [rsp+0C8h+var_98], rcx
0x180006eaf  lea     rcx, [rsp+0C8h+var_A8]; this
0x180006eb4  mov     [rsp+0C8h+var_78], rax
0x180006eb9  mov     [rsp+0C8h+var_90], 3
0x180006ec1  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
