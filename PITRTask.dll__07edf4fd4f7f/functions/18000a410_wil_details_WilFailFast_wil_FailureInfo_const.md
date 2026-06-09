# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x18000a410`
- end: `0x18000a4b7`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002914`
- `0x180002b7c`
- `0x180002e18`

## callees

- `0x18000a410`
- `0x18000a4c0`
- `0x180010792`
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
0x18000a410  push    rbx
0x18000a412  sub     rsp, 0C0h
0x18000a419  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x18000a420  mov     rbx, rcx
0x18000a423  test    rax, rax
0x18000a426  jz      short loc_18000A42D
0x18000a428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a42d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a434  test    rax, rax
0x18000a437  jz      short loc_18000A441
0x18000a439  mov     rcx, rbx
0x18000a43c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a441  xor     edx, edx; Val
0x18000a443  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000a448  mov     r8d, 98h; Size
0x18000a44e  call    memset_0
0x18000a453  mov     rcx, [rbx+88h]
0x18000a45a  mov     r8d, 1; struct _CONTEXT *
0x18000a460  mov     [rsp+0C8h+var_90], r8d
0x18000a465  mov     [rsp+0C8h+var_A8], 0C0000409h
0x18000a46d  mov     [rsp+0C8h+var_A4], r8d
0x18000a472  mov     [rsp+0C8h+var_88], 7
0x18000a47b  test    rcx, rcx
0x18000a47e  jnz     short loc_18000A48B
0x18000a480  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000a485  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x18000a48b  movsxd  rax, dword ptr [rbx+8]
0x18000a48f  xor     r8d, r8d; struct _CONTEXT *
0x18000a492  mov     [rsp+0C8h+var_80], rax
0x18000a497  mov     eax, [rbx+40h]
0x18000a49a  mov     [rsp+0C8h+var_98], rcx
0x18000a49f  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000a4a4  mov     [rsp+0C8h+var_78], rax
0x18000a4a9  mov     [rsp+0C8h+var_90], 3
0x18000a4b1  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
