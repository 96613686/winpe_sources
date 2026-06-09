# HostNameVerifierProvider::VerifyFromWeb::StartActivity(ushort const *,ushort const *)

- ea: `0x14000e1e0`
- end: `0x14000e2cb`
- name: `?StartActivity@VerifyFromWeb@HostNameVerifierProvider@@QEAAXPEBG0@Z`
- size: `235`
- prototype: `void __fastcall(HostNameVerifierProvider::VerifyFromWeb *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000ed9c`

## callees

- `0x1400018f8`
- `0x140001b4c`
- `0x14000b0f0`
- `0x14000da38`
- `0x14000e1e0`
- `0x140010c80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e236`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e236`

## pseudocode

```c
void __fastcall HostNameVerifierProvider::VerifyFromWeb::StartActivity(
        HostNameVerifierProvider::VerifyFromWeb *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rcx
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  int *v13; // [rsp+40h] [rbp-28h] BYREF
  __int64 v14[4]; // [rsp+48h] [rbp-20h] BYREF
  DWORD v15; // [rsp+70h] [rbp+8h] BYREF
  int *v16; // [rsp+88h] [rbp+20h] BYREF

  wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v7 = HostNameVerifierProvider::Provider(v6);
  v9 = (__int64)v7;
  if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL, v8) )
  {
    v16 = (int *)a3;
    v13 = (int *)a2;
    CurrentThreadId = GetCurrentThreadId();
    v11 = *((_QWORD *)this + 34);
    v15 = CurrentThreadId;
    v14[0] = 0x1000000;
    if ( !*(_BYTE *)(v11 + 4)
      || (v12 = v11 + 24, !*(_DWORD *)(v11 + 24))
      && !*(_DWORD *)(v11 + 28)
      && !*(_DWORD *)(v11 + 32)
      && !*(_DWORD *)(v11 + 36) )
    {
      v12 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v9,
      (__int64)byte_140015DC3,
      v11 + 8,
      v12,
      (__int64)v14,
      (__int64)&v15,
      &v13,
      &v16);
  }
  wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x14000e1e0  mov     [rsp+arg_8], rbx
0x14000e1e5  push    rbp
0x14000e1e6  push    rsi
0x14000e1e7  push    rdi
0x14000e1e8  sub     rsp, 50h
0x14000e1ec  mov     rsi, r8
0x14000e1ef  mov     rbp, rdx
0x14000e1f2  mov     rbx, rcx
0x14000e1f5  call    ?zInternalStart@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x14000e1fa  call    ?Provider@HostNameVerifierProvider@@SAPEBU_tlgProvider_t@@XZ; HostNameVerifierProvider::Provider(void)
0x14000e1ff  mov     rdi, rax
0x14000e202  mov     r9d, [rax]
0x14000e205  cmp     r9d, 5
0x14000e209  jbe     loc_14000E2B7
0x14000e20f  mov     rdx, 400000000000h
0x14000e219  mov     rcx, rax
0x14000e21c  call    _tlgKeywordOn
0x14000e221  test    al, al
0x14000e223  jz      loc_14000E2B7
0x14000e229  mov     [rsp+68h+arg_18], rsi
0x14000e231  mov     [rsp+68h+var_28], rbp
0x14000e236  call    cs:__imp_GetCurrentThreadId
0x14000e23c  mov     r8, [rbx+110h]
0x14000e243  mov     [rsp+68h+arg_0], eax
0x14000e247  mov     [rsp+68h+var_20], 1000000h
0x14000e250  cmp     byte ptr [r8+4], 0
0x14000e255  jz      short loc_14000E276
0x14000e257  lea     r9, [r8+18h]
0x14000e25b  cmp     dword ptr [r9], 0
0x14000e25f  jnz     short loc_14000E279
0x14000e261  cmp     dword ptr [r9+4], 0
0x14000e266  jnz     short loc_14000E279
0x14000e268  cmp     dword ptr [r9+8], 0
0x14000e26d  jnz     short loc_14000E279
0x14000e26f  cmp     dword ptr [r9+0Ch], 0
0x14000e274  jnz     short loc_14000E279
0x14000e276  xor     r9d, r9d
0x14000e279  lea     rax, [rsp+68h+arg_18]
0x14000e281  add     r8, 8
0x14000e285  mov     [rsp+68h+var_30], rax
0x14000e28a  lea     rdx, byte_140015DC3
0x14000e291  lea     rax, [rsp+68h+var_28]
0x14000e296  mov     rcx, rdi
0x14000e299  mov     [rsp+68h+var_38], rax
0x14000e29e  lea     rax, [rsp+68h+arg_0]
0x14000e2a3  mov     [rsp+68h+var_40], rax
0x14000e2a8  lea     rax, [rsp+68h+var_20]
0x14000e2ad  mov     [rsp+68h+var_48], rax
0x14000e2b2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14000e2b7  mov     rcx, rbx
0x14000e2ba  mov     rbx, [rsp+68h+arg_8]
0x14000e2bf  add     rsp, 50h
0x14000e2c3  pop     rdi
0x14000e2c4  pop     rsi
0x14000e2c5  pop     rbp
0x14000e2c6  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
