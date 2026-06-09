# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x140007558`
- end: `0x1400075ff`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x140004b34`
- `0x140004be4`
- `0x140004e90`
- `0x140007c6c`
- `0x140008a1c`
- `0x14000aca0`

## callees

- `0x140003f8c`
- `0x140007558`
- `0x140007728`
- `0x14000f010`

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
0x140007558  push    rbx
0x14000755a  sub     rsp, 0C0h
0x140007561  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x140007568  mov     rbx, rcx
0x14000756b  test    rax, rax
0x14000756e  jz      short loc_140007575
0x140007570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007575  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000757c  test    rax, rax
0x14000757f  jz      short loc_140007589
0x140007581  mov     rcx, rbx
0x140007584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007589  xor     edx, edx; Val
0x14000758b  lea     rcx, [rsp+0C8h+var_A8]; void *
0x140007590  mov     r8d, 98h; Size
0x140007596  call    memset_0
0x14000759b  mov     rcx, [rbx+88h]
0x1400075a2  mov     r8d, 1; struct _CONTEXT *
0x1400075a8  mov     [rsp+0C8h+var_90], r8d
0x1400075ad  mov     [rsp+0C8h+var_A8], 0C0000409h
0x1400075b5  mov     [rsp+0C8h+var_A4], r8d
0x1400075ba  mov     [rsp+0C8h+var_88], 7
0x1400075c3  test    rcx, rcx
0x1400075c6  jnz     short loc_1400075D3
0x1400075c8  lea     rcx, [rsp+0C8h+var_A8]; this
0x1400075cd  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x1400075d3  movsxd  rax, dword ptr [rbx+8]
0x1400075d7  xor     r8d, r8d; struct _CONTEXT *
0x1400075da  mov     [rsp+0C8h+var_80], rax
0x1400075df  mov     eax, [rbx+40h]
0x1400075e2  mov     [rsp+0C8h+var_98], rcx
0x1400075e7  lea     rcx, [rsp+0C8h+var_A8]; this
0x1400075ec  mov     [rsp+0C8h+var_78], rax
0x1400075f1  mov     [rsp+0C8h+var_90], 3
0x1400075f9  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
