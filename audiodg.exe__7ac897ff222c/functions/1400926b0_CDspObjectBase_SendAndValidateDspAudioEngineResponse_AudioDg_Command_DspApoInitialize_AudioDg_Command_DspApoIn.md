# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspApoInitialize>(AudioDg_Command_DspApoInitialize *)

- ea: `0x1400926b0`
- end: `0x14009282e`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspApoInitialize@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspApoInitialize@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140093a60`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x1400926b0`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009274e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009274e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400927d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400927d9`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400927e4`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400927e4`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspApoInitialize>(
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

  *(_DWORD *)a2 = 6;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 36;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_1400D2BFD,
      v5,
      v6,
      (__int64)&v24);
  }
  if ( (*(int (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[4] + 24LL))(a1[4], a2, 36) < 0 )
  {
    v8 = (_DWORD *)a1[2];
    if ( *v8 > 2u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v7) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v10 = a1[4];
      v24 = CurrentProcessId;
      v25 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v10 + 24LL))(v10, a2, 36);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v8,
        (unsigned int)byte_1400D2CEB,
        v11,
        v12,
        (__int64)&v25,
        (__int64)&v24);
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[4] + 24LL))(a1[4], a2, 36);
    v14 = a1[4];
    v15 = (v13 & 0x1FFF0000) == 458752;
    v16 = *(unsigned __int16 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v14 + 24LL);
    if ( v15 )
      v17 = v16(v14, a2, 36);
    else
      v17 = ((__int64 (__fastcall *)(__int64, __int64, __int64))v16)(v14, a2, 36);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v17);
  }
  if ( *(_DWORD *)a2 != 6 )
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
0x1400926b0  mov     [rsp+arg_10], rbx
0x1400926b5  push    rbp
0x1400926b6  push    rsi
0x1400926b7  push    rdi
0x1400926b8  sub     rsp, 30h
0x1400926bc  mov     dword ptr [rdx], 6
0x1400926c2  mov     ebp, 24h ; '$'
0x1400926c7  mov     rax, [rcx+28h]
0x1400926cb  mov     rbx, rdx
0x1400926ce  mov     [rdx+8], rax
0x1400926d2  mov     rdi, rcx
0x1400926d5  mov     [rdx+10h], ebp
0x1400926d8  mov     r8, [rcx+10h]
0x1400926dc  mov     eax, [r8]
0x1400926df  cmp     eax, 5
0x1400926e2  jbe     short loc_140092714
0x1400926e4  mov     edx, 100000h
0x1400926e9  mov     rcx, r8
0x1400926ec  call    _tlgKeywordOn
0x1400926f1  test    al, al
0x1400926f3  jz      short loc_140092714
0x1400926f5  mov     eax, [rbx]
0x1400926f7  lea     rdx, byte_1400D2BFD
0x1400926fe  mov     [rsp+48h+arg_0], eax
0x140092702  mov     rcx, r8
0x140092705  lea     rax, [rsp+48h+arg_0]
0x14009270a  mov     qword ptr [rsp+48h+var_28], rax
0x14009270f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140092714  mov     rcx, [rdi+20h]
0x140092718  mov     r8, rbp
0x14009271b  mov     rdx, rbx
0x14009271e  mov     rax, [rcx]
0x140092721  mov     rax, [rax+18h]
0x140092725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009272a  test    eax, eax
0x14009272c  jns     loc_1400927EA
0x140092732  mov     rsi, [rdi+10h]
0x140092736  mov     eax, [rsi]
0x140092738  cmp     eax, 2
0x14009273b  jbe     short loc_140092795
0x14009273d  mov     edx, 100000h
0x140092742  mov     rcx, rsi
0x140092745  call    _tlgKeywordOn
0x14009274a  test    al, al
0x14009274c  jz      short loc_140092795
0x14009274e  call    cs:__imp_GetCurrentProcessId
0x140092754  mov     rcx, [rdi+20h]
0x140092758  mov     r8, rbp
0x14009275b  mov     [rsp+48h+arg_0], eax
0x14009275f  mov     rdx, rbx
0x140092762  mov     rax, [rcx]
0x140092765  mov     rax, [rax+18h]
0x140092769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009276e  mov     [rsp+48h+arg_8], eax
0x140092772  lea     rdx, byte_1400D2CEB
0x140092779  lea     rax, [rsp+48h+arg_0]
0x14009277e  mov     rcx, rsi
0x140092781  mov     [rsp+48h+var_20], rax
0x140092786  lea     rax, [rsp+48h+arg_8]
0x14009278b  mov     qword ptr [rsp+48h+var_28], rax; int
0x140092790  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140092795  mov     rcx, [rdi+20h]
0x140092799  mov     r8, rbp
0x14009279c  mov     rdx, rbx
0x14009279f  mov     rax, [rcx]
0x1400927a2  mov     rax, [rax+18h]
0x1400927a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400927ab  mov     rcx, [rdi+20h]
0x1400927af  and     eax, 1FFF0000h
0x1400927b4  cmp     eax, 70000h
0x1400927b9  mov     r8, rbp
0x1400927bc  mov     rdx, rbx
0x1400927bf  mov     r9, [rcx]
0x1400927c2  mov     rax, [r9+18h]
0x1400927c6  jnz     short loc_1400927D2
0x1400927c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400927cd  movzx   edi, ax
0x1400927d0  jmp     short loc_1400927D9
0x1400927d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400927d7  mov     edi, eax
0x1400927d9  call    cs:__imp_GetCurrentProcess
0x1400927df  mov     rcx, rax; hProcess
0x1400927e2  mov     edx, edi; uExitCode
0x1400927e4  call    cs:__imp_TerminateProcess
0x1400927ea  cmp     dword ptr [rbx], 6
0x1400927ed  jz      short loc_140092811
0x1400927ef  mov     ebx, 80070057h
0x1400927f4  mov     edx, 64h ; 'd'; void *
0x1400927f9  mov     rcx, [rsp+48h]; this
0x1400927fe  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140092805  mov     r9d, ebx; char *
0x140092808  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009280d  mov     eax, ebx
0x14009280f  jmp     short loc_140092821
0x140092811  mov     ebx, [rbx+4]
0x140092814  test    ebx, ebx
0x140092816  jns     short loc_14009281F
0x140092818  mov     edx, 65h ; 'e'
0x14009281d  jmp     short loc_1400927F9
0x14009281f  xor     eax, eax
0x140092821  mov     rbx, [rsp+48h+arg_10]
0x140092826  add     rsp, 30h
0x14009282a  pop     rdi
0x14009282b  pop     rsi
0x14009282c  pop     rbp
0x14009282d  retn
```
