# SEReader::UnregisterFromWNFEvents(void)

- ea: `0x180017be4`
- end: `0x180017c8e`
- name: `?UnregisterFromWNFEvents@SEReader@@AEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(SEReader *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800166b0`
- `0x180016afc`

## callees

- `0x180001194`
- `0x180017be4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017c1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017c1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017c00`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017c00`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180017c6c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180017c6c`

## string_xrefs

- `0x180017c44`: `SEReader::UnregisterFromWNFEvents`

## pseudocode

```c
int __fastcall SEReader::UnregisterFromWNFEvents(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  __int64 v3; // rsi
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  int v7; // eax
  const char *v9; // [rsp+40h] [rbp+8h] BYREF
  const char *v10; // [rsp+48h] [rbp+10h] BYREF

  v1 = this + 7;
  EnterCriticalSection(this + 7);
  v3 = *(_QWORD *)&this[10].LockCount;
  *(_QWORD *)&this[10].LockCount = 0;
  LeaveCriticalSection(v1);
  if ( !v3 )
    return 0;
  if ( (unsigned int)dword_18012F048 > 5 )
  {
    v9 = "Cancel WNF callback on Card Emulation primary subscription";
    v10 = "SEReader::UnregisterFromWNFEvents";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v4,
      (unsigned int)&byte_180119C6F,
      v5,
      v6,
      (__int64)&v10,
      (__int64)&v9);
  }
  v7 = RtlUnsubscribeWnfNotificationWaitForCompletion(v3);
  if ( v7 < 0 )
    return v7 | 0x10000000;
  else
    return 0;
}

```

## disassembly

```asm
0x180017be4  mov     [rsp+arg_10], rbx
0x180017be9  mov     [rsp+arg_18], rsi
0x180017bee  push    rdi
0x180017bef  sub     rsp, 30h
0x180017bf3  lea     rbx, [rcx+118h]
0x180017bfa  mov     rdi, rcx
0x180017bfd  mov     rcx, rbx; lpCriticalSection
0x180017c00  call    cs:__imp_EnterCriticalSection
0x180017c06  mov     rsi, [rdi+198h]
0x180017c0d  mov     rcx, rbx; lpCriticalSection
0x180017c10  mov     qword ptr [rdi+198h], 0
0x180017c1b  call    cs:__imp_LeaveCriticalSection
0x180017c21  test    rsi, rsi
0x180017c24  jz      short loc_180017C7C
0x180017c26  mov     eax, cs:dword_18012F048
0x180017c2c  cmp     eax, 5
0x180017c2f  jbe     short loc_180017C69
0x180017c31  lea     rax, aCancelWnfCallb; "Cancel WNF callback on Card Emulation p"...
0x180017c38  mov     [rsp+38h+arg_0], rax
0x180017c3d  lea     rdx, byte_180119C6F
0x180017c44  lea     rax, aSereaderUnregi; "SEReader::UnregisterFromWNFEvents"
0x180017c4b  mov     [rsp+38h+arg_8], rax
0x180017c50  lea     rax, [rsp+38h+arg_0]
0x180017c55  mov     [rsp+38h+var_10], rax
0x180017c5a  lea     rax, [rsp+38h+arg_8]
0x180017c5f  mov     [rsp+38h+var_18], rax
0x180017c64  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180017c69  mov     rcx, rsi
0x180017c6c  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180017c72  test    eax, eax
0x180017c74  jns     short loc_180017C7C
0x180017c76  bts     eax, 1Ch
0x180017c7a  jmp     short loc_180017C7E
0x180017c7c  xor     eax, eax
0x180017c7e  mov     rbx, [rsp+38h+arg_10]
0x180017c83  mov     rsi, [rsp+38h+arg_18]
0x180017c88  add     rsp, 30h
0x180017c8c  pop     rdi
0x180017c8d  retn
```
