# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x1800062cc`
- end: `0x180006373`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180003860`
- `0x180003ae0`
- `0x180003da0`
- `0x180006ce0`
- `0x180007f18`

## callees

- `0x180003290`
- `0x1800062cc`
- `0x180006438`
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
0x1800062cc  push    rbx
0x1800062ce  sub     rsp, 0C0h
0x1800062d5  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x1800062dc  mov     rbx, rcx
0x1800062df  test    rax, rax
0x1800062e2  jz      short loc_1800062E9
0x1800062e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062e9  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800062f0  test    rax, rax
0x1800062f3  jz      short loc_1800062FD
0x1800062f5  mov     rcx, rbx
0x1800062f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062fd  xor     edx, edx; Val
0x1800062ff  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180006304  mov     r8d, 98h; Size
0x18000630a  call    memset_0
0x18000630f  mov     rcx, [rbx+88h]
0x180006316  mov     r8d, 1; struct _CONTEXT *
0x18000631c  mov     [rsp+0C8h+var_90], r8d
0x180006321  mov     [rsp+0C8h+var_A8], 0C0000409h
0x180006329  mov     [rsp+0C8h+var_A4], r8d
0x18000632e  mov     [rsp+0C8h+var_88], 7
0x180006337  test    rcx, rcx
0x18000633a  jnz     short loc_180006347
0x18000633c  lea     rcx, [rsp+0C8h+var_A8]; this
0x180006341  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x180006347  movsxd  rax, dword ptr [rbx+8]
0x18000634b  xor     r8d, r8d; struct _CONTEXT *
0x18000634e  mov     [rsp+0C8h+var_80], rax
0x180006353  mov     eax, [rbx+40h]
0x180006356  mov     [rsp+0C8h+var_98], rcx
0x18000635b  lea     rcx, [rsp+0C8h+var_A8]; this
0x180006360  mov     [rsp+0C8h+var_78], rax
0x180006365  mov     [rsp+0C8h+var_90], 3
0x18000636d  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
