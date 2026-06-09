# GipEquationManager::UpdateDevice(void)

- ea: `0x18001f4d0`
- end: `0x18001f5f0`
- name: `?UpdateDevice@GipEquationManager@@UEAA_KXZ`
- size: `288`
- prototype: `unsigned __int64 __fastcall(GipEquationManager *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000d658`
- `0x180011c7c`
- `0x180011f48`
- `0x1800148d0`
- `0x18001f4d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f5d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f5d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f4f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f4f6`

## pseudocode

```c
unsigned __int64 __fastcall GipEquationManager::UpdateDevice(GipEquationManager *this, __int64 a2)
{
  EquationManager *v3; // r15
  unsigned __int64 v4; // r14
  unsigned __int64 v5; // rbp
  __int64 i; // rdx
  __int64 v7; // rcx
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // rdi

  v3 = (GipEquationManager *)((char *)this + 8);
  v4 = GameInputCurrentTime(this, a2);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 4416));
  if ( *((_BYTE *)this + 4408)
    && (int)EquationManager::CommitVariablesToDevice(v3) >= 0
    && (int)EquationManager::CommitEquationStatesToDevice(v3, v4) >= 0 )
  {
    *((_BYTE *)this + 4408) = 0;
  }
  v5 = -1;
  for ( i = 0; i != 16; ++i )
  {
    v7 = *((_QWORD *)v3 + 2 * i + 518);
    if ( v7 )
    {
      v8 = *(_QWORD *)(v7 + 104);
      if ( v8 != -1 && (*(_DWORD *)(v7 + 88) == 1 || *(_DWORD *)(v7 + 88) == 4) )
        v9 = v8 < ~*(_QWORD *)(v7 + 80) ? *(_QWORD *)(v7 + 80) + v8 : -1LL;
      else
        v9 = 0;
      if ( v4 < v9 && v5 > v9 )
        v5 = v9;
    }
  }
  v10 = *((_QWORD *)this + 560) + 200000LL;
  if ( v4 >= v10 && (int)EquationManager::GetAllEquationsStatesFromDevice(v3) >= 0 )
  {
    *((_QWORD *)this + 560) = v4;
    v10 = v4 + 200000;
  }
  if ( v5 > v10 )
    v5 = v10;
  v11 = 0;
  if ( !*((_BYTE *)this + 4408) )
    v11 = v5;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 4416));
  return v11;
}

```

## disassembly

```asm
0x18001f4d0  push    rbx
0x18001f4d2  push    rbp
0x18001f4d3  push    rsi
0x18001f4d4  push    rdi
0x18001f4d5  push    r14
0x18001f4d7  push    r15
0x18001f4d9  sub     rsp, 28h
0x18001f4dd  mov     rsi, rcx
0x18001f4e0  lea     r15, [rcx+8]
0x18001f4e4  call    GameInputCurrentTime
0x18001f4e9  lea     rbx, [rsi+1140h]
0x18001f4f0  mov     r14, rax
0x18001f4f3  mov     rcx, rbx; lpCriticalSection
0x18001f4f6  call    cs:__imp_EnterCriticalSection
0x18001f4fd  nop     dword ptr [rax+rax+00h]
0x18001f502  cmp     byte ptr [rsi+1138h], 0
0x18001f509  jz      short loc_18001F52D
0x18001f50b  mov     rcx, r15; this
0x18001f50e  call    ?CommitVariablesToDevice@EquationManager@@AEAAJXZ; EquationManager::CommitVariablesToDevice(void)
0x18001f513  test    eax, eax
0x18001f515  js      short loc_18001F52D
0x18001f517  mov     rdx, r14; unsigned __int64
0x18001f51a  mov     rcx, r15; this
0x18001f51d  call    ?CommitEquationStatesToDevice@EquationManager@@AEAAJ_K@Z; EquationManager::CommitEquationStatesToDevice(unsigned __int64)
0x18001f522  test    eax, eax
0x18001f524  js      short loc_18001F52D
0x18001f526  mov     byte ptr [rsi+1138h], 0
0x18001f52d  or      r10, 0FFFFFFFFFFFFFFFFh
0x18001f531  mov     rbp, r10
0x18001f534  xor     edx, edx
0x18001f536  lea     rax, [rdx+103h]
0x18001f53d  add     rax, rax
0x18001f540  mov     rcx, [r15+rax*8]
0x18001f544  test    rcx, rcx
0x18001f547  jz      short loc_18001F586
0x18001f549  mov     r8, [rcx+68h]
0x18001f54d  cmp     r8, r10
0x18001f550  jz      short loc_18001F578
0x18001f552  cmp     dword ptr [rcx+58h], 1
0x18001f556  jz      short loc_18001F55E
0x18001f558  cmp     dword ptr [rcx+58h], 4
0x18001f55c  jnz     short loc_18001F578
0x18001f55e  mov     r9, [rcx+50h]
0x18001f562  mov     rax, r9
0x18001f565  not     rax
0x18001f568  cmp     r8, rax
0x18001f56b  jb      short loc_18001F572
0x18001f56d  mov     rax, r10
0x18001f570  jmp     short loc_18001F57A
0x18001f572  lea     rax, [r9+r8]
0x18001f576  jmp     short loc_18001F57A
0x18001f578  xor     eax, eax
0x18001f57a  cmp     r14, rax
0x18001f57d  jnb     short loc_18001F586
0x18001f57f  cmp     rbp, rax
0x18001f582  cmova   rbp, rax
0x18001f586  inc     rdx
0x18001f589  cmp     rdx, 10h
0x18001f58d  jnz     short loc_18001F536
0x18001f58f  mov     rdi, [rsi+1180h]
0x18001f596  add     rdi, 30D40h
0x18001f59d  cmp     r14, rdi
0x18001f5a0  jb      short loc_18001F5BC
0x18001f5a2  mov     rcx, r15; this
0x18001f5a5  call    ?GetAllEquationsStatesFromDevice@EquationManager@@AEAAJXZ; EquationManager::GetAllEquationsStatesFromDevice(void)
0x18001f5aa  test    eax, eax
0x18001f5ac  js      short loc_18001F5BC
0x18001f5ae  mov     [rsi+1180h], r14
0x18001f5b5  lea     rdi, [r14+30D40h]
0x18001f5bc  cmp     rbp, rdi
0x18001f5bf  mov     rcx, rbx; lpCriticalSection
0x18001f5c2  cmova   rbp, rdi
0x18001f5c6  xor     edi, edi
0x18001f5c8  cmp     [rsi+1138h], dil
0x18001f5cf  cmovz   rdi, rbp
0x18001f5d3  call    cs:__imp_LeaveCriticalSection
0x18001f5da  nop     dword ptr [rax+rax+00h]
0x18001f5df  mov     rax, rdi
0x18001f5e2  add     rsp, 28h
0x18001f5e6  pop     r15
0x18001f5e8  pop     r14
0x18001f5ea  pop     rdi
0x18001f5eb  pop     rsi
0x18001f5ec  pop     rbp
0x18001f5ed  pop     rbx
0x18001f5ee  retn
```
