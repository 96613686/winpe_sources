# CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspAudioEngineAudioOutputEndpoint>(_tlgProvider_t const *,IDspAudioEngine *,uint,AudioDg_Command_CreateDspAudioEngineAudioOutputEndpoint *)

- ea: `0x140094774`
- end: `0x140094962`
- name: `??$ActivateDspAudioEngineObject@UAudioDg_Command_CreateDspAudioEngineAudioOutputEndpoint@@@CDspObjectBase@@QEAAJPEBU_tlgProvider_t@@PEAUIDspAudioEngine@@IPEAUAudioDg_Command_CreateDspAudioEngineAudioOutputEndpoint@@@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140095ddc`

## callees

- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14004f178`
- `0x140094774`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140094854`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140094854`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400948dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400948dc`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400948e7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400948e7`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspAudioEngineAudioOutputEndpoint>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        _DWORD *a5)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  _QWORD *v9; // r14
  _DWORD *v10; // rbx
  _DWORD *v11; // r8
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // r8
  _DWORD *v15; // rdi
  DWORD CurrentProcessId; // eax
  __int64 v17; // rcx
  int v18; // r8d
  int v19; // r9d
  int v20; // eax
  __int64 v21; // rcx
  bool v22; // zf
  unsigned __int16 (__fastcall *v23)(__int64, _DWORD *, __int64); // rax
  UINT v24; // edi
  HANDLE CurrentProcess; // rax
  int v26; // edi
  int v28; // [rsp+20h] [rbp-38h]
  int v29[10]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD v31; // [rsp+60h] [rbp+8h] BYREF

  if ( a1[5] )
  {
    v7 = -2147418113;
    v8 = 56;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\DspObjectBase.h",
      (const char *)v7,
      v28);
    return v7;
  }
  a1[2] = a2;
  v9 = a1 + 4;
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(a1 + 4, a3);
  v10 = a5;
  *a5 = 4;
  v10[4] = 248;
  v10[7] = a4;
  v11 = (_DWORD *)a1[2];
  if ( *v11 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v11) )
  {
    v31 = v10[6];
    v29[0] = *v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned int)byte_1400D2D59,
      v12,
      v13,
      (__int64)v29,
      (__int64)&v31);
  }
  if ( (*(int (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, v10, 248) < 0 )
  {
    v15 = (_DWORD *)a1[2];
    if ( *v15 > 2u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v14) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v17 = *v9;
      v31 = CurrentProcessId;
      v29[0] = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v17 + 24LL))(v17, v10, 248);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v15,
        (unsigned int)word_1400D2D22,
        v18,
        v19,
        (__int64)v29,
        (__int64)&v31);
    }
    v20 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, v10, 248);
    v21 = *v9;
    v22 = (v20 & 0x1FFF0000) == 458752;
    v23 = *(unsigned __int16 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL);
    if ( v22 )
      v24 = v23(v21, v10, 248);
    else
      v24 = ((__int64 (__fastcall *)(__int64, _DWORD *, __int64))v23)(v21, v10, 248);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v24);
  }
  if ( *v10 != 4 || v10[6] != 3 || *((_WORD *)v10 + 24) > 0x6Eu )
  {
    v7 = -2147024809;
    v8 = 73;
    goto LABEL_21;
  }
  v26 = v10[1];
  if ( v26 >= 0 )
  {
    a1[5] = *((_QWORD *)v10 + 1);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\DspObjectBase.h",
      (const char *)(unsigned int)v26,
      v28);
    return (unsigned int)v26;
  }
}

```

## disassembly

