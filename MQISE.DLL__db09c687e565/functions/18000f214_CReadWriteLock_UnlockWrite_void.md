# CReadWriteLock::UnlockWrite(void)

- ea: `0x18000f214`
- end: `0x18000f2d7`
- name: `?UnlockWrite@CReadWriteLock@@QEAAXXZ`
- size: `195`
- prototype: `void __fastcall(CReadWriteLock *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800039dc`
- `0x180006834`
- `0x18000a840`
- `0x18000d930`

## callees

- `0x18000f0c8`
- `0x18000f170`
- `0x18000f214`
- `0x18000f2e0`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x18000f2a2`
- `KERNEL32!ReleaseSemaphore` at `0x18000f2a2`
- `KERNEL32!SetEvent` at `0x18000f2c6`
- `KERNEL32!SetEvent` at `0x18000f2c6`

## pseudocode

```c
void __fastcall CReadWriteLock::UnlockWrite(CReadWriteLock *this, __int64 a2, __int64 a3)
{
  unsigned __int32 v4; // edx
  LONG v5; // edi
  void *WaiterSemaphore; // rax
  void *v7; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, a3, this);
  do
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v4 = *((_DWORD *)this + 1);
        if ( v4 != 1024 )
          break;
        if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 1, 0, 1024) == 1024 )
          return;
      }
      if ( (v4 & 0x3FF000) == 0 )
        break;
      v5 = (v4 >> 12) & 0x3FF;
      if ( v4 == _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v4 - 4095 * v5 - 1024, v4) )
      {
        WaiterSemaphore = CReadWriteLock::GetReadWaiterSemaphore(this);
        ReleaseSemaphore(WaiterSemaphore, v5, 0);
        return;
      }
    }
  }
  while ( v4 != _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v4 - 0x400000, v4) );
  v7 = CReadWriteLock::GetWriteWaiterEvent(this);
  SetEvent(v7);
}

```

## disassembly

```asm
0x18000f214  mov     [rsp+arg_0], rbx
0x18000f219  push    rdi
0x18000f21a  sub     rsp, 20h
0x18000f21e  mov     rbx, rcx
0x18000f221  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f228  lea     rax, WPP_GLOBAL_Control
0x18000f22f  cmp     rcx, rax
0x18000f232  jz      short loc_18000F24B
0x18000f234  test    byte ptr [rcx+1Ch], 4
0x18000f238  jz      short loc_18000F24B
0x18000f23a  mov     rcx, [rcx+10h]
0x18000f23e  mov     edx, 0Dh
0x18000f243  mov     r9, rbx
0x18000f246  call    WPP_SF_q
0x18000f24b  mov     r8d, 400h
0x18000f251  mov     edx, [rbx+4]
0x18000f254  cmp     edx, r8d
0x18000f257  jnz     short loc_18000F267
0x18000f259  xor     ecx, ecx
0x18000f25b  mov     eax, r8d
0x18000f25e  lock cmpxchg [rbx+4], ecx
0x18000f263  jnz     short loc_18000F251
0x18000f265  jmp     short loc_18000F2CC
0x18000f267  test    edx, 3FF000h
0x18000f26d  jz      short loc_18000F2AA
0x18000f26f  mov     edi, edx
0x18000f271  mov     ecx, edx
0x18000f273  shr     edi, 0Ch
0x18000f276  and     edi, 3FFh
0x18000f27c  imul    eax, edi, 0FFFh
0x18000f282  sub     ecx, eax
0x18000f284  mov     eax, edx
0x18000f286  sub     ecx, r8d
0x18000f289  lock cmpxchg [rbx+4], ecx
0x18000f28e  cmp     edx, eax
0x18000f290  jnz     short loc_18000F251
0x18000f292  mov     rcx, rbx; this
0x18000f295  call    ?GetReadWaiterSemaphore@CReadWriteLock@@AEAAPEAXXZ; CReadWriteLock::GetReadWaiterSemaphore(void)
0x18000f29a  mov     rcx, rax; hSemaphore
0x18000f29d  xor     r8d, r8d; lpPreviousCount
0x18000f2a0  mov     edx, edi; lReleaseCount
0x18000f2a2  call    cs:__imp_ReleaseSemaphore
0x18000f2a8  jmp     short loc_18000F2CC
0x18000f2aa  lea     ecx, [rdx-400000h]
0x18000f2b0  mov     eax, edx
0x18000f2b2  lock cmpxchg [rbx+4], ecx
0x18000f2b7  cmp     edx, eax
0x18000f2b9  jnz     short loc_18000F251
0x18000f2bb  mov     rcx, rbx; this
0x18000f2be  call    ?GetWriteWaiterEvent@CReadWriteLock@@AEAAPEAXXZ; CReadWriteLock::GetWriteWaiterEvent(void)
0x18000f2c3  mov     rcx, rax; hEvent
0x18000f2c6  call    cs:__imp_SetEvent
0x18000f2cc  mov     rbx, [rsp+28h+arg_0]
0x18000f2d1  add     rsp, 20h
0x18000f2d5  pop     rdi
0x18000f2d6  retn
```
