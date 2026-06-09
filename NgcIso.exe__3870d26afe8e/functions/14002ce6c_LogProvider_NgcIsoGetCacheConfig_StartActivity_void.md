# LogProvider::NgcIsoGetCacheConfig::StartActivity(void)

- ea: `0x14002ce6c`
- end: `0x14002cf11`
- name: `?StartActivity@NgcIsoGetCacheConfig@LogProvider@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(LogProvider::NgcIsoGetCacheConfig *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140026860`

## callees

- `0x1400030b4`
- `0x14000330c`
- `0x14000c558`
- `0x140016428`
- `0x1400173a0`
- `0x140017478`
- `0x14002ce6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002cea3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002cea3`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoGetCacheConfig::StartActivity(LogProvider::NgcIsoGetCacheConfig *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  __int64 v4; // r8
  int v5; // ecx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = LogProvider::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 4u && (unsigned __int8)tlgKeywordOn(v2, 0x400000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = 0x1000000;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4) || _tlgGuidIsZero((const struct _GUID *)(v4 + 24)) )
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)&byte_1400845CF,
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
0x14002ce6c  mov     [rsp+arg_10], rbx
0x14002ce71  push    rdi
0x14002ce72  sub     rsp, 30h
0x14002ce76  mov     rbx, rcx
0x14002ce79  call    ?zInternalStart@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x14002ce7e  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002ce83  mov     rdi, rax
0x14002ce86  mov     edx, [rax]
0x14002ce88  cmp     edx, 4
0x14002ce8b  jbe     short loc_14002CEFD
0x14002ce8d  mov     rdx, 400000000000h
0x14002ce97  mov     rcx, rax
0x14002ce9a  call    _tlgKeywordOn
0x14002ce9f  test    al, al
0x14002cea1  jz      short loc_14002CEFD
0x14002cea3  call    cs:__imp_GetCurrentThreadId
0x14002cea9  mov     [rsp+38h+arg_0], eax
0x14002cead  mov     [rsp+38h+arg_8], 1000000h
0x14002ceb6  mov     r8, [rbx+110h]
0x14002cebd  cmp     byte ptr [r8+4], 0
0x14002cec2  jz      short loc_14002CED1
0x14002cec4  lea     rcx, [r8+18h]; struct _GUID *
0x14002cec8  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x14002cecd  test    al, al
0x14002cecf  jz      short loc_14002CED3
0x14002ced1  xor     ecx, ecx
0x14002ced3  add     r8, 8
0x14002ced7  lea     rax, [rsp+38h+arg_0]
0x14002cedc  mov     [rsp+38h+var_10], rax
0x14002cee1  lea     rax, [rsp+38h+arg_8]
0x14002cee6  mov     [rsp+38h+var_18], rax
0x14002ceeb  mov     r9, rcx
0x14002ceee  lea     rdx, byte_1400845CF
0x14002cef5  mov     rcx, rdi
0x14002cef8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x14002cefd  mov     rcx, rbx
0x14002cf00  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x14002cf05  nop
0x14002cf06  mov     rbx, [rsp+38h+arg_10]
0x14002cf0b  add     rsp, 30h
0x14002cf0f  pop     rdi
0x14002cf10  retn
```
