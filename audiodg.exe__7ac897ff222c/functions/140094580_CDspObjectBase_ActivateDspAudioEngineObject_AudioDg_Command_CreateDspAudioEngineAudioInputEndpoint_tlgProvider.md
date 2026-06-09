# CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspAudioEngineAudioInputEndpoint>(_tlgProvider_t const *,IDspAudioEngine *,uint,AudioDg_Command_CreateDspAudioEngineAudioInputEndpoint *)

- ea: `0x140094580`
- end: `0x14009476e`
- name: `??$ActivateDspAudioEngineObject@UAudioDg_Command_CreateDspAudioEngineAudioInputEndpoint@@@CDspObjectBase@@QEAAJPEBU_tlgProvider_t@@PEAUIDspAudioEngine@@IPEAUAudioDg_Command_CreateDspAudioEngineAudioInputEndpoint@@@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140095c7c`

## callees

- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14004f178`
- `0x140094580`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140094660`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140094660`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400946e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400946e8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400946f3`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400946f3`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspAudioEngineAudioInputEndpoint>(
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
  v10[4] = 248;
  v10[7] = a4;
  v11 = (_DWORD *)a1[2];
  if ( *v11 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v11) )
  {
    v31 = v10[6];
    v29[0] = *v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned int)byte_1400D2DD5,
      v12,
      v13,
      (__int64)v29,
      (__int64)&v31);
  }
  if ( (*(int (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, v10, 248) < 0 )
  {
    v15 = (_DWORD *)a1[2];
    if ( *v15 > 2u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v14) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v17 = *v9;
      v31 = CurrentProcessId;
      v29[0] = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v17 + 24LL))(v17, v10, 248);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v15,
        (unsigned int)&word_1400D2D9E,
        v18,
        v19,
        (__int64)v29,
        (__int64)&v31);
    }
    v20 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, v10, 248);
    v21 = *v9;
    v22 = (v20 & 0x1FFF0000) == 458752;
    v23 = *(unsigned __int16 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL);
    if ( v22 )
      v24 = v23(v21, v10, 248);
    else
      v24 = ((__int64 (__fastcall *)(__int64, _DWORD *, __int64))v23)(v21, v10, 248);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v24);
  }
  if ( *v10 != 4 || v10[6] != 4 || *((_WORD *)v10 + 24) > 0x6Eu )
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
0x140094580  mov     [rsp+arg_8], rbx
0x140094585  mov     [rsp+arg_10], rbp
0x14009458a  push    rsi
0x14009458b  push    rdi
0x14009458c  push    r14
0x14009458e  sub     rsp, 40h
0x140094592  cmp     qword ptr [rcx+28h], 0
0x140094597  mov     edi, r9d
0x14009459a  mov     rsi, rcx
0x14009459d  jz      short loc_1400945AE
0x14009459f  mov     ebx, 8000FFFFh
0x1400945a4  mov     edx, 38h ; '8'
0x1400945a9  jmp     loc_140094745
0x1400945ae  mov     [rcx+10h], rdx
0x1400945b2  lea     r14, [rcx+20h]
0x1400945b6  mov     rcx, r14
0x1400945b9  mov     rdx, r8
0x1400945bc  call    ??4?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIUnknown@@@Z; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(IUnknown *)
0x1400945c1  mov     rbx, [rsp+58h+arg_20]
0x1400945c9  mov     ebp, 0F8h
0x1400945ce  mov     dword ptr [rbx], 4
0x1400945d4  mov     [rbx+10h], ebp
0x1400945d7  mov     [rbx+1Ch], edi
0x1400945da  mov     r8, [rsi+10h]
0x1400945de  mov     eax, [r8]
0x1400945e1  cmp     eax, 5
0x1400945e4  jbe     short loc_140094627
0x1400945e6  mov     edx, 100000h
0x1400945eb  mov     rcx, r8
0x1400945ee  call    _tlgKeywordOn
0x1400945f3  test    al, al
0x1400945f5  jz      short loc_140094627
0x1400945f7  mov     eax, [rbx+18h]
0x1400945fa  lea     rdx, byte_1400D2DD5
0x140094601  mov     [rsp+58h+arg_0], eax
0x140094605  mov     rcx, r8
0x140094608  mov     eax, [rbx]
0x14009460a  mov     [rsp+58h+var_28], eax
0x14009460e  lea     rax, [rsp+58h+arg_0]
0x140094613  mov     [rsp+58h+var_30], rax
0x140094618  lea     rax, [rsp+58h+var_28]
0x14009461d  mov     qword ptr [rsp+58h+var_38], rax
0x140094622  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140094627  mov     rcx, [r14]
0x14009462a  mov     r8, rbp
0x14009462d  mov     rdx, rbx
0x140094630  mov     rax, [rcx]
0x140094633  mov     rax, [rax+18h]
0x140094637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009463c  test    eax, eax
0x14009463e  jns     loc_1400946F9
0x140094644  mov     rdi, [rsi+10h]
0x140094648  mov     eax, [rdi]
0x14009464a  cmp     eax, 2
0x14009464d  jbe     short loc_1400946A6
0x14009464f  mov     edx, 100000h
0x140094654  mov     rcx, rdi
0x140094657  call    _tlgKeywordOn
0x14009465c  test    al, al
0x14009465e  jz      short loc_1400946A6
0x140094660  call    cs:__imp_GetCurrentProcessId
0x140094666  mov     rcx, [r14]
0x140094669  mov     r8, rbp
0x14009466c  mov     [rsp+58h+arg_0], eax
0x140094670  mov     rdx, rbx
0x140094673  mov     rax, [rcx]
0x140094676  mov     rax, [rax+18h]
0x14009467a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009467f  mov     [rsp+58h+var_28], eax
0x140094683  lea     rdx, word_1400D2D9E
0x14009468a  lea     rax, [rsp+58h+arg_0]
0x14009468f  mov     rcx, rdi
0x140094692  mov     [rsp+58h+var_30], rax
0x140094697  lea     rax, [rsp+58h+var_28]
0x14009469c  mov     qword ptr [rsp+58h+var_38], rax; int
0x1400946a1  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400946a6  mov     rcx, [r14]
0x1400946a9  mov     r8, rbp
0x1400946ac  mov     rdx, rbx
0x1400946af  mov     rax, [rcx]
0x1400946b2  mov     rax, [rax+18h]
0x1400946b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400946bb  mov     rcx, [r14]
0x1400946be  and     eax, 1FFF0000h
0x1400946c3  cmp     eax, 70000h
0x1400946c8  mov     r8, rbp
0x1400946cb  mov     rdx, rbx
0x1400946ce  mov     r9, [rcx]
0x1400946d1  mov     rax, [r9+18h]
0x1400946d5  jnz     short loc_1400946E1
0x1400946d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400946dc  movzx   edi, ax
0x1400946df  jmp     short loc_1400946E8
0x1400946e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400946e6  mov     edi, eax
0x1400946e8  call    cs:__imp_GetCurrentProcess
0x1400946ee  mov     rcx, rax; hProcess
0x1400946f1  mov     edx, edi; uExitCode
0x1400946f3  call    cs:__imp_TerminateProcess
0x1400946f9  cmp     dword ptr [rbx], 4
0x1400946fc  jnz     short loc_14009473B
0x1400946fe  cmp     dword ptr [rbx+18h], 4
0x140094702  jnz     short loc_14009473B
0x140094704  cmp     word ptr [rbx+30h], 6Eh ; 'n'
0x140094709  ja      short loc_14009473B
0x14009470b  mov     edi, [rbx+4]
0x14009470e  test    edi, edi
0x140094710  jns     short loc_14009472F
0x140094712  mov     rcx, [rsp+58h]; this
0x140094717  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14009471e  mov     r9d, edi; char *
0x140094721  mov     edx, 4Ah ; 'J'; void *
0x140094726  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009472b  mov     eax, edi
0x14009472d  jmp     short loc_14009475B
0x14009472f  mov     rax, [rbx+8]
0x140094733  mov     [rsi+28h], rax
0x140094737  xor     eax, eax
0x140094739  jmp     short loc_14009475B
0x14009473b  mov     ebx, 80070057h
0x140094740  mov     edx, 49h ; 'I'; void *
0x140094745  mov     rcx, [rsp+58h]; this
0x14009474a  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140094751  mov     r9d, ebx; char *
0x140094754  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140094759  mov     eax, ebx
0x14009475b  mov     rbx, [rsp+58h+arg_8]
0x140094760  mov     rbp, [rsp+58h+arg_10]
0x140094765  add     rsp, 40h
0x140094769  pop     r14
0x14009476b  pop     rdi
0x14009476c  pop     rsi
0x14009476d  retn
```
