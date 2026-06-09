# SharedBuffer::GetNextReading(GameInputKind,unsigned __int64,ReadingPoolElementPtr const &,ReadingPoolElementPtr &)

- ea: `0x180007278`
- end: `0x180007396`
- name: `?GetNextReading@SharedBuffer@@QEAAJW4GameInputKind@@_KAEBVReadingPoolElementPtr@@AEAV3@@Z`
- size: `286`
- prototype: `__int64 __fastcall(__int64, int, __int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180007140`

## callees

- `0x1800041f8`
- `0x180004274`
- `0x1800044f0`
- `0x180007278`
- `0x180023c58`
- `0x180024794`
- `0x1800248a8`

## pseudocode

```c
__int64 __fastcall SharedBuffer::GetNextReading(__int64 a1, int a2, __int64 a3, _QWORD *a4, __int64 a5)
{
  __int64 v7; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  int NextElement; // r11d
  __int64 v13; // rbx
  unsigned int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-18h] BYREF
  __int16 v17; // [rsp+28h] [rbp-10h]
  int v18; // [rsp+2Ah] [rbp-Eh]
  __int16 v19; // [rsp+2Eh] [rbp-Ah]
  __int64 v20; // [rsp+60h] [rbp+28h] BYREF

  v7 = *(_QWORD *)(a1 + 72);
  if ( v7 )
    InputSynchronizationState::PushTitleEvent(v7, a3, 2);
  if ( (a2 & *(_DWORD *)(a1 + 20)) == 0 )
    return 2206859267LL;
  if ( *a4 != a1 )
    return 2206859268LL;
  v10 = a4[1];
  v11 = *(_QWORD *)(a1 + 24);
  v20 = 0;
  NextElement = ReadingPool::GetNextElement(v11, v10, &v20);
  if ( NextElement < 0 )
    return (unsigned int)NextElement;
  v13 = v20;
  while ( 1 )
  {
    v14 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL) + 16LL * (unsigned __int16)v13 + 8) & 0xFFFFFFF
        | 0xF0000000;
    if ( (*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL) + 16LL * (unsigned __int16)v13 + 8) & 0x8000000LL) == 0 )
      v14 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL) + 16LL * (unsigned __int16)v13 + 8) & 0xFFFFFFF;
    if ( (v14 & a2) != 0 )
      break;
    v15 = *(_QWORD *)(a1 + 24);
    v20 = 0;
    ReadingPool::GetNextElement(v15, v13, &v20);
    ReadingPool::ReleaseElementReference(*(_QWORD *)(a1 + 24), v13);
    v13 = v20;
    if ( NextElement < 0 )
      return (unsigned int)NextElement;
  }
  v18 = *(_DWORD *)((char *)&v20 + 2);
  v19 = HIWORD(v20);
  v16 = a1;
  v17 = v13;
  SharedBuffer::AddReference((SharedBuffer *)a1);
  ReadingPoolElementPtr::operator=(a5, &v16);
  ReadingPoolElementPtr::~ReadingPoolElementPtr((ReadingPoolElementPtr *)&v16);
  return 0;
}

```

## disassembly

