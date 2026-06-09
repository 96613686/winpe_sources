# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180005fe0`
- end: `0x180006087`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180002ce4`
- `0x180002f64`
- `0x180003214`
- `0x1800067fc`

## callees

- `0x1800022ea`
- `0x180005fe0`
- `0x180006090`
- `0x180013010`

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
0x180005fe0  push    rbx
0x180005fe2  sub     rsp, 0C0h
0x180005fe9  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180005ff0  mov     rbx, rcx
0x180005ff3  test    rax, rax
0x180005ff6  jz      short loc_180005FFD
0x180005ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ffd  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006004  test    rax, rax
0x180006007  jz      short loc_180006011
0x180006009  mov     rcx, rbx
0x18000600c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006011  xor     edx, edx; Val
0x180006013  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180006018  mov     r8d, 98h; Size
0x18000601e  call    memset_0
0x180006023  mov     rcx, [rbx+88h]
0x18000602a  mov     r8d, 1; struct _CONTEXT *
0x180006030  mov     [rsp+0C8h+var_90], r8d
0x180006035  mov     [rsp+0C8h+var_A8], 0C0000409h
0x18000603d  mov     [rsp+0C8h+var_A4], r8d
0x180006042  mov     [rsp+0C8h+var_88], 7
0x18000604b  test    rcx, rcx
0x18000604e  jnz     short loc_18000605B
0x180006050  lea     rcx, [rsp+0C8h+var_A8]; this
0x180006055  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x18000605b  movsxd  rax, dword ptr [rbx+8]
0x18000605f  xor     r8d, r8d; struct _CONTEXT *
0x180006062  mov     [rsp+0C8h+var_80], rax
0x180006067  mov     eax, [rbx+40h]
0x18000606a  mov     [rsp+0C8h+var_98], rcx
0x18000606f  lea     rcx, [rsp+0C8h+var_A8]; this
0x180006074  mov     [rsp+0C8h+var_78], rax
0x180006079  mov     [rsp+0C8h+var_90], 3
0x180006081  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
