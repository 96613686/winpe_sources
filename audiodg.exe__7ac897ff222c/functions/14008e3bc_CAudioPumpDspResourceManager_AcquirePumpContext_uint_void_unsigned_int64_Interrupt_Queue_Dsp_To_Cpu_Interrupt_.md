# CAudioPumpDspResourceManager::AcquirePumpContext(uint,void *,unsigned __int64 *,Interrupt_Queue<Dsp_To_Cpu_Interrupt_Queue_Entry,5> * *)

- ea: `0x14008e3bc`
- end: `0x14008e5ba`
- name: `?AcquirePumpContext@CAudioPumpDspResourceManager@@QEAAJIPEAXPEA_KPEAPEAU?$Interrupt_Queue@UDsp_To_Cpu_Interrupt_Queue_Entry@@$04@@@Z`
- size: `510`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140054964`

## callees

- `0x140002710`
- `0x14000c33c`
- `0x14003de5c`
- `0x14005d0e0`
- `0x14008e3bc`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14008e477`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14008e477`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14008e537`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14008e537`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14008e542`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14008e542`

## pseudocode

```c
__int64 __fastcall CAudioPumpDspResourceManager::AcquirePumpContext(
        __int64 a1,
        int a2,
        __int64 a3,
        _QWORD *a4,
        _QWORD *a5)
{
  __int64 v6; // rcx
  __int64 v8; // r8
  _DWORD *v9; // rbx
  DWORD CurrentProcessId; // eax
  __int64 v11; // rcx
  int v12; // r8d
  int v13; // r9d
  int v14; // eax
  __int64 v15; // rcx
  bool v16; // zf
  unsigned __int16 (__fastcall *v17)(__int64, GUID *, __int64, __int128 *, __int64, __int64 *); // rax
  UINT v18; // ebx
  HANDLE CurrentProcess; // rax
  __int64 v20; // rdx
  int v22; // [rsp+20h] [rbp-61h]
  __int64 v23; // [rsp+40h] [rbp-41h] BYREF
  DWORD v24; // [rsp+48h] [rbp-39h] BYREF
  int v25; // [rsp+4Ch] [rbp-35h] BYREF
  __int128 v26; // [rsp+50h] [rbp-31h] BYREF
  __int64 v27; // [rsp+60h] [rbp-21h]
  GUID v28; // [rsp+68h] [rbp-19h] BYREF
  int v29; // [rsp+78h] [rbp-9h]
  int v30; // [rsp+7Ch] [rbp-5h]
  __int64 v31; // [rsp+80h] [rbp-1h]
  int v32; // [rsp+88h] [rbp+7h]
  int v33; // [rsp+8Ch] [rbp+Bh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v32 = a2;
  v6 = *(_QWORD *)(a1 + 120);
  v28 = GUID_3c58e72b_cb3c_4076_93e8_9c528830f2d2;
  v31 = a3;
  v33 = 0;
  v27 = 0;
  v23 = 0;
  v26 = 0;
  v29 = 9;
  v30 = 1;
  v22 = 24;
  if ( (*(int (__fastcall **)(__int64, GUID *, __int64, __int128 *))(*(_QWORD *)v6 + 40LL))(v6, &v28, 40, &v26) < 0 )
  {
    v9 = *(_DWORD **)(a1 + 88);
    if ( *v9 > 2u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 88), 0x100000, v8) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v11 = *(_QWORD *)(a1 + 120);
      v24 = CurrentProcessId;
      v25 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, __int128 *, __int64, __int64 *))(*(_QWORD *)v11 + 40LL))(
              v11,
              &v28,
              40,
              &v26,
              24,
              &v23);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v9,
        (unsigned int)word_1400D2722,
        v12,
        v13,
        (__int64)&v25,
        (__int64)&v24);
    }
    v14 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64, __int128 *, __int64, __int64 *))(**(_QWORD **)(a1 + 120)
                                                                                             + 40LL))(
            *(_QWORD *)(a1 + 120),
            &v28,
            40,
            &v26,
            24,
            &v23);
    v15 = *(_QWORD *)(a1 + 120);
    v16 = (v14 & 0x1FFF0000) == 458752;
    v17 = *(unsigned __int16 (__fastcall **)(__int64, GUID *, __int64, __int128 *, __int64, __int64 *))(*(_QWORD *)v15 + 40LL);
    if ( v16 )
      v18 = v17(v15, &v28, 40, &v26, 24, &v23);
    else
      v18 = ((__int64 (__fastcall *)(__int64, GUID *, __int64, __int128 *, __int64, __int64 *))v17)(
              v15,
              &v28,
              40,
              &v26,
              24,
              &v23);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v18);
  }
  if ( v23 != 24 )
  {
    v20 = 541;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\audiopumpdspresourcemanager.cpp",
      (const char *)0x8000FFFFLL,
      v22);
    return 2147549183LL;
  }
  v16 = (_DWORD)v27 == 5;
  *a4 = v26;
  if ( !v16 )
  {
    v20 = 548;
    goto LABEL_11;
  }
  if ( HIDWORD(v27) != 208 )
  {
    v20 = 549;
    goto LABEL_11;
  }
  *a5 = *((_QWORD *)&v26 + 1);
  return 0;
}

