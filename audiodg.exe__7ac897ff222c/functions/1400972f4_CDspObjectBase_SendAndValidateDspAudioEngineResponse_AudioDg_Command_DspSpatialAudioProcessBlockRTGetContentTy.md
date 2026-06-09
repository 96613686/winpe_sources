# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspSpatialAudioProcessBlockRTGetContentType>(AudioDg_Command_DspSpatialAudioProcessBlockRTGetContentType *)

- ea: `0x1400972f4`
- end: `0x14009746d`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspSpatialAudioProcessBlockRTGetContentType@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspSpatialAudioProcessBlockRTGetContentType@@@Z`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140098110`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x1400972f4`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009738e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009738e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140097419`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140097419`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140097424`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140097424`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspSpatialAudioProcessBlockRTGetContentType>(
        _QWORD *a1,
        __int64 a2)
{
  _DWORD *v4; // r8
  int v5; // r8d
  int v6; // r9d
  __int64 v7; // r8
  _DWORD *v8; // rsi
  DWORD CurrentProcessId; // eax
  __int64 v10; // rcx
  int v11; // r8d
  int v12; // r9d
  int v13; // eax
  __int64 v14; // rcx
  bool v15; // zf
  unsigned __int16 (__fastcall *v16)(__int64, __int64, __int64); // rax
  UINT v17; // edi
  HANDLE CurrentProcess; // rax
  int v19; // ebx
  __int64 v20; // rdx
  int v22; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD v24; // [rsp+50h] [rbp+8h] BYREF
  int v25; // [rsp+58h] [rbp+10h] BYREF

  *(_DWORD *)a2 = 28;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 28;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)word_1400D2F6A,
      v5,
      v6,
      (__int64)&v24);
  }
  if ( (*(int (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[4] + 24LL))(a1[4], a2, 28) < 0 )
  {
    v8 = (_DWORD *)a1[2];
    if ( *v8 > 2u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v7) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v10 = a1[4];
      v24 = CurrentProcessId;
      v25 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v10 + 24LL))(v10, a2, 28);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v8,
        (unsigned int)&byte_1400D308F,
        v11,
        v12,
        (__int64)&v25,
        (__int64)&v24);
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[4] + 24LL))(a1[4], a2, 28);
    v14 = a1[4];
    v15 = (v13 & 0x1FFF0000) == 458752;
    v16 = *(unsigned __int16 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v14 + 24LL);
    if ( v15 )
      v17 = v16(v14, a2, 28);
    else
      v17 = ((__int64 (__fastcall *)(__int64, __int64, __int64))v16)(v14, a2, 28);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v17);
  }
  if ( *(_DWORD *)a2 != 28 )
  {
    v19 = -2147024809;
    v20 = 100;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\DspObjectBase.h",
      (const char *)(unsigned int)v19,
      v22);
    return (unsigned int)v19;
  }
  v19 = *(_DWORD *)(a2 + 4);
  if ( v19 < 0 )
  {
    v20 = 101;
    goto LABEL_14;
  }
  return 0;
}

```

## disassembly