```asm
0x180007278  push    rbp
0x18000727a  push    rbx
0x18000727b  push    rsi
0x18000727c  push    rdi
0x18000727d  mov     rbp, rsp
0x180007280  sub     rsp, 38h
0x180007284  mov     rdi, rcx
0x180007287  mov     rbx, r9
0x18000728a  mov     rcx, [rcx+48h]
0x18000728e  mov     rax, r8
0x180007291  mov     esi, edx
0x180007293  test    rcx, rcx
0x180007296  jz      short loc_1800072A6
0x180007298  mov     r8d, 2
0x18000729e  mov     rdx, rax
0x1800072a1  call    ?PushTitleEvent@InputSynchronizationState@@QEAAX_KW4InputSynchronizationEventKind@@@Z; InputSynchronizationState::PushTitleEvent(unsigned __int64,InputSynchronizationEventKind)
0x1800072a6  test    [rdi+14h], esi
0x1800072a9  jnz     short loc_1800072B5
0x1800072ab  mov     eax, 838A0003h
0x1800072b0  jmp     loc_180007354
0x1800072b5  cmp     [rbx], rdi
0x1800072b8  jz      short loc_1800072C4
0x1800072ba  mov     eax, 838A0004h
0x1800072bf  jmp     loc_180007354
0x1800072c4  mov     rdx, [rbx+8]
0x1800072c8  lea     r8, [rbp+arg_0]
0x1800072cc  mov     rcx, [rdi+18h]
0x1800072d0  mov     [rbp+arg_0], 0
0x1800072d8  call    ?GetNextElement@ReadingPool@@QEAAJVReadingPoolElementId@@AEAV2@@Z; ReadingPool::GetNextElement(ReadingPoolElementId,ReadingPoolElementId &)
0x1800072dd  mov     r11d, eax
0x1800072e0  test    eax, eax
0x1800072e2  js      short loc_180007351
0x1800072e4  mov     rbx, [rbp+arg_0]
0x1800072e8  mov     rax, [rdi+18h]
0x1800072ec  movzx   edx, bx
0x1800072ef  add     rdx, rdx
0x1800072f2  mov     rcx, [rax+8]
0x1800072f6  mov     r8, [rcx+rdx*8+8]
0x1800072fb  nop
0x1800072fc  mov     rcx, r8
0x1800072ff  and     r8d, 8000000h
0x180007306  and     ecx, 0FFFFFFFh
0x18000730c  mov     eax, ecx
0x18000730e  or      eax, 0F0000000h
0x180007313  test    r8, r8
0x180007316  cmovz   eax, ecx
0x180007319  test    esi, eax
0x18000731b  jnz     short loc_18000735E
0x18000731d  mov     rcx, [rdi+18h]
0x180007321  lea     r8, [rbp+arg_0]
0x180007325  mov     rdx, rbx
0x180007328  mov     [rbp+arg_0], 0
0x180007330  call    ?GetNextElement@ReadingPool@@QEAAJVReadingPoolElementId@@AEAV2@@Z; ReadingPool::GetNextElement(ReadingPoolElementId,ReadingPoolElementId &)
0x180007335  mov     rcx, [rdi+18h]
0x180007339  mov     rdx, rbx
0x18000733c  mov     r11d, eax
0x18000733f  call    ?ReleaseElementReference@ReadingPool@@QEAAXVReadingPoolElementId@@@Z; ReadingPool::ReleaseElementReference(ReadingPoolElementId)
0x180007344  mov     rbx, [rbp+arg_0]
0x180007348  mov     [rbp+arg_0], rbx
0x18000734c  test    r11d, r11d
0x18000734f  jns     short loc_1800072E8
0x180007351  mov     eax, r11d
0x180007354  add     rsp, 38h
0x180007358  pop     rdi
0x180007359  pop     rsi
0x18000735a  pop     rbx
0x18000735b  pop     rbp
0x18000735c  retn
0x18000735e  mov     eax, dword ptr [rbp+arg_0+2]
0x180007361  mov     rcx, rdi; this
0x180007364  mov     [rbp+var_E], eax
0x180007367  movzx   eax, word ptr [rbp+arg_0+6]
0x18000736b  mov     [rbp+var_A], ax
0x18000736f  mov     [rbp+var_18], rdi
0x180007373  mov     [rbp+var_10], bx
0x180007377  call    ?AddReference@SharedBuffer@@QEAAXXZ; SharedBuffer::AddReference(void)
0x18000737c  mov     rcx, [rbp+arg_20]
0x180007380  lea     rdx, [rbp+var_18]
0x180007384  call    ??4ReadingPoolElementPtr@@QEAAAEAV0@$$QEAV0@@Z; ReadingPoolElementPtr::operator=(ReadingPoolElementPtr &&)
0x180007389  lea     rcx, [rbp+var_18]; this
0x18000738d  call    ??1ReadingPoolElementPtr@@QEAA@XZ; ReadingPoolElementPtr::~ReadingPoolElementPtr(void)
0x180007392  xor     eax, eax
0x180007394  jmp     short loc_180007354
```
