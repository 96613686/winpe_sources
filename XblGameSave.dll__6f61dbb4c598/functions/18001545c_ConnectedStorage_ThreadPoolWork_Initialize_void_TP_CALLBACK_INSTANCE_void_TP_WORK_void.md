# ConnectedStorage::ThreadPoolWork::Initialize(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)

- ea: `0x18001545c`
- end: `0x1800154c5`
- name: `?Initialize@ThreadPoolWork@ConnectedStorage@@QEAAXP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1@Z`
- size: `105`
- prototype: `void(ConnectedStorage::ThreadPoolWork *__hidden this, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *), void *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180013fd0`
- `0x18001584c`
- `0x180084e30`

## callees

- `0x18000aae4`
- `0x18001545c`
- `0x180015fa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015491`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015491`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180015482`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180015482`

## string_xrefs

- `0x1800154a3`: `ThreadPoolWork::Initialize`

## pseudocode

```c
void __fastcall ConnectedStorage::ThreadPoolWork::Initialize(
        ConnectedStorage::ThreadPoolWork *this,
        void (*a2)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *),
        void *a3)
{
  PTP_WORK ThreadpoolWork; // rax
  signed int LastError; // eax
  const unsigned __int16 *v8; // r8

  ConnectedStorage::ThreadPoolWork::Release(this);
  ThreadpoolWork = CreateThreadpoolWork(a2, a3, 0);
  *((_QWORD *)this + 1) = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)LastError,
      (int)L"ThreadPoolWork::Initialize",
      v8);
  }
  *(_QWORD *)this = a3;
}

```

## disassembly

```asm
0x18001545c  mov     [rsp+arg_0], rbx
0x180015461  mov     [rsp+arg_8], rsi
0x180015466  push    rdi
0x180015467  sub     rsp, 20h
0x18001546b  mov     rsi, r8
0x18001546e  mov     rbx, rdx
0x180015471  mov     rdi, rcx
0x180015474  call    ?Release@ThreadPoolWork@ConnectedStorage@@AEAAXXZ; ConnectedStorage::ThreadPoolWork::Release(void)
0x180015479  xor     r8d, r8d; pcbe
0x18001547c  mov     rdx, rsi; pv
0x18001547f  mov     rcx, rbx; pfnwk
0x180015482  call    cs:__imp_CreateThreadpoolWork
0x180015488  mov     [rdi+8], rax
0x18001548c  test    rax, rax
0x18001548f  jnz     short loc_1800154B2
0x180015491  call    cs:__imp_GetLastError
0x180015497  test    eax, eax
0x180015499  jle     short loc_1800154A3
0x18001549b  movzx   eax, ax
0x18001549e  or      eax, 80070000h
0x1800154a3  lea     rdx, aThreadpoolwork; "ThreadPoolWork::Initialize"
0x1800154aa  mov     ecx, eax; this
0x1800154ac  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x1800154b2  mov     rbx, [rsp+28h+arg_0]
0x1800154b7  mov     [rdi], rsi
0x1800154ba  mov     rsi, [rsp+28h+arg_8]
0x1800154bf  add     rsp, 20h
0x1800154c3  pop     rdi
0x1800154c4  retn
```
