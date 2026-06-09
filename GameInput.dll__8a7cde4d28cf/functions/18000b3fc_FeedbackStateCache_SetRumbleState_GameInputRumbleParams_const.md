# FeedbackStateCache::SetRumbleState(GameInputRumbleParams const *)

- ea: `0x18000b3fc`
- end: `0x18000b577`
- name: `?SetRumbleState@FeedbackStateCache@@QEAAXPEBUGameInputRumbleParams@@@Z`
- size: `379`
- prototype: `void __fastcall(FeedbackStateCache *__hidden this, const struct GameInputRumbleParams *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000b580`

## callees

- `0x1800069a4`
- `0x18000a7a0`
- `0x18000b3fc`
- `0x18002388c`
- `0x18002391c`
- `0x18004d010`

## pseudocode

```c
void __fastcall FeedbackStateCache::SetRumbleState(FeedbackStateCache *this, const struct GameInputRumbleParams *a2)
{
  volatile signed __int64 *v4; // r14
  __int64 v5; // rcx
  __int64 *CurrentBuffer; // rax
  __int64 v7; // rbp
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rbx
  bool v13; // di
  volatile signed __int64 *v14; // rcx
  int v15; // edx
  unsigned __int64 v16; // [rsp+20h] [rbp-38h] BYREF
  SharedBuffer *v17[2]; // [rsp+28h] [rbp-30h] BYREF

  if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 32LL) + 108LL) )
  {
    v16 = 0;
    v4 = (volatile signed __int64 *)((char *)this + 24);
    if ( (unsigned int)VersionedDataGuard::BeginUpdate((volatile signed __int64 *)this + 3, a2 != 0, &v16) != 1 )
    {
      if ( a2 )
        *(_OWORD *)v17 = *(_OWORD *)a2;
      else
        *(_OWORD *)v17 = 0;
      v5 = *((_QWORD *)this + 2);
      *((_OWORD *)this + 2) = *(_OWORD *)v17;
      CurrentBuffer = (__int64 *)GameInputDevice::GetCurrentBuffer(v5, v17);
      v7 = *CurrentBuffer;
      *CurrentBuffer = 0;
      if ( v17[0] )
        SharedBuffer::ReleaseReference(v17[0]);
      if ( v7 )
      {
        v8 = *(_QWORD *)(v7 + 80);
        if ( v8 )
        {
          v9 = *(unsigned int *)(v8 + 4);
          v10 = v9 + v8;
          v11 = -v9;
          v12 = v10 & -(__int64)(v11 != 0);
          if ( v12 )
          {
            v13 = 0;
            v14 = (volatile signed __int64 *)(v10 & -(__int64)(v11 != 0));
            if ( a2 )
            {
              v15 = VersionedDataGuard::BeginUpdateToVersion(v14, 1u, v16);
              if ( !v15 )
              {
                *(_OWORD *)(v12 + 8) = *(_OWORD *)a2;
                _m_prefetchw((const void *)v12);
                v13 = (_InterlockedAnd64((volatile signed __int64 *)v12, 0xFFFFFFFFFFFFFFFDuLL) & 1) == 0;
              }
            }
            else
            {
              v15 = VersionedDataGuard::BeginUpdateToVersion(v14, 0, v16);
              if ( !v15 )
              {
                _m_prefetchw((const void *)v12);
                v13 = (_InterlockedAnd64((volatile signed __int64 *)v12, 0xFFFFFFFFFFFFFFFDuLL) & 1) == 0;
              }
            }
            if ( !v15 && v13 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v7 + 104) + 72LL))(*(_QWORD *)(v7 + 104));
          }
        }
      }
      _InterlockedAnd64(v4, 0xFFFFFFFFFFFFFFFDuLL);
      if ( v7 )
        SharedBuffer::ReleaseReference((SharedBuffer *)v7);
    }
  }
}

```

## disassembly

