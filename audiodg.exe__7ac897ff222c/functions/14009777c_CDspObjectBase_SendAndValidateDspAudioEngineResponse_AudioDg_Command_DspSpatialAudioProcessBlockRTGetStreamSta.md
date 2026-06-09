# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspSpatialAudioProcessBlockRTGetStreamStatus>(AudioDg_Command_DspSpatialAudioProcessBlockRTGetStreamStatus *)

- ea: `0x14009777c`
- end: `0x1400978fa`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspSpatialAudioProcessBlockRTGetStreamStatus@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspSpatialAudioProcessBlockRTGetStreamStatus@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400982c0`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14009777c`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009781a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009781a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400978a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400978a5`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400978b0`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400978b0`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspSpatialAudioProcessBlockRTGetStreamStatus>(
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

  *(_DWORD *)a2 = 25;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 28;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_1400D30FD,
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
        (unsigned int)&word_1400D30C6,
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
  if ( *(_DWORD *)a2 != 25 )
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
0x14009777c  mov     [rsp+arg_10], rbx
0x140097781  push    rbp
0x140097782  push    rsi
0x140097783  push    rdi
0x140097784  sub     rsp, 30h
0x140097788  mov     dword ptr [rdx], 19h
0x14009778e  mov     ebp, 1Ch
0x140097793  mov     rax, [rcx+28h]
0x140097797  mov     rbx, rdx
0x14009779a  mov     [rdx+8], rax
0x14009779e  mov     rdi, rcx
0x1400977a1  mov     [rdx+10h], ebp
0x1400977a4  mov     r8, [rcx+10h]
0x1400977a8  mov     eax, [r8]
0x1400977ab  cmp     eax, 5
0x1400977ae  jbe     short loc_1400977E0
0x1400977b0  mov     edx, 100000h
0x1400977b5  mov     rcx, r8
0x1400977b8  call    _tlgKeywordOn
0x1400977bd  test    al, al
0x1400977bf  jz      short loc_1400977E0
0x1400977c1  mov     eax, [rbx]
0x1400977c3  lea     rdx, byte_1400D30FD
0x1400977ca  mov     [rsp+48h+arg_0], eax
0x1400977ce  mov     rcx, r8
0x1400977d1  lea     rax, [rsp+48h+arg_0]
0x1400977d6  mov     qword ptr [rsp+48h+var_28], rax
0x1400977db  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1400977e0  mov     rcx, [rdi+20h]
0x1400977e4  mov     r8, rbp
0x1400977e7  mov     rdx, rbx
0x1400977ea  mov     rax, [rcx]
0x1400977ed  mov     rax, [rax+18h]
0x1400977f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400977f6  test    eax, eax
0x1400977f8  jns     loc_1400978B6
0x1400977fe  mov     rsi, [rdi+10h]
0x140097802  mov     eax, [rsi]
0x140097804  cmp     eax, 2
0x140097807  jbe     short loc_140097861
0x140097809  mov     edx, 100000h
0x14009780e  mov     rcx, rsi
0x140097811  call    _tlgKeywordOn
0x140097816  test    al, al
0x140097818  jz      short loc_140097861
0x14009781a  call    cs:__imp_GetCurrentProcessId
0x140097820  mov     rcx, [rdi+20h]
0x140097824  mov     r8, rbp
0x140097827  mov     [rsp+48h+arg_0], eax
0x14009782b  mov     rdx, rbx
0x14009782e  mov     rax, [rcx]
0x140097831  mov     rax, [rax+18h]
0x140097835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009783a  mov     [rsp+48h+arg_8], eax
0x14009783e  lea     rdx, word_1400D30C6
0x140097845  lea     rax, [rsp+48h+arg_0]
0x14009784a  mov     rcx, rsi
0x14009784d  mov     [rsp+48h+var_20], rax
0x140097852  lea     rax, [rsp+48h+arg_8]
0x140097857  mov     qword ptr [rsp+48h+var_28], rax; int
0x14009785c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140097861  mov     rcx, [rdi+20h]
0x140097865  mov     r8, rbp
0x140097868  mov     rdx, rbx
0x14009786b  mov     rax, [rcx]
0x14009786e  mov     rax, [rax+18h]
0x140097872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097877  mov     rcx, [rdi+20h]
0x14009787b  and     eax, 1FFF0000h
0x140097880  cmp     eax, 70000h
0x140097885  mov     r8, rbp
0x140097888  mov     rdx, rbx
0x14009788b  mov     r9, [rcx]
0x14009788e  mov     rax, [r9+18h]
0x140097892  jnz     short loc_14009789E
0x140097894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097899  movzx   edi, ax
0x14009789c  jmp     short loc_1400978A5
0x14009789e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400978a3  mov     edi, eax
0x1400978a5  call    cs:__imp_GetCurrentProcess
0x1400978ab  mov     rcx, rax; hProcess
0x1400978ae  mov     edx, edi; uExitCode
0x1400978b0  call    cs:__imp_TerminateProcess
0x1400978b6  cmp     dword ptr [rbx], 19h
0x1400978b9  jz      short loc_1400978DD
0x1400978bb  mov     ebx, 80070057h
0x1400978c0  mov     edx, 64h ; 'd'; void *
0x1400978c5  mov     rcx, [rsp+48h]; this
0x1400978ca  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x1400978d1  mov     r9d, ebx; char *
0x1400978d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400978d9  mov     eax, ebx
0x1400978db  jmp     short loc_1400978ED
0x1400978dd  mov     ebx, [rbx+4]
0x1400978e0  test    ebx, ebx
0x1400978e2  jns     short loc_1400978EB
0x1400978e4  mov     edx, 65h ; 'e'
0x1400978e9  jmp     short loc_1400978C5
0x1400978eb  xor     eax, eax
0x1400978ed  mov     rbx, [rsp+48h+arg_10]
0x1400978f2  add     rsp, 30h
0x1400978f6  pop     rdi
0x1400978f7  pop     rsi
0x1400978f8  pop     rbp
0x1400978f9  retn
```
