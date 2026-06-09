# Rdp::Avenc::Hevc::CHevcProcessor::PacketWriterThreadProc(void)

- ea: `0x180024ee0`
- end: `0x1800252a1`
- name: `?PacketWriterThreadProc@CHevcProcessor@Hevc@Avenc@Rdp@@AEAAXXZ`
- size: `961`
- prototype: `void __fastcall(Rdp::Avenc::Hevc::CHevcProcessor *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006fc4`
- `0x1800103c0`
- `0x180010bc8`
- `0x1800203d4`
- `0x180023a28`
- `0x180024ee0`
- `0x180026ef0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180024fe0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180024fe0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024fc1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800251c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025257`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024fc1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800251c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025257`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180024ff7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025183`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180024ff7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025183`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024f88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024f88`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180024f7a`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180024f7a`

## string_xrefs

- `0x1800251eb`: `Failed to write packet to channel`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Rdp::Avenc::Hevc::CHevcProcessor::PacketWriterThreadProc(Rdp::Avenc::Hevc::CHevcProcessor *this)
{
  char *v2; // r13
  bool v3; // zf
  __int64 v4; // rbx
  _QWORD **v5; // r14
  _QWORD *v6; // rdx
  _QWORD *v7; // rax
  _QWORD *i; // r14
  __int64 *v9; // rcx
  _QWORD *v10; // rsi
  _QWORD *v11; // r12
  __int64 v12; // r15
  __int64 *v13; // rax
  __int64 v14; // rdx
  __int64 **v15; // rcx
  __int64 *j; // rcx
  _QWORD *v17; // rax
  unsigned int v18; // eax
  const char *v19; // [rsp+28h] [rbp-30h]
  __int128 v20; // [rsp+30h] [rbp-28h] BYREF
  char *v21; // [rsp+40h] [rbp-18h]
  char v22; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  _QWORD *v24; // [rsp+A8h] [rbp+50h] BYREF
  __int64 v25; // [rsp+B0h] [rbp+58h]
  __int64 v26; // [rsp+B8h] [rbp+60h] BYREF

  v20 = xmmword_180093D68;
  if ( *((_BYTE *)this + 520) )
  {
    v2 = (char *)this + 368;
    while ( 1 )
    {
      if ( (unsigned int)mtx_do_lock(v2) )
        std::_Throw_Cpp_error(5);
      if ( *((_DWORD *)v2 + 19) == 0x7FFFFFFF )
      {
        *((_DWORD *)v2 + 19) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      while ( *((_BYTE *)this + 520) && !*((_DWORD *)this + 131) )
      {
        *((_DWORD *)this + 110) = -1;
        --*((_DWORD *)this + 111);
        if ( !SleepConditionVariableSRW((PCONDITION_VARIABLE)this + 57, (PSRWLOCK)this + 48, 0xFFFFFFFF, 0) )
          abort();
        *((_DWORD *)this + 110) = GetCurrentThreadId();
        ++*((_DWORD *)this + 111);
      }
      if ( !*((_BYTE *)this + 520) )
        break;
      v3 = (*((_DWORD *)this + 111))-- == 1;
      if ( v3 )
      {
        *((_DWORD *)this + 110) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)this + 48);
      }
      v4 = 0;
      v25 = 0;
      v21 = (char *)this + 144;
      v22 = 1;
      AcquireSRWLockShared((PSRWLOCK)this + 18);
      v5 = (_QWORD **)((char *)this + 128);
      if ( *((_QWORD *)this + 17) )
      {
        std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Avenc::Hevc::CMonitorContext,wil::err_exception_policy>,GUIDComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Hevc::CMonitorContext,wil::err_exception_policy>>>,0>>::find(
          (char *)this + 128,
          &v24,
          &v20);
        v6 = *v5;
        v7 = v24;
        if ( v24 == *v5 )
          goto LABEL_24;
        i = (_QWORD *)v24[2];
        if ( *((_BYTE *)i + 25) )
        {
          for ( i = (_QWORD *)v24[1]; !*((_BYTE *)i + 25) && v7 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
            v7 = i;
        }
        else
        {
          v9 = (__int64 *)*i;
          if ( !*(_BYTE *)(*i + 25LL) )
          {
            do
            {
              i = v9;
              v9 = (__int64 *)*v9;
            }
            while ( !*((_BYTE *)v9 + 25) );
          }
        }
        v24 = i;
        if ( i == v6 )
        {
LABEL_24:
          i = (_QWORD *)*v6;
          v24 = (_QWORD *)*v6;
        }
        v10 = i;
        while ( 1 )
        {
          v11 = v10;
          v12 = *(_QWORD *)(v10[6] + 216LL);
          if ( v12 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
            v13 = (__int64 *)Rdp::Avenc::Hevc::CPacketQueue::Dequeue(v12 + 200, &v26);
            v14 = *v13;
            *v13 = 0;
            v4 = v14;
            v25 = v14;
            if ( v26 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          }
          if ( v4 )
            break;
          v15 = (__int64 **)v10[2];
          if ( *((_BYTE *)v15 + 25) )
          {
            while ( 1 )
            {
              v10 = (_QWORD *)v10[1];
              if ( *((_BYTE *)v10 + 25) || v11 != (_QWORD *)v10[2] )
                break;
              v11 = v10;
            }
          }
          else
          {
            v10 = (_QWORD *)v10[2];
            for ( j = *v15; !*((_BYTE *)j + 25); j = (__int64 *)*j )
              v10 = j;
          }
          v24 = v10;
          v17 = (_QWORD *)*((_QWORD *)this + 16);
          if ( v10 == v17 )
          {
            v10 = (_QWORD *)*v17;
            v24 = (_QWORD *)*v17;
          }
          if ( v12 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          if ( v10 == i )
            goto LABEL_45;
        }
        v20 = *((_OWORD *)v10 + 2);
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_45:
        ReleaseSRWLockShared((PSRWLOCK)this + 18);
        if ( v4 )
        {
          if ( (unsigned int)mtx_do_lock(v2) )
            std::_Throw_Cpp_error(5);
          if ( *((_DWORD *)v2 + 19) == 0x7FFFFFFF )
          {
            *((_DWORD *)v2 + 19) = 2147483646;
            std::_Throw_Cpp_error(6);
          }
          --*((_DWORD *)this + 131);
          v3 = (*((_DWORD *)v2 + 19))-- == 1;
          if ( v3 )
          {
            *((_DWORD *)v2 + 18) = -1;
            ReleaseSRWLockExclusive((PSRWLOCK)v2 + 2);
          }
          v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 36) + 64LL))(
                  *((_QWORD *)this + 36),
                  v4,
                  0);
          wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0x3E8,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
            (const char *)v18,
            (int)"Failed to write packet to channel",
            v19);
        }
        if ( v4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      }
      else
      {
        ReleaseSRWLockShared((PSRWLOCK)this + 18);
      }
      if ( !*((_BYTE *)this + 520) )
        return;
    }
    v3 = (*((_DWORD *)this + 111))-- == 1;
    if ( v3 )
    {
      *((_DWORD *)this + 110) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 48);
    }
  }
}

