# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspBridgeSourceEndpointAddConsumer>(AudioDg_Command_DspBridgeSourceEndpointAddConsumer *)

- ea: `0x140099368`
- end: `0x1400994e6`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspBridgeSourceEndpointAddConsumer@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspBridgeSourceEndpointAddConsumer@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140099630`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x140099368`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140099406`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140099406`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140099491`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140099491`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009949c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009949c`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspBridgeSourceEndpointAddConsumer>(
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

  *(_DWORD *)a2 = 29;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 32;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_1400D3599,
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
        (unsigned int)word_1400D3562,
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
  if ( *(_DWORD *)a2 != 29 )
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
0x140099368  mov     [rsp+arg_10], rbx
0x14009936d  push    rbp
0x14009936e  push    rsi
0x14009936f  push    rdi
0x140099370  sub     rsp, 30h
0x140099374  mov     dword ptr [rdx], 1Dh
0x14009937a  mov     ebp, 20h ; ' '
0x14009937f  mov     rax, [rcx+28h]
0x140099383  mov     rbx, rdx
0x140099386  mov     [rdx+8], rax
0x14009938a  mov     rdi, rcx
0x14009938d  mov     [rdx+10h], ebp
0x140099390  mov     r8, [rcx+10h]
0x140099394  mov     eax, [r8]
0x140099397  cmp     eax, 5
0x14009939a  jbe     short loc_1400993CC
0x14009939c  mov     edx, 100000h
0x1400993a1  mov     rcx, r8
0x1400993a4  call    _tlgKeywordOn
0x1400993a9  test    al, al
0x1400993ab  jz      short loc_1400993CC
0x1400993ad  mov     eax, [rbx]
0x1400993af  lea     rdx, byte_1400D3599
0x1400993b6  mov     [rsp+48h+arg_0], eax
0x1400993ba  mov     rcx, r8
0x1400993bd  lea     rax, [rsp+48h+arg_0]
0x1400993c2  mov     qword ptr [rsp+48h+var_28], rax
0x1400993c7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1400993cc  mov     rcx, [rdi+20h]
0x1400993d0  mov     r8, rbp
0x1400993d3  mov     rdx, rbx
0x1400993d6  mov     rax, [rcx]
0x1400993d9  mov     rax, [rax+18h]
0x1400993dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400993e2  test    eax, eax
0x1400993e4  jns     loc_1400994A2
0x1400993ea  mov     rsi, [rdi+10h]
0x1400993ee  mov     eax, [rsi]
0x1400993f0  cmp     eax, 2
0x1400993f3  jbe     short loc_14009944D
0x1400993f5  mov     edx, 100000h
0x1400993fa  mov     rcx, rsi
0x1400993fd  call    _tlgKeywordOn
0x140099402  test    al, al
0x140099404  jz      short loc_14009944D
0x140099406  call    cs:__imp_GetCurrentProcessId
0x14009940c  mov     rcx, [rdi+20h]
0x140099410  mov     r8, rbp
0x140099413  mov     [rsp+48h+arg_0], eax
0x140099417  mov     rdx, rbx
0x14009941a  mov     rax, [rcx]
0x14009941d  mov     rax, [rax+18h]
0x140099421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140099426  mov     [rsp+48h+arg_8], eax
0x14009942a  lea     rdx, word_1400D3562
0x140099431  lea     rax, [rsp+48h+arg_0]
0x140099436  mov     rcx, rsi
0x140099439  mov     [rsp+48h+var_20], rax
0x14009943e  lea     rax, [rsp+48h+arg_8]
0x140099443  mov     qword ptr [rsp+48h+var_28], rax; int
0x140099448  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14009944d  mov     rcx, [rdi+20h]
0x140099451  mov     r8, rbp
0x140099454  mov     rdx, rbx
0x140099457  mov     rax, [rcx]
0x14009945a  mov     rax, [rax+18h]
0x14009945e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140099463  mov     rcx, [rdi+20h]
0x140099467  and     eax, 1FFF0000h
0x14009946c  cmp     eax, 70000h
0x140099471  mov     r8, rbp
0x140099474  mov     rdx, rbx
0x140099477  mov     r9, [rcx]
0x14009947a  mov     rax, [r9+18h]
0x14009947e  jnz     short loc_14009948A
0x140099480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140099485  movzx   edi, ax
0x140099488  jmp     short loc_140099491
0x14009948a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009948f  mov     edi, eax
0x140099491  call    cs:__imp_GetCurrentProcess
0x140099497  mov     rcx, rax; hProcess
0x14009949a  mov     edx, edi; uExitCode
0x14009949c  call    cs:__imp_TerminateProcess
0x1400994a2  cmp     dword ptr [rbx], 1Dh
0x1400994a5  jz      short loc_1400994C9
0x1400994a7  mov     ebx, 80070057h
0x1400994ac  mov     edx, 64h ; 'd'; void *
0x1400994b1  mov     rcx, [rsp+48h]; this
0x1400994b6  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x1400994bd  mov     r9d, ebx; char *
0x1400994c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400994c5  mov     eax, ebx
0x1400994c7  jmp     short loc_1400994D9
0x1400994c9  mov     ebx, [rbx+4]
0x1400994cc  test    ebx, ebx
0x1400994ce  jns     short loc_1400994D7
0x1400994d0  mov     edx, 65h ; 'e'
0x1400994d5  jmp     short loc_1400994B1
0x1400994d7  xor     eax, eax
0x1400994d9  mov     rbx, [rsp+48h+arg_10]
0x1400994de  add     rsp, 30h
0x1400994e2  pop     rdi
0x1400994e3  pop     rsi
0x1400994e4  pop     rbp
0x1400994e5  retn
```
