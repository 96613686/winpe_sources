# CQuery::Start(void)

- ea: `0x180003d14`
- end: `0x180003d9d`
- name: `?Start@CQuery@@QEAAJXZ`
- size: `137`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180003330`
- `0x180004440`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003d3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003d3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003d2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003d2b`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x180003d8c`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x180003d8c`

## pseudocode

```c
__int64 __fastcall CQuery::Start(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  v1 = this + 4;
  EnterCriticalSection(this + 4);
  LODWORD(this[5].DebugInfo) = 0;
  LeaveCriticalSection(v1);
  return DevCreateObjectQueryEx(
           LODWORD(this->OwningThread),
           LODWORD(this[1].SpinCount),
           HIDWORD(this[1].SpinCount),
           this[2].DebugInfo,
           this[2].LockCount,
           this[2].OwningThread,
           this[2].LockSemaphore,
           this[2].SpinCount,
           CQuery::Callback,
           this,
           &this[1].LockSemaphore);
}

```

## disassembly

```asm
0x180003d14  mov     [rsp+arg_0], rbx
0x180003d19  push    rdi
0x180003d1a  sub     rsp, 60h
0x180003d1e  lea     rbx, [rcx+0A0h]
0x180003d25  mov     rdi, rcx
0x180003d28  mov     rcx, rbx; lpCriticalSection
0x180003d2b  call    cs:__imp_EnterCriticalSection
0x180003d31  mov     rcx, rbx; lpCriticalSection
0x180003d34  mov     dword ptr [rdi+0C8h], 0
0x180003d3e  call    cs:__imp_LeaveCriticalSection
0x180003d44  mov     r9, [rdi+50h]
0x180003d48  lea     rax, [rdi+40h]
0x180003d4c  mov     r8d, [rdi+4Ch]
0x180003d50  mov     edx, [rdi+48h]
0x180003d53  mov     ecx, [rdi+10h]
0x180003d56  mov     [rsp+68h+var_18], rax
0x180003d5b  lea     rax, ?Callback@CQuery@@KAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; CQuery::Callback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x180003d62  mov     [rsp+68h+var_20], rdi
0x180003d67  mov     [rsp+68h+var_28], rax
0x180003d6c  mov     rax, [rdi+70h]
0x180003d70  mov     [rsp+68h+var_30], rax
0x180003d75  mov     eax, [rdi+68h]
0x180003d78  mov     [rsp+68h+var_38], eax
0x180003d7c  mov     rax, [rdi+60h]
0x180003d80  mov     [rsp+68h+var_40], rax
0x180003d85  mov     eax, [rdi+58h]
0x180003d88  mov     [rsp+68h+var_48], eax
0x180003d8c  call    cs:__imp_DevCreateObjectQueryEx
0x180003d92  mov     rbx, [rsp+68h+arg_0]
0x180003d97  add     rsp, 60h
0x180003d9b  pop     rdi
0x180003d9c  retn
```
