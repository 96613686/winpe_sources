# CSerialWorkQueue::QueueWorkItem(std::function<void (void)>)

- ea: `0x14000efc8`
- end: `0x14000f19c`
- name: `?QueueWorkItem@CSerialWorkQueue@@QEAAJV?$function@$$A6AXXZ@std@@@Z`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x140090000`

## callees

- `0x14000efc8`
- `0x14000f1a4`
- `0x14000f294`
- `0x14000f36c`
- `0x14000f3b8`
- `0x14005d104`
- `0x14005d148`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f15a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f15a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14000f17c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14000f17c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14000f148`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14000f148`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSerialWorkQueue::QueueWorkItem(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  signed int v4; // ebx
  _QWORD *v5; // rax
  _QWORD *v6; // rsi
  __int64 v7; // rcx
  __int64 (__fastcall ***v9)(_QWORD, _BYTE *); // rcx
  std::_Ref_count_base *v10; // rcx
  _BYTE *v11; // rdx
  struct _TP_WORK *ThreadpoolWork; // rdi
  signed int LastError; // eax
  _BYTE v14[56]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE *v15; // [rsp+58h] [rbp-10h]
  _DWORD *v16; // [rsp+B8h] [rbp+50h]

  v2 = a2;
  v4 = 0;
  if ( *(_BYTE *)(a1 + 80) )
    goto LABEL_9;
  v4 = CSerialWorkQueue::Initialize((PTP_POOL *)a1);
  if ( v4 < 0 )
    goto LABEL_9;
  v5 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v6 = v5;
  if ( v5 )
  {
    *v5 = 0;
    v5[1] = 0;
    v5[2] = 0;
  }
  else
  {
    v6 = 0;
  }
  if ( v6 )
  {
    v15 = 0;
    v9 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(v2 + 56);
    if ( v9 )
      v15 = (_BYTE *)(**v9)(v9, v14);
    v6[2] = a1;
    v16 = operator new(0x50u);
    *(_OWORD *)v16 = 0;
    v16[2] = 1;
    v16[3] = 1;
    *(_QWORD *)v16 = &std::_Ref_count_obj2<std::function<void (void)>>::`vftable';
    std::function<void (void)>::function<void (void)>(v16 + 4, v14);
    *v6 = v16 + 4;
    v10 = (std::_Ref_count_base *)v6[1];
    v6[1] = v16;
    if ( v10 )
      std::_Ref_count_base::_Decref(v10);
    v4 = *v6 == 0 ? 0x8007000E : 0;
    if ( v15 )
    {
      v11 = v14;
      LOBYTE(v11) = v15 != v14;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v15 + 32LL))(v15, v11);
    }
    if ( v4 < 0 )
      goto LABEL_7;
    ThreadpoolWork = CreateThreadpoolWork(CSerialWorkQueue::WorkCallback, v6, (PTP_CALLBACK_ENVIRON)(a1 + 8));
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
        goto LABEL_7;
    }
    v6 = 0;
    SubmitThreadpoolWork(ThreadpoolWork);
  }
  else
  {
    v4 = -2147024882;
  }
