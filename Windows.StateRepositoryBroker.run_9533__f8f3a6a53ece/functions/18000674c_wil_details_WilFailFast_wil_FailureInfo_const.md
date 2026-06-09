# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x18000674c`
- end: `0x1800067f3`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180003640`
- `0x1800038d4`
- `0x180006c24`
- `0x180009638`

## callees

- `0x180002900`
- `0x18000674c`
- `0x1800067fc`
- `0x18000b010`

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
0x18000674c  push    rbx
0x18000674e  sub     rsp, 0C0h
0x180006755  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x18000675c  mov     rbx, rcx
0x18000675f  test    rax, rax
0x180006762  jz      short loc_180006769
0x180006764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006769  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006770  test    rax, rax
0x180006773  jz      short loc_18000677D
0x180006775  mov     rcx, rbx
0x180006778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000677d  xor     edx, edx; Val
0x18000677f  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180006784  mov     r8d, 98h; Size
0x18000678a  call    memset_0
0x18000678f  mov     rcx, [rbx+88h]
0x180006796  mov     r8d, 1; struct _CONTEXT *
0x18000679c  mov     [rsp+0C8h+var_90], r8d
0x1800067a1  mov     [rsp+0C8h+var_A8], 0C0000409h
0x1800067a9  mov     [rsp+0C8h+var_A4], r8d
0x1800067ae  mov     [rsp+0C8h+var_88], 7
0x1800067b7  test    rcx, rcx
0x1800067ba  jnz     short loc_1800067C7
0x1800067bc  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800067c1  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x1800067c7  movsxd  rax, dword ptr [rbx+8]
0x1800067cb  xor     r8d, r8d; struct _CONTEXT *
0x1800067ce  mov     [rsp+0C8h+var_80], rax
0x1800067d3  mov     eax, [rbx+40h]
0x1800067d6  mov     [rsp+0C8h+var_98], rcx
0x1800067db  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800067e0  mov     [rsp+0C8h+var_78], rax
0x1800067e5  mov     [rsp+0C8h+var_90], 3
0x1800067ed  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
