# CMILResourceCache::EnsureCount(uint)

- ea: `0x18001ed54`
- end: `0x18001ee24`
- name: `?EnsureCount@CMILResourceCache@@IEAAJI@Z`
- size: `208`
- prototype: `__int64 __fastcall(CMILResourceCache *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001ec70`

## callees

- `0x18000efc0`
- `0x1800171c4`
- `0x18001ed54`
- `0x180022348`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18001ed86`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18001ed86`

## pseudocode

```c
__int64 __fastcall CMILResourceCache::EnsureCount(CMILResourceCache *this, unsigned int a2)
{
  unsigned int v2; // edi
  unsigned int *v5; // rsi
  unsigned int v6; // ebp
  int v7; // eax
  signed __int32 v8; // edx

  _InterlockedDecrement((volatile signed __int32 *)this + 14);
  v2 = 0;
  while ( _InterlockedCompareExchange((volatile signed __int32 *)this + 14, 0x80000000, 0) )
    SleepEx(0, 1);
  v5 = (unsigned int *)((char *)this + 32);
  if ( a2 > *((_DWORD *)this + 8) )
  {
    v6 = a2 - *v5;
    if ( a2 <= *((_DWORD *)this + 7) || (v7 = DynArrayImpl<0>::Grow((_QWORD *)this + 1, 8u, v6, 1, 0), v2 = v7, v7 >= 0) )
    {
      memset_0((void *)(*((_QWORD *)this + 1) + 8LL * *v5), 0, 8LL * v6);
      *v5 = a2;
    }
    else if ( g_doStackCaptures )
    {
      DoStackCapture(v7);
    }
  }
  do
    v8 = *((_DWORD *)this + 14);
  while ( v8 != _InterlockedCompareExchange((volatile signed __int32 *)this + 14, v8 - 0x7FFFFFFF, v8) );
  return v2;
}

```

## disassembly

```asm
0x18001ed54  push    rbx
0x18001ed56  push    rbp
0x18001ed57  push    rsi
0x18001ed58  push    rdi
0x18001ed59  push    r12
0x18001ed5b  push    r14
0x18001ed5d  push    r15
0x18001ed5f  sub     rsp, 30h
0x18001ed63  lock dec dword ptr [rcx+38h]
0x18001ed67  xor     edi, edi
0x18001ed69  mov     r14d, edx
0x18001ed6c  mov     rbx, rcx
0x18001ed6f  mov     esi, 80000000h
0x18001ed74  xor     eax, eax
0x18001ed76  lea     r15d, [rdi+1]
0x18001ed7a  lock cmpxchg [rcx+38h], esi
0x18001ed7f  jz      short loc_18001ED95
0x18001ed81  mov     edx, r15d; bAlertable
0x18001ed84  xor     ecx, ecx; dwMilliseconds
0x18001ed86  call    cs:__imp_SleepEx
0x18001ed8c  xor     eax, eax
0x18001ed8e  lock cmpxchg [rbx+38h], esi
0x18001ed93  jnz     short loc_18001ED81
0x18001ed95  lea     rsi, [rbx+20h]
0x18001ed99  cmp     r14d, [rsi]
0x18001ed9c  jbe     short loc_18001EDFF
0x18001ed9e  mov     ebp, r14d
0x18001eda1  lea     r12, [rbx+8]
0x18001eda5  sub     ebp, [rsi]
0x18001eda7  cmp     r14d, [rbx+1Ch]
0x18001edab  jbe     short loc_18001EDE1
0x18001edad  mov     r9d, r15d
0x18001edb0  mov     [rsp+68h+var_48], rdi
0x18001edb5  mov     r8d, ebp
0x18001edb8  mov     edx, 8
0x18001edbd  mov     rcx, r12
0x18001edc0  call    ?Grow@?$DynArrayImpl@$0A@@@IEAAJIIHPEAPEBX@Z; DynArrayImpl<0>::Grow(uint,uint,int,void const * *)
0x18001edc5  mov     edi, eax
0x18001edc7  test    eax, eax
0x18001edc9  jns     short loc_18001EDE1
0x18001edcb  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001edd2  jz      short loc_18001EDDD
0x18001edd4  mov     ecx, eax; int
0x18001edd6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001eddb  jmp     short loc_18001EDFF
0x18001eddd  test    eax, eax
0x18001eddf  js      short loc_18001EDFF
0x18001ede1  mov     ecx, [rsi]
0x18001ede3  xor     edx, edx; Val
0x18001ede5  mov     rax, [r12]
0x18001ede9  mov     r15, rsi
0x18001edec  mov     r8d, ebp
0x18001edef  shl     r8, 3; Size
0x18001edf3  lea     rcx, [rax+rcx*8]; void *
0x18001edf7  call    memset_0
0x18001edfc  mov     [rsi], r14d
0x18001edff  mov     edx, [rbx+38h]
0x18001ee02  mov     eax, edx
0x18001ee04  lea     ecx, [rdx-7FFFFFFFh]
0x18001ee0a  lock cmpxchg [rbx+38h], ecx
0x18001ee0f  cmp     edx, eax
0x18001ee11  jnz     short loc_18001EDFF
0x18001ee13  mov     eax, edi
0x18001ee15  add     rsp, 30h
0x18001ee19  pop     r15
0x18001ee1b  pop     r14
0x18001ee1d  pop     r12
0x18001ee1f  pop     rdi
0x18001ee20  pop     rsi
0x18001ee21  pop     rbp
0x18001ee22  pop     rbx
0x18001ee23  retn
```
