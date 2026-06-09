# CSerialWorkQueue::QueueWorkItem(std::function<void (void)>)

- ea: `0x180030290`
- end: `0x18003057d`
- name: `?QueueWorkItem@CSerialWorkQueue@@QEAAJV?$function@$$A6AXXZ@std@@@Z`
- size: `749`
- prototype: ``
- caller_count: `29`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800235b4`
- `0x1800236e4`
- `0x18003191c`
- `0x180032ff0`
- `0x180050e90`
- `0x180050f3c`
- `0x180052c6c`
- `0x180054d74`
- `0x180061f7c`
- `0x180069c60`
- `0x180079e44`
- `0x1800a94d0`
- `0x1800a9660`
- `0x1800bd134`
- `0x1800bebc0`
- `0x1800c6390`
- `0x1800c6920`
- `0x1800c730c`
- `0x1800c7ba4`
- `0x1800e42d0`
- `0x1800eed00`
- `0x1800f9530`
- `0x1800fe260`
- `0x18010cd10`
- `0x1801111c0`
- `0x180111520`
- `0x1801151d0`
- `0x18011a1e0`
- `0x180120710`

## callees

- `0x18002a04c`
- `0x180030290`
- `0x180030b5c`
- `0x1800cfd9c`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800303c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800303c0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800303d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800303d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800302e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003050c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800302e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003050c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030558`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800302c3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800302c3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800304a7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800304a7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180030304`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180030304`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1800302dd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1800302dd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180030322`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180030322`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800304be`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800304be`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSerialWorkQueue::QueueWorkItem(__int64 a1, __int64 *a2)
{
  signed int v4; // esi
  PTP_POOL Threadpool; // rax
  signed int v6; // eax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  __int64 *v8; // rax
  unsigned int v9; // edx
  __int64 *v10; // rdi
  __int64 (__fastcall ***v11)(_QWORD, _BYTE *); // rcx
  HANDLE ProcessHeap; // rax
  _DWORD *v13; // rax
  _DWORD *v14; // r15
  volatile signed __int32 *v15; // rsi
  __int64 v16; // rbp
  _BYTE *v17; // rdx
  struct _TP_WORK *ThreadpoolWork; // rbp
  __int64 *v19; // rcx
  __int64 v20; // rdx
  signed int LastError; // eax
  signed int v23; // eax
  signed int v24; // eax
  _BYTE v25[56]; // [rsp+20h] [rbp-78h] BYREF
  _BYTE *v26; // [rsp+58h] [rbp-40h]

  v4 = 0;
  if ( *(_BYTE *)(a1 + 80) )
    goto LABEL_32;
  if ( *(_QWORD *)a1 )
  {
LABEL_10:
    v8 = (__int64 *)operator new[](0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v8;
    if ( v8 )
    {
      *v8 = 0;
      v8[1] = 0;
      v8[2] = 0;
    }
    else
    {
      v10 = 0;
    }
    if ( v10 )
    {
      v26 = 0;
      v11 = (__int64 (__fastcall ***)(_QWORD, _BYTE *))a2[7];
      if ( v11 )
        v26 = (_BYTE *)(**v11)(v11, v25);
      v10[2] = a1;
      ProcessHeap = GetProcessHeap();
      v13 = HeapAlloc(ProcessHeap, 0, 0x50u);
      v14 = v13;
      if ( v13 )
      {
        *(_OWORD *)v13 = 0;
        v13[2] = 1;
        v13[3] = 1;
        *(_QWORD *)v13 = &std::_Ref_count_obj2<std::function<long (SystemEffectDescriptor *,SystemEffectChainDescriptor *)>>::`vftable';
        std::function<void (IAudioStreamInfo *)>::function<void (IAudioStreamInfo *)>(v13 + 4, v25);
      }
      else
      {
        v14 = 0;
      }
      *v10 = (__int64)(v14 + 4);
      v15 = (volatile signed __int32 *)v10[1];
      v10[1] = (__int64)v14;
      if ( v15 )
      {
        if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      v16 = *v10;
      v4 = -2147024882;
      if ( *v10 )
        v4 = 0;
      if ( v26 )
      {
        v17 = v25;
        LOBYTE(v17) = v26 != v25;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v26 + 32LL))(v26, v17);
      }
      if ( !v16 )
        goto LABEL_30;
      ThreadpoolWork = CreateThreadpoolWork(CSerialWorkQueue::WorkCallback, v10, (PTP_CALLBACK_ENVIRON)(a1 + 8));
      if ( ThreadpoolWork )
      {
        v4 = 0;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( v4 < 0 )
          goto LABEL_30;
      }
      v10 = 0;
      SubmitThreadpoolWork(ThreadpoolWork);
    }
    else
    {
      v4 = -2147024882;
    }
LABEL_30:
    if ( v10 )
      _WorkTask::`scalar deleting destructor'((_WorkTask *)v10, v9);
    goto LABEL_32;
  }
  Threadpool = CreateThreadpool(0);
  *(_QWORD *)a1 = Threadpool;
  if ( Threadpool )
    goto LABEL_43;
  v23 = GetLastError();
  v4 = v23;
  if ( v23 > 0 )
    v4 = (unsigned __int16)v23 | 0x80070000;
  if ( v4 >= 0 )
  {
LABEL_43:
    if ( SetThreadpoolThreadMinimum(*(PTP_POOL *)a1, 1u) )
      goto LABEL_51;
    v6 = GetLastError();
    v4 = v6;
    if ( v6 > 0 )
      v4 = (unsigned __int16)v6 | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_51:
      ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
      *(_QWORD *)(a1 + 168) = ThreadpoolCleanupGroup;
      if ( ThreadpoolCleanupGroup )
        goto LABEL_9;
      v24 = GetLastError();
      v4 = v24;
      if ( v24 > 0 )
        v4 = (unsigned __int16)v24 | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_9:
        SetThreadpoolThreadMaximum(*(PTP_POOL *)a1, 1u);
        *(_QWORD *)(a1 + 16) = *(_QWORD *)a1;
        *(_QWORD *)(a1 + 24) = *(_QWORD *)(a1 + 168);
        *(_QWORD *)(a1 + 32) = 0;
        goto LABEL_10;
      }
    }
  }
LABEL_32:
  v19 = (__int64 *)a2[7];
  if ( v19 )
  {
    v20 = *v19;
    LOBYTE(v20) = v19 != a2;
    (*(void (__fastcall **)(__int64 *, __int64))(*v19 + 32))(v19, v20);
    a2[7] = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180030290  mov     [rsp+arg_8], rdx
0x180030295  push    rbx
0x180030296  push    rbp
0x180030297  push    rsi
0x180030298  push    rdi
0x180030299  push    r12
0x18003029b  push    r14
0x18003029d  push    r15
0x18003029f  sub     rsp, 60h
0x1800302a3  mov     rbx, rdx
0x1800302a6  mov     r14, rcx
0x1800302a9  xor     r12d, r12d
0x1800302ac  mov     esi, r12d
0x1800302af  movzx   eax, byte ptr [rcx+50h]
0x1800302b3  nop
0x1800302b4  test    al, al
0x1800302b6  jnz     loc_1800304D4
0x1800302bc  cmp     [rcx], rsi
0x1800302bf  jnz     short loc_18003033E
0x1800302c1  xor     ecx, ecx; reserved
0x1800302c3  call    cs:__imp_CreateThreadpool
0x1800302c9  mov     [r14], rax
0x1800302cc  test    rax, rax
0x1800302cf  jz      loc_180030541
0x1800302d5  mov     edx, 1; cthrdMic
0x1800302da  mov     rcx, [r14]; ptpp
0x1800302dd  call    cs:__imp_SetThreadpoolThreadMinimum
0x1800302e3  test    eax, eax
0x1800302e5  jnz     short loc_180030304
0x1800302e7  call    cs:__imp_GetLastError
0x1800302ed  mov     esi, eax
0x1800302ef  test    eax, eax
0x1800302f1  jle     short loc_1800302FC
0x1800302f3  movzx   esi, ax
0x1800302f6  or      esi, 80070000h
0x1800302fc  test    esi, esi
0x1800302fe  js      loc_1800304D4
0x180030304  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18003030a  mov     [r14+0A8h], rax
0x180030311  test    rax, rax
0x180030314  jz      loc_180030558
0x18003031a  mov     edx, 1; cthrdMost
0x18003031f  mov     rcx, [r14]; ptpp
0x180030322  call    cs:__imp_SetThreadpoolThreadMaximum
0x180030328  mov     rax, [r14]
0x18003032b  mov     [r14+10h], rax
0x18003032f  mov     rax, [r14+0A8h]
0x180030336  mov     [r14+18h], rax
0x18003033a  mov     [r14+20h], r12
0x18003033e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180030345  mov     ecx, 18h; unsigned __int64
0x18003034a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003034f  mov     rdi, rax
0x180030352  mov     [rsp+98h+arg_0], rax
0x18003035a  test    rax, rax
0x18003035d  jz      loc_180030504
0x180030363  mov     [rax], r12
0x180030366  mov     [rax+8], r12
0x18003036a  mov     [rax+10h], r12
0x18003036e  mov     [rsp+98h+arg_0], rdi
0x180030376  test    rdi, rdi
0x180030379  jz      loc_1800304C6
0x18003037f  lea     rax, [rsp+98h+var_78]
0x180030384  mov     [rsp+98h+arg_10], rax
0x18003038c  mov     [rsp+98h+var_40], r12
0x180030391  mov     rcx, [rbx+38h]
0x180030395  test    rcx, rcx
0x180030398  jz      short loc_1800303AF
0x18003039a  mov     rax, [rcx]
0x18003039d  lea     rdx, [rsp+98h+var_78]
0x1800303a2  mov     rax, [rax]
0x1800303a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303aa  mov     [rsp+98h+var_40], rax
0x1800303af  lea     rax, [rsp+98h+var_78]
0x1800303b4  mov     [rsp+98h+arg_10], rax
0x1800303bc  mov     [rdi+10h], r14
0x1800303c0  call    cs:__imp_GetProcessHeap
0x1800303c6  mov     rcx, rax; hHeap
0x1800303c9  xor     edx, edx; dwFlags
0x1800303cb  mov     r8d, 50h ; 'P'; dwBytes
0x1800303d1  call    cs:__imp_HeapAlloc
0x1800303d7  mov     r15, rax
0x1800303da  mov     [rsp+98h+arg_18], rax
0x1800303e2  test    rax, rax
0x1800303e5  jz      loc_180030527
0x1800303eb  xorps   xmm0, xmm0
0x1800303ee  movups  xmmword ptr [rax], xmm0
0x1800303f1  mov     dword ptr [rax+8], 1
0x1800303f8  mov     dword ptr [rax+0Ch], 1
0x1800303ff  lea     rax, ??_7?$_Ref_count_obj2@V?$function@$$A6AJPEAVSystemEffectDescriptor@@PEAVSystemEffectChainDescriptor@@@Z@std@@@std@@6B@; const std::_Ref_count_obj2<std::function<long (SystemEffectDescriptor *,SystemEffectChainDescriptor *)>>::`vftable'
0x180030406  mov     [r15], rax
0x180030409  lea     rcx, [r15+10h]
0x18003040d  lea     rdx, [rsp+98h+var_78]
0x180030412  call    ??0?$function@$$A6AXPEAUIAudioStreamInfo@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (IAudioStreamInfo *)>::function<void (IAudioStreamInfo *)>(std::function<void (IAudioStreamInfo *)> const &)
0x180030417  nop
0x180030418  lea     rax, [r15+10h]
0x18003041c  mov     [rdi], rax
0x18003041f  mov     rsi, [rdi+8]
0x180030423  mov     [rdi+8], r15
0x180030427  test    rsi, rsi
0x18003042a  jz      short loc_180030464
0x18003042c  mov     ebp, 0FFFFFFFFh
0x180030431  mov     eax, ebp
0x180030433  lock xadd [rsi+8], eax
0x180030438  cmp     eax, 1
0x18003043b  jnz     short loc_180030464
0x18003043d  mov     rax, [rsi]
0x180030440  mov     rcx, rsi
0x180030443  mov     rax, [rax]
0x180030446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003044b  lock xadd [rsi+0Ch], ebp
0x180030450  cmp     ebp, 1
0x180030453  jnz     short loc_180030464
0x180030455  mov     rax, [rsi]
0x180030458  mov     rcx, rsi
0x18003045b  mov     rax, [rax+8]
0x18003045f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030464  mov     rbp, [rdi]
0x180030467  mov     esi, 8007000Eh
0x18003046c  test    rbp, rbp
0x18003046f  cmovnz  esi, r12d
0x180030473  mov     rcx, [rsp+98h+var_40]
0x180030478  test    rcx, rcx
0x18003047b  jz      short loc_180030494
0x18003047d  mov     rax, [rcx]
0x180030480  lea     rdx, [rsp+98h+var_78]
0x180030485  cmp     rcx, rdx
0x180030488  setnz   dl
0x18003048b  mov     rax, [rax+20h]
0x18003048f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030494  test    rbp, rbp
0x180030497  jz      short loc_1800304CB
0x180030499  lea     r8, [r14+8]; pcbe
0x18003049d  mov     rdx, rdi; pv
0x1800304a0  lea     rcx, ?WorkCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800304a7  call    cs:__imp_CreateThreadpoolWork
0x1800304ad  mov     rbp, rax
0x1800304b0  test    rax, rax
0x1800304b3  jz      short loc_18003050C
0x1800304b5  mov     esi, r12d
0x1800304b8  mov     rdi, r12
0x1800304bb  mov     rcx, rbp; pwk
0x1800304be  call    cs:__imp_SubmitThreadpoolWork
0x1800304c4  jmp     short loc_1800304CB
0x1800304c6  mov     esi, 8007000Eh
0x1800304cb  test    rdi, rdi
0x1800304ce  jnz     loc_18003056F
0x1800304d4  mov     rcx, [rbx+38h]
0x1800304d8  test    rcx, rcx
0x1800304db  jz      short loc_1800304F3
0x1800304dd  mov     rdx, [rcx]
0x1800304e0  mov     rax, [rdx+20h]
0x1800304e4  cmp     rcx, rbx
0x1800304e7  setnz   dl
0x1800304ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304ef  mov     [rbx+38h], r12
0x1800304f3  mov     eax, esi
0x1800304f5  add     rsp, 60h
0x1800304f9  pop     r15
0x1800304fb  pop     r14
0x1800304fd  pop     r12
0x1800304ff  pop     rdi
0x180030500  pop     rsi
0x180030501  pop     rbp
0x180030502  pop     rbx
0x180030503  retn
0x180030504  mov     rdi, r12
0x180030507  jmp     loc_18003036E
0x18003050c  call    cs:__imp_GetLastError
0x180030512  mov     esi, eax
0x180030514  test    eax, eax
0x180030516  jle     short loc_180030521
0x180030518  movzx   esi, ax
0x18003051b  or      esi, 80070000h
0x180030521  test    esi, esi
0x180030523  jns     short loc_1800304B8
0x180030525  jmp     short loc_1800304CB
0x180030527  mov     r15, r12
0x18003052a  jmp     loc_180030418
0x18003052f  test    esi, esi
0x180030531  js      short loc_1800304D4
0x180030533  jmp     loc_1800302D5
0x180030538  test    esi, esi
0x18003053a  js      short loc_1800304D4
0x18003053c  jmp     loc_18003031A
0x180030541  call    cs:__imp_GetLastError
0x180030547  mov     esi, eax
0x180030549  test    eax, eax
0x18003054b  jle     short loc_18003052F
0x18003054d  movzx   esi, ax
0x180030550  or      esi, 80070000h
0x180030556  jmp     short loc_18003052F
0x180030558  call    cs:__imp_GetLastError
0x18003055e  mov     esi, eax
0x180030560  test    eax, eax
0x180030562  jle     short loc_180030538
0x180030564  movzx   esi, ax
0x180030567  or      esi, 80070000h
0x18003056d  jmp     short loc_180030538
0x18003056f  mov     rcx, rdi; this
0x180030572  call    ??_G_WorkTask@@QEAAPEAXI@Z; _WorkTask::`scalar deleting destructor'(uint)
0x180030577  jmp     loc_1800304D4
```
