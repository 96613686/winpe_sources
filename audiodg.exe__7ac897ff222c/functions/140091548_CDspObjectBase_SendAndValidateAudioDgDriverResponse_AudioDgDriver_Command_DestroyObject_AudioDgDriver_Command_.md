# CDspObjectBase::SendAndValidateAudioDgDriverResponse<AudioDgDriver_Command_DestroyObject>(AudioDgDriver_Command_DestroyObject *)

- ea: `0x140091548`
- end: `0x1400916d9`
- name: `??$SendAndValidateAudioDgDriverResponse@UAudioDgDriver_Command_DestroyObject@@@CDspObjectBase@@QEAAJPEAUAudioDgDriver_Command_DestroyObject@@@Z`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14005166c`

## callees

- `0x1400026b0`
- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x140061904`
- `0x140091548`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400915e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400915e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140091671`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140091671`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009167c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009167c`

## pseudocode

```c
int __fastcall CDspObjectBase::SendAndValidateAudioDgDriverResponse<AudioDgDriver_Command_DestroyObject>(
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
  const char *v20; // r9
  int v21; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD v23; // [rsp+50h] [rbp+8h] BYREF
  int v24; // [rsp+58h] [rbp+10h] BYREF

  *(_DWORD *)a2 = 2;
  *(_QWORD *)(a2 + 8) = a1[5];
  *(_DWORD *)(a2 + 16) = 24;
  v4 = (_DWORD *)a1[2];
  if ( *v4 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v4) )
  {
    v23 = *(_DWORD *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_1400D28AB,
      v5,
      v6,
      (__int64)&v23);
  }
  if ( (*(int (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[3] + 24LL))(a1[3], a2, 24) < 0 )
  {
    v8 = (_DWORD *)a1[2];
    if ( *v8 > 2u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v7) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v10 = a1[3];
      v23 = CurrentProcessId;
      v24 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v10 + 24LL))(v10, a2, 24);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v8,
        (unsigned int)byte_1400D28E3,
        v11,
        v12,
        (__int64)&v24,
        (__int64)&v23);
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[3] + 24LL))(a1[3], a2, 24);
    v14 = a1[3];
    v15 = (v13 & 0x1FFF0000) == 458752;
    v16 = *(unsigned __int16 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v14 + 24LL);
    if ( v15 )
      v17 = v16(v14, a2, 24);
    else
      v17 = ((__int64 (__fastcall *)(__int64, __int64, __int64))v16)(v14, a2, 24);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v17);
  }
  if ( *(_DWORD *)a2 == 2 )
  {
    v20 = (const char *)*(unsigned int *)(a2 + 4);
    if ( (int)v20 >= 0 )
      return 0;
    else
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x9A,
               (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\DspObjectBase.h",
               v20,
               v21);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\DspObjectBase.h",
      (const char *)0xC000000DLL,
      v21);
    return -1073741811;
  }
}

