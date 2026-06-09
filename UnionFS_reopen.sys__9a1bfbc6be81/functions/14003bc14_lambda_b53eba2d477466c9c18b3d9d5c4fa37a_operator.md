# _lambda_b53eba2d477466c9c18b3d9d5c4fa37a_::operator()

- ea: `0x14003bc14`
- end: `0x14003bd34`
- name: `_lambda_b53eba2d477466c9c18b3d9d5c4fa37a_::operator()`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14003d188`

## callees

- `0x14000f7fc`
- `0x14003bc14`

## import_xrefs

- `ntoskrnl!ExInterlockedInsertTailList` at `0x14003bcae`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14003bcae`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003bc7d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003bd1c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003bc7d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003bd1c`
- `ntoskrnl!KeSetEvent` at `0x14003bcec`
- `ntoskrnl!KeSetEvent` at `0x14003bcec`

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
0x14003bc14  push    rbx
0x14003bc16  push    rbp
0x14003bc17  push    rsi
0x14003bc18  push    rdi
0x14003bc19  push    r14
0x14003bc1b  sub     rsp, 20h
0x14003bc1f  xor     dl, dl
0x14003bc21  mov     r14, rcx
0x14003bc24  xor     ebx, ebx
0x14003bc26  lea     esi, [rbx+1]
0x14003bc29  mov     rax, [r14]
0x14003bc2c  mov     rdi, [rax]
0x14003bc2f  cmp     rdi, rax
0x14003bc32  jz      loc_14003BCC9
0x14003bc38  cmp     [rdi+8], rax
0x14003bc3c  jnz     loc_14003BCC2
0x14003bc42  mov     rcx, [rdi]
0x14003bc45  cmp     [rcx+8], rdi
0x14003bc49  jnz     short loc_14003BCC2
0x14003bc4b  mov     rbp, rbx
0x14003bc4e  mov     [rax], rcx
0x14003bc51  mov     [rcx+8], rax
0x14003bc55  lea     rbx, [rdi-20h]
0x14003bc59  test    rbp, rbp
0x14003bc5c  jz      short loc_14003BC89
0x14003bc5e  mov     rcx, [rbp+18h]; this
0x14003bc62  test    rcx, rcx
0x14003bc65  jz      short loc_14003BC6C
0x14003bc67  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003bc6c  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003bc73  mov     rdx, rbp; Entry
0x14003bc76  add     rcx, 440h; Lookaside
0x14003bc7d  call    cs:__imp_ExFreeToLookasideListEx
0x14003bc84  nop     dword ptr [rax+rax+00h]
0x14003bc89  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003bc90  mov     al, [rcx+0C0h]
0x14003bc96  nop
0x14003bc97  test    al, al
0x14003bc99  jz      short loc_14003BCBA
0x14003bc9b  lea     r8, [rcx+0B8h]; Lock
0x14003bca2  xor     ebx, ebx
0x14003bca4  add     rcx, 0A8h; ListHead
0x14003bcab  mov     rdx, rdi; ListEntry
0x14003bcae  call    cs:__imp_ExInterlockedInsertTailList
0x14003bcb5  nop     dword ptr [rax+rax+00h]
0x14003bcba  mov     dl, sil
0x14003bcbd  jmp     loc_14003BC29
0x14003bcc2  mov     ecx, 3
0x14003bcc7  int     29h; Win8: RtlFailFast(ecx)
0x14003bcc9  test    dl, dl
0x14003bccb  jz      short loc_14003BCF8
0x14003bccd  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003bcd4  mov     rcx, [rax+78h]
0x14003bcd8  nop
0x14003bcd9  lock xadd [rcx+8], esi
0x14003bcde  nop
0x14003bcdf  test    esi, esi
0x14003bce1  jnz     short loc_14003BCF8
0x14003bce3  add     rcx, 10h; Event
0x14003bce7  xor     r8d, r8d; Wait
0x14003bcea  xor     edx, edx; Increment
0x14003bcec  call    cs:__imp_KeSetEvent
0x14003bcf3  nop     dword ptr [rax+rax+00h]
0x14003bcf8  test    rbx, rbx
0x14003bcfb  jz      short loc_14003BD28
0x14003bcfd  mov     rcx, [rbx+18h]; this
0x14003bd01  test    rcx, rcx
0x14003bd04  jz      short loc_14003BD0B
0x14003bd06  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003bd0b  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003bd12  mov     rdx, rbx; Entry
0x14003bd15  add     rcx, 440h; Lookaside
0x14003bd1c  call    cs:__imp_ExFreeToLookasideListEx
0x14003bd23  nop     dword ptr [rax+rax+00h]
0x14003bd28  add     rsp, 20h
0x14003bd2c  pop     r14
0x14003bd2e  pop     rdi
0x14003bd2f  pop     rsi
0x14003bd30  pop     rbp
0x14003bd31  pop     rbx
0x14003bd32  retn
```
