# IncomingMessageRegistrationEvent::~IncomingMessageRegistrationEvent(void)

- ea: `0x180009aec`
- end: `0x180009b68`
- name: `??1IncomingMessageRegistrationEvent@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(IncomingMessageRegistrationEvent *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007128`

## callees

- `0x18000266c`
- `0x180009aec`
- `0x180009b70`
- `0x180009bc4`

## import_xrefs

- `EventAggregation!BriDeleteBrokeredEvent` at `0x180009b1e`
- `EventAggregation!BriDeleteBrokeredEvent` at `0x180009b1e`

## pseudocode

```c
void __fastcall IncomingMessageRegistrationEvent::~IncomingMessageRegistrationEvent(
        IncomingMessageRegistrationEvent *this)
{
  void *v2; // rcx
  int v3; // eax
  __int64 v4; // r8
  char *v5; // rcx
  void *v6; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
    IncomingMessageRegistrationEvent::FreeEaEventHandle(v2);
  *((_QWORD *)this + 1) = 0;
  if ( *(_DWORD *)this || *((_DWORD *)this + 1) )
  {
    v3 = BriDeleteBrokeredEvent(this, 1);
    if ( v3 < 0 )
      Log_HREvent_5(v3 | 0x10000000u, 0, v4, 196);
  }
  v5 = (char *)*((_QWORD *)this + 2);
  if ( v5 != (char *)this + 32 )
    operator delete(v5, (const struct std::nothrow_t *)&std::nothrow);
  v6 = (void *)*((_QWORD *)this + 1);
  if ( v6 )
    IncomingMessageRegistrationEvent::FreeEaEventHandle(v6);
}

```

## disassembly

```asm
0x180009aec  push    rbx
0x180009aee  sub     rsp, 30h
0x180009af2  mov     rbx, rcx
0x180009af5  mov     rcx, [rcx+8]; void *
0x180009af9  test    rcx, rcx
0x180009afc  jz      short loc_180009B03
0x180009afe  call    ?FreeEaEventHandle@IncomingMessageRegistrationEvent@@CAXPEAX@Z; IncomingMessageRegistrationEvent::FreeEaEventHandle(void *)
0x180009b03  mov     qword ptr [rbx+8], 0
0x180009b0b  cmp     dword ptr [rbx], 0
0x180009b0e  jnz     short loc_180009B16
0x180009b10  cmp     dword ptr [rbx+4], 0
0x180009b14  jz      short loc_180009B3B
0x180009b16  mov     edx, 1
0x180009b1b  mov     rcx, rbx
0x180009b1e  call    cs:__imp_BriDeleteBrokeredEvent
0x180009b24  test    eax, eax
0x180009b26  jns     short loc_180009B3B
0x180009b28  bts     eax, 1Ch
0x180009b2c  xor     edx, edx
0x180009b2e  mov     ecx, eax
0x180009b30  mov     r9d, 0C4h
0x180009b36  call    Log_HREvent_5
0x180009b3b  mov     rcx, [rbx+10h]; void *
0x180009b3f  lea     rax, [rbx+20h]
0x180009b43  cmp     rcx, rax
0x180009b46  jz      short loc_180009B54
0x180009b48  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009b4f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009b54  mov     rcx, [rbx+8]; void *
0x180009b58  test    rcx, rcx
0x180009b5b  jz      short loc_180009B62
0x180009b5d  call    ?FreeEaEventHandle@IncomingMessageRegistrationEvent@@CAXPEAX@Z; IncomingMessageRegistrationEvent::FreeEaEventHandle(void *)
0x180009b62  add     rsp, 30h
0x180009b66  pop     rbx
0x180009b67  retn
```
