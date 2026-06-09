# PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodic::Get(_TASK_TRIGGER *)

- ea: `0x18001c650`
- end: `0x18001c71b`
- name: `?Get@TriggerPeriodic@PRIVATE_NAMESPACE_Triggers_H@@UEAAJPEAU_TASK_TRIGGER@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodic *__hidden this, struct _TASK_TRIGGER *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18001c280`
- `0x18001c650`
- `0x180022010`

## import_xrefs

- `msvcrt!malloc` at `0x18001c67d`
- `msvcrt!malloc` at `0x18001c67d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c6d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c6d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c6fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c6fb`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodic::Get(
        PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodic *this,
        struct _TASK_TRIGGER *a2)
{
  int v4; // esi
  struct _TASK_TRIGGER_WNFSTATE **v5; // rdi
  __int64 v6; // rcx
  __int128 v8; // [rsp+20h] [rbp-38h] BYREF

  if ( a2 )
  {
    v8 = 0;
    v5 = (struct _TASK_TRIGGER_WNFSTATE **)malloc(0x18u);
    if ( v5 )
    {
      *(_OWORD *)v5 = 0;
      v5[2] = 0;
      v4 = 0;
      v6 = *((_QWORD *)this + 51);
      if ( !v6 || (v4 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v6 + 24LL))(v6, &v8), v4 >= 0) )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)this + 3);
        *(_OWORD *)v5 = *(_OWORD *)((char *)this + 744);
        v5[2] = (struct _TASK_TRIGGER_WNFSTATE *)*((_QWORD *)this + 95);
        v5[2] = (struct _TASK_TRIGGER_WNFSTATE *)*((_QWORD *)&v8 + 1);
        LeaveCriticalSection((LPCRITICAL_SECTION)this + 3);
        *(_DWORD *)&a2->cbTriggerSize = *((_DWORD *)this + 40);
        *(_QWORD *)&a2->wBeginDay = v5;
        return (unsigned int)v4;
      }
    }
    else
    {
      v4 = -2147024882;
    }
    FreePeriodicTrigger(v5);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001c650  push    rbx
0x18001c652  push    rbp
0x18001c653  push    rsi
0x18001c654  push    rdi
0x18001c655  push    r14
0x18001c657  sub     rsp, 30h
0x18001c65b  mov     r14, rdx
0x18001c65e  mov     rbp, rcx
0x18001c661  test    rdx, rdx
0x18001c664  jnz     short loc_18001C670
0x18001c666  mov     esi, 80004003h
0x18001c66b  jmp     loc_18001C70E
0x18001c670  xorps   xmm0, xmm0
0x18001c673  mov     ecx, 18h; Size
0x18001c678  movups  [rsp+58h+var_38], xmm0
0x18001c67d  call    cs:__imp_malloc
0x18001c683  mov     rdi, rax
0x18001c686  test    rax, rax
0x18001c689  jnz     short loc_18001C692
0x18001c68b  mov     esi, 8007000Eh
0x18001c690  jmp     short loc_18001C6C3
0x18001c692  xor     eax, eax
0x18001c694  xorps   xmm0, xmm0
0x18001c697  movups  xmmword ptr [rdi], xmm0
0x18001c69a  mov     [rdi+10h], rax
0x18001c69e  xor     esi, esi
0x18001c6a0  mov     rcx, [rbp+198h]
0x18001c6a7  test    rcx, rcx
0x18001c6aa  jz      short loc_18001C6CD
0x18001c6ac  mov     rax, [rcx]
0x18001c6af  lea     rdx, [rsp+58h+var_38]
0x18001c6b4  mov     rax, [rax+18h]
0x18001c6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6bd  mov     esi, eax
0x18001c6bf  test    eax, eax
0x18001c6c1  jns     short loc_18001C6CD
0x18001c6c3  mov     rcx, rdi; Block
0x18001c6c6  call    ?FreePeriodicTrigger@@YAXPEAU_TASK_TRIGGER_PERIODIC@@@Z; FreePeriodicTrigger(_TASK_TRIGGER_PERIODIC *)
0x18001c6cb  jmp     short loc_18001C70E
0x18001c6cd  lea     rcx, [rbp+78h]; lpCriticalSection
0x18001c6d1  call    cs:__imp_EnterCriticalSection
0x18001c6d7  movups  xmm0, xmmword ptr [rbp+2E8h]
0x18001c6de  lea     rcx, [rbp+78h]; lpCriticalSection
0x18001c6e2  movups  xmmword ptr [rdi], xmm0
0x18001c6e5  movsd   xmm1, qword ptr [rbp+2F8h]
0x18001c6ed  movsd   qword ptr [rdi+10h], xmm1
0x18001c6f2  mov     rax, qword ptr [rsp+58h+var_38+8]
0x18001c6f7  mov     [rdi+10h], rax
0x18001c6fb  call    cs:__imp_LeaveCriticalSection
0x18001c701  mov     eax, [rbp+0A0h]
0x18001c707  mov     [r14], eax
0x18001c70a  mov     [r14+8], rdi
0x18001c70e  mov     eax, esi
0x18001c710  add     rsp, 30h
0x18001c714  pop     r14
0x18001c716  pop     rdi
0x18001c717  pop     rsi
0x18001c718  pop     rbp
0x18001c719  pop     rbx
0x18001c71a  retn
```
