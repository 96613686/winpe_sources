# IncomingTextMessageHandler::_RegisterForTextMessages(void)

- ea: `0x180007930`
- end: `0x180007ade`
- name: `?_RegisterForTextMessages@IncomingTextMessageHandler@@AEAAJXZ`
- size: `430`
- prototype: `__int64 __fastcall(IncomingTextMessageHandler *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000740c`

## callees

- `0x180001148`
- `0x180001730`
- `0x18000266c`
- `0x180007128`
- `0x180007248`
- `0x180007930`
- `0x180009524`
- `0x180009bc4`
- `0x180009e58`
- `0x18000aa50`

## pseudocode

```c
__int64 __fastcall IncomingTextMessageHandler::_RegisterForTextMessages(IncomingTextMessageHandler *this)
{
  int TextMessageFilter; // eax
  __int64 v3; // r8
  unsigned int v4; // ebx
  IncomingMessageRegistrationEvent *v6; // rcx
  const unsigned __int16 *v7; // rdi
  char *v8; // rax
  const unsigned __int16 *v9; // rdx
  __int64 v10; // r8
  IncomingMessageRegistrationEvent *v11; // rbx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // edi
  __int64 v17; // r8
  unsigned __int16 *v18; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 *v19[2]; // [rsp+38h] [rbp-30h] BYREF
  __int16 v20; // [rsp+48h] [rbp-20h] BYREF
  __int64 v21; // [rsp+4Ah] [rbp-1Eh]
  int v22; // [rsp+52h] [rbp-16h]
  __int16 v23; // [rsp+56h] [rbp-12h]

  v21 = 0;
  v23 = 0;
  v22 = 0;
  v19[0] = (unsigned __int16 *)&v20;
  v19[1] = (unsigned __int16 *)&v20;
  v20 = 0;
  TextMessageFilter = SmsMessageFilterBuilder::CreateTextMessageFilter(v19);
  v4 = TextMessageFilter;
  if ( TextMessageFilter < 0 )
  {
    Log_HREvent_3((unsigned int)TextMessageFilter, 1, v3, 142);
    if ( (__int16 *)v19[0] != &v20 )
      operator delete(v19[0], (const struct std::nothrow_t *)&std::nothrow);
    return v4;
  }
  v6 = (IncomingMessageRegistrationEvent *)*((_QWORD *)this + 5);
  if ( v6 )
  {
    tlx::_delete<IncomingMessageRegistrationEvent>(v6);
    *((_QWORD *)this + 5) = 0;
  }
  v7 = v19[0];
  v8 = (char *)operator new(0x30u);
  v11 = (IncomingMessageRegistrationEvent *)v8;
  if ( !v8 )
  {
    v16 = -2147024882;
    Log_HREvent_5(2147942414LL, 0, v10, 122);
    goto LABEL_16;
  }
  *(_QWORD *)(v8 + 34) = 0;
  *(_DWORD *)(v8 + 42) = 0;
  *((_WORD *)v8 + 23) = 0;
  *(_QWORD *)v8 = 0;
  *((_QWORD *)v8 + 1) = 0;
  *((_QWORD *)v8 + 2) = v8 + 32;
  *((_QWORD *)v8 + 3) = v8 + 32;
  *((_WORD *)v8 + 16) = 0;
  v12 = IncomingMessageRegistrationEvent::_Initialize((IncomingMessageRegistrationEvent *)v8, v9, v7);
  v16 = v12;
  if ( v12 < 0 )
  {
    Log_HREvent_5((unsigned int)v12, 1, v14, 124);
    tlx::_delete<IncomingMessageRegistrationEvent>(v11);
LABEL_16:
    Log_HREvent_3(v16, 1, v17, 155);
    if ( (__int16 *)v19[0] != &v20 )
      operator delete(v19[0], (const struct std::nothrow_t *)&std::nothrow);
    return v16;
  }
  *((_QWORD *)this + 5) = v11;
  if ( (unsigned int)dword_180013018 > 3 )
  {
    v18 = v19[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v13,
      (int)byte_1800103F1,
      v14,
      v15,
      (__int64 **)&v18);
  }
  if ( (__int16 *)v19[0] != &v20 )
    operator delete(v19[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x180007930  push    rbp
0x180007932  push    rbx
0x180007933  push    rsi
0x180007934  push    rdi
0x180007935  mov     rbp, rsp
0x180007938  sub     rsp, 68h
0x18000793c  mov     rax, cs:__security_cookie
0x180007943  xor     rax, rsp
0x180007946  mov     [rbp+var_10], rax
0x18000794a  xor     eax, eax
0x18000794c  mov     [rbp+var_1E], 0
0x180007954  mov     [rbp+var_12], ax
0x180007958  mov     rsi, rcx
0x18000795b  lea     rax, [rbp+var_20]
0x18000795f  mov     [rbp+var_16], 0
0x180007966  mov     [rbp+var_30], rax
0x18000796a  lea     rcx, [rbp+var_30]
0x18000796e  lea     rax, [rbp+var_20]
0x180007972  mov     [rbp+var_28], rax
0x180007976  xor     eax, eax
0x180007978  mov     [rbp+var_20], ax
0x18000797c  call    ?CreateTextMessageFilter@SmsMessageFilterBuilder@@SAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; SmsMessageFilterBuilder::CreateTextMessageFilter(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180007981  mov     ebx, eax
0x180007983  test    eax, eax
0x180007985  jns     short loc_1800079B9
0x180007987  mov     edx, 1
0x18000798c  mov     r9d, 8Eh
0x180007992  mov     ecx, eax
0x180007994  call    Log_HREvent_3
0x180007999  mov     rcx, [rbp+var_30]; void *
0x18000799d  lea     rax, [rbp+var_20]
0x1800079a1  cmp     rcx, rax
0x1800079a4  jz      short loc_1800079B2
0x1800079a6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800079ad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800079b2  mov     eax, ebx
0x1800079b4  jmp     loc_180007AC9
0x1800079b9  mov     rcx, [rsi+28h]
0x1800079bd  test    rcx, rcx
0x1800079c0  jz      short loc_1800079CF
0x1800079c2  call    ??$_delete@VIncomingMessageRegistrationEvent@@@tlx@@YAXPEAVIncomingMessageRegistrationEvent@@@Z; tlx::_delete<IncomingMessageRegistrationEvent>(IncomingMessageRegistrationEvent *)
0x1800079c7  mov     qword ptr [rsi+28h], 0
0x1800079cf  mov     rdi, [rbp+var_30]
0x1800079d3  mov     ecx, 30h ; '0'; Size
0x1800079d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800079dd  mov     rbx, rax
0x1800079e0  test    rax, rax
0x1800079e3  jz      loc_180007A8A
0x1800079e9  mov     qword ptr [rax+22h], 0
0x1800079f1  xor     ecx, ecx
0x1800079f3  mov     dword ptr [rax+2Ah], 0
0x1800079fa  mov     r8, rdi; unsigned __int16 *
0x1800079fd  mov     [rax+2Eh], cx
0x180007a01  mov     [rax], rcx
0x180007a04  mov     [rax+8], rcx
0x180007a08  lea     rcx, [rax+20h]
0x180007a0c  mov     [rax+10h], rcx
0x180007a10  mov     [rax+18h], rcx
0x180007a14  xor     eax, eax
0x180007a16  mov     [rcx], ax
0x180007a19  mov     rcx, rbx; this
0x180007a1c  call    ?_Initialize@IncomingMessageRegistrationEvent@@AEAAJPEBG0KP6AXPEAXU_CBROKERED_EVENT_ID@@11KKPEAW4_BI_ACTIVATION_STATUS@@@Z@Z; IncomingMessageRegistrationEvent::_Initialize(ushort const *,ushort const *,ulong,void (*)(void *,_CBROKERED_EVENT_ID,void *,void *,ulong,ulong,_BI_ACTIVATION_STATUS *))
0x180007a21  mov     edi, eax
0x180007a23  test    eax, eax
0x180007a25  jns     short loc_180007A41
0x180007a27  mov     edx, 1
0x180007a2c  mov     ecx, eax
0x180007a2e  lea     r9d, [rdx+7Bh]
0x180007a32  call    Log_HREvent_5
0x180007a37  mov     rcx, rbx
0x180007a3a  call    ??$_delete@VIncomingMessageRegistrationEvent@@@tlx@@YAXPEAVIncomingMessageRegistrationEvent@@@Z; tlx::_delete<IncomingMessageRegistrationEvent>(IncomingMessageRegistrationEvent *)
0x180007a3f  jmp     short loc_180007A9C
0x180007a41  mov     [rsi+28h], rbx
0x180007a45  mov     eax, cs:dword_180013018
0x180007a4b  cmp     eax, 3
0x180007a4e  jbe     short loc_180007A6D
0x180007a50  mov     rax, [rbp+var_30]
0x180007a54  lea     rdx, byte_1800103F1
0x180007a5b  mov     [rbp+var_38], rax
0x180007a5f  lea     rax, [rbp+var_38]
0x180007a63  mov     [rsp+68h+var_48], rax
0x180007a68  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180007a6d  mov     rcx, [rbp+var_30]; void *
0x180007a71  lea     rax, [rbp+var_20]
0x180007a75  cmp     rcx, rax
0x180007a78  jz      short loc_180007A86
0x180007a7a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007a81  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007a86  xor     eax, eax
0x180007a88  jmp     short loc_180007AC9
0x180007a8a  xor     edx, edx
0x180007a8c  mov     edi, 8007000Eh
0x180007a91  mov     ecx, edi
0x180007a93  lea     r9d, [rdx+7Ah]
0x180007a97  call    Log_HREvent_5
0x180007a9c  mov     edx, 1
0x180007aa1  mov     r9d, 9Bh
0x180007aa7  mov     ecx, edi
0x180007aa9  call    Log_HREvent_3
0x180007aae  mov     rcx, [rbp+var_30]; void *
0x180007ab2  lea     rax, [rbp+var_20]
0x180007ab6  cmp     rcx, rax
0x180007ab9  jz      short loc_180007AC7
0x180007abb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007ac2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007ac7  mov     eax, edi
0x180007ac9  mov     rcx, [rbp+var_10]
0x180007acd  xor     rcx, rsp; StackCookie
0x180007ad0  call    __security_check_cookie
0x180007ad5  add     rsp, 68h
0x180007ad9  pop     rdi
0x180007ada  pop     rsi
0x180007adb  pop     rbx
0x180007adc  pop     rbp
0x180007add  retn
```
