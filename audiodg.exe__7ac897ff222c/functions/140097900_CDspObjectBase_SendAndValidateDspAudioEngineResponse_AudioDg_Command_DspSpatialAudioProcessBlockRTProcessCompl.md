# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspSpatialAudioProcessBlockRTProcessComplete>(AudioDg_Command_DspSpatialAudioProcessBlockRTProcessComplete *)

- ea: `0x140097900`
- end: `0x140097a7e`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspSpatialAudioProcessBlockRTProcessComplete@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspSpatialAudioProcessBlockRTProcessComplete@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140098390`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x140097900`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009799e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009799e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140097a29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140097a29`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140097a34`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140097a34`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspSpatialAudioProcessBlockRTProcessComplete>(
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

  *(_DWORD *)a2 = 23;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 24;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_1400D32BD,
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
        (unsigned int)&word_1400D3286,
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
  if ( *(_DWORD *)a2 != 23 )
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
0x140097900  mov     [rsp+arg_10], rbx
0x140097905  push    rbp
0x140097906  push    rsi
0x140097907  push    rdi
0x140097908  sub     rsp, 30h
0x14009790c  mov     dword ptr [rdx], 17h
0x140097912  mov     ebp, 18h
0x140097917  mov     rax, [rcx+28h]
0x14009791b  mov     rbx, rdx
0x14009791e  mov     [rdx+8], rax
0x140097922  mov     rdi, rcx
0x140097925  mov     [rdx+10h], ebp
0x140097928  mov     r8, [rcx+10h]
0x14009792c  mov     eax, [r8]
0x14009792f  cmp     eax, 5
0x140097932  jbe     short loc_140097964
0x140097934  mov     edx, 100000h
0x140097939  mov     rcx, r8
0x14009793c  call    _tlgKeywordOn
0x140097941  test    al, al
0x140097943  jz      short loc_140097964
0x140097945  mov     eax, [rbx]
0x140097947  lea     rdx, byte_1400D32BD
0x14009794e  mov     [rsp+48h+arg_0], eax
0x140097952  mov     rcx, r8
0x140097955  lea     rax, [rsp+48h+arg_0]
0x14009795a  mov     qword ptr [rsp+48h+var_28], rax
0x14009795f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140097964  mov     rcx, [rdi+20h]
0x140097968  mov     r8, rbp
0x14009796b  mov     rdx, rbx
0x14009796e  mov     rax, [rcx]
0x140097971  mov     rax, [rax+18h]
0x140097975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009797a  test    eax, eax
0x14009797c  jns     loc_140097A3A
0x140097982  mov     rsi, [rdi+10h]
0x140097986  mov     eax, [rsi]
0x140097988  cmp     eax, 2
0x14009798b  jbe     short loc_1400979E5
0x14009798d  mov     edx, 100000h
0x140097992  mov     rcx, rsi
0x140097995  call    _tlgKeywordOn
0x14009799a  test    al, al
0x14009799c  jz      short loc_1400979E5
0x14009799e  call    cs:__imp_GetCurrentProcessId
0x1400979a4  mov     rcx, [rdi+20h]
0x1400979a8  mov     r8, rbp
0x1400979ab  mov     [rsp+48h+arg_0], eax
0x1400979af  mov     rdx, rbx
0x1400979b2  mov     rax, [rcx]
0x1400979b5  mov     rax, [rax+18h]
0x1400979b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400979be  mov     [rsp+48h+arg_8], eax
0x1400979c2  lea     rdx, word_1400D3286
0x1400979c9  lea     rax, [rsp+48h+arg_0]
0x1400979ce  mov     rcx, rsi
0x1400979d1  mov     [rsp+48h+var_20], rax
0x1400979d6  lea     rax, [rsp+48h+arg_8]
0x1400979db  mov     qword ptr [rsp+48h+var_28], rax; int
0x1400979e0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400979e5  mov     rcx, [rdi+20h]
0x1400979e9  mov     r8, rbp
0x1400979ec  mov     rdx, rbx
0x1400979ef  mov     rax, [rcx]
0x1400979f2  mov     rax, [rax+18h]
0x1400979f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400979fb  mov     rcx, [rdi+20h]
0x1400979ff  and     eax, 1FFF0000h
0x140097a04  cmp     eax, 70000h
0x140097a09  mov     r8, rbp
0x140097a0c  mov     rdx, rbx
0x140097a0f  mov     r9, [rcx]
0x140097a12  mov     rax, [r9+18h]
0x140097a16  jnz     short loc_140097A22
0x140097a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097a1d  movzx   edi, ax
0x140097a20  jmp     short loc_140097A29
0x140097a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097a27  mov     edi, eax
0x140097a29  call    cs:__imp_GetCurrentProcess
0x140097a2f  mov     rcx, rax; hProcess
0x140097a32  mov     edx, edi; uExitCode
0x140097a34  call    cs:__imp_TerminateProcess
0x140097a3a  cmp     dword ptr [rbx], 17h
0x140097a3d  jz      short loc_140097A61
0x140097a3f  mov     ebx, 80070057h
0x140097a44  mov     edx, 64h ; 'd'; void *
0x140097a49  mov     rcx, [rsp+48h]; this
0x140097a4e  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140097a55  mov     r9d, ebx; char *
0x140097a58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140097a5d  mov     eax, ebx
0x140097a5f  jmp     short loc_140097A71
0x140097a61  mov     ebx, [rbx+4]
0x140097a64  test    ebx, ebx
0x140097a66  jns     short loc_140097A6F
0x140097a68  mov     edx, 65h ; 'e'
0x140097a6d  jmp     short loc_140097A49
0x140097a6f  xor     eax, eax
0x140097a71  mov     rbx, [rsp+48h+arg_10]
0x140097a76  add     rsp, 30h
0x140097a7a  pop     rdi
0x140097a7b  pop     rsi
0x140097a7c  pop     rbp
0x140097a7d  retn
```
