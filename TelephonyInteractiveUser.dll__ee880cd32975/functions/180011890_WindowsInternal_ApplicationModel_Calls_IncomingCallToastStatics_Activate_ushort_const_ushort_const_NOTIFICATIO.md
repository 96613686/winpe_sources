# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::Activate(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)

- ea: `0x180011890`
- end: `0x1800119a1`
- name: `?Activate@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UEAAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z`
- size: `273`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this, const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000155c`
- `0x180011890`
- `0x180011e68`
- `0x180019010`

## string_xrefs

- `0x18001191d`: `IncomingCallToastStatics: Activated, arguments`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::Activate(
        WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct NOTIFICATION_USER_INPUT_DATA *a4)
{
  int v6; // eax
  __int64 v7; // r8

  if ( (unsigned int)dword_180025038 > 4
    && (qword_180025048 & 0x400000000000LL) != 0
    && (qword_180025050 & 0x400000000000LL) == qword_180025050 )
  {
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      0x400000000000LL,
      &byte_180020D4F);
  }
  v6 = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *))(*((_QWORD *)this - 2) + 192LL))(
         (char *)this - 16,
         a3,
         a3,
         a4);
  if ( v6 < 0 )
    Log_HREvent_1((unsigned int)v6, 0, v7, 144);
  return 0;
}

```

## disassembly

```asm
0x180011890  mov     r11, rsp
0x180011893  mov     [r11+10h], rbx
0x180011897  push    rdi
0x180011898  sub     rsp, 70h
0x18001189c  mov     eax, cs:dword_180025038
0x1800118a2  mov     rbx, r8
0x1800118a5  mov     rdi, rcx
0x1800118a8  cmp     eax, 4
0x1800118ab  jbe     loc_180011968
0x1800118b1  mov     rdx, cs:qword_180025050
0x1800118b8  mov     rcx, 400000000000h
0x1800118c2  mov     rax, cs:qword_180025048
0x1800118c9  test    rcx, rax
0x1800118cc  jz      loc_180011968
0x1800118d2  mov     rax, rdx
0x1800118d5  and     rax, rcx
0x1800118d8  cmp     rax, rdx
0x1800118db  jnz     loc_180011968
0x1800118e1  mov     qword ptr [r11-28h], 1000800h
0x1800118e9  test    r9, r9
0x1800118ec  jz      short loc_1800118FB
0x1800118ee  mov     rax, [r9+8]
0x1800118f2  mov     [r11+8], rax
0x1800118f6  mov     rax, [r9]
0x1800118f9  jmp     short loc_180011911
0x1800118fb  lea     rax, aNoValue; "no value"
0x180011902  mov     [rsp+78h+arg_0], rax
0x18001190a  lea     rax, aNoKey; "no key"
0x180011911  mov     [rsp+78h+var_20], rax
0x180011916  lea     rdx, byte_180020D4F
0x18001191d  lea     rax, aIncomingcallto_0; "IncomingCallToastStatics: Activated, ar"...
0x180011924  mov     [rsp+78h+var_18], rbx
0x180011929  mov     [rsp+78h+var_10], rax
0x18001192e  lea     rax, [rsp+78h+var_28]
0x180011933  mov     [rsp+78h+var_38], rax
0x180011938  lea     rax, [rsp+78h+arg_0]
0x180011940  mov     [rsp+78h+var_40], rax
0x180011945  lea     rax, [rsp+78h+var_20]
0x18001194a  mov     [rsp+78h+var_48], rax
0x18001194f  lea     rax, [rsp+78h+var_18]
0x180011954  mov     [rsp+78h+var_50], rax
0x180011959  lea     rax, [rsp+78h+var_10]
0x18001195e  mov     [rsp+78h+var_58], rax
0x180011963  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180011968  lea     rcx, [rdi-10h]
0x18001196c  mov     rdx, rbx
0x18001196f  mov     rax, [rcx]
0x180011972  mov     rax, [rax+0C0h]
0x180011979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001197e  test    eax, eax
0x180011980  jns     short loc_180011991
0x180011982  xor     edx, edx
0x180011984  mov     r9d, 90h
0x18001198a  mov     ecx, eax
0x18001198c  call    Log_HREvent_1
0x180011991  mov     rbx, [rsp+78h+arg_8]
0x180011999  xor     eax, eax
0x18001199b  add     rsp, 70h
0x18001199f  pop     rdi
0x1800119a0  retn
```
