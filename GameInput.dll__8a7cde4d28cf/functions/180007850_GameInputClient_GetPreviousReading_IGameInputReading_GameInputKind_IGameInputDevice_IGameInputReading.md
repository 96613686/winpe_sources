# GameInputClient::GetPreviousReading(IGameInputReading *,GameInputKind,IGameInputDevice *,IGameInputReading * *)

- ea: `0x180007850`
- end: `0x1800079e5`
- name: `?GetPreviousReading@GameInputClient@@UEAAJPEAUIGameInputReading@@W4GameInputKind@@PEAUIGameInputDevice@@PEAPEAU2@@Z`
- size: `405`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800041f8`
- `0x180004274`
- `0x1800044f0`
- `0x180004690`
- `0x1800069a4`
- `0x180007850`
- `0x180008610`
- `0x18000a7a0`
- `0x18000aa98`
- `0x18000d658`
- `0x180024794`

## pseudocode

```c
__int64 __fastcall GameInputClient::GetPreviousReading(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        __int64 a4,
        struct GameInputReading **a5)
{
  __int64 v9; // rax
  struct GameInputReading **v10; // r15
  __int64 v11; // r12
  __int64 i; // rcx
  __int64 *CurrentBuffer; // rax
  __int64 v14; // rdi
  __int64 v15; // rcx
  int v16; // ebx
  __int64 v17; // r8
  struct GameInputReading *v18; // rax
  __int128 v20; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v21[2]; // [rsp+30h] [rbp-10h] BYREF
  SharedBuffer *v22; // [rsp+88h] [rbp+48h] BYREF

