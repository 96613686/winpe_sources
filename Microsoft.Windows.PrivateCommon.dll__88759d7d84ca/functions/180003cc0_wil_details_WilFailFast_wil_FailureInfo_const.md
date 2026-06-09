# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180003cc0`
- end: `0x180003da0`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `224`
- prototype: `void __fastcall __noreturn(wil::details *this, struct _EXCEPTION_RECORD *, __int64, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180004f10`
- `0x180005300`
- `0x1800053e0`

## callees

- `0x1800027d0`
- `0x180003cc0`
- `0x18000b930`

## pseudocode

```c
void __fastcall __noreturn wil::details::WilFailFast(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        __int64 a3,
        unsigned int a4)
{
  __int64 v5; // rcx
  __int64 v6; // rax
  __int128 v7; // [rsp+20h] [rbp-A8h] BYREF
  __int128 v8; // [rsp+30h] [rbp-98h]
  __int128 v9; // [rsp+40h] [rbp-88h]
  __int128 v10; // [rsp+50h] [rbp-78h]
  __int128 v11; // [rsp+60h] [rbp-68h]
  __int128 v12; // [rsp+70h] [rbp-58h]
  __int128 v13; // [rsp+80h] [rbp-48h]
  __int128 v14; // [rsp+90h] [rbp-38h]
  __int128 v15; // [rsp+A0h] [rbp-28h]
  __int64 v16; // [rsp+B0h] [rbp-18h]

  if ( wil::g_pfnWilFailFast )
    wil::g_pfnWilFailFast(this, a2);
  if ( wil::details::g_pfnFailfastWithContextCallback )
    wil::details::g_pfnFailfastWithContextCallback(this, a2);
  v5 = *((_QWORD *)this + 17);
  v16 = 0;
  v7 = 0x1C0000409uLL;
  v8 = 0;
  DWORD2(v8) = 1;
  v9 = 7u;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  if ( !v5 )
    wil::details::WilRaiseFailFastException((wil::details *)&v7, a2, (struct _CONTEXT *)1, a4);
  *((_QWORD *)&v9 + 1) = *((int *)this + 2);
  v6 = *((unsigned int *)this + 16);
  *(_QWORD *)&v8 = v5;
  *(_QWORD *)&v10 = v6;
  DWORD2(v8) = 3;
  wil::details::WilRaiseFailFastException((wil::details *)&v7, a2, 0, a4);
}

```

## disassembly

```asm
0x180003cc0  push    rbx
0x180003cc2  sub     rsp, 0C0h
0x180003cc9  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180003cd0  mov     rbx, rcx
0x180003cd3  test    rax, rax
0x180003cd6  jz      short loc_180003CDE
0x180003cd8  call    cs:__guard_dispatch_icall_fptr
0x180003cde  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003ce5  test    rax, rax
0x180003ce8  jz      short loc_180003CF3
0x180003cea  mov     rcx, rbx
0x180003ced  call    cs:__guard_dispatch_icall_fptr
0x180003cf3  mov     rcx, [rbx+88h]
0x180003cfa  xorps   xmm0, xmm0
0x180003cfd  xor     eax, eax
0x180003cff  mov     [rsp+0C8h+var_18], rax
0x180003d07  movups  [rsp+0C8h+var_A8], xmm0
0x180003d0c  mov     dword ptr [rsp+0C8h+var_A8], 0C0000409h
0x180003d14  mov     dword ptr [rsp+0C8h+var_A8+4], 1
0x180003d1c  movups  [rsp+0C8h+var_98], xmm0
0x180003d21  mov     dword ptr [rsp+0C8h+var_98+8], 1
0x180003d29  movups  [rsp+0C8h+var_88], xmm0
0x180003d2e  mov     qword ptr [rsp+0C8h+var_88], 7
0x180003d37  movups  [rsp+0C8h+var_78], xmm0
0x180003d3c  movups  [rsp+0C8h+var_68], xmm0
0x180003d41  movups  [rsp+0C8h+var_58], xmm0
0x180003d46  movups  [rsp+0C8h+var_48], xmm0
0x180003d4e  movups  [rsp+0C8h+var_38], xmm0
0x180003d56  movups  [rsp+0C8h+var_28], xmm0
0x180003d5e  test    rcx, rcx
0x180003d61  jnz     short loc_180003D74
0x180003d63  mov     r8d, 1; struct _CONTEXT *
0x180003d69  lea     rcx, [rsp+0C8h+var_A8]; this
0x180003d6e  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x180003d74  movsxd  rax, dword ptr [rbx+8]
0x180003d78  xor     r8d, r8d; struct _CONTEXT *
0x180003d7b  mov     qword ptr [rsp+0C8h+var_88+8], rax
0x180003d80  mov     eax, [rbx+40h]
0x180003d83  mov     qword ptr [rsp+0C8h+var_98], rcx
0x180003d88  lea     rcx, [rsp+0C8h+var_A8]; this
0x180003d8d  mov     qword ptr [rsp+0C8h+var_78], rax
0x180003d92  mov     dword ptr [rsp+0C8h+var_98+8], 3
0x180003d9a  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
