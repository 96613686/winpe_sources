# LogProvider::NgcIsoContainerDeauthenticate::StartActivity(NgcDeauthenticationReason)

- ea: `0x18003168c`
- end: `0x180031851`
- name: `?StartActivity@NgcIsoContainerDeauthenticate@LogProvider@@QEAAXW4NgcDeauthenticationReason@@@Z`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002f4d0`

## callees

- `0x1800037c0`
- `0x18001133c`
- `0x180013da4`
- `0x180016828`
- `0x1800168a0`
- `0x18003168c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800316d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031730`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003178d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800317e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800316d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031730`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003178d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800317e3`

## pseudocode

```c
__int64 __fastcall LogProvider::NgcIsoContainerDeauthenticate::StartActivity(__int64 a1, int a2)
{
  int v3; // edx
  const struct _tlgProvider_t *v4; // rdi
  DWORD v5; // eax
  __int64 v6; // r8
  int v7; // ecx
  char *v8; // rdx
  DWORD CurrentThreadId; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  DWORD v13; // [rsp+68h] [rbp+28h] BYREF
  const char *v14; // [rsp+70h] [rbp+30h] BYREF
  __int64 v15; // [rsp+78h] [rbp+38h] BYREF

  if ( a2 )
  {
    v3 = a2 - 1;
    if ( v3 )
    {
      if ( v3 == 1 )
      {
        wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
        v4 = LogProvider::Provider();
        if ( *(_DWORD *)v4 > 5u )
        {
          v14 = "SignOut";
          CurrentThreadId = GetCurrentThreadId();
          v6 = *(_QWORD *)(a1 + 272);
          v13 = CurrentThreadId;
          v15 = 0;
          if ( !*(_BYTE *)(v6 + 4) || _tlgGuidIsZero((const struct _GUID *)(v6 + 24)) )
            v7 = 0;
          v8 = byte_1800AE0E3;
          goto LABEL_24;
        }
      }
      else
      {
        wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
        v4 = LogProvider::Provider();
        if ( *(_DWORD *)v4 > 5u )
        {
          v14 = "Unknown";
          v5 = GetCurrentThreadId();
          v6 = *(_QWORD *)(a1 + 272);
          v13 = v5;
          v15 = 0;
          if ( !*(_BYTE *)(v6 + 4) || _tlgGuidIsZero((const struct _GUID *)(v6 + 24)) )
            v7 = 0;
          v8 = (char *)word_1800AE1FA;
LABEL_24:
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (_DWORD)v4,
            (_DWORD)v8,
            v6 + 8,
            v7,
            (__int64)&v15,
            (__int64)&v13,
            (__int64)&v14);
        }
      }
    }
    else
    {
      wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
      v4 = LogProvider::Provider();
      if ( *(_DWORD *)v4 > 5u )
      {
        v14 = "Lock";
        v10 = GetCurrentThreadId();
        v6 = *(_QWORD *)(a1 + 272);
        v13 = v10;
        v15 = 0;
        if ( !*(_BYTE *)(v6 + 4) || _tlgGuidIsZero((const struct _GUID *)(v6 + 24)) )
          v7 = 0;
        v8 = (char *)&unk_1800AE140;
        goto LABEL_24;
      }
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
    v4 = LogProvider::Provider();
    if ( *(_DWORD *)v4 > 5u )
    {
      v14 = "DeauthenticateTicket";
      v11 = GetCurrentThreadId();
      v6 = *(_QWORD *)(a1 + 272);
      v13 = v11;
      v15 = 0;
      if ( !*(_BYTE *)(v6 + 4) || _tlgGuidIsZero((const struct _GUID *)(v6 + 24)) )
        v7 = 0;
      v8 = byte_1800AE19D;
      goto LABEL_24;
    }
  }
  return wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(a1);
}