```

## disassembly

```asm
0x14008e3bc  push    rbp
0x14008e3be  push    rbx
0x14008e3bf  push    rsi
0x14008e3c0  push    rdi
0x14008e3c1  push    r12
0x14008e3c3  push    r14
0x14008e3c5  push    r15
0x14008e3c7  lea     rbp, [rsp-1Fh]
0x14008e3cc  sub     rsp, 0A0h
0x14008e3d3  mov     rax, cs:__security_cookie
0x14008e3da  xor     rax, rsp
0x14008e3dd  mov     [rbp+4Fh+var_40], rax
0x14008e3e1  movups  xmm0, xmmword ptr cs:_GUID_3c58e72b_cb3c_4076_93e8_9c528830f2d2.Data1
0x14008e3e8  mov     rsi, [rbp+4Fh+arg_20]
0x14008e3ec  xor     eax, eax
0x14008e3ee  mov     [rbp+4Fh+var_48], edx
0x14008e3f1  mov     rdi, rcx
0x14008e3f4  mov     rcx, [rcx+78h]
0x14008e3f8  lea     rdx, [rbp+4Fh+var_90]
0x14008e3fc  movdqu  [rbp+4Fh+var_68], xmm0
0x14008e401  mov     [rbp+4Fh+var_50], r8
0x14008e405  mov     r15d, 18h
0x14008e40b  mov     [rbp+4Fh+var_44], eax
0x14008e40e  xorps   xmm0, xmm0
0x14008e411  mov     [rbp+4Fh+var_70], rax
0x14008e415  mov     r14, r9
0x14008e418  mov     [rbp+4Fh+var_90], rax
0x14008e41c  lea     r9, [rbp+4Fh+var_80]
0x14008e420  mov     [rsp+0D0h+var_A8], rdx
0x14008e425  lea     r12d, [r15+10h]
0x14008e429  movups  [rbp+4Fh+var_80], xmm0
0x14008e42d  mov     [rbp+4Fh+var_58], 9
0x14008e434  lea     rdx, [rbp+4Fh+var_68]
0x14008e438  mov     [rbp+4Fh+var_54], 1
0x14008e43f  mov     r8d, r12d
0x14008e442  mov     rax, [rcx]
0x14008e445  mov     qword ptr [rsp+0D0h+var_B0], r15
0x14008e44a  mov     rax, [rax+28h]
0x14008e44e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008e453  test    eax, eax
0x14008e455  jns     loc_14008E548
0x14008e45b  mov     rbx, [rdi+58h]
0x14008e45f  mov     eax, [rbx]
0x14008e461  cmp     eax, 2
0x14008e464  jbe     short loc_14008E4CD
0x14008e466  mov     edx, 100000h
0x14008e46b  mov     rcx, rbx
0x14008e46e  call    _tlgKeywordOn
0x14008e473  test    al, al
0x14008e475  jz      short loc_14008E4CD
0x14008e477  call    cs:__imp_GetCurrentProcessId
0x14008e47d  mov     rcx, [rdi+78h]
0x14008e481  lea     rdx, [rbp+4Fh+var_90]
0x14008e485  mov     [rbp+4Fh+var_88], eax
0x14008e488  lea     r9, [rbp+4Fh+var_80]
0x14008e48c  mov     [rsp+0D0h+var_A8], rdx
0x14008e491  mov     r8d, r12d
0x14008e494  lea     rdx, [rbp+4Fh+var_68]
0x14008e498  mov     qword ptr [rsp+0D0h+var_B0], r15
0x14008e49d  mov     rax, [rcx]
0x14008e4a0  mov     rax, [rax+28h]
0x14008e4a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008e4a9  mov     [rbp+4Fh+var_84], eax
0x14008e4ac  lea     rdx, word_1400D2722
0x14008e4b3  lea     rax, [rbp+4Fh+var_88]
0x14008e4b7  mov     rcx, rbx
0x14008e4ba  mov     [rsp+0D0h+var_A8], rax
0x14008e4bf  lea     rax, [rbp+4Fh+var_84]
0x14008e4c3  mov     qword ptr [rsp+0D0h+var_B0], rax
0x14008e4c8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14008e4cd  mov     rcx, [rdi+78h]
0x14008e4d1  lea     rdx, [rbp+4Fh+var_90]
0x14008e4d5  mov     [rsp+0D0h+var_A8], rdx
0x14008e4da  lea     r9, [rbp+4Fh+var_80]
0x14008e4de  mov     r8, r12
0x14008e4e1  mov     qword ptr [rsp+0D0h+var_B0], r15
0x14008e4e6  lea     rdx, [rbp+4Fh+var_68]
0x14008e4ea  mov     rax, [rcx]
0x14008e4ed  mov     rax, [rax+28h]
0x14008e4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008e4f6  mov     rcx, [rdi+78h]
0x14008e4fa  lea     r9, [rbp+4Fh+var_80]
0x14008e4fe  and     eax, 1FFF0000h
0x14008e503  lea     rdx, [rbp+4Fh+var_68]
0x14008e507  cmp     eax, 70000h
0x14008e50c  mov     r8, r12
0x14008e50f  lea     rax, [rbp+4Fh+var_90]
0x14008e513  mov     r10, [rcx]
0x14008e516  mov     [rsp+0D0h+var_A8], rax
0x14008e51b  mov     qword ptr [rsp+0D0h+var_B0], r15; int
0x14008e520  mov     rax, [r10+28h]
0x14008e524  jnz     short loc_14008E530
0x14008e526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008e52b  movzx   ebx, ax
0x14008e52e  jmp     short loc_14008E537
0x14008e530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008e535  mov     ebx, eax
0x14008e537  call    cs:__imp_GetCurrentProcess
0x14008e53d  mov     rcx, rax; hProcess
0x14008e540  mov     edx, ebx; uExitCode
0x14008e542  call    cs:__imp_TerminateProcess
0x14008e548  cmp     [rbp+4Fh+var_90], r15
0x14008e54c  jz      short loc_14008E56F
0x14008e54e  mov     edx, 21Dh; void *
0x14008e553  mov     rcx, [rbp+57h]; this
0x14008e557  lea     r8, aAvcoreAudiocor_62; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14008e55e  mov     ebx, 8000FFFFh
0x14008e563  mov     r9d, ebx; char *
0x14008e566  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008e56b  mov     eax, ebx
0x14008e56d  jmp     short loc_14008E59C
0x14008e56f  cmp     dword ptr [rbp+4Fh+var_70], 5
0x14008e573  mov     rax, qword ptr [rbp+4Fh+var_80]
0x14008e577  mov     [r14], rax
0x14008e57a  jz      short loc_14008E583
0x14008e57c  mov     edx, 224h
0x14008e581  jmp     short loc_14008E553
0x14008e583  cmp     dword ptr [rbp+4Fh+var_70+4], 0D0h
0x14008e58a  jz      short loc_14008E593
0x14008e58c  mov     edx, 225h
0x14008e591  jmp     short loc_14008E553
0x14008e593  mov     rax, qword ptr [rbp+4Fh+var_80+8]
0x14008e597  mov     [rsi], rax
0x14008e59a  xor     eax, eax
0x14008e59c  mov     rcx, [rbp+4Fh+var_40]
0x14008e5a0  xor     rcx, rsp; StackCookie
0x14008e5a3  call    __security_check_cookie
0x14008e5a8  add     rsp, 0A0h
0x14008e5af  pop     r15
0x14008e5b1  pop     r14
0x14008e5b3  pop     r12
0x14008e5b5  pop     rdi
0x14008e5b6  pop     rsi
0x14008e5b7  pop     rbx
0x14008e5b8  pop     rbp
0x14008e5b9  retn
```
