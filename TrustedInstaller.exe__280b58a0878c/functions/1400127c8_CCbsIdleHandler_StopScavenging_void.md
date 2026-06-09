# CCbsIdleHandler::StopScavenging(void)

- ea: `0x1400127c8`
- end: `0x1400128ca`
- name: `?StopScavenging@CCbsIdleHandler@@QEAAJXZ`
- size: `258`
- prototype: `__int64 __fastcall(CCbsIdleHandler *this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140009b2c`
- `0x140012784`

## callees

- `0x1400023e0`
- `0x140007edc`
- `0x14000ca98`
- `0x1400127c8`
- `0x140017658`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140012882`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140012882`

## string_xrefs

- `0x140012856`: `Warning: Failed to execute idle scavenge/repair stop. Error code: 0X%x`

## pseudocode

```c
__int64 __fastcall CCbsIdleHandler::StopScavenging(CCbsIdleHandler *this)
{
  unsigned int v1; // ebx
  int WorkerProcess; // eax
  int v4; // eax
  int v5; // edi
  void *v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h] BYREF

  v1 = 0;
  v7 = 0;
  v8 = 0;
  MakeSureStartupProcessingComplete(1);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 10, 0, 0) )
  {
    WorkerProcess = TiCoreGetWorkerProcess(0, &v7);
    v1 = WorkerProcess;
    if ( WorkerProcess >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(void *, _QWORD, int *))(*(_QWORD *)v7 + 96LL))(v7, 0, &v8);
      v1 = v4;
      if ( v4 < 0 )
        CBSWdsLogLight(
          0x4000000,
          (unsigned int)v4,
          1,
          "Warning: Failed to execute idle scavenge/repair stop. Error code: 0X%x",
          v4);
      v5 = 600;
      while ( *((_DWORD *)this + 10) )
      {
        if ( !v5 )
        {
          v1 = -2147023436;
          break;
        }
        --v5;
        Sleep(0x64u);
      }
    }
    else
    {
      CBSWdsLogLight(0x4000000, (unsigned int)WorkerProcess, 1, "Failed to get worker process.");
    }
  }
  if ( v7 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
  return v1;
}

```

## disassembly

```asm
0x1400127c8  mov     [rsp+arg_8], rbx
0x1400127cd  mov     [rsp+arg_10], rsi
0x1400127d2  push    rdi
0x1400127d3  sub     rsp, 50h
0x1400127d7  mov     rax, cs:__security_cookie
0x1400127de  xor     rax, rsp
0x1400127e1  mov     [rsp+58h+var_18], rax
0x1400127e6  xor     ebx, ebx
0x1400127e8  mov     rsi, rcx
0x1400127eb  mov     [rsp+58h+var_28], rbx
0x1400127f0  mov     [rsp+58h+var_20], ebx
0x1400127f4  lea     edi, [rbx+1]
0x1400127f7  mov     cl, dil; bool
0x1400127fa  call    ?MakeSureStartupProcessingComplete@@YA_N_N@Z; MakeSureStartupProcessingComplete(bool)
0x1400127ff  xor     edx, edx
0x140012801  xor     eax, eax
0x140012803  lock cmpxchg [rsi+28h], edx
0x140012808  jz      loc_140012895
0x14001280e  lea     rdx, [rsp+58h+var_28]
0x140012813  xor     ecx, ecx
0x140012815  call    TiCoreGetWorkerProcess
0x14001281a  mov     ebx, eax
0x14001281c  test    eax, eax
0x14001281e  jns     short loc_140012838
0x140012820  lea     r9, aFailedToGetWor_0; "Failed to get worker process."
0x140012827  mov     r8d, edi
0x14001282a  mov     edx, eax
0x14001282c  mov     ecx, 4000000h
0x140012831  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140012836  jmp     short loc_140012895
0x140012838  mov     rcx, [rsp+58h+var_28]
0x14001283d  lea     r8, [rsp+58h+var_20]
0x140012842  xor     edx, edx
0x140012844  mov     rax, [rcx]
0x140012847  mov     rax, [rax+60h]
0x14001284b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012850  mov     ebx, eax
0x140012852  test    eax, eax
0x140012854  jns     short loc_140012870
0x140012856  lea     r9, aWarningFailedT; "Warning: Failed to execute idle scaveng"...
0x14001285d  mov     [rsp+58h+var_38], eax
0x140012861  mov     r8d, edi
0x140012864  mov     edx, eax
0x140012866  mov     ecx, 4000000h
0x14001286b  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140012870  mov     edi, 258h
0x140012875  jmp     short loc_140012888
0x140012877  test    edi, edi
0x140012879  jz      short loc_140012890
0x14001287b  dec     edi
0x14001287d  mov     ecx, 64h ; 'd'; dwMilliseconds
0x140012882  call    cs:__imp_Sleep
0x140012888  cmp     dword ptr [rsi+28h], 0
0x14001288c  jnz     short loc_140012877
0x14001288e  jmp     short loc_140012895
0x140012890  mov     ebx, 800705B4h
0x140012895  mov     rcx, [rsp+58h+var_28]
0x14001289a  test    rcx, rcx
0x14001289d  jz      short loc_1400128AB
0x14001289f  mov     rax, [rcx]
0x1400128a2  mov     rax, [rax+10h]
0x1400128a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400128ab  mov     eax, ebx
0x1400128ad  mov     rcx, [rsp+58h+var_18]
0x1400128b2  xor     rcx, rsp; StackCookie
0x1400128b5  call    __security_check_cookie
0x1400128ba  mov     rbx, [rsp+58h+arg_8]
0x1400128bf  mov     rsi, [rsp+58h+arg_10]
0x1400128c4  add     rsp, 50h
0x1400128c8  pop     rdi
0x1400128c9  retn
```
