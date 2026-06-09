# MDMPushProvider::InitializeActivity::StartActivity(void)

- ea: `0x140017760`
- end: `0x1400177f6`
- name: `?StartActivity@InitializeActivity@MDMPushProvider@@QEAAXXZ`
- size: `150`
- prototype: `void __fastcall(MDMPushProvider::InitializeActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140016a28`

## callees

- `0x14000162c`
- `0x1400167e0`
- `0x140017078`
- `0x140017760`
- `0x140018098`
- `0x1400181d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140017781`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140017781`

## pseudocode

```c
void __fastcall MDMPushProvider::InitializeActivity::StartActivity(MDMPushProvider::InitializeActivity *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  __int64 v4; // r8
  int v5; // ecx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = MDMPushProvider::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = 0;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4) || _tlgGuidIsZero((const struct _GUID *)(v4 + 24)) )
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)&unk_1400201E8,
      v4 + 8,
      v5,
      (__int64)&v7,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x140017760  mov     [rsp+arg_10], rbx
0x140017765  push    rdi
0x140017766  sub     rsp, 30h
0x14001776a  mov     rbx, rcx
0x14001776d  call    ?zInternalStart@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140017772  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140017777  mov     rdi, rax
0x14001777a  mov     edx, [rax]
0x14001777c  cmp     edx, 5
0x14001777f  jbe     short loc_1400177E1
0x140017781  call    cs:__imp_GetCurrentThreadId
0x140017788  nop     dword ptr [rax+rax+00h]
0x14001778d  mov     [rsp+38h+arg_0], eax
0x140017791  mov     [rsp+38h+arg_8], 0
0x14001779a  mov     r8, [rbx+110h]
0x1400177a1  cmp     byte ptr [r8+4], 0
0x1400177a6  jz      short loc_1400177B5
0x1400177a8  lea     rcx, [r8+18h]; struct _GUID *
0x1400177ac  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1400177b1  test    al, al
0x1400177b3  jz      short loc_1400177B7
0x1400177b5  xor     ecx, ecx
0x1400177b7  add     r8, 8
0x1400177bb  lea     rax, [rsp+38h+arg_0]
0x1400177c0  mov     [rsp+38h+var_10], rax
0x1400177c5  lea     rax, [rsp+38h+arg_8]
0x1400177ca  mov     [rsp+38h+var_18], rax
0x1400177cf  mov     r9, rcx
0x1400177d2  lea     rdx, unk_1400201E8
0x1400177d9  mov     rcx, rdi
0x1400177dc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1400177e1  mov     rcx, rbx
0x1400177e4  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1400177e9  nop
0x1400177ea  mov     rbx, [rsp+38h+arg_10]
0x1400177ef  add     rsp, 30h
0x1400177f3  pop     rdi
0x1400177f4  retn
```
