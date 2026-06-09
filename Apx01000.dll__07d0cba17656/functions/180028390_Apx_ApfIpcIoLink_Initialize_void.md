# Apx::ApfIpcIoLink::Initialize(void)

- ea: `0x180028390`
- end: `0x180028726`
- name: `?Initialize@ApfIpcIoLink@Apx@@EEAAJXZ`
- size: `918`
- prototype: `__int64 __fastcall(unsigned __int64 this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180002160`
- `0x18000a12c`
- `0x18000caac`
- `0x18001051c`
- `0x180011e6c`
- `0x180028390`
- `0x1800295dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800284d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800284d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028423`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028423`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800285f8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002865a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800285f8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002865a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028481`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002860a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002866c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028481`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002860a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002866c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002843e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002844b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002843e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002844b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180028477`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180028477`

## pseudocode

```c
__int64 __fastcall Apx::ApfIpcIoLink::Initialize(unsigned __int64 this)
{
  _QWORD *v2; // rcx
  __int64 v3; // rbp
  HANDLE CurrentProcess; // rax
  void *v5; // rdi
  void *v6; // rbx
  HANDLE v7; // rax
  signed int LastError; // eax
  HANDLE v9; // rax
  signed int v10; // ebx
  _QWORD *v11; // r10
  __int64 v12; // rdx
  void *v14; // rax
  HANDLE EventW; // rax
  signed int v16; // eax
  HANDLE v17; // rax
  signed int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  HANDLE TargetHandle; // [rsp+70h] [rbp+8h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = *(_QWORD *)(this + 104);
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_(v2[2], 26, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  TargetHandle = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 16));
  if ( *(_QWORD *)(v3 + 88) )
  {
    if ( !*(_BYTE *)(v3 + 117) )
    {
      CurrentProcess = GetCurrentProcess();
      v5 = *(void **)(v3 + 88);
      v6 = CurrentProcess;
      v7 = GetCurrentProcess();
      if ( !DuplicateHandle(v7, v5, v6, &TargetHandle, 0, 0, 2u) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids,
            ~v3,
            LastError);
        }
        TargetHandle = 0;
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 16));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  }
  v9 = TargetHandle;
  *(_QWORD *)(this + 112) = TargetHandle;
  if ( !v9 )
  {
    v10 = -2147467259;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return (unsigned int)v10;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_30;
    v12 = 18;
    goto LABEL_28;
  }
  v14 = operator new(0x318u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)(this + 256) = v14;
  if ( !v14 )
  {
    v10 = -2147024882;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return (unsigned int)v10;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_30;
    v12 = 19;
    goto LABEL_28;
  }
  EventW = CreateEventW(0, 1, 1, 0);
  *(_QWORD *)(this + 416) = EventW;
  if ( EventW )
  {
    v17 = CreateEventW(0, 1, 1, 0);
    *(_QWORD *)(this + 424) = v17;
    if ( v17 )
    {
      v10 = Apx::ApfWorkItemQueue::Initialize((Apx::ApfWorkItemQueue *)(this + 120));
      if ( v10 >= 0 )
      {
        v10 = Apx::ApfWorkItemQueue::Initialize((Apx::ApfWorkItemQueue *)(this + 264));
        if ( v10 >= 0 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_qqi(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v19,
              v20,
              ~*(_QWORD *)(this + 104),
              ~this,
              *(_QWORD *)(this + 64));
            v11 = WPP_GLOBAL_Control;
          }
          v10 = 0;
          goto LABEL_30;
        }
      }
      goto LABEL_29;
    }
    v18 = GetLastError();
    v10 = v18;
    if ( v18 > 0 )
      v10 = (unsigned __int16)v18 | 0x80070000;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 21;
        goto LABEL_28;
      }
