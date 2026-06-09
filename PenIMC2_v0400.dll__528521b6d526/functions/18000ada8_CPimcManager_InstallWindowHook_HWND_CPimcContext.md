# CPimcManager::InstallWindowHook(HWND__ *,CPimcContext *)

- ea: `0x18000ada8`
- end: `0x18000b098`
- name: `?InstallWindowHook@CPimcManager@@QEAAJPEAUHWND__@@PEAVCPimcContext@@@Z`
- size: `752`
- prototype: `__int64 __fastcall(CPimcManager *__hidden this, HWND, struct CPimcContext *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800062a0`

## callees

- `0x18000aa8c`
- `0x18000ac94`
- `0x18000ada8`
- `0x18000b0c4`
- `0x18000b228`
- `0x18000bffc`
- `0x18000ce0c`
- `0x18000e484`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000adff`
- `KERNEL32!WaitForSingleObject` at `0x18000adff`
- `KERNEL32!ReleaseMutex` at `0x18000af16`
- `KERNEL32!ReleaseMutex` at `0x18000b031`
- `KERNEL32!ReleaseMutex` at `0x18000af16`
- `KERNEL32!ReleaseMutex` at `0x18000b031`
- `KERNEL32!GetCurrentProcessId` at `0x18000ae1a`
- `KERNEL32!GetCurrentProcessId` at `0x18000ae1a`
- `KERNEL32!SetWaitableTimer` at `0x18000aef7`
- `KERNEL32!SetWaitableTimer` at `0x18000aef7`
- `USER32!GetWindowThreadProcessId` at `0x18000ae11`
- `USER32!GetWindowThreadProcessId` at `0x18000ae11`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CPimcManager::InstallWindowHook(CPimcManager *this, HWND a2, struct CPimcContext *a3)
{
  struct CHookThreadItem *v6; // rdi
  _DWORD *v7; // rsi
  DWORD v8; // ebx
  DWORD CurrentProcessId; // eax
  signed int v10; // r14d
  _DWORD *QuadPart; // r12
  bool v12; // al
  __int64 v13; // rcx
  int v14; // edx
  __int64 v15; // r10
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  char *v23; // rcx
  char *v24; // rcx
  int ArgToCompletionRoutine; // [rsp+30h] [rbp-30h] BYREF
  int v27; // [rsp+34h] [rbp-2Ch]
  int v28; // [rsp+38h] [rbp-28h]
  DWORD v29; // [rsp+3Ch] [rbp-24h]
  unsigned int WindowThreadProcessId; // [rsp+40h] [rbp-20h]
  void *Block; // [rsp+48h] [rbp-18h] BYREF
  struct CHookThreadItem *lpParameter; // [rsp+50h] [rbp-10h] BYREF
  LARGE_INTEGER DueTime; // [rsp+58h] [rbp-8h] BYREF
  DWORD dwProcessId; // [rsp+A8h] [rbp+48h] BYREF

  v28 = 0;
  v27 = 0;
  ArgToCompletionRoutine = 0;
  lpParameter = 0;
  v6 = 0;
  v7 = 0;
  Block = 0;
  DueTime.QuadPart = 0;
  v8 = 0;
  v29 = 0;
  if ( g_hMutexHook )
  {
    v8 = WaitForSingleObject(g_hMutexHook, 0xFFFFFFFF);
    v29 = v8;
  }
  WindowThreadProcessId = GetWindowThreadProcessId(a2, &dwProcessId);
  CurrentProcessId = GetCurrentProcessId();
  v10 = dwProcessId != CurrentProcessId ? 0x80000302 : 0;
  if ( CurrentProcessId != dwProcessId )
    goto LABEL_48;
  v10 = CPimcManager::EnsureHookThreadItem(
          (CPimcManager *)(dwProcessId - CurrentProcessId),
          WindowThreadProcessId,
          this,
          (unsigned __int64 *)&lpParameter,
          &ArgToCompletionRoutine);
  if ( v10 < 0 )
    goto LABEL_48;
  v6 = lpParameter;
  ++*((_DWORD *)lpParameter + 4);
  if ( !*((_QWORD *)v6 + 1) )
  {
    v10 = CPimcManager::InitializeHookThread(v6);
    if ( v10 < 0 )
      goto LABEL_15;
    v28 = 1;
  }
  *((_QWORD *)a3 + 21) = v6;
  v10 = CPimcManager::EnsureHookWindowItem(this, a2, (unsigned __int64 *)&Block);
  v7 = Block;
  if ( v10 >= 0 )
  {
    v27 = 1;
    QuadPart = Block;
    v10 = CPbPreallocArray<CPimcManager *,2>::Add((char *)Block + 32);
    if ( v10 >= 0 )
    {
      *((_QWORD *)a3 + 22) = v7;
      if ( v7[2] && (*((_BYTE *)v6 + 96) & 1) == 0 )
      {
        DueTime.QuadPart = -2500000;
        v12 = SetWaitableTimer(*((HANDLE *)v6 + 11), &DueTime, 0, 0, 0, 0);
        *((_DWORD *)v6 + 24) &= ~1u;
        *((_DWORD *)v6 + 24) |= v12;
      }
      if ( !v8 )
        ReleaseMutex(g_hMutexHook);
      return (unsigned int)v10;
    }
    goto LABEL_16;
  }
LABEL_15:
  QuadPart = (_DWORD *)DueTime.QuadPart;
LABEL_16:
  if ( ArgToCompletionRoutine )
  {
    v13 = 0;
    v14 = *((_DWORD *)v6 + 13);
    if ( v14 )
    {
      v15 = *((_QWORD *)v6 + 5);
      while ( *(CPimcManager **)(v15 + 8 * v13) != this )
        v13 = (unsigned int)(v13 + 1);
      if ( (unsigned int)v13 < v14 - 1 )
      {
        memcpy_0(
          (void *)(v15 + 8 * v13),
          (const void *)(v15 + 8LL * (unsigned int)(v13 + 1)),
          (unsigned int)(8 * (v14 - v13) - 8));
        v14 = *((_DWORD *)v6 + 13);
      }
      *((_DWORD *)v6 + 13) = v14 - 1;
    }
  }
  if ( (*((_DWORD *)v6 + 4))-- == 1 )
  {
    v17 = *((_QWORD *)v6 + 13);
    v18 = *((_QWORD *)v6 + 14);
    if ( v17 )
      *(_QWORD *)(v17 + 112) = v18;
    if ( v18 )
      *(_QWORD *)(v18 + 104) = v17;
    v19 = g_HookThreadMap;
    if ( (struct CHookThreadItem *)g_HookThreadMap == v6 )
      v19 = v18;
    g_HookThreadMap = v19;
    v20 = qword_180018A50;
    if ( (struct CHookThreadItem *)qword_180018A50 == v6 )
      v20 = v17;
    qword_180018A50 = v20;
  }
  if ( v27 && !QuadPart[15] )
  {
    v21 = *((_QWORD *)v7 + 8);
    v22 = *((_QWORD *)v7 + 9);
    if ( v21 )
      *(_QWORD *)(v21 + 72) = v22;
    if ( v22 )
      *(_QWORD *)(v22 + 64) = v21;
    if ( *((_DWORD **)this + 2) == v7 )
      *((_QWORD *)this + 2) = v22;
    if ( *((_DWORD **)this + 3) == v7 )
      *((_QWORD *)this + 3) = v21;
    DueTime.QuadPart = (LONGLONG)v7;
    lpParameter = (struct CHookThreadItem *)v7;
    v23 = (char *)*((_QWORD *)v7 + 6);
    if ( v23 && v23 != (char *)(v7 + 8) )
      operator delete(v23);
    operator delete(v7);
  }
LABEL_48:
  if ( !v8 )
    ReleaseMutex(g_hMutexHook);
  if ( v28 )
  {
    CPimcManager::TerminateHookThread(v6);
    DueTime.QuadPart = (LONGLONG)v6;
    if ( v6 )
    {
      v24 = (char *)*((_QWORD *)v6 + 5);
      if ( v24 && v24 != (char *)v6 + 24 )
        operator delete(v24);
      operator delete(v6);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000ada8  mov     [rsp-28h+arg_0], rbx
0x18000adad  mov     [rsp-28h+arg_8], rsi
0x18000adb2  mov     [rsp-28h+arg_10], rdi
0x18000adb7  push    rbp
0x18000adb8  push    r12
0x18000adba  push    r13
0x18000adbc  push    r14
0x18000adbe  push    r15
0x18000adc0  mov     rbp, rsp
0x18000adc3  sub     rsp, 60h
0x18000adc7  mov     r13, r8
0x18000adca  mov     r12, rdx
0x18000adcd  mov     r15, rcx
0x18000add0  xor     eax, eax
0x18000add2  mov     [rbp+var_28], eax
0x18000add5  mov     [rbp+var_2C], eax
0x18000add8  mov     [rbp+ArgToCompletionRoutine], eax
0x18000addb  mov     [rbp+lpParameter], rax
0x18000addf  mov     edi, eax
0x18000ade1  mov     esi, eax
0x18000ade3  mov     [rbp+Block], rax
0x18000ade7  mov     qword ptr [rbp+DueTime], rax
0x18000adeb  mov     ebx, eax
0x18000aded  mov     [rbp+var_24], eax
0x18000adf0  mov     rcx, cs:?g_hMutexHook@@3PEAXEA; hHandle
0x18000adf7  test    rcx, rcx
0x18000adfa  jz      short loc_18000AE0A
0x18000adfc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000adff  call    cs:__imp_WaitForSingleObject
0x18000ae05  mov     ebx, eax
0x18000ae07  mov     [rbp+var_24], eax
0x18000ae0a  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x18000ae0e  mov     rcx, r12; hWnd
0x18000ae11  call    cs:__imp_GetWindowThreadProcessId
0x18000ae17  mov     [rbp+var_20], eax
0x18000ae1a  call    cs:__imp_GetCurrentProcessId
0x18000ae20  mov     ecx, eax
0x18000ae22  sub     ecx, [rbp+dwProcessId]
0x18000ae25  neg     ecx; this
0x18000ae27  sbb     r14d, r14d
0x18000ae2a  and     r14d, 80000302h
0x18000ae31  cmp     eax, [rbp+dwProcessId]
0x18000ae34  jnz     loc_18000B026
0x18000ae3a  lea     rax, [rbp+ArgToCompletionRoutine]
0x18000ae3e  mov     [rsp+60h+lpArgToCompletionRoutine], rax; int *
0x18000ae43  lea     r9, [rbp+lpParameter]; unsigned __int64 *
0x18000ae47  mov     r8, r15; struct CPimcManager *
0x18000ae4a  mov     edx, [rbp+var_20]; unsigned int
0x18000ae4d  call    ?EnsureHookThreadItem@CPimcManager@@QEAAJKPEAV1@PEA_KPEAH@Z; CPimcManager::EnsureHookThreadItem(ulong,CPimcManager *,unsigned __int64 *,int *)
0x18000ae52  mov     r14d, eax
0x18000ae55  test    eax, eax
0x18000ae57  js      loc_18000B026
0x18000ae5d  mov     rdi, [rbp+lpParameter]
0x18000ae61  inc     dword ptr [rdi+10h]
0x18000ae64  cmp     qword ptr [rdi+8], 0
0x18000ae69  jnz     short loc_18000AE85
0x18000ae6b  mov     rcx, rdi; lpParameter
0x18000ae6e  call    ?InitializeHookThread@CPimcManager@@SAJPEAUCHookThreadItem@@@Z; CPimcManager::InitializeHookThread(CHookThreadItem *)
0x18000ae73  mov     r14d, eax
0x18000ae76  test    eax, eax
0x18000ae78  js      loc_18000AF21
0x18000ae7e  mov     [rbp+var_28], 1
0x18000ae85  mov     [r13+0A8h], rdi
0x18000ae8c  lea     r8, [rbp+Block]; unsigned __int64 *
0x18000ae90  mov     rdx, r12; HWND
0x18000ae93  mov     rcx, r15; this
0x18000ae96  call    ?EnsureHookWindowItem@CPimcManager@@QEAAJPEAUHWND__@@PEA_K@Z; CPimcManager::EnsureHookWindowItem(HWND__ *,unsigned __int64 *)
0x18000ae9b  mov     r14d, eax
0x18000ae9e  mov     rsi, [rbp+Block]
0x18000aea2  test    eax, eax
0x18000aea4  js      short loc_18000AF21
0x18000aea6  mov     [rbp+var_2C], 1
0x18000aead  mov     r12, rsi
0x18000aeb0  lea     rcx, [rsi+20h]; Src
0x18000aeb4  mov     rdx, r13
0x18000aeb7  call    ?Add@?$CPbPreallocArray@PEAVCPimcManager@@$01@@QEAAJPEAVCPimcManager@@H@Z; CPbPreallocArray<CPimcManager *,2>::Add(CPimcManager *,int)
0x18000aebc  mov     r14d, eax
0x18000aebf  test    eax, eax
0x18000aec1  js      short loc_18000AF25
0x18000aec3  mov     [r13+0B0h], rsi
0x18000aeca  cmp     dword ptr [rsi+8], 0
0x18000aece  jz      short loc_18000AF07
0x18000aed0  test    byte ptr [rdi+60h], 1
0x18000aed4  jnz     short loc_18000AF07
0x18000aed6  mov     qword ptr [rbp+DueTime], 0FFFFFFFFFFD9DA60h
0x18000aede  and     [rsp+60h+var_38], 0
0x18000aee3  and     [rsp+60h+lpArgToCompletionRoutine], 0
0x18000aee9  xor     r9d, r9d; pfnCompletionRoutine
0x18000aeec  xor     r8d, r8d; lPeriod
0x18000aeef  lea     rdx, [rbp+DueTime]; lpDueTime
0x18000aef3  mov     rcx, [rdi+58h]; hTimer
0x18000aef7  call    cs:__imp_SetWaitableTimer
0x18000aefd  and     dword ptr [rdi+60h], 0FFFFFFFEh
0x18000af01  and     eax, 1
0x18000af04  or      [rdi+60h], eax
0x18000af07  test    ebx, ebx
0x18000af09  jnz     loc_18000B077
0x18000af0f  mov     rcx, cs:?g_hMutexHook@@3PEAXEA; hMutex
0x18000af16  call    cs:__imp_ReleaseMutex
0x18000af1c  jmp     loc_18000B077
0x18000af21  mov     r12, qword ptr [rbp+DueTime]
0x18000af25  cmp     [rbp+ArgToCompletionRoutine], 0
0x18000af29  jz      short loc_18000AF6E
0x18000af2b  xor     ecx, ecx
0x18000af2d  mov     edx, [rdi+34h]
0x18000af30  test    edx, edx
0x18000af32  jz      short loc_18000AF6E
0x18000af34  mov     r10, [rdi+28h]
0x18000af38  lea     r9, [r10+rcx*8]
0x18000af3c  cmp     [r9], r15
0x18000af3f  jz      short loc_18000AF45
0x18000af41  inc     ecx
0x18000af43  jmp     short loc_18000AF38
0x18000af45  lea     eax, [rdx-1]
0x18000af48  cmp     ecx, eax
0x18000af4a  jnb     short loc_18000AF68
0x18000af4c  sub     edx, ecx
0x18000af4e  lea     r8d, ds:0FFFFFFFFFFFFFFF8h[rdx*8]; Size
0x18000af56  lea     eax, [rcx+1]
0x18000af59  lea     rdx, [r10+rax*8]; Src
0x18000af5d  mov     rcx, r9; void *
0x18000af60  call    memcpy_0
0x18000af65  mov     edx, [rdi+34h]
0x18000af68  lea     eax, [rdx-1]
0x18000af6b  mov     [rdi+34h], eax
0x18000af6e  add     dword ptr [rdi+10h], 0FFFFFFFFh
0x18000af72  jnz     short loc_18000AFB8
0x18000af74  mov     rdx, [rdi+68h]
0x18000af78  mov     rcx, [rdi+70h]
0x18000af7c  test    rdx, rdx
0x18000af7f  jz      short loc_18000AF85
0x18000af81  mov     [rdx+70h], rcx
0x18000af85  test    rcx, rcx
0x18000af88  jz      short loc_18000AF8E
0x18000af8a  mov     [rcx+68h], rdx
0x18000af8e  mov     rax, cs:?g_HookThreadMap@@3V?$CPbList@UCHookThreadItem@@@@A; CPbList<CHookThreadItem> g_HookThreadMap
0x18000af95  cmp     rax, rdi
0x18000af98  cmovz   rax, rcx
0x18000af9c  mov     cs:?g_HookThreadMap@@3V?$CPbList@UCHookThreadItem@@@@A, rax; CPbList<CHookThreadItem> g_HookThreadMap
0x18000afa3  mov     rax, cs:qword_180018A50
0x18000afaa  cmp     rax, rdi
0x18000afad  cmovz   rax, rdx
0x18000afb1  mov     cs:qword_180018A50, rax
0x18000afb8  cmp     [rbp+var_2C], 0
0x18000afbc  jz      short loc_18000B026
0x18000afbe  cmp     dword ptr [r12+3Ch], 0
0x18000afc4  jnz     short loc_18000B026
0x18000afc6  mov     rcx, [rsi+40h]
0x18000afca  mov     rax, [rsi+48h]
0x18000afce  test    rcx, rcx
0x18000afd1  jz      short loc_18000AFD7
0x18000afd3  mov     [rcx+48h], rax
0x18000afd7  test    rax, rax
0x18000afda  jz      short loc_18000AFE0
0x18000afdc  mov     [rax+40h], rcx
0x18000afe0  cmp     [r15+10h], rsi
0x18000afe4  jnz     short loc_18000AFEA
0x18000afe6  mov     [r15+10h], rax
0x18000afea  cmp     [r15+18h], rsi
0x18000afee  jnz     short loc_18000AFF4
0x18000aff0  mov     [r15+18h], rcx
0x18000aff4  mov     qword ptr [rbp+DueTime], rsi
0x18000aff8  mov     [rbp+lpParameter], rsi
0x18000affc  lea     rax, [rsi+20h]
0x18000b000  mov     rcx, [rax+10h]; Block
0x18000b004  test    rcx, rcx
0x18000b007  jz      short loc_18000B018
0x18000b009  cmp     rcx, rax
0x18000b00c  jz      short loc_18000B018
0x18000b00e  mov     edx, 8
0x18000b013  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b018  mov     edx, 50h ; 'P'
0x18000b01d  mov     rcx, rsi; Block
0x18000b020  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b025  nop
0x18000b026  test    ebx, ebx
0x18000b028  jnz     short loc_18000B037
0x18000b02a  mov     rcx, cs:?g_hMutexHook@@3PEAXEA; hMutex
0x18000b031  call    cs:__imp_ReleaseMutex
0x18000b037  cmp     [rbp+var_28], 0
0x18000b03b  jz      short loc_18000B077
0x18000b03d  mov     rcx, rdi; struct CHookThreadItem *
0x18000b040  call    ?TerminateHookThread@CPimcManager@@SAXPEAUCHookThreadItem@@@Z; CPimcManager::TerminateHookThread(CHookThreadItem *)
0x18000b045  mov     qword ptr [rbp+DueTime], rdi
0x18000b049  test    rdi, rdi
0x18000b04c  jz      short loc_18000B077
0x18000b04e  lea     rax, [rdi+18h]
0x18000b052  mov     rcx, [rax+10h]; Block
0x18000b056  test    rcx, rcx
0x18000b059  jz      short loc_18000B06A
0x18000b05b  cmp     rcx, rax
0x18000b05e  jz      short loc_18000B06A
0x18000b060  mov     edx, 8
0x18000b065  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b06a  mov     edx, 68h ; 'h'
0x18000b06f  mov     rcx, rdi; Block
0x18000b072  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b077  mov     eax, r14d
0x18000b07a  lea     r11, [rsp+60h+var_s0]
0x18000b07f  mov     rbx, [r11+30h]
0x18000b083  mov     rsi, [r11+38h]
0x18000b087  mov     rdi, [r11+40h]
0x18000b08b  mov     rsp, r11
0x18000b08e  pop     r15
0x18000b090  pop     r14
0x18000b092  pop     r13
0x18000b094  pop     r12
0x18000b096  pop     rbp
0x18000b097  retn
```
