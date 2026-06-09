# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::Show(uint)

- ea: `0x1800120a0`
- end: `0x180012167`
- name: `?Show@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UEAAJI@Z`
- size: `199`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800016a4`
- `0x180011e68`
- `0x1800120a0`
- `0x180019010`

## string_xrefs

- `0x1800120f1`: `IncomingCallToastStatics: Show, callId`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::Show(
        WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this,
        int a2)
{
  int v3; // ebx
  __int64 v4; // r8
  int v5; // r9d
  const char *v7; // [rsp+40h] [rbp-18h] BYREF
  int v8; // [rsp+60h] [rbp+8h] BYREF
  int v9; // [rsp+70h] [rbp+18h] BYREF
  __int64 v10; // [rsp+78h] [rbp+20h] BYREF

  v3 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 1) + 64LL))((char *)this - 8);
  if ( (unsigned int)dword_180025038 > 4
    && (qword_180025048 & 0x400000000000LL) != 0
    && (qword_180025050 & 0x400000000000LL) == qword_180025050 )
  {
    v8 = v3;
    v7 = "IncomingCallToastStatics: Show, callId";
    v10 = 0x1000000;
    v9 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      0,
      (unsigned int)byte_180020E53,
      v4,
      v5,
      (__int64)&v7,
      (__int64)&v9,
      (__int64)&v10,
      (__int64)&v8);
  }
  if ( v3 >= 0 )
    return 0;
  Log_HREvent_1((unsigned int)v3, 1, v4, 81);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800120a0  mov     [rsp+arg_8], rbx
0x1800120a5  push    rdi
0x1800120a6  sub     rsp, 50h
0x1800120aa  add     rcx, 0FFFFFFFFFFFFFFF8h
0x1800120ae  mov     edi, edx
0x1800120b0  mov     rax, [rcx]
0x1800120b3  mov     rax, [rax+40h]
0x1800120b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120bc  mov     ecx, cs:dword_180025038
0x1800120c2  mov     ebx, eax
0x1800120c4  cmp     ecx, 4
0x1800120c7  jbe     short loc_180012142
0x1800120c9  mov     rax, cs:qword_180025050
0x1800120d0  mov     rdx, 400000000000h
0x1800120da  mov     rcx, cs:qword_180025048
0x1800120e1  test    rdx, rcx
0x1800120e4  jz      short loc_180012142
0x1800120e6  mov     rcx, rax
0x1800120e9  and     rcx, rdx
0x1800120ec  cmp     rcx, rax
0x1800120ef  jnz     short loc_180012142
0x1800120f1  lea     rax, aIncomingcallto_5; "IncomingCallToastStatics: Show, callId"
0x1800120f8  mov     [rsp+58h+arg_0], ebx
0x1800120fc  mov     [rsp+58h+var_18], rax
0x180012101  lea     rdx, byte_180020E53
0x180012108  lea     rax, [rsp+58h+arg_0]
0x18001210d  mov     [rsp+58h+arg_18], 1000000h
0x180012116  mov     [rsp+58h+var_20], rax
0x18001211b  lea     rax, [rsp+58h+arg_18]
0x180012120  mov     [rsp+58h+var_28], rax
0x180012125  lea     rax, [rsp+58h+arg_10]
0x18001212a  mov     [rsp+58h+var_30], rax
0x18001212f  lea     rax, [rsp+58h+var_18]
0x180012134  mov     [rsp+58h+var_38], rax
0x180012139  mov     [rsp+58h+arg_10], edi
0x18001213d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180012142  test    ebx, ebx
0x180012144  jns     short loc_18001215A
0x180012146  mov     edx, 1
0x18001214b  mov     ecx, ebx
0x18001214d  lea     r9d, [rdx+50h]
0x180012151  call    Log_HREvent_1
0x180012156  mov     eax, ebx
0x180012158  jmp     short loc_18001215C
0x18001215a  xor     eax, eax
0x18001215c  mov     rbx, [rsp+58h+arg_8]
0x180012161  add     rsp, 50h
0x180012165  pop     rdi
0x180012166  retn
```
