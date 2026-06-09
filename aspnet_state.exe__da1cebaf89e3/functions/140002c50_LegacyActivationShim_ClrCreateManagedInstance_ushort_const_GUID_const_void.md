# LegacyActivationShim::ClrCreateManagedInstance(ushort const *,_GUID const &,void * *)

- ea: `0x140002c50`
- end: `0x140002d1d`
- name: `?ClrCreateManagedInstance@LegacyActivationShim@@YAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `205`
- prototype: `int __fastcall(LegacyActivationShim *this, struct ICLRMetaHost **, const struct _GUID *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140002d20`

## callees

- `0x140002c50`
- `0x140002dfc`
- `0x1400032c4`
- `0x140004efa`
- `0x140006590`

## string_xrefs

- `0x140002cc8`: `ClrCreateManagedInstance`

## pseudocode

```c
int __fastcall LegacyActivationShim::ClrCreateManagedInstance(
        LegacyActivationShim *this,
        struct ICLRMetaHost **a2,
        const struct _GUID *a3,
        unsigned __int64 a4)
{
  unsigned int v4; // eax
  int result; // eax
  __int64 v9; // rcx
  unsigned int *v10; // [rsp+28h] [rbp-20h]
  _QWORD v11[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 *v12; // [rsp+68h] [rbp+20h] BYREF

  v4 = LegacyActivationShim::Util::g_fHasNewActivationAPIs;
  if ( LegacyActivationShim::Util::g_fHasNewActivationAPIs == -1 )
  {
    a4 = (int)LegacyActivationShim::Util::GetCLRMetaHost((LegacyActivationShim::Util *)&v12, a2) >= 0;
    _InterlockedCompareExchange((volatile signed __int32 *)&LegacyActivationShim::Util::g_fHasNewActivationAPIs, a4, -1);
    v4 = LegacyActivationShim::Util::g_fHasNewActivationAPIs;
  }
  if ( !v4 )
    return ClrCreateManagedInstance_0(this, a2, a3, a4);
  v12 = 0;
  result = LegacyActivationShim::Util::GetRuntimeInfo((LegacyActivationShim::Util *)&v12, 0, 0, 0, 0, v10);
  if ( result >= 0 )
  {
    v9 = *v12;
    v11[0] = 0;
    result = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD *))(*(_QWORD *)v9 + 64LL))(
               v9,
               "ClrCreateManagedInstance",
               v11);
    if ( result >= 0 )
      return ((__int64 (__fastcall *)(LegacyActivationShim *, struct ICLRMetaHost **, const struct _GUID *))v11[0])(
               this,
               a2,
               a3);
  }
  return result;
}

```

## disassembly

```asm
0x140002c50  mov     [rsp+arg_0], rbx
0x140002c55  mov     [rsp+arg_8], rsi
0x140002c5a  push    rdi
0x140002c5b  sub     rsp, 40h
0x140002c5f  mov     eax, cs:?g_fHasNewActivationAPIs@Util@LegacyActivationShim@@3KA; ulong LegacyActivationShim::Util::g_fHasNewActivationAPIs
0x140002c65  mov     rbx, r8
0x140002c68  mov     rdi, rdx
0x140002c6b  mov     rsi, rcx
0x140002c6e  cmp     eax, 0FFFFFFFFh
0x140002c71  jnz     short loc_140002C98
0x140002c73  lea     rcx, [rsp+48h+arg_18]; this
0x140002c78  call    ?GetCLRMetaHost@Util@LegacyActivationShim@@YAJPEAPEAUICLRMetaHost@@@Z; LegacyActivationShim::Util::GetCLRMetaHost(ICLRMetaHost * *)
0x140002c7d  xor     r9d, r9d
0x140002c80  test    eax, eax
0x140002c82  setns   r9b
0x140002c86  or      eax, 0FFFFFFFFh
0x140002c89  lock cmpxchg cs:?g_fHasNewActivationAPIs@Util@LegacyActivationShim@@3KA, r9d; ulong LegacyActivationShim::Util::g_fHasNewActivationAPIs
0x140002c92  mov     eax, cs:?g_fHasNewActivationAPIs@Util@LegacyActivationShim@@3KA; ulong LegacyActivationShim::Util::g_fHasNewActivationAPIs
0x140002c98  test    eax, eax
0x140002c9a  jz      short loc_140002CFF
0x140002c9c  and     [rsp+48h+arg_18], 0
0x140002ca2  lea     rcx, [rsp+48h+arg_18]; this
0x140002ca7  and     [rsp+48h+var_28], 0
0x140002cad  xor     r9d, r9d; struct IStream *
0x140002cb0  xor     r8d, r8d; unsigned __int16 *
0x140002cb3  xor     edx, edx; struct LegacyActivationShim::Util::RuntimeInfo **
0x140002cb5  call    ?GetRuntimeInfo@Util@LegacyActivationShim@@YAJPEAPEAURuntimeInfo@12@PEBGPEAUIStream@@PEAGPEAK@Z; LegacyActivationShim::Util::GetRuntimeInfo(LegacyActivationShim::Util::RuntimeInfo * *,ushort const *,IStream *,ushort *,ulong *)
0x140002cba  test    eax, eax
0x140002cbc  js      short loc_140002D0D
0x140002cbe  mov     rax, [rsp+48h+arg_18]
0x140002cc3  lea     r8, [rsp+48h+var_18]
0x140002cc8  lea     rdx, aClrcreatemanag; "ClrCreateManagedInstance"
0x140002ccf  mov     rcx, [rax]
0x140002cd2  and     [rsp+48h+var_18], 0
0x140002cd8  mov     rax, [rcx]
0x140002cdb  mov     rax, [rax+40h]
0x140002cdf  call    cs:__guard_dispatch_icall_fptr
0x140002ce5  test    eax, eax
0x140002ce7  js      short loc_140002D0D
0x140002ce9  mov     rax, [rsp+48h+var_18]
0x140002cee  mov     r8, rbx
0x140002cf1  mov     rdx, rdi
0x140002cf4  mov     rcx, rsi
0x140002cf7  call    cs:__guard_dispatch_icall_fptr
0x140002cfd  jmp     short loc_140002D0D
0x140002cff  mov     r8, rbx
0x140002d02  mov     rdx, rdi
0x140002d05  mov     rcx, rsi
0x140002d08  call    ClrCreateManagedInstance_0
0x140002d0d  mov     rbx, [rsp+48h+arg_0]
0x140002d12  mov     rsi, [rsp+48h+arg_8]
0x140002d17  add     rsp, 40h
0x140002d1b  pop     rdi
0x140002d1c  retn
```
