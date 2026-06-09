# CTSSyncWaitResult::WaitForCompletion(TSWaitType,ITSThread *)

- ea: `0x1800192f0`
- end: `0x18001954c`
- name: `?WaitForCompletion@CTSSyncWaitResult@@QEAAJW4TSWaitType@@PEAVITSThread@@@Z`
- size: `604`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001719c`

## callees

- `0x180001180`
- `0x180001364`
- `0x1800013f4`
- `0x18000c3d0`
- `0x1800192f0`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019318`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800194aa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019318`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800194aa`

## string_xrefs

- `0x1800193bd`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x180019442`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x180019500`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x1800193a4`: `WaitForCompletion`
- `0x180019429`: `WaitForCompletion`
- `0x1800194e7`: `WaitForCompletion`
- `0x1800193cd`: `ThreadWaitForSingleObject timed out`
- `0x180019452`: `ThreadWaitForSingleObject failed with 0x%x`

## pseudocode

```c
__int64 __fastcall CTSSyncWaitResult::WaitForCompletion(__int64 a1, unsigned int a2, __int64 a3)
{
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  int v9; // ebx
  int v11; // r8d
  int v12; // r9d
  int *v13; // rdx
  const char **v14; // rax
  DWORD v15; // eax
  const char **v16; // [rsp+30h] [rbp-50h]
  const char **v17; // [rsp+40h] [rbp-40h]
  const char *v18; // [rsp+50h] [rbp-30h] BYREF
  const char *v19; // [rsp+58h] [rbp-28h] BYREF
  const char *v20; // [rsp+60h] [rbp-20h] BYREF
  const char *v21; // [rsp+68h] [rbp-18h] BYREF
  __int64 v22; // [rsp+70h] [rbp-10h] BYREF
  const char *v23; // [rsp+A0h] [rbp+20h] BYREF
  int v24; // [rsp+B8h] [rbp+38h] BYREF

  v22 = 0;
  if ( !WaitForSingleObject(*(HANDLE *)(a1 + 88), 0) )
  {
    if ( (unsigned int)dword_1800EB958 > 5 )
    {
      v23 = "Event signaled, no need to wait";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v6,
        (unsigned int)word_1800CCE82,
        v7,
        v8,
        (__int64)&v23);
    }
    goto LABEL_4;
  }
  if ( a2 != 4 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)a3 + 72LL))(
           a3,
           *(_QWORD *)(a1 + 88),
           a2,
           0xFFFFFFFFLL);
    if ( v9 == -2092630012 )
    {
      if ( (unsigned int)dword_1800EB958 > 2 )
      {
        LODWORD(v23) = 268;
        v18 = "WaitForCompletion";
        v19 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
        v20 = "ThreadWaitForSingleObject timed out";
        v24 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          -2147467259,
          (unsigned int)byte_1800CCE3D,
          v11,
          v12,
          (__int64)&v20,
          (__int64)&v24,
          (__int64)&v19,
          (__int64)&v23,
          (__int64)&v18);
      }
      goto LABEL_5;
    }
    if ( v9 < 0 )
    {
      if ( (unsigned int)dword_1800EB958 <= 2 )
        goto LABEL_5;
      v24 = 272;
      v20 = "WaitForCompletion";
      v13 = &dword_1800CCDF4;
      v19 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
      v21 = "ThreadWaitForSingleObject failed with 0x%x";
      v17 = &v20;
      v16 = &v19;
      v14 = &v21;
LABEL_13:
      LODWORD(v18) = -2147467259;
      LODWORD(v23) = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        -2147467259,
        (_DWORD)v13,
        v11,
        v12,
        (__int64)v14,
        (__int64)&v18,
        (__int64)v16,
        (__int64)&v24,
        (__int64)v17,
        (__int64)&v23);
      goto LABEL_5;
    }
