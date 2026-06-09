# GameInputServer::UpdateSystemButtonState(void)

- ea: `0x180042758`
- end: `0x18004291e`
- name: `?UpdateSystemButtonState@GameInputServer@@AEAAXXZ`
- size: `454`
- prototype: `void __fastcall(GameInputServer *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18003ee94`
- `0x180042b60`

## callees

- `0x18000d658`
- `0x18003b79c`
- `0x180040f70`
- `0x1800412d8`
- `0x180042758`
- `0x180042fd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042805`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042805`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180042912`

## pseudocode

```c
void __fastcall GameInputServer::UpdateSystemButtonState(RTL_SRWLOCK *this, __int64 a2)
{
  RTL_SRWLOCK *v3; // r12
  RTL_SRWLOCK *Ptr; // rdx
  RTL_SRWLOCK *v5; // r15
  bool v6; // bl
  GameInputServer *i; // rcx
  GameInputServer *v8; // rdx
  GameInputServer *v9; // rdx
  RTL_SRWLOCK *j; // rbx
  __int64 *k; // rdi
  unsigned int FocusPolicy; // ebp
  __int64 *m; // rcx
  int v14; // r14d
  int v15; // ebp
  unsigned int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // [rsp+60h] [rbp+8h]

  v3 = this + 7;
  v18 = GameInputCurrentTime(this, a2);
  Ptr = (RTL_SRWLOCK *)v3->Ptr;
  v5 = 0;
  while ( Ptr != v3 )
  {
    if ( LODWORD(Ptr[11].Ptr) == LODWORD(this[16].Ptr) )
    {
      v5 = Ptr;
      break;
    }
    Ptr = (RTL_SRWLOCK *)Ptr->Ptr;
  }
  v6 = 0;
  if ( (unsigned int)Feature_52580392__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( !LOBYTE(this[34].Ptr) && v5 )
    {
      v8 = (GameInputServer *)&v5[4];
      for ( i = (GameInputServer *)v5[4].Ptr; i != v8; i = *(GameInputServer **)i )
      {
        if ( (GameInputServer::BufferListEntry::GetFocusPolicy(i) & 8) != 0 )
          goto LABEL_18;
      }
    }
  }
  else if ( v5 )
  {
    v9 = (GameInputServer *)&v5[4];
    for ( i = (GameInputServer *)v5[4].Ptr; i != v9; i = *(GameInputServer **)i )
    {
      if ( (GameInputServer::BufferListEntry::GetFocusPolicy(i) & 8) != 0 )
      {
LABEL_18:
        v6 = 1;
        break;
      }
    }
  }
  GameInputServer::SetGuideLegacySuppression(i, v6);
  AcquireSRWLockExclusive(this + 6);
  for ( j = (RTL_SRWLOCK *)v3->Ptr; j != v3; j = (RTL_SRWLOCK *)j->Ptr )
  {
    if ( LODWORD(j[11].Ptr) != LODWORD(this[16].Ptr) )
    {
      for ( k = (__int64 *)j[4].Ptr; k != (__int64 *)&j[4]; k = (__int64 *)*k )
      {
        FocusPolicy = 0;
        if ( v5 )
        {
          for ( m = (__int64 *)v5[4].Ptr; m != (__int64 *)&v5[4]; m = (__int64 *)*m )
          {
            if ( m[2] == k[2] )
            {
              FocusPolicy = GameInputServer::BufferListEntry::GetFocusPolicy(m);
              break;
            }
          }
        }
        v14 = FocusPolicy & 0x20;
        if ( (unsigned int)Feature_52580392__private_IsEnabledDeviceUsageNoInline() && LOBYTE(this[34].Ptr) )
        {
          if ( LOBYTE(j[15].Ptr) )
            v15 = v14 != 0 ? 2 : 0;
          else
            v15 = v14 != 0 ? 3 : 1;
        }
        else
        {
          v15 = (v14 != 0 ? 2 : 0) | (FocusPolicy >> 3) & 1;
        }
        v16 = GameInputServer::BufferListEntry::GetFocusPolicy(k);
        GameInputServer::BufferListEntry::SendSystemButtonState(
          v17,
          v18,
          *((_DWORD *)k + 39) & ~(v15 | ((v16 & 4 | (v16 >> 1) & 8) >> 2)));
      }
      v3 = this + 7;
    }
  }
  ReleaseSRWLockExclusive(this + 6);
}

```

