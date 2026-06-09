# CTieringEngineTaskHandler::FinalConstruct(void)

- ea: `0x14003750c`
- end: `0x1400377bb`
- name: `?FinalConstruct@CTieringEngineTaskHandler@@QEAAJXZ`
- size: `687`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x140002f58`
- `0x14000321c`

## callees

- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140009f1c`
- `0x14003750c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003759c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003760b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400376ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003759c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003760b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400376ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140037653`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400376c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400376ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140037737`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140037740`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140037749`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140037653`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400376c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400376ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140037737`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140037740`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140037749`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14003758e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400375fd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14003766b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14003758e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400375fd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14003766b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1400376e4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1400376e4`

## string_xrefs

- `0x14003752f`: `CTieringEngineTaskHandler::FinalConstruct`

## pseudocode

```c
__int64 __fastcall CTieringEngineTaskHandler::FinalConstruct(PVOID pv)
{
  HANDLE EventW; // rbx
  signed int v3; // eax
  unsigned int v4; // ebx
  HANDLE v5; // rdi
  signed int v6; // eax
  unsigned int v7; // edi
  HANDLE v8; // rsi
  signed int v9; // eax
  unsigned int v10; // esi
  PTP_WORK ThreadpoolWork; // rax
  signed int LastError; // eax
  unsigned int v13; // ebp
  _BYTE v15[8]; // [rsp+20h] [rbp-48h] BYREF
  unsigned int v16; // [rsp+28h] [rbp-40h]

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieringEngineTaskHandler::FinalConstruct";
  CHResultImp::CHResultImp((CHResultImp *)v15);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, pv);
  }
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW )
  {
    v5 = CreateEventW(0, 1, 0, 0);
    if ( v5 )
    {
      v8 = CreateEventW(0, 1, 0, 0);
      if ( v8 )
      {
        ThreadpoolWork = CreateThreadpoolWork(CTieringEngineTaskHandler::ScanTaskStartCallback, pv, 0);
        if ( ThreadpoolWork )
        {
          *((_QWORD *)pv + 9) = v5;
          *((_QWORD *)pv + 8) = EventW;
          *((_QWORD *)pv + 10) = v8;
          *((_QWORD *)pv + 12) = ThreadpoolWork;
          *((_OWORD *)pv + 7) = 0;
          v16 = 0;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, pv);
          }
          v4 = 0;
        }
        else
        {
          LastError = GetLastError();
          v13 = LastError;
          if ( LastError > 0 )
            v13 = (unsigned __int16)LastError | 0x80070000;
          v16 = v13;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, v13);
          }
          CloseHandle(v8);
          CloseHandle(v5);
          CloseHandle(EventW);
          v4 = v13;
        }
      }
      else
      {
        v9 = GetLastError();
        v10 = v9;
        if ( v9 > 0 )
          v10 = (unsigned __int16)v9 | 0x80070000;
        v16 = v10;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, v10);
        }
        CloseHandle(v5);
        CloseHandle(EventW);
        v4 = v10;
      }
    }
    else
    {
      v6 = GetLastError();
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      v16 = v7;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, v7);
      }
      CloseHandle(EventW);
      v4 = v7;
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v16 = v4;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, v4);
    }
  }
  CHResultImp::~CHResultImp((CHResultImp *)v15);
  return v4;
}

```

## disassembly

