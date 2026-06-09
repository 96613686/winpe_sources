# CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspCrossProcessOutputAudioEndpoint>(_tlgProvider_t const *,IDspAudioEngine *,uint,AudioDg_Command_CreateDspCrossProcessOutputAudioEndpoint *)

- ea: `0x140096268`
- end: `0x14009644c`
- name: `??$ActivateDspAudioEngineObject@UAudioDg_Command_CreateDspCrossProcessOutputAudioEndpoint@@@CDspObjectBase@@QEAAJPEBU_tlgProvider_t@@PEAUIDspAudioEngine@@IPEAUAudioDg_Command_CreateDspCrossProcessOutputAudioEndpoint@@@Z`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400987b4`

## callees

- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14004f178`
- `0x140096268`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009635e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009635e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400963e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400963e6`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400963f1`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400963f1`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspCrossProcessOutputAudioEndpoint>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        _DWORD *a5)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  _QWORD *v10; // r14
  _DWORD *v11; // rbx
  _DWORD *v12; // r8
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // r8
  _DWORD *v16; // rdi
  DWORD CurrentProcessId; // eax
  __int64 v18; // rcx
  int v19; // r8d
  int v20; // r9d
  int v21; // eax
  __int64 v22; // rcx
  bool v23; // zf
  unsigned __int16 (__fastcall *v24)(__int64, _DWORD *, __int64); // rax
  UINT v25; // edi
  HANDLE CurrentProcess; // rax
  int v27; // edi
  int v28; // [rsp+20h] [rbp-38h]
  int v29[10]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD v31; // [rsp+60h] [rbp+8h] BYREF

  if ( a1[5] )
  {
    v7 = -2147418113;
    v8 = 56;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\DspObjectBase.h",
      (const char *)v7,
      v28);
    return v7;
  }
  a1[2] = a2;
  v10 = a1 + 4;
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(a1 + 4, a3);
  v11 = a5;
  *a5 = 4;
  v11[4] = 32;
  v11[7] = a4;
  v12 = (_DWORD *)a1[2];
  if ( *v12 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v12) )
  {
    v31 = v11[6];
    v29[0] = *v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v13,
      (unsigned int)word_1400D304A,
      v13,
      v14,
      (__int64)v29,
      (__int64)&v31);
  }
  if ( (*(int (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v10 + 24LL))(*v10, v11, 32) < 0 )
  {
    v16 = (_DWORD *)a1[2];
    if ( *v16 > 2u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v15) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v18 = *v10;
      v31 = CurrentProcessId;
      v29[0] = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v18 + 24LL))(v18, v11, 32);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v16,
        (unsigned int)byte_1400D3013,
        v19,
        v20,
        (__int64)v29,
        (__int64)&v31);
    }
    v21 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v10 + 24LL))(*v10, v11, 32);
    v22 = *v10;
    v23 = (v21 & 0x1FFF0000) == 458752;
    v24 = *(unsigned __int16 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)*v10 + 24LL);
    if ( v23 )
      v25 = v24(v22, v11, 32);
    else
      v25 = ((__int64 (__fastcall *)(__int64, _DWORD *, __int64))v24)(v22, v11, 32);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v25);
  }
  if ( *v11 != 4 )
  {
    v7 = -2147024809;
    v8 = 73;
    goto LABEL_3;
  }
  v27 = v11[1];
  if ( v27 >= 0 )
  {
    a1[5] = *((_QWORD *)v11 + 1);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\DspObjectBase.h",
      (const char *)(unsigned int)v27,
      v28);
    return (unsigned int)v27;
  }
}

```

## disassembly

