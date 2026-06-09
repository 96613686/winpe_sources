# Broker::TimeBroker::OnTimerExpired(Broker::TimeBroker::TimeSource)

- ea: `0x180001c14`
- end: `0x180001ed0`
- name: `?OnTimerExpired@TimeBroker@Broker@@AEAAXW4TimeSource@12@@Z`
- size: `700`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `6`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180001ba4`
- `0x180014970`
- `0x180015178`
- `0x1800152fc`
- `0x1800165b0`
- `0x180016650`

## callees

- `0x180001c14`
- `0x180003840`
- `0x180005d10`
- `0x180007c60`
- `0x180009fc0`
- `0x18000b0d0`
- `0x18000bba0`
- `0x18000bbf0`
- `0x18000d2a8`
- `0x18000ee60`
- `0x180012dd0`
- `0x18001579c`

## pseudocode

```c
__int64 __fastcall Broker::TimeBroker::OnTimerExpired(__int64 a1, int a2)
{
  int v4; // edx
  __int64 result; // rax
  __int64 v6; // rcx
  _BOOL8 v7; // [rsp+30h] [rbp-98h] BYREF
  Broker::TimeBroker *v8; // [rsp+38h] [rbp-90h]
  _BOOL8 v9; // [rsp+40h] [rbp-88h] BYREF
  _BOOL8 v10; // [rsp+48h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+50h] [rbp-78h] BYREF
  _BOOL8 *v12; // [rsp+70h] [rbp-58h]
  __int64 v13; // [rsp+78h] [rbp-50h]
  _BOOL8 *v14; // [rsp+80h] [rbp-48h]
  __int64 v15; // [rsp+88h] [rbp-40h]
  _BOOL8 *v16; // [rsp+90h] [rbp-38h]
  __int64 v17; // [rsp+98h] [rbp-30h]

  v8 = (Broker::TimeBroker *)a1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_i(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids,
      *(_QWORD *)(a1 + 200));
  if ( (unsigned int)dword_180026058 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180026058, 0x200000000000LL) )
  {
    v7 = a2 == 2;
    v9 = a2 == 1;
    v10 = a2 == 0;
    v16 = &v7;
    v17 = 8;
    v14 = &v9;
    v15 = 8;
    v12 = &v10;
    v13 = 8;
    tlgWriteAgg((int)&dword_180026058, (int)&word_18002095E, 0, 5, &v11);
  }
  if ( (unsigned int)dword_180026058 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180026058, 8) )
  {
    LODWORD(v7) = a2;
    v12 = &v7;
    v13 = 4;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)&dword_180026058,
      (unsigned __int8 *)byte_18002082D,
      0,
      0,
      v4 - 5,
      &v11);
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( a2 )
    {
      if ( a2 == 1 )
        goto LABEL_15;
    }
    else if ( *(_BYTE *)(a1 + 160) )
    {
      *(_BYTE *)(a1 + 160) = 0;
      *(_DWORD *)(a1 + 164) *= 2;
      Broker::TimeBroker::RegenerateTimerWheels((Broker::TimeBroker *)a1);
      ((void (__fastcall *)(Broker::SystemTimer *, union _LARGE_INTEGER))Broker::SystemTimer::SetTimer)(
        *(Broker::SystemTimer **)(a1 + 112),
        0);
      *(_DWORD *)(a1 + 164) = 600000000;
    }
    if ( *(_DWORD *)(a1 + 168) != 1 )
    {
LABEL_16:
      Broker::TimeBroker::ExpireTimers((Broker::TimeBroker *)a1, a1);
      Broker::TimeBroker::ExpireTimers((Broker::TimeBroker *)a1, a1 + 16);
      ((void (__fastcall *)(Broker::TimeBroker *))Broker::TimeBroker::SetSytemTimer)((Broker::TimeBroker *)a1);
      goto LABEL_25;
    }
