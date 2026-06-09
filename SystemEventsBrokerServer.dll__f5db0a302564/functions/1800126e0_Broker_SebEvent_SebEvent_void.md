# Broker::SebEvent::~SebEvent(void)

- ea: `0x1800126e0`
- end: `0x1800129b5`
- name: `??1SebEvent@Broker@@UEAA@XZ`
- size: `725`
- prototype: `void __fastcall(Broker::SebEvent *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800126a0`

## callees

- `0x180008c00`
- `0x1800126e0`
- `0x180019130`
- `0x18001d364`
- `0x18001e0d8`
- `0x180027010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012704`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012704`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001279a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001279a`
- `ntdll!RtlWakeAddressAll` at `0x180012742`
- `ntdll!RtlWakeAddressAll` at `0x180012742`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180012942`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180012942`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001270a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001270a`

## pseudocode

```c
void __fastcall Broker::SebEvent::~SebEvent(Broker::SebEvent *this)
{
  __int64 v2; // r14
  volatile signed __int32 *v3; // rdi
  void *v4; // rcx
  unsigned __int64 v5; // rdx
  volatile signed __int32 *v6; // rdi
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rdx
  void *v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // [rsp+50h] [rbp+8h] BYREF
  void *v12; // [rsp+58h] [rbp+10h] BYREF

  *(_QWORD *)this = &Broker::SebEvent::`vftable';
  RtlAcquireSRWLockExclusive((char *)this + 208);
  GetCurrentThreadId();
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids,
      *((_QWORD *)this + 28));
  v2 = *((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = 0;
  *((_DWORD *)this + 33) = 0;
  RtlWakeAddressAll();
  *((_QWORD *)this + 13) = 0;
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  RtlReleaseSRWLockExclusive((char *)this + 208);
  if ( v2 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF__guid_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids,
        *((_QWORD *)this + 28));
    RtlUnsubscribeWnfNotificationWaitForCompletion(v2);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids,
      *((_QWORD *)this + 28));
  v4 = (void *)*((_QWORD *)this + 18);
  if ( v4 )
  {
    v5 = *((_QWORD *)this + 20) - (_QWORD)v4;
    v12 = (void *)*((_QWORD *)this + 18);
    v11 = v5;
    if ( v5 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v12, &v11);
      v5 = v11;
      v4 = v12;
    }
    operator delete(v4, v5);
    *((_QWORD *)this + 18) = 0;
    *((_QWORD *)this + 19) = 0;
    *((_QWORD *)this + 20) = 0;
  }
  v6 = (volatile signed __int32 *)*((_QWORD *)this + 14);
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  v7 = *((_QWORD *)this + 11);
  if ( v7 > 7 )
    std::_Deallocate<16>(*((void **)this + 8), 2 * v7 + 2);
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 7;
  *((_WORD *)this + 32) = 0;
  v8 = *((_QWORD *)this + 7);
  if ( v8 > 7 )
    std::_Deallocate<16>(*((void **)this + 4), 2 * v8 + 2);
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 7;
  *((_WORD *)this + 16) = 0;
  v9 = (void *)*((_QWORD *)this + 1);
  if ( v9 )
  {
    v10 = *((_QWORD *)this + 3) - (_QWORD)v9;
    v12 = (void *)*((_QWORD *)this + 1);
    v11 = v10;
    if ( v10 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v12, &v11);
      v10 = v11;
      v9 = v12;
    }
    operator delete(v9, v10);
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x1800126e0  mov     [rsp+arg_10], rbx
0x1800126e5  push    rbp
0x1800126e6  push    rsi
0x1800126e7  push    rdi
0x1800126e8  push    r14
0x1800126ea  push    r15
0x1800126ec  sub     rsp, 20h
0x1800126f0  lea     rax, ??_7SebEvent@Broker@@6B@; const Broker::SebEvent::`vftable'
0x1800126f7  mov     rbx, rcx
0x1800126fa  mov     [rcx], rax
0x1800126fd  add     rcx, 0D0h
0x180012704  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001270a  call    cs:__imp_GetCurrentThreadId
0x180012710  mov     rcx, cs:WPP_GLOBAL_Control
0x180012717  test    byte ptr [rcx+1Ch], 1
0x18001271b  jz      short loc_180012727
0x18001271d  cmp     byte ptr [rcx+19h], 4
0x180012721  jnb     loc_1800128C4
0x180012727  mov     r14, [rbx+0B0h]
0x18001272e  lea     rcx, [rbx+84h]
0x180012735  xor     r15d, r15d
0x180012738  mov     [rbx+0B0h], r15
0x18001273f  mov     [rcx], r15d
0x180012742  call    cs:__imp_RtlWakeAddressAll
0x180012748  mov     [rbx+68h], r15
0x18001274c  mov     esi, 0FFFFFFFFh
0x180012751  mov     rdi, [rbx+70h]
0x180012755  mov     [rbx+70h], r15
0x180012759  test    rdi, rdi
0x18001275c  jz      short loc_180012793
0x18001275e  mov     eax, esi
0x180012760  lock xadd [rdi+8], eax
0x180012765  cmp     eax, 1
0x180012768  jnz     short loc_180012793
0x18001276a  mov     rax, [rdi]
0x18001276d  mov     rcx, rdi
0x180012770  mov     rax, [rax]
0x180012773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012778  mov     eax, esi
0x18001277a  lock xadd [rdi+0Ch], eax
0x18001277f  cmp     eax, 1
0x180012782  jnz     short loc_180012793
0x180012784  mov     rax, [rdi]
0x180012787  mov     rcx, rdi
0x18001278a  mov     rax, [rax+8]
0x18001278e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012793  lea     rcx, [rbx+0D0h]
0x18001279a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800127a0  test    r14, r14
0x1800127a3  jnz     loc_180012910
0x1800127a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127b0  test    byte ptr [rcx+1Ch], 1
0x1800127b4  jnz     loc_1800128E5
0x1800127ba  mov     rcx, [rbx+90h]; void *
0x1800127c1  test    rcx, rcx
0x1800127c4  jz      short loc_180012801
0x1800127c6  mov     rdx, [rbx+0A0h]
0x1800127cd  sub     rdx, rcx; unsigned __int64
0x1800127d0  mov     [rsp+48h+arg_8], rcx
0x1800127d5  mov     [rsp+48h+arg_0], rdx
0x1800127da  cmp     rdx, 1000h
0x1800127e1  jnb     loc_18001294D
0x1800127e7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800127ec  mov     [rbx+90h], r15
0x1800127f3  mov     [rbx+98h], r15
0x1800127fa  mov     [rbx+0A0h], r15
0x180012801  mov     rdi, [rbx+70h]
0x180012805  test    rdi, rdi
0x180012808  jz      short loc_18001283D
0x18001280a  mov     eax, esi
0x18001280c  lock xadd [rdi+8], eax
0x180012811  cmp     eax, 1
0x180012814  jnz     short loc_18001283D
0x180012816  mov     rax, [rdi]
0x180012819  mov     rcx, rdi
0x18001281c  mov     rax, [rax]
0x18001281f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012824  lock xadd [rdi+0Ch], esi
0x180012829  cmp     esi, 1
0x18001282c  jnz     short loc_18001283D
0x18001282e  mov     rax, [rdi]
0x180012831  mov     rcx, rdi
0x180012834  mov     rax, [rax+8]
0x180012838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001283d  mov     rdx, [rbx+58h]
0x180012841  cmp     rdx, 7
0x180012845  ja      loc_18001296B
0x18001284b  mov     [rbx+50h], r15
0x18001284f  mov     qword ptr [rbx+58h], 7
0x180012857  mov     [rbx+40h], r15w
0x18001285c  mov     rdx, [rbx+38h]
0x180012860  cmp     rdx, 7
0x180012864  ja      loc_180012981
0x18001286a  mov     [rbx+30h], r15
0x18001286e  mov     qword ptr [rbx+38h], 7
0x180012876  mov     [rbx+20h], r15w
0x18001287b  mov     rcx, [rbx+8]; void *
0x18001287f  test    rcx, rcx
0x180012882  jz      short loc_1800128B3
0x180012884  mov     rdx, [rbx+18h]
0x180012888  sub     rdx, rcx; unsigned __int64
0x18001288b  mov     [rsp+48h+arg_8], rcx
0x180012890  mov     [rsp+48h+arg_0], rdx
0x180012895  cmp     rdx, 1000h
0x18001289c  jnb     loc_180012997
0x1800128a2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800128a7  mov     [rbx+8], r15
0x1800128ab  mov     [rbx+10h], r15
0x1800128af  mov     [rbx+18h], r15
0x1800128b3  mov     rbx, [rsp+48h+arg_10]
0x1800128b8  add     rsp, 20h
0x1800128bc  pop     r15
0x1800128be  pop     r14
0x1800128c0  pop     rdi
0x1800128c1  pop     rsi
0x1800128c2  pop     rbp
0x1800128c3  retn
0x1800128c4  mov     r9, [rbx+0E0h]
0x1800128cb  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x1800128d2  mov     rcx, [rcx+10h]
0x1800128d6  mov     edx, 0Bh
0x1800128db  call    WPP_SF__guid_
0x1800128e0  jmp     loc_180012727
0x1800128e5  cmp     byte ptr [rcx+19h], 4
0x1800128e9  jb      loc_1800127BA
0x1800128ef  mov     r9, [rbx+0E0h]
0x1800128f6  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x1800128fd  mov     rcx, [rcx+10h]
0x180012901  mov     edx, 0Dh
0x180012906  call    WPP_SF__guid_
0x18001290b  jmp     loc_1800127BA
0x180012910  mov     rcx, cs:WPP_GLOBAL_Control
0x180012917  test    byte ptr [rcx+1Ch], 1
0x18001291b  jz      short loc_18001293F
0x18001291d  cmp     byte ptr [rcx+19h], 4
0x180012921  jb      short loc_18001293F
0x180012923  mov     r9, [rbx+0E0h]
0x18001292a  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x180012931  mov     rcx, [rcx+10h]
0x180012935  mov     edx, 0Ch
0x18001293a  call    WPP_SF__guid_
0x18001293f  mov     rcx, r14
0x180012942  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180012948  jmp     loc_1800127A9
0x18001294d  lea     rdx, [rsp+48h+arg_0]; unsigned __int64 *
0x180012952  lea     rcx, [rsp+48h+arg_8]; void **
0x180012957  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18001295c  mov     rdx, [rsp+48h+arg_0]
0x180012961  mov     rcx, [rsp+48h+arg_8]
0x180012966  jmp     loc_1800127E7
0x18001296b  mov     rcx, [rbx+40h]
0x18001296f  lea     rdx, ds:2[rdx*2]
0x180012977  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001297c  jmp     loc_18001284B
0x180012981  mov     rcx, [rbx+20h]
0x180012985  lea     rdx, ds:2[rdx*2]
0x18001298d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012992  jmp     loc_18001286A
0x180012997  lea     rdx, [rsp+48h+arg_0]; unsigned __int64 *
0x18001299c  lea     rcx, [rsp+48h+arg_8]; void **
0x1800129a1  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x1800129a6  mov     rdx, [rsp+48h+arg_0]
0x1800129ab  mov     rcx, [rsp+48h+arg_8]
0x1800129b0  jmp     loc_1800128A2
```
