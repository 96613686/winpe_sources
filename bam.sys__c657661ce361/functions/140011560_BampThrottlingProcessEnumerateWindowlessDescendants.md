# BampThrottlingProcessEnumerateWindowlessDescendants

- ea: `0x140011560`
- end: `0x140011659`
- name: `BampThrottlingProcessEnumerateWindowlessDescendants`
- size: `249`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001044c`
- `0x140013d40`

## callees

- `0x140011560`
- `0x140011660`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400115a8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400115a8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400115ba`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400115ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011601`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011601`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400115f5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400115f5`

## pseudocode

```c
char __fastcall BampThrottlingProcessEnumerateWindowlessDescendants(_QWORD *a1, __int64 a2, int **a3)
{
  _QWORD *v3; // rbx
  _QWORD *v4; // rax
  _QWORD *v7; // rbx
  bool v8; // di
  _QWORD *v9; // rdx
  _QWORD *v10; // rdx

  v3 = (_QWORD *)a1[4];
  LOBYTE(v4) = (_BYTE)a1 + 32;
  if ( v3 != a1 + 4 )
  {
    v7 = v3 - 6;
    v8 = 0;
    while ( v7 != a1 )
    {
      if ( v8
        || (KeEnterCriticalRegion(),
            ExAcquirePushLockExclusiveEx(v7 + 2, 0),
            v7[3] = KeGetCurrentThread(),
            LOBYTE(v4) = BampThrottlingProcessPropagateStateToChildren((__int64)v7, a3),
            v9 = (_QWORD *)v7[4],
            v9 == v7 + 4)
        || !(_BYTE)v4 )
      {
        v7[3] = 0;
        ExReleasePushLockExclusiveEx(v7 + 2, 0);
        KeLeaveCriticalRegion();
        v10 = (_QWORD *)v7[8];
        v4 = (_QWORD *)v7[6];
        v7 = v4 - 6;
        if ( v4 == v10 + 4 )
          v7 = v10;
        v8 = v4 == v10 + 4;
      }
      else
      {
        v7 = v9 - 6;
      }
    }
  }
  return (char)v4;
}

```

## disassembly

```asm
0x140011560  mov     [rsp+arg_10], rbx
0x140011565  mov     [rsp+arg_18], rbp
0x14001156a  push    rsi
0x14001156b  sub     rsp, 20h
0x14001156f  mov     rbx, [rcx+20h]
0x140011573  lea     rax, [rcx+20h]
0x140011577  mov     rbp, r8
0x14001157a  mov     rsi, rcx
0x14001157d  cmp     rbx, rax
0x140011580  jz      loc_140011639
0x140011586  mov     [rsp+28h+arg_0], rdi
0x14001158b  add     rbx, 0FFFFFFFFFFFFFFD0h
0x14001158f  xor     dil, dil
0x140011592  cmp     rbx, rcx
0x140011595  jz      loc_140011634
0x14001159b  mov     [rsp+28h+arg_8], r14
0x1400115a0  xor     r14d, r14d
0x1400115a3  test    dil, dil
0x1400115a6  jnz     short loc_1400115EB
0x1400115a8  call    cs:__imp_KeEnterCriticalRegion
0x1400115af  nop     dword ptr [rax+rax+00h]
0x1400115b4  lea     rcx, [rbx+10h]
0x1400115b8  xor     edx, edx
0x1400115ba  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400115c1  nop     dword ptr [rax+rax+00h]
0x1400115c6  mov     rax, gs:188h
0x1400115cf  mov     rdx, rbp
0x1400115d2  mov     rcx, rbx
0x1400115d5  mov     [rbx+18h], rax
0x1400115d9  call    BampThrottlingProcessPropagateStateToChildren
0x1400115de  mov     rdx, [rbx+20h]
0x1400115e2  lea     rcx, [rbx+20h]
0x1400115e6  cmp     rdx, rcx
0x1400115e9  jnz     short loc_14001164F
0x1400115eb  lea     rcx, [rbx+10h]
0x1400115ef  mov     [rbx+18h], r14
0x1400115f3  xor     edx, edx
0x1400115f5  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400115fc  nop     dword ptr [rax+rax+00h]
0x140011601  call    cs:__imp_KeLeaveCriticalRegion
0x140011608  nop     dword ptr [rax+rax+00h]
0x14001160d  mov     rdx, [rbx+40h]
0x140011611  mov     rax, [rbx+30h]
0x140011615  lea     rcx, [rdx+20h]
0x140011619  lea     rbx, [rax-30h]
0x14001161d  cmp     rax, rcx
0x140011620  jz      short loc_14001164A
0x140011622  setz    dil
0x140011626  cmp     rbx, rsi
0x140011629  jnz     loc_1400115A3
0x14001162f  mov     r14, [rsp+28h+arg_8]
0x140011634  mov     rdi, [rsp+28h+arg_0]
0x140011639  mov     rbx, [rsp+28h+arg_10]
0x14001163e  mov     rbp, [rsp+28h+arg_18]
0x140011643  add     rsp, 20h
0x140011647  pop     rsi
0x140011648  retn
0x14001164a  mov     rbx, rdx
0x14001164d  jmp     short loc_140011622
0x14001164f  test    al, al
0x140011651  jz      short loc_1400115EB
0x140011653  lea     rbx, [rdx-30h]
0x140011657  jmp     short loc_140011626
```
