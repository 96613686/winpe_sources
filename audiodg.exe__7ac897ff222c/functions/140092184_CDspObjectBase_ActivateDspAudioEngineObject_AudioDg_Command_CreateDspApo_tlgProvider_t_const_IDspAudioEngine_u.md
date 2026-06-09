# CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspApo>(_tlgProvider_t const *,IDspAudioEngine *,uint,AudioDg_Command_CreateDspApo *)

- ea: `0x140092184`
- end: `0x14009236b`
- name: `??$ActivateDspAudioEngineObject@UAudioDg_Command_CreateDspApo@@@CDspObjectBase@@QEAAJPEBU_tlgProvider_t@@PEAUIDspAudioEngine@@IPEAUAudioDg_Command_CreateDspApo@@@Z`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140094020`

## callees

- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14004f178`
- `0x140092184`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140092264`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140092264`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400922ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400922ec`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400922f7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400922f7`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspApo>(
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
  v10[4] = 64;
  v10[7] = a4;
  v11 = (_DWORD *)a1[2];
  if ( *v11 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v11) )
  {
    v31 = v10[6];
    v29[0] = *v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned int)byte_1400D2C6D,
      v12,
      v13,
      (__int64)v29,
      (__int64)&v31);
  }
  if ( (*(int (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, v10, 64) < 0 )
  {
    v15 = (_DWORD *)a1[2];
    if ( *v15 > 2u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v14) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v17 = *v9;
      v31 = CurrentProcessId;
      v29[0] = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v17 + 24LL))(v17, v10, 64);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v15,
        (unsigned int)&word_1400D2C36,
        v18,
        v19,
        (__int64)v29,
        (__int64)&v31);
    }
    v20 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, v10, 64);
    v21 = *v9;
    v22 = (v20 & 0x1FFF0000) == 458752;
    v23 = *(unsigned __int16 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL);
    if ( v22 )
      v24 = v23(v21, v10, 64);
    else
      v24 = ((__int64 (__fastcall *)(__int64, _DWORD *, __int64))v23)(v21, v10, 64);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v24);
  }
  if ( *v10 != 4 || v10[6] != 1 )
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
0x140092184  mov     [rsp+arg_8], rbx
0x140092189  mov     [rsp+arg_10], rbp
0x14009218e  push    rsi
0x14009218f  push    rdi
0x140092190  push    r14
0x140092192  sub     rsp, 40h
0x140092196  cmp     qword ptr [rcx+28h], 0
0x14009219b  mov     edi, r9d
0x14009219e  mov     rsi, rcx
0x1400921a1  jz      short loc_1400921B2
0x1400921a3  mov     ebx, 8000FFFFh
0x1400921a8  mov     edx, 38h ; '8'
0x1400921ad  jmp     loc_140092342
0x1400921b2  mov     [rcx+10h], rdx
0x1400921b6  lea     r14, [rcx+20h]
0x1400921ba  mov     rcx, r14
0x1400921bd  mov     rdx, r8
0x1400921c0  call    ??4?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIUnknown@@@Z; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(IUnknown *)
0x1400921c5  mov     rbx, [rsp+58h+arg_20]
0x1400921cd  mov     ebp, 40h ; '@'
0x1400921d2  mov     dword ptr [rbx], 4
0x1400921d8  mov     [rbx+10h], ebp
0x1400921db  mov     [rbx+1Ch], edi
0x1400921de  mov     r8, [rsi+10h]
0x1400921e2  mov     eax, [r8]
0x1400921e5  cmp     eax, 5
0x1400921e8  jbe     short loc_14009222B
0x1400921ea  mov     edx, 100000h
0x1400921ef  mov     rcx, r8
0x1400921f2  call    _tlgKeywordOn
0x1400921f7  test    al, al
0x1400921f9  jz      short loc_14009222B
0x1400921fb  mov     eax, [rbx+18h]
0x1400921fe  lea     rdx, byte_1400D2C6D
0x140092205  mov     [rsp+58h+arg_0], eax
0x140092209  mov     rcx, r8
0x14009220c  mov     eax, [rbx]
0x14009220e  mov     [rsp+58h+var_28], eax
0x140092212  lea     rax, [rsp+58h+arg_0]
0x140092217  mov     [rsp+58h+var_30], rax
0x14009221c  lea     rax, [rsp+58h+var_28]
0x140092221  mov     qword ptr [rsp+58h+var_38], rax
0x140092226  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14009222b  mov     rcx, [r14]
0x14009222e  mov     r8, rbp
0x140092231  mov     rdx, rbx
0x140092234  mov     rax, [rcx]
0x140092237  mov     rax, [rax+18h]
0x14009223b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092240  test    eax, eax
0x140092242  jns     loc_1400922FD
0x140092248  mov     rdi, [rsi+10h]
0x14009224c  mov     eax, [rdi]
0x14009224e  cmp     eax, 2
0x140092251  jbe     short loc_1400922AA
0x140092253  mov     edx, 100000h
0x140092258  mov     rcx, rdi
0x14009225b  call    _tlgKeywordOn
0x140092260  test    al, al
0x140092262  jz      short loc_1400922AA
0x140092264  call    cs:__imp_GetCurrentProcessId
0x14009226a  mov     rcx, [r14]
0x14009226d  mov     r8, rbp
0x140092270  mov     [rsp+58h+arg_0], eax
0x140092274  mov     rdx, rbx
0x140092277  mov     rax, [rcx]
0x14009227a  mov     rax, [rax+18h]
0x14009227e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092283  mov     [rsp+58h+var_28], eax
0x140092287  lea     rdx, word_1400D2C36
0x14009228e  lea     rax, [rsp+58h+arg_0]
0x140092293  mov     rcx, rdi
0x140092296  mov     [rsp+58h+var_30], rax
0x14009229b  lea     rax, [rsp+58h+var_28]
0x1400922a0  mov     qword ptr [rsp+58h+var_38], rax; int
0x1400922a5  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400922aa  mov     rcx, [r14]
0x1400922ad  mov     r8, rbp
0x1400922b0  mov     rdx, rbx
0x1400922b3  mov     rax, [rcx]
0x1400922b6  mov     rax, [rax+18h]
0x1400922ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400922bf  mov     rcx, [r14]
0x1400922c2  and     eax, 1FFF0000h
0x1400922c7  cmp     eax, 70000h
0x1400922cc  mov     r8, rbp
0x1400922cf  mov     rdx, rbx
0x1400922d2  mov     r9, [rcx]
0x1400922d5  mov     rax, [r9+18h]
0x1400922d9  jnz     short loc_1400922E5
0x1400922db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400922e0  movzx   edi, ax
0x1400922e3  jmp     short loc_1400922EC
0x1400922e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400922ea  mov     edi, eax
0x1400922ec  call    cs:__imp_GetCurrentProcess
0x1400922f2  mov     rcx, rax; hProcess
0x1400922f5  mov     edx, edi; uExitCode
0x1400922f7  call    cs:__imp_TerminateProcess
0x1400922fd  cmp     dword ptr [rbx], 4
0x140092300  jnz     short loc_140092338
0x140092302  cmp     dword ptr [rbx+18h], 1
0x140092306  jnz     short loc_140092338
0x140092308  mov     edi, [rbx+4]
0x14009230b  test    edi, edi
0x14009230d  jns     short loc_14009232C
0x14009230f  mov     rcx, [rsp+58h]; this
0x140092314  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14009231b  mov     r9d, edi; char *
0x14009231e  mov     edx, 4Ah ; 'J'; void *
0x140092323  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140092328  mov     eax, edi
0x14009232a  jmp     short loc_140092358
0x14009232c  mov     rax, [rbx+8]
0x140092330  mov     [rsi+28h], rax
0x140092334  xor     eax, eax
0x140092336  jmp     short loc_140092358
0x140092338  mov     ebx, 80070057h
0x14009233d  mov     edx, 49h ; 'I'; void *
0x140092342  mov     rcx, [rsp+58h]; this
0x140092347  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14009234e  mov     r9d, ebx; char *
0x140092351  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140092356  mov     eax, ebx
0x140092358  mov     rbx, [rsp+58h+arg_8]
0x14009235d  mov     rbp, [rsp+58h+arg_10]
0x140092362  add     rsp, 40h
0x140092366  pop     r14
0x140092368  pop     rdi
0x140092369  pop     rsi
0x14009236a  retn
```
