# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspApoRegisterSpatialAudioProcessBlock>(AudioDg_Command_DspApoRegisterSpatialAudioProcessBlock *)

- ea: `0x140092a08`
- end: `0x140092b86`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspApoRegisterSpatialAudioProcessBlock@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspApoRegisterSpatialAudioProcessBlock@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140093df0`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x140092a08`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140092aa6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140092aa6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140092b31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140092b31`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140092b3c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140092b3c`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspApoRegisterSpatialAudioProcessBlock>(
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

  *(_DWORD *)a2 = 9;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 36;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)&dword_1400D2BC4,
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
        (unsigned int)byte_1400D2B8D,
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
  if ( *(_DWORD *)a2 != 9 )
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
0x140092a08  mov     [rsp+arg_10], rbx
0x140092a0d  push    rbp
0x140092a0e  push    rsi
0x140092a0f  push    rdi
0x140092a10  sub     rsp, 30h
0x140092a14  mov     dword ptr [rdx], 9
0x140092a1a  mov     ebp, 24h ; '$'
0x140092a1f  mov     rax, [rcx+28h]
0x140092a23  mov     rbx, rdx
0x140092a26  mov     [rdx+8], rax
0x140092a2a  mov     rdi, rcx
0x140092a2d  mov     [rdx+10h], ebp
0x140092a30  mov     r8, [rcx+10h]
0x140092a34  mov     eax, [r8]
0x140092a37  cmp     eax, 5
0x140092a3a  jbe     short loc_140092A6C
0x140092a3c  mov     edx, 100000h
0x140092a41  mov     rcx, r8
0x140092a44  call    _tlgKeywordOn
0x140092a49  test    al, al
0x140092a4b  jz      short loc_140092A6C
0x140092a4d  mov     eax, [rbx]
0x140092a4f  lea     rdx, dword_1400D2BC4
0x140092a56  mov     [rsp+48h+arg_0], eax
0x140092a5a  mov     rcx, r8
0x140092a5d  lea     rax, [rsp+48h+arg_0]
0x140092a62  mov     qword ptr [rsp+48h+var_28], rax
0x140092a67  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140092a6c  mov     rcx, [rdi+20h]
0x140092a70  mov     r8, rbp
0x140092a73  mov     rdx, rbx
0x140092a76  mov     rax, [rcx]
0x140092a79  mov     rax, [rax+18h]
0x140092a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092a82  test    eax, eax
0x140092a84  jns     loc_140092B42
0x140092a8a  mov     rsi, [rdi+10h]
0x140092a8e  mov     eax, [rsi]
0x140092a90  cmp     eax, 2
0x140092a93  jbe     short loc_140092AED
0x140092a95  mov     edx, 100000h
0x140092a9a  mov     rcx, rsi
0x140092a9d  call    _tlgKeywordOn
0x140092aa2  test    al, al
0x140092aa4  jz      short loc_140092AED
0x140092aa6  call    cs:__imp_GetCurrentProcessId
0x140092aac  mov     rcx, [rdi+20h]
0x140092ab0  mov     r8, rbp
0x140092ab3  mov     [rsp+48h+arg_0], eax
0x140092ab7  mov     rdx, rbx
0x140092aba  mov     rax, [rcx]
0x140092abd  mov     rax, [rax+18h]
0x140092ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092ac6  mov     [rsp+48h+arg_8], eax
0x140092aca  lea     rdx, byte_1400D2B8D
0x140092ad1  lea     rax, [rsp+48h+arg_0]
0x140092ad6  mov     rcx, rsi
0x140092ad9  mov     [rsp+48h+var_20], rax
0x140092ade  lea     rax, [rsp+48h+arg_8]
0x140092ae3  mov     qword ptr [rsp+48h+var_28], rax; int
0x140092ae8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140092aed  mov     rcx, [rdi+20h]
0x140092af1  mov     r8, rbp
0x140092af4  mov     rdx, rbx
0x140092af7  mov     rax, [rcx]
0x140092afa  mov     rax, [rax+18h]
0x140092afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092b03  mov     rcx, [rdi+20h]
0x140092b07  and     eax, 1FFF0000h
0x140092b0c  cmp     eax, 70000h
0x140092b11  mov     r8, rbp
0x140092b14  mov     rdx, rbx
0x140092b17  mov     r9, [rcx]
0x140092b1a  mov     rax, [r9+18h]
0x140092b1e  jnz     short loc_140092B2A
0x140092b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092b25  movzx   edi, ax
0x140092b28  jmp     short loc_140092B31
0x140092b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092b2f  mov     edi, eax
0x140092b31  call    cs:__imp_GetCurrentProcess
0x140092b37  mov     rcx, rax; hProcess
0x140092b3a  mov     edx, edi; uExitCode
0x140092b3c  call    cs:__imp_TerminateProcess
0x140092b42  cmp     dword ptr [rbx], 9
0x140092b45  jz      short loc_140092B69
0x140092b47  mov     ebx, 80070057h
0x140092b4c  mov     edx, 64h ; 'd'; void *
0x140092b51  mov     rcx, [rsp+48h]; this
0x140092b56  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140092b5d  mov     r9d, ebx; char *
0x140092b60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140092b65  mov     eax, ebx
0x140092b67  jmp     short loc_140092B79
0x140092b69  mov     ebx, [rbx+4]
0x140092b6c  test    ebx, ebx
0x140092b6e  jns     short loc_140092B77
0x140092b70  mov     edx, 65h ; 'e'
0x140092b75  jmp     short loc_140092B51
0x140092b77  xor     eax, eax
0x140092b79  mov     rbx, [rsp+48h+arg_10]
0x140092b7e  add     rsp, 30h
0x140092b82  pop     rdi
0x140092b83  pop     rsi
0x140092b84  pop     rbp
0x140092b85  retn
```
