# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x140007a80`
- end: `0x140007b27`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140003df4`
- `0x140003eb4`
- `0x140004174`
- `0x1400175c8`
- `0x1400177fc`

## callees

- `0x14000353c`
- `0x140007a80`
- `0x140007c18`
- `0x14001a010`

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
0x140007a80  push    rbx
0x140007a82  sub     rsp, 0C0h
0x140007a89  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x140007a90  mov     rbx, rcx
0x140007a93  test    rax, rax
0x140007a96  jz      short loc_140007A9D
0x140007a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a9d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007aa4  test    rax, rax
0x140007aa7  jz      short loc_140007AB1
0x140007aa9  mov     rcx, rbx
0x140007aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007ab1  xor     edx, edx; Val
0x140007ab3  lea     rcx, [rsp+0C8h+var_A8]; void *
0x140007ab8  mov     r8d, 98h; Size
0x140007abe  call    memset_0
0x140007ac3  mov     rcx, [rbx+88h]
0x140007aca  mov     r8d, 1; struct _CONTEXT *
0x140007ad0  mov     [rsp+0C8h+var_90], r8d
0x140007ad5  mov     [rsp+0C8h+var_A8], 0C0000409h
0x140007add  mov     [rsp+0C8h+var_A4], r8d
0x140007ae2  mov     [rsp+0C8h+var_88], 7
0x140007aeb  test    rcx, rcx
0x140007aee  jnz     short loc_140007AFB
0x140007af0  lea     rcx, [rsp+0C8h+var_A8]; this
0x140007af5  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x140007afb  movsxd  rax, dword ptr [rbx+8]
0x140007aff  xor     r8d, r8d; struct _CONTEXT *
0x140007b02  mov     [rsp+0C8h+var_80], rax
0x140007b07  mov     eax, [rbx+40h]
0x140007b0a  mov     [rsp+0C8h+var_98], rcx
0x140007b0f  lea     rcx, [rsp+0C8h+var_A8]; this
0x140007b14  mov     [rsp+0C8h+var_78], rax
0x140007b19  mov     [rsp+0C8h+var_90], 3
0x140007b21  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
