# GetHidForceFeedbackBrokerFactory(_GUID const &,_GUID const &,void * *)

- ea: `0x180014e3c`
- end: `0x180014f10`
- name: `?GetHidForceFeedbackBrokerFactory@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `212`
- prototype: `int(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003750`

## callees

- `0x180001304`
- `0x18000d68c`
- `0x180014e3c`
- `0x18004c881`

## pseudocode

```c
__int64 __fastcall GetHidForceFeedbackBrokerFactory(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  __int64 v4; // r8
  __int64 v5; // r9
  const char *v7; // [rsp+40h] [rbp-18h] BYREF
  const struct _GUID *v8; // [rsp+60h] [rbp+8h] BYREF
  int v9; // [rsp+78h] [rbp+20h] BYREF

  v8 = a1;
  if ( !memcmp_0(a2, &GUID_00000001_0000_0000_c000_000000000046, 0x10u) )
  {
    if ( !_InterlockedIncrement(&dword_180069068) )
    {
      GameInputFailFast(2147500036LL, 28);
      JUMPOUT(0x180014F0FLL);
    }
    *a3 = &g_hidForceFeedbackBrokerFactory;
    return 0;
  }
  else
  {
    *a3 = 0;
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      LODWORD(v8) = -2147467262;
      v7 = "onecore\\xbox\\gameinput\\feedback\\gameinputfeedback.cpp";
      v9 = 172;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned __int8 *)byte_18005CB41,
        v4,
        v5,
        (__int64 **)&v7,
        (__int64)&v9,
        (__int64)&v8);
    }
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x180014e3c  mov     [rsp+arg_0], rcx
0x180014e41  push    rbx
0x180014e42  sub     rsp, 50h
0x180014e46  mov     rbx, r8
0x180014e49  mov     rcx, rdx; Buf1
0x180014e4c  mov     r8d, 10h; Size
0x180014e52  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046; Buf2
0x180014e59  call    memcmp_0
0x180014e5e  test    eax, eax
0x180014e60  jnz     short loc_180014E7F
0x180014e62  nop
0x180014e63  lock inc cs:dword_180069068
0x180014e6a  nop
0x180014e6b  jz      loc_180014F00
0x180014e71  lea     rax, ?g_hidForceFeedbackBrokerFactory@@3VHidForceFeedbackBrokerFactory@@A; HidForceFeedbackBrokerFactory g_hidForceFeedbackBrokerFactory
0x180014e78  mov     [rbx], rax
0x180014e7b  xor     eax, eax
0x180014e7d  jmp     short loc_180014EF9
0x180014e7f  mov     qword ptr [rbx], 0
0x180014e86  mov     eax, cs:dword_180069000
0x180014e8c  cmp     eax, 2
0x180014e8f  jbe     short loc_180014EF4
0x180014e91  mov     rcx, cs:qword_180069018
0x180014e98  mov     rax, cs:qword_180069010
0x180014e9f  test    al, 8
0x180014ea1  jz      short loc_180014EF4
0x180014ea3  mov     rax, rcx
0x180014ea6  and     eax, 8
0x180014ea9  cmp     rax, rcx
0x180014eac  jnz     short loc_180014EF4
0x180014eae  lea     rax, aOnecoreXboxGam_28; "onecore\\xbox\\gameinput\\feedback\\gam"...
0x180014eb5  mov     dword ptr [rsp+58h+arg_0], 80004002h
0x180014ebd  mov     [rsp+58h+var_18], rax
0x180014ec2  lea     rdx, byte_18005CB41
0x180014ec9  lea     rax, [rsp+58h+arg_0]
0x180014ece  mov     [rsp+58h+arg_18], 0ACh
0x180014ed6  mov     [rsp+58h+var_28], rax
0x180014edb  lea     rax, [rsp+58h+arg_18]
0x180014ee0  mov     [rsp+58h+var_30], rax
0x180014ee5  lea     rax, [rsp+58h+var_18]
0x180014eea  mov     [rsp+58h+var_38], rax
0x180014eef  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180014ef4  mov     eax, 80004002h
0x180014ef9  add     rsp, 50h
0x180014efd  pop     rbx
0x180014efe  retn
0x180014f00  mov     edx, 1Ch
0x180014f05  mov     ecx, 80004004h
0x180014f0a  call    GameInputFailFast
```
