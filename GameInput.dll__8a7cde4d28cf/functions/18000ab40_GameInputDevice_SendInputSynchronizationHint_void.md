# GameInputDevice::SendInputSynchronizationHint(void)

- ea: `0x18000ab40`
- end: `0x18000ac0b`
- name: `?SendInputSynchronizationHint@GameInputDevice@@UEAAXXZ`
- size: `203`
- prototype: `void __fastcall(GameInputDevice *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800041f8`
- `0x1800069a4`
- `0x18000962c`
- `0x18000a7a0`
- `0x18000ab40`
- `0x18000d658`
- `0x180024794`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000abb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000abb5`

## pseudocode

```c
void __fastcall GameInputDevice::SendInputSynchronizationHint(GameInputDevice *this, __int64 a2)
{
  __int64 v3; // rsi
  SharedBuffer **CurrentBuffer; // rax
  SharedBuffer *v5; // rdi
  __int64 v6; // rcx
  _BYTE *v7; // rbx
  _DWORD v8[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v9; // [rsp+28h] [rbp-30h]
  __int64 v10; // [rsp+30h] [rbp-28h]
  __int128 v11; // [rsp+38h] [rbp-20h] BYREF
  SharedBuffer *v12; // [rsp+68h] [rbp+10h] BYREF

  v3 = GameInputCurrentTime(this, a2);
  CurrentBuffer = (SharedBuffer **)GameInputDevice::GetCurrentBuffer(this, &v12);
  v5 = *CurrentBuffer;
  *CurrentBuffer = 0;
  if ( v12 )
    SharedBuffer::ReleaseReference(v12);
  if ( v5 )
  {
    v6 = *((_QWORD *)v5 + 9);
    if ( v6 )
      InputSynchronizationState::PushTitleEvent(v6, v3, 4);
    v7 = (_BYTE *)*((_QWORD *)this + 9);
    if ( v7 )
    {
      if ( *v7 )
      {
        v8[0] = 5;
        v9 = v3;
        v8[1] = GetCurrentThreadId();
        v10 = 0;
        v11 = 0;
        TraceQueue<PixTraceLog::TraceData>::Push(v7 + 8, v8);
        ReadingPoolElementPtr::~ReadingPoolElementPtr((ReadingPoolElementPtr *)&v11);
      }
    }
    SharedBuffer::ReleaseReference(v5);
  }
}

```

## disassembly

```asm
0x18000ab40  mov     [rsp+arg_0], rbx
0x18000ab45  mov     [rsp+arg_10], rsi
0x18000ab4a  push    rdi
0x18000ab4b  sub     rsp, 50h
0x18000ab4f  mov     rbx, rcx
0x18000ab52  call    GameInputCurrentTime
0x18000ab57  lea     rdx, [rsp+58h+arg_8]
0x18000ab5c  mov     rcx, rbx
0x18000ab5f  mov     rsi, rax
0x18000ab62  call    ?GetCurrentBuffer@GameInputDevice@@QEBA?AVSharedBufferPtr@@XZ; GameInputDevice::GetCurrentBuffer(void)
0x18000ab67  mov     rdi, [rax]
0x18000ab6a  mov     qword ptr [rax], 0
0x18000ab71  mov     rcx, [rsp+58h+arg_8]; this
0x18000ab76  test    rcx, rcx
0x18000ab79  jz      short loc_18000AB80
0x18000ab7b  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x18000ab80  test    rdi, rdi
0x18000ab83  jz      short loc_18000ABFA
0x18000ab85  mov     rcx, [rdi+48h]
0x18000ab89  test    rcx, rcx
0x18000ab8c  jz      short loc_18000AB9C
0x18000ab8e  mov     r8d, 4
0x18000ab94  mov     rdx, rsi
0x18000ab97  call    ?PushTitleEvent@InputSynchronizationState@@QEAAX_KW4InputSynchronizationEventKind@@@Z; InputSynchronizationState::PushTitleEvent(unsigned __int64,InputSynchronizationEventKind)
0x18000ab9c  mov     rbx, [rbx+48h]
0x18000aba0  nop
0x18000aba1  test    rbx, rbx
0x18000aba4  jz      short loc_18000ABF2
0x18000aba6  mov     al, [rbx]
0x18000aba8  nop
0x18000aba9  test    al, al
0x18000abab  jz      short loc_18000ABF2
0x18000abad  mov     [rsp+58h+var_38], 5
0x18000abb5  call    cs:__imp_GetCurrentThreadId
0x18000abbc  nop     dword ptr [rax+rax+00h]
0x18000abc1  xorps   xmm0, xmm0
0x18000abc4  mov     [rsp+58h+var_30], rsi
0x18000abc9  mov     [rsp+58h+var_34], eax
0x18000abcd  lea     rcx, [rbx+8]
0x18000abd1  xor     eax, eax
0x18000abd3  lea     rdx, [rsp+58h+var_38]
0x18000abd8  mov     [rsp+58h+var_28], rax
0x18000abdd  movdqu  [rsp+58h+var_20], xmm0
0x18000abe3  call    ?Push@?$TraceQueue@UTraceData@PixTraceLog@@@@QEAA_N$$QEAUTraceData@PixTraceLog@@@Z; TraceQueue<PixTraceLog::TraceData>::Push(PixTraceLog::TraceData &&)
0x18000abe8  lea     rcx, [rsp+58h+var_20]; this
0x18000abed  call    ??1ReadingPoolElementPtr@@QEAA@XZ; ReadingPoolElementPtr::~ReadingPoolElementPtr(void)
0x18000abf2  mov     rcx, rdi; this
0x18000abf5  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x18000abfa  mov     rbx, [rsp+58h+arg_0]
0x18000abff  mov     rsi, [rsp+58h+arg_10]
0x18000ac04  add     rsp, 50h
0x18000ac08  pop     rdi
0x18000ac09  retn
```