LABEL_15:
    Broker::TimeBroker::ExpireTimers((Broker::TimeBroker *)a1, a1 + 64);
    goto LABEL_16;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      ((void (__fastcall *)(Broker::TimeBroker *))Broker::TimeBroker::SubmitLowMemoryWorker)(v8);
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180001E49);
      goto LABEL_25;
    }
    if ( __eh34_catch_type(0, &Broker::Win32Error `RTTI Type Descriptor', 0) )
    {
      ((void (__fastcall *)(Broker::TimeBroker *))Broker::TimeBroker::SubmitLowMemoryWorker)(v8);
      __eh34_try_continuation(0, &Broker::Win32Error `RTTI Type Descriptor', &loc_180001ECB);
      goto LABEL_25;
    }
    if ( __eh34_catch_type(0, &Broker::BILayer::Failure `RTTI Type Descriptor', 0) )
    {
      ((void (__fastcall *)(Broker::TimeBroker *))Broker::TimeBroker::SubmitLowMemoryWorker)(v8);
      __eh34_try_continuation(0, &Broker::BILayer::Failure `RTTI Type Descriptor', &loc_180001E49);
    }
  }
LABEL_25:
  result = (unsigned int)dword_180026058;
  if ( (unsigned int)dword_180026058 > 5 )
  {
    result = tlgKeywordOn(&dword_180026058, 8);
    if ( (_BYTE)result )
      result = _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                 v6,
                 (__int64)word_18002060A);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180001c14  mov     [rsp+arg_8], rbx
0x180001c19  mov     [rsp+arg_10], rsi
0x180001c1e  push    rdi
0x180001c1f  push    r14
0x180001c21  push    r15
0x180001c23  sub     rsp, 0B0h
0x180001c2a  mov     rax, cs:__security_cookie
0x180001c31  xor     rax, rsp
0x180001c34  mov     [rsp+0C8h+var_28], rax
0x180001c3c  mov     r14d, edx
0x180001c3f  mov     rbx, rcx
0x180001c42  mov     [rsp+0C8h+var_90], rcx
0x180001c47  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c4e  mov     edi, 4
0x180001c53  test    byte ptr [rcx+1Ch], 1
0x180001c57  jz      short loc_180001C79
0x180001c59  cmp     [rcx+19h], dil
0x180001c5d  jb      short loc_180001C79
0x180001c5f  lea     edx, [rdi+2Ch]
0x180001c62  mov     r9, [rbx+0C8h]
0x180001c69  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180001c70  mov     rcx, [rcx+10h]
0x180001c74  call    WPP_SF_i
0x180001c79  mov     eax, cs:dword_180026058
0x180001c7f  cmp     eax, 5
0x180001c82  jbe     loc_180001D3C
0x180001c88  mov     rdx, 200000000000h
0x180001c92  lea     rcx, dword_180026058
0x180001c99  call    _tlgKeywordOn
0x180001c9e  test    al, al
0x180001ca0  jz      loc_180001D3C
0x180001ca6  xor     eax, eax
0x180001ca8  lea     esi, [rax+2]
0x180001cab  cmp     r14d, esi
0x180001cae  setz    al
0x180001cb1  mov     [rsp+0C8h+var_98], rax
0x180001cb6  xor     eax, eax
0x180001cb8  cmp     r14d, 1
0x180001cbc  setz    al
0x180001cbf  mov     [rsp+0C8h+var_88], rax
0x180001cc4  xor     eax, eax
0x180001cc6  test    r14d, r14d
0x180001cc9  setz    al
0x180001ccc  mov     [rsp+0C8h+var_80], rax
0x180001cd1  lea     rax, [rsp+0C8h+var_98]
0x180001cd6  mov     [rsp+0C8h+var_38], rax
0x180001cde  mov     [rsp+0C8h+var_30], 8
0x180001cea  lea     rax, [rsp+0C8h+var_88]
0x180001cef  mov     [rsp+0C8h+var_48], rax
0x180001cf7  mov     [rsp+0C8h+var_40], 8
0x180001d03  lea     rax, [rsp+0C8h+var_80]
0x180001d08  mov     [rsp+0C8h+var_58], rax
0x180001d0d  mov     [rsp+0C8h+var_50], 8
0x180001d16  lea     rax, [rsp+0C8h+var_78]
0x180001d1b  mov     [rsp+0C8h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x180001d20  lea     r9d, [rsi+3]; int
0x180001d24  xor     r8d, r8d; int
0x180001d27  lea     rdx, word_18002095E; int
0x180001d2e  lea     rcx, dword_180026058; int
0x180001d35  call    _tlgWriteAgg
0x180001d3a  jmp     short loc_180001D41
0x180001d3c  mov     esi, 2
0x180001d41  mov     eax, cs:dword_180026058
0x180001d47  cmp     eax, 5
0x180001d4a  jbe     short loc_180001DA7
0x180001d4c  mov     edx, 8
0x180001d51  lea     rcx, dword_180026058
0x180001d58  call    _tlgKeywordOn
0x180001d5d  test    al, al
0x180001d5f  jz      short loc_180001DA7
0x180001d61  mov     dword ptr [rsp+0C8h+var_98], r14d
0x180001d66  lea     rax, [rsp+0C8h+var_98]
0x180001d6b  mov     [rsp+0C8h+var_58], rax
0x180001d70  mov     [rsp+0C8h+var_50], 4
0x180001d79  lea     rax, [rsp+0C8h+var_78]
0x180001d7e  mov     [rsp+0C8h+var_A0], rax
0x180001d83  lea     r15d, [rdx-5]
0x180001d87  mov     dword ptr [rsp+0C8h+var_A8], r15d
0x180001d8c  xor     r9d, r9d
0x180001d8f  xor     r8d, r8d
0x180001d92  lea     rdx, byte_18002082D
0x180001d99  lea     rcx, dword_180026058
0x180001da0  call    _tlgWriteTransfer_EventWriteTransfer
0x180001da5  jmp     short loc_180001DAD
0x180001da7  mov     r15d, 3
0x180001dad  test    r14d, r14d
0x180001db0  jnz     short loc_180001DEF
0x180001db2  cmp     [rbx+0A0h], r14b
0x180001db9  jz      short loc_180001DF5
0x180001dbb  mov     [rbx+0A0h], r14b
0x180001dc2  mov     eax, [rbx+0A4h]
0x180001dc8  add     eax, eax
0x180001dca  mov     [rbx+0A4h], eax
0x180001dd0  mov     rcx, rbx; this
0x180001dd3  call    ?RegenerateTimerWheels@TimeBroker@Broker@@AEAAXXZ; Broker::TimeBroker::RegenerateTimerWheels(void)
0x180001dd8  xor     edx, edx; union _LARGE_INTEGER
0x180001dda  mov     rcx, [rbx+70h]; this
0x180001dde  call    ?SetTimer@SystemTimer@Broker@@QEAAX_J@Z; Broker::SystemTimer::SetTimer(__int64)
0x180001de3  mov     dword ptr [rbx+0A4h], 23C34600h
0x180001ded  jmp     short loc_180001DF5
0x180001def  cmp     r14d, 1
0x180001df3  jz      short loc_180001E00
0x180001df5  cmp     dword ptr [rbx+0A8h], 1
0x180001dfc  jnz     short loc_180001E1E
0x180001dfe  jmp     short loc_180001E0F
0x180001e00  cmovnz  esi, edi
0x180001e03  cmp     dword ptr [rbx+0A8h], 1
0x180001e0a  jz      short loc_180001E0F
0x180001e0c  mov     r15d, esi
0x180001e0f  lea     rdx, [rbx+40h]
0x180001e13  mov     r8d, r15d
0x180001e16  mov     rcx, rbx
0x180001e19  call    ?ExpireTimers@TimeBroker@Broker@@AEAAXAEAVTimerWheel@2@W4_TB_TIMER_EXPIRY_REASON@12@@Z; Broker::TimeBroker::ExpireTimers(Broker::TimerWheel &,Broker::TimeBroker::_TB_TIMER_EXPIRY_REASON)
0x180001e1e  xor     r8d, r8d
0x180001e21  mov     rdx, rbx
0x180001e24  mov     rcx, rbx
0x180001e27  call    ?ExpireTimers@TimeBroker@Broker@@AEAAXAEAVTimerWheel@2@W4_TB_TIMER_EXPIRY_REASON@12@@Z; Broker::TimeBroker::ExpireTimers(Broker::TimerWheel &,Broker::TimeBroker::_TB_TIMER_EXPIRY_REASON)
0x180001e2c  lea     rdx, [rbx+10h]
0x180001e30  mov     r8d, 1
0x180001e36  mov     rcx, rbx
0x180001e39  call    ?ExpireTimers@TimeBroker@Broker@@AEAAXAEAVTimerWheel@2@W4_TB_TIMER_EXPIRY_REASON@12@@Z; Broker::TimeBroker::ExpireTimers(Broker::TimerWheel &,Broker::TimeBroker::_TB_TIMER_EXPIRY_REASON)
0x180001e3e  mov     rcx, rbx; this
0x180001e41  call    ?SetSytemTimer@TimeBroker@Broker@@AEAAXXZ; Broker::TimeBroker::SetSytemTimer(void)
0x180001e46  nop
0x180001e47  jmp     short loc_180001E4E
0x180001e49  mov     edi, 4
0x180001e4e  mov     eax, cs:dword_180026058
0x180001e54  cmp     eax, 5
0x180001e57  jbe     short loc_180001E7A
0x180001e59  mov     edx, 8
0x180001e5e  lea     rcx, dword_180026058
0x180001e65  call    _tlgKeywordOn
0x180001e6a  test    al, al
0x180001e6c  jz      short loc_180001E7A
0x180001e6e  lea     rdx, word_18002060A
0x180001e75  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180001e7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e81  test    byte ptr [rcx+1Ch], 1
0x180001e85  jz      short loc_180001EA2
0x180001e87  cmp     [rcx+19h], dil
0x180001e8b  jb      short loc_180001EA2
0x180001e8d  mov     edx, 31h ; '1'
0x180001e92  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180001e99  mov     rcx, [rcx+10h]
0x180001e9d  call    WPP_SF_
0x180001ea2  mov     rcx, [rsp+0C8h+var_28]
0x180001eaa  xor     rcx, rsp; StackCookie
0x180001ead  call    __security_check_cookie
0x180001eb2  lea     r11, [rsp+0C8h+var_18]
0x180001eba  mov     rbx, [r11+28h]
0x180001ebe  mov     rsi, [r11+30h]
0x180001ec2  mov     rsp, r11
0x180001ec5  pop     r15
0x180001ec7  pop     r14
0x180001ec9  pop     rdi
0x180001eca  retn
0x180001ecb  jmp     loc_180001E49
```
