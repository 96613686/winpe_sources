# CProcess::UpdateStreamCountAndProcessCategory(ushort const *,ulong,int,int,int *,_APPLICATION_CATEGORY *)

- ea: `0x1800279f0`
- end: `0x180027e7f`
- name: `?UpdateStreamCountAndProcessCategory@CProcess@@IEAAXPEBGKHHPEAHPEAW4_APPLICATION_CATEGORY@@@Z`
- size: `1167`
- prototype: `void __usercall(CProcess *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, int@<r9d>, int, int *, enum _APPLICATION_CATEGORY *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180022390`
- `0x180024bf0`

## callees

- `0x18000c3c0`
- `0x18001d580`
- `0x18001d650`
- `0x1800279f0`
- `0x180031960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027ba1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027ba1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027c0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027c0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027bde`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027bde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027bcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027bcb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180027b7f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180027d23`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180027b7f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180027d23`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180027cf6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180027cf6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180027b91`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180027b91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027bd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027bd6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180027e52`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180027e52`
- `ntdll!NtAcquireProcessActivityReference` at `0x180027bfc`
- `ntdll!NtAcquireProcessActivityReference` at `0x180027bfc`

## pseudocode

```c
void __fastcall CProcess::UpdateStreamCountAndProcessCategory(
        CProcess *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        int a4,
        int a5,
        int *a6,
        enum _APPLICATION_CATEGORY *a7)
{
  __int64 v9; // r12
  int v10; // ebx
  __int64 v11; // rsi
  int v12; // r14d
  int v13; // edx
  struct _TP_TIMER *v14; // rcx
  char *v15; // r15
  __int64 v16; // r13
  DWORD LastError; // ebx
  __int64 v18; // r10
  _WORD *v19; // r8
  wchar_t *v20; // rcx
  wchar_t *v21; // rdx
  __int64 v22; // rax
  bool v23; // zf
  int v24; // eax
  struct _TP_TIMER *ThreadpoolTimer; // rax
  __int64 v26; // rax
  int v27; // eax
  int v28; // esi
  int v29; // [rsp+30h] [rbp-A1h] BYREF
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp-99h] BYREF
  int *v31; // [rsp+40h] [rbp-91h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-89h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-71h] BYREF
  void *v34; // [rsp+70h] [rbp-61h]
  int v35; // [rsp+78h] [rbp-59h]
  int v36; // [rsp+7Ch] [rbp-55h]
  _WORD *v37; // [rsp+80h] [rbp-51h]
  int v38; // [rsp+88h] [rbp-49h]
  int v39; // [rsp+8Ch] [rbp-45h]
  int **v40; // [rsp+90h] [rbp-41h]
  __int64 v41; // [rsp+98h] [rbp-39h]
  int *v42; // [rsp+A0h] [rbp-31h]
  __int64 v43; // [rsp+A8h] [rbp-29h]
  wchar_t *v44; // [rsp+B0h] [rbp-21h]
  int v45; // [rsp+B8h] [rbp-19h]
  int v46; // [rsp+BCh] [rbp-15h]
  wchar_t *v47; // [rsp+C0h] [rbp-11h]
  int v48; // [rsp+C8h] [rbp-9h]
  int v49; // [rsp+CCh] [rbp-5h]

  v9 = a3;
  v10 = *((_DWORD *)this + 78);
  v11 = -1;
  *(_QWORD *)&EventDescriptor.Id = a7;
  v12 = 1;
  v29 = v10;
  v31 = a6;
  if ( !a4 )
    v12 = -1;
  pftDueTime = 0;
  if ( CProcess::GetActiveStreamCountStatsForEndpoint(this, a2, a5, (unsigned int **)&pftDueTime) >= 0 )
  {
    *(_DWORD *)(4 * v9 + *(_QWORD *)&pftDueTime) += v12;
    if ( a5 )
    {
      *((_DWORD *)this + 77) += v12;
    }
    else
    {
      *((_DWORD *)this + 76) += v12;
      if ( CProcess::GetActiveRenderStreamCount(this, 3u) || CProcess::GetActiveRenderStreamCount(this, 8u) )
      {
        *((_DWORD *)this + 78) = 0;
      }
      else if ( CProcess::GetActiveRenderStreamCount(this, 2u) )
      {
        *((_DWORD *)this + 78) = 1;
      }
      else if ( CProcess::GetActiveRenderStreamCount(this, 0xBu)
             || CProcess::GetActiveRenderStreamCount(this, 0xAu)
             || CProcess::GetActiveRenderStreamCount(this, 1u) )
      {
        *((_DWORD *)this + 78) = 2;
      }
      else
      {
        *((_DWORD *)this + 78) = (CProcess::GetActiveRenderStreamCount(this, 7u) == 0) + 3;
      }
    }
    v13 = *((_DWORD *)this + 76) + *((_DWORD *)this + 77);
    if ( a4 )
    {
      if ( v13 == 1 )
      {
        v14 = (struct _TP_TIMER *)*((_QWORD *)this + 73);
        if ( v14 )
        {
          SetThreadpoolTimer(v14, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 73), 1);
        }
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
        v15 = (char *)*((_QWORD *)this + 72);
        if ( ((unsigned __int64)(v15 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        {
          v16 = *((_QWORD *)this + 19);
          if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            LastError = GetLastError();
            CloseHandle(v15);
            SetLastError(LastError);
          }
          *((_QWORD *)this + 72) = 0;
          NtAcquireProcessActivityReference((char *)this + 576, v16, 0);
        }
        if ( this != (CProcess *)-536LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
        v10 = v29;
      }
    }
    else if ( !v13 )
    {
      ThreadpoolTimer = (struct _TP_TIMER *)*((_QWORD *)this + 73);
      if ( ThreadpoolTimer
        || (ThreadpoolTimer = CreateThreadpoolTimer(
                                lambda_27ffc4f27c89750b73dd50f8af6b1d3e_::_lambda_invoker_cdecl_,
                                this,
                                0),
            (*((_QWORD *)this + 73) = ThreadpoolTimer) != 0) )
      {
        pftDueTime = (struct _FILETIME)-200000000LL;
        SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
      }
    }
  }
  if ( *(_QWORD *)&EventDescriptor.Id )
    **(_DWORD **)&EventDescriptor.Id = v10;
  if ( v31 )
    *v31 = v10 != *((_DWORD *)this + 78);
  if ( v10 != *((_DWORD *)this + 78) )
  {
    v18 = *((_QWORD *)AudioSrvPolicyManagerTelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v18 > 4u
      && (*(_QWORD *)(v18 + 16) & 0x20000LL) != 0
      && (*(_QWORD *)(v18 + 24) & 0x20000LL) == *(_QWORD *)(v18 + 24) )
    {
      v19 = (_WORD *)*((_QWORD *)this + 22);
      v20 = off_180051630[*((int *)this + 78)];
      v21 = off_180051630[v10];
      v29 = *((_DWORD *)this + 40);
      v31 = (int *)*((_QWORD *)this + 26);
      if ( v20 )
      {
        v22 = -1;
        do
          v23 = v20[++v22] == 0;
        while ( !v23 );
        v24 = 2 * v22 + 2;
      }
      else
      {
        v20 = (wchar_t *)&unk_180053B30;
        v24 = 2;
      }
      v47 = v20;
      v48 = v24;
      v49 = 0;
      if ( v21 )
      {
        v26 = -1;
        do
          v23 = v21[++v26] == 0;
        while ( !v23 );
        v27 = 2 * v26 + 2;
      }
      else
      {
        v21 = (wchar_t *)&unk_180053B30;
        v27 = 2;
      }
      v45 = v27;
      v42 = &v29;
      v40 = &v31;
      v44 = v21;
      v46 = 0;
      v43 = 4;
      v41 = 8;
      if ( v19 )
      {
        do
          v23 = v19[++v11] == 0;
        while ( !v23 );
        v28 = 2 * v11 + 2;
      }
      else
      {
        v19 = &unk_180053B30;
        v28 = 2;
      }
      *(_DWORD *)&EventDescriptor.Level = 4;
      UserData.Ptr = *(_QWORD *)(v18 + 8);
      v37 = v19;
      v38 = v28;
      v39 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0x20000;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v34 = &unk_18005734E;
      UserData.Reserved = 2;
      v35 = 78;
      v36 = 1;
      pftDueTime.dwLowDateTime = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v18 + 32), &EventDescriptor, 0, 0, 7u, &UserData);
    }
  }
}

