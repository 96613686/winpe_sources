# NavigationNodeBase::ComparePositions(NavigationNodeBase *,ulong,NavigationNodeBase *,ulong)

- ea: `0x180011064`
- end: `0x1800110d5`
- name: `?ComparePositions@NavigationNodeBase@@SAJPEAV1@K0K@Z`
- size: `113`
- prototype: `__int64 __fastcall(struct NavigationNodeBase *, unsigned int, struct NavigationNodeBase *, unsigned int)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002700`
- `0x180004980`
- `0x180005f10`
- `0x180006bd0`
- `0x180009160`

## callees

- `0x180011064`
- `0x1800110dc`
- `0x1800112fc`
- `0x180012f3c`

## pseudocode

```c
__int64 __fastcall NavigationNodeBase::ComparePositions(
        struct NavigationNodeBase *a1,
        unsigned int a2,
        struct NavigationNodeBase *a3,
        unsigned int a4)
{
  struct NavigationNodeBase *Ancestor; // rax
  int v6; // r8d
  __int64 result; // rax
  int pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  Ancestor = a3;
  if ( a2 >= a4 )
  {
    v6 = 0;
  }
  else
  {
    Ancestor = NavigationNodeBase::QueryAncestor(a3, a4 - a2);
    if ( !Ancestor )
    {
      pExceptionObject = -2147024809;
      throw (long *)&pExceptionObject;
    }
    v6 = -1;
  }
  result = NavigationNodeBase::ComparePositionsAtSameDepth(a1, Ancestor, v6);
  if ( (int)result > 0 )
    return 1;
  if ( (int)result < 0 )
    return 0xFFFFFFFFLL;
  return result;
}

```

## disassembly

```asm
0x180011064  mov     [rsp+arg_0], rbx
0x180011069  push    rdi
0x18001106a  sub     rsp, 20h
0x18001106e  or      edi, 0FFFFFFFFh
0x180011071  mov     rax, r8
0x180011074  mov     rbx, rcx
0x180011077  cmp     edx, r9d
0x18001107a  jnb     short loc_1800110AE
0x18001107c  sub     r9d, edx
0x18001107f  mov     rcx, rax; this
0x180011082  mov     edx, r9d; unsigned int
0x180011085  call    ?QueryAncestor@NavigationNodeBase@@QEAAPEAV1@K@Z; NavigationNodeBase::QueryAncestor(ulong)
0x18001108a  test    rax, rax
0x18001108d  jnz     short loc_1800110A9
0x18001108f  lea     rdx, _TI1J; pThrowInfo
0x180011096  mov     [rsp+28h+pExceptionObject], 80070057h
0x18001109e  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800110a3  call    _CxxThrowException_0
0x1800110a9  mov     r8d, edi
0x1800110ac  jmp     short loc_1800110B1
0x1800110ae  xor     r8d, r8d; int
0x1800110b1  mov     rdx, rax; struct NavigationNodeBase *
0x1800110b4  mov     rcx, rbx; struct NavigationNodeBase *
0x1800110b7  call    ?ComparePositionsAtSameDepth@NavigationNodeBase@@CAJPEAV1@0J@Z; NavigationNodeBase::ComparePositionsAtSameDepth(NavigationNodeBase *,NavigationNodeBase *,long)
0x1800110bc  test    eax, eax
0x1800110be  jle     short loc_1800110C7
0x1800110c0  mov     eax, 1
0x1800110c5  jmp     short loc_1800110CA
0x1800110c7  cmovs   eax, edi
0x1800110ca  mov     rbx, [rsp+28h+arg_0]
0x1800110cf  add     rsp, 20h
0x1800110d3  pop     rdi
0x1800110d4  retn
```
