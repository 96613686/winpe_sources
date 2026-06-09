# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspCrossProcessAudioEndpointRegisterInterruptId>(AudioDg_Command_DspCrossProcessAudioEndpointRegisterInterruptId *)

- ea: `0x140096e68`
- end: `0x140096fe6`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspCrossProcessAudioEndpointRegisterInterruptId@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspCrossProcessAudioEndpointRegisterInterruptId@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140098470`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x140096e68`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140096f06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140096f06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140096f91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140096f91`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140096f9c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140096f9c`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspCrossProcessAudioEndpointRegisterInterruptId>(
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

  *(_DWORD *)a2 = 15;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 28;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)word_1400D2EFA,
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
        (unsigned int)byte_1400D2EC3,
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
  if ( *(_DWORD *)a2 != 15 )
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
0x140096e68  mov     [rsp+arg_10], rbx
0x140096e6d  push    rbp
0x140096e6e  push    rsi
0x140096e6f  push    rdi
0x140096e70  sub     rsp, 30h
0x140096e74  mov     dword ptr [rdx], 0Fh
0x140096e7a  mov     ebp, 1Ch
0x140096e7f  mov     rax, [rcx+28h]
0x140096e83  mov     rbx, rdx
0x140096e86  mov     [rdx+8], rax
0x140096e8a  mov     rdi, rcx
0x140096e8d  mov     [rdx+10h], ebp
0x140096e90  mov     r8, [rcx+10h]
0x140096e94  mov     eax, [r8]
0x140096e97  cmp     eax, 5
0x140096e9a  jbe     short loc_140096ECC
0x140096e9c  mov     edx, 100000h
0x140096ea1  mov     rcx, r8
0x140096ea4  call    _tlgKeywordOn
0x140096ea9  test    al, al
0x140096eab  jz      short loc_140096ECC
0x140096ead  mov     eax, [rbx]
0x140096eaf  lea     rdx, word_1400D2EFA
0x140096eb6  mov     [rsp+48h+arg_0], eax
0x140096eba  mov     rcx, r8
0x140096ebd  lea     rax, [rsp+48h+arg_0]
0x140096ec2  mov     qword ptr [rsp+48h+var_28], rax
0x140096ec7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140096ecc  mov     rcx, [rdi+20h]
0x140096ed0  mov     r8, rbp
0x140096ed3  mov     rdx, rbx
0x140096ed6  mov     rax, [rcx]
0x140096ed9  mov     rax, [rax+18h]
0x140096edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096ee2  test    eax, eax
0x140096ee4  jns     loc_140096FA2
0x140096eea  mov     rsi, [rdi+10h]
0x140096eee  mov     eax, [rsi]
0x140096ef0  cmp     eax, 2
0x140096ef3  jbe     short loc_140096F4D
0x140096ef5  mov     edx, 100000h
0x140096efa  mov     rcx, rsi
0x140096efd  call    _tlgKeywordOn
0x140096f02  test    al, al
0x140096f04  jz      short loc_140096F4D
0x140096f06  call    cs:__imp_GetCurrentProcessId
0x140096f0c  mov     rcx, [rdi+20h]
0x140096f10  mov     r8, rbp
0x140096f13  mov     [rsp+48h+arg_0], eax
0x140096f17  mov     rdx, rbx
0x140096f1a  mov     rax, [rcx]
0x140096f1d  mov     rax, [rax+18h]
0x140096f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096f26  mov     [rsp+48h+arg_8], eax
0x140096f2a  lea     rdx, byte_1400D2EC3
0x140096f31  lea     rax, [rsp+48h+arg_0]
0x140096f36  mov     rcx, rsi
0x140096f39  mov     [rsp+48h+var_20], rax
0x140096f3e  lea     rax, [rsp+48h+arg_8]
0x140096f43  mov     qword ptr [rsp+48h+var_28], rax; int
0x140096f48  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140096f4d  mov     rcx, [rdi+20h]
0x140096f51  mov     r8, rbp
0x140096f54  mov     rdx, rbx
0x140096f57  mov     rax, [rcx]
0x140096f5a  mov     rax, [rax+18h]
0x140096f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096f63  mov     rcx, [rdi+20h]
0x140096f67  and     eax, 1FFF0000h
0x140096f6c  cmp     eax, 70000h
0x140096f71  mov     r8, rbp
0x140096f74  mov     rdx, rbx
0x140096f77  mov     r9, [rcx]
0x140096f7a  mov     rax, [r9+18h]
0x140096f7e  jnz     short loc_140096F8A
0x140096f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096f85  movzx   edi, ax
0x140096f88  jmp     short loc_140096F91
0x140096f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096f8f  mov     edi, eax
0x140096f91  call    cs:__imp_GetCurrentProcess
0x140096f97  mov     rcx, rax; hProcess
0x140096f9a  mov     edx, edi; uExitCode
0x140096f9c  call    cs:__imp_TerminateProcess
0x140096fa2  cmp     dword ptr [rbx], 0Fh
0x140096fa5  jz      short loc_140096FC9
0x140096fa7  mov     ebx, 80070057h
0x140096fac  mov     edx, 64h ; 'd'; void *
0x140096fb1  mov     rcx, [rsp+48h]; this
0x140096fb6  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140096fbd  mov     r9d, ebx; char *
0x140096fc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140096fc5  mov     eax, ebx
0x140096fc7  jmp     short loc_140096FD9
0x140096fc9  mov     ebx, [rbx+4]
0x140096fcc  test    ebx, ebx
0x140096fce  jns     short loc_140096FD7
0x140096fd0  mov     edx, 65h ; 'e'
0x140096fd5  jmp     short loc_140096FB1
0x140096fd7  xor     eax, eax
0x140096fd9  mov     rbx, [rsp+48h+arg_10]
0x140096fde  add     rsp, 30h
0x140096fe2  pop     rdi
0x140096fe3  pop     rsi
0x140096fe4  pop     rbp
0x140096fe5  retn
```
