# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspAudioProcessorUpdateGraph>(AudioDg_Command_DspAudioProcessorUpdateGraph *)

- ea: `0x14009ae04`
- end: `0x14009af82`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspAudioProcessorUpdateGraph@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspAudioProcessorUpdateGraph@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14009b100`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14009ae04`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009aea2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009aea2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009af2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009af2d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009af38`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009af38`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspAudioProcessorUpdateGraph>(
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

  *(_DWORD *)a2 = 21;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 36;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_1400D38B5,
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
        (unsigned int)&word_1400D387E,
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
  if ( *(_DWORD *)a2 != 21 )
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
0x14009ae04  mov     [rsp+arg_10], rbx
0x14009ae09  push    rbp
0x14009ae0a  push    rsi
0x14009ae0b  push    rdi
0x14009ae0c  sub     rsp, 30h
0x14009ae10  mov     dword ptr [rdx], 15h
0x14009ae16  mov     ebp, 24h ; '$'
0x14009ae1b  mov     rax, [rcx+28h]
0x14009ae1f  mov     rbx, rdx
0x14009ae22  mov     [rdx+8], rax
0x14009ae26  mov     rdi, rcx
0x14009ae29  mov     [rdx+10h], ebp
0x14009ae2c  mov     r8, [rcx+10h]
0x14009ae30  mov     eax, [r8]
0x14009ae33  cmp     eax, 5
0x14009ae36  jbe     short loc_14009AE68
0x14009ae38  mov     edx, 100000h
0x14009ae3d  mov     rcx, r8
0x14009ae40  call    _tlgKeywordOn
0x14009ae45  test    al, al
0x14009ae47  jz      short loc_14009AE68
0x14009ae49  mov     eax, [rbx]
0x14009ae4b  lea     rdx, byte_1400D38B5
0x14009ae52  mov     [rsp+48h+arg_0], eax
0x14009ae56  mov     rcx, r8
0x14009ae59  lea     rax, [rsp+48h+arg_0]
0x14009ae5e  mov     qword ptr [rsp+48h+var_28], rax
0x14009ae63  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x14009ae68  mov     rcx, [rdi+20h]
0x14009ae6c  mov     r8, rbp
0x14009ae6f  mov     rdx, rbx
0x14009ae72  mov     rax, [rcx]
0x14009ae75  mov     rax, [rax+18h]
0x14009ae79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009ae7e  test    eax, eax
0x14009ae80  jns     loc_14009AF3E
0x14009ae86  mov     rsi, [rdi+10h]
0x14009ae8a  mov     eax, [rsi]
0x14009ae8c  cmp     eax, 2
0x14009ae8f  jbe     short loc_14009AEE9
0x14009ae91  mov     edx, 100000h
0x14009ae96  mov     rcx, rsi
0x14009ae99  call    _tlgKeywordOn
0x14009ae9e  test    al, al
0x14009aea0  jz      short loc_14009AEE9
0x14009aea2  call    cs:__imp_GetCurrentProcessId
0x14009aea8  mov     rcx, [rdi+20h]
0x14009aeac  mov     r8, rbp
0x14009aeaf  mov     [rsp+48h+arg_0], eax
0x14009aeb3  mov     rdx, rbx
0x14009aeb6  mov     rax, [rcx]
0x14009aeb9  mov     rax, [rax+18h]
0x14009aebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009aec2  mov     [rsp+48h+arg_8], eax
0x14009aec6  lea     rdx, word_1400D387E
0x14009aecd  lea     rax, [rsp+48h+arg_0]
0x14009aed2  mov     rcx, rsi
0x14009aed5  mov     [rsp+48h+var_20], rax
0x14009aeda  lea     rax, [rsp+48h+arg_8]
0x14009aedf  mov     qword ptr [rsp+48h+var_28], rax; int
0x14009aee4  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14009aee9  mov     rcx, [rdi+20h]
0x14009aeed  mov     r8, rbp
0x14009aef0  mov     rdx, rbx
0x14009aef3  mov     rax, [rcx]
0x14009aef6  mov     rax, [rax+18h]
0x14009aefa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009aeff  mov     rcx, [rdi+20h]
0x14009af03  and     eax, 1FFF0000h
0x14009af08  cmp     eax, 70000h
0x14009af0d  mov     r8, rbp
0x14009af10  mov     rdx, rbx
0x14009af13  mov     r9, [rcx]
0x14009af16  mov     rax, [r9+18h]
0x14009af1a  jnz     short loc_14009AF26
0x14009af1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009af21  movzx   edi, ax
0x14009af24  jmp     short loc_14009AF2D
0x14009af26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009af2b  mov     edi, eax
0x14009af2d  call    cs:__imp_GetCurrentProcess
0x14009af33  mov     rcx, rax; hProcess
0x14009af36  mov     edx, edi; uExitCode
0x14009af38  call    cs:__imp_TerminateProcess
0x14009af3e  cmp     dword ptr [rbx], 15h
0x14009af41  jz      short loc_14009AF65
0x14009af43  mov     ebx, 80070057h
0x14009af48  mov     edx, 64h ; 'd'; void *
0x14009af4d  mov     rcx, [rsp+48h]; this
0x14009af52  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14009af59  mov     r9d, ebx; char *
0x14009af5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009af61  mov     eax, ebx
0x14009af63  jmp     short loc_14009AF75
0x14009af65  mov     ebx, [rbx+4]
0x14009af68  test    ebx, ebx
0x14009af6a  jns     short loc_14009AF73
0x14009af6c  mov     edx, 65h ; 'e'
0x14009af71  jmp     short loc_14009AF4D
0x14009af73  xor     eax, eax
0x14009af75  mov     rbx, [rsp+48h+arg_10]
0x14009af7a  add     rsp, 30h
0x14009af7e  pop     rdi
0x14009af7f  pop     rsi
0x14009af80  pop     rbp
0x14009af81  retn
```
