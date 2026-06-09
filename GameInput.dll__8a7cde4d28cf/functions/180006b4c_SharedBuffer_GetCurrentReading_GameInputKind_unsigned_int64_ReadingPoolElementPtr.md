# SharedBuffer::GetCurrentReading(GameInputKind,unsigned __int64,ReadingPoolElementPtr &)

- ea: `0x180006b4c`
- end: `0x180006cbc`
- name: `?GetCurrentReading@SharedBuffer@@QEAAXW4GameInputKind@@_KAEAVReadingPoolElementPtr@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, SharedBuffer **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800069f0`

## callees

- `0x1800044f0`
- `0x180006b4c`
- `0x18000a7a0`
- `0x18000aa98`
- `0x18002361c`
- `0x180024794`
- `0x1800248a8`

## pseudocode

```c
__int64 __fastcall SharedBuffer::GetCurrentReading(__int64 a1, unsigned int a2, __int64 a3, SharedBuffer **a4)
{
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v9; // rbx
  unsigned int v10; // eax
  int v11; // r11d
  __int64 v12; // r11
  __int64 v13; // rcx
  __int64 v14; // r10
  __int64 v15; // [rsp+40h] [rbp+20h] BYREF

  v6 = *(_QWORD *)(a1 + 72);
  result = a3;
  if ( v6 )
    result = InputSynchronizationState::PushTitleEvent(v6, a3, 1);
  if ( (a2 & *(_DWORD *)(a1 + 20)) != 0 )
  {
    for ( result = 0; ; result = v9 )
    {
      v9 = **(_QWORD **)(a1 + 40);
      v15 = v9;
      if ( v9 == result )
        return result;
      if ( (unsigned __int8)ReadingPool::AddElementReference(*(_QWORD *)(a1 + 24), v9) )
      {
        v10 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL) + 16LL * (unsigned __int16)v9 + 8) & 0xFFFFFFF
            | 0xF0000000;
        if ( (*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL) + 16LL * (unsigned __int16)v9 + 8) & 0x8000000LL) == 0 )
          v10 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL) + 16LL * (unsigned __int16)v9 + 8) & 0xFFFFFFF;
        if ( (v10 & a2) != 0 )
          goto LABEL_13;
        v15 = 0;
        SharedBuffer::SearchForReadingChangeReverse(a1, a2, v9, &v15);
        ReadingPool::ReleaseElementReference(*(_QWORD *)(a1 + 24), v9);
        if ( v11 >= 0 )
          break;
      }
    }
    v9 = v15;
LABEL_13:
    if ( !*a4 )
    {
LABEL_14:
      *a4 = (SharedBuffer *)a1;
      SharedBuffer::AddReference((SharedBuffer *)a1);
      *(_DWORD *)((char *)a4 + 10) = *(_DWORD *)((char *)&v15 + 2);
      result = HIWORD(v15);
      *((_WORD *)a4 + 7) = HIWORD(v15);
      *((_WORD *)a4 + 4) = v9;
      return result;
    }
    v12 = *((_QWORD *)*a4 + 3);
    v13 = *(_QWORD *)(a1 + 24);
    v14 = *(_QWORD *)(v12 + 24) * *((unsigned __int16 *)a4 + 4);
    if ( *(_QWORD *)(*(_QWORD *)(v13 + 24) * (unsigned __int16)v9 + *(_QWORD *)(v13 + 16))
       + (unsigned __int64)*(unsigned int *)(*(_QWORD *)(v13 + 24) * (unsigned __int16)v9 + *(_QWORD *)(v13 + 16) + 8LL) > *(_QWORD *)(v14 + *(_QWORD *)(v12 + 16)) + (unsigned __int64)*(unsigned int *)(v14 + *(_QWORD *)(v12 + 16) + 8) )
    {
      ReadingPool::ReleaseElementReference(v12, a4[1]);
      SharedBuffer::ReleaseReference(*a4);
      goto LABEL_14;
    }
    return ReadingPool::ReleaseElementReference(v13, v9);
  }
  return result;
}

```

## disassembly

