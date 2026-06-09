# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspAudioPumpResume>(AudioDg_Command_DspAudioPumpResume *)

- ea: `0x14009a0b4`
- end: `0x14009a232`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspAudioPumpResume@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspAudioPumpResume@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14009a7e0`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14009a0b4`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009a152`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009a152`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009a1dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009a1dd`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009a1e8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009a1e8`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspAudioPumpResume>(
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

  *(_DWORD *)a2 = 20;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 24;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_1400D3609,
      v5,
      v6,
      (__int64)&v24);
  }
  if ( (*(int (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[4] + 24LL))(a1[4], a2, 24) < 0 )
  {
    v8 = (_DWORD *)a1[2];
    if ( *v8 > 2u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v7) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v10 = a1[4];
      v24 = CurrentProcessId;
      v25 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v10 + 24LL))(v10, a2, 24);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v8,
        (unsigned int)word_1400D35D2,
        v11,
        v12,
        (__int64)&v25,
        (__int64)&v24);
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[4] + 24LL))(a1[4], a2, 24);
    v14 = a1[4];
    v15 = (v13 & 0x1FFF0000) == 458752;
    v16 = *(unsigned __int16 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v14 + 24LL);
    if ( v15 )
      v17 = v16(v14, a2, 24);
    else
      v17 = ((__int64 (__fastcall *)(__int64, __int64, __int64))v16)(v14, a2, 24);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v17);
  }
  if ( *(_DWORD *)a2 != 20 )
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
0x14009a0b4  mov     [rsp+arg_10], rbx
0x14009a0b9  push    rbp
0x14009a0ba  push    rsi
0x14009a0bb  push    rdi
0x14009a0bc  sub     rsp, 30h
0x14009a0c0  mov     dword ptr [rdx], 14h
0x14009a0c6  mov     ebp, 18h
0x14009a0cb  mov     rax, [rcx+28h]
0x14009a0cf  mov     rbx, rdx
0x14009a0d2  mov     [rdx+8], rax
0x14009a0d6  mov     rdi, rcx
0x14009a0d9  mov     [rdx+10h], ebp
0x14009a0dc  mov     r8, [rcx+10h]
0x14009a0e0  mov     eax, [r8]
0x14009a0e3  cmp     eax, 5
0x14009a0e6  jbe     short loc_14009A118
0x14009a0e8  mov     edx, 100000h
0x14009a0ed  mov     rcx, r8
0x14009a0f0  call    _tlgKeywordOn
0x14009a0f5  test    al, al
0x14009a0f7  jz      short loc_14009A118
0x14009a0f9  mov     eax, [rbx]
0x14009a0fb  lea     rdx, byte_1400D3609
0x14009a102  mov     [rsp+48h+arg_0], eax
0x14009a106  mov     rcx, r8
0x14009a109  lea     rax, [rsp+48h+arg_0]
0x14009a10e  mov     qword ptr [rsp+48h+var_28], rax
0x14009a113  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x14009a118  mov     rcx, [rdi+20h]
0x14009a11c  mov     r8, rbp
0x14009a11f  mov     rdx, rbx
0x14009a122  mov     rax, [rcx]
0x14009a125  mov     rax, [rax+18h]
0x14009a129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a12e  test    eax, eax
0x14009a130  jns     loc_14009A1EE
0x14009a136  mov     rsi, [rdi+10h]
0x14009a13a  mov     eax, [rsi]
0x14009a13c  cmp     eax, 2
0x14009a13f  jbe     short loc_14009A199
0x14009a141  mov     edx, 100000h
0x14009a146  mov     rcx, rsi
0x14009a149  call    _tlgKeywordOn
0x14009a14e  test    al, al
0x14009a150  jz      short loc_14009A199
0x14009a152  call    cs:__imp_GetCurrentProcessId
0x14009a158  mov     rcx, [rdi+20h]
0x14009a15c  mov     r8, rbp
0x14009a15f  mov     [rsp+48h+arg_0], eax
0x14009a163  mov     rdx, rbx
0x14009a166  mov     rax, [rcx]
0x14009a169  mov     rax, [rax+18h]
0x14009a16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a172  mov     [rsp+48h+arg_8], eax
0x14009a176  lea     rdx, word_1400D35D2
0x14009a17d  lea     rax, [rsp+48h+arg_0]
0x14009a182  mov     rcx, rsi
0x14009a185  mov     [rsp+48h+var_20], rax
0x14009a18a  lea     rax, [rsp+48h+arg_8]
0x14009a18f  mov     qword ptr [rsp+48h+var_28], rax; int
0x14009a194  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14009a199  mov     rcx, [rdi+20h]
0x14009a19d  mov     r8, rbp
0x14009a1a0  mov     rdx, rbx
0x14009a1a3  mov     rax, [rcx]
0x14009a1a6  mov     rax, [rax+18h]
0x14009a1aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a1af  mov     rcx, [rdi+20h]
0x14009a1b3  and     eax, 1FFF0000h
0x14009a1b8  cmp     eax, 70000h
0x14009a1bd  mov     r8, rbp
0x14009a1c0  mov     rdx, rbx
0x14009a1c3  mov     r9, [rcx]
0x14009a1c6  mov     rax, [r9+18h]
0x14009a1ca  jnz     short loc_14009A1D6
0x14009a1cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a1d1  movzx   edi, ax
0x14009a1d4  jmp     short loc_14009A1DD
0x14009a1d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a1db  mov     edi, eax
0x14009a1dd  call    cs:__imp_GetCurrentProcess
0x14009a1e3  mov     rcx, rax; hProcess
0x14009a1e6  mov     edx, edi; uExitCode
0x14009a1e8  call    cs:__imp_TerminateProcess
0x14009a1ee  cmp     dword ptr [rbx], 14h
0x14009a1f1  jz      short loc_14009A215
0x14009a1f3  mov     ebx, 80070057h
0x14009a1f8  mov     edx, 64h ; 'd'; void *
0x14009a1fd  mov     rcx, [rsp+48h]; this
0x14009a202  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14009a209  mov     r9d, ebx; char *
0x14009a20c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009a211  mov     eax, ebx
0x14009a213  jmp     short loc_14009A225
0x14009a215  mov     ebx, [rbx+4]
0x14009a218  test    ebx, ebx
0x14009a21a  jns     short loc_14009A223
0x14009a21c  mov     edx, 65h ; 'e'
0x14009a221  jmp     short loc_14009A1FD
0x14009a223  xor     eax, eax
0x14009a225  mov     rbx, [rsp+48h+arg_10]
0x14009a22a  add     rsp, 30h
0x14009a22e  pop     rdi
0x14009a22f  pop     rsi
0x14009a230  pop     rbp
0x14009a231  retn
```
