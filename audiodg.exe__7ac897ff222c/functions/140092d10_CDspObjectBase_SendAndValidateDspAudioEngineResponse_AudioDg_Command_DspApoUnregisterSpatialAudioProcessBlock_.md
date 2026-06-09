# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspApoUnregisterSpatialAudioProcessBlock>(AudioDg_Command_DspApoUnregisterSpatialAudioProcessBlock *)

- ea: `0x140092d10`
- end: `0x140092e8e`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspApoUnregisterSpatialAudioProcessBlock@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspApoUnregisterSpatialAudioProcessBlock@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400943c0`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x140092d10`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140092dae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140092dae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140092e39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140092e39`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140092e44`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140092e44`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspApoUnregisterSpatialAudioProcessBlock>(
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

  *(_DWORD *)a2 = 10;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 36;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)&word_1400D2A06,
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
        (unsigned int)&byte_1400D29CF,
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
  if ( *(_DWORD *)a2 != 10 )
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
0x140092d10  mov     [rsp+arg_10], rbx
0x140092d15  push    rbp
0x140092d16  push    rsi
0x140092d17  push    rdi
0x140092d18  sub     rsp, 30h
0x140092d1c  mov     dword ptr [rdx], 0Ah
0x140092d22  mov     ebp, 24h ; '$'
0x140092d27  mov     rax, [rcx+28h]
0x140092d2b  mov     rbx, rdx
0x140092d2e  mov     [rdx+8], rax
0x140092d32  mov     rdi, rcx
0x140092d35  mov     [rdx+10h], ebp
0x140092d38  mov     r8, [rcx+10h]
0x140092d3c  mov     eax, [r8]
0x140092d3f  cmp     eax, 5
0x140092d42  jbe     short loc_140092D74
0x140092d44  mov     edx, 100000h
0x140092d49  mov     rcx, r8
0x140092d4c  call    _tlgKeywordOn
0x140092d51  test    al, al
0x140092d53  jz      short loc_140092D74
0x140092d55  mov     eax, [rbx]
0x140092d57  lea     rdx, word_1400D2A06
0x140092d5e  mov     [rsp+48h+arg_0], eax
0x140092d62  mov     rcx, r8
0x140092d65  lea     rax, [rsp+48h+arg_0]
0x140092d6a  mov     qword ptr [rsp+48h+var_28], rax
0x140092d6f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140092d74  mov     rcx, [rdi+20h]
0x140092d78  mov     r8, rbp
0x140092d7b  mov     rdx, rbx
0x140092d7e  mov     rax, [rcx]
0x140092d81  mov     rax, [rax+18h]
0x140092d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092d8a  test    eax, eax
0x140092d8c  jns     loc_140092E4A
0x140092d92  mov     rsi, [rdi+10h]
0x140092d96  mov     eax, [rsi]
0x140092d98  cmp     eax, 2
0x140092d9b  jbe     short loc_140092DF5
0x140092d9d  mov     edx, 100000h
0x140092da2  mov     rcx, rsi
0x140092da5  call    _tlgKeywordOn
0x140092daa  test    al, al
0x140092dac  jz      short loc_140092DF5
0x140092dae  call    cs:__imp_GetCurrentProcessId
0x140092db4  mov     rcx, [rdi+20h]
0x140092db8  mov     r8, rbp
0x140092dbb  mov     [rsp+48h+arg_0], eax
0x140092dbf  mov     rdx, rbx
0x140092dc2  mov     rax, [rcx]
0x140092dc5  mov     rax, [rax+18h]
0x140092dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092dce  mov     [rsp+48h+arg_8], eax
0x140092dd2  lea     rdx, byte_1400D29CF
0x140092dd9  lea     rax, [rsp+48h+arg_0]
0x140092dde  mov     rcx, rsi
0x140092de1  mov     [rsp+48h+var_20], rax
0x140092de6  lea     rax, [rsp+48h+arg_8]
0x140092deb  mov     qword ptr [rsp+48h+var_28], rax; int
0x140092df0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140092df5  mov     rcx, [rdi+20h]
0x140092df9  mov     r8, rbp
0x140092dfc  mov     rdx, rbx
0x140092dff  mov     rax, [rcx]
0x140092e02  mov     rax, [rax+18h]
0x140092e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092e0b  mov     rcx, [rdi+20h]
0x140092e0f  and     eax, 1FFF0000h
0x140092e14  cmp     eax, 70000h
0x140092e19  mov     r8, rbp
0x140092e1c  mov     rdx, rbx
0x140092e1f  mov     r9, [rcx]
0x140092e22  mov     rax, [r9+18h]
0x140092e26  jnz     short loc_140092E32
0x140092e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092e2d  movzx   edi, ax
0x140092e30  jmp     short loc_140092E39
0x140092e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092e37  mov     edi, eax
0x140092e39  call    cs:__imp_GetCurrentProcess
0x140092e3f  mov     rcx, rax; hProcess
0x140092e42  mov     edx, edi; uExitCode
0x140092e44  call    cs:__imp_TerminateProcess
0x140092e4a  cmp     dword ptr [rbx], 0Ah
0x140092e4d  jz      short loc_140092E71
0x140092e4f  mov     ebx, 80070057h
0x140092e54  mov     edx, 64h ; 'd'; void *
0x140092e59  mov     rcx, [rsp+48h]; this
0x140092e5e  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140092e65  mov     r9d, ebx; char *
0x140092e68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140092e6d  mov     eax, ebx
0x140092e6f  jmp     short loc_140092E81
0x140092e71  mov     ebx, [rbx+4]
0x140092e74  test    ebx, ebx
0x140092e76  jns     short loc_140092E7F
0x140092e78  mov     edx, 65h ; 'e'
0x140092e7d  jmp     short loc_140092E59
0x140092e7f  xor     eax, eax
0x140092e81  mov     rbx, [rsp+48h+arg_10]
0x140092e86  add     rsp, 30h
0x140092e8a  pop     rdi
0x140092e8b  pop     rsi
0x140092e8c  pop     rbp
0x140092e8d  retn
```
