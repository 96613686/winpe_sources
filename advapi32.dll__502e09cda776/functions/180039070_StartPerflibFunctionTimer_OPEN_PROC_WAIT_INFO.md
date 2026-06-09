# StartPerflibFunctionTimer(OPEN_PROC_WAIT_INFO *)

- ea: `0x180039070`
- end: `0x180039395`
- name: `?StartPerflibFunctionTimer@@YAPEAXPEAUOPEN_PROC_WAIT_INFO@@@Z`
- size: `805`
- prototype: `void *__fastcall(struct OPEN_PROC_WAIT_INFO *)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dc80`
- `0x18003d248`
- `0x18003dc28`

## callees

- `0x180002e40`
- `0x18000a560`
- `0x180029698`
- `0x180039070`
- `0x180063b8c`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x1800392fe`
- `ntdll!NtWaitForSingleObject` at `0x1800392fe`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800391f3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800391f3`
- `KERNEL32!GetLastError` at `0x1800390e2`
- `KERNEL32!GetLastError` at `0x18003911d`
- `KERNEL32!GetLastError` at `0x18003914f`
- `KERNEL32!GetLastError` at `0x18003920b`
- `KERNEL32!GetLastError` at `0x1800390e2`
- `KERNEL32!GetLastError` at `0x18003911d`
- `KERNEL32!GetLastError` at `0x18003914f`
- `KERNEL32!GetLastError` at `0x18003920b`
- `KERNEL32!CreateEventW` at `0x1800390ca`
- `KERNEL32!CreateEventW` at `0x180039105`
- `KERNEL32!CreateEventW` at `0x1800390ca`
- `KERNEL32!CreateEventW` at `0x180039105`
- `KERNEL32!CloseHandle` at `0x18003916c`
- `KERNEL32!CloseHandle` at `0x1800391b0`
- `KERNEL32!CloseHandle` at `0x18003916c`
- `KERNEL32!CloseHandle` at `0x1800391b0`
- `KERNEL32!WaitForSingleObject` at `0x180039197`
- `KERNEL32!WaitForSingleObject` at `0x180039197`
- `KERNEL32!ReleaseMutex` at `0x18003935d`
- `KERNEL32!ReleaseMutex` at `0x18003935d`
- `KERNEL32!SetEvent` at `0x180039375`
- `KERNEL32!SetEvent` at `0x180039375`
- `KERNEL32!CreateMutexW` at `0x18003913b`
- `KERNEL32!CreateMutexW` at `0x18003913b`
- `KERNEL32!SetLastError` at `0x180039095`
- `KERNEL32!SetLastError` at `0x180039095`

## pseudocode

