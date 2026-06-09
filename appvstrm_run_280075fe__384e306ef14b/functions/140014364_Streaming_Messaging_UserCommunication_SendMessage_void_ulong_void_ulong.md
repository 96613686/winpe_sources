# Streaming::Messaging::UserCommunication::SendMessage(void *,ulong,void *,ulong &)

- ea: `0x140014364`
- end: `0x140014557`
- name: `?SendMessage@UserCommunication@Messaging@Streaming@@QEAAJPEAXK0AEAK@Z`
- size: `499`
- prototype: `int(Streaming::Messaging::UserCommunication *__hidden this, void *, unsigned int, void *, unsigned int *)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140010f38`
- `0x140011478`
- `0x1400115cc`
- `0x140014dcc`

## callees

- `0x14000a1ac`
- `0x140013acc`
- `0x140014364`
- `0x1400147fc`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `FLTMGR!FltSendMessage` at `0x1400143df`
- `FLTMGR!FltSendMessage` at `0x1400143df`

## string_xrefs

- `0x1400143fe`: `UserCommunication::SendMessage() - Send message to the streaming engine failed. Status 0x%08X.`
- `0x140014470`: `UserCommunication::SendMessage() - Send message to the streaming engine failed. Status 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::Messaging::UserCommunication::SendMessage(
        Streaming::Messaging::UserCommunication *this,
        void *a2,
        ULONG a3,
        void *a4,
        unsigned int *ReplyLength)
{
  char v5; // bp
  PFLT_PORT *v9; // rbx
  unsigned int v10; // esi
  __int64 *CurrentActivityID; // rax
  volatile signed __int32 *v12; // rdi
  __int64 *v14; // rax
  volatile signed __int32 *v15; // rdi
  _QWORD *v16; // rax
  volatile signed __int32 *v17; // rdi
  _BYTE v18[8]; // [rsp+40h] [rbp-28h] BYREF
  volatile signed __int32 *v19; // [rsp+48h] [rbp-20h]
  union _LARGE_INTEGER Timeout; // [rsp+70h] [rbp+8h] BYREF

  v5 = 0;
  Timeout.LowPart = 0;
  if ( !*((_BYTE *)this + 32) )
    return 3221225701LL;
  v9 = (PFLT_PORT *)((char *)this + 8);
  if ( !*((_QWORD *)this + 1) )
    return 3221225701LL;
  Timeout.QuadPart = -(__int64)(10000000
                              * (unsigned int)Streaming::Messaging::UserCommunication::GetSendMessageTimeOutValue());
  v10 = FltSendMessage(*((PFLT_FILTER *)Streaming::gStrmFltData + 1), v9, a2, a3, a4, ReplyLength, &Timeout);
  if ( (v10 & 0x80000000) != 0 )
  {
    CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(v18);
    LogWrite(
      1,
      *CurrentActivityID,
      L"UserCommunication::SendMessage() - Send message to the streaming engine failed. Status 0x%08X.",
      v10);
    v12 = v19;
    if ( v19 && _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v10;
  }
  if ( v10 != 258 )
    return v10;
  v14 = (__int64 *)Streaming::Utils::GetCurrentActivityID(v18);
  LogWrite(
    1,
    *v14,
    L"UserCommunication::SendMessage() - Send message to the streaming engine failed. Status 0x%08X.",
    258);
  v15 = v19;
  if ( v19 )
  {
    if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  if ( (byte_14001F407 & 0x10) != 0 )
  {
    v16 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v18);
    McTemplateK0_EtwWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_Context,
      APPV_CLIENT_Evt_StreamFilter_SendMessageTimeout,
      *v16);
    v5 = 1;
  }
  if ( (v5 & 1) != 0 )
  {
    v17 = v19;
    if ( v19 )
    {
      if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
  }
  return 258;
}

```

## disassembly

