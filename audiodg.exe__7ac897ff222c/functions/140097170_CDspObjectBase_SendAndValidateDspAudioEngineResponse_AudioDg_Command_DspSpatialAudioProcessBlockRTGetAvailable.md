# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspSpatialAudioProcessBlockRTGetAvailableObjectCount>(AudioDg_Command_DspSpatialAudioProcessBlockRTGetAvailableObjectCount *)

- ea: `0x140097170`
- end: `0x1400972ee`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspSpatialAudioProcessBlockRTGetAvailableObjectCount@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspSpatialAudioProcessBlockRTGetAvailableObjectCount@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140098080`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x140097170`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009720e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009720e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140097299`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140097299`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400972a4`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400972a4`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspSpatialAudioProcessBlockRTGetAvailableObjectCount>(
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

  *(_DWORD *)a2 = 22;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 28;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)&dword_1400D3214,
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
        (unsigned int)byte_1400D31DD,
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
  if ( *(_DWORD *)a2 != 22 )
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
0x140097170  mov     [rsp+arg_10], rbx
0x140097175  push    rbp
0x140097176  push    rsi
0x140097177  push    rdi
0x140097178  sub     rsp, 30h
0x14009717c  mov     dword ptr [rdx], 16h
0x140097182  mov     ebp, 1Ch
0x140097187  mov     rax, [rcx+28h]
0x14009718b  mov     rbx, rdx
0x14009718e  mov     [rdx+8], rax
0x140097192  mov     rdi, rcx
0x140097195  mov     [rdx+10h], ebp
0x140097198  mov     r8, [rcx+10h]
0x14009719c  mov     eax, [r8]
0x14009719f  cmp     eax, 5
0x1400971a2  jbe     short loc_1400971D4
0x1400971a4  mov     edx, 100000h
0x1400971a9  mov     rcx, r8
0x1400971ac  call    _tlgKeywordOn
0x1400971b1  test    al, al
0x1400971b3  jz      short loc_1400971D4
0x1400971b5  mov     eax, [rbx]
0x1400971b7  lea     rdx, dword_1400D3214
0x1400971be  mov     [rsp+48h+arg_0], eax
0x1400971c2  mov     rcx, r8
0x1400971c5  lea     rax, [rsp+48h+arg_0]
0x1400971ca  mov     qword ptr [rsp+48h+var_28], rax
0x1400971cf  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1400971d4  mov     rcx, [rdi+20h]
0x1400971d8  mov     r8, rbp
0x1400971db  mov     rdx, rbx
0x1400971de  mov     rax, [rcx]
0x1400971e1  mov     rax, [rax+18h]
0x1400971e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400971ea  test    eax, eax
0x1400971ec  jns     loc_1400972AA
0x1400971f2  mov     rsi, [rdi+10h]
0x1400971f6  mov     eax, [rsi]
0x1400971f8  cmp     eax, 2
0x1400971fb  jbe     short loc_140097255
0x1400971fd  mov     edx, 100000h
0x140097202  mov     rcx, rsi
0x140097205  call    _tlgKeywordOn
0x14009720a  test    al, al
0x14009720c  jz      short loc_140097255
0x14009720e  call    cs:__imp_GetCurrentProcessId
0x140097214  mov     rcx, [rdi+20h]
0x140097218  mov     r8, rbp
0x14009721b  mov     [rsp+48h+arg_0], eax
0x14009721f  mov     rdx, rbx
0x140097222  mov     rax, [rcx]
0x140097225  mov     rax, [rax+18h]
0x140097229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009722e  mov     [rsp+48h+arg_8], eax
0x140097232  lea     rdx, byte_1400D31DD
0x140097239  lea     rax, [rsp+48h+arg_0]
0x14009723e  mov     rcx, rsi
0x140097241  mov     [rsp+48h+var_20], rax
0x140097246  lea     rax, [rsp+48h+arg_8]
0x14009724b  mov     qword ptr [rsp+48h+var_28], rax; int
0x140097250  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140097255  mov     rcx, [rdi+20h]
0x140097259  mov     r8, rbp
0x14009725c  mov     rdx, rbx
0x14009725f  mov     rax, [rcx]
0x140097262  mov     rax, [rax+18h]
0x140097266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009726b  mov     rcx, [rdi+20h]
0x14009726f  and     eax, 1FFF0000h
0x140097274  cmp     eax, 70000h
0x140097279  mov     r8, rbp
0x14009727c  mov     rdx, rbx
0x14009727f  mov     r9, [rcx]
0x140097282  mov     rax, [r9+18h]
0x140097286  jnz     short loc_140097292
0x140097288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009728d  movzx   edi, ax
0x140097290  jmp     short loc_140097299
0x140097292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097297  mov     edi, eax
0x140097299  call    cs:__imp_GetCurrentProcess
0x14009729f  mov     rcx, rax; hProcess
0x1400972a2  mov     edx, edi; uExitCode
0x1400972a4  call    cs:__imp_TerminateProcess
0x1400972aa  cmp     dword ptr [rbx], 16h
0x1400972ad  jz      short loc_1400972D1
0x1400972af  mov     ebx, 80070057h
0x1400972b4  mov     edx, 64h ; 'd'; void *
0x1400972b9  mov     rcx, [rsp+48h]; this
0x1400972be  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x1400972c5  mov     r9d, ebx; char *
0x1400972c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400972cd  mov     eax, ebx
0x1400972cf  jmp     short loc_1400972E1
0x1400972d1  mov     ebx, [rbx+4]
0x1400972d4  test    ebx, ebx
0x1400972d6  jns     short loc_1400972DF
0x1400972d8  mov     edx, 65h ; 'e'
0x1400972dd  jmp     short loc_1400972B9
0x1400972df  xor     eax, eax
0x1400972e1  mov     rbx, [rsp+48h+arg_10]
0x1400972e6  add     rsp, 30h
0x1400972ea  pop     rdi
0x1400972eb  pop     rsi
0x1400972ec  pop     rbp
0x1400972ed  retn
```
