# CMidiPipe::AddClient(unsigned __int64)

- ea: `0x140014ad0`
- end: `0x140014c3f`
- name: `?AddClient@CMidiPipe@@UEAAX_K@Z`
- size: `367`
- prototype: `void __fastcall(RTL_SRWLOCK *this, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140001bc0`
- `0x140005180`
- `0x14000984c`
- `0x1400125a0`
- `0x140014ad0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014b71`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014b71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014c2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014c2a`

## string_xrefs

- `0x140014bd5`: `Client already exists`

## pseudocode

```c
void __fastcall CMidiPipe::AddClient(RTL_SRWLOCK *this, __int64 a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  RTL_SRWLOCK *v7; // rbx
  RTL_SRWLOCK *Ptr; // rax
  __int64 trivial_8; // rax
  _QWORD *v10; // rdx
  _DWORD *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  const char *v14; // [rsp+50h] [rbp-10h] BYREF
  const char *v15; // [rsp+58h] [rbp-8h] BYREF
  RTL_SRWLOCK *v16; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v17; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v18; // [rsp+B0h] [rbp+50h] BYREF
  const wchar_t *v19; // [rsp+B8h] [rbp+58h] BYREF

  v17 = a2;
  v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  v7 = this + 2;
  if ( *v4 > 4u )
  {
    if ( this[5].Ptr <= (PVOID)7 )
      Ptr = this + 2;
    else
      Ptr = (RTL_SRWLOCK *)v7->Ptr;
    v16 = Ptr;
    v18 = a2;
    v19 = L"Enter";
    v14 = (const char *)this;
    v15 = "CMidiPipe::AddClient";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)&word_140087D9E,
      v5,
      v6,
      &v15,
      (__int64)&v14,
      &v19,
      (__int64)&v18,
      &v16);
  }
  AcquireSRWLockExclusive(this + 8);
  v16 = this + 8;
  trivial_8 = _std_find_trivial_8(this[11].Ptr, this[12].Ptr, a2);
  v10 = this[12].Ptr;
  if ( (_QWORD *)trivial_8 == v10 )
  {
    if ( v10 == this[13].Ptr )
    {
      std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(&this[11], v10, &v17);
    }
    else
    {
      *v10 = a2;
      this[12].Ptr = (char *)this[12].Ptr + 8;
    }
  }
  else
  {
    v11 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v11 > 3u )
    {
      if ( this[5].Ptr > (PVOID)7 )
        v7 = (RTL_SRWLOCK *)v7->Ptr;
      v16 = v7;
      v18 = a2;
      v19 = L"Client already exists";
      v15 = (const char *)this;
      v14 = "CMidiPipe::AddClient";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (__int64)v11,
        (__int64)&unk_1400877B8,
        v12,
        v13,
        &v14,
        (__int64)&v15,
        &v19,
        (__int64)&v18,
        &v16);
    }
  }
  if ( this != (RTL_SRWLOCK *)-64LL )
    ReleaseSRWLockExclusive(this + 8);
}

