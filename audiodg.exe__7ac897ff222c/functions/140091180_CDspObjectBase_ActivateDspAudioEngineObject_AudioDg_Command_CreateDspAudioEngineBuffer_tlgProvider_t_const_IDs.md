# CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspAudioEngineBuffer>(_tlgProvider_t const *,IDspAudioEngine *,uint,AudioDg_Command_CreateDspAudioEngineBuffer *)

- ea: `0x140091180`
- end: `0x140091367`
- name: `??$ActivateDspAudioEngineObject@UAudioDg_Command_CreateDspAudioEngineBuffer@@@CDspObjectBase@@QEAAJPEBU_tlgProvider_t@@PEAUIDspAudioEngine@@IPEAUAudioDg_Command_CreateDspAudioEngineBuffer@@@Z`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140091f00`

## callees

- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14004f178`
- `0x140091180`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140091260`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140091260`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400912e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400912e8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400912f3`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400912f3`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspAudioEngineBuffer>(
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
LABEL_20:
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
  v10[4] = 168;
  v10[7] = a4;
  v11 = (_DWORD *)a1[2];
  if ( *v11 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v11) )
  {
    v31 = v10[6];
    v29[0] = *v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned int)byte_1400D2951,
      v12,
      v13,
      (__int64)v29,
      (__int64)&v31);
  }
  if ( (*(int (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, v10, 168) < 0 )
  {
    v15 = (_DWORD *)a1[2];
    if ( *v15 > 2u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v14) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v17 = *v9;
      v31 = CurrentProcessId;
      v29[0] = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v17 + 24LL))(v17, v10, 168);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v15,
        (unsigned int)word_1400D291A,
        v18,
        v19,
        (__int64)v29,
        (__int64)&v31);
    }
    v20 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, v10, 168);
    v21 = *v9;
    v22 = (v20 & 0x1FFF0000) == 458752;
    v23 = *(unsigned __int16 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL);
    if ( v22 )
      v24 = v23(v21, v10, 168);
    else
      v24 = ((__int64 (__fastcall *)(__int64, _DWORD *, __int64))v23)(v21, v10, 168);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v24);
  }
  if ( *v10 != 4 || v10[6] != 2 )
  {
    v7 = -2147024809;
    v8 = 73;
    goto LABEL_20;
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
0x140091180  mov     [rsp+arg_8], rbx
0x140091185  mov     [rsp+arg_10], rbp
0x14009118a  push    rsi
0x14009118b  push    rdi
0x14009118c  push    r14
0x14009118e  sub     rsp, 40h
0x140091192  cmp     qword ptr [rcx+28h], 0
0x140091197  mov     edi, r9d
0x14009119a  mov     rsi, rcx
0x14009119d  jz      short loc_1400911AE
0x14009119f  mov     ebx, 8000FFFFh
0x1400911a4  mov     edx, 38h ; '8'
0x1400911a9  jmp     loc_14009133E
0x1400911ae  mov     [rcx+10h], rdx
0x1400911b2  lea     r14, [rcx+20h]
0x1400911b6  mov     rcx, r14
0x1400911b9  mov     rdx, r8
0x1400911bc  call    ??4?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIUnknown@@@Z; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(IUnknown *)
0x1400911c1  mov     rbx, [rsp+58h+arg_20]
0x1400911c9  mov     ebp, 0A8h
0x1400911ce  mov     dword ptr [rbx], 4
0x1400911d4  mov     [rbx+10h], ebp
0x1400911d7  mov     [rbx+1Ch], edi
0x1400911da  mov     r8, [rsi+10h]
0x1400911de  mov     eax, [r8]
0x1400911e1  cmp     eax, 5
0x1400911e4  jbe     short loc_140091227
0x1400911e6  mov     edx, 100000h
0x1400911eb  mov     rcx, r8
0x1400911ee  call    _tlgKeywordOn
0x1400911f3  test    al, al
0x1400911f5  jz      short loc_140091227
0x1400911f7  mov     eax, [rbx+18h]
0x1400911fa  lea     rdx, byte_1400D2951
0x140091201  mov     [rsp+58h+arg_0], eax
0x140091205  mov     rcx, r8
0x140091208  mov     eax, [rbx]
0x14009120a  mov     [rsp+58h+var_28], eax
0x14009120e  lea     rax, [rsp+58h+arg_0]
0x140091213  mov     [rsp+58h+var_30], rax
0x140091218  lea     rax, [rsp+58h+var_28]
0x14009121d  mov     qword ptr [rsp+58h+var_38], rax
0x140091222  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140091227  mov     rcx, [r14]
0x14009122a  mov     r8, rbp
0x14009122d  mov     rdx, rbx
0x140091230  mov     rax, [rcx]
0x140091233  mov     rax, [rax+18h]
0x140091237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009123c  test    eax, eax
0x14009123e  jns     loc_1400912F9
0x140091244  mov     rdi, [rsi+10h]
0x140091248  mov     eax, [rdi]
0x14009124a  cmp     eax, 2
0x14009124d  jbe     short loc_1400912A6
0x14009124f  mov     edx, 100000h
0x140091254  mov     rcx, rdi
0x140091257  call    _tlgKeywordOn
0x14009125c  test    al, al
0x14009125e  jz      short loc_1400912A6
0x140091260  call    cs:__imp_GetCurrentProcessId
0x140091266  mov     rcx, [r14]
0x140091269  mov     r8, rbp
0x14009126c  mov     [rsp+58h+arg_0], eax
0x140091270  mov     rdx, rbx
0x140091273  mov     rax, [rcx]
0x140091276  mov     rax, [rax+18h]
0x14009127a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009127f  mov     [rsp+58h+var_28], eax
0x140091283  lea     rdx, word_1400D291A
0x14009128a  lea     rax, [rsp+58h+arg_0]
0x14009128f  mov     rcx, rdi
0x140091292  mov     [rsp+58h+var_30], rax
0x140091297  lea     rax, [rsp+58h+var_28]
0x14009129c  mov     qword ptr [rsp+58h+var_38], rax; int
0x1400912a1  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400912a6  mov     rcx, [r14]
0x1400912a9  mov     r8, rbp
0x1400912ac  mov     rdx, rbx
0x1400912af  mov     rax, [rcx]
0x1400912b2  mov     rax, [rax+18h]
0x1400912b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400912bb  mov     rcx, [r14]
0x1400912be  and     eax, 1FFF0000h
0x1400912c3  cmp     eax, 70000h
0x1400912c8  mov     r8, rbp
0x1400912cb  mov     rdx, rbx
0x1400912ce  mov     r9, [rcx]
0x1400912d1  mov     rax, [r9+18h]
0x1400912d5  jnz     short loc_1400912E1
0x1400912d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400912dc  movzx   edi, ax
0x1400912df  jmp     short loc_1400912E8
0x1400912e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400912e6  mov     edi, eax
0x1400912e8  call    cs:__imp_GetCurrentProcess
0x1400912ee  mov     rcx, rax; hProcess
0x1400912f1  mov     edx, edi; uExitCode
0x1400912f3  call    cs:__imp_TerminateProcess
0x1400912f9  cmp     dword ptr [rbx], 4
0x1400912fc  jnz     short loc_140091334
0x1400912fe  cmp     dword ptr [rbx+18h], 2
0x140091302  jnz     short loc_140091334
0x140091304  mov     edi, [rbx+4]
0x140091307  test    edi, edi
0x140091309  jns     short loc_140091328
0x14009130b  mov     rcx, [rsp+58h]; this
0x140091310  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140091317  mov     r9d, edi; char *
0x14009131a  mov     edx, 4Ah ; 'J'; void *
0x14009131f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140091324  mov     eax, edi
0x140091326  jmp     short loc_140091354
0x140091328  mov     rax, [rbx+8]
0x14009132c  mov     [rsi+28h], rax
0x140091330  xor     eax, eax
0x140091332  jmp     short loc_140091354
0x140091334  mov     ebx, 80070057h
0x140091339  mov     edx, 49h ; 'I'; void *
0x14009133e  mov     rcx, [rsp+58h]; this
0x140091343  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14009134a  mov     r9d, ebx; char *
0x14009134d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140091352  mov     eax, ebx
0x140091354  mov     rbx, [rsp+58h+arg_8]
0x140091359  mov     rbp, [rsp+58h+arg_10]
0x14009135e  add     rsp, 40h
0x140091362  pop     r14
0x140091364  pop     rdi
0x140091365  pop     rsi
0x140091366  retn
```
