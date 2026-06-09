# PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate::Get(_TASK_TRIGGER *)

- ea: `0x18001c310`
- end: `0x18001c44d`
- name: `?Get@TriggerAggregate@PRIVATE_NAMESPACE_Triggers_H@@EEAAJPEAU_TASK_TRIGGER@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate *__hidden this, struct _TASK_TRIGGER *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18001c0e0`
- `0x18001c310`
- `0x180020c02`
- `0x180022010`

## import_xrefs

- `msvcrt!free` at `0x18001c41c`
- `msvcrt!free` at `0x18001c425`
- `msvcrt!free` at `0x18001c41c`
- `msvcrt!free` at `0x18001c425`
- `msvcrt!malloc` at `0x18001c33b`
- `msvcrt!malloc` at `0x18001c377`
- `msvcrt!malloc` at `0x18001c33b`
- `msvcrt!malloc` at `0x18001c377`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c3a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c3a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c3e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c3e9`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate::Get(
        struct _RTL_CRITICAL_SECTION *this,
        struct _TASK_TRIGGER *a2)
{
  _OWORD *v5; // rax
  _OWORD *v6; // rbx
  int v7; // edi
  unsigned int OwningThread; // eax
  void *v9; // rax
  __int64 v10; // rbp
  PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate *DebugInfo; // r15
  char *v12; // rcx
  __int64 v13; // rax
  struct _TASK_TRIGGER *v14; // rsi
  unsigned int i; // ebp

  if ( !a2 )
    return 2147500035LL;
  v5 = malloc(0x10u);
  v6 = v5;
  if ( v5 )
  {
    v7 = 0;
    *v5 = 0;
    *(_DWORD *)v5 = this[4].SpinCount;
    OwningThread = (unsigned int)this[5].OwningThread;
    if ( OwningThread )
    {
      v9 = malloc(16LL * OwningThread);
      *((_QWORD *)v6 + 1) = v9;
      if ( !v9 )
      {
        v7 = -2147024882;
LABEL_13:
        v14 = (struct _TASK_TRIGGER *)*((_QWORD *)v6 + 1);
        if ( v14 )
        {
          for ( i = 0; i < *((_DWORD *)v6 + 1); v14 = (struct _TASK_TRIGGER *)((char *)v14 + 16) )
          {
            Trigger::Free(v14, 0);
            ++i;
          }
          free(*((void **)v6 + 1));
        }
        free(v6);
        return (unsigned int)v7;
      }
      memset_0(v9, 0, 16LL * LODWORD(this[5].OwningThread));
      EnterCriticalSection(this + 3);
      v10 = *((_QWORD *)v6 + 1);
      DebugInfo = (PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate *)this[5].DebugInfo;
      while ( DebugInfo != (PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate *)&this[5] )
      {
        v12 = (char *)DebugInfo - 8;
        v13 = *((_QWORD *)DebugInfo - 1);
        DebugInfo = *(PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate **)DebugInfo;
        v7 = (*(__int64 (__fastcall **)(char *, __int64))(v13 + 24))(v12, v10);
        if ( v7 < 0 )
          break;
        v10 += 16;
        ++*((_DWORD *)v6 + 1);
      }
      LeaveCriticalSection(this + 3);
      if ( v7 < 0 )
        goto LABEL_13;
    }
    *(_DWORD *)&a2->cbTriggerSize = this[4].DebugInfo;
    *(_QWORD *)&a2->wBeginDay = v6;
    return (unsigned int)v7;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x18001c310  push    rbx
0x18001c312  push    rbp
0x18001c313  push    rsi
0x18001c314  push    rdi
0x18001c315  push    r12
0x18001c317  push    r13
0x18001c319  push    r14
0x18001c31b  push    r15
0x18001c31d  sub     rsp, 28h
0x18001c321  mov     r14, rdx
0x18001c324  mov     rsi, rcx
0x18001c327  test    rdx, rdx
0x18001c32a  jnz     short loc_18001C336
0x18001c32c  mov     eax, 80004003h
0x18001c331  jmp     loc_18001C43C
0x18001c336  mov     ecx, 10h; Size
0x18001c33b  call    cs:__imp_malloc
0x18001c341  mov     rbx, rax
0x18001c344  test    rax, rax
0x18001c347  jnz     short loc_18001C353
0x18001c349  mov     edi, 8007000Eh
0x18001c34e  jmp     loc_18001C43A
0x18001c353  xorps   xmm0, xmm0
0x18001c356  xor     edi, edi
0x18001c358  movups  xmmword ptr [rax], xmm0
0x18001c35b  mov     eax, [rsi+0C0h]
0x18001c361  mov     [rbx], eax
0x18001c363  mov     eax, [rsi+0D8h]
0x18001c369  test    eax, eax
0x18001c36b  jz      loc_18001C42D
0x18001c371  mov     ecx, eax
0x18001c373  shl     rcx, 4; Size
0x18001c377  call    cs:__imp_malloc
0x18001c37d  mov     [rbx+8], rax
0x18001c381  test    rax, rax
0x18001c384  jnz     short loc_18001C38D
0x18001c386  mov     edi, 8007000Eh
0x18001c38b  jmp     short loc_18001C3F3
0x18001c38d  mov     r8d, [rsi+0D8h]
0x18001c394  xor     edx, edx; Val
0x18001c396  shl     r8, 4; Size
0x18001c39a  mov     rcx, rax; void *
0x18001c39d  call    memset_0
0x18001c3a2  lea     rcx, [rsi+78h]; lpCriticalSection
0x18001c3a6  call    cs:__imp_EnterCriticalSection
0x18001c3ac  mov     rbp, [rbx+8]
0x18001c3b0  lea     r12, [rsi+0C8h]
0x18001c3b7  mov     r15, [r12]
0x18001c3bb  jmp     short loc_18001C3E0
0x18001c3bd  lea     rcx, [r15-8]
0x18001c3c1  mov     rdx, rbp
0x18001c3c4  mov     rax, [rcx]
0x18001c3c7  mov     r15, [r15]
0x18001c3ca  mov     rax, [rax+18h]
0x18001c3ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3d3  mov     edi, eax
0x18001c3d5  test    eax, eax
0x18001c3d7  js      short loc_18001C3E5
0x18001c3d9  add     rbp, 10h
0x18001c3dd  inc     dword ptr [rbx+4]
0x18001c3e0  cmp     r15, r12
0x18001c3e3  jnz     short loc_18001C3BD
0x18001c3e5  lea     rcx, [rsi+78h]; lpCriticalSection
0x18001c3e9  call    cs:__imp_LeaveCriticalSection
0x18001c3ef  test    edi, edi
0x18001c3f1  jns     short loc_18001C42D
0x18001c3f3  mov     rsi, [rbx+8]
0x18001c3f7  test    rsi, rsi
0x18001c3fa  jz      short loc_18001C422
0x18001c3fc  xor     ebp, ebp
0x18001c3fe  cmp     [rbx+4], ebp
0x18001c401  jbe     short loc_18001C418
0x18001c403  xor     edx, edx; int
0x18001c405  mov     rcx, rsi; Block
0x18001c408  call    ?Free@Trigger@@SAJPEAU_TASK_TRIGGER@@H@Z; Trigger::Free(_TASK_TRIGGER *,int)
0x18001c40d  inc     ebp
0x18001c40f  add     rsi, 10h
0x18001c413  cmp     ebp, [rbx+4]
0x18001c416  jb      short loc_18001C403
0x18001c418  mov     rcx, [rbx+8]; Block
0x18001c41c  call    cs:__imp_free
0x18001c422  mov     rcx, rbx; Block
0x18001c425  call    cs:__imp_free
0x18001c42b  jmp     short loc_18001C43A
0x18001c42d  mov     eax, [rsi+0A0h]
0x18001c433  mov     [r14], eax
0x18001c436  mov     [r14+8], rbx
0x18001c43a  mov     eax, edi
0x18001c43c  add     rsp, 28h
0x18001c440  pop     r15
0x18001c442  pop     r14
0x18001c444  pop     r13
0x18001c446  pop     r12
0x18001c448  pop     rdi
0x18001c449  pop     rsi
0x18001c44a  pop     rbp
0x18001c44b  pop     rbx
0x18001c44c  retn
```