```c
_QWORD *__fastcall StartPerflibFunctionTimer(struct OPEN_PROC_WAIT_INFO *a1)
{
  __int64 v2; // rsi
  DWORD LastError; // ebx
  DWORD v4; // ecx
  HANDLE MutexW; // rax
  const wchar_t *v7; // rdx
  const wchar_t *v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // r14d
  unsigned int v12; // ebp
  __int64 v13; // rax
  _QWORD *v14; // rbx
  __int64 v15; // r11
  unsigned __int16 *v16; // rcx
  unsigned int v17; // edx
  NTSTATUS v18; // eax
  unsigned int v19; // eax
  LARGE_INTEGER Timeout; // [rsp+70h] [rbp+8h] BYREF

  Timeout.QuadPart = 0;
  v2 = 0;
  if ( !a1 )
  {
    LastError = 87;
LABEL_3:
    v4 = LastError;
LABEL_4:
    SetLastError(v4);
    return (_QWORD *)v2;
  }
  LastError = 0;
  if ( !Object[0] )
  {
    Object[0] = CreateEventW(0, 1, 0, 0);
    if ( !Object[0] )
      LastError = GetLastError();
  }
  if ( !hEvent )
  {
    hEvent = CreateEventW(0, 1, 0, 0);
    if ( !hEvent )
      LastError = GetLastError();
  }
  if ( !hMutex )
  {
    MutexW = CreateMutexW(0, 0, 0);
    if ( MutexW )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&hMutex, (signed __int64)MutexW, 0) )
        CloseHandle(MutexW);
      else
        hMutex = MutexW;
    }
    else
    {
      LastError = GetLastError();
    }
  }
  if ( LastError )
    goto LABEL_3;
  if ( !hObject )
    goto LABEL_25;
  LastError = WaitForSingleObject(hObject, 0);
  if ( !LastError )
  {
    CloseHandle(hObject);
    hObject = 0;
    LastError = 0;
LABEL_25:
    hObject = CreateThread(0, 0, PerflibTimerFunction, 0, 0, 0);
    if ( !hObject )
      LastError = GetLastError();
    goto LABEL_27;
  }
  if ( LastError == 258 )
    LastError = 0;
  if ( !hObject )
    goto LABEL_25;
LABEL_27:
  if ( LastError )
    goto LABEL_3;
  v7 = &P;
  v8 = &P;
  if ( *((_QWORD *)a1 + 1) )
    v8 = (const wchar_t *)*((_QWORD *)a1 + 1);
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( v8[v10] );
  v11 = 2 * v10 + 2;
  if ( *((_QWORD *)a1 + 2) )
    v7 = (const wchar_t *)*((_QWORD *)a1 + 2);
  do
    ++v9;
  while ( v7[v9] );
  v12 = 2 * v9 + 2;
  v13 = operator new((v11 + 2 * (_DWORD)v9 + 49) & 0xFFFFFFF8);
  v14 = (_QWORD *)v13;
  if ( !v13 )
  {
    LastError = 14;
    goto LABEL_3;
  }
  *(_QWORD *)(v13 + 8) = v13 + 40;
  StringCbCopyW((unsigned __int16 *)(v13 + 40), v11, *((const unsigned __int16 **)a1 + 1));
  v16 = (unsigned __int16 *)(v15 + v14[1]);
  v14[2] = v16;
  StringCbCopyW(v16, v12, *((const unsigned __int16 **)a1 + 2));
  v17 = *((_DWORD *)a1 + 6) / 0xC8u;
  *((_DWORD *)v14 + 6) = v17;
  if ( !v17 )
    *((_DWORD *)v14 + 6) = 1;
  *((_DWORD *)v14 + 7) = *((_DWORD *)a1 + 7);
  v14[4] = *((_QWORD *)a1 + 4);
  if ( !hMutex )
  {
    v19 = 21;
    goto LABEL_48;
  }
  Timeout.QuadPart = -4000000;
  v18 = NtWaitForSingleObject(hMutex, 0, &Timeout);
  v19 = PerfpDosError(v18);
  if ( v19 )
  {
LABEL_48:
    v4 = v19;
    goto LABEL_4;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids,
      v14,
      *((_DWORD *)v14 + 6));
  *v14 = qword_1800B22C8;
  qword_1800B22C8 = v14;
  ReleaseMutex(hMutex);
  if ( !*v14 )
    SetEvent(Object[0]);
  return v14;
}

```

## disassembly

