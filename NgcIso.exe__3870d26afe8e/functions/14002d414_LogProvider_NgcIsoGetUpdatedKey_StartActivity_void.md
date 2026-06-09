# LogProvider::NgcIsoGetUpdatedKey::StartActivity(void)

- ea: `0x14002d414`
- end: `0x14002d4a3`
- name: `?StartActivity@NgcIsoGetUpdatedKey@LogProvider@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(LogProvider::NgcIsoGetUpdatedKey *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140027dd0`

## callees

- `0x1400030b4`
- `0x14000c558`
- `0x140016428`
- `0x1400173a0`
- `0x14002d414`
- `0x14003b088`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002d435`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002d435`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoGetUpdatedKey::StartActivity(LogProvider::NgcIsoGetUpdatedKey *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  __int64 v4; // r8
  int v5; // ecx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = LogProvider::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 4u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = 0;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4) || _tlgGuidIsZero((const struct _GUID *)(v4 + 24)) )
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)&dword_140084764,
      v4 + 8,
      v5,
      (__int64)&v7,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x14002d414  mov     [rsp+arg_10], rbx
0x14002d419  push    rdi
0x14002d41a  sub     rsp, 30h
0x14002d41e  mov     rbx, rcx
0x14002d421  call    ?zInternalStart@?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x14002d426  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002d42b  mov     rdi, rax
0x14002d42e  mov     edx, [rax]
0x14002d430  cmp     edx, 4
0x14002d433  jbe     short loc_14002D48F
0x14002d435  call    cs:__imp_GetCurrentThreadId
0x14002d43b  mov     [rsp+38h+arg_0], eax
0x14002d43f  mov     [rsp+38h+arg_8], 0
0x14002d448  mov     r8, [rbx+110h]
0x14002d44f  cmp     byte ptr [r8+4], 0
0x14002d454  jz      short loc_14002D463
0x14002d456  lea     rcx, [r8+18h]; struct _GUID *
0x14002d45a  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x14002d45f  test    al, al
0x14002d461  jz      short loc_14002D465
0x14002d463  xor     ecx, ecx
0x14002d465  add     r8, 8
0x14002d469  lea     rax, [rsp+38h+arg_0]
0x14002d46e  mov     [rsp+38h+var_10], rax
0x14002d473  lea     rax, [rsp+38h+arg_8]
0x14002d478  mov     [rsp+38h+var_18], rax
0x14002d47d  mov     r9, rcx
0x14002d480  lea     rdx, dword_140084764
0x14002d487  mov     rcx, rdi
0x14002d48a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x14002d48f  mov     rcx, rbx
0x14002d492  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x14002d497  nop
0x14002d498  mov     rbx, [rsp+38h+arg_10]
0x14002d49d  add     rsp, 30h
0x14002d4a1  pop     rdi
0x14002d4a2  retn
```
