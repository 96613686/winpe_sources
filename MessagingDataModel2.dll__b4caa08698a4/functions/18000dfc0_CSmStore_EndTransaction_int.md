# CSmStore::EndTransaction(int)

- ea: `0x18000dfc0`
- end: `0x18000e0c6`
- name: `?EndTransaction@CSmStore@@MEAAJH@Z`
- size: `262`
- prototype: `__int64 __fastcall(CSmStore *__hidden this, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001484`
- `0x1800014d4`
- `0x18000c250`
- `0x18000dfc0`
- `0x180012460`
- `0x180012498`
- `0x1800c50ec`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dfd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dffa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dfd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dffa`

## string_xrefs

- `0x18000e02a`: `[Messaging] Not committing`

## pseudocode

```c
__int64 __fastcall CSmStore::EndTransaction(CSmStore *this, unsigned int a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // ebx
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  CSmStore *v13; // [rsp+30h] [rbp-28h] BYREF
  __int64 v14; // [rsp+38h] [rbp-20h]
  const char *v15; // [rsp+40h] [rbp-18h] BYREF

  if ( *((_DWORD *)this + 44) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_1(v4, "onecoreuap\\base\\appmodel\\messagingom\\src\\store.cpp", 1927);
    v7 = *((_DWORD *)this + 44);
    if ( v7 != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v14 = 1;
  v13 = this;
  if ( !a2 && (unsigned int)dword_1800FD5F0 > 5 )
  {
    v15 = "[Messaging] Not committing";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v4,
      (int)word_1800E9062,
      v5,
      v6,
      (const unsigned __int16 **)&v15);
  }
  v8 = *((_QWORD *)this + 10);
  *((_DWORD *)this + 44) = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 240LL))(v8, a2);
  v11 = v9;
  if ( v9 >= 0 )
  {
    LOBYTE(v14) = 0;
    if ( (unsigned int)dword_1800FD5F0 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v10,
        (int)word_1800E903A);
    v11 = 0;
  }
  else
  {
    Log_HREvent_1(v9);
  }
  tlx::_UndoSolo__lambda_7d4c84b60470670c661cbe67679b5cf0___::__UndoSolo__lambda_7d4c84b60470670c661cbe67679b5cf0___(&v13);
  return v11;
}

```

## disassembly

```asm
0x18000dfc0  mov     [rsp+arg_10], rbx
0x18000dfc5  mov     [rsp+arg_18], rsi
0x18000dfca  push    rdi
0x18000dfcb  sub     rsp, 50h
0x18000dfcf  mov     esi, edx
0x18000dfd1  mov     rdi, rcx
0x18000dfd4  call    cs:__imp_GetCurrentThreadId
0x18000dfda  cmp     [rdi+0B0h], eax
0x18000dfe0  jz      short loc_18000E009
0x18000dfe2  mov     r8d, 787h
0x18000dfe8  lea     rdx, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\messagingom"...
0x18000dfef  call    Log_AssertionEvent_1
0x18000dff4  mov     ebx, [rdi+0B0h]
0x18000dffa  call    cs:__imp_GetCurrentThreadId
0x18000e000  cmp     ebx, eax
0x18000e002  jz      short loc_18000E009
0x18000e004  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e009  xorps   xmm0, xmm0
0x18000e00c  movups  [rsp+58h+var_28], xmm0
0x18000e011  mov     qword ptr [rsp+58h+var_28], rdi
0x18000e016  mov     byte ptr [rsp+58h+var_28+8], 1
0x18000e01b  test    esi, esi
0x18000e01d  jnz     short loc_18000E04C
0x18000e01f  mov     eax, cs:dword_1800FD5F0
0x18000e025  cmp     eax, 5
0x18000e028  jbe     short loc_18000E04C
0x18000e02a  lea     rax, aMessagingNotCo; "[Messaging] Not committing"
0x18000e031  mov     [rsp+58h+var_18], rax
0x18000e036  lea     rdx, word_1800E9062
0x18000e03d  lea     rax, [rsp+58h+var_18]
0x18000e042  mov     [rsp+58h+var_38], rax
0x18000e047  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000e04c  mov     rcx, [rdi+50h]
0x18000e050  mov     edx, esi
0x18000e052  mov     dword ptr [rdi+0B0h], 0
0x18000e05c  mov     rax, [rcx]
0x18000e05f  mov     rax, [rax+0F0h]
0x18000e066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e06b  mov     ebx, eax
0x18000e06d  test    eax, eax
0x18000e06f  jns     short loc_18000E08C
0x18000e071  mov     r9d, 797h
0x18000e077  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\messagingom"...
0x18000e07e  mov     edx, 1
0x18000e083  mov     ecx, eax; int
0x18000e085  call    Log_HREvent_1
0x18000e08a  jmp     short loc_18000E0AA
0x18000e08c  mov     eax, cs:dword_1800FD5F0
0x18000e092  mov     byte ptr [rsp+58h+var_28+8], 0
0x18000e097  cmp     eax, 4
0x18000e09a  jbe     short loc_18000E0A8
0x18000e09c  lea     rdx, word_1800E903A
0x18000e0a3  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000e0a8  xor     ebx, ebx
0x18000e0aa  lea     rcx, [rsp+58h+var_28]
0x18000e0af  call    tlx___UndoSolo__lambda_7d4c84b60470670c661cbe67679b5cf0_______UndoSolo__lambda_7d4c84b60470670c661cbe67679b5cf0___
0x18000e0b4  mov     rsi, [rsp+58h+arg_18]
0x18000e0b9  mov     eax, ebx
0x18000e0bb  mov     rbx, [rsp+58h+arg_10]
0x18000e0c0  add     rsp, 50h
0x18000e0c4  pop     rdi
0x18000e0c5  retn
```
