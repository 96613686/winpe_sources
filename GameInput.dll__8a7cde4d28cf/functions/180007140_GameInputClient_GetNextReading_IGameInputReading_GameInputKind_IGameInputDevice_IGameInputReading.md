# GameInputClient::GetNextReading(IGameInputReading *,GameInputKind,IGameInputDevice *,IGameInputReading * *)

- ea: `0x180007140`
- end: `0x180007271`
- name: `?GetNextReading@GameInputClient@@UEAAJPEAUIGameInputReading@@W4GameInputKind@@PEAUIGameInputDevice@@PEAPEAU2@@Z`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800041f8`
- `0x180004690`
- `0x1800069a4`
- `0x180007140`
- `0x180007278`
- `0x180008610`
- `0x18000a7a0`
- `0x18000d658`

## pseudocode

```c
__int64 __fastcall GameInputClient::GetNextReading(__int64 a1, __int64 a2, int a3, __int64 a4, SharedBuffer *a5)
{
  __int64 v9; // rax
  SharedBuffer *v10; // r14
  __int64 v11; // rbp
  __int64 i; // rcx
  SharedBuffer **CurrentBuffer; // rax
  SharedBuffer *v14; // rdi
  int NextReading; // ebx
  struct GameInputReading *v16; // rax
  _OWORD v18[4]; // [rsp+30h] [rbp-48h] BYREF

  v9 = GameInputCurrentTime(a1, a2);
  v10 = a5;
  v11 = v9;
  v18[0] = 0;
  *(_QWORD *)a5 = 0;
  if ( a4 )
  {
    for ( i = *(_QWORD *)(a1 + 16); ; i = *(_QWORD *)(i + 16) )
    {
      if ( !i )
        goto LABEL_17;
      if ( i == a4 )
        break;
    }
    if ( !a2 || i != *(_QWORD *)(a2 + 48) )
    {
LABEL_17:
      NextReading = -2147024809;
      goto LABEL_19;
    }
    CurrentBuffer = (SharedBuffer **)GameInputDevice::GetCurrentBuffer(i, &a5);
    v14 = *CurrentBuffer;
    *CurrentBuffer = 0;
    if ( a5 )
      SharedBuffer::ReleaseReference(a5);
    if ( v14 )
    {
      NextReading = SharedBuffer::GetNextReading((__int64)v14, a3, v11, (_QWORD *)(a2 + 56), (__int64)v18);
      if ( NextReading >= 0 )
      {
        ReadingPoolElementPtr::LogPixReadingEvent((__int64 **)v18, 4, v11);
        v16 = ReadingPoolElementPtr::ConvertToReadingObject((ReadingPoolElementPtr *)v18);
        if ( v16 )
        {
          *(_QWORD *)v10 = v16;
          SharedBuffer::ReleaseReference(v14);
          NextReading = 0;
        }
        else
        {
          SharedBuffer::ReleaseReference(v14);
          NextReading = -2147024882;
        }
      }
      else
      {
        SharedBuffer::ReleaseReference(v14);
      }
    }
    else
    {
      NextReading = -2088108031;
    }
  }
  else
  {
    NextReading = -2147467263;
  }
LABEL_19:
  ReadingPoolElementPtr::~ReadingPoolElementPtr((ReadingPoolElementPtr *)v18);
  return (unsigned int)NextReading;
}

