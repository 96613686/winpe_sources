# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspApoAcquireProcessingPassLock>(AudioDg_Command_DspApoAcquireProcessingPassLock *)

- ea: `0x14009252c`
- end: `0x1400926aa`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspApoAcquireProcessingPassLock@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspApoAcquireProcessingPassLock@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140093430`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14009252c`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400925ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400925ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140092655`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140092655`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140092660`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140092660`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspApoAcquireProcessingPassLock>(
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

  *(_DWORD *)a2 = 11;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 24;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)&word_1400D2996,
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
        (unsigned int)&byte_1400D2AAF,
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
  if ( *(_DWORD *)a2 != 11 )
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
0x14009252c  mov     [rsp+arg_10], rbx
0x140092531  push    rbp
0x140092532  push    rsi
0x140092533  push    rdi
0x140092534  sub     rsp, 30h
0x140092538  mov     dword ptr [rdx], 0Bh
0x14009253e  mov     ebp, 18h
0x140092543  mov     rax, [rcx+28h]
0x140092547  mov     rbx, rdx
0x14009254a  mov     [rdx+8], rax
0x14009254e  mov     rdi, rcx
0x140092551  mov     [rdx+10h], ebp
0x140092554  mov     r8, [rcx+10h]
0x140092558  mov     eax, [r8]
0x14009255b  cmp     eax, 5
0x14009255e  jbe     short loc_140092590
0x140092560  mov     edx, 100000h
0x140092565  mov     rcx, r8
0x140092568  call    _tlgKeywordOn
0x14009256d  test    al, al
0x14009256f  jz      short loc_140092590
0x140092571  mov     eax, [rbx]
0x140092573  lea     rdx, word_1400D2996
0x14009257a  mov     [rsp+48h+arg_0], eax
0x14009257e  mov     rcx, r8
0x140092581  lea     rax, [rsp+48h+arg_0]
0x140092586  mov     qword ptr [rsp+48h+var_28], rax
0x14009258b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140092590  mov     rcx, [rdi+20h]
0x140092594  mov     r8, rbp
0x140092597  mov     rdx, rbx
0x14009259a  mov     rax, [rcx]
0x14009259d  mov     rax, [rax+18h]
0x1400925a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400925a6  test    eax, eax
0x1400925a8  jns     loc_140092666
0x1400925ae  mov     rsi, [rdi+10h]
0x1400925b2  mov     eax, [rsi]
0x1400925b4  cmp     eax, 2
0x1400925b7  jbe     short loc_140092611
0x1400925b9  mov     edx, 100000h
0x1400925be  mov     rcx, rsi
0x1400925c1  call    _tlgKeywordOn
0x1400925c6  test    al, al
0x1400925c8  jz      short loc_140092611
0x1400925ca  call    cs:__imp_GetCurrentProcessId
0x1400925d0  mov     rcx, [rdi+20h]
0x1400925d4  mov     r8, rbp
0x1400925d7  mov     [rsp+48h+arg_0], eax
0x1400925db  mov     rdx, rbx
0x1400925de  mov     rax, [rcx]
0x1400925e1  mov     rax, [rax+18h]
0x1400925e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400925ea  mov     [rsp+48h+arg_8], eax
0x1400925ee  lea     rdx, byte_1400D2AAF
0x1400925f5  lea     rax, [rsp+48h+arg_0]
0x1400925fa  mov     rcx, rsi
0x1400925fd  mov     [rsp+48h+var_20], rax
0x140092602  lea     rax, [rsp+48h+arg_8]
0x140092607  mov     qword ptr [rsp+48h+var_28], rax; int
0x14009260c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140092611  mov     rcx, [rdi+20h]
0x140092615  mov     r8, rbp
0x140092618  mov     rdx, rbx
0x14009261b  mov     rax, [rcx]
0x14009261e  mov     rax, [rax+18h]
0x140092622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092627  mov     rcx, [rdi+20h]
0x14009262b  and     eax, 1FFF0000h
0x140092630  cmp     eax, 70000h
0x140092635  mov     r8, rbp
0x140092638  mov     rdx, rbx
0x14009263b  mov     r9, [rcx]
0x14009263e  mov     rax, [r9+18h]
0x140092642  jnz     short loc_14009264E
0x140092644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092649  movzx   edi, ax
0x14009264c  jmp     short loc_140092655
0x14009264e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092653  mov     edi, eax
0x140092655  call    cs:__imp_GetCurrentProcess
0x14009265b  mov     rcx, rax; hProcess
0x14009265e  mov     edx, edi; uExitCode
0x140092660  call    cs:__imp_TerminateProcess
0x140092666  cmp     dword ptr [rbx], 0Bh
0x140092669  jz      short loc_14009268D
0x14009266b  mov     ebx, 80070057h
0x140092670  mov     edx, 64h ; 'd'; void *
0x140092675  mov     rcx, [rsp+48h]; this
0x14009267a  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140092681  mov     r9d, ebx; char *
0x140092684  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140092689  mov     eax, ebx
0x14009268b  jmp     short loc_14009269D
0x14009268d  mov     ebx, [rbx+4]
0x140092690  test    ebx, ebx
0x140092692  jns     short loc_14009269B
0x140092694  mov     edx, 65h ; 'e'
0x140092699  jmp     short loc_140092675
0x14009269b  xor     eax, eax
0x14009269d  mov     rbx, [rsp+48h+arg_10]
0x1400926a2  add     rsp, 30h
0x1400926a6  pop     rdi
0x1400926a7  pop     rsi
0x1400926a8  pop     rbp
0x1400926a9  retn
```
