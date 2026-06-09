# ReadingPoolElementPtr::LogPixReadingEvent(GameInputPixDataV2::LogEntryKind,unsigned __int64)

- ea: `0x180008610`
- end: `0x1800086cb`
- name: `?LogPixReadingEvent@ReadingPoolElementPtr@@QEBAXW4LogEntryKind@GameInputPixDataV2@@_K@Z`
- size: `187`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1800069f0`
- `0x180007140`
- `0x180007850`

## callees

- `0x1800041f8`
- `0x1800044f0`
- `0x180008610`
- `0x18000962c`
- `0x18000d68c`
- `0x18002361c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008646`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008646`

## pseudocode

```c
void __fastcall ReadingPoolElementPtr::LogPixReadingEvent(__int64 **a1, int a2, __int64 a3)
{
  _BYTE *v5; // rdi
  DWORD CurrentThreadId; // eax
  __int64 *v7; // rsi
  unsigned __int64 v8; // rbx
  _DWORD v9[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+28h] [rbp-30h]
  __int64 v11; // [rsp+30h] [rbp-28h]
  _QWORD v12[4]; // [rsp+38h] [rbp-20h] BYREF

  if ( *a1 )
  {
    v5 = *(_BYTE **)((*a1)[12] + 72);
    if ( v5 )
    {
      if ( *v5 )
      {
        v9[0] = a2;
        CurrentThreadId = GetCurrentThreadId();
        v10 = a3;
        v7 = *a1;
        v8 = (unsigned __int64)a1[1];
        v12[1] = v8;
        v9[1] = CurrentThreadId;
        v11 = 0;
        v12[0] = v7;
        if ( v7 )
        {
          SharedBuffer::AddReference((SharedBuffer *)v7);
          if ( !ReadingPool::AddElementReference(v7[3], v8) )
          {
            GameInputFailFast(2147500036LL, 21);
            JUMPOUT(0x1800086CALL);
          }
        }
        TraceQueue<PixTraceLog::TraceData>::Push(v5 + 8, v9);
        ReadingPoolElementPtr::~ReadingPoolElementPtr((ReadingPoolElementPtr *)v12);
      }
    }
  }
}

```

## disassembly

```asm
0x180008610  mov     [rsp+arg_0], rbx
0x180008615  mov     [rsp+arg_8], rsi
0x18000861a  push    rdi
0x18000861b  sub     rsp, 50h
0x18000861f  mov     rax, [rcx]
0x180008622  mov     rsi, r8
0x180008625  mov     rbx, rcx
0x180008628  test    rax, rax
0x18000862b  jz      short loc_1800086AA
0x18000862d  mov     rax, [rax+60h]
0x180008631  mov     rdi, [rax+48h]
0x180008635  nop
0x180008636  test    rdi, rdi
0x180008639  jz      short loc_1800086AA
0x18000863b  mov     al, [rdi]
0x18000863d  nop
0x18000863e  test    al, al
0x180008640  jz      short loc_1800086AA
0x180008642  mov     [rsp+58h+var_38], edx
0x180008646  call    cs:__imp_GetCurrentThreadId
0x18000864d  nop     dword ptr [rax+rax+00h]
0x180008652  mov     [rsp+58h+var_30], rsi
0x180008657  mov     rsi, [rbx]
0x18000865a  mov     rbx, [rbx+8]
0x18000865e  mov     [rsp+58h+var_18], rbx
0x180008663  mov     [rsp+58h+var_34], eax
0x180008667  mov     [rsp+58h+var_28], 0
0x180008670  mov     [rsp+58h+var_20], rsi
0x180008675  test    rsi, rsi
0x180008678  jz      short loc_180008692
0x18000867a  mov     rcx, rsi; this
0x18000867d  call    ?AddReference@SharedBuffer@@QEAAXXZ; SharedBuffer::AddReference(void)
0x180008682  mov     rcx, [rsi+18h]
0x180008686  mov     rdx, rbx
0x180008689  call    ?AddElementReference@ReadingPool@@QEAA_NVReadingPoolElementId@@@Z; ReadingPool::AddElementReference(ReadingPoolElementId)
0x18000868e  test    al, al
0x180008690  jz      short loc_1800086BB
0x180008692  lea     rcx, [rdi+8]
0x180008696  lea     rdx, [rsp+58h+var_38]
0x18000869b  call    ?Push@?$TraceQueue@UTraceData@PixTraceLog@@@@QEAA_N$$QEAUTraceData@PixTraceLog@@@Z; TraceQueue<PixTraceLog::TraceData>::Push(PixTraceLog::TraceData &&)
0x1800086a0  lea     rcx, [rsp+58h+var_20]; this
0x1800086a5  call    ??1ReadingPoolElementPtr@@QEAA@XZ; ReadingPoolElementPtr::~ReadingPoolElementPtr(void)
0x1800086aa  mov     rbx, [rsp+58h+arg_0]
0x1800086af  mov     rsi, [rsp+58h+arg_8]
0x1800086b4  add     rsp, 50h
0x1800086b8  pop     rdi
0x1800086b9  retn
0x1800086bb  mov     edx, 15h
0x1800086c0  mov     ecx, 80004004h
0x1800086c5  call    GameInputFailFast
```
