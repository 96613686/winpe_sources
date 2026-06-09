# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspApoLockForProcess>(AudioDg_Command_DspApoLockForProcess *)

- ea: `0x140092834`
- end: `0x140092a01`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspApoLockForProcess@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspApoLockForProcess@@@Z`
- size: `461`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140093b10`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x140092834`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400928d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400928d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009295d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009295d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140092968`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140092968`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspApoLockForProcess>(
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
  unsigned int v19; // r8d
  unsigned int v20; // edx
  unsigned int v21; // r8d
  unsigned int v22; // edx
  int v23; // ebx
  __int64 v24; // rdx
  int v26; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD v28; // [rsp+50h] [rbp+8h] BYREF
  int v29; // [rsp+58h] [rbp+10h] BYREF

  *(_DWORD *)a2 = 7;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 560;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v28 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)word_1400D2CB2,
      v5,
      v6,
      (__int64)&v28);
  }
  if ( (*(int (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[4] + 24LL))(a1[4], a2, 560) < 0 )
  {
    v8 = (_DWORD *)a1[2];
    if ( *v8 > 2u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v7) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v10 = a1[4];
      v28 = CurrentProcessId;
      v29 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v10 + 24LL))(v10, a2, 560);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v8,
        (unsigned int)&word_1400D2B56,
        v11,
        v12,
        (__int64)&v29,
        (__int64)&v28);
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[4] + 24LL))(a1[4], a2, 560);
    v14 = a1[4];
    v15 = (v13 & 0x1FFF0000) == 458752;
    v16 = *(unsigned __int16 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v14 + 24LL);
    if ( v15 )
      v17 = v16(v14, a2, 560);
    else
      v17 = ((__int64 (__fastcall *)(__int64, __int64, __int64))v16)(v14, a2, 560);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v17);
  }
  if ( *(_DWORD *)a2 != 7 )
    goto LABEL_24;
  v19 = *(_DWORD *)(a2 + 24);
  if ( v19 > 3 )
    goto LABEL_24;
  v20 = 0;
  if ( v19 )
  {
    while ( *(_WORD *)(88LL * v20 + a2 + 60) <= 0x36u )
    {
      if ( ++v20 >= v19 )
        goto LABEL_17;
    }
    goto LABEL_24;
  }
LABEL_17:
  v21 = *(_DWORD *)(a2 + 28);
  if ( v21 > 3 )
  {
LABEL_24:
    v23 = -2147024809;
    v24 = 100;
    goto LABEL_25;
  }
  v22 = 0;
  if ( v21 )
  {
    while ( *(_WORD *)(88LL * v22 + a2 + 324) <= 0x36u )
    {
      if ( ++v22 >= v21 )
        goto LABEL_21;
    }
    goto LABEL_24;
  }
LABEL_21:
  v23 = *(_DWORD *)(a2 + 4);
  if ( v23 >= 0 )
    return 0;
  v24 = 101;
LABEL_25:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v24,
    (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\DspObjectBase.h",
    (const char *)(unsigned int)v23,
    v26);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x140092834  mov     [rsp+arg_10], rbx
0x140092839  push    rbp
0x14009283a  push    rsi
0x14009283b  push    rdi
0x14009283c  sub     rsp, 30h
0x140092840  mov     dword ptr [rdx], 7
0x140092846  mov     ebp, 230h
0x14009284b  mov     rax, [rcx+28h]
0x14009284f  mov     rbx, rdx
0x140092852  mov     [rdx+8], rax
0x140092856  mov     rdi, rcx
0x140092859  mov     [rdx+10h], ebp
0x14009285c  mov     r8, [rcx+10h]
0x140092860  mov     eax, [r8]
0x140092863  cmp     eax, 5
0x140092866  jbe     short loc_140092898
0x140092868  mov     edx, 100000h
0x14009286d  mov     rcx, r8
0x140092870  call    _tlgKeywordOn
0x140092875  test    al, al
0x140092877  jz      short loc_140092898
0x140092879  mov     eax, [rbx]
0x14009287b  lea     rdx, word_1400D2CB2
0x140092882  mov     [rsp+48h+arg_0], eax
0x140092886  mov     rcx, r8
0x140092889  lea     rax, [rsp+48h+arg_0]
0x14009288e  mov     qword ptr [rsp+48h+var_28], rax
0x140092893  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140092898  mov     rcx, [rdi+20h]
0x14009289c  mov     r8, rbp
0x14009289f  mov     rdx, rbx
0x1400928a2  mov     rax, [rcx]
0x1400928a5  mov     rax, [rax+18h]
0x1400928a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400928ae  test    eax, eax
0x1400928b0  jns     loc_14009296E
0x1400928b6  mov     rsi, [rdi+10h]
0x1400928ba  mov     eax, [rsi]
0x1400928bc  cmp     eax, 2
0x1400928bf  jbe     short loc_140092919
0x1400928c1  mov     edx, 100000h
0x1400928c6  mov     rcx, rsi
0x1400928c9  call    _tlgKeywordOn
0x1400928ce  test    al, al
0x1400928d0  jz      short loc_140092919
0x1400928d2  call    cs:__imp_GetCurrentProcessId
0x1400928d8  mov     rcx, [rdi+20h]
0x1400928dc  mov     r8, rbp
0x1400928df  mov     [rsp+48h+arg_0], eax
0x1400928e3  mov     rdx, rbx
0x1400928e6  mov     rax, [rcx]
0x1400928e9  mov     rax, [rax+18h]
0x1400928ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400928f2  mov     [rsp+48h+arg_8], eax
0x1400928f6  lea     rdx, word_1400D2B56
0x1400928fd  lea     rax, [rsp+48h+arg_0]
0x140092902  mov     rcx, rsi
0x140092905  mov     [rsp+48h+var_20], rax
0x14009290a  lea     rax, [rsp+48h+arg_8]
0x14009290f  mov     qword ptr [rsp+48h+var_28], rax; int
0x140092914  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140092919  mov     rcx, [rdi+20h]
0x14009291d  mov     r8, rbp
0x140092920  mov     rdx, rbx
0x140092923  mov     rax, [rcx]
0x140092926  mov     rax, [rax+18h]
0x14009292a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009292f  mov     rcx, [rdi+20h]
0x140092933  and     eax, 1FFF0000h
0x140092938  cmp     eax, 70000h
0x14009293d  mov     r8, rbp
0x140092940  mov     rdx, rbx
0x140092943  mov     r9, [rcx]
0x140092946  mov     rax, [r9+18h]
0x14009294a  jnz     short loc_140092956
0x14009294c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092951  movzx   edi, ax
0x140092954  jmp     short loc_14009295D
0x140092956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009295b  mov     edi, eax
0x14009295d  call    cs:__imp_GetCurrentProcess
0x140092963  mov     rcx, rax; hProcess
0x140092966  mov     edx, edi; uExitCode
0x140092968  call    cs:__imp_TerminateProcess
0x14009296e  cmp     dword ptr [rbx], 7
0x140092971  jnz     short loc_1400929D4
0x140092973  mov     r8d, [rbx+18h]
0x140092977  cmp     r8d, 3
0x14009297b  ja      short loc_1400929D4
0x14009297d  xor     edx, edx
0x14009297f  test    r8d, r8d
0x140092982  jz      short loc_140092999
0x140092984  mov     eax, edx
0x140092986  imul    rcx, rax, 58h ; 'X'
0x14009298a  cmp     word ptr [rcx+rbx+3Ch], 36h ; '6'
0x140092990  ja      short loc_1400929D4
0x140092992  inc     edx
0x140092994  cmp     edx, r8d
0x140092997  jb      short loc_140092984
0x140092999  mov     r8d, [rbx+1Ch]
0x14009299d  cmp     r8d, 3
0x1400929a1  ja      short loc_1400929D4
0x1400929a3  xor     edx, edx
0x1400929a5  test    r8d, r8d
0x1400929a8  jz      short loc_1400929C2
0x1400929aa  mov     eax, edx
0x1400929ac  imul    rcx, rax, 58h ; 'X'
0x1400929b0  cmp     word ptr [rcx+rbx+144h], 36h ; '6'
0x1400929b9  ja      short loc_1400929D4
0x1400929bb  inc     edx
0x1400929bd  cmp     edx, r8d
0x1400929c0  jb      short loc_1400929AA
0x1400929c2  mov     ebx, [rbx+4]
0x1400929c5  test    ebx, ebx
0x1400929c7  jns     short loc_1400929D0
0x1400929c9  mov     edx, 65h ; 'e'
0x1400929ce  jmp     short loc_1400929DE
0x1400929d0  xor     eax, eax
0x1400929d2  jmp     short loc_1400929F4
0x1400929d4  mov     ebx, 80070057h
0x1400929d9  mov     edx, 64h ; 'd'; void *
0x1400929de  mov     rcx, [rsp+48h]; this
0x1400929e3  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x1400929ea  mov     r9d, ebx; char *
0x1400929ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400929f2  mov     eax, ebx
0x1400929f4  mov     rbx, [rsp+48h+arg_10]
0x1400929f9  add     rsp, 30h
0x1400929fd  pop     rdi
0x1400929fe  pop     rsi
0x1400929ff  pop     rbp
0x140092a00  retn
```
