# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspAudioPumpStart>(AudioDg_Command_DspAudioPumpStart *)

- ea: `0x14009a238`
- end: `0x14009a3b6`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspAudioPumpStart@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspAudioPumpStart@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14009a940`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14009a238`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009a2d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009a2d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009a361`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009a361`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009a36c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009a36c`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspAudioPumpStart>(
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

  *(_DWORD *)a2 = 17;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 24;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_1400D36E9,
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
        (unsigned int)word_1400D36B2,
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
  if ( *(_DWORD *)a2 != 17 )
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
0x14009a238  mov     [rsp+arg_10], rbx
0x14009a23d  push    rbp
0x14009a23e  push    rsi
0x14009a23f  push    rdi
0x14009a240  sub     rsp, 30h
0x14009a244  mov     dword ptr [rdx], 11h
0x14009a24a  mov     ebp, 18h
0x14009a24f  mov     rax, [rcx+28h]
0x14009a253  mov     rbx, rdx
0x14009a256  mov     [rdx+8], rax
0x14009a25a  mov     rdi, rcx
0x14009a25d  mov     [rdx+10h], ebp
0x14009a260  mov     r8, [rcx+10h]
0x14009a264  mov     eax, [r8]
0x14009a267  cmp     eax, 5
0x14009a26a  jbe     short loc_14009A29C
0x14009a26c  mov     edx, 100000h
0x14009a271  mov     rcx, r8
0x14009a274  call    _tlgKeywordOn
0x14009a279  test    al, al
0x14009a27b  jz      short loc_14009A29C
0x14009a27d  mov     eax, [rbx]
0x14009a27f  lea     rdx, byte_1400D36E9
0x14009a286  mov     [rsp+48h+arg_0], eax
0x14009a28a  mov     rcx, r8
0x14009a28d  lea     rax, [rsp+48h+arg_0]
0x14009a292  mov     qword ptr [rsp+48h+var_28], rax
0x14009a297  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x14009a29c  mov     rcx, [rdi+20h]
0x14009a2a0  mov     r8, rbp
0x14009a2a3  mov     rdx, rbx
0x14009a2a6  mov     rax, [rcx]
0x14009a2a9  mov     rax, [rax+18h]
0x14009a2ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a2b2  test    eax, eax
0x14009a2b4  jns     loc_14009A372
0x14009a2ba  mov     rsi, [rdi+10h]
0x14009a2be  mov     eax, [rsi]
0x14009a2c0  cmp     eax, 2
0x14009a2c3  jbe     short loc_14009A31D
0x14009a2c5  mov     edx, 100000h
0x14009a2ca  mov     rcx, rsi
0x14009a2cd  call    _tlgKeywordOn
0x14009a2d2  test    al, al
0x14009a2d4  jz      short loc_14009A31D
0x14009a2d6  call    cs:__imp_GetCurrentProcessId
0x14009a2dc  mov     rcx, [rdi+20h]
0x14009a2e0  mov     r8, rbp
0x14009a2e3  mov     [rsp+48h+arg_0], eax
0x14009a2e7  mov     rdx, rbx
0x14009a2ea  mov     rax, [rcx]
0x14009a2ed  mov     rax, [rax+18h]
0x14009a2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a2f6  mov     [rsp+48h+arg_8], eax
0x14009a2fa  lea     rdx, word_1400D36B2
0x14009a301  lea     rax, [rsp+48h+arg_0]
0x14009a306  mov     rcx, rsi
0x14009a309  mov     [rsp+48h+var_20], rax
0x14009a30e  lea     rax, [rsp+48h+arg_8]
0x14009a313  mov     qword ptr [rsp+48h+var_28], rax; int
0x14009a318  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14009a31d  mov     rcx, [rdi+20h]
0x14009a321  mov     r8, rbp
0x14009a324  mov     rdx, rbx
0x14009a327  mov     rax, [rcx]
0x14009a32a  mov     rax, [rax+18h]
0x14009a32e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a333  mov     rcx, [rdi+20h]
0x14009a337  and     eax, 1FFF0000h
0x14009a33c  cmp     eax, 70000h
0x14009a341  mov     r8, rbp
0x14009a344  mov     rdx, rbx
0x14009a347  mov     r9, [rcx]
0x14009a34a  mov     rax, [r9+18h]
0x14009a34e  jnz     short loc_14009A35A
0x14009a350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a355  movzx   edi, ax
0x14009a358  jmp     short loc_14009A361
0x14009a35a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a35f  mov     edi, eax
0x14009a361  call    cs:__imp_GetCurrentProcess
0x14009a367  mov     rcx, rax; hProcess
0x14009a36a  mov     edx, edi; uExitCode
0x14009a36c  call    cs:__imp_TerminateProcess
0x14009a372  cmp     dword ptr [rbx], 11h
0x14009a375  jz      short loc_14009A399
0x14009a377  mov     ebx, 80070057h
0x14009a37c  mov     edx, 64h ; 'd'; void *
0x14009a381  mov     rcx, [rsp+48h]; this
0x14009a386  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14009a38d  mov     r9d, ebx; char *
0x14009a390  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009a395  mov     eax, ebx
0x14009a397  jmp     short loc_14009A3A9
0x14009a399  mov     ebx, [rbx+4]
0x14009a39c  test    ebx, ebx
0x14009a39e  jns     short loc_14009A3A7
0x14009a3a0  mov     edx, 65h ; 'e'
0x14009a3a5  jmp     short loc_14009A381
0x14009a3a7  xor     eax, eax
0x14009a3a9  mov     rbx, [rsp+48h+arg_10]
0x14009a3ae  add     rsp, 30h
0x14009a3b2  pop     rdi
0x14009a3b3  pop     rsi
0x14009a3b4  pop     rbp
0x14009a3b5  retn
```
