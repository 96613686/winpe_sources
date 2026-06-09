# MsDeleteTransactionContext

- ea: `0x140047580`
- end: `0x140047720`
- name: `MsDeleteTransactionContext`
- size: `416`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d820`
- `0x1400aa590`
- `0x1400b6650`
- `0x1400bce90`
- `0x1400bee50`
- `0x14015c200`
- `0x14028e0ec`
- `0x1402e7094`
- `0x140302eb0`

## callees

- `0x140047580`
- `0x140047730`
- `0x14011d3a8`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140047635`
- `ntoskrnl!KeSetEvent` at `0x140047635`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400475d8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400475d8`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14004765b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14004765b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400476e8`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400476e8`
- `ntoskrnl!ExReleasePushLockEx` at `0x14004764a`
- `ntoskrnl!ExReleasePushLockEx` at `0x14004764a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047701`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047701`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400476b0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400476b0`

## pseudocode

```c
void __fastcall MsDeleteTransactionContext(CmsTransactionContext *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  struct _SLIST_ENTRY *v4; // rdi
  struct _SLIST_ENTRY *Next; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v6; // rcx
  __int64 v7; // rcx
  signed __int32 v8; // ett
  unsigned int i; // ecx
  __int64 v10; // rbx
  __int64 v11; // rcx

  v2 = *(_QWORD *)a1 & 0x10000000LL;
  v3 = *((_QWORD *)a1 + 1);
  CmsTransactionContext::~CmsTransactionContext(a1);
  if ( !v2 )
  {
    v4 = (struct _SLIST_ENTRY *)((char *)a1 - 16);
    Next = v4->Next;
    if ( v4->Next )
    {
      if ( *((_BYTE *)&Next->Next + 8) )
      {
        v6 = (struct _NPAGED_LOOKASIDE_LIST *)&Next[4];
        if ( *((_BYTE *)&Next->Next + 9) )
          ExFreeToNPagedLookasideList(v6, v4);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v6, v4);
        return;
      }
      v11 = *((_QWORD *)&Next[5].Next + 1);
      if ( (int)v11 < SLODWORD(Next[5].Next) || SHIDWORD(v11) >= (int)v11 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)&Next[4], v4);
        _InterlockedIncrement((volatile signed __int32 *)&Next[5].Next + 2);
        return;
      }
    }
    ExFreePoolWithTag(v4, 0);
    return;
  }
  if ( *(_DWORD *)(v3 + 172) )
  {
    for ( i = 0; i < *(_DWORD *)(v3 + 168); ++i )
    {
      v10 = 16LL * i;
      if ( *(CmsTransactionContext **)(v10 + *(_QWORD *)(v3 + 160)) == a1 )
      {
        if ( *(_BYTE *)(v3 + 216) )
          ExAcquirePushLockExclusiveEx(v3 + 208, 0);
        v7 = *(_QWORD *)(v3 + 160);
        do
          v8 = *(_DWORD *)(v10 + v7 + 8);
        while ( v8 != _InterlockedCompareExchange((volatile signed __int32 *)(v10 + v7 + 8), v8 & 0xFFFFFFFE, v8) );
        _InterlockedDecrement((volatile signed __int32 *)(v3 + 172));
        if ( *(_BYTE *)(v3 + 216) )
        {
          KeSetEvent((PRKEVENT)(v3 + 184), 0, 0);
          ExReleasePushLockEx(v3 + 208, 0);
        }
        return;
      }
    }
  }
}

