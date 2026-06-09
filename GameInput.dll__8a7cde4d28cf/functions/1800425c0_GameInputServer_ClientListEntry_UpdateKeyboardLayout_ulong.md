# GameInputServer::ClientListEntry::UpdateKeyboardLayout(ulong)

- ea: `0x1800425c0`
- end: `0x180042752`
- name: `?UpdateKeyboardLayout@ClientListEntry@GameInputServer@@QEAAXK@Z`
- size: `402`
- prototype: `void __fastcall(GameInputServer::ClientListEntry *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003b3f0`
- `0x18003dc00`

## callees

- `0x18000d658`
- `0x180023e1c`
- `0x1800425c0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180042617`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180042617`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004271f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004271f`

## pseudocode

```c
void __fastcall GameInputServer::ClientListEntry::UpdateKeyboardLayout(RTL_SRWLOCK *this, __int64 a2)
{
  unsigned int v2; // ebx
  HKL v4; // rbp
  char v5; // r12
  RTL_SRWLOCK *i; // rbx
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // r14
  int v12; // r13d
  int v13; // r10d
  __int64 v14; // r8
  volatile signed __int16 *v15; // r8
  signed __int16 v16; // dx
  __int16 v17; // r9
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // [rsp+70h] [rbp+8h]

  v2 = a2;
  v21 = GameInputCurrentTime(this, a2);
  if ( qword_180069700 )
    v4 = (HKL)qword_180069700(v2);
  else
    v4 = 0;
  if ( this[14].Ptr != v4 )
  {
    v5 = 0;
    this[14].Ptr = v4;
    _mm_mfence();
    AcquireSRWLockShared(this + 3);
    for ( i = (RTL_SRWLOCK *)this[4].Ptr; i != &this[4]; i = (RTL_SRWLOCK *)i->Ptr )
    {
      v7 = ((__int64)i[7].Ptr + *((unsigned int *)i[7].Ptr + 4)) & -(__int64)(*((_DWORD *)i[7].Ptr + 4) != 0);
      v8 = *(unsigned int *)(v7 + 0x14);
      v9 = v8 + v7;
      v10 = -v8;
      v11 = v9 & -(__int64)(v10 != 0);
      if ( v11 )
      {
        v12 = *(_DWORD *)((v9 & -(__int64)(v10 != 0)) + 0xC04);
        KeyboardLookupTable::Initialize((KeyboardLookupTable *)(v9 & -(__int64)(v10 != 0)), v4);
        v13 = *(_DWORD *)(v11 + 3076);
        if ( v13 != v12 )
        {
          v14 = ((__int64)i[7].Ptr + *((unsigned int *)i[7].Ptr + 3)) & -(__int64)(*((_DWORD *)i[7].Ptr + 3) != 0);
          v15 = (volatile signed __int16 *)((*(unsigned int *)(v14 + 0xC) + v14)
                                          & -(__int64)(*(_DWORD *)(v14 + 0xC) != 0));
          if ( v15 )
          {
            v16 = *v15;
            v17 = HIBYTE(*v15);
            if ( (unsigned __int8)*v15 == 8 )
              _InterlockedCompareExchange16(v15, ((((_BYTE)v17 + 1) & 0xF8) << 8) | 7, v16);
            v18 = (unsigned __int8)v17 + (unsigned __int64)(unsigned __int8)v16;
            v19 = v18 - 8;
            if ( v18 < 8 )
              v19 = v18;
            v20 = 3 * v19;
            *(_QWORD *)&v15[4 * v20 + 4] = v21;
            *(_QWORD *)&v15[4 * v20 + 8] = v4;
            *(_DWORD *)&v15[4 * v20 + 12] = v13;
            *(_DWORD *)&v15[4 * v20 + 14] = v12;
            _InterlockedIncrement16(v15);
            v5 = 1;
          }
        }
      }
    }
    ReleaseSRWLockShared(this + 3);
    if ( v5 )
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)this[2].Ptr + 72LL))(this[2].Ptr);
  }
}

```

## disassembly

