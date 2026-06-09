# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspSpatialAudioProcessBlockRTGetAllocatedObjectCount>(AudioDg_Command_DspSpatialAudioProcessBlockRTGetAllocatedObjectCount *)

- ea: `0x140096fec`
- end: `0x14009716a`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspSpatialAudioProcessBlockRTGetAllocatedObjectCount@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspSpatialAudioProcessBlockRTGetAllocatedObjectCount@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140097fc0`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x140096fec`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009708a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009708a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140097115`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140097115`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140097120`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140097120`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspSpatialAudioProcessBlockRTGetAllocatedObjectCount>(
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

  *(_DWORD *)a2 = 24;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 32;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_1400D324D,
      v5,
      v6,
      (__int64)&v24);
  }
  if ( (*(int (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[4] + 24LL))(a1[4], a2, 32) < 0 )
  {
    v8 = (_DWORD *)a1[2];
    if ( *v8 > 2u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v7) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v10 = a1[4];
      v24 = CurrentProcessId;
      v25 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v10 + 24LL))(v10, a2, 32);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v8,
        (unsigned int)&word_1400D3136,
        v11,
        v12,
        (__int64)&v25,
        (__int64)&v24);
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[4] + 24LL))(a1[4], a2, 32);
    v14 = a1[4];
    v15 = (v13 & 0x1FFF0000) == 458752;
    v16 = *(unsigned __int16 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v14 + 24LL);
    if ( v15 )
      v17 = v16(v14, a2, 32);
    else
      v17 = ((__int64 (__fastcall *)(__int64, __int64, __int64))v16)(v14, a2, 32);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v17);
  }
  if ( *(_DWORD *)a2 != 24 )
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
0x140096fec  mov     [rsp+arg_10], rbx
0x140096ff1  push    rbp
0x140096ff2  push    rsi
0x140096ff3  push    rdi
0x140096ff4  sub     rsp, 30h
0x140096ff8  mov     dword ptr [rdx], 18h
0x140096ffe  mov     ebp, 20h ; ' '
0x140097003  mov     rax, [rcx+28h]
0x140097007  mov     rbx, rdx
0x14009700a  mov     [rdx+8], rax
0x14009700e  mov     rdi, rcx
0x140097011  mov     [rdx+10h], ebp
0x140097014  mov     r8, [rcx+10h]
0x140097018  mov     eax, [r8]
0x14009701b  cmp     eax, 5
0x14009701e  jbe     short loc_140097050
0x140097020  mov     edx, 100000h
0x140097025  mov     rcx, r8
0x140097028  call    _tlgKeywordOn
0x14009702d  test    al, al
0x14009702f  jz      short loc_140097050
0x140097031  mov     eax, [rbx]
0x140097033  lea     rdx, byte_1400D324D
0x14009703a  mov     [rsp+48h+arg_0], eax
0x14009703e  mov     rcx, r8
0x140097041  lea     rax, [rsp+48h+arg_0]
0x140097046  mov     qword ptr [rsp+48h+var_28], rax
0x14009704b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140097050  mov     rcx, [rdi+20h]
0x140097054  mov     r8, rbp
0x140097057  mov     rdx, rbx
0x14009705a  mov     rax, [rcx]
0x14009705d  mov     rax, [rax+18h]
0x140097061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097066  test    eax, eax
0x140097068  jns     loc_140097126
0x14009706e  mov     rsi, [rdi+10h]
0x140097072  mov     eax, [rsi]
0x140097074  cmp     eax, 2
0x140097077  jbe     short loc_1400970D1
0x140097079  mov     edx, 100000h
0x14009707e  mov     rcx, rsi
0x140097081  call    _tlgKeywordOn
0x140097086  test    al, al
0x140097088  jz      short loc_1400970D1
0x14009708a  call    cs:__imp_GetCurrentProcessId
0x140097090  mov     rcx, [rdi+20h]
0x140097094  mov     r8, rbp
0x140097097  mov     [rsp+48h+arg_0], eax
0x14009709b  mov     rdx, rbx
0x14009709e  mov     rax, [rcx]
0x1400970a1  mov     rax, [rax+18h]
0x1400970a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400970aa  mov     [rsp+48h+arg_8], eax
0x1400970ae  lea     rdx, word_1400D3136
0x1400970b5  lea     rax, [rsp+48h+arg_0]
0x1400970ba  mov     rcx, rsi
0x1400970bd  mov     [rsp+48h+var_20], rax
0x1400970c2  lea     rax, [rsp+48h+arg_8]
0x1400970c7  mov     qword ptr [rsp+48h+var_28], rax; int
0x1400970cc  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400970d1  mov     rcx, [rdi+20h]
0x1400970d5  mov     r8, rbp
0x1400970d8  mov     rdx, rbx
0x1400970db  mov     rax, [rcx]
0x1400970de  mov     rax, [rax+18h]
0x1400970e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400970e7  mov     rcx, [rdi+20h]
0x1400970eb  and     eax, 1FFF0000h
0x1400970f0  cmp     eax, 70000h
0x1400970f5  mov     r8, rbp
0x1400970f8  mov     rdx, rbx
0x1400970fb  mov     r9, [rcx]
0x1400970fe  mov     rax, [r9+18h]
0x140097102  jnz     short loc_14009710E
0x140097104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097109  movzx   edi, ax
0x14009710c  jmp     short loc_140097115
0x14009710e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097113  mov     edi, eax
0x140097115  call    cs:__imp_GetCurrentProcess
0x14009711b  mov     rcx, rax; hProcess
0x14009711e  mov     edx, edi; uExitCode
0x140097120  call    cs:__imp_TerminateProcess
0x140097126  cmp     dword ptr [rbx], 18h
0x140097129  jz      short loc_14009714D
0x14009712b  mov     ebx, 80070057h
0x140097130  mov     edx, 64h ; 'd'; void *
0x140097135  mov     rcx, [rsp+48h]; this
0x14009713a  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140097141  mov     r9d, ebx; char *
0x140097144  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140097149  mov     eax, ebx
0x14009714b  jmp     short loc_14009715D
0x14009714d  mov     ebx, [rbx+4]
0x140097150  test    ebx, ebx
0x140097152  jns     short loc_14009715B
0x140097154  mov     edx, 65h ; 'e'
0x140097159  jmp     short loc_140097135
0x14009715b  xor     eax, eax
0x14009715d  mov     rbx, [rsp+48h+arg_10]
0x140097162  add     rsp, 30h
0x140097166  pop     rdi
0x140097167  pop     rsi
0x140097168  pop     rbp
0x140097169  retn
```