```asm
0x140014364  mov     [rsp+arg_8], rbx
0x140014369  mov     [rsp+arg_10], rbp
0x14001436e  push    rsi
0x14001436f  push    rdi
0x140014370  push    r14
0x140014372  sub     rsp, 50h
0x140014376  xor     ebp, ebp
0x140014378  mov     rdi, r9
0x14001437b  mov     dword ptr [rsp+68h+arg_0], ebp
0x14001437f  mov     esi, r8d
0x140014382  mov     r14, rdx
0x140014385  cmp     [rcx+20h], bpl
0x140014389  jz      loc_14001453C
0x14001438f  lea     rbx, [rcx+8]
0x140014393  cmp     [rbx], rbp
0x140014396  jz      loc_14001453C
0x14001439c  call    ?GetSendMessageTimeOutValue@UserCommunication@Messaging@Streaming@@CAKXZ; Streaming::Messaging::UserCommunication::GetSendMessageTimeOutValue(void)
0x1400143a1  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x1400143a8  mov     r9d, esi; SenderBufferLength
0x1400143ab  imul    eax, 989680h
0x1400143b1  mov     r8, r14; SenderBuffer
0x1400143b4  mov     rdx, rbx; ClientPort
0x1400143b7  neg     rax
0x1400143ba  mov     qword ptr [rsp+68h+arg_0], rax
0x1400143bf  lea     rax, [rsp+68h+arg_0]
0x1400143c4  mov     rcx, [rcx+8]; Filter
0x1400143c8  mov     [rsp+68h+Timeout], rax; Timeout
0x1400143cd  mov     rax, [rsp+68h+arg_20]
0x1400143d5  mov     [rsp+68h+ReplyLength], rax; ReplyLength
0x1400143da  mov     [rsp+68h+ReplyBuffer], rdi; ReplyBuffer
0x1400143df  call    cs:__imp_FltSendMessage
0x1400143e6  nop     dword ptr [rax+rax+00h]
0x1400143eb  mov     esi, eax
0x1400143ed  test    eax, eax
0x1400143ef  jns     short loc_140014458
0x1400143f1  lea     rcx, [rsp+68h+var_28]
0x1400143f6  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x1400143fb  mov     r9d, esi
0x1400143fe  lea     r8, aUsercommunicat_3; "UserCommunication::SendMessage() - Send"...
0x140014405  lea     ecx, [rbp+1]
0x140014408  mov     rdx, [rax]
0x14001440b  call    LogWrite
0x140014410  mov     rdi, [rsp+68h+var_20]
0x140014415  test    rdi, rdi
0x140014418  jz      short loc_140014451
0x14001441a  or      ebx, 0FFFFFFFFh
0x14001441d  mov     eax, ebx
0x14001441f  lock xadd [rdi+8], eax
0x140014424  add     eax, ebx
0x140014426  jnz     short loc_140014451
0x140014428  mov     rax, [rdi]
0x14001442b  mov     rcx, rdi
0x14001442e  mov     rax, [rax+8]
0x140014432  call    _guard_dispatch_icall
0x140014437  mov     eax, ebx
0x140014439  lock xadd [rdi+0Ch], eax
0x14001443e  add     eax, ebx
0x140014440  jnz     short loc_140014451
0x140014442  mov     rax, [rdi]
0x140014445  mov     rcx, rdi
0x140014448  mov     rax, [rax+10h]
0x14001444c  call    _guard_dispatch_icall
0x140014451  mov     eax, esi
0x140014453  jmp     loc_140014541
0x140014458  mov     r14d, 102h
0x14001445e  cmp     esi, r14d
0x140014461  jnz     short loc_140014451
0x140014463  lea     rcx, [rsp+68h+var_28]
0x140014468  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14001446d  mov     r9d, r14d
0x140014470  lea     r8, aUsercommunicat_3; "UserCommunication::SendMessage() - Send"...
0x140014477  mov     ecx, 1
0x14001447c  mov     rdx, [rax]
0x14001447f  call    LogWrite
0x140014484  mov     rdi, [rsp+68h+var_20]
0x140014489  or      ebx, 0FFFFFFFFh
0x14001448c  test    rdi, rdi
0x14001448f  jz      short loc_1400144C5
0x140014491  mov     eax, ebx
0x140014493  lock xadd [rdi+8], eax
0x140014498  add     eax, ebx
0x14001449a  jnz     short loc_1400144C5
0x14001449c  mov     rax, [rdi]
0x14001449f  mov     rcx, rdi
0x1400144a2  mov     rax, [rax+8]
0x1400144a6  call    _guard_dispatch_icall
0x1400144ab  mov     eax, ebx
0x1400144ad  lock xadd [rdi+0Ch], eax
0x1400144b2  add     eax, ebx
0x1400144b4  jnz     short loc_1400144C5
0x1400144b6  mov     rax, [rdi]
0x1400144b9  mov     rcx, rdi
0x1400144bc  mov     rax, [rax+10h]
0x1400144c0  call    _guard_dispatch_icall
0x1400144c5  test    cs:byte_14001F407, 10h
0x1400144cc  jz      short loc_1400144F3
0x1400144ce  lea     rcx, [rsp+68h+var_28]
0x1400144d3  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x1400144d8  lea     rdx, APPV_CLIENT_Evt_StreamFilter_SendMessageTimeout
0x1400144df  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x1400144e6  mov     r8, [rax]
0x1400144e9  call    McTemplateK0_EtwWriteTransfer
0x1400144ee  mov     ebp, 1
0x1400144f3  test    bpl, 1
0x1400144f7  jz      short loc_140014537
0x1400144f9  mov     rdi, [rsp+68h+var_20]
0x1400144fe  test    rdi, rdi
0x140014501  jz      short loc_140014537
0x140014503  mov     eax, ebx
0x140014505  lock xadd [rdi+8], eax
0x14001450a  add     eax, ebx
0x14001450c  jnz     short loc_140014537
0x14001450e  mov     rax, [rdi]
0x140014511  mov     rcx, rdi
0x140014514  mov     rax, [rax+8]
0x140014518  call    _guard_dispatch_icall
0x14001451d  mov     edx, ebx
0x14001451f  lock xadd [rdi+0Ch], edx
0x140014524  add     edx, ebx
0x140014526  jnz     short loc_140014537
0x140014528  mov     rdx, [rdi]
0x14001452b  mov     rcx, rdi
0x14001452e  mov     rax, [rdx+10h]
0x140014532  call    _guard_dispatch_icall
0x140014537  mov     eax, r14d
0x14001453a  jmp     short loc_140014541
0x14001453c  mov     eax, 0C00000E5h
0x140014541  lea     r11, [rsp+68h+var_18]
0x140014546  mov     rbx, [r11+28h]
0x14001454a  mov     rbp, [r11+30h]
0x14001454e  mov     rsp, r11
0x140014551  pop     r14
0x140014553  pop     rdi
0x140014554  pop     rsi
0x140014555  retn
```
