# ProcessAddNotification

- ea: `0x180002504`
- end: `0x1800026ca`
- name: `ProcessAddNotification`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180001320`

## callees

- `0x1800010e8`
- `0x180001158`
- `0x180001214`
- `0x180002504`
- `0x180002974`
- `0x180002f80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000252b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000252b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000260f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002624`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002693`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000260f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002624`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002693`
- `rtutils!TracePrintfExA` at `0x18000259d`
- `rtutils!TracePrintfExA` at `0x1800025d8`
- `rtutils!TracePrintfExA` at `0x180002606`
- `rtutils!TracePrintfExA` at `0x18000268a`
- `rtutils!TracePrintfExA` at `0x1800026b1`
- `rtutils!TracePrintfExA` at `0x18000259d`
- `rtutils!TracePrintfExA` at `0x1800025d8`
- `rtutils!TracePrintfExA` at `0x180002606`
- `rtutils!TracePrintfExA` at `0x18000268a`
- `rtutils!TracePrintfExA` at `0x1800026b1`

## string_xrefs

- `0x18000255e`: `ProcessAddNotification: InitializeRasmanMonitorThread failed, Error=%d`
- `0x180002593`: `Rasman Service Status when ProcessAddNotification called for first time: %d`

## pseudocode

```c
__int64 __fastcall ProcessAddNotification(__int64 a1, __int64 a2, int a3, unsigned int a4)
{
  DWORD v8; // ecx
  unsigned int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax

  EnterCriticalSection(&g_RasCriticalSection);
  if ( !g_fRasmanMonitorThread )
  {
    v9 = InitializeRasmanMonitorThread();
    v10 = v9;
    if ( v9 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "ProcessAddNotification: InitializeRasmanMonitorThread failed, Error=%d", v9);
      goto LABEL_23;
    }
    g_fRasmanMonitorThread = 1;
    v11 = IsServiceRunning();
    v8 = g_dwTraceId;
    g_fRasmanStarted = v11;
    g_fRCNInitialized = v11;
    if ( g_dwTraceId == -1 )
      goto LABEL_8;
    TracePrintfExA(
      g_dwTraceId,
      0xCu,
      "Rasman Service Status when ProcessAddNotification called for first time: %d",
      v11);
  }
  v11 = g_fRasmanStarted;
LABEL_8:
  if ( !v11 )
    goto LABEL_20;
  EnterCriticalSection(&g_RasCriticalSection);
  if ( !g_fRasReferenced )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "RasmanAddNotification: Calling RasReferenceRasmanInternal");
    v12 = RasReferenceRasmanInternal(1);
    v10 = v12;
    if ( v12 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "RasmanAddNotification: RasReferenceRasmanInternal failed, Error=%d", v12);
      LeaveCriticalSection(&g_RasCriticalSection);
      goto LABEL_23;
    }
    g_fRasReferenced = 1;
  }
  LeaveCriticalSection(&g_RasCriticalSection);
  v13 = SubmitLocalRequest(0x46u, a4, a1, a2, a3);
  v10 = v13;
  if ( v13 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "RasmanAddNotification: SubmitLocalRequest failed, Error: %d", v13);
  }
  else
  {
LABEL_20:
    v14 = AddNotifierToList(v8, a1, a2, a3, a4);
    v10 = v14;
    if ( v14 && g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "ProcessAddNotification: AddNotifierList failed, Error=%d", v14);
  }
LABEL_23:
  LeaveCriticalSection(&g_RasCriticalSection);
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "ProcessAddNotification exiting ... %d", v10);
  return v10;
}

```

## disassembly

