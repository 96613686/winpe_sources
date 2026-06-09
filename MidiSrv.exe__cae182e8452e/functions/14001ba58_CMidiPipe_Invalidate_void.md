# CMidiPipe::Invalidate(void)

- ea: `0x14001ba58`
- end: `0x14001bbce`
- name: `?Invalidate@CMidiPipe@@QEAAXXZ`
- size: `374`
- prototype: `void __fastcall(CMidiPipe *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001bf60`

## callees

- `0x140001ce8`
- `0x14000984c`
- `0x14001ba58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001bae1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001bae1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001bbbd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001bbbd`

## string_xrefs

- `0x14001bb6e`: `Invalidate() called but pipe already invalid`

## pseudocode

```c
void __fastcall CMidiPipe::Invalidate(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  _DWORD *v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  RTL_SRWLOCK *Ptr; // rax
  _DWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  _DWORD *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  RTL_SRWLOCK *v13; // [rsp+70h] [rbp+30h] BYREF
  const wchar_t *v14; // [rsp+78h] [rbp+38h] BYREF
  RTL_SRWLOCK *v15; // [rsp+80h] [rbp+40h] BYREF
  const char *v16; // [rsp+88h] [rbp+48h] BYREF

  v2 = this + 2;
  v3 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v3 > 4u )
  {
    if ( this[5].Ptr <= (PVOID)7 )
      Ptr = this + 2;
    else
      Ptr = (RTL_SRWLOCK *)v2->Ptr;
    v13 = Ptr;
    v15 = this;
    v14 = L"Enter";
    v16 = "CMidiPipe::Invalidate";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v3,
      (__int64)&byte_1400880A7,
      v4,
      v5,
      &v16,
      (__int64)&v15,
      &v14,
      &v13);
  }
  AcquireSRWLockExclusive(this + 8);
  if ( LOBYTE(this[14].Ptr) )
  {
    v10 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v10 > 3u )
    {
      if ( this[5].Ptr > (PVOID)7 )
        v2 = (RTL_SRWLOCK *)v2->Ptr;
      v13 = v2;
      v14 = L"Invalidate() called but pipe already invalid";
      v15 = this;
      v16 = "CMidiPipe::Invalidate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v10,
        (__int64)&dword_140087E7C,
        v11,
        v12,
        &v16,
        (__int64)&v15,
        &v14,
        &v13);
    }
  }
  else
  {
    v7 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v7 > 4u )
    {
      if ( this[5].Ptr > (PVOID)7 )
        v2 = (RTL_SRWLOCK *)v2->Ptr;
      v13 = v2;
      v14 = L"Lock acquired. Marking pipe invalid";
      v15 = this;
      v16 = "CMidiPipe::Invalidate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v7,
        (__int64)byte_140087825,
        v8,
        v9,
        &v16,
        (__int64)&v15,
        &v14,
        &v13);
    }
    LOBYTE(this[14].Ptr) = 1;
  }
  if ( this != (RTL_SRWLOCK *)-64LL )
    ReleaseSRWLockExclusive(this + 8);
}

```

## disassembly

