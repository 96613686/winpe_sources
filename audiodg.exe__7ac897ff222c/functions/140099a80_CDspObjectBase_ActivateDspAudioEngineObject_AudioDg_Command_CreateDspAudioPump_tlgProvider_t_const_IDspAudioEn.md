# CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspAudioPump>(_tlgProvider_t const *,IDspAudioEngine *,uint,AudioDg_Command_CreateDspAudioPump *)

- ea: `0x140099a80`
- end: `0x140099c67`
- name: `??$ActivateDspAudioEngineObject@UAudioDg_Command_CreateDspAudioPump@@@CDspObjectBase@@QEAAJPEBU_tlgProvider_t@@PEAUIDspAudioEngine@@IPEAUAudioDg_Command_CreateDspAudioPump@@@Z`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14009a850`

## callees

- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14004f178`
- `0x140099a80`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140099b60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140099b60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140099be8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140099be8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140099bf3`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140099bf3`

## pseudocode

```c
__int64 __fastcall CDspObjectBase::ActivateDspAudioEngineObject<AudioDg_Command_CreateDspAudioPump>(
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
      (unsigned int)byte_1400D37C9,
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
        (unsigned int)word_1400D3792,
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
  if ( *v10 != 4 || v10[6] != 7 )
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
0x140099a80  mov     [rsp+arg_8], rbx
0x140099a85  mov     [rsp+arg_10], rbp
0x140099a8a  push    rsi
0x140099a8b  push    rdi
0x140099a8c  push    r14
0x140099a8e  sub     rsp, 40h
0x140099a92  cmp     qword ptr [rcx+28h], 0
0x140099a97  mov     edi, r9d
0x140099a9a  mov     rsi, rcx
0x140099a9d  jz      short loc_140099AAE
0x140099a9f  mov     ebx, 8000FFFFh
0x140099aa4  mov     edx, 38h ; '8'
0x140099aa9  jmp     loc_140099C3E
0x140099aae  mov     [rcx+10h], rdx
0x140099ab2  lea     r14, [rcx+20h]
0x140099ab6  mov     rcx, r14
0x140099ab9  mov     rdx, r8
0x140099abc  call    ??4?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIUnknown@@@Z; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(IUnknown *)
0x140099ac1  mov     rbx, [rsp+58h+arg_20]
0x140099ac9  mov     ebp, 20h ; ' '
0x140099ace  mov     dword ptr [rbx], 4
0x140099ad4  mov     [rbx+10h], ebp
0x140099ad7  mov     [rbx+1Ch], edi
0x140099ada  mov     r8, [rsi+10h]
0x140099ade  mov     eax, [r8]
0x140099ae1  cmp     eax, 5
0x140099ae4  jbe     short loc_140099B27
0x140099ae6  mov     edx, 100000h
0x140099aeb  mov     rcx, r8
0x140099aee  call    _tlgKeywordOn
0x140099af3  test    al, al
0x140099af5  jz      short loc_140099B27
0x140099af7  mov     eax, [rbx+18h]
0x140099afa  lea     rdx, byte_1400D37C9
0x140099b01  mov     [rsp+58h+arg_0], eax
0x140099b05  mov     rcx, r8
0x140099b08  mov     eax, [rbx]
0x140099b0a  mov     [rsp+58h+var_28], eax
0x140099b0e  lea     rax, [rsp+58h+arg_0]
0x140099b13  mov     [rsp+58h+var_30], rax
0x140099b18  lea     rax, [rsp+58h+var_28]
0x140099b1d  mov     qword ptr [rsp+58h+var_38], rax
0x140099b22  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140099b27  mov     rcx, [r14]
0x140099b2a  mov     r8, rbp
0x140099b2d  mov     rdx, rbx
0x140099b30  mov     rax, [rcx]
0x140099b33  mov     rax, [rax+18h]
0x140099b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140099b3c  test    eax, eax
0x140099b3e  jns     loc_140099BF9
0x140099b44  mov     rdi, [rsi+10h]
0x140099b48  mov     eax, [rdi]
0x140099b4a  cmp     eax, 2
0x140099b4d  jbe     short loc_140099BA6
0x140099b4f  mov     edx, 100000h
0x140099b54  mov     rcx, rdi
0x140099b57  call    _tlgKeywordOn
0x140099b5c  test    al, al
0x140099b5e  jz      short loc_140099BA6
0x140099b60  call    cs:__imp_GetCurrentProcessId
0x140099b66  mov     rcx, [r14]
0x140099b69  mov     r8, rbp
0x140099b6c  mov     [rsp+58h+arg_0], eax
0x140099b70  mov     rdx, rbx
0x140099b73  mov     rax, [rcx]
0x140099b76  mov     rax, [rax+18h]
0x140099b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140099b7f  mov     [rsp+58h+var_28], eax
0x140099b83  lea     rdx, word_1400D3792
0x140099b8a  lea     rax, [rsp+58h+arg_0]
0x140099b8f  mov     rcx, rdi
0x140099b92  mov     [rsp+58h+var_30], rax
0x140099b97  lea     rax, [rsp+58h+var_28]
0x140099b9c  mov     qword ptr [rsp+58h+var_38], rax; int
0x140099ba1  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140099ba6  mov     rcx, [r14]
0x140099ba9  mov     r8, rbp
0x140099bac  mov     rdx, rbx
0x140099baf  mov     rax, [rcx]
0x140099bb2  mov     rax, [rax+18h]
0x140099bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140099bbb  mov     rcx, [r14]
0x140099bbe  and     eax, 1FFF0000h
0x140099bc3  cmp     eax, 70000h
0x140099bc8  mov     r8, rbp
0x140099bcb  mov     rdx, rbx
0x140099bce  mov     r9, [rcx]
0x140099bd1  mov     rax, [r9+18h]
0x140099bd5  jnz     short loc_140099BE1
0x140099bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140099bdc  movzx   edi, ax
0x140099bdf  jmp     short loc_140099BE8
0x140099be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140099be6  mov     edi, eax
0x140099be8  call    cs:__imp_GetCurrentProcess
0x140099bee  mov     rcx, rax; hProcess
0x140099bf1  mov     edx, edi; uExitCode
0x140099bf3  call    cs:__imp_TerminateProcess
0x140099bf9  cmp     dword ptr [rbx], 4
0x140099bfc  jnz     short loc_140099C34
0x140099bfe  cmp     dword ptr [rbx+18h], 7
0x140099c02  jnz     short loc_140099C34
0x140099c04  mov     edi, [rbx+4]
0x140099c07  test    edi, edi
0x140099c09  jns     short loc_140099C28
0x140099c0b  mov     rcx, [rsp+58h]; this
0x140099c10  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140099c17  mov     r9d, edi; char *
0x140099c1a  mov     edx, 4Ah ; 'J'; void *
0x140099c1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140099c24  mov     eax, edi
0x140099c26  jmp     short loc_140099C54
0x140099c28  mov     rax, [rbx+8]
0x140099c2c  mov     [rsi+28h], rax
0x140099c30  xor     eax, eax
0x140099c32  jmp     short loc_140099C54
0x140099c34  mov     ebx, 80070057h
0x140099c39  mov     edx, 49h ; 'I'; void *
0x140099c3e  mov     rcx, [rsp+58h]; this
0x140099c43  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140099c4a  mov     r9d, ebx; char *
0x140099c4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140099c52  mov     eax, ebx
0x140099c54  mov     rbx, [rsp+58h+arg_8]
0x140099c59  mov     rbp, [rsp+58h+arg_10]
0x140099c5e  add     rsp, 40h
0x140099c62  pop     r14
0x140099c64  pop     rdi
0x140099c65  pop     rsi
0x140099c66  retn
```
