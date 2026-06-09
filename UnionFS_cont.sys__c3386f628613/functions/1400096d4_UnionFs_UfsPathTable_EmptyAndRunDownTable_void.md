# UnionFs::UfsPathTable::EmptyAndRunDownTable(void)

- ea: `0x1400096d4`
- end: `0x1400097af`
- name: `?EmptyAndRunDownTable@UfsPathTable@UnionFs@@QEAAXXZ`
- size: `219`
- prototype: `void __fastcall(UnionFs::UfsPathTable *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140006390`
- `0x1400086b0`
- `0x14002333c`
- `0x14003b6d4`
- `0x14005572c`
- `0x14005a338`

## callees

- `0x140005d9c`
- `0x1400096d4`
- `0x140079a6c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009766`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009766`
- `ntoskrnl!ExRundownCompletedCacheAware` at `0x140009715`
- `ntoskrnl!ExRundownCompletedCacheAware` at `0x140009715`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140009702`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140009702`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000978d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000978d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009799`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009799`
- `FLTMGR!FltReleaseContext` at `0x14000974c`
- `FLTMGR!FltReleaseContext` at `0x14000974c`

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
0x1400096d4  push    rbx
0x1400096d6  push    rbp
0x1400096d7  push    rsi
0x1400096d8  push    rdi
0x1400096d9  sub     rsp, 28h
0x1400096dd  mov     rbx, rcx
0x1400096e0  lea     rdx, [rcx+20h]
0x1400096e4  lea     rcx, [rsp+48h+Resource]
0x1400096e9  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x1400096ee  cmp     byte ptr [rbx+94h], 0
0x1400096f5  jnz     loc_140009783
0x1400096fb  mov     rcx, [rbx+88h]; RunRef
0x140009702  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140009709  nop     dword ptr [rax+rax+00h]
0x14000970e  mov     rcx, [rbx+88h]; RunRefCacheAware
0x140009715  call    cs:__imp_ExRundownCompletedCacheAware
0x14000971c  nop     dword ptr [rax+rax+00h]
0x140009721  lea     rsi, [rbx+8]
0x140009725  mov     rdi, [rsi]
0x140009728  cmp     rdi, rsi
0x14000972b  jz      short loc_140009774
0x14000972d  mov     rcx, [rdi+8]
0x140009731  mov     rax, [rdi]
0x140009734  mov     [rcx], rax
0x140009737  mov     [rax+8], rcx
0x14000973b  mov     rcx, [rdi+18h]; Context
0x14000973f  mov     qword ptr [rdi+18h], 0
0x140009747  test    rcx, rcx
0x14000974a  jz      short loc_140009758
0x14000974c  call    cs:__imp_FltReleaseContext
0x140009753  nop     dword ptr [rax+rax+00h]
0x140009758  lea     rcx, [rdi+10h]
0x14000975c  call    ??1?$unique_ptr@VUfsPathTierNode@UnionFs@@U?$default_delete@VUfsPathTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(void)
0x140009761  xor     edx, edx; Tag
0x140009763  mov     rcx, rdi; P
0x140009766  call    cs:__imp_ExFreePoolWithTag
0x14000976d  nop     dword ptr [rax+rax+00h]
0x140009772  jmp     short loc_140009725
0x140009774  mov     qword ptr [rsi+10h], 0
0x14000977c  mov     byte ptr [rbx+94h], 1
0x140009783  mov     rcx, [rsp+48h+Resource]; Resource
0x140009788  test    rcx, rcx
0x14000978b  jz      short loc_1400097A5
0x14000978d  call    cs:__imp_ExReleaseResourceLite
0x140009794  nop     dword ptr [rax+rax+00h]
0x140009799  call    cs:__imp_KeLeaveCriticalRegion
0x1400097a0  nop     dword ptr [rax+rax+00h]
0x1400097a5  add     rsp, 28h
0x1400097a9  pop     rdi
0x1400097aa  pop     rsi
0x1400097ab  pop     rbp
0x1400097ac  pop     rbx
0x1400097ad  retn
```