```asm
0x140096268  mov     [rsp+arg_8], rbx
0x14009626d  mov     [rsp+arg_10], rbp
0x140096272  push    rsi
0x140096273  push    rdi
0x140096274  push    r14
0x140096276  sub     rsp, 40h
0x14009627a  cmp     qword ptr [rcx+28h], 0
0x14009627f  mov     edi, r9d
0x140096282  mov     rsi, rcx
0x140096285  jz      short loc_1400962AC
0x140096287  mov     ebx, 8000FFFFh
0x14009628c  mov     edx, 38h ; '8'; void *
0x140096291  mov     rcx, [rsp+58h]; this
0x140096296  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14009629d  mov     r9d, ebx; char *
0x1400962a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400962a5  mov     eax, ebx
0x1400962a7  jmp     loc_140096439
0x1400962ac  mov     [rcx+10h], rdx
0x1400962b0  lea     r14, [rcx+20h]
0x1400962b4  mov     rcx, r14
0x1400962b7  mov     rdx, r8
0x1400962ba  call    ??4?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIUnknown@@@Z; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(IUnknown *)
0x1400962bf  mov     rbx, [rsp+58h+arg_20]
0x1400962c7  mov     ebp, 20h ; ' '
0x1400962cc  mov     dword ptr [rbx], 4
0x1400962d2  mov     [rbx+10h], ebp
0x1400962d5  mov     [rbx+1Ch], edi
0x1400962d8  mov     r8, [rsi+10h]
0x1400962dc  mov     eax, [r8]
0x1400962df  cmp     eax, 5
0x1400962e2  jbe     short loc_140096325
0x1400962e4  mov     edx, 100000h
0x1400962e9  mov     rcx, r8
0x1400962ec  call    _tlgKeywordOn
0x1400962f1  test    al, al
0x1400962f3  jz      short loc_140096325
0x1400962f5  mov     eax, [rbx+18h]
0x1400962f8  lea     rdx, word_1400D304A
0x1400962ff  mov     [rsp+58h+arg_0], eax
0x140096303  mov     rcx, r8
0x140096306  mov     eax, [rbx]
0x140096308  mov     [rsp+58h+var_28], eax
0x14009630c  lea     rax, [rsp+58h+arg_0]
0x140096311  mov     [rsp+58h+var_30], rax
0x140096316  lea     rax, [rsp+58h+var_28]
0x14009631b  mov     qword ptr [rsp+58h+var_38], rax
0x140096320  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140096325  mov     rcx, [r14]
0x140096328  mov     r8, rbp
0x14009632b  mov     rdx, rbx
0x14009632e  mov     rax, [rcx]
0x140096331  mov     rax, [rax+18h]
0x140096335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009633a  test    eax, eax
0x14009633c  jns     loc_1400963F7
0x140096342  mov     rdi, [rsi+10h]
0x140096346  mov     eax, [rdi]
0x140096348  cmp     eax, 2
0x14009634b  jbe     short loc_1400963A4
0x14009634d  mov     edx, 100000h
0x140096352  mov     rcx, rdi
0x140096355  call    _tlgKeywordOn
0x14009635a  test    al, al
0x14009635c  jz      short loc_1400963A4
0x14009635e  call    cs:__imp_GetCurrentProcessId
0x140096364  mov     rcx, [r14]
0x140096367  mov     r8, rbp
0x14009636a  mov     [rsp+58h+arg_0], eax
0x14009636e  mov     rdx, rbx
0x140096371  mov     rax, [rcx]
0x140096374  mov     rax, [rax+18h]
0x140096378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009637d  mov     [rsp+58h+var_28], eax
0x140096381  lea     rdx, byte_1400D3013
0x140096388  lea     rax, [rsp+58h+arg_0]
0x14009638d  mov     rcx, rdi
0x140096390  mov     [rsp+58h+var_30], rax
0x140096395  lea     rax, [rsp+58h+var_28]
0x14009639a  mov     qword ptr [rsp+58h+var_38], rax; int
0x14009639f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400963a4  mov     rcx, [r14]
0x1400963a7  mov     r8, rbp
0x1400963aa  mov     rdx, rbx
0x1400963ad  mov     rax, [rcx]
0x1400963b0  mov     rax, [rax+18h]
0x1400963b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400963b9  mov     rcx, [r14]
0x1400963bc  and     eax, 1FFF0000h
0x1400963c1  cmp     eax, 70000h
0x1400963c6  mov     r8, rbp
0x1400963c9  mov     rdx, rbx
0x1400963cc  mov     r9, [rcx]
0x1400963cf  mov     rax, [r9+18h]
0x1400963d3  jnz     short loc_1400963DF
0x1400963d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400963da  movzx   edi, ax
0x1400963dd  jmp     short loc_1400963E6
0x1400963df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400963e4  mov     edi, eax
0x1400963e6  call    cs:__imp_GetCurrentProcess
0x1400963ec  mov     rcx, rax; hProcess
0x1400963ef  mov     edx, edi; uExitCode
0x1400963f1  call    cs:__imp_TerminateProcess
0x1400963f7  cmp     dword ptr [rbx], 4
0x1400963fa  jz      short loc_14009640B
0x1400963fc  mov     ebx, 80070057h
0x140096401  mov     edx, 49h ; 'I'
0x140096406  jmp     loc_140096291
0x14009640b  mov     edi, [rbx+4]
0x14009640e  test    edi, edi
0x140096410  jns     short loc_14009642F
0x140096412  mov     rcx, [rsp+58h]; this
0x140096417  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14009641e  mov     r9d, edi; char *
0x140096421  mov     edx, 4Ah ; 'J'; void *
0x140096426  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009642b  mov     eax, edi
0x14009642d  jmp     short loc_140096439
0x14009642f  mov     rax, [rbx+8]
0x140096433  mov     [rsi+28h], rax
0x140096437  xor     eax, eax
0x140096439  mov     rbx, [rsp+58h+arg_8]
0x14009643e  mov     rbp, [rsp+58h+arg_10]
0x140096443  add     rsp, 40h
0x140096447  pop     r14
0x140096449  pop     rdi
0x14009644a  pop     rsi
0x14009644b  retn
```
