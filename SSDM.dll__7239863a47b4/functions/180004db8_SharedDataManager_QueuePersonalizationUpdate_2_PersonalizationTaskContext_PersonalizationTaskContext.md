# _SharedDataManager::QueuePersonalizationUpdate_::_2_::PersonalizationTaskContext::_PersonalizationTaskContext

- ea: `0x180004db8`
- end: `0x180004e2c`
- name: `_SharedDataManager::QueuePersonalizationUpdate_::_2_::PersonalizationTaskContext::_PersonalizationTaskContext`
- size: `116`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18000493c`
- `0x1800054f8`

## callees

- `0x180004c60`
- `0x180004db8`
- `0x180010010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004e1a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004e1a`

## pseudocode

```c
void __fastcall SharedDataManager::QueuePersonalizationUpdate_::_2_::PersonalizationTaskContext::_PersonalizationTaskContext(
        __int64 a1)
{
  volatile signed __int32 *v2; // rbx
  void *v3; // rbx

  v2 = *(volatile signed __int32 **)(a1 + 24);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  v3 = *(void **)(a1 + 8);
  if ( v3 )
  {
    HrtfPersonalizationParams::~HrtfPersonalizationParams(*(HrtfPersonalizationParams **)(a1 + 8));
    operator delete(v3);
  }
}

```

## disassembly

```asm
0x180004db8  mov     [rsp+arg_0], rbx
0x180004dbd  push    rdi
0x180004dbe  sub     rsp, 20h
0x180004dc2  mov     rdi, rcx
0x180004dc5  mov     rbx, [rcx+18h]
0x180004dc9  test    rbx, rbx
0x180004dcc  jz      short loc_180004E06
0x180004dce  or      eax, 0FFFFFFFFh
0x180004dd1  lock xadd [rbx+8], eax
0x180004dd6  cmp     eax, 1
0x180004dd9  jnz     short loc_180004E06
0x180004ddb  mov     rax, [rbx]
0x180004dde  mov     rcx, rbx
0x180004de1  mov     rax, [rax]
0x180004de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004de9  or      eax, 0FFFFFFFFh
0x180004dec  lock xadd [rbx+0Ch], eax
0x180004df1  cmp     eax, 1
0x180004df4  jnz     short loc_180004E06
0x180004df6  mov     rax, [rbx]
0x180004df9  mov     rcx, rbx
0x180004dfc  mov     rax, [rax+8]
0x180004e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e05  nop
0x180004e06  mov     rbx, [rdi+8]
0x180004e0a  test    rbx, rbx
0x180004e0d  jz      short loc_180004E21
0x180004e0f  mov     rcx, rbx; this
0x180004e12  call    ??1HrtfPersonalizationParams@@QEAA@XZ; HrtfPersonalizationParams::~HrtfPersonalizationParams(void)
0x180004e17  mov     rcx, rbx
0x180004e1a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004e20  nop
0x180004e21  mov     rbx, [rsp+28h+arg_0]
0x180004e26  add     rsp, 20h
0x180004e2a  pop     rdi
0x180004e2b  retn
```
