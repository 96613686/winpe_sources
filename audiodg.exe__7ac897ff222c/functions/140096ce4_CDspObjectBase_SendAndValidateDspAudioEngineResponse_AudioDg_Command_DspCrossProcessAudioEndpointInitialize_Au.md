# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspCrossProcessAudioEndpointInitialize>(AudioDg_Command_DspCrossProcessAudioEndpointInitialize *)

- ea: `0x140096ce4`
- end: `0x140096e62`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspCrossProcessAudioEndpointInitialize@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspCrossProcessAudioEndpointInitialize@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140097f40`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x140096ce4`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140096d82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140096d82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140096e0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140096e0d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140096e18`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140096e18`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspCrossProcessAudioEndpointInitialize>(
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

  *(_DWORD *)a2 = 14;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 28;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)word_1400D2E1A,
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
        (unsigned int)byte_1400D2F33,
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
  if ( *(_DWORD *)a2 != 14 )
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
0x140096ce4  mov     [rsp+arg_10], rbx
0x140096ce9  push    rbp
0x140096cea  push    rsi
0x140096ceb  push    rdi
0x140096cec  sub     rsp, 30h
0x140096cf0  mov     dword ptr [rdx], 0Eh
0x140096cf6  mov     ebp, 1Ch
0x140096cfb  mov     rax, [rcx+28h]
0x140096cff  mov     rbx, rdx
0x140096d02  mov     [rdx+8], rax
0x140096d06  mov     rdi, rcx
0x140096d09  mov     [rdx+10h], ebp
0x140096d0c  mov     r8, [rcx+10h]
0x140096d10  mov     eax, [r8]
0x140096d13  cmp     eax, 5
0x140096d16  jbe     short loc_140096D48
0x140096d18  mov     edx, 100000h
0x140096d1d  mov     rcx, r8
0x140096d20  call    _tlgKeywordOn
0x140096d25  test    al, al
0x140096d27  jz      short loc_140096D48
0x140096d29  mov     eax, [rbx]
0x140096d2b  lea     rdx, word_1400D2E1A
0x140096d32  mov     [rsp+48h+arg_0], eax
0x140096d36  mov     rcx, r8
0x140096d39  lea     rax, [rsp+48h+arg_0]
0x140096d3e  mov     qword ptr [rsp+48h+var_28], rax
0x140096d43  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140096d48  mov     rcx, [rdi+20h]
0x140096d4c  mov     r8, rbp
0x140096d4f  mov     rdx, rbx
0x140096d52  mov     rax, [rcx]
0x140096d55  mov     rax, [rax+18h]
0x140096d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096d5e  test    eax, eax
0x140096d60  jns     loc_140096E1E
0x140096d66  mov     rsi, [rdi+10h]
0x140096d6a  mov     eax, [rsi]
0x140096d6c  cmp     eax, 2
0x140096d6f  jbe     short loc_140096DC9
0x140096d71  mov     edx, 100000h
0x140096d76  mov     rcx, rsi
0x140096d79  call    _tlgKeywordOn
0x140096d7e  test    al, al
0x140096d80  jz      short loc_140096DC9
0x140096d82  call    cs:__imp_GetCurrentProcessId
0x140096d88  mov     rcx, [rdi+20h]
0x140096d8c  mov     r8, rbp
0x140096d8f  mov     [rsp+48h+arg_0], eax
0x140096d93  mov     rdx, rbx
0x140096d96  mov     rax, [rcx]
0x140096d99  mov     rax, [rax+18h]
0x140096d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096da2  mov     [rsp+48h+arg_8], eax
0x140096da6  lea     rdx, byte_1400D2F33
0x140096dad  lea     rax, [rsp+48h+arg_0]
0x140096db2  mov     rcx, rsi
0x140096db5  mov     [rsp+48h+var_20], rax
0x140096dba  lea     rax, [rsp+48h+arg_8]
0x140096dbf  mov     qword ptr [rsp+48h+var_28], rax; int
0x140096dc4  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140096dc9  mov     rcx, [rdi+20h]
0x140096dcd  mov     r8, rbp
0x140096dd0  mov     rdx, rbx
0x140096dd3  mov     rax, [rcx]
0x140096dd6  mov     rax, [rax+18h]
0x140096dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096ddf  mov     rcx, [rdi+20h]
0x140096de3  and     eax, 1FFF0000h
0x140096de8  cmp     eax, 70000h
0x140096ded  mov     r8, rbp
0x140096df0  mov     rdx, rbx
0x140096df3  mov     r9, [rcx]
0x140096df6  mov     rax, [r9+18h]
0x140096dfa  jnz     short loc_140096E06
0x140096dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096e01  movzx   edi, ax
0x140096e04  jmp     short loc_140096E0D
0x140096e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096e0b  mov     edi, eax
0x140096e0d  call    cs:__imp_GetCurrentProcess
0x140096e13  mov     rcx, rax; hProcess
0x140096e16  mov     edx, edi; uExitCode
0x140096e18  call    cs:__imp_TerminateProcess
0x140096e1e  cmp     dword ptr [rbx], 0Eh
0x140096e21  jz      short loc_140096E45
0x140096e23  mov     ebx, 80070057h
0x140096e28  mov     edx, 64h ; 'd'; void *
0x140096e2d  mov     rcx, [rsp+48h]; this
0x140096e32  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140096e39  mov     r9d, ebx; char *
0x140096e3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140096e41  mov     eax, ebx
0x140096e43  jmp     short loc_140096E55
0x140096e45  mov     ebx, [rbx+4]
0x140096e48  test    ebx, ebx
0x140096e4a  jns     short loc_140096E53
0x140096e4c  mov     edx, 65h ; 'e'
0x140096e51  jmp     short loc_140096E2D
0x140096e53  xor     eax, eax
0x140096e55  mov     rbx, [rsp+48h+arg_10]
0x140096e5a  add     rsp, 30h
0x140096e5e  pop     rdi
0x140096e5f  pop     rsi
0x140096e60  pop     rbp
0x140096e61  retn
```
