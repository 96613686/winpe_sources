# CDlpTask::ExecutePrepare(void)

- ea: `0x140038100`
- end: `0x14003847d`
- name: `?ExecutePrepare@CDlpTask@@AEAAJXZ`
- size: `893`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1400356d0`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x140034ab4`
- `0x140038100`
- `0x140082010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140038457`
- `KERNEL32!CloseHandle` at `0x140038457`
- `KERNEL32!GetExitCodeThread` at `0x14003834b`
- `KERNEL32!GetExitCodeThread` at `0x14003834b`
- `KERNEL32!CreateThread` at `0x140038144`
- `KERNEL32!CreateThread` at `0x140038144`
- `KERNEL32!GetLastError` at `0x14003815c`
- `KERNEL32!GetLastError` at `0x1400382a3`
- `KERNEL32!GetLastError` at `0x14003835b`
- `KERNEL32!GetLastError` at `0x14003815c`
- `KERNEL32!GetLastError` at `0x1400382a3`
- `KERNEL32!GetLastError` at `0x14003835b`
- `KERNEL32!WaitForSingleObject` at `0x140038243`
- `KERNEL32!WaitForSingleObject` at `0x140038243`

## string_xrefs

- `0x1400381c1`: `CDlpTask::ExecutePrepare`
- `0x140038415`: `CDlpTask::ExecutePrepare`
- `0x140038227`: `Waiting for prepare thread to exit.`
- `0x14003832f`: `Prepare thread has exited.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpTask::ExecutePrepare(CDlpTask *this)
{
  HANDLE Thread; // rbp
  signed int LastError; // eax
  signed int v4; // esi
  __int64 v5; // rax
  unsigned int v6; // edi
  int v7; // eax
  void *v8; // rdi
  char *v9; // r14
  __int64 v10; // rax
  DWORD v11; // eax
  __int64 v12; // rax
  unsigned int v13; // edi
  signed int v14; // eax
  __int64 v15; // rax
  signed int v16; // eax
  int v17; // eax
  __int64 v19; // [rsp+20h] [rbp-28h]
  __int64 v20; // [rsp+28h] [rbp-20h]
  DWORD ExitCode; // [rsp+58h] [rbp+10h] BYREF

  ExitCode = 0;
  Thread = CreateThread(0, 0, CDlpTask::ExecutePrepareThreadProc, this, 0, 0);
  if ( !Thread )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
    {
      v5 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
      v6 = 0;
      if ( v4 < 0 )
      {
        if ( v5 )
        {
          LODWORD(v20) = v4;
          LODWORD(v19) = 3170;
          v7 = CDlpLogT<CEmptyType>::DlpLogFormat(
                 v5,
                 4,
                 L"%s(%d): Result = 0x%X",
                 L"CDlpTask::ExecutePrepare",
                 v19,
                 v20,
                 -2);
          v6 = v7;
          if ( v7 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
        }
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
    }
    v8 = 0;
    goto LABEL_47;
  }
  v9 = (char *)this + 176;
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9) )
  {
    v10 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9);
    CDlpLogT<CEmptyType>::DlpLogFormat(v10, 2, L"Waiting for prepare thread to exit.");
  }
  v11 = WaitForSingleObject(Thread, 0xFFFFFFFF);
  if ( v11 )
  {
    if ( v11 == -1 )
    {
      v14 = GetLastError();
      v4 = v14;
      if ( v14 > 0 )
        v4 = (unsigned __int16)v14 | 0x80070000;
      if ( v4 >= 0 || !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9) )
        goto LABEL_46;
      v12 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9);
      v13 = 0;
      if ( !v12 )
        goto LABEL_45;
      LODWORD(v20) = v4;
      LODWORD(v19) = 3189;
      goto LABEL_43;
    }
    v4 = -2147418113;
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9) )
    {
LABEL_46:
      v8 = Thread;
      goto LABEL_47;
    }
    v12 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9);
    v13 = 0;
    if ( v12 )
    {
      LODWORD(v20) = -2147418113;
      LODWORD(v19) = 3194;
      goto LABEL_43;
    }
    goto LABEL_45;
  }
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9) )
  {
    v15 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9);
    CDlpLogT<CEmptyType>::DlpLogFormat(v15, 2, L"Prepare thread has exited.");
  }
  if ( !GetExitCodeThread(Thread, &ExitCode) )
  {
    v16 = GetLastError();
    v4 = v16;
    if ( v16 )
    {
      if ( v16 > 0 )
        v4 = (unsigned __int16)v16 | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9) )
      goto LABEL_46;
    v12 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9);
    v13 = 0;
    if ( v4 >= 0 || !v12 )
      goto LABEL_45;
    LODWORD(v20) = v4;
    LODWORD(v19) = 3184;
    goto LABEL_43;
  }
  v4 = ExitCode;
  if ( (int)ExitCode > 0 )
    v4 = (unsigned __int16)ExitCode | 0x80070000;
  v8 = Thread;
  if ( v4 < 0 && (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9) )
  {
    v12 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9);
    v13 = 0;
    if ( v12 )
    {
      LODWORD(v20) = v4;
      LODWORD(v19) = 3185;
LABEL_43:
      v17 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v12,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpTask::ExecutePrepare",
              v19,
              v20,
              -2);
      v13 = v17;
      if ( v17 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v17);
    }
LABEL_45:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
    goto LABEL_46;
  }
LABEL_47:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
  if ( v8 )
    CloseHandle(v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140038100  mov     rax, rsp
0x140038103  push    r14
0x140038105  sub     rsp, 40h
0x140038109  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x140038111  mov     [rax+8], rbp
0x140038115  mov     [rax+18h], rsi
0x140038119  mov     [rax+20h], rdi
0x14003811d  mov     r14, rcx
0x140038120  mov     dword ptr [rax+10h], 0
0x140038127  mov     qword ptr [rax-20h], 0
0x14003812f  mov     dword ptr [rax-28h], 0
0x140038136  mov     r9, rcx; lpParameter
0x140038139  lea     r8, ?ExecutePrepareThreadProc@CDlpTask@@SAKPEAX@Z; lpStartAddress
0x140038140  xor     edx, edx; dwStackSize
0x140038142  xor     ecx, ecx; lpThreadAttributes
0x140038144  call    cs:__imp_CreateThread
0x14003814b  nop     dword ptr [rax+rax+00h]
0x140038150  mov     rbp, rax
0x140038153  test    rax, rax
0x140038156  jnz     loc_1400381F5
0x14003815c  call    cs:__imp_GetLastError
0x140038163  nop     dword ptr [rax+rax+00h]
0x140038168  mov     esi, eax
0x14003816a  test    eax, eax
0x14003816c  jnz     short loc_140038175
0x14003816e  mov     esi, 80004005h
0x140038173  jmp     short loc_140038180
0x140038175  jle     short loc_140038180
0x140038177  movzx   esi, ax
0x14003817a  or      esi, 80070000h
0x140038180  lea     rdi, [r14+0B0h]
0x140038187  mov     rax, [rdi]
0x14003818a  mov     rcx, rdi
0x14003818d  mov     rax, [rax+10h]
0x140038191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038196  test    rax, rax
0x140038199  jz      short loc_1400381EE
0x14003819b  mov     rax, [rdi]
0x14003819e  mov     rcx, rdi
0x1400381a1  mov     rax, [rax+10h]
0x1400381a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400381aa  xor     edi, edi
0x1400381ac  test    esi, esi
0x1400381ae  jns     short loc_1400381E7
0x1400381b0  test    rax, rax
0x1400381b3  jz      short loc_1400381E7
0x1400381b5  mov     dword ptr [rsp+48h+var_20], esi
0x1400381b9  mov     dword ptr [rsp+48h+var_28], 0C62h
0x1400381c1  lea     r9, aCdlptaskExecut; "CDlpTask::ExecutePrepare"
0x1400381c8  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1400381cf  lea     edx, [rdi+4]
0x1400381d2  mov     rcx, rax
0x1400381d5  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1400381da  mov     edi, eax
0x1400381dc  test    eax, eax
0x1400381de  jns     short loc_1400381E7
0x1400381e0  mov     ecx, eax
0x1400381e2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400381e7  mov     ecx, edi
0x1400381e9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400381ee  xor     edi, edi
0x1400381f0  jmp     loc_140038447
0x1400381f5  add     r14, 0B0h
0x1400381fc  mov     rax, [r14]
0x1400381ff  mov     rcx, r14
0x140038202  mov     rax, [rax+10h]
0x140038206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003820b  mov     esi, 2
0x140038210  test    rax, rax
0x140038213  jz      short loc_140038235
0x140038215  mov     rax, [r14]
0x140038218  mov     rcx, r14
0x14003821b  mov     rax, [rax+10h]
0x14003821f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038224  mov     rcx, rax
0x140038227  lea     r8, aWaitingForPrep; "Waiting for prepare thread to exit."
0x14003822e  mov     edx, esi
0x140038230  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x140038235  xor     ecx, ecx
0x140038237  test    rbp, rbp
0x14003823a  cmovnz  rcx, rbp; hHandle
0x14003823e  or      edi, 0FFFFFFFFh
0x140038241  mov     edx, edi; dwMilliseconds
0x140038243  call    cs:__imp_WaitForSingleObject
0x14003824a  nop     dword ptr [rax+rax+00h]
0x14003824f  test    eax, eax
0x140038251  jz      loc_140038309
0x140038257  cmp     eax, edi
0x140038259  jz      short loc_1400382A3
0x14003825b  mov     esi, 8000FFFFh
0x140038260  mov     rax, [r14]
0x140038263  mov     rcx, r14
0x140038266  mov     rax, [rax+10h]
0x14003826a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003826f  test    rax, rax
0x140038272  jz      loc_140038444
0x140038278  mov     rax, [r14]
0x14003827b  mov     rcx, r14
0x14003827e  mov     rax, [rax+10h]
0x140038282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038287  xor     edi, edi
0x140038289  test    rax, rax
0x14003828c  jz      loc_14003843D
0x140038292  mov     dword ptr [rsp+48h+var_20], esi
0x140038296  mov     dword ptr [rsp+48h+var_28], 0C7Ah
0x14003829e  jmp     loc_140038415
0x1400382a3  call    cs:__imp_GetLastError
0x1400382aa  nop     dword ptr [rax+rax+00h]
0x1400382af  mov     esi, eax
0x1400382b1  test    eax, eax
0x1400382b3  jle     short loc_1400382BE
0x1400382b5  movzx   esi, ax
0x1400382b8  or      esi, 80070000h
0x1400382be  test    esi, esi
0x1400382c0  jns     loc_140038444
0x1400382c6  mov     rax, [r14]
0x1400382c9  mov     rcx, r14
0x1400382cc  mov     rax, [rax+10h]
0x1400382d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400382d5  test    rax, rax
0x1400382d8  jz      loc_140038444
0x1400382de  mov     rax, [r14]
0x1400382e1  mov     rcx, r14
0x1400382e4  mov     rax, [rax+10h]
0x1400382e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400382ed  xor     edi, edi
0x1400382ef  test    rax, rax
0x1400382f2  jz      loc_14003843D
0x1400382f8  mov     dword ptr [rsp+48h+var_20], esi
0x1400382fc  mov     dword ptr [rsp+48h+var_28], 0C75h
0x140038304  jmp     loc_140038415
0x140038309  mov     rax, [r14]
0x14003830c  mov     rcx, r14
0x14003830f  mov     rax, [rax+10h]
0x140038313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038318  test    rax, rax
0x14003831b  jz      short loc_14003833D
0x14003831d  mov     rax, [r14]
0x140038320  mov     rcx, r14
0x140038323  mov     rax, [rax+10h]
0x140038327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003832c  mov     rcx, rax
0x14003832f  lea     r8, aPrepareThreadH; "Prepare thread has exited."
0x140038336  mov     edx, esi
0x140038338  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14003833d  xor     ecx, ecx
0x14003833f  test    rbp, rbp
0x140038342  cmovnz  rcx, rbp; hThread
0x140038346  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x14003834b  call    cs:__imp_GetExitCodeThread
0x140038352  nop     dword ptr [rax+rax+00h]
0x140038357  test    eax, eax
0x140038359  jnz     short loc_1400383C7
0x14003835b  call    cs:__imp_GetLastError
0x140038362  nop     dword ptr [rax+rax+00h]
0x140038367  mov     esi, eax
0x140038369  test    eax, eax
0x14003836b  jnz     short loc_140038374
0x14003836d  mov     esi, 80004005h
0x140038372  jmp     short loc_14003837F
0x140038374  jle     short loc_14003837F
0x140038376  movzx   esi, ax
0x140038379  or      esi, 80070000h
0x14003837f  mov     rax, [r14]
0x140038382  mov     rcx, r14
0x140038385  mov     rax, [rax+10h]
0x140038389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003838e  test    rax, rax
0x140038391  jz      loc_140038444
0x140038397  mov     rax, [r14]
0x14003839a  mov     rcx, r14
0x14003839d  mov     rax, [rax+10h]
0x1400383a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400383a6  xor     edi, edi
0x1400383a8  test    esi, esi
0x1400383aa  jns     loc_14003843D
0x1400383b0  test    rax, rax
0x1400383b3  jz      loc_14003843D
0x1400383b9  mov     dword ptr [rsp+48h+var_20], esi
0x1400383bd  mov     dword ptr [rsp+48h+var_28], 0C70h
0x1400383c5  jmp     short loc_140038415
0x1400383c7  mov     esi, [rsp+48h+ExitCode]
0x1400383cb  test    esi, esi
0x1400383cd  jle     short loc_1400383D8
0x1400383cf  movzx   esi, si
0x1400383d2  or      esi, 80070000h
0x1400383d8  mov     rdi, rbp
0x1400383db  test    esi, esi
0x1400383dd  jns     short loc_140038447
0x1400383df  mov     rax, [r14]
0x1400383e2  mov     rcx, r14
0x1400383e5  mov     rax, [rax+10h]
0x1400383e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400383ee  test    rax, rax
0x1400383f1  jz      short loc_140038447
0x1400383f3  mov     rax, [r14]
0x1400383f6  mov     rcx, r14
0x1400383f9  mov     rax, [rax+10h]
0x1400383fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038402  xor     edi, edi
0x140038404  test    rax, rax
0x140038407  jz      short loc_14003843D
0x140038409  mov     dword ptr [rsp+48h+var_20], esi
0x14003840d  mov     dword ptr [rsp+48h+var_28], 0C71h
0x140038415  lea     r9, aCdlptaskExecut; "CDlpTask::ExecutePrepare"
0x14003841c  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x140038423  mov     edx, 4
0x140038428  mov     rcx, rax
0x14003842b  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x140038430  test    eax, eax
0x140038432  mov     edi, eax
0x140038434  jns     short loc_14003843D
0x140038436  mov     ecx, eax
0x140038438  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14003843d  mov     ecx, edi
0x14003843f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140038444  mov     rdi, rbp
0x140038447  mov     ecx, esi
0x140038449  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14003844e  nop
0x14003844f  test    rdi, rdi
0x140038452  jz      short loc_140038464
0x140038454  mov     rcx, rdi; hObject
0x140038457  call    cs:__imp_CloseHandle
0x14003845e  nop     dword ptr [rax+rax+00h]
0x140038463  nop
0x140038464  mov     eax, esi
0x140038466  mov     rbp, [rsp+48h+arg_0]
0x14003846b  mov     rsi, [rsp+48h+arg_10]
0x140038470  mov     rdi, [rsp+48h+arg_18]
0x140038475  add     rsp, 40h
0x140038479  pop     r14
0x14003847b  retn
```
