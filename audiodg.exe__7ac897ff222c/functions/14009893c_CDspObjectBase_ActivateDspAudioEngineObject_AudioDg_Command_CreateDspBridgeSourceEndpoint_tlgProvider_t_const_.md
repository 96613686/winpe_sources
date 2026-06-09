# CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspBridgeSourceEndpoint>(_tlgProvider_t const *,IDspAudioEngine *,uint,AudioDg_Command_CreateDspBridgeSourceEndpoint *)

- ea: `0x14009893c`
- end: `0x140098b2a`
- name: `??$ActivateDspAudioEngineObject@UAudioDg_Command_CreateDspBridgeSourceEndpoint@@@CDspObjectBase@@QEAAJPEBU_tlgProvider_t@@PEAUIDspAudioEngine@@IPEAUAudioDg_Command_CreateDspBridgeSourceEndpoint@@@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140099748`

## callees

- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14004f178`
- `0x14009893c`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140098a1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140098a1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140098aa4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140098aa4`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140098aaf`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140098aaf`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspBridgeSourceEndpoint>(
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
  v10[4] = 116;
  v10[7] = a4;
  v11 = (_DWORD *)a1[2];
  if ( *v11 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v11) )
  {
    v31 = v10[6];
    v29[0] = *v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned int)byte_1400D351D,
      v12,
      v13,
      (__int64)v29,
      (__int64)&v31);
  }
  if ( (*(int (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, v10, 116) < 0 )
  {
    v15 = (_DWORD *)a1[2];
    if ( *v15 > 2u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v14) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v17 = *v9;
      v31 = CurrentProcessId;
      v29[0] = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v17 + 24LL))(v17, v10, 116);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v15,
        (unsigned int)&word_1400D34E6,
        v18,
        v19,
        (__int64)v29,
        (__int64)&v31);
    }
    v20 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, v10, 116);
    v21 = *v9;
    v22 = (v20 & 0x1FFF0000) == 458752;
    v23 = *(unsigned __int16 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL);
    if ( v22 )
      v24 = v23(v21, v10, 116);
    else
      v24 = ((__int64 (__fastcall *)(__int64, _DWORD *, __int64))v23)(v21, v10, 116);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v24);
  }
  if ( *v10 != 4 || v10[6] != 11 || *((_WORD *)v10 + 24) > 0x36u )
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
0x14009893c  mov     [rsp+arg_8], rbx
0x140098941  mov     [rsp+arg_10], rbp
0x140098946  push    rsi
0x140098947  push    rdi
0x140098948  push    r14
0x14009894a  sub     rsp, 40h
0x14009894e  cmp     qword ptr [rcx+28h], 0
0x140098953  mov     edi, r9d
0x140098956  mov     rsi, rcx
0x140098959  jz      short loc_14009896A
0x14009895b  mov     ebx, 8000FFFFh
0x140098960  mov     edx, 38h ; '8'
0x140098965  jmp     loc_140098B01
0x14009896a  mov     [rcx+10h], rdx
0x14009896e  lea     r14, [rcx+20h]
0x140098972  mov     rcx, r14
0x140098975  mov     rdx, r8
0x140098978  call    ??4?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIUnknown@@@Z; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(IUnknown *)
0x14009897d  mov     rbx, [rsp+58h+arg_20]
0x140098985  mov     ebp, 74h ; 't'
0x14009898a  mov     dword ptr [rbx], 4
0x140098990  mov     [rbx+10h], ebp
0x140098993  mov     [rbx+1Ch], edi
0x140098996  mov     r8, [rsi+10h]
0x14009899a  mov     eax, [r8]
0x14009899d  cmp     eax, 5
0x1400989a0  jbe     short loc_1400989E3
0x1400989a2  mov     edx, 100000h
0x1400989a7  mov     rcx, r8
0x1400989aa  call    _tlgKeywordOn
0x1400989af  test    al, al
0x1400989b1  jz      short loc_1400989E3
0x1400989b3  mov     eax, [rbx+18h]
0x1400989b6  lea     rdx, byte_1400D351D
0x1400989bd  mov     [rsp+58h+arg_0], eax
0x1400989c1  mov     rcx, r8
0x1400989c4  mov     eax, [rbx]
0x1400989c6  mov     [rsp+58h+var_28], eax
0x1400989ca  lea     rax, [rsp+58h+arg_0]
0x1400989cf  mov     [rsp+58h+var_30], rax
0x1400989d4  lea     rax, [rsp+58h+var_28]
0x1400989d9  mov     qword ptr [rsp+58h+var_38], rax
0x1400989de  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400989e3  mov     rcx, [r14]
0x1400989e6  mov     r8, rbp
0x1400989e9  mov     rdx, rbx
0x1400989ec  mov     rax, [rcx]
0x1400989ef  mov     rax, [rax+18h]
0x1400989f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400989f8  test    eax, eax
0x1400989fa  jns     loc_140098AB5
0x140098a00  mov     rdi, [rsi+10h]
0x140098a04  mov     eax, [rdi]
0x140098a06  cmp     eax, 2
0x140098a09  jbe     short loc_140098A62
0x140098a0b  mov     edx, 100000h
0x140098a10  mov     rcx, rdi
0x140098a13  call    _tlgKeywordOn
0x140098a18  test    al, al
0x140098a1a  jz      short loc_140098A62
0x140098a1c  call    cs:__imp_GetCurrentProcessId
0x140098a22  mov     rcx, [r14]
0x140098a25  mov     r8, rbp
0x140098a28  mov     [rsp+58h+arg_0], eax
0x140098a2c  mov     rdx, rbx
0x140098a2f  mov     rax, [rcx]
0x140098a32  mov     rax, [rax+18h]
0x140098a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098a3b  mov     [rsp+58h+var_28], eax
0x140098a3f  lea     rdx, word_1400D34E6
0x140098a46  lea     rax, [rsp+58h+arg_0]
0x140098a4b  mov     rcx, rdi
0x140098a4e  mov     [rsp+58h+var_30], rax
0x140098a53  lea     rax, [rsp+58h+var_28]
0x140098a58  mov     qword ptr [rsp+58h+var_38], rax; int
0x140098a5d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140098a62  mov     rcx, [r14]
0x140098a65  mov     r8, rbp
0x140098a68  mov     rdx, rbx
0x140098a6b  mov     rax, [rcx]
0x140098a6e  mov     rax, [rax+18h]
0x140098a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098a77  mov     rcx, [r14]
0x140098a7a  and     eax, 1FFF0000h
0x140098a7f  cmp     eax, 70000h
0x140098a84  mov     r8, rbp
0x140098a87  mov     rdx, rbx
0x140098a8a  mov     r9, [rcx]
0x140098a8d  mov     rax, [r9+18h]
0x140098a91  jnz     short loc_140098A9D
0x140098a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098a98  movzx   edi, ax
0x140098a9b  jmp     short loc_140098AA4
0x140098a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098aa2  mov     edi, eax
0x140098aa4  call    cs:__imp_GetCurrentProcess
0x140098aaa  mov     rcx, rax; hProcess
0x140098aad  mov     edx, edi; uExitCode
0x140098aaf  call    cs:__imp_TerminateProcess
0x140098ab5  cmp     dword ptr [rbx], 4
0x140098ab8  jnz     short loc_140098AF7
0x140098aba  cmp     dword ptr [rbx+18h], 0Bh
0x140098abe  jnz     short loc_140098AF7
0x140098ac0  cmp     word ptr [rbx+30h], 36h ; '6'
0x140098ac5  ja      short loc_140098AF7
0x140098ac7  mov     edi, [rbx+4]
0x140098aca  test    edi, edi
0x140098acc  jns     short loc_140098AEB
0x140098ace  mov     rcx, [rsp+58h]; this
0x140098ad3  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140098ada  mov     r9d, edi; char *
0x140098add  mov     edx, 4Ah ; 'J'; void *
0x140098ae2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140098ae7  mov     eax, edi
0x140098ae9  jmp     short loc_140098B17
0x140098aeb  mov     rax, [rbx+8]
0x140098aef  mov     [rsi+28h], rax
0x140098af3  xor     eax, eax
0x140098af5  jmp     short loc_140098B17
0x140098af7  mov     ebx, 80070057h
0x140098afc  mov     edx, 49h ; 'I'; void *
0x140098b01  mov     rcx, [rsp+58h]; this
0x140098b06  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140098b0d  mov     r9d, ebx; char *
0x140098b10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140098b15  mov     eax, ebx
0x140098b17  mov     rbx, [rsp+58h+arg_8]
0x140098b1c  mov     rbp, [rsp+58h+arg_10]
0x140098b21  add     rsp, 40h
0x140098b25  pop     r14
0x140098b27  pop     rdi
0x140098b28  pop     rsi
0x140098b29  retn
```
