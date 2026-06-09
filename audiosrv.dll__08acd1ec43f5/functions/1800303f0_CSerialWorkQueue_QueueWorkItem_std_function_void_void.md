# CSerialWorkQueue::QueueWorkItem(std::function<void (void)>)

- ea: `0x1800303f0`
- end: `0x1800306dd`
- name: `?QueueWorkItem@CSerialWorkQueue@@QEAAJV?$function@$$A6AXXZ@std@@@Z`
- size: `749`
- prototype: ``
- caller_count: `29`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180023704`
- `0x180023834`
- `0x180031a7c`
- `0x180033150`
- `0x180050a00`
- `0x180050aac`
- `0x1800527dc`
- `0x1800548e4`
- `0x180061aec`
- `0x1800697d0`
- `0x180079944`
- `0x1800a8220`
- `0x1800a83b0`
- `0x1800bb5e4`
- `0x1800bd070`
- `0x1800c4500`
- `0x1800c4b30`
- `0x1800c551c`
- `0x1800c5db4`
- `0x1800e3b50`
- `0x1800ee510`
- `0x1800f97c0`
- `0x1800fe4f0`
- `0x18010cfc0`
- `0x180111470`
- `0x1801117d0`
- `0x180115450`
- `0x18011a430`
- `0x180120960`

## callees

- `0x18002a1ac`
- `0x1800303f0`
- `0x180030cbc`
- `0x1800cddac`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030520`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030520`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030531`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003066c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003066c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306b8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180030423`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180030423`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180030607`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180030607`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180030464`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180030464`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18003043d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18003043d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180030482`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180030482`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003061e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003061e`

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
0x1800303f0  mov     [rsp+arg_8], rdx
0x1800303f5  push    rbx
0x1800303f6  push    rbp
0x1800303f7  push    rsi
0x1800303f8  push    rdi
0x1800303f9  push    r12
0x1800303fb  push    r14
0x1800303fd  push    r15
0x1800303ff  sub     rsp, 60h
0x180030403  mov     rbx, rdx
0x180030406  mov     r14, rcx
0x180030409  xor     r12d, r12d
0x18003040c  mov     esi, r12d
0x18003040f  movzx   eax, byte ptr [rcx+50h]
0x180030413  nop
0x180030414  test    al, al
0x180030416  jnz     loc_180030634
0x18003041c  cmp     [rcx], rsi
0x18003041f  jnz     short loc_18003049E
0x180030421  xor     ecx, ecx; reserved
0x180030423  call    cs:__imp_CreateThreadpool
0x180030429  mov     [r14], rax
0x18003042c  test    rax, rax
0x18003042f  jz      loc_1800306A1
0x180030435  mov     edx, 1; cthrdMic
0x18003043a  mov     rcx, [r14]; ptpp
0x18003043d  call    cs:__imp_SetThreadpoolThreadMinimum
0x180030443  test    eax, eax
0x180030445  jnz     short loc_180030464
0x180030447  call    cs:__imp_GetLastError
0x18003044d  mov     esi, eax
0x18003044f  test    eax, eax
0x180030451  jle     short loc_18003045C
0x180030453  movzx   esi, ax
0x180030456  or      esi, 80070000h
0x18003045c  test    esi, esi
0x18003045e  js      loc_180030634
0x180030464  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18003046a  mov     [r14+0A8h], rax
0x180030471  test    rax, rax
0x180030474  jz      loc_1800306B8
0x18003047a  mov     edx, 1; cthrdMost
0x18003047f  mov     rcx, [r14]; ptpp
0x180030482  call    cs:__imp_SetThreadpoolThreadMaximum
0x180030488  mov     rax, [r14]
0x18003048b  mov     [r14+10h], rax
0x18003048f  mov     rax, [r14+0A8h]
0x180030496  mov     [r14+18h], rax
0x18003049a  mov     [r14+20h], r12
0x18003049e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800304a5  mov     ecx, 18h; unsigned __int64
0x1800304aa  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800304af  mov     rdi, rax
0x1800304b2  mov     [rsp+98h+arg_0], rax
0x1800304ba  test    rax, rax
0x1800304bd  jz      loc_180030664
0x1800304c3  mov     [rax], r12
0x1800304c6  mov     [rax+8], r12
0x1800304ca  mov     [rax+10h], r12
0x1800304ce  mov     [rsp+98h+arg_0], rdi
0x1800304d6  test    rdi, rdi
0x1800304d9  jz      loc_180030626
0x1800304df  lea     rax, [rsp+98h+var_78]
0x1800304e4  mov     [rsp+98h+arg_10], rax
0x1800304ec  mov     [rsp+98h+var_40], r12
0x1800304f1  mov     rcx, [rbx+38h]
0x1800304f5  test    rcx, rcx
0x1800304f8  jz      short loc_18003050F
0x1800304fa  mov     rax, [rcx]
0x1800304fd  lea     rdx, [rsp+98h+var_78]
0x180030502  mov     rax, [rax]
0x180030505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003050a  mov     [rsp+98h+var_40], rax
0x18003050f  lea     rax, [rsp+98h+var_78]
0x180030514  mov     [rsp+98h+arg_10], rax
0x18003051c  mov     [rdi+10h], r14
0x180030520  call    cs:__imp_GetProcessHeap
0x180030526  mov     rcx, rax; hHeap
0x180030529  xor     edx, edx; dwFlags
0x18003052b  mov     r8d, 50h ; 'P'; dwBytes
0x180030531  call    cs:__imp_HeapAlloc
0x180030537  mov     r15, rax
0x18003053a  mov     [rsp+98h+arg_18], rax
0x180030542  test    rax, rax
0x180030545  jz      loc_180030687
0x18003054b  xorps   xmm0, xmm0
0x18003054e  movups  xmmword ptr [rax], xmm0
0x180030551  mov     dword ptr [rax+8], 1
0x180030558  mov     dword ptr [rax+0Ch], 1
0x18003055f  lea     rax, ??_7?$_Ref_count_obj2@V?$function@$$A6AJPEAVSystemEffectDescriptor@@PEAVSystemEffectChainDescriptor@@@Z@std@@@std@@6B@; const std::_Ref_count_obj2<std::function<long (SystemEffectDescriptor *,SystemEffectChainDescriptor *)>>::`vftable'
0x180030566  mov     [r15], rax
0x180030569  lea     rcx, [r15+10h]
0x18003056d  lea     rdx, [rsp+98h+var_78]
0x180030572  call    ??0?$function@$$A6AXPEAUIAudioStreamInfo@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (IAudioStreamInfo *)>::function<void (IAudioStreamInfo *)>(std::function<void (IAudioStreamInfo *)> const &)
0x180030577  nop
0x180030578  lea     rax, [r15+10h]
0x18003057c  mov     [rdi], rax
0x18003057f  mov     rsi, [rdi+8]
0x180030583  mov     [rdi+8], r15
0x180030587  test    rsi, rsi
0x18003058a  jz      short loc_1800305C4
0x18003058c  mov     ebp, 0FFFFFFFFh
0x180030591  mov     eax, ebp
0x180030593  lock xadd [rsi+8], eax
0x180030598  cmp     eax, 1
0x18003059b  jnz     short loc_1800305C4
0x18003059d  mov     rax, [rsi]
0x1800305a0  mov     rcx, rsi
0x1800305a3  mov     rax, [rax]
0x1800305a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305ab  lock xadd [rsi+0Ch], ebp
0x1800305b0  cmp     ebp, 1
0x1800305b3  jnz     short loc_1800305C4
0x1800305b5  mov     rax, [rsi]
0x1800305b8  mov     rcx, rsi
0x1800305bb  mov     rax, [rax+8]
0x1800305bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305c4  mov     rbp, [rdi]
0x1800305c7  mov     esi, 8007000Eh
0x1800305cc  test    rbp, rbp
0x1800305cf  cmovnz  esi, r12d
0x1800305d3  mov     rcx, [rsp+98h+var_40]
0x1800305d8  test    rcx, rcx
0x1800305db  jz      short loc_1800305F4
0x1800305dd  mov     rax, [rcx]
0x1800305e0  lea     rdx, [rsp+98h+var_78]
0x1800305e5  cmp     rcx, rdx
0x1800305e8  setnz   dl
0x1800305eb  mov     rax, [rax+20h]
0x1800305ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305f4  test    rbp, rbp
0x1800305f7  jz      short loc_18003062B
0x1800305f9  lea     r8, [r14+8]; pcbe
0x1800305fd  mov     rdx, rdi; pv
0x180030600  lea     rcx, ?WorkCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180030607  call    cs:__imp_CreateThreadpoolWork
0x18003060d  mov     rbp, rax
0x180030610  test    rax, rax
0x180030613  jz      short loc_18003066C
0x180030615  mov     esi, r12d
0x180030618  mov     rdi, r12
0x18003061b  mov     rcx, rbp; pwk
0x18003061e  call    cs:__imp_SubmitThreadpoolWork
0x180030624  jmp     short loc_18003062B
0x180030626  mov     esi, 8007000Eh
0x18003062b  test    rdi, rdi
0x18003062e  jnz     loc_1800306CF
0x180030634  mov     rcx, [rbx+38h]
0x180030638  test    rcx, rcx
0x18003063b  jz      short loc_180030653
0x18003063d  mov     rdx, [rcx]
0x180030640  mov     rax, [rdx+20h]
0x180030644  cmp     rcx, rbx
0x180030647  setnz   dl
0x18003064a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003064f  mov     [rbx+38h], r12
0x180030653  mov     eax, esi
0x180030655  add     rsp, 60h
0x180030659  pop     r15
0x18003065b  pop     r14
0x18003065d  pop     r12
0x18003065f  pop     rdi
0x180030660  pop     rsi
0x180030661  pop     rbp
0x180030662  pop     rbx
0x180030663  retn
0x180030664  mov     rdi, r12
0x180030667  jmp     loc_1800304CE
0x18003066c  call    cs:__imp_GetLastError
0x180030672  mov     esi, eax
0x180030674  test    eax, eax
0x180030676  jle     short loc_180030681
0x180030678  movzx   esi, ax
0x18003067b  or      esi, 80070000h
0x180030681  test    esi, esi
0x180030683  jns     short loc_180030618
0x180030685  jmp     short loc_18003062B
0x180030687  mov     r15, r12
0x18003068a  jmp     loc_180030578
0x18003068f  test    esi, esi
0x180030691  js      short loc_180030634
0x180030693  jmp     loc_180030435
0x180030698  test    esi, esi
0x18003069a  js      short loc_180030634
0x18003069c  jmp     loc_18003047A
0x1800306a1  call    cs:__imp_GetLastError
0x1800306a7  mov     esi, eax
0x1800306a9  test    eax, eax
0x1800306ab  jle     short loc_18003068F
0x1800306ad  movzx   esi, ax
0x1800306b0  or      esi, 80070000h
0x1800306b6  jmp     short loc_18003068F
0x1800306b8  call    cs:__imp_GetLastError
0x1800306be  mov     esi, eax
0x1800306c0  test    eax, eax
0x1800306c2  jle     short loc_180030698
0x1800306c4  movzx   esi, ax
0x1800306c7  or      esi, 80070000h
0x1800306cd  jmp     short loc_180030698
0x1800306cf  mov     rcx, rdi; this
0x1800306d2  call    ??_G_WorkTask@@QEAAPEAXI@Z; _WorkTask::`scalar deleting destructor'(uint)
0x1800306d7  jmp     loc_180030634
```
