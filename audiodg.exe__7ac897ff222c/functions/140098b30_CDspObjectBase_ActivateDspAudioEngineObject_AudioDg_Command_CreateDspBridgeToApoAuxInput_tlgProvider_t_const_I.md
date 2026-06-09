# CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspBridgeToApoAuxInput>(_tlgProvider_t const *,IDspAudioEngine *,uint,AudioDg_Command_CreateDspBridgeToApoAuxInput *)

- ea: `0x140098b30`
- end: `0x140098d1e`
- name: `??$ActivateDspAudioEngineObject@UAudioDg_Command_CreateDspBridgeToApoAuxInput@@@CDspObjectBase@@QEAAJPEBU_tlgProvider_t@@PEAUIDspAudioEngine@@IPEAUAudioDg_Command_CreateDspBridgeToApoAuxInput@@@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140099858`

## callees

- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14004f178`
- `0x140098b30`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140098c10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140098c10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140098c98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140098c98`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140098ca3`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140098ca3`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspBridgeToApoAuxInput>(
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
      (unsigned int)byte_1400D3425,
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
        (unsigned int)&word_1400D33EE,
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
  if ( *v10 != 4 || v10[6] != 13 || *((_WORD *)v10 + 24) > 0x36u )
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
0x140098b30  mov     [rsp+arg_8], rbx
0x140098b35  mov     [rsp+arg_10], rbp
0x140098b3a  push    rsi
0x140098b3b  push    rdi
0x140098b3c  push    r14
0x140098b3e  sub     rsp, 40h
0x140098b42  cmp     qword ptr [rcx+28h], 0
0x140098b47  mov     edi, r9d
0x140098b4a  mov     rsi, rcx
0x140098b4d  jz      short loc_140098B5E
0x140098b4f  mov     ebx, 8000FFFFh
0x140098b54  mov     edx, 38h ; '8'
0x140098b59  jmp     loc_140098CF5
0x140098b5e  mov     [rcx+10h], rdx
0x140098b62  lea     r14, [rcx+20h]
0x140098b66  mov     rcx, r14
0x140098b69  mov     rdx, r8
0x140098b6c  call    ??4?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIUnknown@@@Z; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(IUnknown *)
0x140098b71  mov     rbx, [rsp+58h+arg_20]
0x140098b79  mov     ebp, 78h ; 'x'
0x140098b7e  mov     dword ptr [rbx], 4
0x140098b84  mov     [rbx+10h], ebp
0x140098b87  mov     [rbx+1Ch], edi
0x140098b8a  mov     r8, [rsi+10h]
0x140098b8e  mov     eax, [r8]
0x140098b91  cmp     eax, 5
0x140098b94  jbe     short loc_140098BD7
0x140098b96  mov     edx, 100000h
0x140098b9b  mov     rcx, r8
0x140098b9e  call    _tlgKeywordOn
0x140098ba3  test    al, al
0x140098ba5  jz      short loc_140098BD7
0x140098ba7  mov     eax, [rbx+18h]
0x140098baa  lea     rdx, byte_1400D3425
0x140098bb1  mov     [rsp+58h+arg_0], eax
0x140098bb5  mov     rcx, r8
0x140098bb8  mov     eax, [rbx]
0x140098bba  mov     [rsp+58h+var_28], eax
0x140098bbe  lea     rax, [rsp+58h+arg_0]
0x140098bc3  mov     [rsp+58h+var_30], rax
0x140098bc8  lea     rax, [rsp+58h+var_28]
0x140098bcd  mov     qword ptr [rsp+58h+var_38], rax
0x140098bd2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140098bd7  mov     rcx, [r14]
0x140098bda  mov     r8, rbp
0x140098bdd  mov     rdx, rbx
0x140098be0  mov     rax, [rcx]
0x140098be3  mov     rax, [rax+18h]
0x140098be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098bec  test    eax, eax
0x140098bee  jns     loc_140098CA9
0x140098bf4  mov     rdi, [rsi+10h]
0x140098bf8  mov     eax, [rdi]
0x140098bfa  cmp     eax, 2
0x140098bfd  jbe     short loc_140098C56
0x140098bff  mov     edx, 100000h
0x140098c04  mov     rcx, rdi
0x140098c07  call    _tlgKeywordOn
0x140098c0c  test    al, al
0x140098c0e  jz      short loc_140098C56
0x140098c10  call    cs:__imp_GetCurrentProcessId
0x140098c16  mov     rcx, [r14]
0x140098c19  mov     r8, rbp
0x140098c1c  mov     [rsp+58h+arg_0], eax
0x140098c20  mov     rdx, rbx
0x140098c23  mov     rax, [rcx]
0x140098c26  mov     rax, [rax+18h]
0x140098c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098c2f  mov     [rsp+58h+var_28], eax
0x140098c33  lea     rdx, word_1400D33EE
0x140098c3a  lea     rax, [rsp+58h+arg_0]
0x140098c3f  mov     rcx, rdi
0x140098c42  mov     [rsp+58h+var_30], rax
0x140098c47  lea     rax, [rsp+58h+var_28]
0x140098c4c  mov     qword ptr [rsp+58h+var_38], rax; int
0x140098c51  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140098c56  mov     rcx, [r14]
0x140098c59  mov     r8, rbp
0x140098c5c  mov     rdx, rbx
0x140098c5f  mov     rax, [rcx]
0x140098c62  mov     rax, [rax+18h]
0x140098c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098c6b  mov     rcx, [r14]
0x140098c6e  and     eax, 1FFF0000h
0x140098c73  cmp     eax, 70000h
0x140098c78  mov     r8, rbp
0x140098c7b  mov     rdx, rbx
0x140098c7e  mov     r9, [rcx]
0x140098c81  mov     rax, [r9+18h]
0x140098c85  jnz     short loc_140098C91
0x140098c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098c8c  movzx   edi, ax
0x140098c8f  jmp     short loc_140098C98
0x140098c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098c96  mov     edi, eax
0x140098c98  call    cs:__imp_GetCurrentProcess
0x140098c9e  mov     rcx, rax; hProcess
0x140098ca1  mov     edx, edi; uExitCode
0x140098ca3  call    cs:__imp_TerminateProcess
0x140098ca9  cmp     dword ptr [rbx], 4
0x140098cac  jnz     short loc_140098CEB
0x140098cae  cmp     dword ptr [rbx+18h], 0Dh
0x140098cb2  jnz     short loc_140098CEB
0x140098cb4  cmp     word ptr [rbx+30h], 36h ; '6'
0x140098cb9  ja      short loc_140098CEB
0x140098cbb  mov     edi, [rbx+4]
0x140098cbe  test    edi, edi
0x140098cc0  jns     short loc_140098CDF
0x140098cc2  mov     rcx, [rsp+58h]; this
0x140098cc7  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140098cce  mov     r9d, edi; char *
0x140098cd1  mov     edx, 4Ah ; 'J'; void *
0x140098cd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140098cdb  mov     eax, edi
0x140098cdd  jmp     short loc_140098D0B
0x140098cdf  mov     rax, [rbx+8]
0x140098ce3  mov     [rsi+28h], rax
0x140098ce7  xor     eax, eax
0x140098ce9  jmp     short loc_140098D0B
0x140098ceb  mov     ebx, 80070057h
0x140098cf0  mov     edx, 49h ; 'I'; void *
0x140098cf5  mov     rcx, [rsp+58h]; this
0x140098cfa  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140098d01  mov     r9d, ebx; char *
0x140098d04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140098d09  mov     eax, ebx
0x140098d0b  mov     rbx, [rsp+58h+arg_8]
0x140098d10  mov     rbp, [rsp+58h+arg_10]
0x140098d15  add     rsp, 40h
0x140098d19  pop     r14
0x140098d1b  pop     rdi
0x140098d1c  pop     rsi
0x140098d1d  retn
```
