# CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspBridgeToRenderGraph>(_tlgProvider_t const *,IDspAudioEngine *,uint,AudioDg_Command_CreateDspBridgeToRenderGraph *)

- ea: `0x140098d24`
- end: `0x140098f12`
- name: `??$ActivateDspAudioEngineObject@UAudioDg_Command_CreateDspBridgeToRenderGraph@@@CDspObjectBase@@QEAAJPEBU_tlgProvider_t@@PEAUIDspAudioEngine@@IPEAUAudioDg_Command_CreateDspBridgeToRenderGraph@@@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14009996c`

## callees

- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14004f178`
- `0x140098d24`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140098e04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140098e04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140098e8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140098e8c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140098e97`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140098e97`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspBridgeToRenderGraph>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        _DWORD *a5)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  _QWORD *v9; // r14
  _DWORD *v10; // rbx
  _DWORD *v11; // r8
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // r8
  _DWORD *v15; // rdi
  DWORD CurrentProcessId; // eax
  __int64 v17; // rcx
  int v18; // r8d
  int v19; // r9d
  int v20; // eax
  __int64 v21; // rcx
  bool v22; // zf
  unsigned __int16 (__fastcall *v23)(__int64, _DWORD *, __int64); // rax
  UINT v24; // edi
  HANDLE CurrentProcess; // rax
  int v26; // edi
  int v28; // [rsp+20h] [rbp-38h]
  int v29[10]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD v31; // [rsp+60h] [rbp+8h] BYREF

  if ( a1[5] )
  {
    v7 = -2147418113;
    v8 = 56;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\DspObjectBase.h",
      (const char *)v7,
      v28);
    return v7;
  }
  a1[2] = a2;
  v9 = a1 + 4;
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(a1 + 4, a3);
  v10 = a5;
  *a5 = 4;
  v10[4] = 120;
  v10[7] = a4;
  v11 = (_DWORD *)a1[2];
  if ( *v11 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v11) )
  {
    v31 = v10[6];
    v29[0] = *v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned int)byte_1400D34A1,
      v12,
      v13,
      (__int64)v29,
      (__int64)&v31);
  }
  if ( (*(int (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, v10, 120) < 0 )
  {
    v15 = (_DWORD *)a1[2];
    if ( *v15 > 2u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v14) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v17 = *v9;
      v31 = CurrentProcessId;
      v29[0] = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v17 + 24LL))(v17, v10, 120);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v15,
        (unsigned int)word_1400D346A,
        v18,
        v19,
        (__int64)v29,
        (__int64)&v31);
    }
    v20 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, v10, 120);
    v21 = *v9;
    v22 = (v20 & 0x1FFF0000) == 458752;
    v23 = *(unsigned __int16 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL);
    if ( v22 )
      v24 = v23(v21, v10, 120);
    else
      v24 = ((__int64 (__fastcall *)(__int64, _DWORD *, __int64))v23)(v21, v10, 120);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v24);
  }
  if ( *v10 != 4 || v10[6] != 12 || *((_WORD *)v10 + 24) > 0x36u )
  {
    v7 = -2147024809;
    v8 = 73;
    goto LABEL_21;
  }
  v26 = v10[1];
  if ( v26 >= 0 )
  {
    a1[5] = *((_QWORD *)v10 + 1);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\DspObjectBase.h",
      (const char *)(unsigned int)v26,
      v28);
    return (unsigned int)v26;
  }
}

```

## disassembly

