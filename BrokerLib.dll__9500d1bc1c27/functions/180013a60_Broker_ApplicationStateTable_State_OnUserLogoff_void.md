# Broker::ApplicationStateTable::State::OnUserLogoff(void)

- ea: `0x180013a60`
- end: `0x180013ac2`
- name: `?OnUserLogoff@State@ApplicationStateTable@Broker@@QEAA_NXZ`
- size: `98`
- prototype: `bool __fastcall(Broker::ApplicationStateTable::State *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800026b4`
- `0x180007a0c`

## callees

- `0x180013a60`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180013a7c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180013a7c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180013aa9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180013aa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013a82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013a82`

## pseudocode

```c
char __fastcall Broker::ApplicationStateTable::State::OnUserLogoff(Broker::ApplicationStateTable::State *this)
{
  char *v1; // rsi
  char v3; // di

  v1 = (char *)this + 144;
  RtlAcquireSRWLockExclusive((char *)this + 144);
  GetCurrentThreadId();
  if ( !*((_BYTE *)this + 136) || (v3 = 1, !*((_BYTE *)this + 137)) )
    v3 = 0;
  *((_BYTE *)this + 136) = 0;
  RtlReleaseSRWLockExclusive(v1);
  return v3;
}

```

## disassembly

```asm
0x180013a60  mov     [rsp+arg_0], rbx
0x180013a65  mov     [rsp+arg_8], rsi
0x180013a6a  push    rdi
0x180013a6b  sub     rsp, 20h
0x180013a6f  lea     rsi, [rcx+90h]
0x180013a76  mov     rbx, rcx
0x180013a79  mov     rcx, rsi
0x180013a7c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180013a82  call    cs:__imp_GetCurrentThreadId
0x180013a88  xor     eax, eax
0x180013a8a  cmp     [rbx+88h], al
0x180013a90  jz      short loc_180013A9D
0x180013a92  mov     dil, 1
0x180013a95  cmp     [rbx+89h], al
0x180013a9b  jnz     short loc_180013AA0
0x180013a9d  mov     dil, al
0x180013aa0  mov     rcx, rsi
0x180013aa3  mov     [rbx+88h], al
0x180013aa9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180013aaf  mov     rbx, [rsp+28h+arg_0]
0x180013ab4  mov     al, dil
0x180013ab7  mov     rsi, [rsp+28h+arg_8]
0x180013abc  add     rsp, 20h
0x180013ac0  pop     rdi
0x180013ac1  retn
```
