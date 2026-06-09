# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspAudioPumpInitialize>(AudioDg_Command_DspAudioPumpInitialize *)

- ea: `0x140099da4`
- end: `0x140099f29`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DspAudioPumpInitialize@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DspAudioPumpInitialize@@@Z`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14009a5a0`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x140099da4`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140099e42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140099e42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140099ecd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140099ecd`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140099ed8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140099ed8`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DspAudioPumpInitialize>(
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

  *(_DWORD *)a2 = 16;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 124;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_1400D3845,
      v5,
      v6,
      (__int64)&v24);
  }
  if ( (*(int (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[4] + 24LL))(a1[4], a2, 124) < 0 )
  {
    v8 = (_DWORD *)a1[2];
    if ( *v8 > 2u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v7) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v10 = a1[4];
      v24 = CurrentProcessId;
      v25 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v10 + 24LL))(v10, a2, 124);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v8,
        (unsigned int)&word_1400D380E,
        v11,
        v12,
        (__int64)&v25,
        (__int64)&v24);
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[4] + 24LL))(a1[4], a2, 124);
    v14 = a1[4];
    v15 = (v13 & 0x1FFF0000) == 458752;
    v16 = *(unsigned __int16 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v14 + 24LL);
    if ( v15 )
      v17 = v16(v14, a2, 124);
    else
      v17 = ((__int64 (__fastcall *)(__int64, __int64, __int64))v16)(v14, a2, 124);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v17);
  }
  if ( *(_DWORD *)a2 == 16 && *(_WORD *)(a2 + 68) <= 0x36u )
  {
    v19 = *(_DWORD *)(a2 + 4);
    if ( v19 >= 0 )
      return 0;
    v20 = 101;
  }
  else
  {
    v19 = -2147024809;
    v20 = 100;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v20,
    (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\DspObjectBase.h",
    (const char *)(unsigned int)v19,
    v22);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x140099da4  mov     [rsp+arg_10], rbx
0x140099da9  push    rbp
0x140099daa  push    rsi
0x140099dab  push    rdi
0x140099dac  sub     rsp, 30h
0x140099db0  mov     dword ptr [rdx], 10h
0x140099db6  mov     ebp, 7Ch ; '|'
0x140099dbb  mov     rax, [rcx+28h]
0x140099dbf  mov     rbx, rdx
0x140099dc2  mov     [rdx+8], rax
0x140099dc6  mov     rdi, rcx
0x140099dc9  mov     [rdx+10h], ebp
0x140099dcc  mov     r8, [rcx+10h]
0x140099dd0  mov     eax, [r8]
0x140099dd3  cmp     eax, 5
0x140099dd6  jbe     short loc_140099E08
0x140099dd8  mov     edx, 100000h
0x140099ddd  mov     rcx, r8
0x140099de0  call    _tlgKeywordOn
0x140099de5  test    al, al
0x140099de7  jz      short loc_140099E08
0x140099de9  mov     eax, [rbx]
0x140099deb  lea     rdx, byte_1400D3845
0x140099df2  mov     [rsp+48h+arg_0], eax
0x140099df6  mov     rcx, r8
0x140099df9  lea     rax, [rsp+48h+arg_0]
0x140099dfe  mov     qword ptr [rsp+48h+var_28], rax
0x140099e03  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140099e08  mov     rcx, [rdi+20h]
0x140099e0c  mov     r8, rbp
0x140099e0f  mov     rdx, rbx
0x140099e12  mov     rax, [rcx]
0x140099e15  mov     rax, [rax+18h]
0x140099e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140099e1e  test    eax, eax
0x140099e20  jns     loc_140099EDE
0x140099e26  mov     rsi, [rdi+10h]
0x140099e2a  mov     eax, [rsi]
0x140099e2c  cmp     eax, 2
0x140099e2f  jbe     short loc_140099E89
0x140099e31  mov     edx, 100000h
0x140099e36  mov     rcx, rsi
0x140099e39  call    _tlgKeywordOn
0x140099e3e  test    al, al
0x140099e40  jz      short loc_140099E89
0x140099e42  call    cs:__imp_GetCurrentProcessId
0x140099e48  mov     rcx, [rdi+20h]
0x140099e4c  mov     r8, rbp
0x140099e4f  mov     [rsp+48h+arg_0], eax
0x140099e53  mov     rdx, rbx
0x140099e56  mov     rax, [rcx]
0x140099e59  mov     rax, [rax+18h]
0x140099e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140099e62  mov     [rsp+48h+arg_8], eax
0x140099e66  lea     rdx, word_1400D380E
0x140099e6d  lea     rax, [rsp+48h+arg_0]
0x140099e72  mov     rcx, rsi
0x140099e75  mov     [rsp+48h+var_20], rax
0x140099e7a  lea     rax, [rsp+48h+arg_8]
0x140099e7f  mov     qword ptr [rsp+48h+var_28], rax; int
0x140099e84  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140099e89  mov     rcx, [rdi+20h]
0x140099e8d  mov     r8, rbp
0x140099e90  mov     rdx, rbx
0x140099e93  mov     rax, [rcx]
0x140099e96  mov     rax, [rax+18h]
0x140099e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140099e9f  mov     rcx, [rdi+20h]
0x140099ea3  and     eax, 1FFF0000h
0x140099ea8  cmp     eax, 70000h
0x140099ead  mov     r8, rbp
0x140099eb0  mov     rdx, rbx
0x140099eb3  mov     r9, [rcx]
0x140099eb6  mov     rax, [r9+18h]
0x140099eba  jnz     short loc_140099EC6
0x140099ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140099ec1  movzx   edi, ax
0x140099ec4  jmp     short loc_140099ECD
0x140099ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140099ecb  mov     edi, eax
0x140099ecd  call    cs:__imp_GetCurrentProcess
0x140099ed3  mov     rcx, rax; hProcess
0x140099ed6  mov     edx, edi; uExitCode
0x140099ed8  call    cs:__imp_TerminateProcess
0x140099ede  cmp     dword ptr [rbx], 10h
0x140099ee1  jnz     short loc_140099EFC
0x140099ee3  cmp     word ptr [rbx+44h], 36h ; '6'
0x140099ee8  ja      short loc_140099EFC
0x140099eea  mov     ebx, [rbx+4]
0x140099eed  test    ebx, ebx
0x140099eef  jns     short loc_140099EF8
0x140099ef1  mov     edx, 65h ; 'e'
0x140099ef6  jmp     short loc_140099F06
0x140099ef8  xor     eax, eax
0x140099efa  jmp     short loc_140099F1C
0x140099efc  mov     ebx, 80070057h
0x140099f01  mov     edx, 64h ; 'd'; void *
0x140099f06  mov     rcx, [rsp+48h]; this
0x140099f0b  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140099f12  mov     r9d, ebx; char *
0x140099f15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140099f1a  mov     eax, ebx
0x140099f1c  mov     rbx, [rsp+48h+arg_10]
0x140099f21  add     rsp, 30h
0x140099f25  pop     rdi
0x140099f26  pop     rsi
0x140099f27  pop     rbp
0x140099f28  retn
```
