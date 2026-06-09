# CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspSpatialCrossProcessInputAudioEndpoint>(_tlgProvider_t const *,IDspAudioEngine *,uint,AudioDg_Command_CreateDspSpatialCrossProcessInputAudioEndpoint *)

- ea: `0x140096454`
- end: `0x14009663b`
- name: `??$ActivateDspAudioEngineObject@UAudioDg_Command_CreateDspSpatialCrossProcessInputAudioEndpoint@@@CDspObjectBase@@QEAAJPEBU_tlgProvider_t@@PEAUIDspAudioEngine@@IPEAUAudioDg_Command_CreateDspSpatialCrossProcessInputAudioEndpoint@@@Z`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140098878`

## callees

- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14004f178`
- `0x140096454`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140096534`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140096534`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400965bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400965bc`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400965c7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400965c7`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspSpatialCrossProcessInputAudioEndpoint>(
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
      (unsigned int)byte_1400D332D,
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
        (unsigned int)&word_1400D32F6,
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
  if ( *v10 != 4 || v10[6] != 10 )
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
0x140096454  mov     [rsp+arg_8], rbx
0x140096459  mov     [rsp+arg_10], rbp
0x14009645e  push    rsi
0x14009645f  push    rdi
0x140096460  push    r14
0x140096462  sub     rsp, 40h
0x140096466  cmp     qword ptr [rcx+28h], 0
0x14009646b  mov     edi, r9d
0x14009646e  mov     rsi, rcx
0x140096471  jz      short loc_140096482
0x140096473  mov     ebx, 8000FFFFh
0x140096478  mov     edx, 38h ; '8'
0x14009647d  jmp     loc_140096612
0x140096482  mov     [rcx+10h], rdx
0x140096486  lea     r14, [rcx+20h]
0x14009648a  mov     rcx, r14
0x14009648d  mov     rdx, r8
0x140096490  call    ??4?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIUnknown@@@Z; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(IUnknown *)
0x140096495  mov     rbx, [rsp+58h+arg_20]
0x14009649d  mov     ebp, 20h ; ' '
0x1400964a2  mov     dword ptr [rbx], 4
0x1400964a8  mov     [rbx+10h], ebp
0x1400964ab  mov     [rbx+1Ch], edi
0x1400964ae  mov     r8, [rsi+10h]
0x1400964b2  mov     eax, [r8]
0x1400964b5  cmp     eax, 5
0x1400964b8  jbe     short loc_1400964FB
0x1400964ba  mov     edx, 100000h
0x1400964bf  mov     rcx, r8
0x1400964c2  call    _tlgKeywordOn
0x1400964c7  test    al, al
0x1400964c9  jz      short loc_1400964FB
0x1400964cb  mov     eax, [rbx+18h]
0x1400964ce  lea     rdx, byte_1400D332D
0x1400964d5  mov     [rsp+58h+arg_0], eax
0x1400964d9  mov     rcx, r8
0x1400964dc  mov     eax, [rbx]
0x1400964de  mov     [rsp+58h+var_28], eax
0x1400964e2  lea     rax, [rsp+58h+arg_0]
0x1400964e7  mov     [rsp+58h+var_30], rax
0x1400964ec  lea     rax, [rsp+58h+var_28]
0x1400964f1  mov     qword ptr [rsp+58h+var_38], rax
0x1400964f6  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400964fb  mov     rcx, [r14]
0x1400964fe  mov     r8, rbp
0x140096501  mov     rdx, rbx
0x140096504  mov     rax, [rcx]
0x140096507  mov     rax, [rax+18h]
0x14009650b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096510  test    eax, eax
0x140096512  jns     loc_1400965CD
0x140096518  mov     rdi, [rsi+10h]
0x14009651c  mov     eax, [rdi]
0x14009651e  cmp     eax, 2
0x140096521  jbe     short loc_14009657A
0x140096523  mov     edx, 100000h
0x140096528  mov     rcx, rdi
0x14009652b  call    _tlgKeywordOn
0x140096530  test    al, al
0x140096532  jz      short loc_14009657A
0x140096534  call    cs:__imp_GetCurrentProcessId
0x14009653a  mov     rcx, [r14]
0x14009653d  mov     r8, rbp
0x140096540  mov     [rsp+58h+arg_0], eax
0x140096544  mov     rdx, rbx
0x140096547  mov     rax, [rcx]
0x14009654a  mov     rax, [rax+18h]
0x14009654e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096553  mov     [rsp+58h+var_28], eax
0x140096557  lea     rdx, word_1400D32F6
0x14009655e  lea     rax, [rsp+58h+arg_0]
0x140096563  mov     rcx, rdi
0x140096566  mov     [rsp+58h+var_30], rax
0x14009656b  lea     rax, [rsp+58h+var_28]
0x140096570  mov     qword ptr [rsp+58h+var_38], rax; int
0x140096575  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14009657a  mov     rcx, [r14]
0x14009657d  mov     r8, rbp
0x140096580  mov     rdx, rbx
0x140096583  mov     rax, [rcx]
0x140096586  mov     rax, [rax+18h]
0x14009658a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009658f  mov     rcx, [r14]
0x140096592  and     eax, 1FFF0000h
0x140096597  cmp     eax, 70000h
0x14009659c  mov     r8, rbp
0x14009659f  mov     rdx, rbx
0x1400965a2  mov     r9, [rcx]
0x1400965a5  mov     rax, [r9+18h]
0x1400965a9  jnz     short loc_1400965B5
0x1400965ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400965b0  movzx   edi, ax
0x1400965b3  jmp     short loc_1400965BC
0x1400965b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400965ba  mov     edi, eax
0x1400965bc  call    cs:__imp_GetCurrentProcess
0x1400965c2  mov     rcx, rax; hProcess
0x1400965c5  mov     edx, edi; uExitCode
0x1400965c7  call    cs:__imp_TerminateProcess
0x1400965cd  cmp     dword ptr [rbx], 4
0x1400965d0  jnz     short loc_140096608
0x1400965d2  cmp     dword ptr [rbx+18h], 0Ah
0x1400965d6  jnz     short loc_140096608
0x1400965d8  mov     edi, [rbx+4]
0x1400965db  test    edi, edi
0x1400965dd  jns     short loc_1400965FC
0x1400965df  mov     rcx, [rsp+58h]; this
0x1400965e4  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x1400965eb  mov     r9d, edi; char *
0x1400965ee  mov     edx, 4Ah ; 'J'; void *
0x1400965f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400965f8  mov     eax, edi
0x1400965fa  jmp     short loc_140096628
0x1400965fc  mov     rax, [rbx+8]
0x140096600  mov     [rsi+28h], rax
0x140096604  xor     eax, eax
0x140096606  jmp     short loc_140096628
0x140096608  mov     ebx, 80070057h
0x14009660d  mov     edx, 49h ; 'I'; void *
0x140096612  mov     rcx, [rsp+58h]; this
0x140096617  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14009661e  mov     r9d, ebx; char *
0x140096621  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140096626  mov     eax, ebx
0x140096628  mov     rbx, [rsp+58h+arg_8]
0x14009662d  mov     rbp, [rsp+58h+arg_10]
0x140096632  add     rsp, 40h
0x140096636  pop     r14
0x140096638  pop     rdi
0x140096639  pop     rsi
0x14009663a  retn
```