```asm
0x14003750c  push    rbx
0x14003750e  push    rbp
0x14003750f  push    rsi
0x140037510  push    rdi
0x140037511  push    r12
0x140037513  push    r14
0x140037515  push    r15
0x140037517  sub     rsp, 30h
0x14003751b  mov     rax, gs:58h
0x140037524  mov     rbp, rcx
0x140037527  mov     ecx, 8
0x14003752c  mov     rdx, [rax]
0x14003752f  lea     rax, aCtieringengine_2; "CTieringEngineTaskHandler::FinalConstru"...
0x140037536  mov     [rcx+rdx], rax
0x14003753a  lea     rcx, [rsp+68h+var_48]; this
0x14003753f  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140037544  mov     rcx, cs:WPP_GLOBAL_Control
0x14003754b  lea     r15, WPP_GLOBAL_Control
0x140037552  lea     r12, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x140037559  mov     r14d, 1
0x14003755f  cmp     rcx, r15
0x140037562  jz      short loc_140037583
0x140037564  test    [rcx+1Ch], r14b
0x140037568  jz      short loc_140037583
0x14003756a  cmp     byte ptr [rcx+19h], 4
0x14003756e  jb      short loc_140037583
0x140037570  mov     rcx, [rcx+10h]
0x140037574  lea     edx, [r14+9]
0x140037578  mov     r9, rbp
0x14003757b  mov     r8, r12
0x14003757e  call    WPP_SF_q
0x140037583  xor     r9d, r9d; lpName
0x140037586  xor     r8d, r8d; bInitialState
0x140037589  mov     edx, r14d; bManualReset
0x14003758c  xor     ecx, ecx; lpEventAttributes
0x14003758e  call    cs:__imp_CreateEventW
0x140037594  mov     rbx, rax
0x140037597  test    rax, rax
0x14003759a  jnz     short loc_1400375F2
0x14003759c  call    cs:__imp_GetLastError
0x1400375a2  mov     ebx, eax
0x1400375a4  test    eax, eax
0x1400375a6  jle     short loc_1400375B1
0x1400375a8  movzx   ebx, ax
0x1400375ab  or      ebx, 80070000h
0x1400375b1  mov     [rsp+68h+var_40], ebx
0x1400375b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400375bc  cmp     rcx, r15
0x1400375bf  jz      loc_1400377A0
0x1400375c5  test    [rcx+1Ch], r14b
0x1400375c9  jz      loc_1400377A0
0x1400375cf  cmp     byte ptr [rcx+19h], 2
0x1400375d3  jb      loc_1400377A0
0x1400375d9  mov     rcx, [rcx+10h]
0x1400375dd  mov     edx, 0Bh
0x1400375e2  mov     r9d, ebx
0x1400375e5  mov     r8, r12
0x1400375e8  call    WPP_SF_d
0x1400375ed  jmp     loc_1400377A0
0x1400375f2  xor     r9d, r9d; lpName
0x1400375f5  xor     r8d, r8d; bInitialState
0x1400375f8  mov     edx, r14d; bManualReset
0x1400375fb  xor     ecx, ecx; lpEventAttributes
0x1400375fd  call    cs:__imp_CreateEventW
0x140037603  mov     rdi, rax
0x140037606  test    rax, rax
0x140037609  jnz     short loc_140037660
0x14003760b  call    cs:__imp_GetLastError
0x140037611  mov     edi, eax
0x140037613  test    eax, eax
0x140037615  jle     short loc_140037620
0x140037617  movzx   edi, ax
0x14003761a  or      edi, 80070000h
0x140037620  mov     [rsp+68h+var_40], edi
0x140037624  mov     rcx, cs:WPP_GLOBAL_Control
0x14003762b  cmp     rcx, r15
0x14003762e  jz      short loc_140037650
0x140037630  test    [rcx+1Ch], r14b
0x140037634  jz      short loc_140037650
0x140037636  cmp     byte ptr [rcx+19h], 2
0x14003763a  jb      short loc_140037650
0x14003763c  mov     rcx, [rcx+10h]
0x140037640  mov     edx, 0Ch
0x140037645  mov     r9d, edi
0x140037648  mov     r8, r12
0x14003764b  call    WPP_SF_d
0x140037650  mov     rcx, rbx; hObject
0x140037653  call    cs:__imp_CloseHandle
0x140037659  mov     ebx, edi
0x14003765b  jmp     loc_1400377A0
0x140037660  xor     r9d, r9d; lpName
0x140037663  xor     r8d, r8d; bInitialState
0x140037666  mov     edx, r14d; bManualReset
0x140037669  xor     ecx, ecx; lpEventAttributes
0x14003766b  call    cs:__imp_CreateEventW
0x140037671  mov     rsi, rax
0x140037674  test    rax, rax
0x140037677  jnz     short loc_1400376D7
0x140037679  call    cs:__imp_GetLastError
0x14003767f  mov     esi, eax
0x140037681  test    eax, eax
0x140037683  jle     short loc_14003768E
0x140037685  movzx   esi, ax
0x140037688  or      esi, 80070000h
0x14003768e  mov     [rsp+68h+var_40], esi
0x140037692  mov     rcx, cs:WPP_GLOBAL_Control
0x140037699  cmp     rcx, r15
0x14003769c  jz      short loc_1400376BE
0x14003769e  test    [rcx+1Ch], r14b
0x1400376a2  jz      short loc_1400376BE
0x1400376a4  cmp     byte ptr [rcx+19h], 2
0x1400376a8  jb      short loc_1400376BE
0x1400376aa  mov     rcx, [rcx+10h]
0x1400376ae  mov     edx, 0Dh
0x1400376b3  mov     r9d, esi
0x1400376b6  mov     r8, r12
0x1400376b9  call    WPP_SF_d
0x1400376be  mov     rcx, rdi; hObject
0x1400376c1  call    cs:__imp_CloseHandle
0x1400376c7  mov     rcx, rbx; hObject
0x1400376ca  call    cs:__imp_CloseHandle
0x1400376d0  mov     ebx, esi
0x1400376d2  jmp     loc_1400377A0
0x1400376d7  xor     r8d, r8d; pcbe
0x1400376da  lea     rcx, ?ScanTaskStartCallback@CTieringEngineTaskHandler@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1400376e1  mov     rdx, rbp; pv
0x1400376e4  call    cs:__imp_CreateThreadpoolWork
0x1400376ea  test    rax, rax
0x1400376ed  jnz     short loc_140037753
0x1400376ef  call    cs:__imp_GetLastError
0x1400376f5  mov     ebp, eax
0x1400376f7  test    eax, eax
0x1400376f9  jle     short loc_140037704
0x1400376fb  movzx   ebp, ax
0x1400376fe  or      ebp, 80070000h
0x140037704  mov     [rsp+68h+var_40], ebp
0x140037708  mov     rcx, cs:WPP_GLOBAL_Control
0x14003770f  cmp     rcx, r15
0x140037712  jz      short loc_140037734
0x140037714  test    [rcx+1Ch], r14b
0x140037718  jz      short loc_140037734
0x14003771a  cmp     byte ptr [rcx+19h], 2
0x14003771e  jb      short loc_140037734
0x140037720  mov     rcx, [rcx+10h]
0x140037724  mov     edx, 0Eh
0x140037729  mov     r9d, ebp
0x14003772c  mov     r8, r12
0x14003772f  call    WPP_SF_d
0x140037734  mov     rcx, rsi; hObject
0x140037737  call    cs:__imp_CloseHandle
0x14003773d  mov     rcx, rdi; hObject
0x140037740  call    cs:__imp_CloseHandle
0x140037746  mov     rcx, rbx; hObject
0x140037749  call    cs:__imp_CloseHandle
0x14003774f  mov     ebx, ebp
0x140037751  jmp     short loc_1400377A0
0x140037753  xorps   xmm0, xmm0
0x140037756  mov     [rbp+48h], rdi
0x14003775a  mov     [rbp+40h], rbx
0x14003775e  mov     [rbp+50h], rsi
0x140037762  mov     [rbp+60h], rax
0x140037766  movups  xmmword ptr [rbp+70h], xmm0
0x14003776a  mov     [rsp+68h+var_40], 0
0x140037772  mov     rcx, cs:WPP_GLOBAL_Control
0x140037779  cmp     rcx, r15
0x14003777c  jz      short loc_14003779E
0x14003777e  test    [rcx+1Ch], r14b
0x140037782  jz      short loc_14003779E
0x140037784  cmp     byte ptr [rcx+19h], 4
0x140037788  jb      short loc_14003779E
0x14003778a  mov     rcx, [rcx+10h]
0x14003778e  mov     edx, 0Fh
0x140037793  mov     r9, rbp
0x140037796  mov     r8, r12
0x140037799  call    WPP_SF_q
0x14003779e  xor     ebx, ebx
0x1400377a0  lea     rcx, [rsp+68h+var_48]; this
0x1400377a5  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1400377aa  mov     eax, ebx
0x1400377ac  add     rsp, 30h
0x1400377b0  pop     r15
0x1400377b2  pop     r14
0x1400377b4  pop     r12
0x1400377b6  pop     rdi
0x1400377b7  pop     rsi
0x1400377b8  pop     rbp
0x1400377b9  pop     rbx
0x1400377ba  retn
```
