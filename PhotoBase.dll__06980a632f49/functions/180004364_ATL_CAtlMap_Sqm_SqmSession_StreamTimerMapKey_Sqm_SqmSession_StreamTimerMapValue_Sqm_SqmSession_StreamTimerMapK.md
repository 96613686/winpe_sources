# ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::GetNode(Sqm::SqmSession::StreamTimerMapKey const &,uint &,uint &,ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::CNode * &)

- ea: `0x180004364`
- end: `0x1800043d6`
- name: `?GetNode@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEBAPEAVCNode@12@AEBUStreamTimerMapKey@SqmSession@Sqm@@AEAI1AEAPEAV312@@Z`
- size: `114`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800048b0`
- `0x1800066dc`
- `0x180006880`
- `0x180006b20`

## callees

- `0x180004364`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::GetNode(
        __int64 *a1,
        int *a2,
        _DWORD *a3,
        unsigned int *a4,
        _QWORD *a5)
{
  int v5; // r11d
  int v6; // r10d
  int v7; // ebx
  unsigned int v8; // r10d
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 result; // rax
  __int64 v12; // rcx

  v5 = a2[1];
  v6 = *((unsigned __int16 *)a2 + 3);
  v7 = *a2;
  HIDWORD(v9) = 0;
  v8 = v7 ^ ((v5 << 16) | v6);
  *a4 = v8;
  LODWORD(v9) = v8 % *((_DWORD *)a1 + 4);
  v10 = *a1;
  *a3 = v9;
  if ( !v10 )
    return 0;
  result = *(_QWORD *)(v10 + 8 * v9);
  *a5 = 0;
  if ( !result )
    return 0;
  v12 = 0;
  while ( *(_DWORD *)(result + 80) != v8 || *(_DWORD *)result != v7 || *(_DWORD *)(result + 4) != v5 )
  {
    v12 = result;
    result = *(_QWORD *)(result + 72);
    if ( !result )
      return 0;
  }
  *a5 = v12;
  return result;
}

```

## disassembly

```asm
0x180004364  mov     [rsp+arg_0], rbx
0x180004369  mov     r11d, [rdx+4]
0x18000436d  mov     eax, r11d
0x180004370  movzx   r10d, word ptr [rdx+6]
0x180004375  mov     ebx, [rdx]
0x180004377  xor     edx, edx
0x180004379  shl     eax, 10h
0x18000437c  or      r10d, eax
0x18000437f  xor     r10d, ebx
0x180004382  mov     eax, r10d
0x180004385  mov     [r9], r10d
0x180004388  div     dword ptr [rcx+10h]
0x18000438b  mov     r9, [rcx]
0x18000438e  mov     [r8], edx
0x180004391  test    r9, r9
0x180004394  jz      short loc_1800043C9
0x180004396  mov     r8, [rsp+arg_20]
0x18000439b  mov     rax, [r9+rdx*8]
0x18000439f  mov     qword ptr [r8], 0
0x1800043a6  test    rax, rax
0x1800043a9  jz      short loc_1800043C9
0x1800043ab  xor     ecx, ecx
0x1800043ad  cmp     [rax+50h], r10d
0x1800043b1  jnz     short loc_1800043BD
0x1800043b3  cmp     [rax], ebx
0x1800043b5  jnz     short loc_1800043BD
0x1800043b7  cmp     [rax+4], r11d
0x1800043bb  jz      short loc_1800043D1
0x1800043bd  mov     rcx, rax
0x1800043c0  mov     rax, [rax+48h]
0x1800043c4  test    rax, rax
0x1800043c7  jnz     short loc_1800043AD
0x1800043c9  xor     eax, eax
0x1800043cb  mov     rbx, [rsp+arg_0]
0x1800043d0  retn
0x1800043d1  mov     [r8], rcx
0x1800043d4  jmp     short loc_1800043CB
```