  v9 = GameInputCurrentTime(a1, a2);
  v10 = a5;
  v11 = v9;
  v20 = 0;
  *a5 = 0;
  if ( a4 )
  {
    for ( i = *(_QWORD *)(a1 + 16); ; i = *(_QWORD *)(i + 16) )
    {
      if ( !i )
        goto LABEL_23;
      if ( i == a4 )
        break;
    }
    if ( a2 && i == a2[6] )
    {
      CurrentBuffer = (__int64 *)GameInputDevice::GetCurrentBuffer(i, &v22);
      v14 = *CurrentBuffer;
      *CurrentBuffer = 0;
      if ( v22 )
        SharedBuffer::ReleaseReference(v22);
      if ( v14 )
      {
        v15 = *(_QWORD *)(v14 + 72);
        if ( v15 )
          InputSynchronizationState::PushTitleEvent(v15, v11, 3);
        if ( (a3 & *(_DWORD *)(v14 + 20)) == 0 )
        {
          v16 = -2088108029;
LABEL_18:
          SharedBuffer::ReleaseReference((SharedBuffer *)v14);
          goto LABEL_25;
        }
        if ( a2[7] != v14 )
        {
          v16 = -2088108028;
          goto LABEL_18;
        }
        v17 = a2[8];
        a5 = 0;
        v16 = SharedBuffer::SearchForReadingChangeReverse(v14, a3, v17, &a5);
        if ( v16 < 0 )
          goto LABEL_18;
        v21[1] = a5;
        v21[0] = v14;
        SharedBuffer::AddReference((SharedBuffer *)v14);
        ReadingPoolElementPtr::operator=(&v20, v21);
        ReadingPoolElementPtr::~ReadingPoolElementPtr((ReadingPoolElementPtr *)v21);
        ReadingPoolElementPtr::LogPixReadingEvent((__int64 **)&v20, 4, v11);
        v18 = ReadingPoolElementPtr::ConvertToReadingObject((ReadingPoolElementPtr *)&v20);
        if ( v18 )
        {
          *v10 = v18;
          SharedBuffer::ReleaseReference((SharedBuffer *)v14);
          v16 = 0;
        }
        else
        {
          SharedBuffer::ReleaseReference((SharedBuffer *)v14);
          v16 = -2147024882;
        }
      }
      else
      {
        v16 = -2088108031;
      }
    }
    else
    {
LABEL_23:
      v16 = -2147024809;
    }
  }
  else
  {
    v16 = -2147467263;
  }
LABEL_25:
  ReadingPoolElementPtr::~ReadingPoolElementPtr((ReadingPoolElementPtr *)&v20);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180007850  mov     [rsp-28h+arg_0], rbx
0x180007855  mov     [rsp-28h+arg_8], rsi
0x18000785a  push    rbp
0x18000785b  push    rdi
0x18000785c  push    r12
0x18000785e  push    r14
0x180007860  push    r15
0x180007862  mov     rbp, rsp
0x180007865  sub     rsp, 40h
0x180007869  mov     rdi, r9
0x18000786c  mov     r14d, r8d
0x18000786f  mov     rbx, rdx
0x180007872  mov     rsi, rcx
0x180007875  call    GameInputCurrentTime
0x18000787a  mov     r15, [rbp+arg_20]
0x18000787e  xorps   xmm0, xmm0
0x180007881  mov     r12, rax
0x180007884  movdqu  [rbp+var_20], xmm0
0x180007889  mov     qword ptr [r15], 0
0x180007890  test    rdi, rdi
0x180007893  jz      loc_1800079BD
0x180007899  mov     rcx, [rsi+10h]
0x18000789d  nop
0x18000789e  test    rcx, rcx
0x1800078a1  jz      loc_1800079B6
0x1800078a7  cmp     rcx, rdi
0x1800078aa  jz      short loc_1800078B2
0x1800078ac  mov     rcx, [rcx+10h]
0x1800078b0  jmp     short loc_18000789D
0x1800078b2  test    rbx, rbx
0x1800078b5  jz      loc_1800079B6
0x1800078bb  cmp     rcx, [rbx+30h]
0x1800078bf  jnz     loc_1800079B6
0x1800078c5  lea     rdx, [rbp+arg_18]
0x1800078c9  call    ?GetCurrentBuffer@GameInputDevice@@QEBA?AVSharedBufferPtr@@XZ; GameInputDevice::GetCurrentBuffer(void)
0x1800078ce  mov     rdi, [rax]
0x1800078d1  mov     qword ptr [rax], 0
0x1800078d8  mov     rcx, [rbp+arg_18]; this
0x1800078dc  test    rcx, rcx
0x1800078df  jz      short loc_1800078E6
0x1800078e1  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x1800078e6  test    rdi, rdi
0x1800078e9  jz      loc_1800079AF
0x1800078ef  mov     rcx, [rdi+48h]
0x1800078f3  test    rcx, rcx
0x1800078f6  jz      short loc_180007906
0x1800078f8  mov     r8d, 3
0x1800078fe  mov     rdx, r12
0x180007901  call    ?PushTitleEvent@InputSynchronizationState@@QEAAX_KW4InputSynchronizationEventKind@@@Z; InputSynchronizationState::PushTitleEvent(unsigned __int64,InputSynchronizationEventKind)
0x180007906  test    [rdi+14h], r14d
0x18000790a  jnz     short loc_180007913
0x18000790c  mov     ebx, 838A0003h
0x180007911  jmp     short loc_180007941
0x180007913  cmp     [rbx+38h], rdi
0x180007917  jz      short loc_180007920
0x180007919  mov     ebx, 838A0004h
0x18000791e  jmp     short loc_180007941
0x180007920  mov     r8, [rbx+40h]
0x180007924  lea     r9, [rbp+arg_20]
0x180007928  mov     edx, r14d
0x18000792b  mov     [rbp+arg_20], 0
0x180007933  mov     rcx, rdi
0x180007936  call    ?SearchForReadingChangeReverse@SharedBuffer@@AEAAJW4GameInputKind@@VReadingPoolElementId@@AEAV3@@Z; SharedBuffer::SearchForReadingChangeReverse(GameInputKind,ReadingPoolElementId,ReadingPoolElementId &)
0x18000793b  mov     ebx, eax
0x18000793d  test    eax, eax
0x18000793f  jns     short loc_18000794B
0x180007941  mov     rcx, rdi; this
0x180007944  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x180007949  jmp     short loc_1800079C2
0x18000794b  mov     rax, [rbp+arg_20]
0x18000794f  mov     rcx, rdi; this
0x180007952  mov     [rbp+var_8], rax
0x180007956  mov     [rbp+var_10], rdi
0x18000795a  call    ?AddReference@SharedBuffer@@QEAAXXZ; SharedBuffer::AddReference(void)
0x18000795f  lea     rdx, [rbp+var_10]
0x180007963  lea     rcx, [rbp+var_20]
0x180007967  call    ??4ReadingPoolElementPtr@@QEAAAEAV0@$$QEAV0@@Z; ReadingPoolElementPtr::operator=(ReadingPoolElementPtr &&)
0x18000796c  lea     rcx, [rbp+var_10]; this
0x180007970  call    ??1ReadingPoolElementPtr@@QEAA@XZ; ReadingPoolElementPtr::~ReadingPoolElementPtr(void)
0x180007975  mov     r8, r12
0x180007978  lea     rcx, [rbp+var_20]
0x18000797c  mov     edx, 4
0x180007981  call    ?LogPixReadingEvent@ReadingPoolElementPtr@@QEBAXW4LogEntryKind@GameInputPixDataV2@@_K@Z; ReadingPoolElementPtr::LogPixReadingEvent(GameInputPixDataV2::LogEntryKind,unsigned __int64)
0x180007986  lea     rcx, [rbp+var_20]; this
0x18000798a  call    ?ConvertToReadingObject@ReadingPoolElementPtr@@QEAAPEAVGameInputReading@@XZ; ReadingPoolElementPtr::ConvertToReadingObject(void)
0x18000798f  mov     rcx, rdi; this
0x180007992  test    rax, rax
0x180007995  jz      short loc_1800079A3
0x180007997  mov     [r15], rax
0x18000799a  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x18000799f  xor     ebx, ebx
0x1800079a1  jmp     short loc_1800079C2
0x1800079a3  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x1800079a8  mov     ebx, 8007000Eh
0x1800079ad  jmp     short loc_1800079C2
0x1800079af  mov     ebx, 838A0001h
0x1800079b4  jmp     short loc_1800079C2
0x1800079b6  mov     ebx, 80070057h
0x1800079bb  jmp     short loc_1800079C2
0x1800079bd  mov     ebx, 80004001h
0x1800079c2  lea     rcx, [rbp+var_20]; this
0x1800079c6  call    ??1ReadingPoolElementPtr@@QEAA@XZ; ReadingPoolElementPtr::~ReadingPoolElementPtr(void)
0x1800079cb  mov     rsi, [rsp+40h+arg_8]
0x1800079d0  mov     eax, ebx
0x1800079d2  mov     rbx, [rsp+40h+arg_0]
0x1800079d7  add     rsp, 40h
0x1800079db  pop     r15
0x1800079dd  pop     r14
0x1800079df  pop     r12
0x1800079e1  pop     rdi
0x1800079e2  pop     rbp
0x1800079e3  retn
```