```asm
0x180002504  push    rbx
0x180002506  push    rbp
0x180002507  push    rsi
0x180002508  push    rdi
0x180002509  push    r12
0x18000250b  push    r13
0x18000250d  push    r14
0x18000250f  push    r15
0x180002511  sub     rsp, 38h
0x180002515  mov     r14, rcx
0x180002518  lea     r13, g_RasCriticalSection
0x18000251f  mov     rcx, r13; lpCriticalSection
0x180002522  mov     edi, r9d
0x180002525  mov     esi, r8d
0x180002528  mov     rbp, rdx
0x18000252b  call    cs:__imp_EnterCriticalSection
0x180002531  or      r15d, 0FFFFFFFFh
0x180002535  mov     r12d, 0Ch
0x18000253b  cmp     cs:g_fRasmanMonitorThread, 0
0x180002542  jnz     short loc_1800025A3
0x180002544  call    InitializeRasmanMonitorThread
0x180002549  mov     ebx, eax
0x18000254b  test    eax, eax
0x18000254d  jz      short loc_18000256A
0x18000254f  mov     ecx, cs:g_dwTraceId
0x180002555  cmp     ecx, r15d
0x180002558  jz      loc_180002690
0x18000255e  lea     r8, aProcessaddnoti_1; "ProcessAddNotification: InitializeRasma"...
0x180002565  jmp     loc_180002684
0x18000256a  mov     cs:g_fRasmanMonitorThread, 1
0x180002574  call    IsServiceRunning
0x180002579  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000257f  mov     cs:g_fRasmanStarted, eax
0x180002585  mov     cs:g_fRCNInitialized, eax
0x18000258b  cmp     ecx, r15d
0x18000258e  jz      short loc_1800025A9
0x180002590  mov     r9d, eax
0x180002593  lea     r8, aRasmanServiceS; "Rasman Service Status when ProcessAddNo"...
0x18000259a  mov     edx, r12d; dwFlags
0x18000259d  call    cs:__imp_TracePrintfExA
0x1800025a3  mov     eax, cs:g_fRasmanStarted
0x1800025a9  test    eax, eax
0x1800025ab  jz      loc_18000265A
0x1800025b1  mov     rcx, r13; lpCriticalSection
0x1800025b4  call    cs:__imp_EnterCriticalSection
0x1800025ba  cmp     cs:g_fRasReferenced, 0
0x1800025c1  jnz     short loc_180002621
0x1800025c3  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800025c9  cmp     ecx, r15d
0x1800025cc  jz      short loc_1800025DE
0x1800025ce  lea     r8, aRasmanaddnotif_3; "RasmanAddNotification: Calling RasRefer"...
0x1800025d5  mov     edx, r12d; dwFlags
0x1800025d8  call    cs:__imp_TracePrintfExA
0x1800025de  mov     ecx, 1
0x1800025e3  call    RasReferenceRasmanInternal
0x1800025e8  mov     ebx, eax
0x1800025ea  test    eax, eax
0x1800025ec  jz      short loc_180002617
0x1800025ee  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800025f4  cmp     ecx, r15d
0x1800025f7  jz      short loc_18000260C
0x1800025f9  mov     r9d, eax
0x1800025fc  lea     r8, aRasmanaddnotif_0; "RasmanAddNotification: RasReferenceRasm"...
0x180002603  mov     edx, r12d; dwFlags
0x180002606  call    cs:__imp_TracePrintfExA
0x18000260c  mov     rcx, r13; lpCriticalSection
0x18000260f  call    cs:__imp_LeaveCriticalSection
0x180002615  jmp     short loc_180002690
0x180002617  mov     cs:g_fRasReferenced, 1
0x180002621  mov     rcx, r13; lpCriticalSection
0x180002624  call    cs:__imp_LeaveCriticalSection
0x18000262a  mov     ecx, 46h ; 'F'
0x18000262f  mov     [rsp+78h+var_58], esi
0x180002633  mov     r9, rbp
0x180002636  mov     r8, r14
0x180002639  mov     edx, edi
0x18000263b  call    SubmitLocalRequest
0x180002640  mov     ebx, eax
0x180002642  test    eax, eax
0x180002644  jz      short loc_18000265A
0x180002646  mov     ecx, cs:g_dwTraceId
0x18000264c  cmp     ecx, r15d
0x18000264f  jz      short loc_180002690
0x180002651  lea     r8, aRasmanaddnotif_2; "RasmanAddNotification: SubmitLocalReque"...
0x180002658  jmp     short loc_180002684
0x18000265a  mov     r9d, esi
0x18000265d  mov     [rsp+78h+var_58], edi
0x180002661  mov     r8, rbp
0x180002664  mov     rdx, r14
0x180002667  call    AddNotifierToList
0x18000266c  mov     ebx, eax
0x18000266e  test    eax, eax
0x180002670  jz      short loc_180002690
0x180002672  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180002678  cmp     ecx, r15d
0x18000267b  jz      short loc_180002690
0x18000267d  lea     r8, aProcessaddnoti_0; "ProcessAddNotification: AddNotifierList"...
0x180002684  mov     r9d, eax
0x180002687  mov     edx, r12d; dwFlags
0x18000268a  call    cs:__imp_TracePrintfExA
0x180002690  mov     rcx, r13; lpCriticalSection
0x180002693  call    cs:__imp_LeaveCriticalSection
0x180002699  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000269f  cmp     ecx, r15d
0x1800026a2  jz      short loc_1800026B7
0x1800026a4  mov     r9d, ebx
0x1800026a7  lea     r8, aProcessaddnoti; "ProcessAddNotification exiting ... %d"
0x1800026ae  mov     edx, r12d; dwFlags
0x1800026b1  call    cs:__imp_TracePrintfExA
0x1800026b7  mov     eax, ebx
0x1800026b9  add     rsp, 38h
0x1800026bd  pop     r15
0x1800026bf  pop     r14
0x1800026c1  pop     r13
0x1800026c3  pop     r12
0x1800026c5  pop     rdi
0x1800026c6  pop     rsi
0x1800026c7  pop     rbp
0x1800026c8  pop     rbx
0x1800026c9  retn
```