```asm
0x140094774  mov     [rsp+arg_8], rbx
0x140094779  mov     [rsp+arg_10], rbp
0x14009477e  push    rsi
0x14009477f  push    rdi
0x140094780  push    r14
0x140094782  sub     rsp, 40h
0x140094786  cmp     qword ptr [rcx+28h], 0
0x14009478b  mov     edi, r9d
0x14009478e  mov     rsi, rcx
0x140094791  jz      short loc_1400947A2
0x140094793  mov     ebx, 8000FFFFh
0x140094798  mov     edx, 38h ; '8'
0x14009479d  jmp     loc_140094939
0x1400947a2  mov     [rcx+10h], rdx
0x1400947a6  lea     r14, [rcx+20h]
0x1400947aa  mov     rcx, r14
0x1400947ad  mov     rdx, r8
0x1400947b0  call    ??4?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIUnknown@@@Z; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(IUnknown *)
0x1400947b5  mov     rbx, [rsp+58h+arg_20]
0x1400947bd  mov     ebp, 0F8h
0x1400947c2  mov     dword ptr [rbx], 4
0x1400947c8  mov     [rbx+10h], ebp
0x1400947cb  mov     [rbx+1Ch], edi
0x1400947ce  mov     r8, [rsi+10h]
0x1400947d2  mov     eax, [r8]
0x1400947d5  cmp     eax, 5
0x1400947d8  jbe     short loc_14009481B
0x1400947da  mov     edx, 100000h
0x1400947df  mov     rcx, r8
0x1400947e2  call    _tlgKeywordOn
0x1400947e7  test    al, al
0x1400947e9  jz      short loc_14009481B
0x1400947eb  mov     eax, [rbx+18h]
0x1400947ee  lea     rdx, byte_1400D2D59
0x1400947f5  mov     [rsp+58h+arg_0], eax
0x1400947f9  mov     rcx, r8
0x1400947fc  mov     eax, [rbx]
0x1400947fe  mov     [rsp+58h+var_28], eax
0x140094802  lea     rax, [rsp+58h+arg_0]
0x140094807  mov     [rsp+58h+var_30], rax
0x14009480c  lea     rax, [rsp+58h+var_28]
0x140094811  mov     qword ptr [rsp+58h+var_38], rax
0x140094816  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14009481b  mov     rcx, [r14]
0x14009481e  mov     r8, rbp
0x140094821  mov     rdx, rbx
0x140094824  mov     rax, [rcx]
0x140094827  mov     rax, [rax+18h]
0x14009482b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140094830  test    eax, eax
0x140094832  jns     loc_1400948ED
0x140094838  mov     rdi, [rsi+10h]
0x14009483c  mov     eax, [rdi]
0x14009483e  cmp     eax, 2
0x140094841  jbe     short loc_14009489A
0x140094843  mov     edx, 100000h
0x140094848  mov     rcx, rdi
0x14009484b  call    _tlgKeywordOn
0x140094850  test    al, al
0x140094852  jz      short loc_14009489A
0x140094854  call    cs:__imp_GetCurrentProcessId
0x14009485a  mov     rcx, [r14]
0x14009485d  mov     r8, rbp
0x140094860  mov     [rsp+58h+arg_0], eax
0x140094864  mov     rdx, rbx
0x140094867  mov     rax, [rcx]
0x14009486a  mov     rax, [rax+18h]
0x14009486e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140094873  mov     [rsp+58h+var_28], eax
0x140094877  lea     rdx, word_1400D2D22
0x14009487e  lea     rax, [rsp+58h+arg_0]
0x140094883  mov     rcx, rdi
0x140094886  mov     [rsp+58h+var_30], rax
0x14009488b  lea     rax, [rsp+58h+var_28]
0x140094890  mov     qword ptr [rsp+58h+var_38], rax; int
0x140094895  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14009489a  mov     rcx, [r14]
0x14009489d  mov     r8, rbp
0x1400948a0  mov     rdx, rbx
0x1400948a3  mov     rax, [rcx]
0x1400948a6  mov     rax, [rax+18h]
0x1400948aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400948af  mov     rcx, [r14]
0x1400948b2  and     eax, 1FFF0000h
0x1400948b7  cmp     eax, 70000h
0x1400948bc  mov     r8, rbp
0x1400948bf  mov     rdx, rbx
0x1400948c2  mov     r9, [rcx]
0x1400948c5  mov     rax, [r9+18h]
0x1400948c9  jnz     short loc_1400948D5
0x1400948cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400948d0  movzx   edi, ax
0x1400948d3  jmp     short loc_1400948DC
0x1400948d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400948da  mov     edi, eax
0x1400948dc  call    cs:__imp_GetCurrentProcess
0x1400948e2  mov     rcx, rax; hProcess
0x1400948e5  mov     edx, edi; uExitCode
0x1400948e7  call    cs:__imp_TerminateProcess
0x1400948ed  cmp     dword ptr [rbx], 4
0x1400948f0  jnz     short loc_14009492F
0x1400948f2  cmp     dword ptr [rbx+18h], 3
0x1400948f6  jnz     short loc_14009492F
0x1400948f8  cmp     word ptr [rbx+30h], 6Eh ; 'n'
0x1400948fd  ja      short loc_14009492F
0x1400948ff  mov     edi, [rbx+4]
0x140094902  test    edi, edi
0x140094904  jns     short loc_140094923
0x140094906  mov     rcx, [rsp+58h]; this
0x14009490b  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140094912  mov     r9d, edi; char *
0x140094915  mov     edx, 4Ah ; 'J'; void *
0x14009491a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009491f  mov     eax, edi
0x140094921  jmp     short loc_14009494F
0x140094923  mov     rax, [rbx+8]
0x140094927  mov     [rsi+28h], rax
0x14009492b  xor     eax, eax
0x14009492d  jmp     short loc_14009494F
0x14009492f  mov     ebx, 80070057h
0x140094934  mov     edx, 49h ; 'I'; void *
0x140094939  mov     rcx, [rsp+58h]; this
0x14009493e  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140094945  mov     r9d, ebx; char *
0x140094948  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009494d  mov     eax, ebx
0x14009494f  mov     rbx, [rsp+58h+arg_8]
0x140094954  mov     rbp, [rsp+58h+arg_10]
0x140094959  add     rsp, 40h
0x14009495d  pop     r14
0x14009495f  pop     rdi
0x140094960  pop     rsi
0x140094961  retn
```