```

## disassembly

```asm
0x18003168c  push    rbp
0x18003168e  push    rbx
0x18003168f  push    rdi
0x180031690  mov     rbp, rsp
0x180031693  sub     rsp, 40h
0x180031697  mov     rbx, rcx
0x18003169a  test    edx, edx
0x18003169c  jz      loc_1800317C4
0x1800316a2  sub     edx, 1
0x1800316a5  jz      loc_18003176A
0x1800316ab  cmp     edx, 1
0x1800316ae  jz      short loc_18003170D
0x1800316b0  call    ?zInternalStart@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800316b5  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x1800316ba  mov     rdi, rax
0x1800316bd  mov     ecx, [rax]
0x1800316bf  cmp     ecx, 5
0x1800316c2  jbe     loc_180031842
0x1800316c8  lea     rax, aUnknown; "Unknown"
0x1800316cf  mov     [rbp+arg_10], rax
0x1800316d3  call    cs:__imp_GetCurrentThreadId
0x1800316d9  mov     r8, [rbx+110h]
0x1800316e0  mov     [rbp+arg_8], eax
0x1800316e3  mov     [rbp+arg_18], 0
0x1800316eb  cmp     byte ptr [r8+4], 0
0x1800316f0  jz      short loc_1800316FF
0x1800316f2  lea     rcx, [r8+18h]; struct _GUID *
0x1800316f6  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800316fb  test    al, al
0x1800316fd  jz      short loc_180031701
0x1800316ff  xor     ecx, ecx
0x180031701  lea     rdx, word_1800AE1FA
0x180031708  jmp     loc_180031818
0x18003170d  call    ?zInternalStart@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180031712  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x180031717  mov     rdi, rax
0x18003171a  mov     ecx, [rax]
0x18003171c  cmp     ecx, 5
0x18003171f  jbe     loc_180031842
0x180031725  lea     rax, aSignout; "SignOut"
0x18003172c  mov     [rbp+arg_10], rax
0x180031730  call    cs:__imp_GetCurrentThreadId
0x180031736  mov     r8, [rbx+110h]
0x18003173d  mov     [rbp+arg_8], eax
0x180031740  mov     [rbp+arg_18], 0
0x180031748  cmp     byte ptr [r8+4], 0
0x18003174d  jz      short loc_18003175C
0x18003174f  lea     rcx, [r8+18h]; struct _GUID *
0x180031753  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180031758  test    al, al
0x18003175a  jz      short loc_18003175E
0x18003175c  xor     ecx, ecx
0x18003175e  lea     rdx, byte_1800AE0E3
0x180031765  jmp     loc_180031818
0x18003176a  call    ?zInternalStart@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18003176f  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x180031774  mov     rdi, rax
0x180031777  mov     ecx, [rax]
0x180031779  cmp     ecx, 5
0x18003177c  jbe     loc_180031842
0x180031782  lea     rax, aLock; "Lock"
0x180031789  mov     [rbp+arg_10], rax
0x18003178d  call    cs:__imp_GetCurrentThreadId
0x180031793  mov     r8, [rbx+110h]
0x18003179a  mov     [rbp+arg_8], eax
0x18003179d  mov     [rbp+arg_18], 0
0x1800317a5  cmp     byte ptr [r8+4], 0
0x1800317aa  jz      short loc_1800317B9
0x1800317ac  lea     rcx, [r8+18h]; struct _GUID *
0x1800317b0  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800317b5  test    al, al
0x1800317b7  jz      short loc_1800317BB
0x1800317b9  xor     ecx, ecx
0x1800317bb  lea     rdx, unk_1800AE140
0x1800317c2  jmp     short loc_180031818
0x1800317c4  call    ?zInternalStart@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800317c9  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x1800317ce  mov     rdi, rax
0x1800317d1  mov     ecx, [rax]
0x1800317d3  cmp     ecx, 5
0x1800317d6  jbe     short loc_180031842
0x1800317d8  lea     rax, aDeauthenticate; "DeauthenticateTicket"
0x1800317df  mov     [rbp+arg_10], rax
0x1800317e3  call    cs:__imp_GetCurrentThreadId
0x1800317e9  mov     r8, [rbx+110h]
0x1800317f0  mov     [rbp+arg_8], eax
0x1800317f3  mov     [rbp+arg_18], 0
0x1800317fb  cmp     byte ptr [r8+4], 0
0x180031800  jz      short loc_18003180F
0x180031802  lea     rcx, [r8+18h]; struct _GUID *
0x180031806  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18003180b  test    al, al
0x18003180d  jz      short loc_180031811
0x18003180f  xor     ecx, ecx
0x180031811  lea     rdx, byte_1800AE19D
0x180031818  lea     rax, [rbp+arg_10]
0x18003181c  mov     r9, rcx
0x18003181f  mov     [rsp+40h+var_10], rax
0x180031824  add     r8, 8
0x180031828  lea     rax, [rbp+arg_8]
0x18003182c  mov     rcx, rdi
0x18003182f  mov     [rsp+40h+var_18], rax
0x180031834  lea     rax, [rbp+arg_18]
0x180031838  mov     [rsp+40h+var_20], rax
0x18003183d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180031842  mov     rcx, rbx
0x180031845  add     rsp, 40h
0x180031849  pop     rdi
0x18003184a  pop     rbx
0x18003184b  pop     rbp
0x18003184c  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
