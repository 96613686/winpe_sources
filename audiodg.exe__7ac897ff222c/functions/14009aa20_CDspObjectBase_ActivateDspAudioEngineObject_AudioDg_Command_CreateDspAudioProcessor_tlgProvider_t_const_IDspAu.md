# CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspAudioProcessor>(_tlgProvider_t const *,IDspAudioEngine *,uint,AudioDg_Command_CreateDspAudioProcessor *)

- ea: `0x14009aa20`
- end: `0x14009ac0d`
- name: `??$ActivateDspAudioEngineObject@UAudioDg_Command_CreateDspAudioProcessor@@@CDspObjectBase@@QEAAJPEBU_tlgProvider_t@@PEAUIDspAudioEngine@@IPEAUAudioDg_Command_CreateDspAudioProcessor@@@Z`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14009aff0`

## callees

- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14004f178`
- `0x14009aa20`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009ab00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009ab00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009ab88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009ab88`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009ab93`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009ab93`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspAudioProcessor>(
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
  v10[4] = 36;
  v10[7] = a4;
  v11 = (_DWORD *)a1[2];
  if ( *v11 > 5u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v11) )
  {
    v31 = v10[6];
    v29[0] = *v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned int)byte_1400D3925,
      v12,
      v13,
      (__int64)v29,
      (__int64)&v31);
  }
  if ( (*(int (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, v10, 36) < 0 )
  {
    v15 = (_DWORD *)a1[2];
    if ( *v15 > 2u && (unsigned __int8)tlgKeywordOn(a1[2], 0x100000, v14) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v17 = *v9;
      v31 = CurrentProcessId;
      v29[0] = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v17 + 24LL))(v17, v10, 36);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v15,
        (unsigned int)&word_1400D38EE,
        v18,
        v19,
        (__int64)v29,
        (__int64)&v31);
    }
    v20 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, v10, 36);
    v21 = *v9;
    v22 = (v20 & 0x1FFF0000) == 458752;
    v23 = *(unsigned __int16 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)*v9 + 24LL);
    if ( v22 )
      v24 = v23(v21, v10, 36);
    else
      v24 = ((__int64 (__fastcall *)(__int64, _DWORD *, __int64))v23)(v21, v10, 36);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v24);
  }
  if ( *v10 != 4 || v10[6] != 8 || v10[8] >= 2u )
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
0x14009aa20  mov     [rsp+arg_8], rbx
0x14009aa25  mov     [rsp+arg_10], rbp
0x14009aa2a  push    rsi
0x14009aa2b  push    rdi
0x14009aa2c  push    r14
0x14009aa2e  sub     rsp, 40h
0x14009aa32  cmp     qword ptr [rcx+28h], 0
0x14009aa37  mov     edi, r9d
0x14009aa3a  mov     rsi, rcx
0x14009aa3d  jz      short loc_14009AA4E
0x14009aa3f  mov     ebx, 8000FFFFh
0x14009aa44  mov     edx, 38h ; '8'
0x14009aa49  jmp     loc_14009ABE4
0x14009aa4e  mov     [rcx+10h], rdx
0x14009aa52  lea     r14, [rcx+20h]
0x14009aa56  mov     rcx, r14
0x14009aa59  mov     rdx, r8
0x14009aa5c  call    ??4?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIUnknown@@@Z; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(IUnknown *)
0x14009aa61  mov     rbx, [rsp+58h+arg_20]
0x14009aa69  mov     ebp, 24h ; '$'
0x14009aa6e  mov     dword ptr [rbx], 4
0x14009aa74  mov     [rbx+10h], ebp
0x14009aa77  mov     [rbx+1Ch], edi
0x14009aa7a  mov     r8, [rsi+10h]
0x14009aa7e  mov     eax, [r8]
0x14009aa81  cmp     eax, 5
0x14009aa84  jbe     short loc_14009AAC7
0x14009aa86  mov     edx, 100000h
0x14009aa8b  mov     rcx, r8
0x14009aa8e  call    _tlgKeywordOn
0x14009aa93  test    al, al
0x14009aa95  jz      short loc_14009AAC7
0x14009aa97  mov     eax, [rbx+18h]
0x14009aa9a  lea     rdx, byte_1400D3925
0x14009aaa1  mov     [rsp+58h+arg_0], eax
0x14009aaa5  mov     rcx, r8
0x14009aaa8  mov     eax, [rbx]
0x14009aaaa  mov     [rsp+58h+var_28], eax
0x14009aaae  lea     rax, [rsp+58h+arg_0]
0x14009aab3  mov     [rsp+58h+var_30], rax
0x14009aab8  lea     rax, [rsp+58h+var_28]
0x14009aabd  mov     qword ptr [rsp+58h+var_38], rax
0x14009aac2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14009aac7  mov     rcx, [r14]
0x14009aaca  mov     r8, rbp
0x14009aacd  mov     rdx, rbx
0x14009aad0  mov     rax, [rcx]
0x14009aad3  mov     rax, [rax+18h]
0x14009aad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009aadc  test    eax, eax
0x14009aade  jns     loc_14009AB99
0x14009aae4  mov     rdi, [rsi+10h]
0x14009aae8  mov     eax, [rdi]
0x14009aaea  cmp     eax, 2
0x14009aaed  jbe     short loc_14009AB46
0x14009aaef  mov     edx, 100000h
0x14009aaf4  mov     rcx, rdi
0x14009aaf7  call    _tlgKeywordOn
0x14009aafc  test    al, al
0x14009aafe  jz      short loc_14009AB46
0x14009ab00  call    cs:__imp_GetCurrentProcessId
0x14009ab06  mov     rcx, [r14]
0x14009ab09  mov     r8, rbp
0x14009ab0c  mov     [rsp+58h+arg_0], eax
0x14009ab10  mov     rdx, rbx
0x14009ab13  mov     rax, [rcx]
0x14009ab16  mov     rax, [rax+18h]
0x14009ab1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009ab1f  mov     [rsp+58h+var_28], eax
0x14009ab23  lea     rdx, word_1400D38EE
0x14009ab2a  lea     rax, [rsp+58h+arg_0]
0x14009ab2f  mov     rcx, rdi
0x14009ab32  mov     [rsp+58h+var_30], rax
0x14009ab37  lea     rax, [rsp+58h+var_28]
0x14009ab3c  mov     qword ptr [rsp+58h+var_38], rax; int
0x14009ab41  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14009ab46  mov     rcx, [r14]
0x14009ab49  mov     r8, rbp
0x14009ab4c  mov     rdx, rbx
0x14009ab4f  mov     rax, [rcx]
0x14009ab52  mov     rax, [rax+18h]
0x14009ab56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009ab5b  mov     rcx, [r14]
0x14009ab5e  and     eax, 1FFF0000h
0x14009ab63  cmp     eax, 70000h
0x14009ab68  mov     r8, rbp
0x14009ab6b  mov     rdx, rbx
0x14009ab6e  mov     r9, [rcx]
0x14009ab71  mov     rax, [r9+18h]
0x14009ab75  jnz     short loc_14009AB81
0x14009ab77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009ab7c  movzx   edi, ax
0x14009ab7f  jmp     short loc_14009AB88
0x14009ab81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009ab86  mov     edi, eax
0x14009ab88  call    cs:__imp_GetCurrentProcess
0x14009ab8e  mov     rcx, rax; hProcess
0x14009ab91  mov     edx, edi; uExitCode
0x14009ab93  call    cs:__imp_TerminateProcess
0x14009ab99  cmp     dword ptr [rbx], 4
0x14009ab9c  jnz     short loc_14009ABDA
0x14009ab9e  cmp     dword ptr [rbx+18h], 8
0x14009aba2  jnz     short loc_14009ABDA
0x14009aba4  cmp     dword ptr [rbx+20h], 2
0x14009aba8  jnb     short loc_14009ABDA
0x14009abaa  mov     edi, [rbx+4]
0x14009abad  test    edi, edi
0x14009abaf  jns     short loc_14009ABCE
0x14009abb1  mov     rcx, [rsp+58h]; this
0x14009abb6  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14009abbd  mov     r9d, edi; char *
0x14009abc0  mov     edx, 4Ah ; 'J'; void *
0x14009abc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009abca  mov     eax, edi
0x14009abcc  jmp     short loc_14009ABFA
0x14009abce  mov     rax, [rbx+8]
0x14009abd2  mov     [rsi+28h], rax
0x14009abd6  xor     eax, eax
0x14009abd8  jmp     short loc_14009ABFA
0x14009abda  mov     ebx, 80070057h
0x14009abdf  mov     edx, 49h ; 'I'; void *
0x14009abe4  mov     rcx, [rsp+58h]; this
0x14009abe9  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14009abf0  mov     r9d, ebx; char *
0x14009abf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009abf8  mov     eax, ebx
0x14009abfa  mov     rbx, [rsp+58h+arg_8]
0x14009abff  mov     rbp, [rsp+58h+arg_10]
0x14009ac04  add     rsp, 40h
0x14009ac08  pop     r14
0x14009ac0a  pop     rdi
0x14009ac0b  pop     rsi
0x14009ac0c  retn
```