```asm
0x18000b3fc  mov     r11, rsp
0x18000b3ff  mov     [r11+10h], rbx
0x18000b403  mov     [r11+18h], rbp
0x18000b407  push    rsi
0x18000b408  push    rdi
0x18000b409  push    r14
0x18000b40b  sub     rsp, 40h
0x18000b40f  mov     rax, [rcx+10h]
0x18000b413  mov     rsi, rdx
0x18000b416  mov     rbx, rcx
0x18000b419  mov     r8, [rax+20h]
0x18000b41d  cmp     dword ptr [r8+6Ch], 0
0x18000b422  jz      loc_18000B563
0x18000b428  test    rdx, rdx
0x18000b42b  mov     qword ptr [r11-38h], 0
0x18000b433  lea     r14, [rcx+18h]
0x18000b437  setnz   dl
0x18000b43a  lea     r8, [r11-38h]
0x18000b43e  mov     rcx, r14
0x18000b441  call    ?BeginUpdate@VersionedDataGuard@@QEAA?AW4VersionedDataStatus@@_NAEA_K@Z; VersionedDataGuard::BeginUpdate(bool,unsigned __int64 &)
0x18000b446  cmp     eax, 1
0x18000b449  jz      loc_18000B563
0x18000b44f  lea     rax, [rsp+58h+var_30]
0x18000b454  test    rsi, rsi
0x18000b457  jz      short loc_18000B464
0x18000b459  movups  xmm0, xmmword ptr [rsi]
0x18000b45c  movdqu  xmmword ptr [rsp+58h+var_30], xmm0
0x18000b462  jmp     short loc_18000B46C
0x18000b464  xorps   xmm0, xmm0
0x18000b467  movups  xmmword ptr [rsp+58h+var_30], xmm0
0x18000b46c  movups  xmm0, xmmword ptr [rax]
0x18000b46f  mov     rcx, [rbx+10h]
0x18000b473  lea     rdx, [rsp+58h+var_30]
0x18000b478  movdqu  xmmword ptr [rbx+20h], xmm0
0x18000b47d  call    ?GetCurrentBuffer@GameInputDevice@@QEBA?AVSharedBufferPtr@@XZ; GameInputDevice::GetCurrentBuffer(void)
0x18000b482  mov     rbp, [rax]
0x18000b485  mov     qword ptr [rax], 0
0x18000b48c  mov     rcx, [rsp+58h+var_30]; this
0x18000b491  test    rcx, rcx
0x18000b494  jz      short loc_18000B49B
0x18000b496  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x18000b49b  test    rbp, rbp
0x18000b49e  jz      loc_18000B54F
0x18000b4a4  mov     rcx, [rbp+50h]
0x18000b4a8  test    rcx, rcx
0x18000b4ab  jz      loc_18000B54F
0x18000b4b1  mov     eax, [rcx+4]
0x18000b4b4  add     rcx, rax
0x18000b4b7  neg     rax
0x18000b4ba  sbb     rbx, rbx
0x18000b4bd  and     rbx, rcx
0x18000b4c0  jz      loc_18000B54F
0x18000b4c6  mov     r8, [rsp+58h+var_38]
0x18000b4cb  xor     dil, dil
0x18000b4ce  mov     rcx, rbx
0x18000b4d1  test    rsi, rsi
0x18000b4d4  jz      short loc_18000B50C
0x18000b4d6  mov     dl, 1
0x18000b4d8  call    ?BeginUpdateToVersion@VersionedDataGuard@@QEAA?AW4VersionedDataStatus@@_N_K@Z; VersionedDataGuard::BeginUpdateToVersion(bool,unsigned __int64)
0x18000b4dd  mov     edx, eax
0x18000b4df  test    eax, eax
0x18000b4e1  jnz     short loc_18000B536
0x18000b4e3  movups  xmm0, xmmword ptr [rsi]
0x18000b4e6  movdqu  xmmword ptr [rbx+8], xmm0
0x18000b4eb  nop
0x18000b4ec  prefetchw byte ptr [rbx]
0x18000b4ef  mov     rax, [rbx]
0x18000b4f2  mov     rcx, rax
0x18000b4f5  and     rcx, 0FFFFFFFFFFFFFFFDh
0x18000b4f9  lock cmpxchg [rbx], rcx
0x18000b4fe  jnz     short loc_18000B4F2
0x18000b500  mov     rdi, rax
0x18000b503  not     dil
0x18000b506  and     dil, 1
0x18000b50a  jmp     short loc_18000B535
0x18000b50c  xor     edx, edx
0x18000b50e  call    ?BeginUpdateToVersion@VersionedDataGuard@@QEAA?AW4VersionedDataStatus@@_N_K@Z; VersionedDataGuard::BeginUpdateToVersion(bool,unsigned __int64)
0x18000b513  mov     edx, eax
0x18000b515  test    eax, eax
0x18000b517  jnz     short loc_18000B536
0x18000b519  nop
0x18000b51a  prefetchw byte ptr [rbx]
0x18000b51d  mov     rax, [rbx]
0x18000b520  mov     rcx, rax
0x18000b523  and     rcx, 0FFFFFFFFFFFFFFFDh
0x18000b527  lock cmpxchg [rbx], rcx
0x18000b52c  jnz     short loc_18000B520
0x18000b52e  not     al
0x18000b530  and     al, 1
0x18000b532  mov     dil, al
0x18000b535  nop
0x18000b536  test    edx, edx
0x18000b538  jnz     short loc_18000B54F
0x18000b53a  test    dil, dil
0x18000b53d  jz      short loc_18000B54F
0x18000b53f  mov     rcx, [rbp+68h]
0x18000b543  mov     rax, [rcx]
0x18000b546  mov     rax, [rax+48h]
0x18000b54a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b54f  nop
0x18000b550  lock and qword ptr [r14], 0FFFFFFFFFFFFFFFDh
0x18000b555  nop
0x18000b556  test    rbp, rbp
0x18000b559  jz      short loc_18000B563
0x18000b55b  mov     rcx, rbp; this
0x18000b55e  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x18000b563  mov     rbx, [rsp+58h+arg_8]
0x18000b568  mov     rbp, [rsp+58h+arg_10]
0x18000b56d  add     rsp, 40h
0x18000b571  pop     r14
0x18000b573  pop     rdi
0x18000b574  pop     rsi
0x18000b575  retn
```
