# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspAudioPumpStop>(AudioDg_Command_DspAudioPumpStop *)

- ea: `0x14009a3bc`
- end: `0x14009a53a`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspAudioPumpStop@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspAudioPumpStop@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14009a9b0`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14009a3bc`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009a45a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009a45a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009a4e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009a4e5`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009a4f0`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009a4f0`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspAudioPumpStop>(
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

  *(_DWORD *)a2 = 18;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 24;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_1400D3679,
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
        (unsigned int)word_1400D3642,
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
  if ( *(_DWORD *)a2 != 18 )
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
0x14009a3bc  mov     [rsp+arg_10], rbx
0x14009a3c1  push    rbp
0x14009a3c2  push    rsi
0x14009a3c3  push    rdi
0x14009a3c4  sub     rsp, 30h
0x14009a3c8  mov     dword ptr [rdx], 12h
0x14009a3ce  mov     ebp, 18h
0x14009a3d3  mov     rax, [rcx+28h]
0x14009a3d7  mov     rbx, rdx
0x14009a3da  mov     [rdx+8], rax
0x14009a3de  mov     rdi, rcx
0x14009a3e1  mov     [rdx+10h], ebp
0x14009a3e4  mov     r8, [rcx+10h]
0x14009a3e8  mov     eax, [r8]
0x14009a3eb  cmp     eax, 5
0x14009a3ee  jbe     short loc_14009A420
0x14009a3f0  mov     edx, 100000h
0x14009a3f5  mov     rcx, r8
0x14009a3f8  call    _tlgKeywordOn
0x14009a3fd  test    al, al
0x14009a3ff  jz      short loc_14009A420
0x14009a401  mov     eax, [rbx]
0x14009a403  lea     rdx, byte_1400D3679
0x14009a40a  mov     [rsp+48h+arg_0], eax
0x14009a40e  mov     rcx, r8
0x14009a411  lea     rax, [rsp+48h+arg_0]
0x14009a416  mov     qword ptr [rsp+48h+var_28], rax
0x14009a41b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x14009a420  mov     rcx, [rdi+20h]
0x14009a424  mov     r8, rbp
0x14009a427  mov     rdx, rbx
0x14009a42a  mov     rax, [rcx]
0x14009a42d  mov     rax, [rax+18h]
0x14009a431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a436  test    eax, eax
0x14009a438  jns     loc_14009A4F6
0x14009a43e  mov     rsi, [rdi+10h]
0x14009a442  mov     eax, [rsi]
0x14009a444  cmp     eax, 2
0x14009a447  jbe     short loc_14009A4A1
0x14009a449  mov     edx, 100000h
0x14009a44e  mov     rcx, rsi
0x14009a451  call    _tlgKeywordOn
0x14009a456  test    al, al
0x14009a458  jz      short loc_14009A4A1
0x14009a45a  call    cs:__imp_GetCurrentProcessId
0x14009a460  mov     rcx, [rdi+20h]
0x14009a464  mov     r8, rbp
0x14009a467  mov     [rsp+48h+arg_0], eax
0x14009a46b  mov     rdx, rbx
0x14009a46e  mov     rax, [rcx]
0x14009a471  mov     rax, [rax+18h]
0x14009a475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a47a  mov     [rsp+48h+arg_8], eax
0x14009a47e  lea     rdx, word_1400D3642
0x14009a485  lea     rax, [rsp+48h+arg_0]
0x14009a48a  mov     rcx, rsi
0x14009a48d  mov     [rsp+48h+var_20], rax
0x14009a492  lea     rax, [rsp+48h+arg_8]
0x14009a497  mov     qword ptr [rsp+48h+var_28], rax; int
0x14009a49c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14009a4a1  mov     rcx, [rdi+20h]
0x14009a4a5  mov     r8, rbp
0x14009a4a8  mov     rdx, rbx
0x14009a4ab  mov     rax, [rcx]
0x14009a4ae  mov     rax, [rax+18h]
0x14009a4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a4b7  mov     rcx, [rdi+20h]
0x14009a4bb  and     eax, 1FFF0000h
0x14009a4c0  cmp     eax, 70000h
0x14009a4c5  mov     r8, rbp
0x14009a4c8  mov     rdx, rbx
0x14009a4cb  mov     r9, [rcx]
0x14009a4ce  mov     rax, [r9+18h]
0x14009a4d2  jnz     short loc_14009A4DE
0x14009a4d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a4d9  movzx   edi, ax
0x14009a4dc  jmp     short loc_14009A4E5
0x14009a4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a4e3  mov     edi, eax
0x14009a4e5  call    cs:__imp_GetCurrentProcess
0x14009a4eb  mov     rcx, rax; hProcess
0x14009a4ee  mov     edx, edi; uExitCode
0x14009a4f0  call    cs:__imp_TerminateProcess
0x14009a4f6  cmp     dword ptr [rbx], 12h
0x14009a4f9  jz      short loc_14009A51D
0x14009a4fb  mov     ebx, 80070057h
0x14009a500  mov     edx, 64h ; 'd'; void *
0x14009a505  mov     rcx, [rsp+48h]; this
0x14009a50a  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14009a511  mov     r9d, ebx; char *
0x14009a514  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009a519  mov     eax, ebx
0x14009a51b  jmp     short loc_14009A52D
0x14009a51d  mov     ebx, [rbx+4]
0x14009a520  test    ebx, ebx
0x14009a522  jns     short loc_14009A52B
0x14009a524  mov     edx, 65h ; 'e'
0x14009a529  jmp     short loc_14009A505
0x14009a52b  xor     eax, eax
0x14009a52d  mov     rbx, [rsp+48h+arg_10]
0x14009a532  add     rsp, 30h
0x14009a536  pop     rdi
0x14009a537  pop     rsi
0x14009a538  pop     rbp
0x14009a539  retn
```
