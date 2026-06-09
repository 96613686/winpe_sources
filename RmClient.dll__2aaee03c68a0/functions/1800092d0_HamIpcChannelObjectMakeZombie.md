# HamIpcChannelObjectMakeZombie

- ea: `0x1800092d0`
- end: `0x1800093f9`
- name: `HamIpcChannelObjectMakeZombie`
- size: `297`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010d00`

## callees

- `0x1800092d0`
- `0x1800095a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800092ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800092ed`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800093c5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009351`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800093c5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800092e7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800093a0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800092e7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800093a0`
- `ntdll!RtlRbRemoveNode` at `0x180009374`
- `ntdll!RtlRbRemoveNode` at `0x180009374`
- `ntdll!TpPostWork` at `0x1800093bb`
- `ntdll!TpPostWork` at `0x1800093bb`

## pseudocode

```c
__int64 __fastcall HamIpcChannelObjectMakeZombie(__int64 *a1, __int64 a2)
{
  unsigned __int64 v4; // rbx
  int v5; // ebp
  int v6; // eax
  unsigned __int64 v7; // rax
  __int64 **v9; // rcx
  __int64 *v10; // rbx
  __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // rcx

  RtlAcquireSRWLockExclusive(a1 + 1);
  *((_DWORD *)a1 + 4) = GetCurrentThreadId();
  v4 = a1[3];
  if ( (a1[4] & 1) != 0 )
  {
    if ( !v4 )
      goto LABEL_8;
    v4 ^= (unsigned __int64)(a1 + 3);
  }
  v5 = a1[4] & 1;
  while ( v4 )
  {
    v6 = HampIpcChannelObjectComparePayloadForTree(a2, v4);
    if ( v6 < 0 )
    {
      v7 = *(_QWORD *)v4;
      if ( v5 && v7 )
        goto LABEL_19;
    }
    else
    {
      if ( v6 <= 0 )
      {
        RtlRbRemoveNode(a1 + 3, v4);
        v9 = (__int64 **)a1[6];
        if ( *v9 != a1 + 5 )
          __fastfail(3u);
        v10 = (__int64 *)(v4 + 24);
        v10[1] = (__int64)v9;
        *v10 = (__int64)(a1 + 5);
        *v9 = v10;
        a1[6] = (__int64)v10;
        v11 = *a1;
        RtlAcquireSRWLockExclusive(*a1 + 32);
        *(_DWORD *)(v11 + 64) |= 2u;
        v12 = *(_DWORD *)(v11 + 64);
        if ( (v12 & 1) == 0 )
        {
          v13 = *(_QWORD *)(v11 + 56);
          *(_DWORD *)(v11 + 64) = v12 | 1;
          TpPostWork(v13);
        }
        RtlReleaseSRWLockExclusive(v11 + 32);
        break;
      }
      v7 = *(_QWORD *)(v4 + 8);
      if ( v5 && v7 )
      {
LABEL_19:
        v4 ^= v7;
        continue;
      }
    }
    v4 = v7;
  }
LABEL_8:
  *((_DWORD *)a1 + 4) = 0;
  return RtlReleaseSRWLockExclusive(a1 + 1);
}

```

## disassembly

```asm
0x1800092d0  push    rbx
0x1800092d2  push    rbp
0x1800092d3  push    rsi
0x1800092d4  push    rdi
0x1800092d5  push    r14
0x1800092d7  push    r15
0x1800092d9  sub     rsp, 28h
0x1800092dd  mov     rdi, rcx
0x1800092e0  mov     r14, rdx
0x1800092e3  add     rcx, 8
0x1800092e7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800092ed  call    cs:__imp_GetCurrentThreadId
0x1800092f3  lea     r15, [rdi+18h]
0x1800092f7  mov     [rdi+10h], eax
0x1800092fa  test    byte ptr [r15+8], 1
0x1800092ff  mov     rbx, [r15]
0x180009302  jnz     loc_1800093D0
0x180009308  movzx   ebp, byte ptr [r15+8]
0x18000930d  and     ebp, 1
0x180009310  test    rbx, rbx
0x180009313  jz      short loc_18000933A
0x180009315  mov     rdx, rbx
0x180009318  mov     rcx, r14
0x18000931b  call    HampIpcChannelObjectComparePayloadForTree
0x180009320  test    eax, eax
0x180009322  js      short loc_180009358
0x180009324  jle     short loc_180009369
0x180009326  mov     rax, [rbx+8]
0x18000932a  test    ebp, ebp
0x18000932c  jnz     loc_1800093E1
0x180009332  mov     rbx, rax
0x180009335  test    rbx, rbx
0x180009338  jnz     short loc_180009315
0x18000933a  lea     rcx, [rdi+8]
0x18000933e  mov     dword ptr [rdi+10h], 0
0x180009345  add     rsp, 28h
0x180009349  pop     r15
0x18000934b  pop     r14
0x18000934d  pop     rdi
0x18000934e  pop     rsi
0x18000934f  pop     rbp
0x180009350  pop     rbx
0x180009351  jmp     cs:__imp_RtlReleaseSRWLockExclusive
0x180009358  mov     rax, [rbx]
0x18000935b  test    ebp, ebp
0x18000935d  jz      short loc_180009332
0x18000935f  test    rax, rax
0x180009362  jz      short loc_180009332
0x180009364  jmp     loc_1800093EA
0x180009369  test    rbx, rbx
0x18000936c  jz      short loc_18000933A
0x18000936e  mov     rdx, rbx
0x180009371  mov     rcx, r15
0x180009374  call    cs:__imp_RtlRbRemoveNode
0x18000937a  mov     rcx, [rdi+30h]
0x18000937e  lea     rax, [rdi+28h]
0x180009382  cmp     [rcx], rax
0x180009385  jnz     short loc_1800093F2
0x180009387  add     rbx, 18h
0x18000938b  mov     [rbx+8], rcx
0x18000938f  mov     [rbx], rax
0x180009392  mov     [rcx], rbx
0x180009395  mov     [rax+8], rbx
0x180009399  mov     rbx, [rdi]
0x18000939c  lea     rcx, [rbx+20h]
0x1800093a0  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800093a6  or      dword ptr [rbx+40h], 2
0x1800093aa  mov     eax, [rbx+40h]
0x1800093ad  test    al, 1
0x1800093af  jnz     short loc_1800093C1
0x1800093b1  mov     rcx, [rbx+38h]
0x1800093b5  or      eax, 1
0x1800093b8  mov     [rbx+40h], eax
0x1800093bb  call    cs:__imp_TpPostWork
0x1800093c1  lea     rcx, [rbx+20h]
0x1800093c5  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800093cb  jmp     loc_18000933A
0x1800093d0  test    rbx, rbx
0x1800093d3  jz      loc_18000933A
0x1800093d9  xor     rbx, r15
0x1800093dc  jmp     loc_180009308
0x1800093e1  test    rax, rax
0x1800093e4  jz      loc_180009332
0x1800093ea  xor     rbx, rax
0x1800093ed  jmp     loc_180009335
0x1800093f2  mov     ecx, 3
0x1800093f7  int     29h; Win8: RtlFailFast(ecx)
```
