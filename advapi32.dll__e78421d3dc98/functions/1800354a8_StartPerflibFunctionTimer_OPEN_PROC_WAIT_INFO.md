# StartPerflibFunctionTimer(OPEN_PROC_WAIT_INFO *)

- ea: `0x1800354a8`
- end: `0x180035772`
- name: `?StartPerflibFunctionTimer@@YAPEAXPEAUOPEN_PROC_WAIT_INFO@@@Z`
- size: `714`
- prototype: `void *__fastcall(struct OPEN_PROC_WAIT_INFO *)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014e50`
- `0x180038fbc`
- `0x180039948`

## callees

- `0x180001910`
- `0x180017100`
- `0x180026a7c`
- `0x1800354a8`
- `0x180057a98`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x1800356ed`
- `ntdll!NtWaitForSingleObject` at `0x1800356ed`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800355ee`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800355ee`
- `KERNEL32!GetLastError` at `0x18003550d`
- `KERNEL32!GetLastError` at `0x18003553c`
- `KERNEL32!GetLastError` at `0x180035562`
- `KERNEL32!GetLastError` at `0x180035600`
- `KERNEL32!GetLastError` at `0x18003550d`
- `KERNEL32!GetLastError` at `0x18003553c`
- `KERNEL32!GetLastError` at `0x180035562`
- `KERNEL32!GetLastError` at `0x180035600`
- `KERNEL32!CreateEventW` at `0x1800354fb`
- `KERNEL32!CreateEventW` at `0x18003552a`
- `KERNEL32!CreateEventW` at `0x1800354fb`
- `KERNEL32!CreateEventW` at `0x18003552a`
- `KERNEL32!CloseHandle` at `0x180035579`
- `KERNEL32!CloseHandle` at `0x1800355b1`
- `KERNEL32!CloseHandle` at `0x180035579`
- `KERNEL32!CloseHandle` at `0x1800355b1`
- `KERNEL32!WaitForSingleObject` at `0x18003559e`
- `KERNEL32!WaitForSingleObject` at `0x18003559e`
- `KERNEL32!ReleaseMutex` at `0x180035746`
- `KERNEL32!ReleaseMutex` at `0x180035746`
- `KERNEL32!SetEvent` at `0x180035758`
- `KERNEL32!SetEvent` at `0x180035758`
- `KERNEL32!CreateMutexW` at `0x180035554`
- `KERNEL32!CreateMutexW` at `0x180035554`
- `KERNEL32!SetLastError` at `0x1800354cd`
- `KERNEL32!SetLastError` at `0x1800354cd`

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
  *v14 = hMem;
  hMem = v14;
  ReleaseMutex(hMutex);
  if ( !*v14 )
    SetEvent(Object[0]);
  return v14;
}

```

## disassembly

