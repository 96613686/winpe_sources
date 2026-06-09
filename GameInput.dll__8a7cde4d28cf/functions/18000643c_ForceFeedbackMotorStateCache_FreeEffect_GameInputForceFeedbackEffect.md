# ForceFeedbackMotorStateCache::FreeEffect(GameInputForceFeedbackEffect *)

- ea: `0x18000643c`
- end: `0x180006543`
- name: `?FreeEffect@ForceFeedbackMotorStateCache@@QEAAXPEAVGameInputForceFeedbackEffect@@@Z`
- size: `263`
- prototype: `void __fastcall(ForceFeedbackMotorStateCache *__hidden this, struct GameInputForceFeedbackEffect *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18000a6b0`

## callees

- `0x18000643c`
- `0x18000654c`
- `0x180006798`
- `0x1800077d0`
- `0x18000a7a0`
- `0x18002388c`
- `0x18002391c`
- `0x18004d010`

## pseudocode

```c
void __fastcall ForceFeedbackMotorStateCache::FreeEffect(
        ForceFeedbackMotorStateCache *this,
        struct GameInputForceFeedbackEffect *a2)
{
  ForceFeedbackMotorStateCache *v4; // rcx
  struct ForceFeedbackEffectState *BufferEffectState; // rax
  SharedBuffer *v6; // rbx
  void *v7; // rdi
  unsigned int v8; // edi
  unsigned int PoolEffectIndex; // eax
  SharedBuffer *v10; // [rsp+50h] [rbp+8h] BYREF
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF

  v11 = 0;
  VersionedDataGuard::BeginUpdate((char *)a2 + 24, 0, &v11);
  *((_QWORD *)a2 + 4) = 0;
  _mm_mfence();
  *((_DWORD *)a2 + 10) = 0;
  _mm_mfence();
  v4 = (ForceFeedbackMotorStateCache *)*((_QWORD *)a2 + 2);
  v10 = 0;
  BufferEffectState = ForceFeedbackMotorStateCache::GetBufferEffectState(v4, a2, (struct SharedBufferPtr *)&v10);
  v6 = v10;
  if ( BufferEffectState )
  {
    v7 = (char *)BufferEffectState + 8;
    if ( !(unsigned int)VersionedDataGuard::BeginUpdateToVersion((char *)BufferEffectState + 8, 0, v11) )
    {
      _m_prefetchw(v7);
      if ( (_InterlockedAnd64((volatile signed __int64 *)v7, 0xFFFFFFFFFFFFFFFDuLL) & 1) == 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v6 + 13) + 72LL))(*((_QWORD *)v6 + 13));
    }
  }
  _InterlockedAnd64((volatile signed __int64 *)a2 + 3, 0xFFFFFFFFFFFFFFFDuLL);
  v8 = *((_DWORD *)a2 + 11);
  if ( v6 )
    SharedBuffer::ReleaseReference(v6);
  PoolEffectIndex = ForceFeedbackMotorStateCache::GetPoolEffectIndex(this, a2);
  _InterlockedOr64(
    (volatile signed __int64 *)this + ((unsigned __int64)PoolEffectIndex >> 6) + 3,
    1LL << (PoolEffectIndex & 0x3F));
  ForceFeedbackMotorResourceState::FreeEffectResources((char *)this + 88, v8);
}

```

## disassembly

