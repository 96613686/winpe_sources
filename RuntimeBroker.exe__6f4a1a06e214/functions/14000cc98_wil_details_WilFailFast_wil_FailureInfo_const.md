# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x14000cc98`
- end: `0x14000cd3f`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x14000a530`
- `0x14000a648`
- `0x14000a8dc`

## callees

- `0x140009640`
- `0x14000cc98`
- `0x14000cd48`
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
0x14000cc98  push    rbx
0x14000cc9a  sub     rsp, 0C0h
0x14000cca1  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x14000cca8  mov     rbx, rcx
0x14000ccab  test    rax, rax
0x14000ccae  jz      short loc_14000CCB5
0x14000ccb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ccb5  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000ccbc  test    rax, rax
0x14000ccbf  jz      short loc_14000CCC9
0x14000ccc1  mov     rcx, rbx
0x14000ccc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ccc9  xor     edx, edx; Val
0x14000cccb  lea     rcx, [rsp+0C8h+var_A8]; void *
0x14000ccd0  mov     r8d, 98h; Size
0x14000ccd6  call    memset_0
0x14000ccdb  mov     rcx, [rbx+88h]
0x14000cce2  mov     r8d, 1; struct _CONTEXT *
0x14000cce8  mov     [rsp+0C8h+var_90], r8d
0x14000cced  mov     [rsp+0C8h+var_A8], 0C0000409h
0x14000ccf5  mov     [rsp+0C8h+var_A4], r8d
0x14000ccfa  mov     [rsp+0C8h+var_88], 7
0x14000cd03  test    rcx, rcx
0x14000cd06  jnz     short loc_14000CD13
0x14000cd08  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000cd0d  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x14000cd13  movsxd  rax, dword ptr [rbx+8]
0x14000cd17  xor     r8d, r8d; struct _CONTEXT *
0x14000cd1a  mov     [rsp+0C8h+var_80], rax
0x14000cd1f  mov     eax, [rbx+40h]
0x14000cd22  mov     [rsp+0C8h+var_98], rcx
0x14000cd27  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000cd2c  mov     [rsp+0C8h+var_78], rax
0x14000cd31  mov     [rsp+0C8h+var_90], 3
0x14000cd39  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