LABEL_4:
    v9 = 0;
    goto LABEL_5;
  }
  v15 = WaitForSingleObject(*(HANDLE *)(a1 + 88), 0xFFFFFFFF);
  if ( !v15 )
    goto LABEL_4;
  if ( v15 == 128 )
  {
    v9 = -2092629814;
  }
  else
  {
    v9 = -2092629813;
    if ( v15 != 258 )
      v9 = -2147467259;
  }
  if ( (unsigned int)dword_1800EB958 > 2 )
  {
    v24 = 287;
    v21 = "WaitForCompletion";
    v13 = (int *)byte_1800CCDAB;
    v20 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
    v19 = "PAL_System_SingleCondWait failed with 0x%x";
    v17 = &v21;
    v16 = &v20;
    v14 = &v19;
    goto LABEL_13;
  }
LABEL_5:
  TCntPtr<ITSThread>::SafeRelease(&v22);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800192f0  mov     [rsp-18h+arg_8], rbx
0x1800192f5  push    rbp
0x1800192f6  push    rsi
0x1800192f7  push    rdi
0x1800192f8  mov     rbp, rsp
0x1800192fb  sub     rsp, 80h
0x180019302  mov     rsi, r8
0x180019305  mov     [rbp+var_10], 0
0x18001930d  mov     edi, edx
0x18001930f  mov     rbx, rcx
0x180019312  mov     rcx, [rcx+58h]; hHandle
0x180019316  xor     edx, edx; dwMilliseconds
0x180019318  call    cs:__imp_WaitForSingleObject
0x18001931e  test    eax, eax
0x180019320  jnz     short loc_18001936D
0x180019322  mov     eax, cs:dword_1800EB958
0x180019328  cmp     eax, 5
0x18001932b  jbe     short loc_18001934D
0x18001932d  lea     rax, aEventSignaledN; "Event signaled, no need to wait"
0x180019334  mov     [rbp+arg_0], rax
0x180019338  lea     rdx, word_1800CCE82
0x18001933f  lea     rax, [rbp+arg_0]
0x180019343  mov     [rsp+80h+var_60], rax
0x180019348  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18001934d  xor     ebx, ebx
0x18001934f  lea     rcx, [rbp+var_10]
0x180019353  call    ?SafeRelease@?$TCntPtr@VITSThread@@@@AEAAXXZ; TCntPtr<ITSThread>::SafeRelease(void)
0x180019358  mov     eax, ebx
0x18001935a  mov     rbx, [rsp+80h+arg_8]
0x180019362  add     rsp, 80h
0x180019369  pop     rdi
0x18001936a  pop     rsi
0x18001936b  pop     rbp
0x18001936c  retn
0x18001936d  cmp     edi, 4
0x180019370  jz      loc_1800194A3
0x180019376  mov     rax, [rsi]
0x180019379  or      r9d, 0FFFFFFFFh
0x18001937d  mov     rdx, [rbx+58h]
0x180019381  mov     r8d, edi
0x180019384  mov     rcx, rsi
0x180019387  mov     rax, [rax+48h]
0x18001938b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019390  mov     ebx, eax
0x180019392  cmp     eax, 83450004h
0x180019397  jnz     short loc_180019412
0x180019399  mov     ecx, cs:dword_1800EB958
0x18001939f  cmp     ecx, 2
0x1800193a2  jbe     short loc_18001934F
0x1800193a4  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x1800193ab  mov     dword ptr [rbp+arg_0], 10Ch
0x1800193b2  mov     [rbp+var_30], rax
0x1800193b6  lea     rdx, byte_1800CCE3D
0x1800193bd  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800193c4  mov     ecx, 80004005h
0x1800193c9  mov     [rbp+var_28], rax
0x1800193cd  lea     rax, aThreadwaitfors_0; "ThreadWaitForSingleObject timed out"
0x1800193d4  mov     [rbp+var_20], rax
0x1800193d8  lea     rax, [rbp+var_30]
0x1800193dc  mov     [rsp+80h+var_40], rax
0x1800193e1  lea     rax, [rbp+arg_0]
0x1800193e5  mov     [rsp+80h+var_48], rax
0x1800193ea  lea     rax, [rbp+var_28]
0x1800193ee  mov     [rsp+80h+var_50], rax
0x1800193f3  lea     rax, [rbp+arg_18]
0x1800193f7  mov     [rsp+80h+var_58], rax
0x1800193fc  lea     rax, [rbp+var_20]
0x180019400  mov     [rsp+80h+var_60], rax
0x180019405  mov     [rbp+arg_18], ecx
0x180019408  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001940d  jmp     loc_18001934F
0x180019412  test    ebx, ebx
0x180019414  jns     loc_18001934D
0x18001941a  mov     eax, cs:dword_1800EB958
0x180019420  cmp     eax, 2
0x180019423  jbe     loc_18001934F
0x180019429  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x180019430  mov     [rbp+arg_18], 110h
0x180019437  mov     [rbp+var_20], rax
0x18001943b  lea     rdx, dword_1800CCDF4
0x180019442  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180019449  mov     ecx, 80004005h
0x18001944e  mov     [rbp+var_28], rax
0x180019452  lea     rax, aThreadwaitfors; "ThreadWaitForSingleObject failed with 0"...
0x180019459  mov     [rbp+var_18], rax
0x18001945d  lea     rax, [rbp+arg_0]
0x180019461  mov     [rsp+80h+var_38], rax
0x180019466  lea     rax, [rbp+var_20]
0x18001946a  mov     [rsp+80h+var_40], rax
0x18001946f  lea     rax, [rbp+arg_18]
0x180019473  mov     [rsp+80h+var_48], rax
0x180019478  lea     rax, [rbp+var_28]
0x18001947c  mov     [rsp+80h+var_50], rax
0x180019481  lea     rax, [rbp+var_30]
0x180019485  mov     [rsp+80h+var_58], rax
0x18001948a  lea     rax, [rbp+var_18]
0x18001948e  mov     [rsp+80h+var_60], rax
0x180019493  mov     dword ptr [rbp+var_30], ecx
0x180019496  mov     dword ptr [rbp+arg_0], ebx
0x180019499  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001949e  jmp     loc_18001934F
0x1800194a3  mov     rcx, [rbx+58h]; hHandle
0x1800194a7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800194aa  call    cs:__imp_WaitForSingleObject
0x1800194b0  test    eax, eax
0x1800194b2  jz      loc_18001934D
0x1800194b8  mov     ecx, 80004005h
0x1800194bd  cmp     eax, 80h
0x1800194c2  jz      short loc_1800194D3
0x1800194c4  cmp     eax, 102h
0x1800194c9  mov     ebx, 834500CBh
0x1800194ce  cmovnz  ebx, ecx
0x1800194d1  jmp     short loc_1800194D8
0x1800194d3  mov     ebx, 834500CAh
0x1800194d8  mov     eax, cs:dword_1800EB958
0x1800194de  cmp     eax, 2
0x1800194e1  jbe     loc_18001934F
0x1800194e7  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x1800194ee  mov     [rbp+arg_18], 11Fh
0x1800194f5  mov     [rbp+var_18], rax
0x1800194f9  lea     rdx, byte_1800CCDAB
0x180019500  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180019507  mov     [rbp+var_20], rax
0x18001950b  lea     rax, aPalSystemSingl; "PAL_System_SingleCondWait failed with 0"...
0x180019512  mov     [rbp+var_28], rax
0x180019516  lea     rax, [rbp+arg_0]
0x18001951a  mov     [rsp+80h+var_38], rax
0x18001951f  lea     rax, [rbp+var_18]
0x180019523  mov     [rsp+80h+var_40], rax
0x180019528  lea     rax, [rbp+arg_18]
0x18001952c  mov     [rsp+80h+var_48], rax
0x180019531  lea     rax, [rbp+var_20]
0x180019535  mov     [rsp+80h+var_50], rax
0x18001953a  lea     rax, [rbp+var_30]
0x18001953e  mov     [rsp+80h+var_58], rax
0x180019543  lea     rax, [rbp+var_28]
0x180019547  jmp     loc_18001948E
```
