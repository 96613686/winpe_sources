# _lambda_b53eba2d477466c9c18b3d9d5c4fa37a_::operator()

- ea: `0x14003bd34`
- end: `0x14003be54`
- name: `_lambda_b53eba2d477466c9c18b3d9d5c4fa37a_::operator()`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14003d2a8`

## callees

- `0x14000f81c`
- `0x14003bd34`

## import_xrefs

- `ntoskrnl!ExInterlockedInsertTailList` at `0x14003bdce`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14003bdce`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003bd9d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003be3c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003bd9d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003be3c`
- `ntoskrnl!KeSetEvent` at `0x14003be0c`
- `ntoskrnl!KeSetEvent` at `0x14003be0c`

## pseudocode

```c
void __fastcall lambda_b53eba2d477466c9c18b3d9d5c4fa37a_::operator()(struct _LIST_ENTRY ***a1)
{
  char v1; // dl
  struct _LIST_ENTRY *v3; // rbx
  struct _LIST_ENTRY **v4; // rax
  struct _LIST_ENTRY *v5; // rdi
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v7; // rbp
  utl::_RefCountBase *Blink; // rcx
  __int64 v9; // rcx
  utl::_RefCountBase *v10; // rcx

  v1 = 0;
  v3 = 0;
  while ( 1 )
  {
    v4 = *a1;
    v5 = **a1;
    if ( v5 == (struct _LIST_ENTRY *)*a1 )
      break;
    if ( (struct _LIST_ENTRY **)v5->Blink != v4 || (Flink = v5->Flink, v5->Flink->Blink != v5) )
      __fastfail(3u);
    v7 = v3;
    *v4 = Flink;
    Flink->Blink = (struct _LIST_ENTRY *)v4;
    v3 = v5 - 2;
    if ( v7 )
    {
      Blink = (utl::_RefCountBase *)v7[1].Blink;
      if ( Blink )
        utl::_RefCountBase::_DecStrong(Blink);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1088), v7);
    }
    if ( *((_BYTE *)UnionFs::g_FilterState + 192) )
    {
      v3 = 0;
      ExInterlockedInsertTailList(
        (PLIST_ENTRY)((char *)UnionFs::g_FilterState + 168),
        v5,
        (PKSPIN_LOCK)UnionFs::g_FilterState + 23);
    }
    v1 = 1;
  }
  if ( v1 )
  {
    v9 = *((_QWORD *)UnionFs::g_FilterState + 15);
    if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 8), 1u) )
      KeSetEvent((PRKEVENT)(v9 + 16), 0, 0);
  }
  if ( v3 )
  {
    v10 = (utl::_RefCountBase *)v3[1].Blink;
    if ( v10 )
      utl::_RefCountBase::_DecStrong(v10);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1088), v3);
  }
}

```

## disassembly

```asm
0x14003bd34  push    rbx
0x14003bd36  push    rbp
0x14003bd37  push    rsi
0x14003bd38  push    rdi
0x14003bd39  push    r14
0x14003bd3b  sub     rsp, 20h
0x14003bd3f  xor     dl, dl
0x14003bd41  mov     r14, rcx
0x14003bd44  xor     ebx, ebx
0x14003bd46  lea     esi, [rbx+1]
0x14003bd49  mov     rax, [r14]
0x14003bd4c  mov     rdi, [rax]
0x14003bd4f  cmp     rdi, rax
0x14003bd52  jz      loc_14003BDE9
0x14003bd58  cmp     [rdi+8], rax
0x14003bd5c  jnz     loc_14003BDE2
0x14003bd62  mov     rcx, [rdi]
0x14003bd65  cmp     [rcx+8], rdi
0x14003bd69  jnz     short loc_14003BDE2
0x14003bd6b  mov     rbp, rbx
0x14003bd6e  mov     [rax], rcx
0x14003bd71  mov     [rcx+8], rax
0x14003bd75  lea     rbx, [rdi-20h]
0x14003bd79  test    rbp, rbp
0x14003bd7c  jz      short loc_14003BDA9
0x14003bd7e  mov     rcx, [rbp+18h]; this
0x14003bd82  test    rcx, rcx
0x14003bd85  jz      short loc_14003BD8C
0x14003bd87  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003bd8c  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003bd93  mov     rdx, rbp; Entry
0x14003bd96  add     rcx, 440h; Lookaside
0x14003bd9d  call    cs:__imp_ExFreeToLookasideListEx
0x14003bda4  nop     dword ptr [rax+rax+00h]
0x14003bda9  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003bdb0  mov     al, [rcx+0C0h]
0x14003bdb6  nop
0x14003bdb7  test    al, al
0x14003bdb9  jz      short loc_14003BDDA
0x14003bdbb  lea     r8, [rcx+0B8h]; Lock
0x14003bdc2  xor     ebx, ebx
0x14003bdc4  add     rcx, 0A8h; ListHead
0x14003bdcb  mov     rdx, rdi; ListEntry
0x14003bdce  call    cs:__imp_ExInterlockedInsertTailList
0x14003bdd5  nop     dword ptr [rax+rax+00h]
0x14003bdda  mov     dl, sil
0x14003bddd  jmp     loc_14003BD49
0x14003bde2  mov     ecx, 3
0x14003bde7  int     29h; Win8: RtlFailFast(ecx)
0x14003bde9  test    dl, dl
0x14003bdeb  jz      short loc_14003BE18
0x14003bded  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003bdf4  mov     rcx, [rax+78h]
0x14003bdf8  nop
0x14003bdf9  lock xadd [rcx+8], esi
0x14003bdfe  nop
0x14003bdff  test    esi, esi
0x14003be01  jnz     short loc_14003BE18
0x14003be03  add     rcx, 10h; Event
0x14003be07  xor     r8d, r8d; Wait
0x14003be0a  xor     edx, edx; Increment
0x14003be0c  call    cs:__imp_KeSetEvent
0x14003be13  nop     dword ptr [rax+rax+00h]
0x14003be18  test    rbx, rbx
0x14003be1b  jz      short loc_14003BE48
0x14003be1d  mov     rcx, [rbx+18h]; this
0x14003be21  test    rcx, rcx
0x14003be24  jz      short loc_14003BE2B
0x14003be26  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003be2b  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003be32  mov     rdx, rbx; Entry
0x14003be35  add     rcx, 440h; Lookaside
0x14003be3c  call    cs:__imp_ExFreeToLookasideListEx
0x14003be43  nop     dword ptr [rax+rax+00h]
0x14003be48  add     rsp, 20h
0x14003be4c  pop     r14
0x14003be4e  pop     rdi
0x14003be4f  pop     rsi
0x14003be50  pop     rbp
0x14003be51  pop     rbx
0x14003be52  retn
```