```asm
0x18000643c  mov     [rsp+arg_10], rbx
0x180006441  push    rbp
0x180006442  push    rsi
0x180006443  push    rdi
0x180006444  push    r14
0x180006446  push    r15
0x180006448  sub     rsp, 20h
0x18000644c  mov     rsi, rdx
0x18000644f  mov     [rsp+48h+arg_8], 0
0x180006458  mov     r15, rcx
0x18000645b  lea     r8, [rsp+48h+arg_8]
0x180006460  xor     edx, edx
0x180006462  lea     rcx, [rsi+18h]
0x180006466  call    ?BeginUpdate@VersionedDataGuard@@QEAA?AW4VersionedDataStatus@@_NAEA_K@Z; VersionedDataGuard::BeginUpdate(bool,unsigned __int64 &)
0x18000646b  nop
0x18000646c  mov     qword ptr [rsi+20h], 0
0x180006474  mfence
0x180006477  xorps   xmm0, xmm0
0x18000647a  nop
0x18000647b  movss   dword ptr [rsi+28h], xmm0
0x180006480  mfence
0x180006483  mov     rcx, [rsi+10h]; this
0x180006487  lea     r8, [rsp+48h+arg_0]; struct SharedBufferPtr *
0x18000648c  mov     rdx, rsi; struct GameInputForceFeedbackEffect *
0x18000648f  mov     [rsp+48h+arg_0], 0
0x180006498  call    ?GetBufferEffectState@ForceFeedbackMotorStateCache@@QEBAPEAVForceFeedbackEffectState@@PEBVGameInputForceFeedbackEffect@@AEAVSharedBufferPtr@@@Z; ForceFeedbackMotorStateCache::GetBufferEffectState(GameInputForceFeedbackEffect const *,SharedBufferPtr &)
0x18000649d  mov     rbx, [rsp+48h+arg_0]
0x1800064a2  mov     ebp, 1
0x1800064a7  test    rax, rax
0x1800064aa  jz      short loc_1800064EE
0x1800064ac  mov     r8, [rsp+48h+arg_8]
0x1800064b1  lea     rdi, [rax+8]
0x1800064b5  mov     rcx, rdi
0x1800064b8  xor     edx, edx
0x1800064ba  call    ?BeginUpdateToVersion@VersionedDataGuard@@QEAA?AW4VersionedDataStatus@@_N_K@Z; VersionedDataGuard::BeginUpdateToVersion(bool,unsigned __int64)
0x1800064bf  test    eax, eax
0x1800064c1  jnz     short loc_1800064EE
0x1800064c3  nop
0x1800064c4  prefetchw byte ptr [rdi]
0x1800064c7  mov     rax, [rdi]
0x1800064ca  mov     rcx, rax
0x1800064cd  and     rcx, 0FFFFFFFFFFFFFFFDh
0x1800064d1  lock cmpxchg [rdi], rcx
0x1800064d6  jnz     short loc_1800064CA
0x1800064d8  nop
0x1800064d9  test    bpl, al
0x1800064dc  jnz     short loc_1800064EE
0x1800064de  mov     rcx, [rbx+68h]
0x1800064e2  mov     rax, [rcx]
0x1800064e5  mov     rax, [rax+48h]
0x1800064e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ee  nop
0x1800064ef  lock and qword ptr [rsi+18h], 0FFFFFFFFFFFFFFFDh
0x1800064f5  nop
0x1800064f6  mov     edi, [rsi+2Ch]
0x1800064f9  test    rbx, rbx
0x1800064fc  jz      short loc_180006506
0x1800064fe  mov     rcx, rbx; this
0x180006501  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x180006506  mov     rdx, rsi; struct GameInputForceFeedbackEffect *
0x180006509  mov     rcx, r15; this
0x18000650c  call    ?GetPoolEffectIndex@ForceFeedbackMotorStateCache@@AEBAIPEBVGameInputForceFeedbackEffect@@@Z; ForceFeedbackMotorStateCache::GetPoolEffectIndex(GameInputForceFeedbackEffect const *)
0x180006511  mov     cl, al
0x180006513  mov     r8d, eax
0x180006516  and     cl, 3Fh
0x180006519  nop
0x18000651a  shl     rbp, cl
0x18000651d  shr     r8, 6
0x180006521  lock or [r15+r8*8+18h], rbp
0x180006527  lea     rcx, [r15+58h]
0x18000652b  mov     edx, edi
0x18000652d  nop
0x18000652e  mov     rbx, [rsp+48h+arg_10]
0x180006533  add     rsp, 20h
0x180006537  pop     r15
0x180006539  pop     r14
0x18000653b  pop     rdi
0x18000653c  pop     rsi
0x18000653d  pop     rbp
0x18000653e  jmp     ?FreeEffectResources@ForceFeedbackMotorResourceState@@QEAAXW4GameInputForceFeedbackEffectKind@@@Z; ForceFeedbackMotorResourceState::FreeEffectResources(GameInputForceFeedbackEffectKind)
```
