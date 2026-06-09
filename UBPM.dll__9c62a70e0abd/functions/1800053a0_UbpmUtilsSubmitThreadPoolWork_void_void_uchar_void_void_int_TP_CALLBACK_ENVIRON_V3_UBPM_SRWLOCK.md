# UbpmUtilsSubmitThreadPoolWork(void (*)(void *,uchar,void *),void *,int,_TP_CALLBACK_ENVIRON_V3 *,_UBPM_SRWLOCK *)

- ea: `0x1800053a0`
- end: `0x18000560d`
- name: `?UbpmUtilsSubmitThreadPoolWork@@YAKP6AXPEAXE0@Z0HPEAU_TP_CALLBACK_ENVIRON_V3@@PEAU_UBPM_SRWLOCK@@@Z`
- size: `621`
- prototype: `unsigned int(void (*)(void *, unsigned __int8, void *), void *, int, struct _TP_CALLBACK_ENVIRON_V3 *, struct _UBPM_SRWLOCK *)`
- caller_count: `15`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001f40`
- `0x180003da0`
- `0x1800044f8`
- `0x180004768`
- `0x180005320`
- `0x1800060d0`
- `0x180011a90`
- `0x180015b90`
- `0x18001da20`
- `0x18002c05c`
- `0x18002c7d0`
- `0x180030b14`
- `0x1800367b0`
- `0x1800367e0`
- `0x180038814`

## callees

- `0x1800053a0`
- `0x1800351ec`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800054b5`
- `ntdll!RtlFreeHeap` at `0x1800054b5`
- `ntdll!RtlTryAcquireSRWLockShared` at `0x18000541d`
- `ntdll!RtlTryAcquireSRWLockShared` at `0x18000541d`
- `ntdll!RtlAllocateHeap` at `0x1800053d0`
- `ntdll!RtlAllocateHeap` at `0x1800053d0`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800055fc`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800055fc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180005453`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180005453`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180005487`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180005487`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005518`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005518`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000550c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000550c`

## pseudocode

```c
__int64 __fastcall UbpmUtilsSubmitThreadPoolWork(
        void (*a1)(void *, unsigned __int8, void *),
        void *a2,
        char a3,
        struct _TP_CALLBACK_ENVIRON_V3 *a4,
        struct _UBPM_SRWLOCK *a5)
{
  _DWORD *Heap; // rbx
  struct _TP_CALLBACK_ENVIRON_V3 *v10; // rbp
  char v11; // r14
  struct _UBPM_SRWLOCK *v12; // r15
  struct _TP_WORK *ThreadpoolWork; // rcx
  char v14; // si
  DWORD LastError; // edi
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  DWORD v19; // ebx

  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x30u);
  if ( Heap )
  {
    v10 = &g_CallbackEnv;
    v11 = 0;
    v12 = (struct _UBPM_SRWLOCK *)&g_TpSubmitLock;
    if ( a4 )
    {
      v12 = a5;
      v10 = a4;
    }
    if ( v12 )
    {
      if ( !(unsigned __int8)RtlTryAcquireSRWLockShared(v12) )
      {
        LastError = 1235;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, 1235);
LABEL_14:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        return LastError;
      }
      v11 = 1;
    }
    if ( a4 || g_pThreadpool )
    {
      ThreadpoolWork = CreateThreadpoolWork(UbpmUtilsWorkCallback, Heap, v10);
      if ( ThreadpoolWork )
      {
        v14 = *((_BYTE *)Heap + 24) ^ a3;
        *Heap = 1886667349;
        *((_BYTE *)Heap + 24) ^= v14 & 1;
        *((_QWORD *)Heap + 1) = a2;
        *((_QWORD *)Heap + 2) = a1;
        Heap = 0;
        SubmitThreadpoolWork(ThreadpoolWork);
        LastError = 0;
        goto LABEL_11;
      }
      LastError = GetLastError();
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      v18 = 22;
    }
    else
    {
      LastError = 1115;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      v18 = 21;
    }
    WPP_SF_d(v17[2], v18, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, LastError);
LABEL_11:
    if ( v11 )
      RtlReleaseSRWLockShared(v12);
    if ( !Heap )
      return LastError;
    goto LABEL_14;
  }
  SetLastError(8u);
  v19 = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, v19);
  return v19;
}

```

