# MyService::WorkerThread(void)

- ea: `0x180008510`
- end: `0x18000882f`
- name: `?WorkerThread@MyService@@UEAAKXZ`
- size: `799`
- prototype: `unsigned int __fastcall(MyService *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008510`
- `0x180008840`
- `0x1800098a0`
- `0x18000ae04`
- `0x18000b648`
- `0x180010740`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800087a4`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800087a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000879b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800087ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800087d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000879b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800087ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800087d0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800087ba`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800087db`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800087ba`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800087db`
- `wbemcomn!?Close@CEventLog@@QEAAHXZ` at `0x18000877d`
- `wbemcomn!?Close@CEventLog@@QEAAHXZ` at `0x18000877d`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x180008774`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x180008774`
- `wbemcomn!?Open@CEventLog@@QEAAHXZ` at `0x1800085d8`
- `wbemcomn!?Open@CEventLog@@QEAAHXZ` at `0x1800085d8`
- `wbemcomn!??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z` at `0x1800085be`
- `wbemcomn!??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z` at `0x1800085be`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180008599`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180008599`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000857a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000857a`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall MyService::WorkerThread(void **this)
{
  CEventLog *v3; // rax
  CInsertionString *v4; // r13
  CInsertionString *v5; // r12
  CInsertionString *v6; // r15
  CInsertionString *v7; // r14
  CInsertionString *v8; // rsi
  CInsertionString *v9; // rdi
  CInsertionString *v10; // rbx
  CInsertionString *v11; // rax
  unsigned int v12; // edx
  HANDLE CurrentThread; // rax
  int ThreadPriority; // ebx
  HANDLE v15; // rax
  HANDLE v16; // rax
  _BYTE v17[16]; // [rsp+C0h] [rbp-D8h] BYREF
  _BYTE v18[16]; // [rsp+D0h] [rbp-C8h] BYREF
  _BYTE v19[16]; // [rsp+E0h] [rbp-B8h] BYREF
  _BYTE v20[16]; // [rsp+F0h] [rbp-A8h] BYREF
  _BYTE v21[16]; // [rsp+100h] [rbp-98h] BYREF
  _BYTE v22[16]; // [rsp+110h] [rbp-88h] BYREF
  _BYTE v23[16]; // [rsp+120h] [rbp-78h] BYREF
  _BYTE v24[16]; // [rsp+130h] [rbp-68h] BYREF
  _BYTE v25[16]; // [rsp+140h] [rbp-58h] BYREF
  _BYTE v26[72]; // [rsp+150h] [rbp-48h] BYREF
  CEventLog *v27; // [rsp+1A0h] [rbp+8h]
  CInsertionString *v28; // [rsp+1A8h] [rbp+10h]
  CInsertionString *v29; // [rsp+1B0h] [rbp+18h]
  void **v30; // [rsp+1B8h] [rbp+20h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_2716f4bd31e130f967505b342dce5479_Traceguids);
  }
  v30 = this + 8;
  if ( (unsigned int)Initialize(this[8]) )
  {
    try
    {
      v3 = (CEventLog *)CWin32DefaultArena::WbemMemAlloc(0x58u);
      if ( v3 )
        v3 = CEventLog::CEventLog(v3, 0, (const struct _GUID *)S_WinMgmtR, 0xAu);
      v27 = v3;
      if ( v3 )
      {
        CEventLog::Open(v3);
        v28 = CInsertionString::CInsertionString((CInsertionString *)v17);
        v29 = CInsertionString::CInsertionString((CInsertionString *)v18);
        v4 = CInsertionString::CInsertionString((CInsertionString *)v19);
        v5 = CInsertionString::CInsertionString((CInsertionString *)v20);
        v6 = CInsertionString::CInsertionString((CInsertionString *)v21);
        v7 = CInsertionString::CInsertionString((CInsertionString *)v22);
        v8 = CInsertionString::CInsertionString((CInsertionString *)v23);
        v9 = CInsertionString::CInsertionString((CInsertionString *)v24);
        v10 = CInsertionString::CInsertionString((CInsertionString *)v25);
        v11 = CInsertionString::CInsertionString((CInsertionString *)v26);
        CEventLog::Report(v27, 0, WBEM_MC_WBEM_STARTED_SUCESSFULLY, v11, v10, v9, v8, v7, v6, v5, v4, v29, v28);
        CEventLog::Close(v27);
        CEventLog::`scalar deleting destructor'(v27, v12);
      }
    }
    catch ( CX_MemoryException )
    {
    }
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    v15 = GetCurrentThread();
    SetThreadPriority(v15, 2);
    WaitingFunction(*v30);
    v16 = GetCurrentThread();
    SetThreadPriority(v16, ThreadPriority);
    if ( dword_180032CC8 != 0x80000000
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_2716f4bd31e130f967505b342dce5479_Traceguids);
    }
    return 0;
  }
  else
  {
    if ( g_ProgRes )
    {
      CoUninitialize();
      g_ProgRes = 0;
    }
    return 2147749908LL;
  }
}

```

## disassembly

```asm
0x180008510  push    rbx
0x180008512  push    rsi
0x180008513  push    rdi
0x180008514  push    r12
0x180008516  push    r13
0x180008518  push    r14
0x18000851a  push    r15
0x18000851c  sub     rsp, 160h
0x180008523  mov     rbx, rcx
0x180008526  lea     rdi, WPP_GLOBAL_Control
0x18000852d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008534  cmp     rcx, rdi
0x180008537  jz      short loc_18000855A
0x180008539  test    byte ptr [rcx+1Ch], 1
0x18000853d  jz      short loc_18000855A
0x18000853f  cmp     byte ptr [rcx+19h], 5
0x180008543  jb      short loc_18000855A
0x180008545  mov     edx, 23h ; '#'
0x18000854a  lea     r8, WPP_2716f4bd31e130f967505b342dce5479_Traceguids
0x180008551  mov     rcx, [rcx+10h]
0x180008555  call    WPP_SF_
0x18000855a  lea     rax, [rbx+40h]
0x18000855e  mov     [rsp+198h+arg_18], rax
0x180008566  mov     rcx, [rax]; void *
0x180008569  call    ?Initialize@@YAHPEAX@Z; Initialize(void *)
0x18000856e  test    eax, eax
0x180008570  jnz     short loc_180008594
0x180008572  cmp     dword ptr cs:?g_ProgRes@@3U_PROG_RESOURCES@@A, eax; _PROG_RESOURCES g_ProgRes
0x180008578  jz      short loc_18000858A
0x18000857a  call    cs:__imp_CoUninitialize
0x180008580  mov     dword ptr cs:?g_ProgRes@@3U_PROG_RESOURCES@@A, 0; _PROG_RESOURCES g_ProgRes
0x18000858a  mov     eax, 80041014h
0x18000858f  jmp     loc_18000881C
0x180008594  mov     ecx, 58h ; 'X'
0x180008599  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000859f  mov     [rsp+198h+arg_8], rax
0x1800085a7  test    rax, rax
0x1800085aa  jz      short loc_1800085C4
0x1800085ac  mov     r9d, 0Ah
0x1800085b2  lea     r8, S_WinMgmtR
0x1800085b9  xor     edx, edx
0x1800085bb  mov     rcx, rax
0x1800085be  call    cs:__imp_??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z; CEventLog::CEventLog(ushort const *,_GUID const &,ulong)
0x1800085c4  mov     [rsp+198h+arg_0], rax
0x1800085cc  test    rax, rax
0x1800085cf  jz      loc_180008792
0x1800085d5  mov     rcx, rax
0x1800085d8  call    cs:__imp_?Open@CEventLog@@QEAAHXZ; CEventLog::Open(void)
0x1800085de  lea     rax, [rsp+198h+var_D8]
0x1800085e6  mov     [rsp+198h+var_128], rax
0x1800085eb  lea     rcx, [rsp+198h+var_D8]; this
0x1800085f3  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800085f8  mov     [rsp+198h+arg_8], rax
0x180008600  lea     rax, [rsp+198h+var_C8]
0x180008608  mov     [rsp+198h+var_120], rax
0x18000860d  lea     rcx, [rsp+198h+var_C8]; this
0x180008615  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18000861a  mov     [rsp+198h+arg_10], rax
0x180008622  lea     rax, [rsp+198h+var_B8]
0x18000862a  mov     [rsp+198h+var_118], rax
0x180008632  lea     rcx, [rsp+198h+var_B8]; this
0x18000863a  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18000863f  mov     r13, rax
0x180008642  lea     rax, [rsp+198h+var_A8]
0x18000864a  mov     [rsp+198h+var_110], rax
0x180008652  lea     rcx, [rsp+198h+var_A8]; this
0x18000865a  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18000865f  mov     r12, rax
0x180008662  lea     rax, [rsp+198h+var_98]
0x18000866a  mov     [rsp+198h+var_108], rax
0x180008672  lea     rcx, [rsp+198h+var_98]; this
0x18000867a  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18000867f  mov     r15, rax
0x180008682  lea     rax, [rsp+198h+var_88]
0x18000868a  mov     [rsp+198h+var_100], rax
0x180008692  lea     rcx, [rsp+198h+var_88]; this
0x18000869a  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18000869f  mov     r14, rax
0x1800086a2  lea     rax, [rsp+198h+var_78]
0x1800086aa  mov     [rsp+198h+var_F8], rax
0x1800086b2  lea     rcx, [rsp+198h+var_78]; this
0x1800086ba  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800086bf  mov     rsi, rax
0x1800086c2  lea     rax, [rsp+198h+var_68]
0x1800086ca  mov     [rsp+198h+var_F0], rax
0x1800086d2  lea     rcx, [rsp+198h+var_68]; this
0x1800086da  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800086df  mov     rdi, rax
0x1800086e2  lea     rax, [rsp+198h+var_58]
0x1800086ea  mov     [rsp+198h+var_E8], rax
0x1800086f2  lea     rcx, [rsp+198h+var_58]; this
0x1800086fa  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800086ff  mov     rbx, rax
0x180008702  lea     rax, [rsp+198h+var_48]
0x18000870a  mov     [rsp+198h+var_E0], rax
0x180008712  lea     rcx, [rsp+198h+var_48]; this
0x18000871a  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18000871f  nop
0x180008720  xor     edx, edx
0x180008722  mov     rcx, [rsp+198h+arg_8]
0x18000872a  mov     [rsp+198h+var_138], rcx
0x18000872f  mov     rcx, [rsp+198h+arg_10]
0x180008737  mov     [rsp+198h+var_140], rcx
0x18000873c  mov     [rsp+198h+var_148], r13
0x180008741  mov     [rsp+198h+var_150], r12
0x180008746  mov     [rsp+198h+var_158], r15
0x18000874b  mov     [rsp+198h+var_160], r14
0x180008750  mov     [rsp+198h+var_168], rsi
0x180008755  mov     [rsp+198h+var_170], rdi
0x18000875a  mov     [rsp+198h+var_178], rbx
0x18000875f  mov     r9, rax
0x180008762  lea     r8, WBEM_MC_WBEM_STARTED_SUCESSFULLY
0x180008769  mov     rbx, [rsp+198h+arg_0]
0x180008771  mov     rcx, rbx
0x180008774  call    cs:__imp_?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z; CEventLog::Report(ushort,_EVENT_DESCRIPTOR const &,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString)
0x18000877a  mov     rcx, rbx
0x18000877d  call    cs:__imp_?Close@CEventLog@@QEAAHXZ; CEventLog::Close(void)
0x180008783  mov     rcx, rbx; this
0x180008786  call    ??_GCEventLog@@QEAAPEAXI@Z; CEventLog::`scalar deleting destructor'(uint)
0x18000878b  lea     rdi, WPP_GLOBAL_Control
0x180008792  jmp     short loc_18000879B
0x180008794  lea     rdi, WPP_GLOBAL_Control
0x18000879b  call    cs:__imp_GetCurrentThread
0x1800087a1  mov     rcx, rax; hThread
0x1800087a4  call    cs:__imp_GetThreadPriority
0x1800087aa  mov     ebx, eax
0x1800087ac  call    cs:__imp_GetCurrentThread
0x1800087b2  mov     rcx, rax; hThread
0x1800087b5  mov     edx, 2; nPriority
0x1800087ba  call    cs:__imp_SetThreadPriority
0x1800087c0  mov     rcx, [rsp+198h+arg_18]
0x1800087c8  mov     rcx, [rcx]; void *
0x1800087cb  call    ?WaitingFunction@@YAXPEAX@Z; WaitingFunction(void *)
0x1800087d0  call    cs:__imp_GetCurrentThread
0x1800087d6  mov     rcx, rax; hThread
0x1800087d9  mov     edx, ebx; nPriority
0x1800087db  call    cs:__imp_SetThreadPriority
0x1800087e1  cmp     cs:dword_180032CC8, 80000000h
0x1800087eb  jz      short loc_18000881A
0x1800087ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087f4  cmp     rcx, rdi
0x1800087f7  jz      short loc_18000881A
0x1800087f9  test    byte ptr [rcx+1Ch], 1
0x1800087fd  jz      short loc_18000881A
0x1800087ff  cmp     byte ptr [rcx+19h], 5
0x180008803  jb      short loc_18000881A
0x180008805  mov     edx, 24h ; '$'
0x18000880a  lea     r8, WPP_2716f4bd31e130f967505b342dce5479_Traceguids
0x180008811  mov     rcx, [rcx+10h]
0x180008815  call    WPP_SF_
0x18000881a  xor     eax, eax
0x18000881c  add     rsp, 160h
0x180008823  pop     r15
0x180008825  pop     r14
0x180008827  pop     r13
0x180008829  pop     r12
0x18000882b  pop     rdi
0x18000882c  pop     rsi
0x18000882d  pop     rbx
0x18000882e  retn
```
