# PRIVATE_NAMESPACE_Triggers_H::TriggerCEAggregate::Get(_TASK_TRIGGER *)

- ea: `0x18001c4f0`
- end: `0x18001c647`
- name: `?Get@TriggerCEAggregate@PRIVATE_NAMESPACE_Triggers_H@@EEAAJPEAU_TASK_TRIGGER@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerCEAggregate *__hidden this, struct _TASK_TRIGGER *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18001c20c`
- `0x18001c4f0`
- `0x180020c02`
- `0x180022010`

## import_xrefs

- `msvcrt!malloc` at `0x18001c513`
- `msvcrt!malloc` at `0x18001c545`
- `msvcrt!malloc` at `0x18001c594`
- `msvcrt!malloc` at `0x18001c513`
- `msvcrt!malloc` at `0x18001c545`
- `msvcrt!malloc` at `0x18001c594`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c5c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c5c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c605`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c610`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c605`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c610`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerCEAggregate::Get(
        struct _RTL_CRITICAL_SECTION *this,
        struct _TASK_TRIGGER *a2)
{
  struct _TASK_TRIGGER_CEAGGREGATE *v4; // rax
  struct _TASK_TRIGGER_CEAGGREGATE *v5; // rdi
  int v6; // ebx
  _OWORD *v7; // rax
  HANDLE LockSemaphore; // rcx
  unsigned int SpinCount; // eax
  void *v10; // rax
  struct _RTL_CRITICAL_SECTION *v11; // rbp
  struct _RTL_CRITICAL_SECTION *v12; // r12
  __int64 v13; // rsi
  _QWORD *p_Type; // r15
  _QWORD *v15; // rcx
  __int64 v16; // rax