LABEL_30:
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
        WPP_SF_(v11[2], 23, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
    }
  }
  else
  {
    v16 = GetLastError();
    v10 = v16;
    if ( v16 > 0 )
      v10 = (unsigned __int16)v16 | 0x80070000;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 20;
LABEL_28:
        WPP_SF_qqd(v11[2], v12, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids, ~this, *(_QWORD *)(this + 64), v10);
LABEL_29:
        v11 = WPP_GLOBAL_Control;
        goto LABEL_30;
      }
      goto LABEL_30;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180028390  mov     [rsp+arg_8], rbx
0x180028395  mov     [rsp+arg_10], rbp
0x18002839a  push    rsi
0x18002839b  push    rdi
0x18002839c  push    r12
0x18002839e  push    r13
0x1800283a0  push    r14
0x1800283a2  sub     rsp, 40h
0x1800283a6  mov     rsi, rcx
0x1800283a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800283b0  lea     r12, WPP_GLOBAL_Control
0x1800283b7  mov     r13d, 1
0x1800283bd  cmp     rcx, r12
0x1800283c0  jz      short loc_1800283E9
0x1800283c2  test    [rcx+1Ch], r13b
0x1800283c6  jz      short loc_1800283E9
0x1800283c8  cmp     byte ptr [rcx+19h], 5
0x1800283cc  jb      short loc_1800283E9
0x1800283ce  mov     rcx, [rcx+10h]
0x1800283d2  lea     edx, [r13+10h]
0x1800283d6  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x1800283dd  call    WPP_SF_
0x1800283e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800283e9  mov     rbp, [rsi+68h]
0x1800283ed  cmp     rcx, r12
0x1800283f0  jz      short loc_180028413
0x1800283f2  test    [rcx+1Ch], r13b
0x1800283f6  jz      short loc_180028413
0x1800283f8  cmp     byte ptr [rcx+19h], 5
0x1800283fc  jb      short loc_180028413
0x1800283fe  mov     rcx, [rcx+10h]
0x180028402  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180028409  mov     edx, 1Ah
0x18002840e  call    WPP_SF_
0x180028413  lea     r14, [rbp+10h]
0x180028417  mov     [rsp+68h+TargetHandle], 0
0x180028420  mov     rcx, r14; lpCriticalSection
0x180028423  call    cs:__imp_EnterCriticalSection
0x180028429  cmp     qword ptr [rbp+58h], 0
0x18002842e  jz      loc_1800284D3
0x180028434  cmp     byte ptr [rbp+75h], 0
0x180028438  jnz     loc_1800284D3
0x18002843e  call    cs:__imp_GetCurrentProcess
0x180028444  mov     rdi, [rbp+58h]
0x180028448  mov     rbx, rax
0x18002844b  call    cs:__imp_GetCurrentProcess
0x180028451  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180028459  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x18002845e  mov     rcx, rax; hSourceProcessHandle
0x180028461  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180028469  mov     r8, rbx; hTargetProcessHandle
0x18002846c  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x180028474  mov     rdx, rdi; hSourceHandle
0x180028477  call    cs:__imp_DuplicateHandle
0x18002847d  test    eax, eax
0x18002847f  jnz     short loc_1800284D3
0x180028481  call    cs:__imp_GetLastError
0x180028487  test    eax, eax
0x180028489  jle     short loc_180028493
0x18002848b  movzx   eax, ax
0x18002848e  or      eax, 80070000h
0x180028493  mov     rcx, cs:WPP_GLOBAL_Control
0x18002849a  cmp     rcx, r12
0x18002849d  jz      short loc_1800284CA
0x18002849f  test    byte ptr [rcx+1Ch], 20h
0x1800284a3  jz      short loc_1800284CA
0x1800284a5  cmp     byte ptr [rcx+19h], 2
0x1800284a9  jb      short loc_1800284CA
0x1800284ab  mov     rcx, [rcx+10h]
0x1800284af  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x1800284b6  not     rbp
0x1800284b9  mov     [rsp+68h+dwDesiredAccess], eax
0x1800284bd  mov     r9, rbp
0x1800284c0  mov     edx, 1Bh
0x1800284c5  call    WPP_SF_qd
0x1800284ca  mov     [rsp+68h+TargetHandle], 0
0x1800284d3  mov     rcx, r14; lpCriticalSection
0x1800284d6  call    cs:__imp_LeaveCriticalSection
0x1800284dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284e3  cmp     rcx, r12
0x1800284e6  jz      short loc_180028509
0x1800284e8  test    [rcx+1Ch], r13b
0x1800284ec  jz      short loc_180028509
0x1800284ee  cmp     byte ptr [rcx+19h], 5
0x1800284f2  jb      short loc_180028509
0x1800284f4  mov     rcx, [rcx+10h]
0x1800284f8  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x1800284ff  mov     edx, 1Ch
0x180028504  call    WPP_SF_
0x180028509  mov     rax, [rsp+68h+TargetHandle]
0x18002850e  mov     [rsi+70h], rax
0x180028512  test    rax, rax
0x180028515  jnz     loc_1800285A9
0x18002851b  mov     ebx, 80004005h
0x180028520  mov     r10, cs:WPP_GLOBAL_Control
0x180028527  cmp     r10, r12
0x18002852a  jz      short loc_18002858E
0x18002852c  test    byte ptr [r10+1Ch], 20h
0x180028531  jz      short loc_180028567
0x180028533  cmp     byte ptr [r10+19h], 2
0x180028538  jb      short loc_180028567
0x18002853a  lea     edx, [rax+12h]
0x18002853d  mov     rax, [rsi+40h]
0x180028541  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180028548  mov     rcx, [r10+10h]
0x18002854c  mov     r9, rsi
0x18002854f  not     r9
0x180028552  mov     [rsp+68h+bInheritHandle], ebx
0x180028556  mov     qword ptr [rsp+68h+dwDesiredAccess], rax
0x18002855b  call    WPP_SF_qqd
0x180028560  mov     r10, cs:WPP_GLOBAL_Control
0x180028567  cmp     r10, r12
0x18002856a  jz      short loc_18002858E
0x18002856c  test    [r10+1Ch], r13b
0x180028570  jz      short loc_18002858E
0x180028572  cmp     byte ptr [r10+19h], 5
0x180028577  jb      short loc_18002858E
0x180028579  mov     rcx, [r10+10h]
0x18002857d  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180028584  mov     edx, 17h
0x180028589  call    WPP_SF_
0x18002858e  lea     r11, [rsp+68h+var_28]
0x180028593  mov     eax, ebx
0x180028595  mov     rbx, [r11+38h]
0x180028599  mov     rbp, [r11+40h]
0x18002859d  mov     rsp, r11
0x1800285a0  pop     r14
0x1800285a2  pop     r13
0x1800285a4  pop     r12
0x1800285a6  pop     rdi
0x1800285a7  pop     rsi
0x1800285a8  retn
0x1800285a9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800285b0  mov     ecx, 318h; unsigned __int64
0x1800285b5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800285ba  mov     [rsi+100h], rax
0x1800285c1  test    rax, rax
0x1800285c4  jnz     short loc_1800285ED
0x1800285c6  mov     ebx, 8007000Eh
0x1800285cb  mov     r10, cs:WPP_GLOBAL_Control
0x1800285d2  cmp     r10, r12
0x1800285d5  jz      short loc_18002858E
0x1800285d7  test    byte ptr [r10+1Ch], 20h
0x1800285dc  jz      short loc_180028567
0x1800285de  cmp     byte ptr [r10+19h], 2
0x1800285e3  jb      short loc_180028567
0x1800285e5  lea     edx, [rax+13h]
0x1800285e8  jmp     loc_18002853D
0x1800285ed  xor     r9d, r9d; lpName
0x1800285f0  mov     r8d, r13d; bInitialState
0x1800285f3  mov     edx, r13d; bManualReset
0x1800285f6  xor     ecx, ecx; lpEventAttributes
0x1800285f8  call    cs:__imp_CreateEventW
0x1800285fe  mov     [rsi+1A0h], rax
0x180028605  test    rax, rax
0x180028608  jnz     short loc_18002864F
0x18002860a  call    cs:__imp_GetLastError
0x180028610  mov     ebx, eax
0x180028612  test    eax, eax
0x180028614  jle     short loc_18002861F
0x180028616  movzx   ebx, ax
0x180028619  or      ebx, 80070000h
0x18002861f  mov     r10, cs:WPP_GLOBAL_Control
0x180028626  cmp     r10, r12
0x180028629  jz      loc_18002858E
0x18002862f  test    byte ptr [r10+1Ch], 20h
0x180028634  jz      loc_180028567
0x18002863a  cmp     byte ptr [r10+19h], 2
0x18002863f  jb      loc_180028567
0x180028645  mov     edx, 14h
0x18002864a  jmp     loc_18002853D
0x18002864f  xor     r9d, r9d; lpName
0x180028652  mov     r8d, r13d; bInitialState
0x180028655  mov     edx, r13d; bManualReset
0x180028658  xor     ecx, ecx; lpEventAttributes
0x18002865a  call    cs:__imp_CreateEventW
0x180028660  mov     [rsi+1A8h], rax
0x180028667  test    rax, rax
0x18002866a  jnz     short loc_1800286B1
0x18002866c  call    cs:__imp_GetLastError
0x180028672  mov     ebx, eax
0x180028674  test    eax, eax
0x180028676  jle     short loc_180028681
0x180028678  movzx   ebx, ax
0x18002867b  or      ebx, 80070000h
0x180028681  mov     r10, cs:WPP_GLOBAL_Control
0x180028688  cmp     r10, r12
0x18002868b  jz      loc_18002858E
0x180028691  test    byte ptr [r10+1Ch], 20h
0x180028696  jz      loc_180028567
0x18002869c  cmp     byte ptr [r10+19h], 2
0x1800286a1  jb      loc_180028567
0x1800286a7  mov     edx, 15h
0x1800286ac  jmp     loc_18002853D
0x1800286b1  lea     rcx, [rsi+78h]; this
0x1800286b5  call    ?Initialize@ApfWorkItemQueue@Apx@@QEAAJXZ; Apx::ApfWorkItemQueue::Initialize(void)
0x1800286ba  mov     ebx, eax
0x1800286bc  test    eax, eax
0x1800286be  js      loc_180028560
0x1800286c4  lea     rcx, [rsi+108h]; this
0x1800286cb  call    ?Initialize@ApfWorkItemQueue@Apx@@QEAAJXZ; Apx::ApfWorkItemQueue::Initialize(void)
0x1800286d0  mov     ebx, eax
0x1800286d2  test    eax, eax
0x1800286d4  js      loc_180028560
0x1800286da  mov     r10, cs:WPP_GLOBAL_Control
0x1800286e1  cmp     r10, r12
0x1800286e4  jz      short loc_18002871F
0x1800286e6  test    byte ptr [r10+1Ch], 20h
0x1800286eb  jz      short loc_18002871F
0x1800286ed  cmp     byte ptr [r10+19h], 4
0x1800286f2  jb      short loc_18002871F
0x1800286f4  mov     rax, [rsi+40h]
0x1800286f8  mov     rcx, rsi
0x1800286fb  mov     r9, [rsi+68h]
0x1800286ff  not     rcx
0x180028702  mov     qword ptr [rsp+68h+bInheritHandle], rax
0x180028707  not     r9
0x18002870a  mov     qword ptr [rsp+68h+dwDesiredAccess], rcx
0x18002870f  mov     rcx, [r10+10h]
0x180028713  call    WPP_SF_qqi
0x180028718  mov     r10, cs:WPP_GLOBAL_Control
0x18002871f  xor     ebx, ebx
0x180028721  jmp     loc_180028567
```
