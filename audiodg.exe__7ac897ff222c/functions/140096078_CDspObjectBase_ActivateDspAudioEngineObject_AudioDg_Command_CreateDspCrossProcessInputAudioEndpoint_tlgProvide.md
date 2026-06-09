# CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspCrossProcessInputAudioEndpoint>(_tlgProvider_t const *,IDspAudioEngine *,uint,AudioDg_Command_CreateDspCrossProcessInputAudioEndpoint *)

- ea: `0x140096078`
- end: `0x14009625f`
- name: `??$ActivateDspAudioEngineObject@UAudioDg_Command_CreateDspCrossProcessInputAudioEndpoint@@@CDspObjectBase@@QEAAJPEBU_tlgProvider_t@@PEAUIDspAudioEngine@@IPEAUAudioDg_Command_CreateDspCrossProcessInputAudioEndpoint@@@Z`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400986f0`

## callees

- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14004f178`
- `0x140096078`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140096158`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140096158`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400961e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400961e0`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400961eb`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400961eb`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspCrossProcessInputAudioEndpoint>(
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
LABEL_20:
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
  v10[4] = 32;
  v10[7] = a4;
  v11 = (_DWORD *)a1[2];
  if ( *v11 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v11) )
  {
    v31 = v10[6];
    v29[0] = *v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned int)byte_1400D33A9,
      v12,
      v13,
      (__int64)v29,
      (__int64)&v31);
  }
  if ( (*(int (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, v10, 32) < 0 )
  {
    v15 = (_DWORD *)a1[2];
    if ( *v15 > 2u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v14) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v17 = *v9;
      v31 = CurrentProcessId;
      v29[0] = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v17 + 24LL))(v17, v10, 32);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v15,
        (unsigned int)word_1400D3372,
        v18,
        v19,
        (__int64)v29,
        (__int64)&v31);
    }
    v20 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, v10, 32);
    v21 = *v9;
    v22 = (v20 & 0x1FFF0000) == 458752;
    v23 = *(unsigned __int16 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL);
    if ( v22 )
      v24 = v23(v21, v10, 32);
    else
      v24 = ((__int64 (__fastcall *)(__int64, _DWORD *, __int64))v23)(v21, v10, 32);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v24);
  }
  if ( *v10 != 4 || v10[6] != 5 )
  {
    v7 = -2147024809;
    v8 = 73;
    goto LABEL_20;
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
0x140096078  mov     [rsp+arg_8], rbx
0x14009607d  mov     [rsp+arg_10], rbp
0x140096082  push    rsi
0x140096083  push    rdi
0x140096084  push    r14
0x140096086  sub     rsp, 40h
0x14009608a  cmp     qword ptr [rcx+28h], 0
0x14009608f  mov     edi, r9d
0x140096092  mov     rsi, rcx
0x140096095  jz      short loc_1400960A6
0x140096097  mov     ebx, 8000FFFFh
0x14009609c  mov     edx, 38h ; '8'
0x1400960a1  jmp     loc_140096236
0x1400960a6  mov     [rcx+10h], rdx
0x1400960aa  lea     r14, [rcx+20h]
0x1400960ae  mov     rcx, r14
0x1400960b1  mov     rdx, r8
0x1400960b4  call    ??4?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIUnknown@@@Z; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(IUnknown *)
0x1400960b9  mov     rbx, [rsp+58h+arg_20]
0x1400960c1  mov     ebp, 20h ; ' '
0x1400960c6  mov     dword ptr [rbx], 4
0x1400960cc  mov     [rbx+10h], ebp
0x1400960cf  mov     [rbx+1Ch], edi
0x1400960d2  mov     r8, [rsi+10h]
0x1400960d6  mov     eax, [r8]
0x1400960d9  cmp     eax, 5
0x1400960dc  jbe     short loc_14009611F
0x1400960de  mov     edx, 100000h
0x1400960e3  mov     rcx, r8
0x1400960e6  call    _tlgKeywordOn
0x1400960eb  test    al, al
0x1400960ed  jz      short loc_14009611F
0x1400960ef  mov     eax, [rbx+18h]
0x1400960f2  lea     rdx, byte_1400D33A9
0x1400960f9  mov     [rsp+58h+arg_0], eax
0x1400960fd  mov     rcx, r8
0x140096100  mov     eax, [rbx]
0x140096102  mov     [rsp+58h+var_28], eax
0x140096106  lea     rax, [rsp+58h+arg_0]
0x14009610b  mov     [rsp+58h+var_30], rax
0x140096110  lea     rax, [rsp+58h+var_28]
0x140096115  mov     qword ptr [rsp+58h+var_38], rax
0x14009611a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14009611f  mov     rcx, [r14]
0x140096122  mov     r8, rbp
0x140096125  mov     rdx, rbx
0x140096128  mov     rax, [rcx]
0x14009612b  mov     rax, [rax+18h]
0x14009612f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096134  test    eax, eax
0x140096136  jns     loc_1400961F1
0x14009613c  mov     rdi, [rsi+10h]
0x140096140  mov     eax, [rdi]
0x140096142  cmp     eax, 2
0x140096145  jbe     short loc_14009619E
0x140096147  mov     edx, 100000h
0x14009614c  mov     rcx, rdi
0x14009614f  call    _tlgKeywordOn
0x140096154  test    al, al
0x140096156  jz      short loc_14009619E
0x140096158  call    cs:__imp_GetCurrentProcessId
0x14009615e  mov     rcx, [r14]
0x140096161  mov     r8, rbp
0x140096164  mov     [rsp+58h+arg_0], eax
0x140096168  mov     rdx, rbx
0x14009616b  mov     rax, [rcx]
0x14009616e  mov     rax, [rax+18h]
0x140096172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096177  mov     [rsp+58h+var_28], eax
0x14009617b  lea     rdx, word_1400D3372
0x140096182  lea     rax, [rsp+58h+arg_0]
0x140096187  mov     rcx, rdi
0x14009618a  mov     [rsp+58h+var_30], rax
0x14009618f  lea     rax, [rsp+58h+var_28]
0x140096194  mov     qword ptr [rsp+58h+var_38], rax; int
0x140096199  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14009619e  mov     rcx, [r14]
0x1400961a1  mov     r8, rbp
0x1400961a4  mov     rdx, rbx
0x1400961a7  mov     rax, [rcx]
0x1400961aa  mov     rax, [rax+18h]
0x1400961ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400961b3  mov     rcx, [r14]
0x1400961b6  and     eax, 1FFF0000h
0x1400961bb  cmp     eax, 70000h
0x1400961c0  mov     r8, rbp
0x1400961c3  mov     rdx, rbx
0x1400961c6  mov     r9, [rcx]
0x1400961c9  mov     rax, [r9+18h]
0x1400961cd  jnz     short loc_1400961D9
0x1400961cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400961d4  movzx   edi, ax
0x1400961d7  jmp     short loc_1400961E0
0x1400961d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400961de  mov     edi, eax
0x1400961e0  call    cs:__imp_GetCurrentProcess
0x1400961e6  mov     rcx, rax; hProcess
0x1400961e9  mov     edx, edi; uExitCode
0x1400961eb  call    cs:__imp_TerminateProcess
0x1400961f1  cmp     dword ptr [rbx], 4
0x1400961f4  jnz     short loc_14009622C
0x1400961f6  cmp     dword ptr [rbx+18h], 5
0x1400961fa  jnz     short loc_14009622C
0x1400961fc  mov     edi, [rbx+4]
0x1400961ff  test    edi, edi
0x140096201  jns     short loc_140096220
0x140096203  mov     rcx, [rsp+58h]; this
0x140096208  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14009620f  mov     r9d, edi; char *
0x140096212  mov     edx, 4Ah ; 'J'; void *
0x140096217  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009621c  mov     eax, edi
0x14009621e  jmp     short loc_14009624C
0x140096220  mov     rax, [rbx+8]
0x140096224  mov     [rsi+28h], rax
0x140096228  xor     eax, eax
0x14009622a  jmp     short loc_14009624C
0x14009622c  mov     ebx, 80070057h
0x140096231  mov     edx, 49h ; 'I'; void *
0x140096236  mov     rcx, [rsp+58h]; this
0x14009623b  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140096242  mov     r9d, ebx; char *
0x140096245  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009624a  mov     eax, ebx
0x14009624c  mov     rbx, [rsp+58h+arg_8]
0x140096251  mov     rbp, [rsp+58h+arg_10]
0x140096256  add     rsp, 40h
0x14009625a  pop     r14
0x14009625c  pop     rdi
0x14009625d  pop     rsi
0x14009625e  retn
```
