# CAudioPumpDspResourceManager::ReleasePumpContext(unsigned __int64)

- ea: `0x1400903c0`
- end: `0x140090536`
- name: `?ReleasePumpContext@CAudioPumpDspResourceManager@@QEAAJ_K@Z`
- size: `374`
- prototype: `__int64 __fastcall(CAudioPumpDspResourceManager *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14005afb8`

## callees

- `0x140002710`
- `0x14003de5c`
- `0x1400903c0`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009044d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14009044d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140090512`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140090512`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009051d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14009051d`

## pseudocode

```c
__int64 __fastcall CAudioPumpDspResourceManager::ReleasePumpContext(CAudioPumpDspResourceManager *this, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // r8
  _DWORD *v5; // rbx
  DWORD CurrentProcessId; // eax
  __int64 v7; // rcx
  int v8; // r8d
  int v9; // r9d
  int v10; // eax
  __int64 v11; // rcx
  bool v12; // zf
  unsigned __int16 (__fastcall *v13)(__int64, GUID *, __int64); // rax
  UINT v14; // ebx
  HANDLE CurrentProcess; // rax
  GUID v17; // [rsp+40h] [rbp-20h] BYREF
  int v18; // [rsp+50h] [rbp-10h]
  int v19; // [rsp+54h] [rbp-Ch]
  __int64 v20; // [rsp+58h] [rbp-8h]
  DWORD v21; // [rsp+80h] [rbp+20h] BYREF
  int v22; // [rsp+88h] [rbp+28h] BYREF
  __int64 v23; // [rsp+90h] [rbp+30h] BYREF

  v20 = a2;
  v3 = *((_QWORD *)this + 15);
  v17 = GUID_3c58e72b_cb3c_4076_93e8_9c528830f2d2;
  v18 = 10;
  v19 = 2;
  v23 = 0;
  if ( (*(int (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v3 + 40LL))(v3, &v17, 32) < 0 )
  {
    v5 = (_DWORD *)*((_QWORD *)this + 11);
    if ( *v5 > 2u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 11), 0x100000, v4) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v7 = *((_QWORD *)this + 15);
      v21 = CurrentProcessId;
      v22 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v7 + 40LL))(
              v7,
              &v17,
              32,
              0,
              0,
              &v23);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v5,
        (unsigned int)byte_1400D2759,
        v8,
        v9,
        (__int64)&v22,
        (__int64)&v21);
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64, _QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 15) + 40LL))(
            *((_QWORD *)this + 15),
            &v17,
            32,
            0,
            0,
            &v23);
    v11 = *((_QWORD *)this + 15);
    v12 = (v10 & 0x1FFF0000) == 458752;
    v13 = *(unsigned __int16 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v11 + 40LL);
    if ( v12 )
      v14 = v13(v11, &v17, 32);
    else
      v14 = ((__int64 (__fastcall *)(__int64, GUID *, __int64))v13)(v11, &v17, 32);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v14);
  }
  return 0;
}

```

## disassembly

```asm
0x1400903c0  mov     [rsp-18h+arg_18], rbx
0x1400903c5  push    rbp
0x1400903c6  push    rdi
0x1400903c7  push    r14
0x1400903c9  mov     rbp, rsp
0x1400903cc  sub     rsp, 60h
0x1400903d0  movups  xmm0, xmmword ptr cs:_GUID_3c58e72b_cb3c_4076_93e8_9c528830f2d2.Data1
0x1400903d7  mov     [rbp+var_8], rdx
0x1400903db  mov     rdi, rcx
0x1400903de  mov     rcx, [rcx+78h]
0x1400903e2  lea     rdx, [rbp+arg_10]
0x1400903e6  mov     [rsp+60h+var_38], rdx
0x1400903eb  xor     r9d, r9d
0x1400903ee  movdqu  [rbp+var_20], xmm0
0x1400903f3  mov     [rbp+var_10], 0Ah
0x1400903fa  lea     rdx, [rbp+var_20]
0x1400903fe  mov     [rbp+var_C], 2
0x140090405  mov     [rbp+arg_10], 0
0x14009040d  lea     r14d, [r9+20h]
0x140090411  mov     rax, [rcx]
0x140090414  mov     r8d, r14d
0x140090417  mov     [rsp+60h+var_40], 0
0x140090420  mov     rax, [rax+28h]
0x140090424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090429  test    eax, eax
0x14009042b  jns     loc_140090523
0x140090431  mov     rbx, [rdi+58h]
0x140090435  mov     eax, [rbx]
0x140090437  cmp     eax, 2
0x14009043a  jbe     short loc_1400904A6
0x14009043c  mov     edx, 100000h
0x140090441  mov     rcx, rbx
0x140090444  call    _tlgKeywordOn
0x140090449  test    al, al
0x14009044b  jz      short loc_1400904A6
0x14009044d  call    cs:__imp_GetCurrentProcessId
0x140090453  mov     rcx, [rdi+78h]
0x140090457  lea     rdx, [rbp+arg_10]
0x14009045b  mov     [rbp+arg_0], eax
0x14009045e  xor     r9d, r9d
0x140090461  mov     [rsp+60h+var_38], rdx
0x140090466  mov     r8d, r14d
0x140090469  lea     rdx, [rbp+var_20]
0x14009046d  mov     [rsp+60h+var_40], 0
0x140090476  mov     rax, [rcx]
0x140090479  mov     rax, [rax+28h]
0x14009047d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090482  mov     [rbp+arg_8], eax
0x140090485  lea     rdx, byte_1400D2759
0x14009048c  lea     rax, [rbp+arg_0]
0x140090490  mov     rcx, rbx
0x140090493  mov     [rsp+60h+var_38], rax
0x140090498  lea     rax, [rbp+arg_8]
0x14009049c  mov     [rsp+60h+var_40], rax
0x1400904a1  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400904a6  mov     rcx, [rdi+78h]
0x1400904aa  lea     rdx, [rbp+arg_10]
0x1400904ae  mov     [rsp+60h+var_38], rdx
0x1400904b3  xor     r9d, r9d
0x1400904b6  mov     r8, r14
0x1400904b9  mov     [rsp+60h+var_40], 0
0x1400904c2  lea     rdx, [rbp+var_20]
0x1400904c6  mov     rax, [rcx]
0x1400904c9  mov     rax, [rax+28h]
0x1400904cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400904d2  mov     rcx, [rdi+78h]
0x1400904d6  lea     rdx, [rbp+var_20]
0x1400904da  and     eax, 1FFF0000h
0x1400904df  xor     r9d, r9d
0x1400904e2  cmp     eax, 70000h
0x1400904e7  mov     r8, r14
0x1400904ea  lea     rax, [rbp+arg_10]
0x1400904ee  mov     r10, [rcx]
0x1400904f1  mov     [rsp+60h+var_38], rax
0x1400904f6  mov     [rsp+60h+var_40], r9
0x1400904fb  mov     rax, [r10+28h]
0x1400904ff  jnz     short loc_14009050B
0x140090501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090506  movzx   ebx, ax
0x140090509  jmp     short loc_140090512
0x14009050b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090510  mov     ebx, eax
0x140090512  call    cs:__imp_GetCurrentProcess
0x140090518  mov     rcx, rax; hProcess
0x14009051b  mov     edx, ebx; uExitCode
0x14009051d  call    cs:__imp_TerminateProcess
0x140090523  mov     rbx, [rsp+60h+arg_18]
0x14009052b  xor     eax, eax
0x14009052d  add     rsp, 60h
0x140090531  pop     r14
0x140090533  pop     rdi
0x140090534  pop     rbp
0x140090535  retn
```
