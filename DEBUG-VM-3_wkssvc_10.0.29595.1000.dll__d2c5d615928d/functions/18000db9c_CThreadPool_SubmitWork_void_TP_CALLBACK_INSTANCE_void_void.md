# CThreadPool::SubmitWork(void (*)(_TP_CALLBACK_INSTANCE *,void *),void *)

- ea: `0x18000db9c`
- end: `0x18000dbce`
- name: `?SubmitWork@CThreadPool@@QEAAKP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z1@Z`
- size: `50`
- prototype: `unsigned int(CThreadPool *__hidden this, void (*)(struct _TP_CALLBACK_INSTANCE *, void *), void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fac0`
- `0x1800310f0`

## callees

- `0x18000db9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbbe`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000dbb4`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000dbb4`

## pseudocode

```c
__int64 __fastcall CThreadPool::SubmitWork(
        CThreadPool *this,
        void (*a2)(struct _TP_CALLBACK_INSTANCE *, void *),
        void *a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( !TrySubmitThreadpoolCallback(a2, a3, (PTP_CALLBACK_ENVIRON)((char *)this + 8)) )
    return GetLastError();
  return v3;
}

```

## disassembly

```asm
0x18000db9c  push    rbx
0x18000db9e  sub     rsp, 20h
0x18000dba2  mov     rax, r8
0x18000dba5  mov     r9, rdx
0x18000dba8  lea     r8, [rcx+8]; pcbe
0x18000dbac  mov     rdx, rax; pv
0x18000dbaf  mov     rcx, r9; pfns
0x18000dbb2  xor     ebx, ebx
0x18000dbb4  call    cs:__imp_TrySubmitThreadpoolCallback
0x18000dbba  test    eax, eax
0x18000dbbc  jnz     short loc_18000DBC6
0x18000dbbe  call    cs:__imp_GetLastError
0x18000dbc4  mov     ebx, eax
0x18000dbc6  mov     eax, ebx
0x18000dbc8  add     rsp, 20h
0x18000dbcc  pop     rbx
0x18000dbcd  retn
```
