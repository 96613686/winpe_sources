# ForceFeedbackMotorStateCache::AllocateEffect(GameInputForceFeedbackParams const *,GameInputForceFeedbackEffect * *)

- ea: `0x180004524`
- end: `0x180004689`
- name: `?AllocateEffect@ForceFeedbackMotorStateCache@@QEAAJPEBUGameInputForceFeedbackParams@@PEAPEAVGameInputForceFeedbackEffect@@@Z`
- size: `357`
- prototype: `int(ForceFeedbackMotorStateCache *__hidden this, const struct GameInputForceFeedbackParams *, struct GameInputForceFeedbackEffect **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800056d0`

## callees

- `0x180004524`
- `0x18000654c`
- `0x1800065d8`
- `0x180007e80`
- `0x180008424`
- `0x1800086d4`
- `0x180009ec0`

## pseudocode

```c
__int64 __fastcall ForceFeedbackMotorStateCache::AllocateEffect(
        ForceFeedbackMotorStateCache *this,
        const struct GameInputForceFeedbackParams *a2,
        struct GameInputForceFeedbackEffect **a3)
{
  unsigned int v3; // esi
  volatile signed __int64 *v4; // rbx
  signed __int64 v5; // rdi
  bool v8; // zf
  signed __int64 v9; // rax
  __int64 v10; // r10
  __int64 v11; // rdx
  unsigned __int64 v12; // r8
  int v13; // r9d
  __int64 v14; // rcx
  signed __int64 v15; // rax
  __int64 result; // rax
  volatile signed __int32 *v17; // rbx
  int v18; // [rsp+20h] [rbp-10h]
  int v19; // [rsp+60h] [rbp+30h] BYREF
  unsigned __int8 v20; // [rsp+68h] [rbp+38h] BYREF
  unsigned int v21; // [rsp+78h] [rbp+48h] BYREF

  v3 = *(_DWORD *)a2;
  v4 = (volatile signed __int64 *)((char *)this + 88);
  v5 = *((_QWORD *)this + 11);
  while ( 1 )
  {
    v21 = 0;
    v20 = 0;
    LOBYTE(v19) = 0;
    ForceFeedbackMotorResourceState::QueryState(v4, v5, v3, &v21, &v20, &v19);
    if ( !(_BYTE)v19 || v20 > v21 )
      break;
    LOBYTE(v18) = v19 - 1;
    v9 = _InterlockedCompareExchange64(
           v4,
           ForceFeedbackMotorResourceState::ModifyState(v20, v5, v3, v21 - v20, v18),
           v5);
    v8 = v5 == v9;
    v5 = v9;
    if ( v8 )
    {
      v11 = 0;
      if ( *(_DWORD *)(v10 + 20) )
      {
        while ( 1 )
        {
          v12 = *(_QWORD *)(v10 + 8 * v11 + 24);
          if ( v12 )
            break;
LABEL_12:
          if ( ++v11 >= (unsigned __int64)*(unsigned int *)(v10 + 20) )
            goto LABEL_13;
        }
        v13 = (_DWORD)v11 << 6;
        while ( 1 )
        {
          _BitScanForward64((unsigned __int64 *)&v14, v12);
          v19 = 0;
          if ( (unsigned int)(v14 + v13) >= *(_DWORD *)(v10 + 16) )
            break;
          v15 = _InterlockedCompareExchange64((volatile signed __int64 *)(v10 + 8 * v11 + 24), v12 & ~(1LL << v14), v12);
          v8 = v12 == v15;
          v12 = v15;
          if ( v8 )
          {
            v17 = (volatile signed __int32 *)(v10 + 112 + 280LL * (unsigned int)(v14 + v13));
            GameInputForceFeedbackEffect::Initialize((GameInputForceFeedbackEffect *)v17, a2);
            _InterlockedIncrement(v17 + 2);
            GameInputClient::IncrementGlobalObjectCount();
            ++dword_1800696A0;
            GameInputClientDebugRefCountCheck();
            result = 0;
            *a3 = (struct GameInputForceFeedbackEffect *)v17;
            return result;
          }
          if ( !v15 )
            goto LABEL_12;
        }
      }
LABEL_13:
      ForceFeedbackMotorResourceState::FreeEffectResources(v4, *(unsigned int *)a2);
      break;
    }
  }
  *a3 = 0;
  return 2206859270LL;
}

```

## disassembly

