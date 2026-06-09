# SvcInitialize(ulong,ushort const * * const)

- ea: `0x18000b264`
- end: `0x18000b3b1`
- name: `?SvcInitialize@@YAJKQEAPEBG@Z`
- size: `333`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180003860`

## callees

- `0x180001010`
- `0x1800012f0`
- `0x18000131c`
- `0x180008d7c`
- `0x180009194`
- `0x18000af0c`
- `0x18000b04c`
- `0x18000b118`
- `0x18000b264`
- `0x18000d8bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b2cc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b31e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b2cc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b31e`

## string_xrefs

- `0x18000b391`: `onecore\base\time\autotime\timeservice\timesvcimpl.cpp`
- `0x18000b313`: `sync_task`

## pseudocode

```c
__int64 __fastcall SvcInitialize(unsigned int a1, const unsigned __int16 **const a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  bool v6; // di
  unsigned int i; // ebx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int v12; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  const unsigned __int16 *v14; // [rsp+80h] [rbp+18h] BYREF

  AutoTimeLoggingRegister();
  v4 = IntializeComSecurity();
  if ( v4 < 0 )
  {
    v5 = 138;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\timesvcimpl.cpp",
      (const char *)(unsigned int)v4,
      v12);
    return (unsigned int)v4;
  }
  Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  v4 = AdjustPrivileges();
  if ( v4 < 0 )
  {
    v5 = 143;
    goto LABEL_18;
  }
  v6 = 0;
  for ( i = 1; i < a1; ++i )
  {
    if ( (unsigned int)_o__wcsicmp(a2[i], L"TriggerStarted") )
    {
      if ( (unsigned int)_o__wcsicmp(a2[i], L"sync_task") )
      {
        if ( (unsigned int)dword_18001C010 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
        {
          v14 = a2[i];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v8,
            (unsigned int)byte_180016943,
            v9,
            v10,
            (__int64)&v14);
        }
      }
      else
      {
        v6 = 1;
      }
    }
    else if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
    {
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18001C010,
        byte_180016925,
        0,
        0);
    }
  }
  v4 = RegisterForWNFs(v6);
  if ( v4 < 0 )
  {
    v5 = 173;
    goto LABEL_18;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000b264  push    rbx
0x18000b266  push    rbp
0x18000b267  push    rsi
0x18000b268  push    rdi
0x18000b269  push    r14
0x18000b26b  push    r15
0x18000b26d  sub     rsp, 38h
0x18000b271  mov     r14, rdx
0x18000b274  mov     ebp, ecx
0x18000b276  call    ?AutoTimeLoggingRegister@@YAXXZ; AutoTimeLoggingRegister(void)
0x18000b27b  call    ?IntializeComSecurity@@YAJXZ; IntializeComSecurity(void)
0x18000b280  mov     ebx, eax
0x18000b282  test    eax, eax
0x18000b284  jns     short loc_18000B290
0x18000b286  mov     edx, 8Ah
0x18000b28b  jmp     loc_18000B38E
0x18000b290  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18000b295  call    ?AdjustPrivileges@@YAJXZ; AdjustPrivileges(void)
0x18000b29a  mov     ebx, eax
0x18000b29c  test    eax, eax
0x18000b29e  jns     short loc_18000B2AA
0x18000b2a0  mov     edx, 8Fh
0x18000b2a5  jmp     loc_18000B38E
0x18000b2aa  xor     dil, dil
0x18000b2ad  mov     r15d, 1
0x18000b2b3  mov     ebx, r15d
0x18000b2b6  cmp     ebp, r15d
0x18000b2b9  jbe     loc_18000B37B
0x18000b2bf  mov     esi, ebx
0x18000b2c1  lea     rdx, aTriggerstarted; "TriggerStarted"
0x18000b2c8  mov     rcx, [r14+rsi*8]
0x18000b2cc  call    cs:__imp__o__wcsicmp
0x18000b2d2  test    eax, eax
0x18000b2d4  jnz     short loc_18000B313
0x18000b2d6  mov     eax, cs:dword_18001C010
0x18000b2dc  cmp     eax, 4
0x18000b2df  jbe     loc_18000B370
0x18000b2e5  mov     rdx, r15
0x18000b2e8  lea     rcx, dword_18001C010
0x18000b2ef  call    _tlgKeywordOn
0x18000b2f4  test    al, al
0x18000b2f6  jz      short loc_18000B370
0x18000b2f8  xor     r9d, r9d
0x18000b2fb  xor     r8d, r8d
0x18000b2fe  lea     rdx, byte_180016925
0x18000b305  lea     rcx, dword_18001C010
0x18000b30c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000b311  jmp     short loc_18000B370
0x18000b313  lea     rdx, aSyncTask; "sync_task"
0x18000b31a  mov     rcx, [r14+rsi*8]
0x18000b31e  call    cs:__imp__o__wcsicmp
0x18000b324  test    eax, eax
0x18000b326  jnz     short loc_18000B32D
0x18000b328  mov     dil, r15b
0x18000b32b  jmp     short loc_18000B370
0x18000b32d  mov     eax, cs:dword_18001C010
0x18000b333  cmp     eax, 3
0x18000b336  jbe     short loc_18000B370
0x18000b338  mov     rdx, r15
0x18000b33b  lea     rcx, dword_18001C010
0x18000b342  call    _tlgKeywordOn
0x18000b347  test    al, al
0x18000b349  jz      short loc_18000B370
0x18000b34b  mov     rax, [r14+rsi*8]
0x18000b34f  mov     [rsp+68h+arg_10], rax
0x18000b357  lea     rax, [rsp+68h+arg_10]
0x18000b35f  mov     qword ptr [rsp+68h+var_48], rax; int
0x18000b364  lea     rdx, byte_180016943
0x18000b36b  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000b370  add     ebx, r15d
0x18000b373  cmp     ebx, ebp
0x18000b375  jb      loc_18000B2BF
0x18000b37b  mov     cl, dil; bool
0x18000b37e  call    ?RegisterForWNFs@@YAJ_N@Z; RegisterForWNFs(bool)
0x18000b383  mov     ebx, eax
0x18000b385  test    eax, eax
0x18000b387  jns     short loc_18000B3A2
0x18000b389  mov     edx, 0ADh; void *
0x18000b38e  mov     r9d, ebx; char *
0x18000b391  lea     r8, aOnecoreBaseTim_1; "onecore\\base\\time\\autotime\\timeserv"...
0x18000b398  mov     rcx, [rsp+68h]; this
0x18000b39d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b3a2  mov     eax, ebx
0x18000b3a4  add     rsp, 38h
0x18000b3a8  pop     r15
0x18000b3aa  pop     r14
0x18000b3ac  pop     rdi
0x18000b3ad  pop     rsi
0x18000b3ae  pop     rbp
0x18000b3af  pop     rbx
0x18000b3b0  retn
```
