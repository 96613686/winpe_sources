# CILogCreateStorage2A::CreateStream(char *)

- ea: `0x180002370`
- end: `0x1800023ed`
- name: `?CreateStream@CILogCreateStorage2A@@UEAAJPEAD@Z`
- size: `125`
- prototype: `__int64 __fastcall(CILogCreateStorage2A *__hidden this, char *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002370`
- `0x1800042b4`
- `0x1800045f4`

## pseudocode

```c
__int64 __fastcall CILogCreateStorage2A::CreateStream(CILogCreateStorage2A *this, char *a2)
{
  __int64 v4; // rcx
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF
  struct _STRMTBL *v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  v6 = 0;
  if ( !a2 )
    return 2147942487LL;
  v4 = *((_QWORD *)this + 1);
  if ( !v4 )
    return 2147549183LL;
  CILogStorage::FindStream((CILogStorage *)(v4 + 96), a2, &v7, &v6);
  if ( v7 )
    return 2147942487LL;
  else
    return CILogStorage::AddStream((CILogStorage *)(*((_QWORD *)this + 1) + 96LL), a2, &v7, &v6);
}

```

## disassembly

```asm
0x180002370  mov     [rsp+arg_0], rbx
0x180002375  push    rdi
0x180002376  sub     rsp, 20h
0x18000237a  mov     [rsp+28h+arg_10], 0
0x180002383  mov     rbx, rdx
0x180002386  mov     [rsp+28h+arg_8], 0
0x18000238e  mov     rdi, rcx
0x180002391  test    rdx, rdx
0x180002394  jz      short loc_1800023DD
0x180002396  mov     rcx, [rcx+8]
0x18000239a  test    rcx, rcx
0x18000239d  jnz     short loc_1800023A6
0x18000239f  mov     eax, 8000FFFFh
0x1800023a4  jmp     short loc_1800023E2
0x1800023a6  add     rcx, 60h ; '`'; this
0x1800023aa  lea     r9, [rsp+28h+arg_8]; unsigned int *
0x1800023af  lea     r8, [rsp+28h+arg_10]; struct _STRMTBL **
0x1800023b4  call    ?FindStream@CILogStorage@@AEAAJPEADPEAPEAU_STRMTBL@@PEAK@Z; CILogStorage::FindStream(char *,_STRMTBL * *,ulong *)
0x1800023b9  cmp     [rsp+28h+arg_10], 0
0x1800023bf  jnz     short loc_1800023DD
0x1800023c1  mov     rcx, [rdi+8]
0x1800023c5  lea     r9, [rsp+28h+arg_8]; unsigned int *
0x1800023ca  add     rcx, 60h ; '`'; this
0x1800023ce  lea     r8, [rsp+28h+arg_10]; struct _STRMTBL **
0x1800023d3  mov     rdx, rbx; char *
0x1800023d6  call    ?AddStream@CILogStorage@@AEAAJPEADPEAPEAU_STRMTBL@@PEAK@Z; CILogStorage::AddStream(char *,_STRMTBL * *,ulong *)
0x1800023db  jmp     short loc_1800023E2
0x1800023dd  mov     eax, 80070057h
0x1800023e2  mov     rbx, [rsp+28h+arg_0]
0x1800023e7  add     rsp, 20h
0x1800023eb  pop     rdi
0x1800023ec  retn
```