```

## disassembly

```asm
0x1800279f0  mov     [rsp-8+arg_18], rbx
0x1800279f5  push    rbp
0x1800279f6  push    rsi
0x1800279f7  push    rdi
0x1800279f8  push    r12
0x1800279fa  push    r13
0x1800279fc  push    r14
0x1800279fe  push    r15
0x180027a00  lea     rbp, [rsp-0Fh]
0x180027a05  sub     rsp, 0E0h
0x180027a0c  mov     rax, cs:__security_cookie
0x180027a13  xor     rax, rsp
0x180027a16  mov     [rbp+3Fh+var_40], rax
0x180027a1a  mov     rax, [rbp+3Fh+arg_28]
0x180027a1e  mov     rdi, rcx
0x180027a21  mov     rcx, [rbp+3Fh+arg_30]
0x180027a25  test    r9d, r9d
0x180027a28  mov     r15d, [rbp+3Fh+arg_20]
0x180027a2c  mov     r13d, r9d
0x180027a2f  mov     r12d, r8d
0x180027a32  lea     r9, [rsp+110h+pftDueTime]; unsigned int **
0x180027a37  mov     ebx, [rdi+138h]
0x180027a3d  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180027a44  mov     qword ptr [rsp+110h+EventDescriptor.Id], rcx
0x180027a49  mov     r14d, 1
0x180027a4f  mov     r8d, r15d; int
0x180027a52  mov     [rsp+110h+var_E0], ebx
0x180027a56  mov     rcx, rdi; this
0x180027a59  mov     [rsp+110h+var_D0], rax
0x180027a5e  cmovz   r14d, esi
0x180027a62  mov     qword ptr [rsp+110h+pftDueTime.dwLowDateTime], 0
0x180027a6b  call    ?GetActiveStreamCountStatsForEndpoint@CProcess@@IEAAJPEBGHPEAPEAI@Z; CProcess::GetActiveStreamCountStatsForEndpoint(ushort const *,int,uint * *)
0x180027a70  test    eax, eax
0x180027a72  js      loc_180027C14
0x180027a78  mov     rax, qword ptr [rsp+110h+pftDueTime.dwLowDateTime]
0x180027a7d  lea     rcx, ds:0[r12*4]
0x180027a85  add     [rcx+rax], r14d
0x180027a89  test    r15d, r15d
0x180027a8c  jnz     loc_180027B46
0x180027a92  add     [rdi+130h], r14d
0x180027a99  mov     edx, 3; unsigned int
0x180027a9e  mov     rcx, rdi; this
0x180027aa1  call    ?GetActiveRenderStreamCount@CProcess@@QEAAIK@Z; CProcess::GetActiveRenderStreamCount(ulong)
0x180027aa6  test    eax, eax
0x180027aa8  jnz     loc_180027B3A
0x180027aae  mov     edx, 8; unsigned int
0x180027ab3  mov     rcx, rdi; this
0x180027ab6  call    ?GetActiveRenderStreamCount@CProcess@@QEAAIK@Z; CProcess::GetActiveRenderStreamCount(ulong)
0x180027abb  test    eax, eax
0x180027abd  jnz     short loc_180027B3A
0x180027abf  mov     edx, 2; unsigned int
0x180027ac4  mov     rcx, rdi; this
0x180027ac7  call    ?GetActiveRenderStreamCount@CProcess@@QEAAIK@Z; CProcess::GetActiveRenderStreamCount(ulong)
0x180027acc  test    eax, eax
0x180027ace  jz      short loc_180027ADC
0x180027ad0  mov     dword ptr [rdi+138h], 1
0x180027ada  jmp     short loc_180027B4D
0x180027adc  mov     edx, 0Bh; unsigned int
0x180027ae1  mov     rcx, rdi; this
0x180027ae4  call    ?GetActiveRenderStreamCount@CProcess@@QEAAIK@Z; CProcess::GetActiveRenderStreamCount(ulong)
0x180027ae9  test    eax, eax
0x180027aeb  jnz     short loc_180027B2E
0x180027aed  mov     edx, 0Ah; unsigned int
0x180027af2  mov     rcx, rdi; this
0x180027af5  call    ?GetActiveRenderStreamCount@CProcess@@QEAAIK@Z; CProcess::GetActiveRenderStreamCount(ulong)
0x180027afa  test    eax, eax
0x180027afc  jnz     short loc_180027B2E
0x180027afe  mov     edx, 1; unsigned int
0x180027b03  mov     rcx, rdi; this
0x180027b06  call    ?GetActiveRenderStreamCount@CProcess@@QEAAIK@Z; CProcess::GetActiveRenderStreamCount(ulong)
0x180027b0b  test    eax, eax
0x180027b0d  jnz     short loc_180027B2E
0x180027b0f  mov     edx, 7; unsigned int
0x180027b14  mov     rcx, rdi; this
0x180027b17  call    ?GetActiveRenderStreamCount@CProcess@@QEAAIK@Z; CProcess::GetActiveRenderStreamCount(ulong)
0x180027b1c  xor     ecx, ecx
0x180027b1e  test    eax, eax
0x180027b20  setz    cl
0x180027b23  add     ecx, 3
0x180027b26  mov     [rdi+138h], ecx
0x180027b2c  jmp     short loc_180027B4D
0x180027b2e  mov     dword ptr [rdi+138h], 2
0x180027b38  jmp     short loc_180027B4D
0x180027b3a  mov     dword ptr [rdi+138h], 0
0x180027b44  jmp     short loc_180027B4D
0x180027b46  add     [rdi+134h], r14d
0x180027b4d  mov     edx, [rdi+134h]
0x180027b53  add     edx, [rdi+130h]
0x180027b59  test    r13d, r13d
0x180027b5c  jz      loc_180027CD5
0x180027b62  cmp     edx, 1
0x180027b65  jnz     loc_180027C14
0x180027b6b  mov     rcx, [rdi+248h]; pti
0x180027b72  test    rcx, rcx
0x180027b75  jz      short loc_180027B97
0x180027b77  xor     r9d, r9d; msWindowLength
0x180027b7a  xor     r8d, r8d; msPeriod
0x180027b7d  xor     edx, edx; pftDueTime
0x180027b7f  call    cs:__imp_SetThreadpoolTimer
0x180027b85  mov     rcx, [rdi+248h]; pti
0x180027b8c  mov     edx, 1; fCancelPendingCallbacks
0x180027b91  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180027b97  lea     r14, [rdi+218h]
0x180027b9e  mov     rcx, r14; lpCriticalSection
0x180027ba1  call    cs:__imp_EnterCriticalSection
0x180027ba7  mov     r15, [rdi+240h]
0x180027bae  lea     rax, [r15+1]
0x180027bb2  test    rax, 0FFFFFFFFFFFFFFFEh
0x180027bb8  jnz     short loc_180027C02
0x180027bba  mov     r13, [rdi+98h]
0x180027bc1  lea     rax, [r15-1]
0x180027bc5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180027bc9  ja      short loc_180027BE4
0x180027bcb  call    cs:__imp_GetLastError
0x180027bd1  mov     rcx, r15; hObject
0x180027bd4  mov     ebx, eax
0x180027bd6  call    cs:__imp_CloseHandle
0x180027bdc  mov     ecx, ebx; dwErrCode
0x180027bde  call    cs:__imp_SetLastError
0x180027be4  xor     r8d, r8d
0x180027be7  mov     qword ptr [rdi+240h], 0
0x180027bf2  mov     rdx, r13
0x180027bf5  lea     rcx, [rdi+240h]
0x180027bfc  call    cs:__imp_NtAcquireProcessActivityReference
0x180027c02  test    r14, r14
0x180027c05  jz      short loc_180027C10
0x180027c07  mov     rcx, r14; lpCriticalSection
0x180027c0a  call    cs:__imp_LeaveCriticalSection
0x180027c10  mov     ebx, [rsp+110h+var_E0]
0x180027c14  mov     rax, qword ptr [rsp+110h+EventDescriptor.Id]
0x180027c19  test    rax, rax
0x180027c1c  jz      short loc_180027C20
0x180027c1e  mov     [rax], ebx
0x180027c20  mov     rcx, [rsp+110h+var_D0]
0x180027c25  xor     r14d, r14d
0x180027c28  test    rcx, rcx
0x180027c2b  jz      short loc_180027C3B
0x180027c2d  cmp     ebx, [rdi+138h]
0x180027c33  mov     eax, r14d
0x180027c36  setnz   al
0x180027c39  mov     [rcx], eax
0x180027c3b  cmp     ebx, [rdi+138h]
0x180027c41  jz      loc_180027E58
0x180027c47  call    ?Instance@AudioSrvPolicyManagerTelemetryProvider@@KAPEAV1@XZ; AudioSrvPolicyManagerTelemetryProvider::Instance(void)
0x180027c4c  mov     r10, [rax+8]
0x180027c50  mov     eax, [r10]
0x180027c53  cmp     eax, 4
0x180027c56  jbe     loc_180027E58
0x180027c5c  mov     rcx, [r10+18h]
0x180027c60  mov     rax, [r10+10h]
0x180027c64  bt      rax, 11h
0x180027c69  jnb     loc_180027E58
0x180027c6f  mov     rax, rcx
0x180027c72  and     eax, 20000h
0x180027c77  cmp     rax, rcx
0x180027c7a  jnz     loc_180027E58
0x180027c80  movsxd  rax, dword ptr [rdi+138h]
0x180027c87  lea     rdx, off_180051630; "AppCat_Communication"
0x180027c8e  mov     r8, [rdi+0B0h]
0x180027c95  mov     rcx, [rdx+rax*8]
0x180027c99  movsxd  rax, ebx
0x180027c9c  mov     rdx, [rdx+rax*8]
0x180027ca0  mov     eax, [rdi+0A0h]
0x180027ca6  mov     [rsp+110h+var_E0], eax
0x180027caa  mov     rax, [rdi+0D0h]
0x180027cb1  mov     [rsp+110h+var_D0], rax
0x180027cb6  test    rcx, rcx
0x180027cb9  jz      short loc_180027D2E
0x180027cbb  mov     rax, rsi
0x180027cbe  xchg    ax, ax
0x180027cc0  cmp     word ptr [rcx+rax*2+2], 0
0x180027cc6  lea     rax, [rax+1]
0x180027cca  jnz     short loc_180027CC0
0x180027ccc  lea     eax, ds:2[rax*2]
0x180027cd3  jmp     short loc_180027D3A
0x180027cd5  test    edx, edx
0x180027cd7  jnz     loc_180027C14
0x180027cdd  mov     rax, [rdi+248h]
0x180027ce4  test    rax, rax
0x180027ce7  jnz     short loc_180027D0C
0x180027ce9  xor     r8d, r8d; pcbe
0x180027cec  lea     rcx, _lambda_27ffc4f27c89750b73dd50f8af6b1d3e____lambda_invoker_cdecl_; pfnti
0x180027cf3  mov     rdx, rdi; pv
0x180027cf6  call    cs:__imp_CreateThreadpoolTimer
0x180027cfc  mov     [rdi+248h], rax
0x180027d03  test    rax, rax
0x180027d06  jz      loc_180027C14
0x180027d0c  xor     r9d, r9d; msWindowLength
0x180027d0f  mov     qword ptr [rsp+110h+pftDueTime.dwLowDateTime], 0FFFFFFFFF4143E00h
0x180027d18  xor     r8d, r8d; msPeriod
0x180027d1b  lea     rdx, [rsp+110h+pftDueTime]; pftDueTime
0x180027d20  mov     rcx, rax; pti
0x180027d23  call    cs:__imp_SetThreadpoolTimer
0x180027d29  jmp     loc_180027C14
0x180027d2e  lea     rcx, unk_180053B30
0x180027d35  mov     eax, 2
0x180027d3a  mov     [rbp+3Fh+var_50], rcx
0x180027d3e  mov     [rbp+3Fh+var_48], eax
0x180027d41  mov     [rbp+3Fh+var_44], r14d
0x180027d45  test    rdx, rdx
0x180027d48  jz      short loc_180027D65
0x180027d4a  mov     rax, rsi
0x180027d4d  nop     dword ptr [rax]
0x180027d50  cmp     word ptr [rdx+rax*2+2], 0
0x180027d56  lea     rax, [rax+1]
0x180027d5a  jnz     short loc_180027D50
0x180027d5c  lea     eax, ds:2[rax*2]
0x180027d63  jmp     short loc_180027D71
0x180027d65  lea     rdx, unk_180053B30
0x180027d6c  mov     eax, 2
0x180027d71  mov     [rbp+3Fh+var_58], eax
0x180027d74  lea     rax, [rsp+110h+var_E0]
0x180027d79  mov     [rbp+3Fh+var_70], rax
0x180027d7d  lea     rax, [rsp+110h+var_D0]
0x180027d82  mov     [rbp+3Fh+var_80], rax
0x180027d86  mov     [rbp+3Fh+var_60], rdx
0x180027d8a  mov     [rbp+3Fh+var_54], r14d
0x180027d8e  mov     [rbp+3Fh+var_68], 4
0x180027d96  mov     [rbp+3Fh+var_78], 8
0x180027d9e  test    r8, r8
0x180027da1  jz      short loc_180027DB9
0x180027da3  cmp     word ptr [r8+rsi*2+2], 0
0x180027daa  lea     rsi, [rsi+1]
0x180027dae  jnz     short loc_180027DA3
0x180027db0  lea     esi, ds:2[rsi*2]
0x180027db7  jmp     short loc_180027DC5
0x180027db9  lea     r8, unk_180053B30
0x180027dc0  mov     esi, 2
0x180027dc5  movzx   eax, cs:word_180057344
0x180027dcc  lea     rcx, _TraceLoggingMetadata
0x180027dd3  mov     dword ptr [rsp+110h+EventDescriptor.Level], eax
0x180027dd7  lea     rdx, [rsp+110h+EventDescriptor]; EventDescriptor
0x180027ddc  mov     rax, [r10+8]
0x180027de0  xor     r9d, r9d; RelatedActivityId
0x180027de3  mov     [rbp+3Fh+var_B0.Ptr], rax
0x180027de7  mov     [rbp+3Fh+var_90], r8
0x180027deb  xor     r8d, r8d; ActivityId
0x180027dee  mov     [rbp+3Fh+var_88], esi
0x180027df1  mov     [rbp+3Fh+var_84], r14d
0x180027df5  mov     dword ptr [rsp+110h+EventDescriptor.Id], 0B000000h
0x180027dfd  mov     [rsp+110h+EventDescriptor.Keyword], 20000h
0x180027e06  movzx   eax, word ptr [rax]
0x180027e09  mov     [rbp+3Fh+var_B0.Size], eax
0x180027e0c  lea     rax, unk_18005734E
0x180027e13  mov     [rbp+3Fh+var_A0], rax
0x180027e17  lea     rax, _TraceLoggingMetadataEnd
0x180027e1e  sub     eax, ecx
0x180027e20  mov     dword ptr [rbp+3Fh+var_B0.0Ch], 2
0x180027e27  mov     [rbp+3Fh+var_98], 4Eh ; 'N'
0x180027e2e  mov     [rbp+3Fh+var_94], 1
0x180027e35  mov     [rsp+110h+pftDueTime.dwLowDateTime], eax
0x180027e39  mov     eax, [rsp+110h+pftDueTime.dwLowDateTime]
0x180027e3d  mov     rcx, [r10+20h]; RegHandle
0x180027e41  lea     rax, [rbp+3Fh+var_B0]
0x180027e45  mov     [rsp+110h+UserData], rax; UserData
0x180027e4a  mov     [rsp+110h+UserDataCount], 7; UserDataCount
0x180027e52  call    cs:__imp_EventWriteTransfer
0x180027e58  mov     rcx, [rbp+3Fh+var_40]
0x180027e5c  xor     rcx, rsp; StackCookie
0x180027e5f  call    __security_check_cookie
0x180027e64  mov     rbx, [rsp+110h+arg_18]
0x180027e6c  add     rsp, 0E0h
0x180027e73  pop     r15
0x180027e75  pop     r14
0x180027e77  pop     r13
0x180027e79  pop     r12
0x180027e7b  pop     rdi
0x180027e7c  pop     rsi
0x180027e7d  pop     rbp
0x180027e7e  retn
```
