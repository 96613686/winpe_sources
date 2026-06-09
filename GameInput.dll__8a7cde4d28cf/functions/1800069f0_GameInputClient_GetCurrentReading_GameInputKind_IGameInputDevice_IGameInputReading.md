# GameInputClient::GetCurrentReading(GameInputKind,IGameInputDevice *,IGameInputReading * *)

- ea: `0x1800069f0`
- end: `0x180006b44`
- name: `?GetCurrentReading@GameInputClient@@UEAAJW4GameInputKind@@PEAUIGameInputDevice@@PEAPEAUIGameInputReading@@@Z`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800041f8`
- `0x180004690`
- `0x1800069a4`
- `0x1800069f0`
- `0x180006b4c`
- `0x180008610`
- `0x18000a7a0`
- `0x18000d658`

## pseudocode

```c
__int64 __fastcall GameInputClient::GetCurrentReading(__int64 a1, __int64 a2, __int64 a3, struct GameInputReading **a4)
{
  unsigned int v6; // ebp
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rsi
  __int64 i; // rcx
  SharedBuffer **CurrentBuffer; // rax
  SharedBuffer *v12; // rbx
  unsigned int v13; // ebx
  struct GameInputReading *v14; // rax
  SharedBuffer **v15; // rax
  SharedBuffer *v16; // rdi
  _OWORD v18[2]; // [rsp+20h] [rbp-28h] BYREF
  SharedBuffer *v19; // [rsp+60h] [rbp+18h] BYREF

  v6 = a2;
  v7 = a1;
  v8 = GameInputCurrentTime(a1, a2);
  *a4 = 0;
  v9 = v8;
  v18[0] = 0;
  if ( a3 )
  {
    for ( i = *(_QWORD *)(v7 + 16); ; i = *(_QWORD *)(i + 16) )
    {
      if ( !i )
      {
        v13 = -2147024809;
        goto LABEL_21;
      }
      if ( i == a3 )
        break;
    }
    CurrentBuffer = (SharedBuffer **)GameInputDevice::GetCurrentBuffer(i, &v19);
    v12 = *CurrentBuffer;
    *CurrentBuffer = 0;
    if ( v19 )
      SharedBuffer::ReleaseReference(v19);
    if ( !v12 )
    {
      v13 = -2088108031;
      goto LABEL_21;
    }
    SharedBuffer::GetCurrentReading((__int64)v12, v6, v9, (SharedBuffer **)v18);
    SharedBuffer::ReleaseReference(v12);
  }
  else
  {
    while ( 1 )
    {
      v7 = *(_QWORD *)(v7 + 16);
      if ( !v7 )
        break;
      v15 = (SharedBuffer **)GameInputDevice::GetCurrentBuffer(v7, &v19);
      v16 = *v15;
      *v15 = 0;
      if ( v19 )
        SharedBuffer::ReleaseReference(v19);
      if ( v16 )
      {
        SharedBuffer::GetCurrentReading((__int64)v16, v6, v9, (SharedBuffer **)v18);
        SharedBuffer::ReleaseReference(v16);
      }
    }
  }
  if ( *(_QWORD *)&v18[0]
    && (ReadingPoolElementPtr::LogPixReadingEvent((__int64 **)v18, 2, v9),
        (v14 = ReadingPoolElementPtr::ConvertToReadingObject((ReadingPoolElementPtr *)v18)) != 0) )
  {
    *a4 = v14;
    v13 = 0;
  }
  else
  {
    v13 = -2088108029;
  }
LABEL_21:
  ReadingPoolElementPtr::~ReadingPoolElementPtr((ReadingPoolElementPtr *)v18);
  return v13;
}

