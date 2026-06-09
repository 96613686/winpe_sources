# CCbsIdleHandler::Start(IUnknown *,wchar_t *)

- ea: `0x1400122d4`
- end: `0x14001252b`
- name: `?Start@CCbsIdleHandler@@UEAAJPEAUIUnknown@@PEA_W@Z`
- size: `599`
- prototype: `__int64 __fastcall(CCbsIdleHandler *__hidden this, struct IUnknown *, wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400122c0`

## callees

- `0x1400023e0`
- `0x140007edc`
- `0x1400122d4`
- `0x140017658`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012452`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140012429`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140012429`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012501`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012501`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400123a7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400123a7`

## string_xrefs

- `0x1400122f7`: `Idle scavenging/repair requested`
- `0x140012343`: `Failed to query TaskHandler services for scavenge/repair status callback`
- `0x140012391`: `Idle scavenge/repair is waiting for StartupProcessing to complete`
- `0x1400123b4`: `Idle scavenge/repair timed out waiting for Startup Processing to complete`
- `0x1400123c2`: `Idle scavenging/repair begins`
- `0x140012469`: `Failed to create idle scavenging/repair thread.`
- `0x140012494`: `Signaling IdleScavenge and/or repair complete, without starting maintenance`
- `0x1400124bf`: `Warning: Unable to mark idle scavenging/repair complete.`

## pseudocode

```c
__int64 __fastcall CCbsIdleHandler::Start(CCbsIdleHandler *this, struct IUnknown *a2, wchar_t *a3)
{
  struct IUnknownVtbl *lpVtbl; // rax
  char *Thread; // r14
  int v7; // r15d
  int v8; // eax
  volatile __int32 *v9; // rsi
  unsigned int v10; // ebx
  const char *v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rax
  char *v16; // rcx
  char *v17; // rcx
  signed int LastError; // eax
  int v19; // eax
  __int64 v21; // [rsp+30h] [rbp-38h] BYREF

  CBSWdsLogLight(0x4000000, 0, 0, "Idle scavenging/repair requested");
  lpVtbl = a2->lpVtbl;
  Thread = 0;
  v21 = 0;
  v7 = 0;
  v8 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a2,
         &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
         &v21);
  v9 = (volatile __int32 *)((char *)this - 56);
  v10 = v8;
  if ( v8 < 0 )
  {
    v11 = "Failed to query TaskHandler services for scavenge/repair status callback";
    v12 = (unsigned int)v8;
LABEL_3:
    CBSWdsLogLight(0x4000000, v12, 1, v11);
    goto LABEL_20;
  }
  if ( _InterlockedExchange(v9 + 10, 1) == 1 )
  {
    v10 = 267009;
  }
  else
  {
    v13 = 0;
    v7 = 1;
    while ( !MakeSureStartupProcessingComplete(0) )
    {
      if ( (unsigned __int64)++v13 >= 0xA )
      {
        v10 = -2146498302;
        v11 = "Idle scavenge/repair timed out waiting for Startup Processing to complete";
        v12 = 2148468994LL;
        goto LABEL_3;
      }
      CBSWdsLogLight(0x4000000, 0, 0, "Idle scavenge/repair is waiting for StartupProcessing to complete");
      Sleep(0x3E8u);
    }
    CBSWdsLogLight(0x4000000, 0, 0, "Idle scavenging/repair begins");
    v14 = *((_QWORD *)this - 4);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    *((_QWORD *)this - 4) = v21;
    v15 = *((_QWORD *)this - 6);
    v21 = 0;
    v16 = (char *)this + *(int *)(v15 + 4) - 48;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 8LL))(v16);
    Thread = (char *)CreateThread(0, 0, StartIdleScavenge, (char *)this - 56, 0, 0);
    if ( !Thread )
    {
      v17 = (char *)this + *(int *)(*((_QWORD *)this - 6) + 4LL) - 48;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 16LL))(v17);
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      v11 = "Failed to create idle scavenging/repair thread.";
      if ( (v10 & 0x80000000) == 0 )
        v10 = -2147467259;
      v12 = v10;
      goto LABEL_3;
    }
    v10 = 0;
    v7 = 0;
  }
LABEL_20:
  if ( v21 )
  {
    CBSWdsLogLight(0x4000000, 0, 0, "Signaling IdleScavenge and/or repair complete, without starting maintenance");
    v19 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v21 + 32LL))(v21, v10);
    if ( v19 < 0 )
      CBSWdsLogLight(0x4000000, (unsigned int)v19, 1, "Warning: Unable to mark idle scavenging/repair complete.");
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  if ( v7 )
    _InterlockedExchange(v9 + 10, 0);
  if ( (unsigned __int64)(Thread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(Thread);
  return v10;
}

```

