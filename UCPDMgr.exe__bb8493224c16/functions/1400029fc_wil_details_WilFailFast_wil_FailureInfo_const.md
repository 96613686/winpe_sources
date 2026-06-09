# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x1400029fc`
- end: `0x140002aa3`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140004778`
- `0x140004c6c`
- `0x140004d94`

## callees

- `0x140001904`
- `0x1400029fc`
- `0x14000f4d0`
- `0x14000f550`

## pseudocode

```c
void __fastcall __noreturn wil::details::WilFailFast(wil::details *this, const struct wil::FailureInfo *a2)
{
  struct _EXCEPTION_RECORD *v3; // rdx
  unsigned int v4; // r9d
  __int64 v5; // rcx
  __int64 v6; // rax
  _QWORD v7[21]; // [rsp+20h] [rbp-A8h] BYREF

  if ( wil::g_pfnWilFailFast )
    wil::g_pfnWilFailFast(this, a2);
  if ( wil::details::g_pfnFailfastWithContextCallback )
    wil::details::g_pfnFailfastWithContextCallback(this, a2);
  memset(v7, 0, 0x98u);
  v5 = *((_QWORD *)this + 17);
  LODWORD(v7[3]) = 1;
  v7[0] = 0x1C0000409LL;
  v7[4] = 7;
  if ( !v5 )
    wil::details::WilRaiseFailFastException((wil::details *)v7, v3, (struct _CONTEXT *)1, v4);
  v7[5] = *((int *)this + 2);
  v6 = *((unsigned int *)this + 16);
  v7[2] = v5;
  v7[6] = v6;
  LODWORD(v7[3]) = 3;
  wil::details::WilRaiseFailFastException((wil::details *)v7, v3, 0, v4);
}

```

## disassembly

```asm
0x1400029fc  push    rbx
0x1400029fe  sub     rsp, 0C0h
0x140002a05  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x140002a0c  mov     rbx, rcx
0x140002a0f  test    rax, rax
0x140002a12  jz      short loc_140002A19
0x140002a14  call    _guard_dispatch_icall
0x140002a19  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002a20  test    rax, rax
0x140002a23  jz      short loc_140002A2D
0x140002a25  mov     rcx, rbx
0x140002a28  call    _guard_dispatch_icall
0x140002a2d  xor     edx, edx; Val
0x140002a2f  lea     rcx, [rsp+0C8h+var_A8]; void *
0x140002a34  mov     r8d, 98h; Size
0x140002a3a  call    memset
0x140002a3f  mov     rcx, [rbx+88h]
0x140002a46  mov     r8d, 1; struct _CONTEXT *
0x140002a4c  mov     [rsp+0C8h+var_90], r8d
0x140002a51  mov     [rsp+0C8h+var_A8], 0C0000409h
0x140002a59  mov     [rsp+0C8h+var_A4], r8d
0x140002a5e  mov     [rsp+0C8h+var_88], 7
0x140002a67  test    rcx, rcx
0x140002a6a  jnz     short loc_140002A77
0x140002a6c  lea     rcx, [rsp+0C8h+var_A8]; this
0x140002a71  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x140002a77  movsxd  rax, dword ptr [rbx+8]
0x140002a7b  xor     r8d, r8d; struct _CONTEXT *
0x140002a7e  mov     [rsp+0C8h+var_80], rax
0x140002a83  mov     eax, [rbx+40h]
0x140002a86  mov     [rsp+0C8h+var_98], rcx
0x140002a8b  lea     rcx, [rsp+0C8h+var_A8]; this
0x140002a90  mov     [rsp+0C8h+var_78], rax
0x140002a95  mov     [rsp+0C8h+var_90], 3
0x140002a9d  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