```asm
0x14001ba58  push    rbp
0x14001ba5a  push    rbx
0x14001ba5b  push    rsi
0x14001ba5c  push    rdi
0x14001ba5d  push    r14
0x14001ba5f  mov     rbp, rsp
0x14001ba62  sub     rsp, 40h
0x14001ba66  mov     rdi, rcx
0x14001ba69  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001ba6e  lea     rbx, [rdi+10h]
0x14001ba72  lea     r14, aCmidipipeInval; "CMidiPipe::Invalidate"
0x14001ba79  mov     rcx, [rax+8]
0x14001ba7d  mov     eax, [rcx]
0x14001ba7f  cmp     eax, 4
0x14001ba82  jbe     short loc_14001BADA
0x14001ba84  cmp     qword ptr [rbx+18h], 7
0x14001ba89  jbe     short loc_14001BA90
0x14001ba8b  mov     rax, [rbx]
0x14001ba8e  jmp     short loc_14001BA93
0x14001ba90  mov     rax, rbx
0x14001ba93  mov     [rbp+arg_0], rax
0x14001ba97  lea     rdx, byte_1400880A7
0x14001ba9e  lea     rax, aEnter; "Enter"
0x14001baa5  mov     [rbp+arg_10], rdi
0x14001baa9  mov     [rbp+arg_8], rax
0x14001baad  lea     rax, [rbp+arg_0]
0x14001bab1  mov     [rsp+40h+var_8], rax
0x14001bab6  lea     rax, [rbp+arg_8]
0x14001baba  mov     [rsp+40h+var_10], rax
0x14001babf  lea     rax, [rbp+arg_10]
0x14001bac3  mov     [rsp+40h+var_18], rax
0x14001bac8  lea     rax, [rbp+arg_18]
0x14001bacc  mov     [rsp+40h+var_20], rax
0x14001bad1  mov     [rbp+arg_18], r14
0x14001bad5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14001bada  lea     rsi, [rdi+40h]
0x14001bade  mov     rcx, rsi; SRWLock
0x14001bae1  call    cs:__imp_AcquireSRWLockExclusive
0x14001bae7  cmp     byte ptr [rdi+70h], 0
0x14001baeb  jnz     short loc_14001BB54
0x14001baed  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001baf2  mov     rcx, [rax+8]
0x14001baf6  mov     eax, [rcx]
0x14001baf8  cmp     eax, 4
0x14001bafb  jbe     short loc_14001BB4E
0x14001bafd  cmp     qword ptr [rbx+18h], 7
0x14001bb02  jbe     short loc_14001BB07
0x14001bb04  mov     rbx, [rbx]
0x14001bb07  lea     rax, aLockAcquiredMa; "Lock acquired. Marking pipe invalid"
0x14001bb0e  mov     [rbp+arg_0], rbx
0x14001bb12  mov     [rbp+arg_8], rax
0x14001bb16  lea     rdx, byte_140087825
0x14001bb1d  lea     rax, [rbp+arg_0]
0x14001bb21  mov     [rbp+arg_10], rdi
0x14001bb25  mov     [rsp+40h+var_8], rax
0x14001bb2a  lea     rax, [rbp+arg_8]
0x14001bb2e  mov     [rsp+40h+var_10], rax
0x14001bb33  lea     rax, [rbp+arg_10]
0x14001bb37  mov     [rsp+40h+var_18], rax
0x14001bb3c  lea     rax, [rbp+arg_18]
0x14001bb40  mov     [rsp+40h+var_20], rax
0x14001bb45  mov     [rbp+arg_18], r14
0x14001bb49  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14001bb4e  mov     byte ptr [rdi+70h], 1
0x14001bb52  jmp     short loc_14001BBB5
0x14001bb54  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001bb59  mov     rcx, [rax+8]
0x14001bb5d  mov     eax, [rcx]
0x14001bb5f  cmp     eax, 3
0x14001bb62  jbe     short loc_14001BBB5
0x14001bb64  cmp     qword ptr [rbx+18h], 7
0x14001bb69  jbe     short loc_14001BB6E
0x14001bb6b  mov     rbx, [rbx]
0x14001bb6e  lea     rax, aInvalidateCall; "Invalidate() called but pipe already in"...
0x14001bb75  mov     [rbp+arg_0], rbx
0x14001bb79  mov     [rbp+arg_8], rax
0x14001bb7d  lea     rdx, dword_140087E7C
0x14001bb84  lea     rax, [rbp+arg_0]
0x14001bb88  mov     [rbp+arg_10], rdi
0x14001bb8c  mov     [rsp+40h+var_8], rax
0x14001bb91  lea     rax, [rbp+arg_8]
0x14001bb95  mov     [rsp+40h+var_10], rax
0x14001bb9a  lea     rax, [rbp+arg_10]
0x14001bb9e  mov     [rsp+40h+var_18], rax
0x14001bba3  lea     rax, [rbp+arg_18]
0x14001bba7  mov     [rsp+40h+var_20], rax
0x14001bbac  mov     [rbp+arg_18], r14
0x14001bbb0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14001bbb5  test    rsi, rsi
0x14001bbb8  jz      short loc_14001BBC3
0x14001bbba  mov     rcx, rsi; SRWLock
0x14001bbbd  call    cs:__imp_ReleaseSRWLockExclusive
0x14001bbc3  add     rsp, 40h
0x14001bbc7  pop     r14
0x14001bbc9  pop     rdi
0x14001bbca  pop     rsi
0x14001bbcb  pop     rbx
0x14001bbcc  pop     rbp
0x14001bbcd  retn
```
