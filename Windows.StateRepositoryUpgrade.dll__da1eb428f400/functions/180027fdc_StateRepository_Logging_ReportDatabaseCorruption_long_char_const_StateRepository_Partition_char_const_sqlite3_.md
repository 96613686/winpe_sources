# StateRepository::Logging::ReportDatabaseCorruption(long,char const *,StateRepository::Partition,char const *,sqlite3 *,char const *,unsigned __int64,unsigned __int64)

- ea: `0x180027fdc`
- end: `0x1800281f9`
- name: `?ReportDatabaseCorruption@Logging@StateRepository@@YAJJPEBDW4Partition@2@0PEAUsqlite3@@0_K3@Z`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180028200`

## callees

- `0x180001aac`
- `0x180002e54`
- `0x18000a3c0`
- `0x18000c3bc`
- `0x180018ef0`
- `0x1800237bc`
- `0x180024d40`
- `0x180027fdc`
- `0x180028c4c`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002808c`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002808c`

## string_xrefs

- `0x180028038`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`
- `0x1800281cf`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`

## pseudocode

```c
__int64 StateRepository::Logging::ReportDatabaseCorruption(int a1, __int64 a2, unsigned int a3, __int64 a4, ...)
{
  int DatabaseCorruptionLastReported; // eax
  StateRepository::DataType::Temporal *v6; // rcx
  unsigned int v7; // ebx
  const unsigned __int16 *Now; // rbx
  int v10; // edx
  const unsigned __int16 *v11; // r14
  int v12; // ecx
  const unsigned __int16 *v13; // rsi
  StateRepository::DataType::Temporal *v14; // rcx
  __int64 v15; // r15
  __int64 v16; // r12
  __int64 v17; // r13
  int v18; // r8d
  int v19; // r9d
  int Reported; // eax
  int v21; // [rsp+28h] [rbp-91h]
  const unsigned __int16 *v22; // [rsp+78h] [rbp-41h] BYREF
  __int64 v23; // [rsp+80h] [rbp-39h] BYREF
  const unsigned __int16 *v24; // [rsp+88h] [rbp-31h] BYREF
  __int64 v25; // [rsp+90h] [rbp-29h] BYREF
  __int64 v26; // [rsp+98h] [rbp-21h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v28; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v29[9]; // [rsp+B0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+47h]
  unsigned int v33; // [rsp+118h] [rbp+5Fh] BYREF
  __int64 v34; // [rsp+120h] [rbp+67h]
  unsigned __int64 UnbiasedTime; // [rsp+128h] [rbp+6Fh] BYREF
  va_list UnbiasedTimea; // [rsp+128h] [rbp+6Fh]
  __int64 v37; // [rsp+130h] [rbp+77h]
  __int64 v38; // [rsp+138h] [rbp+7Fh]
  __int64 v39; // [rsp+140h] [rbp+87h]
  va_list va1; // [rsp+148h] [rbp+8Fh] BYREF

  va_start(va1, a4);
  va_start(UnbiasedTimea, a4);
  UnbiasedTime = va_arg(va1, _QWORD);
  v37 = va_arg(va1, _QWORD);
  v38 = va_arg(va1, _QWORD);
  v39 = va_arg(va1, _QWORD);
  v34 = a4;
  if ( a3 )
  {
    v23 = 0;
    UnbiasedTime = 0;
    v22 = 0;
    DatabaseCorruptionLastReported = StateRepository::Globals::GetDatabaseCorruptionLastReported(
                                       a3,
                                       &v23,
                                       (unsigned __int64 *)UnbiasedTimea,
                                       &v22);
    v7 = DatabaseCorruptionLastReported;
    if ( DatabaseCorruptionLastReported < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x241,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
        (const char *)(unsigned int)DatabaseCorruptionLastReported,
        v21);
      return v7;
    }
    Now = (const unsigned __int16 *)UnbiasedTime;
    if ( !UnbiasedTime )
    {
      UnbiasedTime = 0;
      QueryUnbiasedInterruptTime((PULONGLONG)UnbiasedTimea);
      v13 = (const unsigned __int16 *)UnbiasedTime;
      Now = (const unsigned __int16 *)StateRepository::DataType::Temporal::GetNow(v14);
      v11 = Now;
      goto LABEL_8;
    }
    v11 = (const unsigned __int16 *)StateRepository::DataType::Temporal::GetNow(v6);
    v12 = (_DWORD)v11 - (_DWORD)v22;
    if ( (unsigned __int64)((char *)v11 - (char *)v22) >= 0x324A9A7000LL )
    {
      v13 = (const unsigned __int16 *)v23;
LABEL_8:
      v15 = v39;
      v16 = v38;
      v17 = v37;
      if ( Microsoft_Windows_StateRepositoryEnableBits < 0 )
        McTemplateU0dsdssxxxx_EventWriteTransfer(v12, v10, a1, a2, a3, v34, v37, v38, v39, (char)v13, (char)Now);
      if ( *(_DWORD *)qword_18004BFB0 > 1u
        && (unsigned __int8)tlgKeywordOn(qword_18004BFB0, 0x400000000000LL, qword_18004BFB0) )
      {
        v28 = v34;
        v29[0] = a2;
        LODWORD(UnbiasedTime) = a1;
        v23 = 0x1000000;
        v22 = Now;
        v24 = v13;
        v25 = v15;
        v26 = v16;
        v27 = v17;
        v33 = a3;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          v18,
          (unsigned int)&word_180045BEE,
          v18,
          v19,
          (__int64)UnbiasedTimea,
          (__int64)v29,
          (__int64)&v33,
          (__int64)&v28,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v22,
          (__int64)&v23);
      }
      Reported = StateRepository::Globals::SetDatabaseCorruptionLastReported(a3, v13, Now, v11);
      if ( Reported < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x267,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
          (const char *)(unsigned int)Reported,
          v21);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180027fdc  mov     rax, rsp
0x180027fdf  mov     [rax+20h], r9
0x180027fe3  mov     [rax+10h], rdx
0x180027fe7  mov     [rax+8], ecx
0x180027fea  push    rbp
0x180027feb  push    rbx
0x180027fec  push    rsi
0x180027fed  push    rdi
0x180027fee  push    r12
0x180027ff0  push    r13
0x180027ff2  push    r14
0x180027ff4  push    r15
0x180027ff6  lea     rbp, [rax-47h]
0x180027ffa  sub     rsp, 0B8h
0x180028001  xor     esi, esi
0x180028003  mov     edi, r8d
0x180028006  test    r8d, r8d
0x180028009  jz      loc_1800281E3
0x18002800f  lea     r9, [rbp+3Fh+var_80]
0x180028013  mov     [rbp+3Fh+var_78], rsi
0x180028017  lea     r8, [rbp+3Fh+UnbiasedTime]
0x18002801b  mov     [rbp+3Fh+UnbiasedTime], rsi
0x18002801f  lea     rdx, [rbp+3Fh+var_78]
0x180028023  mov     [rbp+3Fh+var_80], rsi
0x180028027  mov     ecx, edi
0x180028029  call    ?GetDatabaseCorruptionLastReported@Globals@StateRepository@@YAJW4Partition@2@PEA_K11@Z; StateRepository::Globals::GetDatabaseCorruptionLastReported(StateRepository::Partition,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)
0x18002802e  mov     ebx, eax
0x180028030  test    eax, eax
0x180028032  jns     short loc_180028053
0x180028034  mov     rcx, [rbp+47h]; this
0x180028038  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x18002803f  mov     r9d, eax; char *
0x180028042  mov     edx, 241h; void *
0x180028047  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002804c  mov     eax, ebx
0x18002804e  jmp     loc_1800281E5
0x180028053  mov     rbx, [rbp+3Fh+UnbiasedTime]
0x180028057  test    rbx, rbx
0x18002805a  jz      short loc_180028084
0x18002805c  call    ?GetNow@Temporal@DataType@StateRepository@@YA_KXZ; StateRepository::DataType::Temporal::GetNow(void)
0x180028061  mov     rcx, rax
0x180028064  mov     r14, rax
0x180028067  sub     rcx, [rbp+3Fh+var_80]
0x18002806b  mov     rax, 324A9A7000h
0x180028075  cmp     rcx, rax
0x180028078  jb      loc_1800281E3
0x18002807e  mov     rsi, [rbp+3Fh+var_78]
0x180028082  jmp     short loc_1800280A1
0x180028084  lea     rcx, [rbp+3Fh+UnbiasedTime]; UnbiasedTime
0x180028088  mov     [rbp+3Fh+UnbiasedTime], rsi
0x18002808c  call    cs:__imp_QueryUnbiasedInterruptTime
0x180028092  mov     rsi, [rbp+3Fh+UnbiasedTime]
0x180028096  call    ?GetNow@Temporal@DataType@StateRepository@@YA_KXZ; StateRepository::DataType::Temporal::GetNow(void)
0x18002809b  mov     rbx, rax
0x18002809e  mov     r14, rax
0x1800280a1  cmp     cs:Microsoft_Windows_StateRepositoryEnableBits, 0
0x1800280a8  mov     r15, [rbp+3Fh+arg_38]
0x1800280af  mov     r12, [rbp+3Fh+arg_30]
0x1800280b3  mov     r13, [rbp+3Fh+arg_28]
0x1800280b7  jge     short loc_1800280EC
0x1800280b9  mov     rax, [rbp+3Fh+arg_18]
0x1800280bd  mov     r9, [rbp+3Fh+arg_8]
0x1800280c1  mov     r8d, [rbp+3Fh+arg_0]
0x1800280c5  mov     [rsp+0F0h+var_A0], rbx
0x1800280ca  mov     [rsp+0F0h+var_A8], rsi
0x1800280cf  mov     [rsp+0F0h+var_B0], r15
0x1800280d4  mov     [rsp+0F0h+var_B8], r12
0x1800280d9  mov     [rsp+0F0h+var_C0], r13
0x1800280de  mov     [rsp+0F0h+var_C8], rax
0x1800280e3  mov     [rsp+0F0h+var_D0], edi
0x1800280e7  call    McTemplateU0dsdssxxxx_EventWriteTransfer
0x1800280ec  mov     r8, cs:qword_18004BFB0
0x1800280f3  mov     eax, [r8]
0x1800280f6  cmp     eax, 1
0x1800280f9  jbe     loc_1800281B7
0x1800280ff  mov     rdx, 400000000000h
0x180028109  mov     rcx, r8
0x18002810c  call    _tlgKeywordOn
0x180028111  test    al, al
0x180028113  jz      loc_1800281B7
0x180028119  mov     rax, [rbp+3Fh+arg_18]
0x18002811d  lea     rdx, word_180045BEE
0x180028124  mov     [rbp+3Fh+var_50], rax
0x180028128  mov     rcx, r8
0x18002812b  mov     rax, [rbp+3Fh+arg_8]
0x18002812f  mov     [rbp+3Fh+var_48], rax
0x180028133  mov     eax, [rbp+3Fh+arg_0]
0x180028136  mov     dword ptr [rbp+3Fh+UnbiasedTime], eax
0x180028139  lea     rax, [rbp+3Fh+var_78]
0x18002813d  mov     [rsp+68h], rax
0x180028142  lea     rax, [rbp+3Fh+var_80]
0x180028146  mov     [rsp+0F0h+var_90], rax
0x18002814b  lea     rax, [rbp+3Fh+var_70]
0x18002814f  mov     [rsp+0F0h+var_98], rax
0x180028154  lea     rax, [rbp+3Fh+var_68]
0x180028158  mov     [rsp+0F0h+var_A0], rax
0x18002815d  lea     rax, [rbp+3Fh+var_60]
0x180028161  mov     [rsp+0F0h+var_A8], rax
0x180028166  lea     rax, [rbp+3Fh+var_58]
0x18002816a  mov     [rsp+0F0h+var_B0], rax
0x18002816f  lea     rax, [rbp+3Fh+var_50]
0x180028173  mov     [rsp+0F0h+var_B8], rax
0x180028178  lea     rax, [rbp+3Fh+arg_10]
0x18002817c  mov     [rsp+0F0h+var_C0], rax
0x180028181  lea     rax, [rbp+3Fh+var_48]
0x180028185  mov     [rsp+0F0h+var_C8], rax
0x18002818a  lea     rax, [rbp+3Fh+UnbiasedTime]
0x18002818e  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180028193  mov     [rbp+3Fh+var_78], 1000000h
0x18002819b  mov     [rbp+3Fh+var_80], rbx
0x18002819f  mov     [rbp+3Fh+var_70], rsi
0x1800281a3  mov     [rbp+3Fh+var_68], r15
0x1800281a7  mov     [rbp+3Fh+var_60], r12
0x1800281ab  mov     [rbp+3Fh+var_58], r13
0x1800281af  mov     [rbp+3Fh+arg_10], edi
0x1800281b2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@U2@U2@U?$_tlgWrapperByVal@$07@@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@344AEBU?$_tlgWrapperByVal@$07@@5555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800281b7  mov     r9, r14
0x1800281ba  mov     r8, rbx
0x1800281bd  mov     rdx, rsi
0x1800281c0  mov     ecx, edi
0x1800281c2  call    ?SetDatabaseCorruptionLastReported@Globals@StateRepository@@YAJW4Partition@2@_K11@Z; StateRepository::Globals::SetDatabaseCorruptionLastReported(StateRepository::Partition,unsigned __int64,unsigned __int64,unsigned __int64)
0x1800281c7  test    eax, eax
0x1800281c9  jns     short loc_1800281E3
0x1800281cb  mov     rcx, [rbp+47h]; this
0x1800281cf  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800281d6  mov     r9d, eax; char *
0x1800281d9  mov     edx, 267h; void *
0x1800281de  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800281e3  xor     eax, eax
0x1800281e5  add     rsp, 0B8h
0x1800281ec  pop     r15
0x1800281ee  pop     r14
0x1800281f0  pop     r13
0x1800281f2  pop     r12
0x1800281f4  pop     rdi
0x1800281f5  pop     rsi
0x1800281f6  pop     rbx
0x1800281f7  pop     rbp
0x1800281f8  retn
```