```

## disassembly

```asm
0x180007140  push    rbx
0x180007142  push    rbp
0x180007143  push    rsi
0x180007144  push    rdi
0x180007145  push    r14
0x180007147  push    r15
0x180007149  sub     rsp, 48h
0x18000714d  mov     rdi, r9
0x180007150  mov     r15d, r8d
0x180007153  mov     rbx, rdx
0x180007156  mov     rsi, rcx
0x180007159  call    GameInputCurrentTime
0x18000715e  mov     r14, [rsp+78h+arg_20]
0x180007166  xorps   xmm0, xmm0
0x180007169  mov     rbp, rax
0x18000716c  movdqu  [rsp+78h+var_48], xmm0
0x180007172  mov     qword ptr [r14], 0
0x180007179  test    rdi, rdi
0x18000717c  jz      loc_180007252
0x180007182  mov     rcx, [rsi+10h]
0x180007186  nop
0x180007187  test    rcx, rcx
0x18000718a  jz      loc_18000724B
0x180007190  cmp     rcx, rdi
0x180007193  jz      short loc_18000719B
0x180007195  mov     rcx, [rcx+10h]
0x180007199  jmp     short loc_180007186
0x18000719b  test    rbx, rbx
0x18000719e  jz      loc_18000724B
0x1800071a4  cmp     rcx, [rbx+30h]
0x1800071a8  jnz     loc_18000724B
0x1800071ae  lea     rdx, [rsp+78h+arg_20]
0x1800071b6  call    ?GetCurrentBuffer@GameInputDevice@@QEBA?AVSharedBufferPtr@@XZ; GameInputDevice::GetCurrentBuffer(void)
0x1800071bb  mov     rdi, [rax]
0x1800071be  mov     qword ptr [rax], 0
0x1800071c5  mov     rcx, [rsp+78h+arg_20]; this
0x1800071cd  test    rcx, rcx
0x1800071d0  jz      short loc_1800071D7
0x1800071d2  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x1800071d7  test    rdi, rdi
0x1800071da  jz      short loc_180007244
0x1800071dc  lea     rax, [rsp+78h+var_48]
0x1800071e1  mov     r8, rbp
0x1800071e4  lea     r9, [rbx+38h]
0x1800071e8  mov     [rsp+78h+var_58], rax
0x1800071ed  mov     edx, r15d
0x1800071f0  mov     rcx, rdi
0x1800071f3  call    ?GetNextReading@SharedBuffer@@QEAAJW4GameInputKind@@_KAEBVReadingPoolElementPtr@@AEAV3@@Z; SharedBuffer::GetNextReading(GameInputKind,unsigned __int64,ReadingPoolElementPtr const &,ReadingPoolElementPtr &)
0x1800071f8  mov     ebx, eax
0x1800071fa  test    eax, eax
0x1800071fc  jns     short loc_180007208
0x1800071fe  mov     rcx, rdi; this
0x180007201  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x180007206  jmp     short loc_180007257
0x180007208  mov     r8, rbp
0x18000720b  lea     rcx, [rsp+78h+var_48]
0x180007210  mov     edx, 4
0x180007215  call    ?LogPixReadingEvent@ReadingPoolElementPtr@@QEBAXW4LogEntryKind@GameInputPixDataV2@@_K@Z; ReadingPoolElementPtr::LogPixReadingEvent(GameInputPixDataV2::LogEntryKind,unsigned __int64)
0x18000721a  lea     rcx, [rsp+78h+var_48]; this
0x18000721f  call    ?ConvertToReadingObject@ReadingPoolElementPtr@@QEAAPEAVGameInputReading@@XZ; ReadingPoolElementPtr::ConvertToReadingObject(void)
0x180007224  mov     rcx, rdi; this
0x180007227  test    rax, rax
0x18000722a  jz      short loc_180007238
0x18000722c  mov     [r14], rax
0x18000722f  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x180007234  xor     ebx, ebx
0x180007236  jmp     short loc_180007257
0x180007238  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x18000723d  mov     ebx, 8007000Eh
0x180007242  jmp     short loc_180007257
0x180007244  mov     ebx, 838A0001h
0x180007249  jmp     short loc_180007257
0x18000724b  mov     ebx, 80070057h
0x180007250  jmp     short loc_180007257
0x180007252  mov     ebx, 80004001h
0x180007257  lea     rcx, [rsp+78h+var_48]; this
0x18000725c  call    ??1ReadingPoolElementPtr@@QEAA@XZ; ReadingPoolElementPtr::~ReadingPoolElementPtr(void)
0x180007261  mov     eax, ebx
0x180007263  add     rsp, 48h
0x180007267  pop     r15
0x180007269  pop     r14
0x18000726b  pop     rdi
0x18000726c  pop     rsi
0x18000726d  pop     rbp
0x18000726e  pop     rbx
0x18000726f  retn
```