## disassembly

```asm
0x1800053a0  push    rbx
0x1800053a2  push    rsi
0x1800053a3  push    rdi
0x1800053a4  push    r12
0x1800053a6  push    r13
0x1800053a8  sub     rsp, 20h
0x1800053ac  mov     r13, rcx
0x1800053af  mov     esi, r8d
0x1800053b2  mov     rcx, gs:60h
0x1800053bb  mov     r12, rdx
0x1800053be  mov     edx, 8; Flags
0x1800053c3  mov     r8d, 30h ; '0'; Size
0x1800053c9  mov     rdi, r9
0x1800053cc  mov     rcx, [rcx+30h]; HeapHandle
0x1800053d0  call    cs:__imp_RtlAllocateHeap
0x1800053d7  nop     dword ptr [rax+rax+00h]
0x1800053dc  mov     rbx, rax
0x1800053df  test    rax, rax
0x1800053e2  jz      loc_180005507
0x1800053e8  mov     [rsp+48h+arg_0], rbp
0x1800053ed  lea     rbp, ?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv
0x1800053f4  mov     [rsp+48h+arg_8], r14
0x1800053f9  xor     r14b, r14b
0x1800053fc  test    rdi, rdi
0x1800053ff  mov     [rsp+48h+arg_10], r15
0x180005404  lea     r15, ?g_TpSubmitLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TpSubmitLock
0x18000540b  cmovnz  r15, [rsp+48h+arg_20]
0x180005411  cmovnz  rbp, rdi
0x180005415  test    r15, r15
0x180005418  jz      short loc_180005434
0x18000541a  mov     rcx, r15
0x18000541d  call    cs:__imp_RtlTryAcquireSRWLockShared
0x180005424  nop     dword ptr [rax+rax+00h]
0x180005429  test    al, al
0x18000542b  jz      loc_180005568
0x180005431  mov     r14b, 1
0x180005434  test    rdi, rdi
0x180005437  jnz     short loc_180005446
0x180005439  cmp     cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA, rdi; _TP_POOL * g_pThreadpool
0x180005440  jz      loc_1800054DF
0x180005446  mov     r8, rbp; pcbe
0x180005449  lea     rcx, ?UbpmUtilsWorkCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180005450  mov     rdx, rbx; pv
0x180005453  call    cs:__imp_CreateThreadpoolWork
0x18000545a  nop     dword ptr [rax+rax+00h]
0x18000545f  mov     rcx, rax; pwk
0x180005462  test    rax, rax
0x180005465  jz      loc_1800055C8
0x18000546b  xor     sil, [rbx+18h]
0x18000546f  mov     dword ptr [rbx], 70744255h
0x180005475  and     sil, 1
0x180005479  xor     [rbx+18h], sil
0x18000547d  mov     [rbx+8], r12
0x180005481  mov     [rbx+10h], r13
0x180005485  xor     ebx, ebx
0x180005487  call    cs:__imp_SubmitThreadpoolWork
0x18000548e  nop     dword ptr [rax+rax+00h]
0x180005493  xor     edi, edi
0x180005495  test    r14b, r14b
0x180005498  jnz     loc_1800055F9
0x18000549e  test    rbx, rbx
0x1800054a1  jz      short loc_1800054C1
0x1800054a3  mov     rcx, gs:60h
0x1800054ac  mov     r8, rbx; P
0x1800054af  xor     edx, edx; Flags
0x1800054b1  mov     rcx, [rcx+30h]; HeapHandle
0x1800054b5  call    cs:__imp_RtlFreeHeap
0x1800054bc  nop     dword ptr [rax+rax+00h]
0x1800054c1  mov     r14, [rsp+48h+arg_8]
0x1800054c6  mov     eax, edi
0x1800054c8  mov     rbp, [rsp+48h+arg_0]
0x1800054cd  mov     r15, [rsp+48h+arg_10]
0x1800054d2  add     rsp, 20h
0x1800054d6  pop     r13
0x1800054d8  pop     r12
0x1800054da  pop     rdi
0x1800054db  pop     rsi
0x1800054dc  pop     rbx
0x1800054dd  retn
0x1800054df  mov     edi, 45Bh
0x1800054e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054eb  lea     rax, WPP_GLOBAL_Control
0x1800054f2  cmp     rcx, rax
0x1800054f5  jz      short loc_180005495
0x1800054f7  test    byte ptr [rcx+1Ch], 1
0x1800054fb  jz      short loc_180005495
0x1800054fd  mov     edx, 15h
0x180005502  jmp     loc_1800055B0
0x180005507  mov     ecx, 8; dwErrCode
0x18000550c  call    cs:__imp_SetLastError
0x180005513  nop     dword ptr [rax+rax+00h]
0x180005518  call    cs:__imp_GetLastError
0x18000551f  nop     dword ptr [rax+rax+00h]
0x180005524  mov     ebx, eax
0x180005526  mov     rcx, cs:WPP_GLOBAL_Control
0x18000552d  lea     rax, WPP_GLOBAL_Control
0x180005534  cmp     rcx, rax
0x180005537  jnz     short loc_180005548
0x180005539  mov     eax, ebx
0x18000553b  add     rsp, 20h
0x18000553f  pop     r13
0x180005541  pop     r12
0x180005543  pop     rdi
0x180005544  pop     rsi
0x180005545  pop     rbx
0x180005546  retn
0x180005548  test    byte ptr [rcx+1Ch], 1
0x18000554c  jz      short loc_180005539
0x18000554e  mov     rcx, [rcx+10h]
0x180005552  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x180005559  mov     edx, 13h
0x18000555e  mov     r9d, ebx
0x180005561  call    WPP_SF_d
0x180005566  jmp     short loc_180005539
0x180005568  mov     edi, 4D3h
0x18000556d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005574  lea     rax, WPP_GLOBAL_Control
0x18000557b  cmp     rcx, rax
0x18000557e  jz      loc_1800054A3
0x180005584  test    byte ptr [rcx+1Ch], 1
0x180005588  jz      loc_1800054A3
0x18000558e  mov     rcx, [rcx+10h]
0x180005592  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x180005599  mov     edx, 14h
0x18000559e  mov     r9d, edi
0x1800055a1  call    WPP_SF_d
0x1800055a6  jmp     loc_1800054A3
0x1800055ab  mov     edx, 16h
0x1800055b0  mov     rcx, [rcx+10h]
0x1800055b4  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x1800055bb  mov     r9d, edi
0x1800055be  call    WPP_SF_d
0x1800055c3  jmp     loc_180005495
0x1800055c8  call    cs:__imp_GetLastError
0x1800055cf  nop     dword ptr [rax+rax+00h]
0x1800055d4  mov     edi, eax
0x1800055d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055dd  lea     rax, WPP_GLOBAL_Control
0x1800055e4  cmp     rcx, rax
0x1800055e7  jz      loc_180005495
0x1800055ed  test    byte ptr [rcx+1Ch], 1
0x1800055f1  jz      loc_180005495
0x1800055f7  jmp     short loc_1800055AB
0x1800055f9  mov     rcx, r15
0x1800055fc  call    cs:__imp_RtlReleaseSRWLockShared
0x180005603  nop     dword ptr [rax+rax+00h]
0x180005608  jmp     loc_18000549E
```