```asm
0x1800354a8  push    rbx
0x1800354aa  push    rbp
0x1800354ab  push    rsi
0x1800354ac  push    rdi
0x1800354ad  push    r14
0x1800354af  push    r15
0x1800354b1  sub     rsp, 38h
0x1800354b5  xor     r15d, r15d
0x1800354b8  mov     rdi, rcx
0x1800354bb  mov     qword ptr [rsp+68h+Timeout], r15
0x1800354c0  mov     esi, r15d
0x1800354c3  test    rcx, rcx
0x1800354c6  jnz     short loc_1800354E3
0x1800354c8  lea     ebx, [rcx+57h]
0x1800354cb  mov     ecx, ebx; dwErrCode
0x1800354cd  call    cs:__imp_SetLastError
0x1800354d3  mov     rax, rsi
0x1800354d6  add     rsp, 38h
0x1800354da  pop     r15
0x1800354dc  pop     r14
0x1800354de  pop     rdi
0x1800354df  pop     rsi
0x1800354e0  pop     rbp
0x1800354e1  pop     rbx
0x1800354e2  retn
0x1800354e3  cmp     cs:Object, r15
0x1800354ea  mov     ebx, r15d
0x1800354ed  jnz     short loc_180035515
0x1800354ef  xor     r9d, r9d; lpName
0x1800354f2  xor     r8d, r8d; bInitialState
0x1800354f5  xor     ecx, ecx; lpEventAttributes
0x1800354f7  lea     edx, [r9+1]; bManualReset
0x1800354fb  call    cs:__imp_CreateEventW
0x180035501  mov     cs:Object, rax
0x180035508  test    rax, rax
0x18003550b  jnz     short loc_180035515
0x18003550d  call    cs:__imp_GetLastError
0x180035513  mov     ebx, eax
0x180035515  cmp     cs:hEvent, r15
0x18003551c  jnz     short loc_180035544
0x18003551e  xor     r9d, r9d; lpName
0x180035521  xor     r8d, r8d; bInitialState
0x180035524  xor     ecx, ecx; lpEventAttributes
0x180035526  lea     edx, [r9+1]; bManualReset
0x18003552a  call    cs:__imp_CreateEventW
0x180035530  mov     cs:hEvent, rax
0x180035537  test    rax, rax
0x18003553a  jnz     short loc_180035544
0x18003553c  call    cs:__imp_GetLastError
0x180035542  mov     ebx, eax
0x180035544  cmp     cs:hMutex, r15
0x18003554b  jnz     short loc_180035588
0x18003554d  xor     r8d, r8d; lpName
0x180035550  xor     edx, edx; bInitialOwner
0x180035552  xor     ecx, ecx; lpMutexAttributes
0x180035554  call    cs:__imp_CreateMutexW
0x18003555a  mov     rcx, rax; hObject
0x18003555d  test    rax, rax
0x180035560  jnz     short loc_18003556C
0x180035562  call    cs:__imp_GetLastError
0x180035568  mov     ebx, eax
0x18003556a  jmp     short loc_180035588
0x18003556c  xor     eax, eax
0x18003556e  lock cmpxchg cs:hMutex, rcx
0x180035577  jz      short loc_180035581
0x180035579  call    cs:__imp_CloseHandle
0x18003557f  jmp     short loc_180035588
0x180035581  mov     cs:hMutex, rcx
0x180035588  test    ebx, ebx
0x18003558a  jnz     loc_1800354CB
0x180035590  mov     rcx, cs:hObject; hHandle
0x180035597  test    rcx, rcx
0x18003559a  jz      short loc_1800355D6
0x18003559c  xor     edx, edx; dwMilliseconds
0x18003559e  call    cs:__imp_WaitForSingleObject
0x1800355a4  mov     ebx, eax
0x1800355a6  test    eax, eax
0x1800355a8  jnz     short loc_1800355C3
0x1800355aa  mov     rcx, cs:hObject; hObject
0x1800355b1  call    cs:__imp_CloseHandle
0x1800355b7  mov     cs:hObject, r15
0x1800355be  mov     ebx, r15d
0x1800355c1  jmp     short loc_1800355D6
0x1800355c3  cmp     ebx, 102h
0x1800355c9  cmovz   ebx, r15d
0x1800355cd  cmp     cs:hObject, r15
0x1800355d4  jnz     short loc_180035608
0x1800355d6  mov     [rsp+68h+lpThreadId], r15; lpThreadId
0x1800355db  lea     r8, ?PerflibTimerFunction@@YAKPEAK@Z; lpStartAddress
0x1800355e2  xor     r9d, r9d; lpParameter
0x1800355e5  mov     [rsp+68h+dwCreationFlags], r15d; dwCreationFlags
0x1800355ea  xor     edx, edx; dwStackSize
0x1800355ec  xor     ecx, ecx; lpThreadAttributes
0x1800355ee  call    cs:__imp_CreateThread
0x1800355f4  mov     cs:hObject, rax
0x1800355fb  test    rax, rax
0x1800355fe  jnz     short loc_180035608
0x180035600  call    cs:__imp_GetLastError
0x180035606  mov     ebx, eax
0x180035608  test    ebx, ebx
0x18003560a  jnz     loc_1800354CB
0x180035610  cmp     [rdi+8], r15
0x180035614  lea     rdx, P
0x18003561b  mov     r8, rdx
0x18003561e  cmovnz  r8, [rdi+8]
0x180035623  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035627  mov     rcx, rax
0x18003562a  inc     rcx
0x18003562d  cmp     [r8+rcx*2], r15w
0x180035632  jnz     short loc_18003562A
0x180035634  cmp     [rdi+10h], r15
0x180035638  lea     r14d, ds:2[rcx*2]
0x180035640  cmovnz  rdx, [rdi+10h]
0x180035645  inc     rax
0x180035648  cmp     [rdx+rax*2], r15w
0x18003564d  jnz     short loc_180035645
0x18003564f  lea     ebp, ds:2[rax*2]
0x180035656  mov     eax, 0FFFFFFF8h
0x18003565b  lea     ecx, [rbp+2Fh]
0x18003565e  add     ecx, r14d
0x180035661  and     rcx, rax
0x180035664  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180035669  mov     rbx, rax
0x18003566c  test    rax, rax
0x18003566f  jnz     short loc_180035679
0x180035671  lea     ebx, [rax+0Eh]
0x180035674  jmp     loc_1800354CB
0x180035679  lea     rcx, [rax+28h]; unsigned __int16 *
0x18003567d  mov     edx, r14d; unsigned __int64
0x180035680  mov     [rax+8], rcx
0x180035684  mov     r8, [rdi+8]; unsigned __int16 *
0x180035688  mov     r11d, r14d
0x18003568b  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180035690  mov     rcx, [rbx+8]
0x180035694  add     rcx, r11; unsigned __int16 *
0x180035697  mov     edx, ebp; unsigned __int64
0x180035699  mov     [rbx+10h], rcx
0x18003569d  mov     r8, [rdi+10h]; unsigned __int16 *
0x1800356a1  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800356a6  mov     eax, 51EB851Fh
0x1800356ab  mul     dword ptr [rdi+18h]
0x1800356ae  shr     edx, 6
0x1800356b1  mov     [rbx+18h], edx
0x1800356b4  test    edx, edx
0x1800356b6  jnz     short loc_1800356BF
0x1800356b8  mov     dword ptr [rbx+18h], 1
0x1800356bf  mov     eax, [rdi+1Ch]
0x1800356c2  mov     [rbx+1Ch], eax
0x1800356c5  mov     rax, [rdi+20h]
0x1800356c9  mov     [rbx+20h], rax
0x1800356cd  mov     rcx, cs:hMutex; Handle
0x1800356d4  test    rcx, rcx
0x1800356d7  jz      loc_180035766
0x1800356dd  lea     r8, [rsp+68h+Timeout]; Timeout
0x1800356e2  mov     qword ptr [rsp+68h+Timeout], 0FFFFFFFFFFC2F700h
0x1800356eb  xor     edx, edx; Alertable
0x1800356ed  call    cs:__imp_NtWaitForSingleObject
0x1800356f3  mov     ecx, eax; int
0x1800356f5  call    ?PerfpDosError@@YAKJ@Z; PerfpDosError(long)
0x1800356fa  test    eax, eax
0x1800356fc  jnz     short loc_18003576B
0x1800356fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180035705  test    byte ptr [rcx+1Ch], 40h
0x180035709  jz      short loc_18003572E
0x18003570b  cmp     byte ptr [rcx+19h], 4
0x18003570f  jb      short loc_18003572E
0x180035711  mov     rcx, [rcx+10h]
0x180035715  lea     edx, [rax+16h]
0x180035718  mov     eax, [rbx+18h]
0x18003571b  lea     r8, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids
0x180035722  mov     r9, rbx
0x180035725  mov     [rsp+68h+dwCreationFlags], eax
0x180035729  call    WPP_SF_qd
0x18003572e  mov     rax, cs:hMem
0x180035735  mov     [rbx], rax
0x180035738  mov     rcx, cs:hMutex; hMutex
0x18003573f  mov     cs:hMem, rbx
0x180035746  call    cs:__imp_ReleaseMutex
0x18003574c  cmp     [rbx], r15
0x18003574f  jnz     short loc_18003575E
0x180035751  mov     rcx, cs:Object; hEvent
0x180035758  call    cs:__imp_SetEvent
0x18003575e  mov     rsi, rbx
0x180035761  jmp     loc_1800354D3
0x180035766  mov     eax, 15h
0x18003576b  mov     ecx, eax
0x18003576d  jmp     loc_1800354CD
```
