# VfsPkgCtxRelease

- ea: `0x140005888`
- end: `0x1400058fd`
- name: `VfsPkgCtxRelease`
- size: `117`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400059b0`
- `0x140009218`
- `0x140009784`
- `0x140009d44`

## callees

- `0x140005888`
- `0x1400093f0`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400058ba`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400058ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400058ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400058ce`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400058e5`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400058e5`

## pseudocode

```c
void __fastcall VfsPkgCtxRelease(__int64 a1)
{
  struct _ERESOURCE **v2; // rbx
  struct _ERESOURCE *v3; // rbx

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 32), 0xFFFFFFFF) == 1 )
  {
    v2 = (struct _ERESOURCE **)(a1 + 40);
    if ( *(_QWORD *)(a1 + 40) )
    {
      VfsRemoveMappings(a1 + 40);
      v3 = *v2;
      ExDeleteResourceLite(v3);
      ExFreePoolWithTag(v3, 0x72454656u);
    }
    ExFreeToPagedLookasideList(&stru_14001F500, (PVOID)(a1 - 32));
  }
}

```

## disassembly

```asm
0x140005888  mov     [rsp+arg_0], rbx
0x14000588d  push    rdi
0x14000588e  sub     rsp, 20h
0x140005892  mov     rdi, rcx
0x140005895  or      eax, 0FFFFFFFFh
0x140005898  lock xadd [rcx+20h], eax
0x14000589d  cmp     eax, 1
0x1400058a0  jnz     short loc_1400058F1
0x1400058a2  lea     rbx, [rcx+28h]
0x1400058a6  cmp     qword ptr [rbx], 0
0x1400058aa  jz      short loc_1400058DA
0x1400058ac  mov     rcx, rbx
0x1400058af  call    VfsRemoveMappings
0x1400058b4  mov     rbx, [rbx]
0x1400058b7  mov     rcx, rbx; Resource
0x1400058ba  call    cs:__imp_ExDeleteResourceLite
0x1400058c1  nop     dword ptr [rax+rax+00h]
0x1400058c6  mov     edx, 72454656h; Tag
0x1400058cb  mov     rcx, rbx; P
0x1400058ce  call    cs:__imp_ExFreePoolWithTag
0x1400058d5  nop     dword ptr [rax+rax+00h]
0x1400058da  lea     rdx, [rdi-20h]; Entry
0x1400058de  lea     rcx, stru_14001F500; Lookaside
0x1400058e5  call    cs:__imp_ExFreeToPagedLookasideList
0x1400058ec  nop     dword ptr [rax+rax+00h]
0x1400058f1  mov     rbx, [rsp+28h+arg_0]
0x1400058f6  add     rsp, 20h
0x1400058fa  pop     rdi
0x1400058fb  retn
```