```asm
0x180004524  mov     [rsp-28h+arg_10], rbx
0x180004529  push    rbp
0x18000452a  push    rsi
0x18000452b  push    rdi
0x18000452c  push    r14
0x18000452e  push    r15
0x180004530  mov     rbp, rsp
0x180004533  sub     rsp, 30h
0x180004537  mov     esi, [rdx]
0x180004539  lea     rbx, [rcx+58h]
0x18000453d  mov     rdi, [rbx]
0x180004540  mov     r15, r8
0x180004543  nop
0x180004544  mov     r14, rdx
0x180004547  mov     r10, rcx
0x18000454a  jmp     short loc_18000458A
0x18000454c  movzx   ecx, [rbp+arg_8]
0x180004550  mov     r9d, [rbp+arg_18]
0x180004554  cmp     ecx, r9d
0x180004557  ja      loc_180004632
0x18000455d  dec     r11b
0x180004560  sub     r9d, ecx
0x180004563  mov     r8d, esi
0x180004566  mov     byte ptr [rsp+30h+var_10], r11b
0x18000456b  mov     rdx, rdi
0x18000456e  call    ?ModifyState@ForceFeedbackMotorResourceState@@AEBA_K_KW4GameInputForceFeedbackEffectKind@@IE@Z; ForceFeedbackMotorResourceState::ModifyState(unsigned __int64,GameInputForceFeedbackEffectKind,uint,uchar)
0x180004573  mov     r9, rax
0x180004576  nop
0x180004577  mov     rax, rdi
0x18000457a  lock cmpxchg [rbx], r9
0x18000457f  mov     rdi, rax
0x180004582  nop
0x180004583  setz    al
0x180004586  test    al, al
0x180004588  jnz     short loc_1800045C8
0x18000458a  lea     rax, [rbp+arg_0]
0x18000458e  mov     [rbp+arg_18], 0
0x180004595  mov     [rsp+30h+var_8], rax
0x18000459a  lea     r9, [rbp+arg_18]
0x18000459e  lea     rax, [rbp+arg_8]
0x1800045a2  mov     [rbp+arg_8], 0
0x1800045a6  mov     r8d, esi
0x1800045a9  mov     [rsp+30h+var_10], rax
0x1800045ae  mov     rdx, rdi
0x1800045b1  mov     byte ptr [rbp+arg_0], 0
0x1800045b5  mov     rcx, rbx
0x1800045b8  call    ?QueryState@ForceFeedbackMotorResourceState@@AEBAX_KW4GameInputForceFeedbackEffectKind@@AEAIAEAE3@Z; ForceFeedbackMotorResourceState::QueryState(unsigned __int64,GameInputForceFeedbackEffectKind,uint &,uchar &,uchar &)
0x1800045bd  mov     r11b, byte ptr [rbp+arg_0]
0x1800045c1  test    r11b, r11b
0x1800045c4  jnz     short loc_18000454C
0x1800045c6  jmp     short loc_180004632
0x1800045c8  xor     edx, edx
0x1800045ca  cmp     [r10+14h], edx
0x1800045ce  jbe     short loc_180004627
0x1800045d0  mov     r8, [r10+rdx*8+18h]
0x1800045d5  nop
0x1800045d6  test    r8, r8
0x1800045d9  jz      short loc_18000461B
0x1800045db  mov     r9d, edx
0x1800045de  shl     r9d, 6
0x1800045e2  bsf     rcx, r8
0x1800045e6  mov     [rbp+arg_0], 0
0x1800045ed  mov     eax, ecx
0x1800045ef  lea     r11d, [rcx+r9]
0x1800045f3  cmp     r11d, [r10+10h]
0x1800045f7  jnb     short loc_180004627
0x1800045f9  mov     rcx, r8
0x1800045fc  nop
0x1800045fd  btr     rcx, rax
0x180004601  mov     rax, r8
0x180004604  lock cmpxchg [r10+rdx*8+18h], rcx
0x18000460b  mov     r8, rax
0x18000460e  nop
0x18000460f  setz    al
0x180004612  test    al, al
0x180004614  jnz     short loc_180004650
0x180004616  test    r8, r8
0x180004619  jnz     short loc_1800045E2
0x18000461b  mov     eax, [r10+14h]
0x18000461f  inc     rdx
0x180004622  cmp     rdx, rax
0x180004625  jb      short loc_1800045D0
0x180004627  mov     edx, [r14]
0x18000462a  mov     rcx, rbx
0x18000462d  call    ?FreeEffectResources@ForceFeedbackMotorResourceState@@QEAAXW4GameInputForceFeedbackEffectKind@@@Z; ForceFeedbackMotorResourceState::FreeEffectResources(GameInputForceFeedbackEffectKind)
0x180004632  mov     qword ptr [r15], 0
0x180004639  mov     eax, 838A0006h
0x18000463e  mov     rbx, [rsp+30h+arg_10]
0x180004643  add     rsp, 30h
0x180004647  pop     r15
0x180004649  pop     r14
0x18000464b  pop     rdi
0x18000464c  pop     rsi
0x18000464d  pop     rbp
0x18000464e  retn
0x180004650  mov     eax, r11d
0x180004653  add     r10, 70h ; 'p'
0x180004657  imul    rbx, rax, 118h
0x18000465e  mov     rdx, r14; struct GameInputForceFeedbackParams *
0x180004661  add     rbx, r10
0x180004664  mov     rcx, rbx; this
0x180004667  call    ?Initialize@GameInputForceFeedbackEffect@@QEAAXAEBUGameInputForceFeedbackParams@@@Z; GameInputForceFeedbackEffect::Initialize(GameInputForceFeedbackParams const &)
0x18000466c  nop
0x18000466d  lock inc dword ptr [rbx+8]
0x180004671  nop
0x180004672  call    ?IncrementGlobalObjectCount@GameInputClient@@SAXXZ; GameInputClient::IncrementGlobalObjectCount(void)
0x180004677  inc     cs:dword_1800696A0
0x18000467d  call    GameInputClientDebugRefCountCheck
0x180004682  xor     eax, eax
0x180004684  mov     [r15], rbx
0x180004687  jmp     short loc_18000463E
```
