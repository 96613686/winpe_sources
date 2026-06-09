# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspCrossProcessAudioEndpointAssignBuffer>(AudioDg_Command_DspCrossProcessAudioEndpointAssignBuffer *)

- ea: `0x140096b60`
- end: `0x140096cde`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspCrossProcessAudioEndpointAssignBuffer@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspCrossProcessAudioEndpointAssignBuffer@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140097d30`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x140096b60`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140096bfe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140096bfe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140096c89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140096c89`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140096c94`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140096c94`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspCrossProcessAudioEndpointAssignBuffer>(
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

  *(_DWORD *)a2 = 13;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 32;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)word_1400D2E8A,
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
        (unsigned int)byte_1400D2E53,
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
  if ( *(_DWORD *)a2 != 13 )
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
0x140096b60  mov     [rsp+arg_10], rbx
0x140096b65  push    rbp
0x140096b66  push    rsi
0x140096b67  push    rdi
0x140096b68  sub     rsp, 30h
0x140096b6c  mov     dword ptr [rdx], 0Dh
0x140096b72  mov     ebp, 20h ; ' '
0x140096b77  mov     rax, [rcx+28h]
0x140096b7b  mov     rbx, rdx
0x140096b7e  mov     [rdx+8], rax
0x140096b82  mov     rdi, rcx
0x140096b85  mov     [rdx+10h], ebp
0x140096b88  mov     r8, [rcx+10h]
0x140096b8c  mov     eax, [r8]
0x140096b8f  cmp     eax, 5
0x140096b92  jbe     short loc_140096BC4
0x140096b94  mov     edx, 100000h
0x140096b99  mov     rcx, r8
0x140096b9c  call    _tlgKeywordOn
0x140096ba1  test    al, al
0x140096ba3  jz      short loc_140096BC4
0x140096ba5  mov     eax, [rbx]
0x140096ba7  lea     rdx, word_1400D2E8A
0x140096bae  mov     [rsp+48h+arg_0], eax
0x140096bb2  mov     rcx, r8
0x140096bb5  lea     rax, [rsp+48h+arg_0]
0x140096bba  mov     qword ptr [rsp+48h+var_28], rax
0x140096bbf  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140096bc4  mov     rcx, [rdi+20h]
0x140096bc8  mov     r8, rbp
0x140096bcb  mov     rdx, rbx
0x140096bce  mov     rax, [rcx]
0x140096bd1  mov     rax, [rax+18h]
0x140096bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096bda  test    eax, eax
0x140096bdc  jns     loc_140096C9A
0x140096be2  mov     rsi, [rdi+10h]
0x140096be6  mov     eax, [rsi]
0x140096be8  cmp     eax, 2
0x140096beb  jbe     short loc_140096C45
0x140096bed  mov     edx, 100000h
0x140096bf2  mov     rcx, rsi
0x140096bf5  call    _tlgKeywordOn
0x140096bfa  test    al, al
0x140096bfc  jz      short loc_140096C45
0x140096bfe  call    cs:__imp_GetCurrentProcessId
0x140096c04  mov     rcx, [rdi+20h]
0x140096c08  mov     r8, rbp
0x140096c0b  mov     [rsp+48h+arg_0], eax
0x140096c0f  mov     rdx, rbx
0x140096c12  mov     rax, [rcx]
0x140096c15  mov     rax, [rax+18h]
0x140096c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096c1e  mov     [rsp+48h+arg_8], eax
0x140096c22  lea     rdx, byte_1400D2E53
0x140096c29  lea     rax, [rsp+48h+arg_0]
0x140096c2e  mov     rcx, rsi
0x140096c31  mov     [rsp+48h+var_20], rax
0x140096c36  lea     rax, [rsp+48h+arg_8]
0x140096c3b  mov     qword ptr [rsp+48h+var_28], rax; int
0x140096c40  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140096c45  mov     rcx, [rdi+20h]
0x140096c49  mov     r8, rbp
0x140096c4c  mov     rdx, rbx
0x140096c4f  mov     rax, [rcx]
0x140096c52  mov     rax, [rax+18h]
0x140096c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096c5b  mov     rcx, [rdi+20h]
0x140096c5f  and     eax, 1FFF0000h
0x140096c64  cmp     eax, 70000h
0x140096c69  mov     r8, rbp
0x140096c6c  mov     rdx, rbx
0x140096c6f  mov     r9, [rcx]
0x140096c72  mov     rax, [r9+18h]
0x140096c76  jnz     short loc_140096C82
0x140096c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096c7d  movzx   edi, ax
0x140096c80  jmp     short loc_140096C89
0x140096c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096c87  mov     edi, eax
0x140096c89  call    cs:__imp_GetCurrentProcess
0x140096c8f  mov     rcx, rax; hProcess
0x140096c92  mov     edx, edi; uExitCode
0x140096c94  call    cs:__imp_TerminateProcess
0x140096c9a  cmp     dword ptr [rbx], 0Dh
0x140096c9d  jz      short loc_140096CC1
0x140096c9f  mov     ebx, 80070057h
0x140096ca4  mov     edx, 64h ; 'd'; void *
0x140096ca9  mov     rcx, [rsp+48h]; this
0x140096cae  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140096cb5  mov     r9d, ebx; char *
0x140096cb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140096cbd  mov     eax, ebx
0x140096cbf  jmp     short loc_140096CD1
0x140096cc1  mov     ebx, [rbx+4]
0x140096cc4  test    ebx, ebx
0x140096cc6  jns     short loc_140096CCF
0x140096cc8  mov     edx, 65h ; 'e'
0x140096ccd  jmp     short loc_140096CA9
0x140096ccf  xor     eax, eax
0x140096cd1  mov     rbx, [rsp+48h+arg_10]
0x140096cd6  add     rsp, 30h
0x140096cda  pop     rdi
0x140096cdb  pop     rsi
0x140096cdc  pop     rbp
0x140096cdd  retn
```