  if ( a2 )
  {
    v4 = (struct _TASK_TRIGGER_CEAGGREGATE *)malloc(0x18u);
    v5 = v4;
    if ( v4 )
    {
      *(_OWORD *)v4 = 0;
      *((_QWORD *)v4 + 2) = 0;
      *((_DWORD *)v4 + 2) = this[4].SpinCount;
      v7 = malloc(0x10u);
      *(_QWORD *)v5 = v7;
      if ( v7 )
      {
        v6 = 0;
        *v7 = 0;
        LockSemaphore = this[5].LockSemaphore;
        if ( LockSemaphore )
        {
          v6 = (*(__int64 (__fastcall **)(HANDLE, _QWORD))(*(_QWORD *)LockSemaphore + 24LL))(
                 LockSemaphore,
                 *(_QWORD *)v5);
          if ( v6 < 0 )
            goto LABEL_15;
        }
        SpinCount = this[5].SpinCount;
        if ( !SpinCount )
        {
LABEL_16:
          *(_DWORD *)&a2->cbTriggerSize = 4;
          *(_QWORD *)&a2->wBeginDay = v5;
          return (unsigned int)v6;
        }
        v10 = malloc(16LL * SpinCount);
        *((_QWORD *)v5 + 2) = v10;
        if ( v10 )
        {
          memset_0(v10, 0, 16LL * LODWORD(this[5].SpinCount));
          v11 = this + 3;
          EnterCriticalSection(this + 3);
          v12 = this + 6;
          v13 = *((_QWORD *)v5 + 2);
          p_Type = &v12->DebugInfo->Type;
          while ( p_Type != (_QWORD *)v12 )
          {
            v15 = p_Type - 1;
            v16 = *(p_Type - 1);
            p_Type = (_QWORD *)*p_Type;
            v6 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(v16 + 24))(v15, v13);
            if ( v6 < 0 )
            {
              LeaveCriticalSection(v11);
              goto LABEL_15;
            }
            v13 += 16;
            ++*((_DWORD *)v5 + 3);
          }
          LeaveCriticalSection(v11);
          goto LABEL_16;
        }
      }
    }
    v6 = -2147024882;
LABEL_15:
    FreeCEAggregateTrigger(v5);
    return (unsigned int)v6;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18001c4f0  push    rbx
0x18001c4f2  push    rbp
0x18001c4f3  push    rsi
0x18001c4f4  push    rdi
0x18001c4f5  push    r12
0x18001c4f7  push    r14
0x18001c4f9  push    r15
0x18001c4fb  sub     rsp, 20h
0x18001c4ff  mov     r14, rdx
0x18001c502  mov     rsi, rcx
0x18001c505  test    rdx, rdx
0x18001c508  jz      loc_18001C633
0x18001c50e  mov     ecx, 18h; Size
0x18001c513  call    cs:__imp_malloc
0x18001c519  mov     rdi, rax
0x18001c51c  test    rax, rax
0x18001c51f  jnz     short loc_18001C52B
0x18001c521  mov     ebx, 8007000Eh
0x18001c526  jmp     loc_18001C61A
0x18001c52b  xor     eax, eax
0x18001c52d  xorps   xmm0, xmm0
0x18001c530  movups  xmmword ptr [rdi], xmm0
0x18001c533  mov     [rdi+10h], rax
0x18001c537  mov     ecx, 10h; Size
0x18001c53c  mov     eax, [rsi+0C0h]
0x18001c542  mov     [rdi+8], eax
0x18001c545  call    cs:__imp_malloc
0x18001c54b  mov     [rdi], rax
0x18001c54e  test    rax, rax
0x18001c551  jz      short loc_18001C521
0x18001c553  xorps   xmm0, xmm0
0x18001c556  xor     ebx, ebx
0x18001c558  movups  xmmword ptr [rax], xmm0
0x18001c55b  mov     rcx, [rsi+0E0h]
0x18001c562  test    rcx, rcx
0x18001c565  jz      short loc_18001C580
0x18001c567  mov     rax, [rcx]
0x18001c56a  mov     rdx, [rdi]
0x18001c56d  mov     rax, [rax+18h]
0x18001c571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c576  mov     ebx, eax
0x18001c578  test    eax, eax
0x18001c57a  js      loc_18001C61A
0x18001c580  mov     eax, [rsi+0E8h]
0x18001c586  test    eax, eax
0x18001c588  jz      loc_18001C624
0x18001c58e  mov     ecx, eax
0x18001c590  shl     rcx, 4; Size
0x18001c594  call    cs:__imp_malloc
0x18001c59a  mov     [rdi+10h], rax
0x18001c59e  test    rax, rax
0x18001c5a1  jz      loc_18001C521
0x18001c5a7  mov     r8d, [rsi+0E8h]
0x18001c5ae  xor     edx, edx; Val
0x18001c5b0  shl     r8, 4; Size
0x18001c5b4  mov     rcx, rax; void *
0x18001c5b7  call    memset_0
0x18001c5bc  lea     rbp, [rsi+78h]
0x18001c5c0  mov     rcx, rbp; lpCriticalSection
0x18001c5c3  call    cs:__imp_EnterCriticalSection
0x18001c5c9  lea     r12, [rsi+0F0h]
0x18001c5d0  mov     rsi, [rdi+10h]
0x18001c5d4  mov     r15, [r12]
0x18001c5d8  cmp     r15, r12
0x18001c5db  jz      short loc_18001C60D
0x18001c5dd  lea     rcx, [r15-8]
0x18001c5e1  mov     rdx, rsi
0x18001c5e4  mov     rax, [rcx]
0x18001c5e7  mov     r15, [r15]
0x18001c5ea  mov     rax, [rax+18h]
0x18001c5ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5f3  mov     ebx, eax
0x18001c5f5  test    eax, eax
0x18001c5f7  js      short loc_18001C602
0x18001c5f9  add     rsi, 10h
0x18001c5fd  inc     dword ptr [rdi+0Ch]
0x18001c600  jmp     short loc_18001C5D8
0x18001c602  mov     rcx, rbp; lpCriticalSection
0x18001c605  call    cs:__imp_LeaveCriticalSection
0x18001c60b  jmp     short loc_18001C61A
0x18001c60d  mov     rcx, rbp; lpCriticalSection
0x18001c610  call    cs:__imp_LeaveCriticalSection
0x18001c616  test    ebx, ebx
0x18001c618  jns     short loc_18001C624
0x18001c61a  mov     rcx, rdi; Block
0x18001c61d  call    ?FreeCEAggregateTrigger@@YAXPEAU_TASK_TRIGGER_CEAGGREGATE@@@Z; FreeCEAggregateTrigger(_TASK_TRIGGER_CEAGGREGATE *)
0x18001c622  jmp     short loc_18001C62F
0x18001c624  mov     dword ptr [r14], 4
0x18001c62b  mov     [r14+8], rdi
0x18001c62f  mov     eax, ebx
0x18001c631  jmp     short loc_18001C638
0x18001c633  mov     eax, 80004003h
0x18001c638  add     rsp, 20h
0x18001c63c  pop     r15
0x18001c63e  pop     r14
0x18001c640  pop     r12
0x18001c642  pop     rdi
0x18001c643  pop     rsi
0x18001c644  pop     rbp
0x18001c645  pop     rbx
0x18001c646  retn
```