## disassembly

```asm
0x1400122d4  mov     [rsp+arg_10], rbx
0x1400122d9  push    rsi
0x1400122da  push    rdi
0x1400122db  push    r13
0x1400122dd  push    r14
0x1400122df  push    r15
0x1400122e1  sub     rsp, 40h
0x1400122e5  mov     rax, cs:__security_cookie
0x1400122ec  xor     rax, rsp
0x1400122ef  mov     [rsp+68h+var_30], rax
0x1400122f4  mov     rbx, rdx
0x1400122f7  lea     r9, aIdleScavenging_0; "Idle scavenging/repair requested"
0x1400122fe  mov     rdi, rcx
0x140012301  mov     r13d, 4000000h
0x140012307  mov     ecx, r13d
0x14001230a  xor     r8d, r8d
0x14001230d  xor     edx, edx
0x14001230f  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140012314  mov     rax, [rbx]
0x140012317  lea     r8, [rsp+68h+var_38]
0x14001231c  xor     r14d, r14d
0x14001231f  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x140012326  mov     rcx, rbx
0x140012329  mov     [rsp+68h+var_38], r14
0x14001232e  xor     r15d, r15d
0x140012331  mov     rax, [rax]
0x140012334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012339  lea     rsi, [rdi-38h]
0x14001233d  mov     ebx, eax
0x14001233f  test    eax, eax
0x140012341  jns     short loc_14001235D
0x140012343  lea     r9, aFailedToQueryT; "Failed to query TaskHandler services fo"...
0x14001234a  mov     edx, eax
0x14001234c  lea     r8d, [r14+1]
0x140012350  mov     ecx, r13d
0x140012353  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140012358  jmp     loc_140012487
0x14001235d  mov     eax, 1
0x140012362  xchg    eax, [rsi+28h]
0x140012365  cmp     eax, 1
0x140012368  jnz     short loc_140012374
0x14001236a  mov     ebx, 41301h
0x14001236f  jmp     loc_140012487
0x140012374  xor     ebx, ebx
0x140012376  lea     r15d, [rbx+1]
0x14001237a  xor     ecx, ecx; bool
0x14001237c  call    ?MakeSureStartupProcessingComplete@@YA_N_N@Z; MakeSureStartupProcessingComplete(bool)
0x140012381  mov     ecx, r13d
0x140012384  test    al, al
0x140012386  jnz     short loc_1400123C2
0x140012388  inc     rbx
0x14001238b  cmp     rbx, 0Ah
0x14001238f  jnb     short loc_1400123AF
0x140012391  lea     r9, aIdleScavengeRe_0; "Idle scavenge/repair is waiting for Sta"...
0x140012398  xor     r8d, r8d
0x14001239b  xor     edx, edx
0x14001239d  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400123a2  mov     ecx, 3E8h; dwMilliseconds
0x1400123a7  call    cs:__imp_Sleep
0x1400123ad  jmp     short loc_14001237A
0x1400123af  mov     ebx, 800F0902h
0x1400123b4  lea     r9, aIdleScavengeRe; "Idle scavenge/repair timed out waiting "...
0x1400123bb  mov     edx, ebx
0x1400123bd  mov     r8d, r15d
0x1400123c0  jmp     short loc_140012353
0x1400123c2  lea     r9, aIdleScavenging_1; "Idle scavenging/repair begins"
0x1400123c9  xor     r8d, r8d
0x1400123cc  xor     edx, edx
0x1400123ce  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400123d3  mov     rcx, [rdi-20h]
0x1400123d7  test    rcx, rcx
0x1400123da  jz      short loc_1400123E8
0x1400123dc  mov     rax, [rcx]
0x1400123df  mov     rax, [rax+10h]
0x1400123e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400123e8  mov     rax, [rsp+68h+var_38]
0x1400123ed  mov     [rdi-20h], rax
0x1400123f1  mov     rax, [rdi-30h]
0x1400123f5  mov     [rsp+68h+var_38], r14
0x1400123fa  movsxd  rcx, dword ptr [rax+4]
0x1400123fe  add     rcx, 0FFFFFFFFFFFFFFD0h
0x140012402  add     rcx, rdi
0x140012405  mov     rax, [rcx]
0x140012408  mov     rax, [rax+8]
0x14001240c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012411  mov     r9, rsi; lpParameter
0x140012414  mov     [rsp+68h+lpThreadId], r14; lpThreadId
0x140012419  lea     r8, ?StartIdleScavenge@@YAKPEAX@Z; lpStartAddress
0x140012420  mov     [rsp+68h+dwCreationFlags], r14d; dwCreationFlags
0x140012425  xor     edx, edx; dwStackSize
0x140012427  xor     ecx, ecx; lpThreadAttributes
0x140012429  call    cs:__imp_CreateThread
0x14001242f  mov     r14, rax
0x140012432  test    rax, rax
0x140012435  jnz     short loc_140012482
0x140012437  mov     rcx, [rdi-30h]
0x14001243b  movsxd  rcx, dword ptr [rcx+4]
0x14001243f  add     rcx, 0FFFFFFFFFFFFFFD0h
0x140012443  add     rcx, rdi
0x140012446  mov     rdx, [rcx]
0x140012449  mov     rax, [rdx+10h]
0x14001244d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012452  call    cs:__imp_GetLastError
0x140012458  mov     ebx, eax
0x14001245a  test    eax, eax
0x14001245c  jle     short loc_140012467
0x14001245e  movzx   ebx, ax
0x140012461  or      ebx, 80070000h
0x140012467  test    ebx, ebx
0x140012469  lea     r9, aFailedToCreate_25; "Failed to create idle scavenging/repair"...
0x140012470  mov     eax, 80004005h
0x140012475  mov     r8d, r15d
0x140012478  cmovns  ebx, eax
0x14001247b  mov     edx, ebx
0x14001247d  jmp     loc_140012350
0x140012482  xor     ebx, ebx
0x140012484  xor     r15d, r15d
0x140012487  mov     edi, 28h ; '('
0x14001248c  cmp     [rsp+68h+var_38], 0
0x140012492  jz      short loc_1400124EA
0x140012494  lea     r9, aSignalingIdles; "Signaling IdleScavenge and/or repair co"...
0x14001249b  xor     r8d, r8d
0x14001249e  xor     edx, edx
0x1400124a0  mov     ecx, r13d
0x1400124a3  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400124a8  mov     rcx, [rsp+68h+var_38]
0x1400124ad  mov     edx, ebx
0x1400124af  mov     rax, [rcx]
0x1400124b2  mov     rax, [rax+20h]
0x1400124b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400124bb  test    eax, eax
0x1400124bd  jns     short loc_1400124D4
0x1400124bf  lea     r9, aWarningUnableT; "Warning: Unable to mark idle scavenging"...
0x1400124c6  mov     edx, eax
0x1400124c8  lea     r8d, [rdi-27h]
0x1400124cc  mov     ecx, r13d
0x1400124cf  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400124d4  mov     rcx, [rsp+68h+var_38]
0x1400124d9  test    rcx, rcx
0x1400124dc  jz      short loc_1400124EA
0x1400124de  mov     rax, [rcx]
0x1400124e1  mov     rax, [rax+10h]
0x1400124e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400124ea  test    r15d, r15d
0x1400124ed  jz      short loc_1400124F4
0x1400124ef  xor     eax, eax
0x1400124f1  xchg    eax, [rdi+rsi]
0x1400124f4  lea     rax, [r14-1]
0x1400124f8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400124fc  ja      short loc_140012507
0x1400124fe  mov     rcx, r14; hObject
0x140012501  call    cs:__imp_CloseHandle
0x140012507  mov     eax, ebx
0x140012509  mov     rcx, [rsp+68h+var_30]
0x14001250e  xor     rcx, rsp; StackCookie
0x140012511  call    __security_check_cookie
0x140012516  mov     rbx, [rsp+68h+arg_10]
0x14001251e  add     rsp, 40h
0x140012522  pop     r15
0x140012524  pop     r14
0x140012526  pop     r13
0x140012528  pop     rdi
0x140012529  pop     rsi
0x14001252a  retn
```