```asm
0x140098d24  mov     [rsp+arg_8], rbx
0x140098d29  mov     [rsp+arg_10], rbp
0x140098d2e  push    rsi
0x140098d2f  push    rdi
0x140098d30  push    r14
0x140098d32  sub     rsp, 40h
0x140098d36  cmp     qword ptr [rcx+28h], 0
0x140098d3b  mov     edi, r9d
0x140098d3e  mov     rsi, rcx
0x140098d41  jz      short loc_140098D52
0x140098d43  mov     ebx, 8000FFFFh
0x140098d48  mov     edx, 38h ; '8'
0x140098d4d  jmp     loc_140098EE9
0x140098d52  mov     [rcx+10h], rdx
0x140098d56  lea     r14, [rcx+20h]
0x140098d5a  mov     rcx, r14
0x140098d5d  mov     rdx, r8
0x140098d60  call    ??4?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIUnknown@@@Z; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(IUnknown *)
0x140098d65  mov     rbx, [rsp+58h+arg_20]
0x140098d6d  mov     ebp, 78h ; 'x'
0x140098d72  mov     dword ptr [rbx], 4
0x140098d78  mov     [rbx+10h], ebp
0x140098d7b  mov     [rbx+1Ch], edi
0x140098d7e  mov     r8, [rsi+10h]
0x140098d82  mov     eax, [r8]
0x140098d85  cmp     eax, 5
0x140098d88  jbe     short loc_140098DCB
0x140098d8a  mov     edx, 100000h
0x140098d8f  mov     rcx, r8
0x140098d92  call    _tlgKeywordOn
0x140098d97  test    al, al
0x140098d99  jz      short loc_140098DCB
0x140098d9b  mov     eax, [rbx+18h]
0x140098d9e  lea     rdx, byte_1400D34A1
0x140098da5  mov     [rsp+58h+arg_0], eax
0x140098da9  mov     rcx, r8
0x140098dac  mov     eax, [rbx]
0x140098dae  mov     [rsp+58h+var_28], eax
0x140098db2  lea     rax, [rsp+58h+arg_0]
0x140098db7  mov     [rsp+58h+var_30], rax
0x140098dbc  lea     rax, [rsp+58h+var_28]
0x140098dc1  mov     qword ptr [rsp+58h+var_38], rax
0x140098dc6  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140098dcb  mov     rcx, [r14]
0x140098dce  mov     r8, rbp
0x140098dd1  mov     rdx, rbx
0x140098dd4  mov     rax, [rcx]
0x140098dd7  mov     rax, [rax+18h]
0x140098ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098de0  test    eax, eax
0x140098de2  jns     loc_140098E9D
0x140098de8  mov     rdi, [rsi+10h]
0x140098dec  mov     eax, [rdi]
0x140098dee  cmp     eax, 2
0x140098df1  jbe     short loc_140098E4A
0x140098df3  mov     edx, 100000h
0x140098df8  mov     rcx, rdi
0x140098dfb  call    _tlgKeywordOn
0x140098e00  test    al, al
0x140098e02  jz      short loc_140098E4A
0x140098e04  call    cs:__imp_GetCurrentProcessId
0x140098e0a  mov     rcx, [r14]
0x140098e0d  mov     r8, rbp
0x140098e10  mov     [rsp+58h+arg_0], eax
0x140098e14  mov     rdx, rbx
0x140098e17  mov     rax, [rcx]
0x140098e1a  mov     rax, [rax+18h]
0x140098e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098e23  mov     [rsp+58h+var_28], eax
0x140098e27  lea     rdx, word_1400D346A
0x140098e2e  lea     rax, [rsp+58h+arg_0]
0x140098e33  mov     rcx, rdi
0x140098e36  mov     [rsp+58h+var_30], rax
0x140098e3b  lea     rax, [rsp+58h+var_28]
0x140098e40  mov     qword ptr [rsp+58h+var_38], rax; int
0x140098e45  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140098e4a  mov     rcx, [r14]
0x140098e4d  mov     r8, rbp
0x140098e50  mov     rdx, rbx
0x140098e53  mov     rax, [rcx]
0x140098e56  mov     rax, [rax+18h]
0x140098e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098e5f  mov     rcx, [r14]
0x140098e62  and     eax, 1FFF0000h
0x140098e67  cmp     eax, 70000h
0x140098e6c  mov     r8, rbp
0x140098e6f  mov     rdx, rbx
0x140098e72  mov     r9, [rcx]
0x140098e75  mov     rax, [r9+18h]
0x140098e79  jnz     short loc_140098E85
0x140098e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098e80  movzx   edi, ax
0x140098e83  jmp     short loc_140098E8C
0x140098e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098e8a  mov     edi, eax
0x140098e8c  call    cs:__imp_GetCurrentProcess
0x140098e92  mov     rcx, rax; hProcess
0x140098e95  mov     edx, edi; uExitCode
0x140098e97  call    cs:__imp_TerminateProcess
0x140098e9d  cmp     dword ptr [rbx], 4
0x140098ea0  jnz     short loc_140098EDF
0x140098ea2  cmp     dword ptr [rbx+18h], 0Ch
0x140098ea6  jnz     short loc_140098EDF
0x140098ea8  cmp     word ptr [rbx+30h], 36h ; '6'
0x140098ead  ja      short loc_140098EDF
0x140098eaf  mov     edi, [rbx+4]
0x140098eb2  test    edi, edi
0x140098eb4  jns     short loc_140098ED3
0x140098eb6  mov     rcx, [rsp+58h]; this
0x140098ebb  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140098ec2  mov     r9d, edi; char *
0x140098ec5  mov     edx, 4Ah ; 'J'; void *
0x140098eca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140098ecf  mov     eax, edi
0x140098ed1  jmp     short loc_140098EFF
0x140098ed3  mov     rax, [rbx+8]
0x140098ed7  mov     [rsi+28h], rax
0x140098edb  xor     eax, eax
0x140098edd  jmp     short loc_140098EFF
0x140098edf  mov     ebx, 80070057h
0x140098ee4  mov     edx, 49h ; 'I'; void *
0x140098ee9  mov     rcx, [rsp+58h]; this
0x140098eee  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140098ef5  mov     r9d, ebx; char *
0x140098ef8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140098efd  mov     eax, ebx
0x140098eff  mov     rbx, [rsp+58h+arg_8]
0x140098f04  mov     rbp, [rsp+58h+arg_10]
0x140098f09  add     rsp, 40h
0x140098f0d  pop     r14
0x140098f0f  pop     rdi
0x140098f10  pop     rsi
0x140098f11  retn
```