```

## disassembly

```asm
0x1800069f0  mov     [rsp+arg_0], rbx
0x1800069f5  mov     [rsp+arg_8], rbp
0x1800069fa  push    rsi
0x1800069fb  push    rdi
0x1800069fc  push    r14
0x1800069fe  sub     rsp, 30h
0x180006a02  mov     r14, r9
0x180006a05  mov     rdi, r8
0x180006a08  mov     ebp, edx
0x180006a0a  mov     rbx, rcx
0x180006a0d  call    GameInputCurrentTime
0x180006a12  mov     qword ptr [r14], 0
0x180006a19  xorps   xmm0, xmm0
0x180006a1c  mov     rsi, rax
0x180006a1f  movdqu  [rsp+48h+var_28], xmm0
0x180006a25  test    rdi, rdi
0x180006a28  jz      loc_180006ACE
0x180006a2e  mov     rcx, [rbx+10h]
0x180006a32  nop
0x180006a33  test    rcx, rcx
0x180006a36  jz      loc_180006AC7
0x180006a3c  cmp     rcx, rdi
0x180006a3f  jz      short loc_180006A47
0x180006a41  mov     rcx, [rcx+10h]
0x180006a45  jmp     short loc_180006A32
0x180006a47  lea     rdx, [rsp+48h+arg_10]
0x180006a4c  call    ?GetCurrentBuffer@GameInputDevice@@QEBA?AVSharedBufferPtr@@XZ; GameInputDevice::GetCurrentBuffer(void)
0x180006a51  mov     rbx, [rax]
0x180006a54  mov     qword ptr [rax], 0
0x180006a5b  mov     rcx, [rsp+48h+arg_10]; this
0x180006a60  test    rcx, rcx
0x180006a63  jz      short loc_180006A6A
0x180006a65  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x180006a6a  test    rbx, rbx
0x180006a6d  jnz     short loc_180006A79
0x180006a6f  mov     ebx, 838A0001h
0x180006a74  jmp     loc_180006B24
0x180006a79  lea     r9, [rsp+48h+var_28]
0x180006a7e  mov     r8, rsi
0x180006a81  mov     edx, ebp
0x180006a83  mov     rcx, rbx
0x180006a86  call    ?GetCurrentReading@SharedBuffer@@QEAAXW4GameInputKind@@_KAEAVReadingPoolElementPtr@@@Z; SharedBuffer::GetCurrentReading(GameInputKind,unsigned __int64,ReadingPoolElementPtr &)
0x180006a8b  mov     rcx, rbx; this
0x180006a8e  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x180006a93  cmp     qword ptr [rsp+48h+var_28], 0
0x180006a99  jz      loc_180006B1F
0x180006a9f  mov     r8, rsi
0x180006aa2  lea     rcx, [rsp+48h+var_28]
0x180006aa7  mov     edx, 2
0x180006aac  call    ?LogPixReadingEvent@ReadingPoolElementPtr@@QEBAXW4LogEntryKind@GameInputPixDataV2@@_K@Z; ReadingPoolElementPtr::LogPixReadingEvent(GameInputPixDataV2::LogEntryKind,unsigned __int64)
0x180006ab1  lea     rcx, [rsp+48h+var_28]; this
0x180006ab6  call    ?ConvertToReadingObject@ReadingPoolElementPtr@@QEAAPEAVGameInputReading@@XZ; ReadingPoolElementPtr::ConvertToReadingObject(void)
0x180006abb  test    rax, rax
0x180006abe  jz      short loc_180006B1F
0x180006ac0  mov     [r14], rax
0x180006ac3  xor     ebx, ebx
0x180006ac5  jmp     short loc_180006B24
0x180006ac7  mov     ebx, 80070057h
0x180006acc  jmp     short loc_180006B24
0x180006ace  mov     rbx, [rbx+10h]
0x180006ad2  nop
0x180006ad3  test    rbx, rbx
0x180006ad6  jz      short loc_180006A93
0x180006ad8  lea     rdx, [rsp+48h+arg_10]
0x180006add  mov     rcx, rbx
0x180006ae0  call    ?GetCurrentBuffer@GameInputDevice@@QEBA?AVSharedBufferPtr@@XZ; GameInputDevice::GetCurrentBuffer(void)
0x180006ae5  mov     rdi, [rax]
0x180006ae8  mov     qword ptr [rax], 0
0x180006aef  mov     rcx, [rsp+48h+arg_10]; this
0x180006af4  test    rcx, rcx
0x180006af7  jz      short loc_180006AFE
0x180006af9  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x180006afe  test    rdi, rdi
0x180006b01  jz      short loc_180006ACE
0x180006b03  lea     r9, [rsp+48h+var_28]
0x180006b08  mov     r8, rsi
0x180006b0b  mov     edx, ebp
0x180006b0d  mov     rcx, rdi
0x180006b10  call    ?GetCurrentReading@SharedBuffer@@QEAAXW4GameInputKind@@_KAEAVReadingPoolElementPtr@@@Z; SharedBuffer::GetCurrentReading(GameInputKind,unsigned __int64,ReadingPoolElementPtr &)
0x180006b15  mov     rcx, rdi; this
0x180006b18  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x180006b1d  jmp     short loc_180006ACE
0x180006b1f  mov     ebx, 838A0003h
0x180006b24  lea     rcx, [rsp+48h+var_28]; this
0x180006b29  call    ??1ReadingPoolElementPtr@@QEAA@XZ; ReadingPoolElementPtr::~ReadingPoolElementPtr(void)
0x180006b2e  mov     rbp, [rsp+48h+arg_8]
0x180006b33  mov     eax, ebx
0x180006b35  mov     rbx, [rsp+48h+arg_0]
0x180006b3a  add     rsp, 30h
0x180006b3e  pop     r14
0x180006b40  pop     rdi
0x180006b41  pop     rsi
0x180006b42  retn
```
