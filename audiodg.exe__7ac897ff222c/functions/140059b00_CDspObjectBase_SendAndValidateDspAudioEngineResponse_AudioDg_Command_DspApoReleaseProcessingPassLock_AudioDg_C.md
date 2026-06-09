# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspApoReleaseProcessingPassLock>(AudioDg_Command_DspApoReleaseProcessingPassLock *)

- ea: `0x140059b00`
- end: `0x140059c7e`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspApoReleaseProcessingPassLock@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspApoReleaseProcessingPassLock@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140059a9c`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x140059b00`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140059b9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140059b9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140059c29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140059c29`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140059c34`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140059c34`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspApoReleaseProcessingPassLock>(
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

  *(_DWORD *)a2 = 12;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 24;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)&word_1400D2A76,
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
        (unsigned int)&byte_1400D2A3F,
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
  if ( *(_DWORD *)a2 != 12 )
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
0x140059b00  mov     [rsp+arg_10], rbx
0x140059b05  push    rbp
0x140059b06  push    rsi
0x140059b07  push    rdi
0x140059b08  sub     rsp, 30h
0x140059b0c  mov     dword ptr [rdx], 0Ch
0x140059b12  mov     ebp, 18h
0x140059b17  mov     rax, [rcx+28h]
0x140059b1b  mov     rbx, rdx
0x140059b1e  mov     [rdx+8], rax
0x140059b22  mov     rdi, rcx
0x140059b25  mov     [rdx+10h], ebp
0x140059b28  mov     r8, [rcx+10h]
0x140059b2c  mov     eax, [r8]
0x140059b2f  cmp     eax, 5
0x140059b32  jbe     short loc_140059B64
0x140059b34  mov     edx, 100000h
0x140059b39  mov     rcx, r8
0x140059b3c  call    _tlgKeywordOn
0x140059b41  test    al, al
0x140059b43  jz      short loc_140059B64
0x140059b45  mov     eax, [rbx]
0x140059b47  lea     rdx, word_1400D2A76
0x140059b4e  mov     [rsp+48h+arg_0], eax
0x140059b52  mov     rcx, r8
0x140059b55  lea     rax, [rsp+48h+arg_0]
0x140059b5a  mov     qword ptr [rsp+48h+var_28], rax
0x140059b5f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140059b64  mov     rcx, [rdi+20h]
0x140059b68  mov     r8, rbp
0x140059b6b  mov     rdx, rbx
0x140059b6e  mov     rax, [rcx]
0x140059b71  mov     rax, [rax+18h]
0x140059b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059b7a  test    eax, eax
0x140059b7c  jns     loc_140059C3A
0x140059b82  mov     rsi, [rdi+10h]
0x140059b86  mov     eax, [rsi]
0x140059b88  cmp     eax, 2
0x140059b8b  jbe     short loc_140059BE5
0x140059b8d  mov     edx, 100000h
0x140059b92  mov     rcx, rsi
0x140059b95  call    _tlgKeywordOn
0x140059b9a  test    al, al
0x140059b9c  jz      short loc_140059BE5
0x140059b9e  call    cs:__imp_GetCurrentProcessId
0x140059ba4  mov     rcx, [rdi+20h]
0x140059ba8  mov     r8, rbp
0x140059bab  mov     [rsp+48h+arg_0], eax
0x140059baf  mov     rdx, rbx
0x140059bb2  mov     rax, [rcx]
0x140059bb5  mov     rax, [rax+18h]
0x140059bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059bbe  mov     [rsp+48h+arg_8], eax
0x140059bc2  lea     rdx, byte_1400D2A3F
0x140059bc9  lea     rax, [rsp+48h+arg_0]
0x140059bce  mov     rcx, rsi
0x140059bd1  mov     [rsp+48h+var_20], rax
0x140059bd6  lea     rax, [rsp+48h+arg_8]
0x140059bdb  mov     qword ptr [rsp+48h+var_28], rax; int
0x140059be0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140059be5  mov     rcx, [rdi+20h]
0x140059be9  mov     r8, rbp
0x140059bec  mov     rdx, rbx
0x140059bef  mov     rax, [rcx]
0x140059bf2  mov     rax, [rax+18h]
0x140059bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059bfb  mov     rcx, [rdi+20h]
0x140059bff  and     eax, 1FFF0000h
0x140059c04  cmp     eax, 70000h
0x140059c09  mov     r8, rbp
0x140059c0c  mov     rdx, rbx
0x140059c0f  mov     r9, [rcx]
0x140059c12  mov     rax, [r9+18h]
0x140059c16  jnz     short loc_140059C22
0x140059c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059c1d  movzx   edi, ax
0x140059c20  jmp     short loc_140059C29
0x140059c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059c27  mov     edi, eax
0x140059c29  call    cs:__imp_GetCurrentProcess
0x140059c2f  mov     rcx, rax; hProcess
0x140059c32  mov     edx, edi; uExitCode
0x140059c34  call    cs:__imp_TerminateProcess
0x140059c3a  cmp     dword ptr [rbx], 0Ch
0x140059c3d  jz      short loc_140059C61
0x140059c3f  mov     ebx, 80070057h
0x140059c44  mov     edx, 64h ; 'd'; void *
0x140059c49  mov     rcx, [rsp+48h]; this
0x140059c4e  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140059c55  mov     r9d, ebx; char *
0x140059c58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140059c5d  mov     eax, ebx
0x140059c5f  jmp     short loc_140059C71
0x140059c61  mov     ebx, [rbx+4]
0x140059c64  test    ebx, ebx
0x140059c66  jns     short loc_140059C6F
0x140059c68  mov     edx, 65h ; 'e'
0x140059c6d  jmp     short loc_140059C49
0x140059c6f  xor     eax, eax
0x140059c71  mov     rbx, [rsp+48h+arg_10]
0x140059c76  add     rsp, 30h
0x140059c7a  pop     rdi
0x140059c7b  pop     rsi
0x140059c7c  pop     rbp
0x140059c7d  retn
```