```asm
0x1400972f4  mov     [rsp+arg_10], rbx
0x1400972f9  push    rbp
0x1400972fa  push    rsi
0x1400972fb  push    rdi
0x1400972fc  sub     rsp, 30h
0x140097300  mov     ebp, 1Ch
0x140097305  mov     rbx, rdx
0x140097308  mov     [rdx], ebp
0x14009730a  mov     rdi, rcx
0x14009730d  mov     rax, [rcx+28h]
0x140097311  mov     [rdx+8], rax
0x140097315  mov     [rdx+10h], ebp
0x140097318  mov     r8, [rcx+10h]
0x14009731c  mov     eax, [r8]
0x14009731f  cmp     eax, 5
0x140097322  jbe     short loc_140097354
0x140097324  mov     edx, 100000h
0x140097329  mov     rcx, r8
0x14009732c  call    _tlgKeywordOn
0x140097331  test    al, al
0x140097333  jz      short loc_140097354
0x140097335  mov     eax, [rbx]
0x140097337  lea     rdx, word_1400D2F6A
0x14009733e  mov     [rsp+48h+arg_0], eax
0x140097342  mov     rcx, r8
0x140097345  lea     rax, [rsp+48h+arg_0]
0x14009734a  mov     qword ptr [rsp+48h+var_28], rax
0x14009734f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140097354  mov     rcx, [rdi+20h]
0x140097358  mov     r8, rbp
0x14009735b  mov     rdx, rbx
0x14009735e  mov     rax, [rcx]
0x140097361  mov     rax, [rax+18h]
0x140097365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009736a  test    eax, eax
0x14009736c  jns     loc_14009742A
0x140097372  mov     rsi, [rdi+10h]
0x140097376  mov     eax, [rsi]
0x140097378  cmp     eax, 2
0x14009737b  jbe     short loc_1400973D5
0x14009737d  mov     edx, 100000h
0x140097382  mov     rcx, rsi
0x140097385  call    _tlgKeywordOn
0x14009738a  test    al, al
0x14009738c  jz      short loc_1400973D5
0x14009738e  call    cs:__imp_GetCurrentProcessId
0x140097394  mov     rcx, [rdi+20h]
0x140097398  mov     r8, rbp
0x14009739b  mov     [rsp+48h+arg_0], eax
0x14009739f  mov     rdx, rbx
0x1400973a2  mov     rax, [rcx]
0x1400973a5  mov     rax, [rax+18h]
0x1400973a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400973ae  mov     [rsp+48h+arg_8], eax
0x1400973b2  lea     rdx, byte_1400D308F
0x1400973b9  lea     rax, [rsp+48h+arg_0]
0x1400973be  mov     rcx, rsi
0x1400973c1  mov     [rsp+48h+var_20], rax
0x1400973c6  lea     rax, [rsp+48h+arg_8]
0x1400973cb  mov     qword ptr [rsp+48h+var_28], rax; int
0x1400973d0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400973d5  mov     rcx, [rdi+20h]
0x1400973d9  mov     r8, rbp
0x1400973dc  mov     rdx, rbx
0x1400973df  mov     rax, [rcx]
0x1400973e2  mov     rax, [rax+18h]
0x1400973e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400973eb  mov     rcx, [rdi+20h]
0x1400973ef  and     eax, 1FFF0000h
0x1400973f4  cmp     eax, 70000h
0x1400973f9  mov     r8, rbp
0x1400973fc  mov     rdx, rbx
0x1400973ff  mov     r9, [rcx]
0x140097402  mov     rax, [r9+18h]
0x140097406  jnz     short loc_140097412
0x140097408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009740d  movzx   edi, ax
0x140097410  jmp     short loc_140097419
0x140097412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097417  mov     edi, eax
0x140097419  call    cs:__imp_GetCurrentProcess
0x14009741f  mov     rcx, rax; hProcess
0x140097422  mov     edx, edi; uExitCode
0x140097424  call    cs:__imp_TerminateProcess
0x14009742a  cmp     [rbx], ebp
0x14009742c  jz      short loc_140097450
0x14009742e  mov     ebx, 80070057h
0x140097433  mov     edx, 64h ; 'd'; void *
0x140097438  mov     rcx, [rsp+48h]; this
0x14009743d  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140097444  mov     r9d, ebx; char *
0x140097447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009744c  mov     eax, ebx
0x14009744e  jmp     short loc_140097460
0x140097450  mov     ebx, [rbx+4]
0x140097453  test    ebx, ebx
0x140097455  jns     short loc_14009745E
0x140097457  mov     edx, 65h ; 'e'
0x14009745c  jmp     short loc_140097438
0x14009745e  xor     eax, eax
0x140097460  mov     rbx, [rsp+48h+arg_10]
0x140097465  add     rsp, 30h
0x140097469  pop     rdi
0x14009746a  pop     rsi
0x14009746b  pop     rbp
0x14009746c  retn
```
