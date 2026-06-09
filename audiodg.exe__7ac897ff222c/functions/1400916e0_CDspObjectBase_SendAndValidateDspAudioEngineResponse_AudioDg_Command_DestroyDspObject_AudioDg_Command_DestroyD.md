# CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DestroyDspObject>(AudioDg_Command_DestroyDspObject *)

- ea: `0x1400916e0`
- end: `0x14009185e`
- name: `??$SendAndValidateDspAudioEngineResponse@UAudioDg_Command_DestroyDspObject@@@CDspObjectBase@@QEAAJPEAUAudioDg_Command_DestroyDspObject@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005166c`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x1400916e0`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009177e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009177e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140091809`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140091809`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140091814`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140091814`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::SendAndValidateDspAudioEngineResponse<AudioDg_Command_DestroyDspObject>(
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

  *(_DWORD *)a2 = 5;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 24;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v24 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_1400D283B,
      v5,
      v6,
      (__int64)&v24);
  }
  if ( (*(int (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[4] + 24LL))(a1[4], a2, 24) < 0 )
  {
    v8 = (_DWORD *)a1[2];
    if ( *v8 > 2u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v7) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v10 = a1[4];
      v24 = CurrentProcessId;
      v25 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v10 + 24LL))(v10, a2, 24);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v8,
        (unsigned int)&dword_1400D2874,
        v11,
        v12,
        (__int64)&v25,
        (__int64)&v24);
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[4] + 24LL))(a1[4], a2, 24);
    v14 = a1[4];
    v15 = (v13 & 0x1FFF0000) == 458752;
    v16 = *(unsigned __int16 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v14 + 24LL);
    if ( v15 )
      v17 = v16(v14, a2, 24);
    else
      v17 = ((__int64 (__fastcall *)(__int64, __int64, __int64))v16)(v14, a2, 24);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v17);
  }
  if ( *(_DWORD *)a2 != 5 )
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
0x1400916e0  mov     [rsp+arg_10], rbx
0x1400916e5  push    rbp
0x1400916e6  push    rsi
0x1400916e7  push    rdi
0x1400916e8  sub     rsp, 30h
0x1400916ec  mov     dword ptr [rdx], 5
0x1400916f2  mov     ebp, 18h
0x1400916f7  mov     rax, [rcx+28h]
0x1400916fb  mov     rbx, rdx
0x1400916fe  mov     [rdx+8], rax
0x140091702  mov     rdi, rcx
0x140091705  mov     [rdx+10h], ebp
0x140091708  mov     r8, [rcx+10h]
0x14009170c  mov     eax, [r8]
0x14009170f  cmp     eax, 5
0x140091712  jbe     short loc_140091744
0x140091714  mov     edx, 100000h
0x140091719  mov     rcx, r8
0x14009171c  call    _tlgKeywordOn
0x140091721  test    al, al
0x140091723  jz      short loc_140091744
0x140091725  mov     eax, [rbx]
0x140091727  lea     rdx, byte_1400D283B
0x14009172e  mov     [rsp+48h+arg_0], eax
0x140091732  mov     rcx, r8
0x140091735  lea     rax, [rsp+48h+arg_0]
0x14009173a  mov     qword ptr [rsp+48h+var_28], rax
0x14009173f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140091744  mov     rcx, [rdi+20h]
0x140091748  mov     r8, rbp
0x14009174b  mov     rdx, rbx
0x14009174e  mov     rax, [rcx]
0x140091751  mov     rax, [rax+18h]
0x140091755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009175a  test    eax, eax
0x14009175c  jns     loc_14009181A
0x140091762  mov     rsi, [rdi+10h]
0x140091766  mov     eax, [rsi]
0x140091768  cmp     eax, 2
0x14009176b  jbe     short loc_1400917C5
0x14009176d  mov     edx, 100000h
0x140091772  mov     rcx, rsi
0x140091775  call    _tlgKeywordOn
0x14009177a  test    al, al
0x14009177c  jz      short loc_1400917C5
0x14009177e  call    cs:__imp_GetCurrentProcessId
0x140091784  mov     rcx, [rdi+20h]
0x140091788  mov     r8, rbp
0x14009178b  mov     [rsp+48h+arg_0], eax
0x14009178f  mov     rdx, rbx
0x140091792  mov     rax, [rcx]
0x140091795  mov     rax, [rax+18h]
0x140091799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009179e  mov     [rsp+48h+arg_8], eax
0x1400917a2  lea     rdx, dword_1400D2874
0x1400917a9  lea     rax, [rsp+48h+arg_0]
0x1400917ae  mov     rcx, rsi
0x1400917b1  mov     [rsp+48h+var_20], rax
0x1400917b6  lea     rax, [rsp+48h+arg_8]
0x1400917bb  mov     qword ptr [rsp+48h+var_28], rax; int
0x1400917c0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400917c5  mov     rcx, [rdi+20h]
0x1400917c9  mov     r8, rbp
0x1400917cc  mov     rdx, rbx
0x1400917cf  mov     rax, [rcx]
0x1400917d2  mov     rax, [rax+18h]
0x1400917d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400917db  mov     rcx, [rdi+20h]
0x1400917df  and     eax, 1FFF0000h
0x1400917e4  cmp     eax, 70000h
0x1400917e9  mov     r8, rbp
0x1400917ec  mov     rdx, rbx
0x1400917ef  mov     r9, [rcx]
0x1400917f2  mov     rax, [r9+18h]
0x1400917f6  jnz     short loc_140091802
0x1400917f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400917fd  movzx   edi, ax
0x140091800  jmp     short loc_140091809
0x140091802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140091807  mov     edi, eax
0x140091809  call    cs:__imp_GetCurrentProcess
0x14009180f  mov     rcx, rax; hProcess
0x140091812  mov     edx, edi; uExitCode
0x140091814  call    cs:__imp_TerminateProcess
0x14009181a  cmp     dword ptr [rbx], 5
0x14009181d  jz      short loc_140091841
0x14009181f  mov     ebx, 80070057h
0x140091824  mov     edx, 64h ; 'd'; void *
0x140091829  mov     rcx, [rsp+48h]; this
0x14009182e  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140091835  mov     r9d, ebx; char *
0x140091838  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009183d  mov     eax, ebx
0x14009183f  jmp     short loc_140091851
0x140091841  mov     ebx, [rbx+4]
0x140091844  test    ebx, ebx
0x140091846  jns     short loc_14009184F
0x140091848  mov     edx, 65h ; 'e'
0x14009184d  jmp     short loc_140091829
0x14009184f  xor     eax, eax
0x140091851  mov     rbx, [rsp+48h+arg_10]
0x140091856  add     rsp, 30h
0x14009185a  pop     rdi
0x14009185b  pop     rsi
0x14009185c  pop     rbp
0x14009185d  retn
```
