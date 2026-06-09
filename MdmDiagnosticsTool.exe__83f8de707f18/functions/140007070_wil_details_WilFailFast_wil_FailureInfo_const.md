# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x140007070`
- end: `0x140007117`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1400026e0`
- `0x140002790`
- `0x14000289c`
- `0x140002b44`

## callees

- `0x140007070`
- `0x140007170`
- `0x140009cc6`
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
0x140007070  push    rbx
0x140007072  sub     rsp, 0C0h
0x140007079  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x140007080  mov     rbx, rcx
0x140007083  test    rax, rax
0x140007086  jz      short loc_14000708D
0x140007088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000708d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007094  test    rax, rax
0x140007097  jz      short loc_1400070A1
0x140007099  mov     rcx, rbx
0x14000709c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400070a1  xor     edx, edx; Val
0x1400070a3  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1400070a8  mov     r8d, 98h; Size
0x1400070ae  call    memset_0
0x1400070b3  mov     rcx, [rbx+88h]
0x1400070ba  mov     r8d, 1; struct _CONTEXT *
0x1400070c0  mov     [rsp+0C8h+var_90], r8d
0x1400070c5  mov     [rsp+0C8h+var_A8], 0C0000409h
0x1400070cd  mov     [rsp+0C8h+var_A4], r8d
0x1400070d2  mov     [rsp+0C8h+var_88], 7
0x1400070db  test    rcx, rcx
0x1400070de  jnz     short loc_1400070EB
0x1400070e0  lea     rcx, [rsp+0C8h+var_A8]; this
0x1400070e5  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x1400070eb  movsxd  rax, dword ptr [rbx+8]
0x1400070ef  xor     r8d, r8d; struct _CONTEXT *
0x1400070f2  mov     [rsp+0C8h+var_80], rax
0x1400070f7  mov     eax, [rbx+40h]
0x1400070fa  mov     [rsp+0C8h+var_98], rcx
0x1400070ff  lea     rcx, [rsp+0C8h+var_A8]; this
0x140007104  mov     [rsp+0C8h+var_78], rax
0x140007109  mov     [rsp+0C8h+var_90], 3
0x140007111  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
