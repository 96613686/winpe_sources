# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspSpatialAudioProcessBlockRTGetStreamIdentifier>(AudioDg_Command_DspSpatialAudioProcessBlockRTGetStreamIdentifier *)

- ea: `0x1400975f8`
- end: `0x140097776`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspSpatialAudioProcessBlockRTGetStreamIdentifier@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspSpatialAudioProcessBlockRTGetStreamIdentifier@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140098230`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x1400975f8`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140097696`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140097696`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140097721`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140097721`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009772c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009772c`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspSpatialAudioProcessBlockRTGetStreamIdentifier>(
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

  *(_DWORD *)a2 = 27;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 32;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)&dword_1400D31A4,
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
        (unsigned int)byte_1400D316D,
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
  if ( *(_DWORD *)a2 != 27 )
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
0x1400975f8  mov     [rsp+arg_10], rbx
0x1400975fd  push    rbp
0x1400975fe  push    rsi
0x1400975ff  push    rdi
0x140097600  sub     rsp, 30h
0x140097604  mov     dword ptr [rdx], 1Bh
0x14009760a  mov     ebp, 20h ; ' '
0x14009760f  mov     rax, [rcx+28h]
0x140097613  mov     rbx, rdx
0x140097616  mov     [rdx+8], rax
0x14009761a  mov     rdi, rcx
0x14009761d  mov     [rdx+10h], ebp
0x140097620  mov     r8, [rcx+10h]
0x140097624  mov     eax, [r8]
0x140097627  cmp     eax, 5
0x14009762a  jbe     short loc_14009765C
0x14009762c  mov     edx, 100000h
0x140097631  mov     rcx, r8
0x140097634  call    _tlgKeywordOn
0x140097639  test    al, al
0x14009763b  jz      short loc_14009765C
0x14009763d  mov     eax, [rbx]
0x14009763f  lea     rdx, dword_1400D31A4
0x140097646  mov     [rsp+48h+arg_0], eax
0x14009764a  mov     rcx, r8
0x14009764d  lea     rax, [rsp+48h+arg_0]
0x140097652  mov     qword ptr [rsp+48h+var_28], rax
0x140097657  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x14009765c  mov     rcx, [rdi+20h]
0x140097660  mov     r8, rbp
0x140097663  mov     rdx, rbx
0x140097666  mov     rax, [rcx]
0x140097669  mov     rax, [rax+18h]
0x14009766d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097672  test    eax, eax
0x140097674  jns     loc_140097732
0x14009767a  mov     rsi, [rdi+10h]
0x14009767e  mov     eax, [rsi]
0x140097680  cmp     eax, 2
0x140097683  jbe     short loc_1400976DD
0x140097685  mov     edx, 100000h
0x14009768a  mov     rcx, rsi
0x14009768d  call    _tlgKeywordOn
0x140097692  test    al, al
0x140097694  jz      short loc_1400976DD
0x140097696  call    cs:__imp_GetCurrentProcessId
0x14009769c  mov     rcx, [rdi+20h]
0x1400976a0  mov     r8, rbp
0x1400976a3  mov     [rsp+48h+arg_0], eax
0x1400976a7  mov     rdx, rbx
0x1400976aa  mov     rax, [rcx]
0x1400976ad  mov     rax, [rax+18h]
0x1400976b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400976b6  mov     [rsp+48h+arg_8], eax
0x1400976ba  lea     rdx, byte_1400D316D
0x1400976c1  lea     rax, [rsp+48h+arg_0]
0x1400976c6  mov     rcx, rsi
0x1400976c9  mov     [rsp+48h+var_20], rax
0x1400976ce  lea     rax, [rsp+48h+arg_8]
0x1400976d3  mov     qword ptr [rsp+48h+var_28], rax; int
0x1400976d8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400976dd  mov     rcx, [rdi+20h]
0x1400976e1  mov     r8, rbp
0x1400976e4  mov     rdx, rbx
0x1400976e7  mov     rax, [rcx]
0x1400976ea  mov     rax, [rax+18h]
0x1400976ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400976f3  mov     rcx, [rdi+20h]
0x1400976f7  and     eax, 1FFF0000h
0x1400976fc  cmp     eax, 70000h
0x140097701  mov     r8, rbp
0x140097704  mov     rdx, rbx
0x140097707  mov     r9, [rcx]
0x14009770a  mov     rax, [r9+18h]
0x14009770e  jnz     short loc_14009771A
0x140097710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097715  movzx   edi, ax
0x140097718  jmp     short loc_140097721
0x14009771a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009771f  mov     edi, eax
0x140097721  call    cs:__imp_GetCurrentProcess
0x140097727  mov     rcx, rax; hProcess
0x14009772a  mov     edx, edi; uExitCode
0x14009772c  call    cs:__imp_TerminateProcess
0x140097732  cmp     dword ptr [rbx], 1Bh
0x140097735  jz      short loc_140097759
0x140097737  mov     ebx, 80070057h
0x14009773c  mov     edx, 64h ; 'd'; void *
0x140097741  mov     rcx, [rsp+48h]; this
0x140097746  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14009774d  mov     r9d, ebx; char *
0x140097750  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140097755  mov     eax, ebx
0x140097757  jmp     short loc_140097769
0x140097759  mov     ebx, [rbx+4]
0x14009775c  test    ebx, ebx
0x14009775e  jns     short loc_140097767
0x140097760  mov     edx, 65h ; 'e'
0x140097765  jmp     short loc_140097741
0x140097767  xor     eax, eax
0x140097769  mov     rbx, [rsp+48h+arg_10]
0x14009776e  add     rsp, 30h
0x140097772  pop     rdi
0x140097773  pop     rsi
0x140097774  pop     rbp
0x140097775  retn
```
