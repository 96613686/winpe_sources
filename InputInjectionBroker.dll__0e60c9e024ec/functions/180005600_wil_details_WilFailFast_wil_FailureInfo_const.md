# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180005600`
- end: `0x1800056a7`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800025ec`
- `0x180002854`
- `0x180002ae8`

## callees

- `0x180005600`
- `0x1800056b0`
- `0x18001143a`
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
0x180005600  push    rbx
0x180005602  sub     rsp, 0C0h
0x180005609  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180005610  mov     rbx, rcx
0x180005613  test    rax, rax
0x180005616  jz      short loc_18000561D
0x180005618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000561d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005624  test    rax, rax
0x180005627  jz      short loc_180005631
0x180005629  mov     rcx, rbx
0x18000562c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005631  xor     edx, edx; Val
0x180005633  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180005638  mov     r8d, 98h; Size
0x18000563e  call    memset_0
0x180005643  mov     rcx, [rbx+88h]
0x18000564a  mov     r8d, 1; struct _CONTEXT *
0x180005650  mov     [rsp+0C8h+var_90], r8d
0x180005655  mov     [rsp+0C8h+var_A8], 0C0000409h
0x18000565d  mov     [rsp+0C8h+var_A4], r8d
0x180005662  mov     [rsp+0C8h+var_88], 7
0x18000566b  test    rcx, rcx
0x18000566e  jnz     short loc_18000567B
0x180005670  lea     rcx, [rsp+0C8h+var_A8]; this
0x180005675  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x18000567b  movsxd  rax, dword ptr [rbx+8]
0x18000567f  xor     r8d, r8d; struct _CONTEXT *
0x180005682  mov     [rsp+0C8h+var_80], rax
0x180005687  mov     eax, [rbx+40h]
0x18000568a  mov     [rsp+0C8h+var_98], rcx
0x18000568f  lea     rcx, [rsp+0C8h+var_A8]; this
0x180005694  mov     [rsp+0C8h+var_78], rax
0x180005699  mov     [rsp+0C8h+var_90], 3
0x1800056a1  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
