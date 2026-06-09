# Broker::ApplicationStateTable::State::OnUserLogon(void)

- ea: `0x180008604`
- end: `0x180008660`
- name: `?OnUserLogon@State@ApplicationStateTable@Broker@@QEAA_NXZ`
- size: `92`
- prototype: `bool __fastcall(Broker::ApplicationStateTable::State *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007a0c`
- `0x18000c970`

## callees

- `0x180008604`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000861b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000861b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000864d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000864d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008621`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008621`

## pseudocode

```c
bool __fastcall Broker::ApplicationStateTable::State::OnUserLogon(Broker::ApplicationStateTable::State *this)
{
  char *v1; // rdi
  char v3; // cl
  _BYTE *v4; // rax
  bool v5; // zf
  bool v6; // bl

  v1 = (char *)this + 144;
  RtlAcquireSRWLockExclusive((char *)this + 144);
  GetCurrentThreadId();
  v3 = 0;
  v4 = (char *)this + 137;
  if ( *((_BYTE *)this + 136) )
    v3 = *v4 != 0;
  v5 = v3 == *v4;
  *((_BYTE *)this + 136) = 1;
  v6 = !v5;
  RtlReleaseSRWLockExclusive(v1);
  return v6;
}

```

## disassembly

```asm
0x180008604  mov     [rsp+arg_0], rbx
0x180008609  push    rdi
0x18000860a  sub     rsp, 20h
0x18000860e  lea     rdi, [rcx+90h]
0x180008615  mov     rbx, rcx
0x180008618  mov     rcx, rdi
0x18000861b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180008621  call    cs:__imp_GetCurrentThreadId
0x180008627  xor     ecx, ecx
0x180008629  lea     rax, [rbx+89h]
0x180008630  cmp     [rbx+88h], cl
0x180008636  jz      short loc_18000863E
0x180008638  cmp     [rax], cl
0x18000863a  jz      short loc_18000863E
0x18000863c  mov     cl, 1
0x18000863e  cmp     cl, [rax]
0x180008640  mov     rcx, rdi
0x180008643  mov     byte ptr [rbx+88h], 1
0x18000864a  setnz   bl
0x18000864d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008653  mov     al, bl
0x180008655  mov     rbx, [rsp+28h+arg_0]
0x18000865a  add     rsp, 20h
0x18000865e  pop     rdi
0x18000865f  retn
```
