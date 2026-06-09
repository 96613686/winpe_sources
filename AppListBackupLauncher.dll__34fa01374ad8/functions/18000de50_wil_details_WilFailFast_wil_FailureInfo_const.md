# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x18000de50`
- end: `0x18000def7`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180003a3c`
- `0x180003cbc`
- `0x180003f78`
- `0x180004224`
- `0x180005bfc`
- `0x18000cc18`

## callees

- `0x180002de0`
- `0x18000de50`
- `0x18000dfac`
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
0x18000de50  push    rbx
0x18000de52  sub     rsp, 0C0h
0x18000de59  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x18000de60  mov     rbx, rcx
0x18000de63  test    rax, rax
0x18000de66  jz      short loc_18000DE6D
0x18000de68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de6d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000de74  test    rax, rax
0x18000de77  jz      short loc_18000DE81
0x18000de79  mov     rcx, rbx
0x18000de7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de81  xor     edx, edx; Val
0x18000de83  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000de88  mov     r8d, 98h; Size
0x18000de8e  call    memset_0
0x18000de93  mov     rcx, [rbx+88h]
0x18000de9a  mov     r8d, 1; struct _CONTEXT *
0x18000dea0  mov     [rsp+0C8h+var_90], r8d
0x18000dea5  mov     [rsp+0C8h+var_A8], 0C0000409h
0x18000dead  mov     [rsp+0C8h+var_A4], r8d
0x18000deb2  mov     [rsp+0C8h+var_88], 7
0x18000debb  test    rcx, rcx
0x18000debe  jnz     short loc_18000DECB
0x18000dec0  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000dec5  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x18000decb  movsxd  rax, dword ptr [rbx+8]
0x18000decf  xor     r8d, r8d; struct _CONTEXT *
0x18000ded2  mov     [rsp+0C8h+var_80], rax
0x18000ded7  mov     eax, [rbx+40h]
0x18000deda  mov     [rsp+0C8h+var_98], rcx
0x18000dedf  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000dee4  mov     [rsp+0C8h+var_78], rax
0x18000dee9  mov     [rsp+0C8h+var_90], 3
0x18000def1  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
