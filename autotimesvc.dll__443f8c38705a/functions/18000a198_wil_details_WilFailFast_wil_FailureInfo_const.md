# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x18000a198`
- end: `0x18000a23f`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180004418`
- `0x1800044d8`
- `0x1800045e0`
- `0x18000488c`
- `0x18000d8e0`

## callees

- `0x18000365c`
- `0x18000a198`
- `0x18000a2d4`
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
0x18000a198  push    rbx
0x18000a19a  sub     rsp, 0C0h
0x18000a1a1  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x18000a1a8  mov     rbx, rcx
0x18000a1ab  test    rax, rax
0x18000a1ae  jz      short loc_18000A1B5
0x18000a1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1b5  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a1bc  test    rax, rax
0x18000a1bf  jz      short loc_18000A1C9
0x18000a1c1  mov     rcx, rbx
0x18000a1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1c9  xor     edx, edx; Val
0x18000a1cb  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000a1d0  mov     r8d, 98h; Size
0x18000a1d6  call    memset_0
0x18000a1db  mov     rcx, [rbx+88h]
0x18000a1e2  mov     r8d, 1; struct _CONTEXT *
0x18000a1e8  mov     [rsp+0C8h+var_90], r8d
0x18000a1ed  mov     [rsp+0C8h+var_A8], 0C0000409h
0x18000a1f5  mov     [rsp+0C8h+var_A4], r8d
0x18000a1fa  mov     [rsp+0C8h+var_88], 7
0x18000a203  test    rcx, rcx
0x18000a206  jnz     short loc_18000A213
0x18000a208  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000a20d  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x18000a213  movsxd  rax, dword ptr [rbx+8]
0x18000a217  xor     r8d, r8d; struct _CONTEXT *
0x18000a21a  mov     [rsp+0C8h+var_80], rax
0x18000a21f  mov     eax, [rbx+40h]
0x18000a222  mov     [rsp+0C8h+var_98], rcx
0x18000a227  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000a22c  mov     [rsp+0C8h+var_78], rax
0x18000a231  mov     [rsp+0C8h+var_90], 3
0x18000a239  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
