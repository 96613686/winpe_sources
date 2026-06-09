# Streaming::PendingQueue::~PendingQueue(void)

- ea: `0x1400053e8`
- end: `0x140005492`
- name: `??1PendingQueue@Streaming@@QEAA@XZ`
- size: `170`
- prototype: `void __fastcall(Streaming::PendingQueue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005b20`
- `0x140007b40`

## callees

- `0x1400053e8`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140005464`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140005464`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140005453`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140005453`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400053f9`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400053f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000547a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000547a`

## pseudocode

```c
void __fastcall Streaming::PendingQueue::~PendingQueue(Streaming::PendingQueue *this)
{
  volatile signed __int32 *v2; // rbx
  struct _RTL_AVL_TABLE *v3; // rcx
  PVOID v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx

  ExDeleteResourceLite((PERESOURCE)((char *)this + 8));
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 15);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 16LL))(v2);
    }
  }
  v3 = *(struct _RTL_AVL_TABLE **)this;
  if ( *(_QWORD *)this )
  {
    while ( 1 )
    {
      v4 = RtlEnumerateGenericTableAvl(v3, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)this;
      if ( !v4 )
        break;
      RtlDeleteElementGenericTableAvl(v5, v4);
      v3 = *(struct _RTL_AVL_TABLE **)this;
    }
    ExFreePoolWithTag(v5, 0);
  }
}

```

## disassembly

```asm
0x1400053e8  mov     [rsp+arg_0], rbx
0x1400053ed  push    rdi
0x1400053ee  sub     rsp, 20h
0x1400053f2  mov     rdi, rcx
0x1400053f5  add     rcx, 8; Resource
0x1400053f9  call    cs:__imp_ExDeleteResourceLite
0x140005400  nop     dword ptr [rax+rax+00h]
0x140005405  mov     rbx, [rdi+78h]
0x140005409  test    rbx, rbx
0x14000540c  jz      short loc_140005446
0x14000540e  or      eax, 0FFFFFFFFh
0x140005411  lock xadd [rbx+8], eax
0x140005416  cmp     eax, 1
0x140005419  jnz     short loc_140005446
0x14000541b  mov     rax, [rbx]
0x14000541e  mov     rcx, rbx
0x140005421  mov     rax, [rax+8]
0x140005425  call    _guard_dispatch_icall
0x14000542a  or      eax, 0FFFFFFFFh
0x14000542d  lock xadd [rbx+0Ch], eax
0x140005432  cmp     eax, 1
0x140005435  jnz     short loc_140005446
0x140005437  mov     rax, [rbx]
0x14000543a  mov     rcx, rbx
0x14000543d  mov     rax, [rax+10h]
0x140005441  call    _guard_dispatch_icall
0x140005446  mov     rcx, [rdi]
0x140005449  test    rcx, rcx
0x14000544c  jz      short loc_140005486
0x14000544e  jmp     short loc_140005462
0x140005450  mov     rdx, rax; Buffer
0x140005453  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14000545a  nop     dword ptr [rax+rax+00h]
0x14000545f  mov     rcx, [rdi]; Table
0x140005462  mov     dl, 1; Restart
0x140005464  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14000546b  nop     dword ptr [rax+rax+00h]
0x140005470  mov     rcx, [rdi]; P
0x140005473  test    rax, rax
0x140005476  jnz     short loc_140005450
0x140005478  xor     edx, edx; Tag
0x14000547a  call    cs:__imp_ExFreePoolWithTag
0x140005481  nop     dword ptr [rax+rax+00h]
0x140005486  mov     rbx, [rsp+28h+arg_0]
0x14000548b  add     rsp, 20h
0x14000548f  pop     rdi
0x140005490  retn
```
