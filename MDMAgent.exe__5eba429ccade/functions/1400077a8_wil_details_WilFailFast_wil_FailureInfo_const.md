# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x1400077a8`
- end: `0x14000784f`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140003d44`
- `0x140003e04`
- `0x1400040b0`
- `0x140016920`
- `0x140016b48`

## callees

- `0x14000349c`
- `0x1400077a8`
- `0x140007938`
- `0x140019010`

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
0x1400077a8  push    rbx
0x1400077aa  sub     rsp, 0C0h
0x1400077b1  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x1400077b8  mov     rbx, rcx
0x1400077bb  test    rax, rax
0x1400077be  jz      short loc_1400077C5
0x1400077c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400077c5  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400077cc  test    rax, rax
0x1400077cf  jz      short loc_1400077D9
0x1400077d1  mov     rcx, rbx
0x1400077d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400077d9  xor     edx, edx; Val
0x1400077db  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1400077e0  mov     r8d, 98h; Size
0x1400077e6  call    memset_0
0x1400077eb  mov     rcx, [rbx+88h]
0x1400077f2  mov     r8d, 1; struct _CONTEXT *
0x1400077f8  mov     [rsp+0C8h+var_90], r8d
0x1400077fd  mov     [rsp+0C8h+var_A8], 0C0000409h
0x140007805  mov     [rsp+0C8h+var_A4], r8d
0x14000780a  mov     [rsp+0C8h+var_88], 7
0x140007813  test    rcx, rcx
0x140007816  jnz     short loc_140007823
0x140007818  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000781d  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x140007823  movsxd  rax, dword ptr [rbx+8]
0x140007827  xor     r8d, r8d; struct _CONTEXT *
0x14000782a  mov     [rsp+0C8h+var_80], rax
0x14000782f  mov     eax, [rbx+40h]
0x140007832  mov     [rsp+0C8h+var_98], rcx
0x140007837  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000783c  mov     [rsp+0C8h+var_78], rax
0x140007841  mov     [rsp+0C8h+var_90], 3
0x140007849  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