```asm
0x180039070  push    rbx
0x180039072  push    rbp
0x180039073  push    rsi
0x180039074  push    rdi
0x180039075  push    r14
0x180039077  push    r15
0x180039079  sub     rsp, 38h
0x18003907d  xor     r15d, r15d
0x180039080  mov     rdi, rcx
0x180039083  mov     qword ptr [rsp+68h+Timeout], r15
0x180039088  mov     esi, r15d
0x18003908b  test    rcx, rcx
0x18003908e  jnz     short loc_1800390B2
0x180039090  lea     ebx, [rcx+57h]
0x180039093  mov     ecx, ebx; dwErrCode
0x180039095  call    cs:__imp_SetLastError
0x18003909c  nop     dword ptr [rax+rax+00h]
0x1800390a1  mov     rax, rsi
0x1800390a4  add     rsp, 38h
0x1800390a8  pop     r15
0x1800390aa  pop     r14
0x1800390ac  pop     rdi
0x1800390ad  pop     rsi
0x1800390ae  pop     rbp
0x1800390af  pop     rbx
0x1800390b0  retn
0x1800390b2  cmp     cs:Object, r15
0x1800390b9  mov     ebx, r15d
0x1800390bc  jnz     short loc_1800390F0
0x1800390be  xor     r9d, r9d; lpName
0x1800390c1  xor     r8d, r8d; bInitialState
0x1800390c4  xor     ecx, ecx; lpEventAttributes
0x1800390c6  lea     edx, [r9+1]; bManualReset
0x1800390ca  call    cs:__imp_CreateEventW
0x1800390d1  nop     dword ptr [rax+rax+00h]
0x1800390d6  mov     cs:Object, rax
0x1800390dd  test    rax, rax
0x1800390e0  jnz     short loc_1800390F0
0x1800390e2  call    cs:__imp_GetLastError
0x1800390e9  nop     dword ptr [rax+rax+00h]
0x1800390ee  mov     ebx, eax
0x1800390f0  cmp     cs:hEvent, r15
0x1800390f7  jnz     short loc_18003912B
0x1800390f9  xor     r9d, r9d; lpName
0x1800390fc  xor     r8d, r8d; bInitialState
0x1800390ff  xor     ecx, ecx; lpEventAttributes
0x180039101  lea     edx, [r9+1]; bManualReset
0x180039105  call    cs:__imp_CreateEventW
0x18003910c  nop     dword ptr [rax+rax+00h]
0x180039111  mov     cs:hEvent, rax
0x180039118  test    rax, rax
0x18003911b  jnz     short loc_18003912B
0x18003911d  call    cs:__imp_GetLastError
0x180039124  nop     dword ptr [rax+rax+00h]
0x180039129  mov     ebx, eax
0x18003912b  cmp     cs:hMutex, r15
0x180039132  jnz     short loc_180039181
0x180039134  xor     r8d, r8d; lpName
0x180039137  xor     edx, edx; bInitialOwner
0x180039139  xor     ecx, ecx; lpMutexAttributes
0x18003913b  call    cs:__imp_CreateMutexW
0x180039142  nop     dword ptr [rax+rax+00h]
0x180039147  mov     rcx, rax; hObject
0x18003914a  test    rax, rax
0x18003914d  jnz     short loc_18003915F
0x18003914f  call    cs:__imp_GetLastError
0x180039156  nop     dword ptr [rax+rax+00h]
0x18003915b  mov     ebx, eax
0x18003915d  jmp     short loc_180039181
0x18003915f  xor     eax, eax
0x180039161  lock cmpxchg cs:hMutex, rcx
0x18003916a  jz      short loc_18003917A
0x18003916c  call    cs:__imp_CloseHandle
0x180039173  nop     dword ptr [rax+rax+00h]
0x180039178  jmp     short loc_180039181
0x18003917a  mov     cs:hMutex, rcx
0x180039181  test    ebx, ebx
0x180039183  jnz     loc_180039093
0x180039189  mov     rcx, cs:hObject; hHandle
0x180039190  test    rcx, rcx
0x180039193  jz      short loc_1800391DB
0x180039195  xor     edx, edx; dwMilliseconds
0x180039197  call    cs:__imp_WaitForSingleObject
0x18003919e  nop     dword ptr [rax+rax+00h]
0x1800391a3  mov     ebx, eax
0x1800391a5  test    eax, eax
0x1800391a7  jnz     short loc_1800391C8
0x1800391a9  mov     rcx, cs:hObject; hObject
0x1800391b0  call    cs:__imp_CloseHandle
0x1800391b7  nop     dword ptr [rax+rax+00h]
0x1800391bc  mov     cs:hObject, r15
0x1800391c3  mov     ebx, r15d
0x1800391c6  jmp     short loc_1800391DB
0x1800391c8  cmp     ebx, 102h
0x1800391ce  cmovz   ebx, r15d
0x1800391d2  cmp     cs:hObject, r15
0x1800391d9  jnz     short loc_180039219
0x1800391db  mov     [rsp+68h+lpThreadId], r15; lpThreadId
0x1800391e0  lea     r8, ?PerflibTimerFunction@@YAKPEAK@Z; lpStartAddress
0x1800391e7  xor     r9d, r9d; lpParameter
0x1800391ea  mov     [rsp+68h+dwCreationFlags], r15d; dwCreationFlags
0x1800391ef  xor     edx, edx; dwStackSize
0x1800391f1  xor     ecx, ecx; lpThreadAttributes
0x1800391f3  call    cs:__imp_CreateThread
0x1800391fa  nop     dword ptr [rax+rax+00h]
0x1800391ff  mov     cs:hObject, rax
0x180039206  test    rax, rax
0x180039209  jnz     short loc_180039219
0x18003920b  call    cs:__imp_GetLastError
0x180039212  nop     dword ptr [rax+rax+00h]
0x180039217  mov     ebx, eax
0x180039219  test    ebx, ebx
0x18003921b  jnz     loc_180039093
0x180039221  cmp     [rdi+8], r15
0x180039225  lea     rdx, P
0x18003922c  mov     r8, rdx
0x18003922f  cmovnz  r8, [rdi+8]
0x180039234  or      rax, 0FFFFFFFFFFFFFFFFh
0x180039238  mov     rcx, rax
0x18003923b  inc     rcx
0x18003923e  cmp     [r8+rcx*2], r15w
0x180039243  jnz     short loc_18003923B
0x180039245  cmp     [rdi+10h], r15
0x180039249  lea     r14d, ds:2[rcx*2]
0x180039251  cmovnz  rdx, [rdi+10h]
0x180039256  inc     rax
0x180039259  cmp     [rdx+rax*2], r15w
0x18003925e  jnz     short loc_180039256
0x180039260  lea     ebp, ds:2[rax*2]
0x180039267  mov     eax, 0FFFFFFF8h
0x18003926c  lea     ecx, [rbp+2Fh]
0x18003926f  add     ecx, r14d
0x180039272  and     rcx, rax
0x180039275  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18003927a  mov     rbx, rax
0x18003927d  test    rax, rax
0x180039280  jnz     short loc_18003928A
0x180039282  lea     ebx, [rax+0Eh]
0x180039285  jmp     loc_180039093
0x18003928a  lea     rcx, [rax+28h]; unsigned __int16 *
0x18003928e  mov     edx, r14d; unsigned __int64
0x180039291  mov     [rax+8], rcx
0x180039295  mov     r8, [rdi+8]; unsigned __int16 *
0x180039299  mov     r11d, r14d
0x18003929c  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800392a1  mov     rcx, [rbx+8]
0x1800392a5  add     rcx, r11; unsigned __int16 *
0x1800392a8  mov     edx, ebp; unsigned __int64
0x1800392aa  mov     [rbx+10h], rcx
0x1800392ae  mov     r8, [rdi+10h]; unsigned __int16 *
0x1800392b2  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800392b7  mov     eax, 51EB851Fh
0x1800392bc  mul     dword ptr [rdi+18h]
0x1800392bf  shr     edx, 6
0x1800392c2  mov     [rbx+18h], edx
0x1800392c5  test    edx, edx
0x1800392c7  jnz     short loc_1800392D0
0x1800392c9  mov     dword ptr [rbx+18h], 1
0x1800392d0  mov     eax, [rdi+1Ch]
0x1800392d3  mov     [rbx+1Ch], eax
0x1800392d6  mov     rax, [rdi+20h]
0x1800392da  mov     [rbx+20h], rax
0x1800392de  mov     rcx, cs:hMutex; Handle
0x1800392e5  test    rcx, rcx
0x1800392e8  jz      loc_180039389
0x1800392ee  lea     r8, [rsp+68h+Timeout]; Timeout
0x1800392f3  mov     qword ptr [rsp+68h+Timeout], 0FFFFFFFFFFC2F700h
0x1800392fc  xor     edx, edx; Alertable
0x1800392fe  call    cs:__imp_NtWaitForSingleObject
0x180039305  nop     dword ptr [rax+rax+00h]
0x18003930a  mov     ecx, eax; int
0x18003930c  call    ?PerfpDosError@@YAKJ@Z; PerfpDosError(long)
0x180039311  test    eax, eax
0x180039313  jnz     short loc_18003938E
0x180039315  mov     rcx, cs:WPP_GLOBAL_Control
0x18003931c  test    byte ptr [rcx+1Ch], 40h
0x180039320  jz      short loc_180039345
0x180039322  cmp     byte ptr [rcx+19h], 4
0x180039326  jb      short loc_180039345
0x180039328  mov     rcx, [rcx+10h]
0x18003932c  lea     edx, [rax+16h]
0x18003932f  mov     eax, [rbx+18h]
0x180039332  lea     r8, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids
0x180039339  mov     r9, rbx
0x18003933c  mov     [rsp+68h+dwCreationFlags], eax
0x180039340  call    WPP_SF_qd
0x180039345  mov     rax, cs:qword_1800B22C8
0x18003934c  mov     [rbx], rax
0x18003934f  mov     rcx, cs:hMutex; hMutex
0x180039356  mov     cs:qword_1800B22C8, rbx
0x18003935d  call    cs:__imp_ReleaseMutex
0x180039364  nop     dword ptr [rax+rax+00h]
0x180039369  cmp     [rbx], r15
0x18003936c  jnz     short loc_180039381
0x18003936e  mov     rcx, cs:Object; hEvent
0x180039375  call    cs:__imp_SetEvent
0x18003937c  nop     dword ptr [rax+rax+00h]
0x180039381  mov     rsi, rbx
0x180039384  jmp     loc_1800390A1
0x180039389  mov     eax, 15h
0x18003938e  mov     ecx, eax
0x180039390  jmp     loc_180039095
```
