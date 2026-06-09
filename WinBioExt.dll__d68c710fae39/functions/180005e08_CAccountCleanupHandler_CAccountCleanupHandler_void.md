# CAccountCleanupHandler::~CAccountCleanupHandler(void)

- ea: `0x180005e08`
- end: `0x180005e85`
- name: `??1CAccountCleanupHandler@@AEAA@XZ`
- size: `125`
- prototype: `void __fastcall(CAccountCleanupHandler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800063c0`

## callees

- `0x1800037e4`
- `0x180005e08`
- `0x180006af0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005e43`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005e43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e30`

## string_xrefs

- `0x180005e73`: `onecore\ds\security\biometrics\credprov\common\threads.cpp`

## pseudocode

```c
void __fastcall CAccountCleanupHandler::~CAccountCleanupHandler(CAccountCleanupHandler *this)
{
  handle_thread *v1; // rdi
  __int64 v2; // rsi
  int v3; // ebx
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (CAccountCleanupHandler *)((char *)this + 96);
  *(_QWORD *)this = &CAccountCleanupHandler::`vftable';
  v2 = *((_QWORD *)this + 12);
  if ( v2 )
  {
    v3 = *(_DWORD *)(v2 + 16);
    if ( GetCurrentThreadId() == v3 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x174,
        (unsigned int)"onecore\\ds\\security\\biometrics\\credprov\\common\\threads.cpp",
        v4);
    WaitForSingleObject(*(HANDLE *)(v2 + 120), 0x7D0u);
  }
  handle_thread::Close(v1);
  --dword_1800105B4;
  handle_thread::Close(v1);
}

```

## disassembly

```asm
0x180005e08  mov     [rsp+arg_0], rbx
0x180005e0d  mov     [rsp+arg_8], rsi
0x180005e12  push    rdi
0x180005e13  sub     rsp, 20h
0x180005e17  lea     rax, ??_7CAccountCleanupHandler@@6B@; const CAccountCleanupHandler::`vftable'
0x180005e1e  lea     rdi, [rcx+60h]
0x180005e22  mov     [rcx], rax
0x180005e25  mov     rsi, [rdi]
0x180005e28  test    rsi, rsi
0x180005e2b  jz      short loc_180005E49
0x180005e2d  mov     ebx, [rsi+10h]
0x180005e30  call    cs:__imp_GetCurrentThreadId
0x180005e36  cmp     eax, ebx
0x180005e38  jz      short loc_180005E6E
0x180005e3a  mov     rcx, [rsi+78h]; hHandle
0x180005e3e  mov     edx, 7D0h; dwMilliseconds
0x180005e43  call    cs:__imp_WaitForSingleObject
0x180005e49  mov     rcx, rdi; this
0x180005e4c  call    ?Close@handle_thread@@QEAAXXZ; handle_thread::Close(void)
0x180005e51  dec     cs:dword_1800105B4
0x180005e57  mov     rcx, rdi; this
0x180005e5a  mov     rbx, [rsp+28h+arg_0]
0x180005e5f  mov     rsi, [rsp+28h+arg_8]
0x180005e64  add     rsp, 20h
0x180005e68  pop     rdi
0x180005e69  jmp     ?Close@handle_thread@@QEAAXXZ; handle_thread::Close(void)
0x180005e6e  mov     rcx, [rsp+28h]; this
0x180005e73  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\biometrics\\cred"...
0x180005e7a  mov     edx, 174h; void *
0x180005e7f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