```

## disassembly

```asm
0x140091548  mov     [rsp+arg_10], rbx
0x14009154d  push    rbp
0x14009154e  push    rsi
0x14009154f  push    rdi
0x140091550  sub     rsp, 30h
0x140091554  mov     dword ptr [rdx], 2
0x14009155a  mov     ebp, 18h
0x14009155f  mov     rax, [rcx+28h]
0x140091563  mov     rbx, rdx
0x140091566  mov     [rdx+8], rax
0x14009156a  mov     rdi, rcx
0x14009156d  mov     [rdx+10h], ebp
0x140091570  mov     r8, [rcx+10h]
0x140091574  mov     eax, [r8]
0x140091577  cmp     eax, 5
0x14009157a  jbe     short loc_1400915AC
0x14009157c  mov     edx, 100000h
0x140091581  mov     rcx, r8
0x140091584  call    _tlgKeywordOn
0x140091589  test    al, al
0x14009158b  jz      short loc_1400915AC
0x14009158d  mov     eax, [rbx]
0x14009158f  lea     rdx, byte_1400D28AB
0x140091596  mov     [rsp+48h+arg_0], eax
0x14009159a  mov     rcx, r8
0x14009159d  lea     rax, [rsp+48h+arg_0]
0x1400915a2  mov     qword ptr [rsp+48h+var_28], rax
0x1400915a7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1400915ac  mov     rcx, [rdi+18h]
0x1400915b0  mov     r8, rbp
0x1400915b3  mov     rdx, rbx
0x1400915b6  mov     rax, [rcx]
0x1400915b9  mov     rax, [rax+18h]
0x1400915bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400915c2  test    eax, eax
0x1400915c4  jns     loc_140091682
0x1400915ca  mov     rsi, [rdi+10h]
0x1400915ce  mov     eax, [rsi]
0x1400915d0  cmp     eax, 2
0x1400915d3  jbe     short loc_14009162D
0x1400915d5  mov     edx, 100000h
0x1400915da  mov     rcx, rsi
0x1400915dd  call    _tlgKeywordOn
0x1400915e2  test    al, al
0x1400915e4  jz      short loc_14009162D
0x1400915e6  call    cs:__imp_GetCurrentProcessId
0x1400915ec  mov     rcx, [rdi+18h]
0x1400915f0  mov     r8, rbp
0x1400915f3  mov     [rsp+48h+arg_0], eax
0x1400915f7  mov     rdx, rbx
0x1400915fa  mov     rax, [rcx]
0x1400915fd  mov     rax, [rax+18h]
0x140091601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140091606  mov     [rsp+48h+arg_8], eax
0x14009160a  lea     rdx, byte_1400D28E3
0x140091611  lea     rax, [rsp+48h+arg_0]
0x140091616  mov     rcx, rsi
0x140091619  mov     [rsp+48h+var_20], rax
0x14009161e  lea     rax, [rsp+48h+arg_8]
0x140091623  mov     qword ptr [rsp+48h+var_28], rax; int
0x140091628  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14009162d  mov     rcx, [rdi+18h]
0x140091631  mov     r8, rbp
0x140091634  mov     rdx, rbx
0x140091637  mov     rax, [rcx]
0x14009163a  mov     rax, [rax+18h]
0x14009163e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140091643  mov     rcx, [rdi+18h]
0x140091647  and     eax, 1FFF0000h
0x14009164c  cmp     eax, 70000h
0x140091651  mov     r8, rbp
0x140091654  mov     rdx, rbx
0x140091657  mov     r9, [rcx]
0x14009165a  mov     rax, [r9+18h]
0x14009165e  jnz     short loc_14009166A
0x140091660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140091665  movzx   edi, ax
0x140091668  jmp     short loc_140091671
0x14009166a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009166f  mov     edi, eax
0x140091671  call    cs:__imp_GetCurrentProcess
0x140091677  mov     rcx, rax; hProcess
0x14009167a  mov     edx, edi; uExitCode
0x14009167c  call    cs:__imp_TerminateProcess
0x140091682  cmp     dword ptr [rbx], 2
0x140091685  jz      short loc_1400916A9
0x140091687  mov     rcx, [rsp+48h]; this
0x14009168c  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140091693  mov     ebx, 0C000000Dh
0x140091698  mov     edx, 99h; void *
0x14009169d  mov     r9d, ebx; char *
0x1400916a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400916a5  mov     eax, ebx
0x1400916a7  jmp     short loc_1400916CC
0x1400916a9  mov     r9d, [rbx+4]; char *
0x1400916ad  test    r9d, r9d
0x1400916b0  jns     short loc_1400916CA
0x1400916b2  mov     rcx, [rsp+48h]; this
0x1400916b7  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x1400916be  mov     edx, 9Ah; void *
0x1400916c3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1400916c8  jmp     short loc_1400916CC
0x1400916ca  xor     eax, eax
0x1400916cc  mov     rbx, [rsp+48h+arg_10]
0x1400916d1  add     rsp, 30h
0x1400916d5  pop     rdi
0x1400916d6  pop     rsi
0x1400916d7  pop     rbp
0x1400916d8  retn
```