```

## disassembly

```asm
0x140047580  mov     [rsp+arg_0], rbx
0x140047585  mov     [rsp+arg_10], rsi
0x14004758a  push    rdi
0x14004758b  sub     rsp, 30h
0x14004758f  mov     rdi, rcx
0x140047592  mov     rbx, [rcx]
0x140047595  and     ebx, 10000000h
0x14004759b  mov     rsi, [rcx+8]
0x14004759f  call    ??1CmsTransactionContext@@AEAA@XZ; CmsTransactionContext::~CmsTransactionContext(void)
0x1400475a4  test    rbx, rbx
0x1400475a7  jnz     loc_14004766C
0x1400475ad  add     rdi, 0FFFFFFFFFFFFFFF0h
0x1400475b1  mov     rbx, [rdi]
0x1400475b4  test    rbx, rbx
0x1400475b7  jz      loc_1400476FC
0x1400475bd  cmp     byte ptr [rbx+8], 0
0x1400475c1  jz      loc_1400476C1
0x1400475c7  lea     rcx, [rbx+40h]; Lookaside
0x1400475cb  mov     rdx, rdi; Entry
0x1400475ce  cmp     byte ptr [rbx+9], 0
0x1400475d2  jz      loc_14004765B
0x1400475d8  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400475df  nop     dword ptr [rax+rax+00h]
0x1400475e4  jmp     loc_14004770D
0x1400475e9  cmp     byte ptr [rsi+0D8h], 0
0x1400475f0  jnz     loc_1400476A7
0x1400475f6  mov     rcx, [rsi+0A0h]
0x1400475fd  nop     dword ptr [rax]
0x140047600  mov     eax, [rbx+rcx+8]
0x140047604  mov     edx, eax
0x140047606  and     edx, 0FFFFFFFEh
0x140047609  nop
0x14004760a  lock cmpxchg [rbx+rcx+8], edx
0x140047610  nop
0x140047611  jnz     short loc_140047600
0x140047613  nop
0x140047614  lock dec dword ptr [rsi+0ACh]
0x14004761b  nop
0x14004761c  cmp     byte ptr [rsi+0D8h], 0
0x140047623  jz      loc_14004770D
0x140047629  lea     rcx, [rsi+0B8h]; Event
0x140047630  xor     r8d, r8d; Wait
0x140047633  xor     edx, edx; Increment
0x140047635  call    cs:__imp_KeSetEvent
0x14004763c  nop     dword ptr [rax+rax+00h]
0x140047641  lea     rcx, [rsi+0D0h]
0x140047648  xor     edx, edx
0x14004764a  call    cs:__imp_ExReleasePushLockEx
0x140047651  nop     dword ptr [rax+rax+00h]
0x140047656  jmp     loc_14004770D
0x14004765b  call    cs:__imp_ExFreeToPagedLookasideList
0x140047662  nop     dword ptr [rax+rax+00h]
0x140047667  jmp     loc_14004770D
0x14004766c  mov     eax, [rsi+0ACh]
0x140047672  test    eax, eax
0x140047674  jz      loc_14004770D
0x14004767a  xor     ecx, ecx
0x14004767c  mov     [rsp+38h+var_18], ecx
0x140047680  cmp     ecx, [rsi+0A8h]
0x140047686  jnb     loc_14004770D
0x14004768c  mov     ebx, ecx
0x14004768e  shl     rbx, 4
0x140047692  mov     rax, [rsi+0A0h]
0x140047699  cmp     [rbx+rax], rdi
0x14004769d  jz      loc_1400475E9
0x1400476a3  inc     ecx
0x1400476a5  jmp     short loc_14004767C
0x1400476a7  lea     rcx, [rsi+0D0h]
0x1400476ae  xor     edx, edx
0x1400476b0  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400476b7  nop     dword ptr [rax+rax+00h]
0x1400476bc  jmp     loc_1400475F6
0x1400476c1  xor     ecx, ecx
0x1400476c3  mov     [rsp+38h+arg_8], rcx
0x1400476c8  mov     rcx, [rbx+58h]
0x1400476cc  mov     [rsp+38h+arg_8], rcx
0x1400476d1  cmp     ecx, [rbx+50h]
0x1400476d4  jl      short loc_1400476E1
0x1400476d6  mov     rax, rcx
0x1400476d9  shr     rax, 20h
0x1400476dd  cmp     eax, ecx
0x1400476df  jl      short loc_1400476FC
0x1400476e1  lea     rcx, [rbx+40h]; ListHead
0x1400476e5  mov     rdx, rdi; ListEntry
0x1400476e8  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400476ef  nop     dword ptr [rax+rax+00h]
0x1400476f4  nop
0x1400476f5  lock inc dword ptr [rbx+58h]
0x1400476f9  nop
0x1400476fa  jmp     short loc_14004770D
0x1400476fc  xor     edx, edx; Tag
0x1400476fe  mov     rcx, rdi; P
0x140047701  call    cs:__imp_ExFreePoolWithTag
0x140047708  nop     dword ptr [rax+rax+00h]
0x14004770d  jmp     short $+2
0x14004770f  mov     rbx, [rsp+38h+arg_0]
0x140047714  mov     rsi, [rsp+38h+arg_10]
0x140047719  add     rsp, 30h
0x14004771d  pop     rdi
0x14004771e  retn
0x1401f5180  push    rbp
0x1401f5182  sub     rsp, 20h
0x1401f5186  mov     rbp, rdx
0x1401f5189  call    ?MinstoreBugcheckExceptionFilter@@YAXPEAU_EXCEPTION_POINTERS@@@Z; MinstoreBugcheckExceptionFilter(_EXCEPTION_POINTERS *)
0x1401f518f  add     rsp, 20h
0x1401f5193  pop     rbp
0x1401f5194  retn
```