LABEL_7:
  if ( v6 )
    _WorkTask::`scalar deleting destructor'((_WorkTask *)v6, a2);
LABEL_9:
  v7 = *(_QWORD *)(v2 + 56);
  if ( v7 )
  {
    LOBYTE(a2) = v7 != v2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 32LL))(v7, a2);
    *(_QWORD *)(v2 + 56) = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000efc8  mov     [rsp-30h+arg_8], rdx
0x14000efcd  push    rbp
0x14000efce  push    rbx
0x14000efcf  push    rsi
0x14000efd0  push    rdi
0x14000efd1  push    r14
0x14000efd3  push    r15
0x14000efd5  mov     rbp, rsp
0x14000efd8  sub     rsp, 68h
0x14000efdc  mov     r14, rdx
0x14000efdf  mov     r15, rcx
0x14000efe2  xor     ebx, ebx
0x14000efe4  mov     al, [rcx+50h]
0x14000efe7  nop
0x14000efe8  test    al, al
0x14000efea  jnz     short loc_14000F046
0x14000efec  call    ?Initialize@CSerialWorkQueue@@AEAAJXZ; CSerialWorkQueue::Initialize(void)
0x14000eff1  mov     ebx, eax
0x14000eff3  test    eax, eax
0x14000eff5  js      short loc_14000F046
0x14000eff7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000effe  mov     ecx, 18h; unsigned __int64
0x14000f003  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000f008  mov     rsi, rax
0x14000f00b  mov     [rbp+arg_0], rax
0x14000f00f  test    rax, rax
0x14000f012  jz      loc_14000F187
0x14000f018  mov     qword ptr [rax], 0
0x14000f01f  mov     qword ptr [rax+8], 0
0x14000f027  mov     qword ptr [rax+10h], 0
0x14000f02f  mov     [rbp+arg_0], rsi
0x14000f033  test    rsi, rsi
0x14000f036  jnz     short loc_14000F078
0x14000f038  mov     ebx, 8007000Eh
0x14000f03d  test    rsi, rsi
0x14000f040  jnz     loc_14000F18E
0x14000f046  mov     rcx, [r14+38h]
0x14000f04a  test    rcx, rcx
0x14000f04d  jz      short loc_14000F069
0x14000f04f  mov     rax, [rcx]
0x14000f052  cmp     rcx, r14
0x14000f055  setnz   dl
0x14000f058  mov     rax, [rax+20h]
0x14000f05c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f061  mov     qword ptr [r14+38h], 0
0x14000f069  mov     eax, ebx
0x14000f06b  add     rsp, 68h
0x14000f06f  pop     r15
0x14000f071  pop     r14
0x14000f073  pop     rdi
0x14000f074  pop     rsi
0x14000f075  pop     rbx
0x14000f076  pop     rbp
0x14000f077  retn
0x14000f078  lea     rax, [rbp+var_48]
0x14000f07c  mov     [rbp+arg_10], rax
0x14000f080  mov     [rbp+var_10], 0
0x14000f088  mov     rcx, [r14+38h]
0x14000f08c  test    rcx, rcx
0x14000f08f  jz      short loc_14000F0A4
0x14000f091  mov     rax, [rcx]
0x14000f094  lea     rdx, [rbp+var_48]
0x14000f098  mov     rax, [rax]
0x14000f09b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f0a0  mov     [rbp+var_10], rax
0x14000f0a4  lea     rax, [rbp+var_48]
0x14000f0a8  mov     [rbp+arg_10], rax
0x14000f0ac  mov     [rsi+10h], r15
0x14000f0b0  mov     ecx, 50h ; 'P'; Size
0x14000f0b5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000f0ba  mov     rdi, rax
0x14000f0bd  mov     [rbp+arg_18], rax
0x14000f0c1  xorps   xmm0, xmm0
0x14000f0c4  movups  xmmword ptr [rax], xmm0
0x14000f0c7  mov     eax, 1
0x14000f0cc  mov     [rdi+8], eax
0x14000f0cf  mov     [rdi+0Ch], eax
0x14000f0d2  lea     rax, ??_7?$_Ref_count_obj2@V?$function@$$A6AXXZ@std@@@std@@6B@; const std::_Ref_count_obj2<std::function<void (void)>>::`vftable'
0x14000f0d9  mov     [rdi], rax
0x14000f0dc  lea     rbx, [rdi+10h]
0x14000f0e0  lea     rdx, [rbp+var_48]
0x14000f0e4  mov     rcx, rbx
0x14000f0e7  call    ??0?$function@$$A6AXXZ@std@@QEAA@AEBV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> const &)
0x14000f0ec  nop
0x14000f0ed  mov     [rsi], rbx
0x14000f0f0  mov     rcx, [rsi+8]; this
0x14000f0f4  mov     [rsi+8], rdi
0x14000f0f8  test    rcx, rcx
0x14000f0fb  jz      short loc_14000F102
0x14000f0fd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000f102  mov     rax, [rsi]
0x14000f105  neg     rax
0x14000f108  sbb     ecx, ecx
0x14000f10a  not     ecx
0x14000f10c  mov     ebx, 8007000Eh
0x14000f111  and     ebx, ecx
0x14000f113  mov     rcx, [rbp+var_10]
0x14000f117  test    rcx, rcx
0x14000f11a  jz      short loc_14000F132
0x14000f11c  mov     rax, [rcx]
0x14000f11f  lea     rdx, [rbp+var_48]
0x14000f123  cmp     rcx, rdx
0x14000f126  setnz   dl
0x14000f129  mov     rax, [rax+20h]
0x14000f12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f132  test    ebx, ebx
0x14000f134  js      loc_14000F03D
0x14000f13a  lea     r8, [r15+8]; pcbe
0x14000f13e  mov     rdx, rsi; pv
0x14000f141  lea     rcx, ?WorkCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x14000f148  call    cs:__imp_CreateThreadpoolWork
0x14000f14e  mov     rdi, rax
0x14000f151  test    rax, rax
0x14000f154  jz      short loc_14000F15A
0x14000f156  xor     ebx, ebx
0x14000f158  jmp     short loc_14000F177
0x14000f15a  call    cs:__imp_GetLastError
0x14000f160  mov     ebx, eax
0x14000f162  test    eax, eax
0x14000f164  jle     short loc_14000F16F
0x14000f166  movzx   ebx, ax
0x14000f169  or      ebx, 80070000h
0x14000f16f  test    ebx, ebx
0x14000f171  js      loc_14000F03D
0x14000f177  xor     esi, esi
0x14000f179  mov     rcx, rdi; pwk
0x14000f17c  call    cs:__imp_SubmitThreadpoolWork
0x14000f182  jmp     loc_14000F03D
0x14000f187  xor     esi, esi
0x14000f189  jmp     loc_14000F02F
0x14000f18e  mov     rcx, rsi; this
0x14000f191  call    ??_G_WorkTask@@QEAAPEAXI@Z; _WorkTask::`scalar deleting destructor'(uint)
0x14000f196  jmp     loc_14000F046
```
