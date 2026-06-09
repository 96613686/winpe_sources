# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::Update(uint)

- ea: `0x180012330`
- end: `0x1800123fe`
- name: `?Update@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UEAAJI@Z`
- size: `206`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800016a4`
- `0x180011e68`
- `0x180012330`
- `0x180015cf4`
- `0x180019010`

## string_xrefs

- `0x180012381`: `IncomingCallToastStatics: Update, callId`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::Update(
        WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this,
        unsigned int a2)
{
  int v3; // ebx
  __int64 v4; // r8
  int v5; // r9d
  const char *v7; // [rsp+40h] [rbp-18h] BYREF
  int v8; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v9; // [rsp+70h] [rbp+18h] BYREF
  __int64 v10; // [rsp+78h] [rbp+20h] BYREF

  v3 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 1) + 64LL))((char *)this - 8);
  if ( (unsigned int)dword_180025038 > 5
    && (qword_180025048 & 0x400000000000LL) != 0
    && (qword_180025050 & 0x400000000000LL) == qword_180025050 )
  {
    v8 = v3;
    v7 = "IncomingCallToastStatics: Update, callId";
    v10 = 0x1000000;
    v9 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      0,
      (unsigned int)byte_180020DBB,
      v4,
      v5,
      (__int64)&v7,
      (__int64)&v9,
      (__int64)&v10,
      (__int64)&v8);
  }
  if ( v3 >= 0 )
  {
    TraceLogging::IncomingCallToastUpdated(a2);
    return 0;
  }
  else
  {
    Log_HREvent_1((unsigned int)v3, 1, v4, 121);
    return (unsigned int)v3;
  }
}

```

## disassembly

```asm
0x180012330  mov     [rsp+arg_8], rbx
0x180012335  push    rdi
0x180012336  sub     rsp, 50h
0x18001233a  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18001233e  mov     edi, edx
0x180012340  mov     rax, [rcx]
0x180012343  mov     rax, [rax+40h]
0x180012347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001234c  mov     ecx, cs:dword_180025038
0x180012352  mov     ebx, eax
0x180012354  cmp     ecx, 5
0x180012357  jbe     short loc_1800123D2
0x180012359  mov     rax, cs:qword_180025050
0x180012360  mov     rdx, 400000000000h
0x18001236a  mov     rcx, cs:qword_180025048
0x180012371  test    rdx, rcx
0x180012374  jz      short loc_1800123D2
0x180012376  mov     rcx, rax
0x180012379  and     rcx, rdx
0x18001237c  cmp     rcx, rax
0x18001237f  jnz     short loc_1800123D2
0x180012381  lea     rax, aIncomingcallto_3; "IncomingCallToastStatics: Update, callI"...
0x180012388  mov     [rsp+58h+arg_0], ebx
0x18001238c  mov     [rsp+58h+var_18], rax
0x180012391  lea     rdx, byte_180020DBB
0x180012398  lea     rax, [rsp+58h+arg_0]
0x18001239d  mov     [rsp+58h+arg_18], 1000000h
0x1800123a6  mov     [rsp+58h+var_20], rax
0x1800123ab  lea     rax, [rsp+58h+arg_18]
0x1800123b0  mov     [rsp+58h+var_28], rax
0x1800123b5  lea     rax, [rsp+58h+arg_10]
0x1800123ba  mov     [rsp+58h+var_30], rax
0x1800123bf  lea     rax, [rsp+58h+var_18]
0x1800123c4  mov     [rsp+58h+var_38], rax
0x1800123c9  mov     [rsp+58h+arg_10], edi
0x1800123cd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800123d2  test    ebx, ebx
0x1800123d4  jns     short loc_1800123EA
0x1800123d6  mov     edx, 1
0x1800123db  mov     ecx, ebx
0x1800123dd  lea     r9d, [rdx+78h]
0x1800123e1  call    Log_HREvent_1
0x1800123e6  mov     eax, ebx
0x1800123e8  jmp     short loc_1800123F3
0x1800123ea  mov     ecx, edi; unsigned int
0x1800123ec  call    ?IncomingCallToastUpdated@TraceLogging@@SAXI@Z; TraceLogging::IncomingCallToastUpdated(uint)
0x1800123f1  xor     eax, eax
0x1800123f3  mov     rbx, [rsp+58h+arg_8]
0x1800123f8  add     rsp, 50h
0x1800123fc  pop     rdi
0x1800123fd  retn
```