## disassembly

```asm
0x180042758  mov     [rsp+arg_10], rbx
0x18004275d  push    rbp
0x18004275e  push    rsi
0x18004275f  push    rdi
0x180042760  push    r12
0x180042762  push    r13
0x180042764  push    r14
0x180042766  push    r15
0x180042768  sub     rsp, 20h
0x18004276c  mov     r13, rcx
0x18004276f  call    GameInputCurrentTime
0x180042774  lea     r12, [r13+38h]
0x180042778  mov     [rsp+58h+arg_0], rax
0x18004277d  mov     rdx, [r12]
0x180042781  xor     r15d, r15d
0x180042784  cmp     rdx, r12
0x180042787  jz      short loc_18004279E
0x180042789  mov     ecx, [r13+80h]
0x180042790  nop
0x180042791  cmp     [rdx+58h], ecx
0x180042794  jz      short loc_18004279B
0x180042796  mov     rdx, [rdx]
0x180042799  jmp     short loc_180042784
0x18004279b  mov     r15, rdx
0x18004279e  xor     bl, bl
0x1800427a0  call    Feature_52580392__private_IsEnabledDeviceUsageNoInline
0x1800427a5  test    eax, eax
0x1800427a7  jz      short loc_1800427D1
0x1800427a9  cmp     [r13+110h], bl
0x1800427b0  jnz     short loc_1800427F2
0x1800427b2  test    r15, r15
0x1800427b5  jz      short loc_1800427F2
0x1800427b7  lea     rdx, [r15+20h]
0x1800427bb  mov     rcx, [rdx]
0x1800427be  cmp     rcx, rdx
0x1800427c1  jz      short loc_1800427F2
0x1800427c3  call    ?GetFocusPolicy@BufferListEntry@GameInputServer@@QEBA?AW4GameInputFocusPolicy@@XZ; GameInputServer::BufferListEntry::GetFocusPolicy(void)
0x1800427c8  test    al, 8
0x1800427ca  jnz     short loc_1800427F0
0x1800427cc  mov     rcx, [rcx]
0x1800427cf  jmp     short loc_1800427BE
0x1800427d1  test    r15, r15
0x1800427d4  jz      short loc_1800427F2
0x1800427d6  lea     rdx, [r15+20h]
0x1800427da  mov     rcx, [rdx]
0x1800427dd  cmp     rcx, rdx
0x1800427e0  jz      short loc_1800427F2
0x1800427e2  call    ?GetFocusPolicy@BufferListEntry@GameInputServer@@QEBA?AW4GameInputFocusPolicy@@XZ; GameInputServer::BufferListEntry::GetFocusPolicy(void)
0x1800427e7  test    al, 8
0x1800427e9  jnz     short loc_1800427F0
0x1800427eb  mov     rcx, [rcx]
0x1800427ee  jmp     short loc_1800427DD
0x1800427f0  mov     bl, 1
0x1800427f2  mov     dl, bl; bool
0x1800427f4  call    ?SetGuideLegacySuppression@GameInputServer@@QEAAJ_N@Z; GameInputServer::SetGuideLegacySuppression(bool)
0x1800427f9  lea     rsi, [r13+30h]
0x1800427fd  mov     rcx, rsi; SRWLock
0x180042800  mov     [rsp+58h+arg_8], rsi
0x180042805  call    cs:__imp_AcquireSRWLockExclusive
0x18004280c  nop     dword ptr [rax+rax+00h]
0x180042811  mov     rbx, [r12]
0x180042815  mov     rsi, [rsp+58h+arg_0]
0x18004281a  cmp     rbx, r12
0x18004281d  jz      loc_1800428F9
0x180042823  mov     eax, [r13+80h]
0x18004282a  nop
0x18004282b  cmp     [rbx+58h], eax
0x18004282e  jz      loc_1800428F1
0x180042834  lea     r12, [rbx+20h]
0x180042838  mov     rdi, [r12]
0x18004283c  cmp     rdi, r12
0x18004283f  jz      loc_1800428ED
0x180042845  xor     ebp, ebp
0x180042847  test    r15, r15
0x18004284a  jz      short loc_18004286E
0x18004284c  lea     rdx, [r15+20h]
0x180042850  mov     rcx, [rdx]
0x180042853  cmp     rcx, rdx
0x180042856  jz      short loc_18004286E
0x180042858  mov     rax, [rdi+10h]
0x18004285c  cmp     [rcx+10h], rax
0x180042860  jz      short loc_180042867
0x180042862  mov     rcx, [rcx]
0x180042865  jmp     short loc_180042853
0x180042867  call    ?GetFocusPolicy@BufferListEntry@GameInputServer@@QEBA?AW4GameInputFocusPolicy@@XZ; GameInputServer::BufferListEntry::GetFocusPolicy(void)
0x18004286c  mov     ebp, eax
0x18004286e  mov     r14d, ebp
0x180042871  and     r14d, 20h
0x180042875  call    Feature_52580392__private_IsEnabledDeviceUsageNoInline
0x18004287a  test    eax, eax
0x18004287c  jz      short loc_1800428A4
0x18004287e  cmp     byte ptr [r13+110h], 0
0x180042886  jz      short loc_1800428A4
0x180042888  cmp     byte ptr [rbx+78h], 0
0x18004288c  jz      short loc_180042898
0x18004288e  neg     r14d
0x180042891  sbb     ebp, ebp
0x180042893  and     ebp, 2
0x180042896  jmp     short loc_1800428B4
0x180042898  neg     r14d
0x18004289b  sbb     ebp, ebp
0x18004289d  and     ebp, 2
0x1800428a0  inc     ebp
0x1800428a2  jmp     short loc_1800428B4
0x1800428a4  shr     ebp, 3
0x1800428a7  and     ebp, 1
0x1800428aa  neg     r14d
0x1800428ad  sbb     eax, eax
0x1800428af  and     eax, 2
0x1800428b2  or      ebp, eax
0x1800428b4  mov     rcx, rdi
0x1800428b7  call    ?GetFocusPolicy@BufferListEntry@GameInputServer@@QEBA?AW4GameInputFocusPolicy@@XZ; GameInputServer::BufferListEntry::GetFocusPolicy(void)
0x1800428bc  mov     r8d, eax
0x1800428bf  mov     rdx, rsi
0x1800428c2  shr     r8d, 1
0x1800428c5  and     eax, 4
0x1800428c8  and     r8d, 8
0x1800428cc  or      r8d, eax
0x1800428cf  shr     r8d, 2
0x1800428d3  or      r8d, ebp
0x1800428d6  not     r8d
0x1800428d9  and     r8d, [rdi+9Ch]
0x1800428e0  call    ?SendSystemButtonState@BufferListEntry@GameInputServer@@QEAAX_KW4GameInputSystemButtons@@@Z; GameInputServer::BufferListEntry::SendSystemButtonState(unsigned __int64,GameInputSystemButtons)
0x1800428e5  mov     rdi, [rdi]
0x1800428e8  jmp     loc_18004283C
0x1800428ed  lea     r12, [r13+38h]
0x1800428f1  mov     rbx, [rbx]
0x1800428f4  jmp     loc_18004281A
0x1800428f9  mov     rcx, [rsp+58h+arg_8]
0x1800428fe  mov     rbx, [rsp+58h+arg_10]
0x180042903  add     rsp, 20h
0x180042907  pop     r15
0x180042909  pop     r14
0x18004290b  pop     r13
0x18004290d  pop     r12
0x18004290f  pop     rdi
0x180042910  pop     rsi
0x180042911  pop     rbp
0x180042912  jmp     cs:__imp_ReleaseSRWLockExclusive
```