```asm
0x1800425c0  push    rbx
0x1800425c2  push    rbp
0x1800425c3  push    rsi
0x1800425c4  push    rdi
0x1800425c5  push    r12
0x1800425c7  push    r13
0x1800425c9  push    r14
0x1800425cb  push    r15
0x1800425cd  sub     rsp, 28h
0x1800425d1  mov     ebx, edx
0x1800425d3  mov     rsi, rcx
0x1800425d6  call    GameInputCurrentTime
0x1800425db  mov     [rsp+68h+arg_0], rax
0x1800425e0  mov     rax, cs:qword_180069700
0x1800425e7  test    rax, rax
0x1800425ea  jz      short loc_1800425F8
0x1800425ec  mov     ecx, ebx
0x1800425ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800425f3  mov     rbp, rax
0x1800425f6  jmp     short loc_1800425FA
0x1800425f8  xor     ebp, ebp
0x1800425fa  mov     rax, [rsi+70h]
0x1800425fe  nop
0x1800425ff  cmp     rax, rbp
0x180042602  jz      loc_180042740
0x180042608  nop
0x180042609  xor     r12b, r12b
0x18004260c  mov     [rsi+70h], rbp
0x180042610  mfence
0x180042613  lea     rcx, [rsi+18h]; SRWLock
0x180042617  call    cs:__imp_AcquireSRWLockShared
0x18004261e  nop     dword ptr [rax+rax+00h]
0x180042623  mov     rdi, [rsp+68h+arg_0]
0x180042628  lea     r15, [rsi+20h]
0x18004262c  mov     rbx, [r15]
0x18004262f  cmp     rbx, r15
0x180042632  jz      loc_18004271B
0x180042638  mov     rax, [rbx+38h]
0x18004263c  mov     ecx, [rax+10h]
0x18004263f  lea     rdx, [rcx+rax]
0x180042643  neg     rcx
0x180042646  sbb     r8, r8
0x180042649  and     r8, rdx
0x18004264c  mov     eax, [r8+14h]
0x180042650  lea     rcx, [rax+r8]
0x180042654  neg     rax
0x180042657  sbb     r14, r14
0x18004265a  and     r14, rcx
0x18004265d  jz      loc_180042713
0x180042663  mov     r13d, [r14+0C04h]
0x18004266a  mov     rdx, rbp; HKL
0x18004266d  mov     rcx, r14; this
0x180042670  call    ?Initialize@KeyboardLookupTable@@QEAAXPEAUHKL__@@@Z; KeyboardLookupTable::Initialize(HKL__ *)
0x180042675  mov     r10d, [r14+0C04h]
0x18004267c  cmp     r10d, r13d
0x18004267f  jz      loc_180042713
0x180042685  mov     rax, [rbx+38h]
0x180042689  mov     ecx, [rax+0Ch]
0x18004268c  lea     rdx, [rcx+rax]
0x180042690  neg     rcx
0x180042693  sbb     r8, r8
0x180042696  and     r8, rdx
0x180042699  mov     eax, [r8+0Ch]
0x18004269d  lea     rcx, [rax+r8]
0x1800426a1  neg     rax
0x1800426a4  sbb     r8, r8
0x1800426a7  and     r8, rcx
0x1800426aa  jz      short loc_180042713
0x1800426ac  movzx   edx, word ptr [r8]
0x1800426b0  nop
0x1800426b1  movzx   r9d, dx
0x1800426b5  shr     r9w, 8
0x1800426ba  cmp     dl, 8
0x1800426bd  jnz     short loc_1800426DB
0x1800426bf  lea     eax, [r9+1]
0x1800426c3  nop
0x1800426c4  and     al, 0F8h
0x1800426c6  movzx   ecx, al
0x1800426c9  movzx   eax, dx
0x1800426cc  shl     cx, 8
0x1800426d0  or      cx, 7
0x1800426d4  lock cmpxchg [r8], cx
0x1800426da  nop
0x1800426db  movzx   eax, r9b
0x1800426df  movzx   edx, dl
0x1800426e2  add     rdx, rax
0x1800426e5  cmp     rdx, 8
0x1800426e9  lea     rax, [rdx-8]
0x1800426ed  cmovb   rax, rdx
0x1800426f1  lea     rcx, [rax+rax*2]
0x1800426f5  mov     [r8+rcx*8+8], rdi
0x1800426fa  mov     [r8+rcx*8+10h], rbp
0x1800426ff  mov     [r8+rcx*8+18h], r10d
0x180042704  mov     [r8+rcx*8+1Ch], r13d
0x180042709  nop
0x18004270a  lock inc word ptr [r8]
0x18004270f  nop
0x180042710  mov     r12b, 1
0x180042713  mov     rbx, [rbx]
0x180042716  jmp     loc_18004262F
0x18004271b  lea     rcx, [rsi+18h]; SRWLock
0x18004271f  call    cs:__imp_ReleaseSRWLockShared
0x180042726  nop     dword ptr [rax+rax+00h]
0x18004272b  test    r12b, r12b
0x18004272e  jz      short loc_180042740
0x180042730  mov     rcx, [rsi+10h]
0x180042734  mov     rax, [rcx]
0x180042737  mov     rax, [rax+48h]
0x18004273b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042740  add     rsp, 28h
0x180042744  pop     r15
0x180042746  pop     r14
0x180042748  pop     r13
0x18004274a  pop     r12
0x18004274c  pop     rdi
0x18004274d  pop     rsi
0x18004274e  pop     rbp
0x18004274f  pop     rbx
0x180042750  retn
```
