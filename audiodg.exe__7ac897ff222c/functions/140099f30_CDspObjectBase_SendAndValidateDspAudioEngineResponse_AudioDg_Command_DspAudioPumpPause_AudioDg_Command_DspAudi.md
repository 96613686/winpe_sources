# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspAudioPumpPause>(AudioDg_Command_DspAudioPumpPause *)

- ea: `0x140099f30`
- end: `0x14009a0ae`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspAudioPumpPause@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspAudioPumpPause@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14009a6c0`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x140099f30`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140099fce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140099fce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009a059`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009a059`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009a064`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009a064`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspAudioPumpPause>(
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

  *(_DWORD *)a2 = 19;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 24;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_1400D3759,
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
        (unsigned int)word_1400D3722,
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
  if ( *(_DWORD *)a2 != 19 )
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
0x140099f30  mov     [rsp+arg_10], rbx
0x140099f35  push    rbp
0x140099f36  push    rsi
0x140099f37  push    rdi
0x140099f38  sub     rsp, 30h
0x140099f3c  mov     dword ptr [rdx], 13h
0x140099f42  mov     ebp, 18h
0x140099f47  mov     rax, [rcx+28h]
0x140099f4b  mov     rbx, rdx
0x140099f4e  mov     [rdx+8], rax
0x140099f52  mov     rdi, rcx
0x140099f55  mov     [rdx+10h], ebp
0x140099f58  mov     r8, [rcx+10h]
0x140099f5c  mov     eax, [r8]
0x140099f5f  cmp     eax, 5
0x140099f62  jbe     short loc_140099F94
0x140099f64  mov     edx, 100000h
0x140099f69  mov     rcx, r8
0x140099f6c  call    _tlgKeywordOn
0x140099f71  test    al, al
0x140099f73  jz      short loc_140099F94
0x140099f75  mov     eax, [rbx]
0x140099f77  lea     rdx, byte_1400D3759
0x140099f7e  mov     [rsp+48h+arg_0], eax
0x140099f82  mov     rcx, r8
0x140099f85  lea     rax, [rsp+48h+arg_0]
0x140099f8a  mov     qword ptr [rsp+48h+var_28], rax
0x140099f8f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140099f94  mov     rcx, [rdi+20h]
0x140099f98  mov     r8, rbp
0x140099f9b  mov     rdx, rbx
0x140099f9e  mov     rax, [rcx]
0x140099fa1  mov     rax, [rax+18h]
0x140099fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140099faa  test    eax, eax
0x140099fac  jns     loc_14009A06A
0x140099fb2  mov     rsi, [rdi+10h]
0x140099fb6  mov     eax, [rsi]
0x140099fb8  cmp     eax, 2
0x140099fbb  jbe     short loc_14009A015
0x140099fbd  mov     edx, 100000h
0x140099fc2  mov     rcx, rsi
0x140099fc5  call    _tlgKeywordOn
0x140099fca  test    al, al
0x140099fcc  jz      short loc_14009A015
0x140099fce  call    cs:__imp_GetCurrentProcessId
0x140099fd4  mov     rcx, [rdi+20h]
0x140099fd8  mov     r8, rbp
0x140099fdb  mov     [rsp+48h+arg_0], eax
0x140099fdf  mov     rdx, rbx
0x140099fe2  mov     rax, [rcx]
0x140099fe5  mov     rax, [rax+18h]
0x140099fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140099fee  mov     [rsp+48h+arg_8], eax
0x140099ff2  lea     rdx, word_1400D3722
0x140099ff9  lea     rax, [rsp+48h+arg_0]
0x140099ffe  mov     rcx, rsi
0x14009a001  mov     [rsp+48h+var_20], rax
0x14009a006  lea     rax, [rsp+48h+arg_8]
0x14009a00b  mov     qword ptr [rsp+48h+var_28], rax; int
0x14009a010  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14009a015  mov     rcx, [rdi+20h]
0x14009a019  mov     r8, rbp
0x14009a01c  mov     rdx, rbx
0x14009a01f  mov     rax, [rcx]
0x14009a022  mov     rax, [rax+18h]
0x14009a026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a02b  mov     rcx, [rdi+20h]
0x14009a02f  and     eax, 1FFF0000h
0x14009a034  cmp     eax, 70000h
0x14009a039  mov     r8, rbp
0x14009a03c  mov     rdx, rbx
0x14009a03f  mov     r9, [rcx]
0x14009a042  mov     rax, [r9+18h]
0x14009a046  jnz     short loc_14009A052
0x14009a048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a04d  movzx   edi, ax
0x14009a050  jmp     short loc_14009A059
0x14009a052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009a057  mov     edi, eax
0x14009a059  call    cs:__imp_GetCurrentProcess
0x14009a05f  mov     rcx, rax; hProcess
0x14009a062  mov     edx, edi; uExitCode
0x14009a064  call    cs:__imp_TerminateProcess
0x14009a06a  cmp     dword ptr [rbx], 13h
0x14009a06d  jz      short loc_14009A091
0x14009a06f  mov     ebx, 80070057h
0x14009a074  mov     edx, 64h ; 'd'; void *
0x14009a079  mov     rcx, [rsp+48h]; this
0x14009a07e  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14009a085  mov     r9d, ebx; char *
0x14009a088  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009a08d  mov     eax, ebx
0x14009a08f  jmp     short loc_14009A0A1
0x14009a091  mov     ebx, [rbx+4]
0x14009a094  test    ebx, ebx
0x14009a096  jns     short loc_14009A09F
0x14009a098  mov     edx, 65h ; 'e'
0x14009a09d  jmp     short loc_14009A079
0x14009a09f  xor     eax, eax
0x14009a0a1  mov     rbx, [rsp+48h+arg_10]
0x14009a0a6  add     rsp, 30h
0x14009a0aa  pop     rdi
0x14009a0ab  pop     rsi
0x14009a0ac  pop     rbp
0x14009a0ad  retn
```
