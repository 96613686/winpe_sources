# PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicEx::Get(_TASK_TRIGGER *)

- ea: `0x18001c730`
- end: `0x18001c7fb`
- name: `?Get@TriggerPeriodicEx@PRIVATE_NAMESPACE_Triggers_H@@UEAAJPEAU_TASK_TRIGGER@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicEx *__hidden this, struct _TASK_TRIGGER *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18001c2ac`
- `0x18001c730`
- `0x180022010`

## import_xrefs

- `msvcrt!malloc` at `0x18001c75d`
- `msvcrt!malloc` at `0x18001c75d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c7b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c7b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c7db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c7db`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicEx::Get(
        PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicEx *this,
        struct _TASK_TRIGGER *a2)
{
  int v4; // esi
  struct _TASK_TRIGGER_AGGREGATE **v5; // rdi
  __int64 v6; // rcx
  __int128 v8; // [rsp+20h] [rbp-38h] BYREF

  if ( a2 )
  {
    v8 = 0;
    v5 = (struct _TASK_TRIGGER_AGGREGATE **)malloc(0x18u);
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
        v5[2] = (struct _TASK_TRIGGER_AGGREGATE *)*((_QWORD *)this + 95);
        v5[2] = (struct _TASK_TRIGGER_AGGREGATE *)*((_QWORD *)&v8 + 1);
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
    FreePeriodicTriggerEx(v5);
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
0x18001c730  push    rbx
0x18001c732  push    rbp
0x18001c733  push    rsi
0x18001c734  push    rdi
0x18001c735  push    r14
0x18001c737  sub     rsp, 30h
0x18001c73b  mov     r14, rdx
0x18001c73e  mov     rbp, rcx
0x18001c741  test    rdx, rdx
0x18001c744  jnz     short loc_18001C750
0x18001c746  mov     esi, 80004003h
0x18001c74b  jmp     loc_18001C7EE
0x18001c750  xorps   xmm0, xmm0
0x18001c753  mov     ecx, 18h; Size
0x18001c758  movups  [rsp+58h+var_38], xmm0
0x18001c75d  call    cs:__imp_malloc
0x18001c763  mov     rdi, rax
0x18001c766  test    rax, rax
0x18001c769  jnz     short loc_18001C772
0x18001c76b  mov     esi, 8007000Eh
0x18001c770  jmp     short loc_18001C7A3
0x18001c772  xor     eax, eax
0x18001c774  xorps   xmm0, xmm0
0x18001c777  movups  xmmword ptr [rdi], xmm0
0x18001c77a  mov     [rdi+10h], rax
0x18001c77e  xor     esi, esi
0x18001c780  mov     rcx, [rbp+198h]
0x18001c787  test    rcx, rcx
0x18001c78a  jz      short loc_18001C7AD
0x18001c78c  mov     rax, [rcx]
0x18001c78f  lea     rdx, [rsp+58h+var_38]
0x18001c794  mov     rax, [rax+18h]
0x18001c798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c79d  mov     esi, eax
0x18001c79f  test    eax, eax
0x18001c7a1  jns     short loc_18001C7AD
0x18001c7a3  mov     rcx, rdi; Block
0x18001c7a6  call    ?FreePeriodicTriggerEx@@YAXPEAU_TASK_TRIGGER_PERIODICEX@@@Z; FreePeriodicTriggerEx(_TASK_TRIGGER_PERIODICEX *)
0x18001c7ab  jmp     short loc_18001C7EE
0x18001c7ad  lea     rcx, [rbp+78h]; lpCriticalSection
0x18001c7b1  call    cs:__imp_EnterCriticalSection
0x18001c7b7  movups  xmm0, xmmword ptr [rbp+2E8h]
0x18001c7be  lea     rcx, [rbp+78h]; lpCriticalSection
0x18001c7c2  movups  xmmword ptr [rdi], xmm0
0x18001c7c5  movsd   xmm1, qword ptr [rbp+2F8h]
0x18001c7cd  movsd   qword ptr [rdi+10h], xmm1
0x18001c7d2  mov     rax, qword ptr [rsp+58h+var_38+8]
0x18001c7d7  mov     [rdi+10h], rax
0x18001c7db  call    cs:__imp_LeaveCriticalSection
0x18001c7e1  mov     eax, [rbp+0A0h]
0x18001c7e7  mov     [r14], eax
0x18001c7ea  mov     [r14+8], rdi
0x18001c7ee  mov     eax, esi
0x18001c7f0  add     rsp, 30h
0x18001c7f4  pop     r14
0x18001c7f6  pop     rdi
0x18001c7f7  pop     rsi
0x18001c7f8  pop     rbp
0x18001c7f9  pop     rbx
0x18001c7fa  retn
```