```

## disassembly

```asm
0x180024ee0  push    rbp
0x180024ee2  push    rbx
0x180024ee3  push    rsi
0x180024ee4  push    rdi
0x180024ee5  push    r12
0x180024ee7  push    r13
0x180024ee9  push    r14
0x180024eeb  push    r15
0x180024eed  mov     rbp, rsp
0x180024ef0  sub     rsp, 58h
0x180024ef4  mov     rdi, rcx
0x180024ef7  xor     r15d, r15d
0x180024efa  movups  xmm0, cs:xmmword_180093D68
0x180024f01  movdqu  [rbp+var_28], xmm0
0x180024f06  mov     al, [rcx+208h]
0x180024f0c  nop
0x180024f0d  test    al, al
0x180024f0f  jz      loc_180025230
0x180024f15  lea     r13, [rcx+170h]
0x180024f1c  mov     rcx, r13
0x180024f1f  call    mtx_do_lock
0x180024f24  test    eax, eax
0x180024f26  jnz     loc_180025272
0x180024f2c  cmp     dword ptr [r13+4Ch], 7FFFFFFFh
0x180024f34  jz      loc_18002525F
0x180024f3a  lea     rbx, [rdi+180h]
0x180024f41  mov     al, [rdi+208h]
0x180024f47  nop
0x180024f48  test    al, al
0x180024f4a  jz      short loc_180024F9C
0x180024f4c  cmp     [rdi+20Ch], r15d
0x180024f53  ja      short loc_180024F9C
0x180024f55  mov     dword ptr [rdi+1B8h], 0FFFFFFFFh
0x180024f5f  dec     dword ptr [rdi+1BCh]
0x180024f65  lea     rdx, [rdi+180h]; SRWLock
0x180024f6c  lea     rcx, [rdi+1C8h]; ConditionVariable
0x180024f73  xor     r9d, r9d; Flags
0x180024f76  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180024f7a  call    cs:__imp_SleepConditionVariableSRW
0x180024f80  test    eax, eax
0x180024f82  jz      loc_18002527D
0x180024f88  call    cs:__imp_GetCurrentThreadId
0x180024f8e  mov     [rdi+1B8h], eax
0x180024f94  inc     dword ptr [rdi+1BCh]
0x180024f9a  jmp     short loc_180024F41
0x180024f9c  mov     al, [rdi+208h]
0x180024fa2  nop
0x180024fa3  test    al, al
0x180024fa5  jz      loc_180025241
0x180024fab  sub     dword ptr [rdi+1BCh], 1
0x180024fb2  jnz     short loc_180024FC7
0x180024fb4  mov     dword ptr [rdi+1B8h], 0FFFFFFFFh
0x180024fbe  mov     rcx, rbx; SRWLock
0x180024fc1  call    cs:__imp_ReleaseSRWLockExclusive
0x180024fc7  mov     rbx, r15
0x180024fca  mov     [rbp+arg_10], rbx
0x180024fce  lea     rsi, [rdi+90h]
0x180024fd5  mov     [rbp+var_18], rsi
0x180024fd9  mov     [rbp+var_10], 1
0x180024fdd  mov     rcx, rsi; SRWLock
0x180024fe0  call    cs:__imp_AcquireSRWLockShared
0x180024fe6  nop
0x180024fe7  lea     r14, [rdi+80h]
0x180024fee  cmp     [r14+8], r15
0x180024ff2  jnz     short loc_180025003
0x180024ff4  mov     rcx, rsi; SRWLock
0x180024ff7  call    cs:__imp_ReleaseSRWLockShared
0x180024ffd  nop
0x180024ffe  jmp     loc_180025221
0x180025003  lea     r8, [rbp+var_28]
0x180025007  lea     rdx, [rbp+arg_8]
0x18002500b  mov     rcx, r14
0x18002500e  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$com_ptr_t@VCMonitorContext@Hevc@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@UGUIDComparer@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorContext@Hevc@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorContext@Hevc@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Avenc::Hevc::CMonitorContext,wil::err_exception_policy>,GUIDComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Hevc::CMonitorContext,wil::err_exception_policy>>>,0>>::find(_GUID const &)
0x180025013  mov     rdx, [r14]
0x180025016  mov     rax, [rbp+arg_8]
0x18002501a  cmp     rax, rdx
0x18002501d  jz      short loc_180025065
0x18002501f  mov     r14, [rax+10h]
0x180025023  cmp     [r14+19h], r15b
0x180025027  jz      short loc_180025044
0x180025029  mov     r14, [rax+8]
0x18002502d  jmp     short loc_18002503C
0x18002502f  cmp     rax, [r14+10h]
0x180025033  jnz     short loc_18002505C
0x180025035  mov     rax, r14
0x180025038  mov     r14, [r14+8]
0x18002503c  cmp     [r14+19h], r15b
0x180025040  jz      short loc_18002502F
0x180025042  jmp     short loc_18002505C
0x180025044  mov     rcx, [r14]
0x180025047  cmp     [rcx+19h], r15b
0x18002504b  jnz     short loc_18002505C
0x18002504d  mov     r14, rcx
0x180025050  mov     rax, [rcx]
0x180025053  mov     rcx, rax
0x180025056  cmp     [rax+19h], r15b
0x18002505a  jz      short loc_18002504D
0x18002505c  mov     [rbp+arg_8], r14
0x180025060  cmp     r14, rdx
0x180025063  jnz     short loc_18002506C
0x180025065  mov     r14, [rdx]
0x180025068  mov     [rbp+arg_8], r14
0x18002506c  mov     rsi, r14
0x18002506f  mov     r12, rsi
0x180025072  mov     rax, [rsi+30h]
0x180025076  mov     r15, [rax+0D8h]
0x18002507d  mov     [rbp+arg_0], r15
0x180025081  test    r15, r15
0x180025084  jz      short loc_180025096
0x180025086  mov     rax, [r15]
0x180025089  mov     rcx, r15
0x18002508c  mov     rax, [rax+8]
0x180025090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025095  nop
0x180025096  test    r15, r15
0x180025099  jz      short loc_1800250E7
0x18002509b  lea     rcx, [r15+0C8h]
0x1800250a2  lea     rdx, [rbp+arg_18]
0x1800250a6  call    ?Dequeue@CPacketQueue@Hevc@Avenc@Rdp@@QEAA?AV?$com_ptr_t@UIIoPacket@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@XZ; Rdp::Avenc::Hevc::CPacketQueue::Dequeue(void)
0x1800250ab  mov     rdx, [rax]
0x1800250ae  mov     qword ptr [rax], 0
0x1800250b5  mov     rcx, rbx
0x1800250b8  mov     rbx, rdx
0x1800250bb  mov     [rbp+arg_10], rdx
0x1800250bf  test    rcx, rcx
0x1800250c2  jz      short loc_1800250D1
0x1800250c4  mov     rax, [rcx]
0x1800250c7  mov     rax, [rax+10h]
0x1800250cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250d0  nop
0x1800250d1  mov     rcx, [rbp+arg_18]
0x1800250d5  test    rcx, rcx
0x1800250d8  jz      short loc_1800250E7
0x1800250da  mov     rax, [rcx]
0x1800250dd  mov     rax, [rax+10h]
0x1800250e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250e6  nop
0x1800250e7  test    rbx, rbx
0x1800250ea  jnz     short loc_18002515E
0x1800250ec  mov     rcx, [rsi+10h]
0x1800250f0  cmp     [rcx+19h], bl
0x1800250f3  jnz     short loc_180025152
0x1800250f5  mov     rsi, rcx
0x1800250f8  mov     rcx, [rcx]
0x1800250fb  cmp     [rcx+19h], bl
0x1800250fe  jnz     short loc_18002510F
0x180025100  mov     rsi, rcx
0x180025103  mov     rax, [rcx]
0x180025106  mov     rcx, rax
0x180025109  cmp     byte ptr [rax+19h], 0
0x18002510d  jz      short loc_180025100
0x18002510f  mov     [rbp+arg_8], rsi
0x180025113  mov     rax, [rdi+80h]
0x18002511a  cmp     rsi, rax
0x18002511d  jnz     short loc_180025126
0x18002511f  mov     rsi, [rax]
0x180025122  mov     [rbp+arg_8], rsi
0x180025126  mov     r12, rsi
0x180025129  test    r15, r15
0x18002512c  jz      short loc_18002513E
0x18002512e  mov     rax, [r15]
0x180025131  mov     rcx, r15
0x180025134  mov     rax, [rax+10h]
0x180025138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002513d  nop
0x18002513e  cmp     r12, r14
0x180025141  jnz     loc_18002506F
0x180025147  jmp     short loc_18002517C
0x180025149  cmp     r12, [rsi+10h]
0x18002514d  jnz     short loc_18002510F
0x18002514f  mov     r12, rsi
0x180025152  mov     rsi, [rsi+8]
0x180025156  cmp     byte ptr [rsi+19h], 0
0x18002515a  jz      short loc_180025149
0x18002515c  jmp     short loc_18002510F
0x18002515e  movups  xmm0, xmmword ptr [rsi+20h]
0x180025162  movdqu  [rbp+var_28], xmm0
0x180025167  test    r15, r15
0x18002516a  jz      short loc_18002517C
0x18002516c  mov     rax, [r15]
0x18002516f  mov     rcx, r15
0x180025172  mov     rax, [rax+10h]
0x180025176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002517b  nop
0x18002517c  lea     rcx, [rdi+90h]; SRWLock
0x180025183  call    cs:__imp_ReleaseSRWLockShared
0x180025189  xor     r15d, r15d
0x18002518c  test    rbx, rbx
0x18002518f  jz      short loc_18002520C
0x180025191  mov     rcx, r13
0x180025194  call    mtx_do_lock
0x180025199  test    eax, eax
0x18002519b  jnz     loc_180025296
0x1800251a1  cmp     dword ptr [r13+4Ch], 7FFFFFFFh
0x1800251a9  jz      loc_180025283
0x1800251af  dec     dword ptr [rdi+20Ch]
0x1800251b5  sub     dword ptr [r13+4Ch], 1
0x1800251ba  jnz     short loc_1800251CE
0x1800251bc  mov     dword ptr [r13+48h], 0FFFFFFFFh
0x1800251c4  lea     rcx, [r13+10h]; SRWLock
0x1800251c8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800251ce  mov     rcx, [rdi+120h]
0x1800251d5  mov     rax, [rcx]
0x1800251d8  xor     r8d, r8d
0x1800251db  mov     rdx, rbx
0x1800251de  mov     rax, [rax+40h]
0x1800251e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251e7  mov     rcx, [rbp+40h]; this
0x1800251eb  lea     rdx, aFailedToWriteP; "Failed to write packet to channel"
0x1800251f2  mov     qword ptr [rsp+58h+var_38], rdx; int
0x1800251f7  mov     r9d, eax; char *
0x1800251fa  lea     r8, aOnecoreuapTerm_26; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180025201  mov     edx, 3E8h; void *
0x180025206  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002520b  nop
0x18002520c  test    rbx, rbx
0x18002520f  jz      short loc_180025221
0x180025211  mov     rax, [rbx]
0x180025214  mov     rcx, rbx
0x180025217  mov     rax, [rax+10h]
0x18002521b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025220  nop
0x180025221  mov     al, [rdi+208h]
0x180025227  nop
0x180025228  test    al, al
0x18002522a  jnz     loc_180024F1C
0x180025230  add     rsp, 58h
0x180025234  pop     r15
0x180025236  pop     r14
0x180025238  pop     r13
0x18002523a  pop     r12
0x18002523c  pop     rdi
0x18002523d  pop     rsi
0x18002523e  pop     rbx
0x18002523f  pop     rbp
0x180025240  retn
0x180025241  sub     dword ptr [rdi+1BCh], 1
0x180025248  jnz     short loc_180025230
0x18002524a  mov     dword ptr [rdi+1B8h], 0FFFFFFFFh
0x180025254  mov     rcx, rbx; SRWLock
0x180025257  call    cs:__imp_ReleaseSRWLockExclusive
0x18002525d  jmp     short loc_180025230
0x18002525f  mov     dword ptr [r13+4Ch], 7FFFFFFEh
0x180025267  mov     ecx, 6; int
0x18002526c  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180025272  mov     ecx, 5; int
0x180025277  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18002527d  call    abort
0x180025283  mov     dword ptr [r13+4Ch], 7FFFFFFEh
0x18002528b  mov     ecx, 6; int
0x180025290  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180025296  mov     ecx, 5; int
0x18002529b  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