```

## disassembly

```asm
0x140014ad0  mov     [rsp-38h+arg_8], rdx
0x140014ad5  push    rbp
0x140014ad6  push    rbx
0x140014ad7  push    rsi
0x140014ad8  push    rdi
0x140014ad9  push    r12
0x140014adb  push    r14
0x140014add  push    r15
0x140014adf  mov     rbp, rsp
0x140014ae2  sub     rsp, 60h
0x140014ae6  mov     r15, rdx
0x140014ae9  mov     r14, rcx
0x140014aec  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140014af1  mov     rcx, [rax+8]
0x140014af5  mov     eax, [rcx]
0x140014af7  lea     rbx, [r14+10h]
0x140014afb  lea     r12, aCmidipipeAddcl; "CMidiPipe::AddClient"
0x140014b02  cmp     eax, 4
0x140014b05  jbe     short loc_140014B6A
0x140014b07  cmp     qword ptr [rbx+18h], 7
0x140014b0c  jbe     short loc_140014B13
0x140014b0e  mov     rax, [rbx]
0x140014b11  jmp     short loc_140014B16
0x140014b13  mov     rax, rbx
0x140014b16  mov     [rbp+arg_0], rax
0x140014b1a  mov     [rbp+arg_10], r15
0x140014b1e  lea     rax, aEnter; "Enter"
0x140014b25  mov     [rbp+arg_18], rax
0x140014b29  mov     [rbp+var_10], r14
0x140014b2d  mov     [rbp+var_8], r12
0x140014b31  lea     rax, [rbp+arg_0]
0x140014b35  mov     [rsp+60h+var_20], rax
0x140014b3a  lea     rax, [rbp+arg_10]
0x140014b3e  mov     [rsp+60h+var_28], rax
0x140014b43  lea     rax, [rbp+arg_18]
0x140014b47  mov     [rsp+60h+var_30], rax
0x140014b4c  lea     rax, [rbp+var_10]
0x140014b50  mov     [rsp+60h+var_38], rax
0x140014b55  lea     rax, [rbp+var_8]
0x140014b59  mov     [rsp+60h+var_40], rax
0x140014b5e  lea     rdx, word_140087D9E
0x140014b65  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@45@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x140014b6a  lea     rsi, [r14+40h]
0x140014b6e  mov     rcx, rsi; SRWLock
0x140014b71  call    cs:__imp_AcquireSRWLockExclusive
0x140014b77  mov     [rbp+arg_0], rsi
0x140014b7b  mov     r8, r15
0x140014b7e  mov     rdx, [r14+60h]
0x140014b82  mov     rcx, [r14+58h]
0x140014b86  call    __std_find_trivial_8
0x140014b8b  mov     rdx, [r14+60h]
0x140014b8f  cmp     rax, rdx
0x140014b92  jnz     short loc_140014BB3
0x140014b94  cmp     rdx, [r14+68h]
0x140014b98  jz      short loc_140014BA4
0x140014b9a  mov     [rdx], r15
0x140014b9d  add     qword ptr [r14+60h], 8
0x140014ba2  jmp     short loc_140014C22
0x140014ba4  lea     r8, [rbp+arg_8]
0x140014ba8  lea     rcx, [r14+58h]
0x140014bac  call    ??$_Emplace_reallocate@AEB_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAPEA_KQEA_KAEB_K@Z; std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(unsigned __int64 * const,unsigned __int64 const &)
0x140014bb1  jmp     short loc_140014C22
0x140014bb3  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140014bb8  mov     rcx, [rax+8]
0x140014bbc  mov     eax, [rcx]
0x140014bbe  cmp     eax, 3
0x140014bc1  jbe     short loc_140014C22
0x140014bc3  cmp     qword ptr [rbx+18h], 7
0x140014bc8  jbe     short loc_140014BCD
0x140014bca  mov     rbx, [rbx]
0x140014bcd  mov     [rbp+arg_0], rbx
0x140014bd1  mov     [rbp+arg_10], r15
0x140014bd5  lea     rax, aClientAlreadyE; "Client already exists"
0x140014bdc  mov     [rbp+arg_18], rax
0x140014be0  mov     [rbp+var_8], r14
0x140014be4  mov     [rbp+var_10], r12
0x140014be8  lea     rax, [rbp+arg_0]
0x140014bec  mov     [rsp+60h+var_20], rax
0x140014bf1  lea     rax, [rbp+arg_10]
0x140014bf5  mov     [rsp+60h+var_28], rax
0x140014bfa  lea     rax, [rbp+arg_18]
0x140014bfe  mov     [rsp+60h+var_30], rax
0x140014c03  lea     rax, [rbp+var_8]
0x140014c07  mov     [rsp+60h+var_38], rax
0x140014c0c  lea     rax, [rbp+var_10]
0x140014c10  mov     [rsp+60h+var_40], rax
0x140014c15  lea     rdx, unk_1400877B8
0x140014c1c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@45@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x140014c21  nop
0x140014c22  test    rsi, rsi
0x140014c25  jz      short loc_140014C30
0x140014c27  mov     rcx, rsi; SRWLock
0x140014c2a  call    cs:__imp_ReleaseSRWLockExclusive
0x140014c30  add     rsp, 60h
0x140014c34  pop     r15
0x140014c36  pop     r14
0x140014c38  pop     r12
0x140014c3a  pop     rdi
0x140014c3b  pop     rsi
0x140014c3c  pop     rbx
0x140014c3d  pop     rbp
0x140014c3e  retn
```
