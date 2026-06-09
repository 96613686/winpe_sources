# ForceFeedbackMotorStateCache::GetBufferEffectState(GameInputForceFeedbackEffect const *,SharedBufferPtr &)

- ea: `0x180006798`
- end: `0x18000686c`
- name: `?GetBufferEffectState@ForceFeedbackMotorStateCache@@QEBAPEAVForceFeedbackEffectState@@PEBVGameInputForceFeedbackEffect@@AEAVSharedBufferPtr@@@Z`
- size: `212`
- prototype: `struct ForceFeedbackEffectState *__fastcall(ForceFeedbackMotorStateCache *__hidden this, const struct GameInputForceFeedbackEffect *, struct SharedBufferPtr *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x18000643c`
- `0x180007c30`
- `0x180008424`
- `0x18000b0c0`
- `0x18000b260`
- `0x18000b5a0`

## callees

- `0x180006798`
- `0x1800069a4`
- `0x1800077d0`
- `0x18000a7a0`

## pseudocode

```c
struct ForceFeedbackEffectState *__fastcall ForceFeedbackMotorStateCache::GetBufferEffectState(
        ForceFeedbackMotorStateCache *this,
        const struct GameInputForceFeedbackEffect *a2,
        SharedBuffer **a3)
{
  SharedBuffer **CurrentBuffer; // rax
  SharedBuffer *v7; // rcx
  SharedBuffer **v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rdi
  unsigned int PoolEffectIndex; // eax
  __int64 v14; // r8
  struct ForceFeedbackEffectState *result; // rax
  SharedBuffer *v16; // [rsp+50h] [rbp+8h] BYREF

  CurrentBuffer = (SharedBuffer **)GameInputDevice::GetCurrentBuffer(*(_QWORD *)this, &v16);
  v7 = *a3;
  v8 = CurrentBuffer;
  if ( *a3 != *CurrentBuffer )
  {
    if ( v7 )
      SharedBuffer::ReleaseReference(v7);
    *a3 = *v8;
    *v8 = 0;
  }
  if ( v16 )
    SharedBuffer::ReleaseReference(v16);
  if ( !*a3
    || (v9 = *((_QWORD *)*a3 + 10)) == 0
    || (v10 = (*(unsigned int *)(v9 + 24) + v9) & -(__int64)(*(_DWORD *)(v9 + 24) != 0)) == 0
    || (v11 = *(unsigned int *)(v10 + 4LL * *((unsigned int *)this + 2)), (v12 = (v11 + v9) & -(__int64)(v11 != 0)) == 0)
    || (PoolEffectIndex = ForceFeedbackMotorStateCache::GetPoolEffectIndex(this, a2),
        (v14 = (*(unsigned int *)(v12 + 8) + v12) & -(__int64)(*(_DWORD *)(v12 + 8) != 0)) == 0)
    || (result = (struct ForceFeedbackEffectState *)(v14 + 136LL * PoolEffectIndex)) == 0 )
  {
    if ( *a3 )
    {
      SharedBuffer::ReleaseReference(*a3);
      *a3 = 0;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006798  push    rbx
0x18000679a  push    rbp
0x18000679b  push    rsi
0x18000679c  push    rdi
0x18000679d  sub     rsp, 28h
0x1800067a1  mov     rbp, rdx
0x1800067a4  mov     rsi, rcx
0x1800067a7  mov     rcx, [rcx]
0x1800067aa  lea     rdx, [rsp+48h+arg_0]
0x1800067af  mov     rbx, r8
0x1800067b2  call    ?GetCurrentBuffer@GameInputDevice@@QEBA?AVSharedBufferPtr@@XZ; GameInputDevice::GetCurrentBuffer(void)
0x1800067b7  mov     rcx, [rbx]; this
0x1800067ba  mov     rdi, rax
0x1800067bd  cmp     rcx, [rax]
0x1800067c0  jz      short loc_1800067D9
0x1800067c2  test    rcx, rcx
0x1800067c5  jz      short loc_1800067CC
0x1800067c7  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x1800067cc  mov     rcx, [rdi]
0x1800067cf  mov     [rbx], rcx
0x1800067d2  mov     qword ptr [rdi], 0
0x1800067d9  mov     rcx, [rsp+48h+arg_0]; this
0x1800067de  test    rcx, rcx
0x1800067e1  jz      short loc_1800067E8
0x1800067e3  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x1800067e8  mov     rdx, [rbx]
0x1800067eb  test    rdx, rdx
0x1800067ee  jz      short loc_18000684C
0x1800067f0  mov     rdx, [rdx+50h]
0x1800067f4  test    rdx, rdx
0x1800067f7  jz      short loc_18000684C
0x1800067f9  mov     eax, [rdx+18h]
0x1800067fc  lea     rcx, [rax+rdx]
0x180006800  neg     rax
0x180006803  sbb     r8, r8
0x180006806  and     r8, rcx
0x180006809  jz      short loc_18000684C
0x18000680b  mov     eax, [rsi+8]
0x18000680e  mov     ecx, [r8+rax*4]
0x180006812  lea     rax, [rcx+rdx]
0x180006816  neg     rcx
0x180006819  sbb     rdi, rdi
0x18000681c  and     rdi, rax
0x18000681f  jz      short loc_18000684C
0x180006821  mov     rdx, rbp; struct GameInputForceFeedbackEffect *
0x180006824  mov     rcx, rsi; this
0x180006827  call    ?GetPoolEffectIndex@ForceFeedbackMotorStateCache@@AEBAIPEBVGameInputForceFeedbackEffect@@@Z; ForceFeedbackMotorStateCache::GetPoolEffectIndex(GameInputForceFeedbackEffect const *)
0x18000682c  mov     ecx, [rdi+8]
0x18000682f  lea     rdx, [rcx+rdi]
0x180006833  neg     rcx
0x180006836  sbb     r8, r8
0x180006839  and     r8, rdx
0x18000683c  jz      short loc_18000684C
0x18000683e  mov     eax, eax
0x180006840  imul    rax, 88h
0x180006847  add     rax, r8
0x18000684a  jnz     short loc_180006862
0x18000684c  mov     rcx, [rbx]; this
0x18000684f  test    rcx, rcx
0x180006852  jz      short loc_180006860
0x180006854  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x180006859  mov     qword ptr [rbx], 0
0x180006860  xor     eax, eax
0x180006862  add     rsp, 28h
0x180006866  pop     rdi
0x180006867  pop     rsi
0x180006868  pop     rbp
0x180006869  pop     rbx
0x18000686a  retn
```
