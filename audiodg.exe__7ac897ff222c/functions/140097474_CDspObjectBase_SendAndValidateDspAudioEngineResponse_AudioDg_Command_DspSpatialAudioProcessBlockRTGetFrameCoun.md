# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspSpatialAudioProcessBlockRTGetFrameCount>(AudioDg_Command_DspSpatialAudioProcessBlockRTGetFrameCount *)

- ea: `0x140097474`
- end: `0x1400975f2`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspSpatialAudioProcessBlockRTGetFrameCount@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspSpatialAudioProcessBlockRTGetFrameCount@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400981a0`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x140097474`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140097512`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140097512`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009759d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009759d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400975a8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400975a8`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspSpatialAudioProcessBlockRTGetFrameCount>(
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

  *(_DWORD *)a2 = 26;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 28;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)word_1400D2FDA,
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
        (unsigned int)byte_1400D2FA3,
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
  if ( *(_DWORD *)a2 != 26 )
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
0x140097474  mov     [rsp+arg_10], rbx
0x140097479  push    rbp
0x14009747a  push    rsi
0x14009747b  push    rdi
0x14009747c  sub     rsp, 30h
0x140097480  mov     dword ptr [rdx], 1Ah
0x140097486  mov     ebp, 1Ch
0x14009748b  mov     rax, [rcx+28h]
0x14009748f  mov     rbx, rdx
0x140097492  mov     [rdx+8], rax
0x140097496  mov     rdi, rcx
0x140097499  mov     [rdx+10h], ebp
0x14009749c  mov     r8, [rcx+10h]
0x1400974a0  mov     eax, [r8]
0x1400974a3  cmp     eax, 5
0x1400974a6  jbe     short loc_1400974D8
0x1400974a8  mov     edx, 100000h
0x1400974ad  mov     rcx, r8
0x1400974b0  call    _tlgKeywordOn
0x1400974b5  test    al, al
0x1400974b7  jz      short loc_1400974D8
0x1400974b9  mov     eax, [rbx]
0x1400974bb  lea     rdx, word_1400D2FDA
0x1400974c2  mov     [rsp+48h+arg_0], eax
0x1400974c6  mov     rcx, r8
0x1400974c9  lea     rax, [rsp+48h+arg_0]
0x1400974ce  mov     qword ptr [rsp+48h+var_28], rax
0x1400974d3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1400974d8  mov     rcx, [rdi+20h]
0x1400974dc  mov     r8, rbp
0x1400974df  mov     rdx, rbx
0x1400974e2  mov     rax, [rcx]
0x1400974e5  mov     rax, [rax+18h]
0x1400974e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400974ee  test    eax, eax
0x1400974f0  jns     loc_1400975AE
0x1400974f6  mov     rsi, [rdi+10h]
0x1400974fa  mov     eax, [rsi]
0x1400974fc  cmp     eax, 2
0x1400974ff  jbe     short loc_140097559
0x140097501  mov     edx, 100000h
0x140097506  mov     rcx, rsi
0x140097509  call    _tlgKeywordOn
0x14009750e  test    al, al
0x140097510  jz      short loc_140097559
0x140097512  call    cs:__imp_GetCurrentProcessId
0x140097518  mov     rcx, [rdi+20h]
0x14009751c  mov     r8, rbp
0x14009751f  mov     [rsp+48h+arg_0], eax
0x140097523  mov     rdx, rbx
0x140097526  mov     rax, [rcx]
0x140097529  mov     rax, [rax+18h]
0x14009752d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097532  mov     [rsp+48h+arg_8], eax
0x140097536  lea     rdx, byte_1400D2FA3
0x14009753d  lea     rax, [rsp+48h+arg_0]
0x140097542  mov     rcx, rsi
0x140097545  mov     [rsp+48h+var_20], rax
0x14009754a  lea     rax, [rsp+48h+arg_8]
0x14009754f  mov     qword ptr [rsp+48h+var_28], rax; int
0x140097554  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140097559  mov     rcx, [rdi+20h]
0x14009755d  mov     r8, rbp
0x140097560  mov     rdx, rbx
0x140097563  mov     rax, [rcx]
0x140097566  mov     rax, [rax+18h]
0x14009756a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009756f  mov     rcx, [rdi+20h]
0x140097573  and     eax, 1FFF0000h
0x140097578  cmp     eax, 70000h
0x14009757d  mov     r8, rbp
0x140097580  mov     rdx, rbx
0x140097583  mov     r9, [rcx]
0x140097586  mov     rax, [r9+18h]
0x14009758a  jnz     short loc_140097596
0x14009758c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097591  movzx   edi, ax
0x140097594  jmp     short loc_14009759D
0x140097596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009759b  mov     edi, eax
0x14009759d  call    cs:__imp_GetCurrentProcess
0x1400975a3  mov     rcx, rax; hProcess
0x1400975a6  mov     edx, edi; uExitCode
0x1400975a8  call    cs:__imp_TerminateProcess
0x1400975ae  cmp     dword ptr [rbx], 1Ah
0x1400975b1  jz      short loc_1400975D5
0x1400975b3  mov     ebx, 80070057h
0x1400975b8  mov     edx, 64h ; 'd'; void *
0x1400975bd  mov     rcx, [rsp+48h]; this
0x1400975c2  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x1400975c9  mov     r9d, ebx; char *
0x1400975cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400975d1  mov     eax, ebx
0x1400975d3  jmp     short loc_1400975E5
0x1400975d5  mov     ebx, [rbx+4]
0x1400975d8  test    ebx, ebx
0x1400975da  jns     short loc_1400975E3
0x1400975dc  mov     edx, 65h ; 'e'
0x1400975e1  jmp     short loc_1400975BD
0x1400975e3  xor     eax, eax
0x1400975e5  mov     rbx, [rsp+48h+arg_10]
0x1400975ea  add     rsp, 30h
0x1400975ee  pop     rdi
0x1400975ef  pop     rsi
0x1400975f0  pop     rbp
0x1400975f1  retn
```
