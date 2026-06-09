# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x18000ae90`
- end: `0x18000af37`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002564`
- `0x1800027cc`
- `0x180002a68`

## callees

- `0x18000ae90`
- `0x18000af40`
- `0x18000f5c2`
- `0x180011010`

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
0x18000ae90  push    rbx
0x18000ae92  sub     rsp, 0C0h
0x18000ae99  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x18000aea0  mov     rbx, rcx
0x18000aea3  test    rax, rax
0x18000aea6  jz      short loc_18000AEAD
0x18000aea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aead  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000aeb4  test    rax, rax
0x18000aeb7  jz      short loc_18000AEC1
0x18000aeb9  mov     rcx, rbx
0x18000aebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aec1  xor     edx, edx; Val
0x18000aec3  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000aec8  mov     r8d, 98h; Size
0x18000aece  call    memset_0
0x18000aed3  mov     rcx, [rbx+88h]
0x18000aeda  mov     r8d, 1; struct _CONTEXT *
0x18000aee0  mov     [rsp+0C8h+var_90], r8d
0x18000aee5  mov     [rsp+0C8h+var_A8], 0C0000409h
0x18000aeed  mov     [rsp+0C8h+var_A4], r8d
0x18000aef2  mov     [rsp+0C8h+var_88], 7
0x18000aefb  test    rcx, rcx
0x18000aefe  jnz     short loc_18000AF0B
0x18000af00  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000af05  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x18000af0b  movsxd  rax, dword ptr [rbx+8]
0x18000af0f  xor     r8d, r8d; struct _CONTEXT *
0x18000af12  mov     [rsp+0C8h+var_80], rax
0x18000af17  mov     eax, [rbx+40h]
0x18000af1a  mov     [rsp+0C8h+var_98], rcx
0x18000af1f  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000af24  mov     [rsp+0C8h+var_78], rax
0x18000af29  mov     [rsp+0C8h+var_90], 3
0x18000af31  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