```asm
0x180006b4c  mov     [rsp-18h+arg_8], rbx
0x180006b51  mov     [rsp-18h+arg_10], rsi
0x180006b56  push    rbp
0x180006b57  push    rdi
0x180006b58  push    r14
0x180006b5a  mov     rbp, rsp
0x180006b5d  sub     rsp, 20h
0x180006b61  mov     rdi, rcx
0x180006b64  mov     rsi, r9
0x180006b67  mov     rcx, [rcx+48h]
0x180006b6b  mov     rax, r8
0x180006b6e  mov     r14d, edx
0x180006b71  test    rcx, rcx
0x180006b74  jz      short loc_180006B84
0x180006b76  mov     r8d, 1
0x180006b7c  mov     rdx, rax
0x180006b7f  call    ?PushTitleEvent@InputSynchronizationState@@QEAAX_KW4InputSynchronizationEventKind@@@Z; InputSynchronizationState::PushTitleEvent(unsigned __int64,InputSynchronizationEventKind)
0x180006b84  test    [rdi+14h], r14d
0x180006b88  jz      loc_180006CA8
0x180006b8e  xor     eax, eax
0x180006b90  mov     rcx, [rdi+28h]
0x180006b94  mov     rbx, [rcx]
0x180006b97  nop
0x180006b98  mov     [rbp+arg_0], rbx
0x180006b9c  cmp     rbx, rax
0x180006b9f  jz      loc_180006CA8
0x180006ba5  mov     rcx, [rdi+18h]
0x180006ba9  mov     rdx, rbx
0x180006bac  call    ?AddElementReference@ReadingPool@@QEAA_NVReadingPoolElementId@@@Z; ReadingPool::AddElementReference(ReadingPoolElementId)
0x180006bb1  test    al, al
0x180006bb3  jz      short loc_180006C19
0x180006bb5  mov     rax, [rdi+18h]
0x180006bb9  movzx   edx, bx
0x180006bbc  add     rdx, rdx
0x180006bbf  mov     rcx, [rax+8]
0x180006bc3  mov     r8, [rcx+rdx*8+8]
0x180006bc8  nop
0x180006bc9  mov     rcx, r8
0x180006bcc  and     r8d, 8000000h
0x180006bd3  and     ecx, 0FFFFFFFh
0x180006bd9  mov     eax, ecx
0x180006bdb  or      eax, 0F0000000h
0x180006be0  test    r8, r8
0x180006be3  cmovz   eax, ecx
0x180006be6  test    r14d, eax
0x180006be9  jnz     short loc_180006C29
0x180006beb  lea     r9, [rbp+arg_0]
0x180006bef  mov     [rbp+arg_0], 0
0x180006bf7  mov     r8, rbx
0x180006bfa  mov     edx, r14d
0x180006bfd  mov     rcx, rdi
0x180006c00  call    ?SearchForReadingChangeReverse@SharedBuffer@@AEAAJW4GameInputKind@@VReadingPoolElementId@@AEAV3@@Z; SharedBuffer::SearchForReadingChangeReverse(GameInputKind,ReadingPoolElementId,ReadingPoolElementId &)
0x180006c05  mov     rcx, [rdi+18h]
0x180006c09  mov     rdx, rbx
0x180006c0c  mov     r11d, eax
0x180006c0f  call    ?ReleaseElementReference@ReadingPool@@QEAAXVReadingPoolElementId@@@Z; ReadingPool::ReleaseElementReference(ReadingPoolElementId)
0x180006c14  test    r11d, r11d
0x180006c17  jns     short loc_180006C21
0x180006c19  mov     rax, rbx
0x180006c1c  jmp     loc_180006B90
0x180006c21  mov     rbx, [rbp+arg_0]
0x180006c25  mov     [rbp+arg_0], rbx
0x180006c29  mov     rax, [rsi]
0x180006c2c  test    rax, rax
0x180006c2f  jnz     short loc_180006C50
0x180006c31  mov     rcx, rdi; this
0x180006c34  mov     [rsi], rdi
0x180006c37  call    ?AddReference@SharedBuffer@@QEAAXXZ; SharedBuffer::AddReference(void)
0x180006c3c  mov     eax, dword ptr [rbp+arg_0+2]
0x180006c3f  mov     [rsi+0Ah], eax
0x180006c42  movzx   eax, word ptr [rbp+arg_0+6]
0x180006c46  mov     [rsi+0Eh], ax
0x180006c4a  mov     [rsi+8], bx
0x180006c4e  jmp     short loc_180006CA8
0x180006c50  mov     r11, [rax+18h]
0x180006c54  mov     rcx, [rdi+18h]
0x180006c58  movzx   r10d, word ptr [rsi+8]
0x180006c5d  movzx   r9d, bx
0x180006c61  imul    r10, [r11+18h]
0x180006c66  imul    r9, [rcx+18h]
0x180006c6b  mov     rax, [r11+10h]
0x180006c6f  mov     r8, [rcx+10h]
0x180006c73  mov     edx, [r10+rax+8]
0x180006c78  add     rdx, [r10+rax]
0x180006c7c  mov     eax, [r9+r8+8]
0x180006c81  add     rax, [r9+r8]
0x180006c85  cmp     rax, rdx
0x180006c88  jbe     short loc_180006CA0
0x180006c8a  mov     rdx, [rsi+8]
0x180006c8e  mov     rcx, r11
0x180006c91  call    ?ReleaseElementReference@ReadingPool@@QEAAXVReadingPoolElementId@@@Z; ReadingPool::ReleaseElementReference(ReadingPoolElementId)
0x180006c96  mov     rcx, [rsi]; this
0x180006c99  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x180006c9e  jmp     short loc_180006C31
0x180006ca0  mov     rdx, rbx
0x180006ca3  call    ?ReleaseElementReference@ReadingPool@@QEAAXVReadingPoolElementId@@@Z; ReadingPool::ReleaseElementReference(ReadingPoolElementId)
0x180006ca8  mov     rbx, [rsp+20h+arg_8]
0x180006cad  mov     rsi, [rsp+20h+arg_10]
0x180006cb2  add     rsp, 20h
0x180006cb6  pop     r14
0x180006cb8  pop     rdi
0x180006cb9  pop     rbp
0x180006cba  retn
```
