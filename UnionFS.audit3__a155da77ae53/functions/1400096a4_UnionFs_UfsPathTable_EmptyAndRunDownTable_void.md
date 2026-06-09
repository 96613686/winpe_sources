# UnionFs::UfsPathTable::EmptyAndRunDownTable(void)

- ea: `0x1400096a4`
- end: `0x14000977f`
- name: `?EmptyAndRunDownTable@UfsPathTable@UnionFs@@QEAAXXZ`
- size: `219`
- prototype: `void __fastcall(UnionFs::UfsPathTable *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140006390`
- `0x14000867c`
- `0x1400233dc`
- `0x14003b7f4`
- `0x1400558ac`
- `0x14005a4b8`

## callees

- `0x140005d9c`
- `0x1400096a4`
- `0x140079d8c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009736`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009736`
- `ntoskrnl!ExRundownCompletedCacheAware` at `0x1400096e5`
- `ntoskrnl!ExRundownCompletedCacheAware` at `0x1400096e5`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400096d2`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400096d2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000975d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000975d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009769`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009769`
- `FLTMGR!FltReleaseContext` at `0x14000971c`
- `FLTMGR!FltReleaseContext` at `0x14000971c`

## pseudocode

```c
void __fastcall UnionFs::UfsPathTable::EmptyAndRunDownTable(PEX_RUNDOWN_REF_CACHE_AWARE *this)
{
  __int64 **v2; // rsi
  __int64 *v3; // rdi
  __int64 *v4; // rcx
  __int64 v5; // rax
  void *v6; // rcx
  PERESOURCE Resource; // [rsp+50h] [rbp+8h] BYREF

  FsFltWil::AcquireResourceExclusive(&Resource, this + 4);
  if ( !*((_BYTE *)this + 148) )
  {
    ExWaitForRundownProtectionReleaseCacheAware(this[17]);
    ExRundownCompletedCacheAware(this[17]);
    v2 = (__int64 **)(this + 1);
    while ( 1 )
    {
      v3 = *v2;
      if ( *v2 == (__int64 *)v2 )
        break;
      v4 = (__int64 *)v3[1];
      v5 = *v3;
      *v4 = *v3;
      *(_QWORD *)(v5 + 8) = v4;
      v6 = (void *)v3[3];
      v3[3] = 0;
      if ( v6 )
        FltReleaseContext(v6);
      utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(v3 + 2);
      ExFreePoolWithTag(v3, 0);
    }
    this[3] = 0;
    *((_BYTE *)this + 148) = 1;
  }
  if ( Resource )
  {
    ExReleaseResourceLite(Resource);
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x1400096a4  push    rbx
0x1400096a6  push    rbp
0x1400096a7  push    rsi
0x1400096a8  push    rdi
0x1400096a9  sub     rsp, 28h
0x1400096ad  mov     rbx, rcx
0x1400096b0  lea     rdx, [rcx+20h]
0x1400096b4  lea     rcx, [rsp+48h+Resource]
0x1400096b9  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x1400096be  cmp     byte ptr [rbx+94h], 0
0x1400096c5  jnz     loc_140009753
0x1400096cb  mov     rcx, [rbx+88h]; RunRef
0x1400096d2  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1400096d9  nop     dword ptr [rax+rax+00h]
0x1400096de  mov     rcx, [rbx+88h]; RunRefCacheAware
0x1400096e5  call    cs:__imp_ExRundownCompletedCacheAware
0x1400096ec  nop     dword ptr [rax+rax+00h]
0x1400096f1  lea     rsi, [rbx+8]
0x1400096f5  mov     rdi, [rsi]
0x1400096f8  cmp     rdi, rsi
0x1400096fb  jz      short loc_140009744
0x1400096fd  mov     rcx, [rdi+8]
0x140009701  mov     rax, [rdi]
0x140009704  mov     [rcx], rax
0x140009707  mov     [rax+8], rcx
0x14000970b  mov     rcx, [rdi+18h]; Context
0x14000970f  mov     qword ptr [rdi+18h], 0
0x140009717  test    rcx, rcx
0x14000971a  jz      short loc_140009728
0x14000971c  call    cs:__imp_FltReleaseContext
0x140009723  nop     dword ptr [rax+rax+00h]
0x140009728  lea     rcx, [rdi+10h]
0x14000972c  call    ??1?$unique_ptr@VUfsPathTierNode@UnionFs@@U?$default_delete@VUfsPathTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(void)
0x140009731  xor     edx, edx; Tag
0x140009733  mov     rcx, rdi; P
0x140009736  call    cs:__imp_ExFreePoolWithTag
0x14000973d  nop     dword ptr [rax+rax+00h]
0x140009742  jmp     short loc_1400096F5
0x140009744  mov     qword ptr [rsi+10h], 0
0x14000974c  mov     byte ptr [rbx+94h], 1
0x140009753  mov     rcx, [rsp+48h+Resource]; Resource
0x140009758  test    rcx, rcx
0x14000975b  jz      short loc_140009775
0x14000975d  call    cs:__imp_ExReleaseResourceLite
0x140009764  nop     dword ptr [rax+rax+00h]
0x140009769  call    cs:__imp_KeLeaveCriticalRegion
0x140009770  nop     dword ptr [rax+rax+00h]
0x140009775  add     rsp, 28h
0x140009779  pop     rdi
0x14000977a  pop     rsi
0x14000977b  pop     rbp
0x14000977c  pop     rbx
0x14000977d  retn
```
